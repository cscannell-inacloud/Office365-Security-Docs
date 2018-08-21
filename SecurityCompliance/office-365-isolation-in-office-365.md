---
title: "Office 365 Isolation and Access Control in Office 365"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "Summary: An explanation of isolation and access control within the various applications of Office 365."
---

# Isolation and Access Control in Office 365

Azure Active Directory and Office 365 use a highly complex data model that includes tens of services, hundreds of entities, thousands of relationships, and tens of thousands of attributes (entities, relationships and attributes are often application-specific). At a high level, Azure Active Directory and the service directories are the containers of tenants and recipients, and they are kept in sync using state-based replication protocols. In addition to the directory information held within Azure Active Directory, each of the services also have their own directory services infrastructure (e.g., Exchange Online Directory Services, SharePoint Online Directory Services, etc.). 
 
![Office 365 tenant data sync](media/office-365-isolation-tenant-data-sync.png)

Within this model, there is no single source of directory data. Every individual piece of data is owned by a specific system, but no single system holds all the data. Office 365 services cooperate with Azure Active Directory to realize the data model. Azure Active Directory is the "system of truth" for shared data, which is typically small and static data used often by every service. The federated model used within Office 365 and Azure Active Directory provides the shared view of the data.

Office 365 uses both physical storage and Azure cloud storage. Exchange Online (including Exchange Online Protection) and Skype for Business use their own storage for customer data. SharePoint Online leverages both its SQL Server storage and Azure storage, which necessitates the need for additional isolation of customer data at the storage level.

## Exchange Online
Exchange Online stores customer data within mailboxes that are hosted within Extensible Storage Engine (ESE) databases called mailbox databases. This includes user mailboxes, linked mailboxes, shared mailboxes and public folder mailboxes. User mailboxes may also include saved Skype for Business content, such as conversation histories. User mailbox content includes emails and email attachments, calendaring and free/busy information, contacts, tasks, notes, Groups, and inference data.

Each mailbox database within Exchange Online contains mailboxes from multiple tenants. All mailboxes are secured by authorization code, including within a tenancy. As with an on-premises deployment of Exchange, by default only the assigned user has access to a mailbox. The access control list (ACL) that secures a mailbox contains an identity that is authenticated by Azure Active Directory at the tenant level. The mailboxes for a given tenant are limited to identities authenticated against that tenant's authentication provider, which include only users from that tenant. Content belonging to TenantA cannot in any way be obtained by users in TenantB, unless explicitly approved by TenantA.

## Skype for Business
Skype for Business stores data in a variety of places:
- User and account information, which includes connection endpoints, tenant IDs, dial plans, roaming settings, presence state, contact lists, etc., is stored in the Skype for Business Active Directory servers, as well as in various Skype for Business database servers. Contact lists are stored in the user's Exchange Online mailbox if the user is enabled for both products, or on Skype for Business servers if the user is not. Skype for Business database servers are not partitioned per-tenant, but multi-tenancy isolation of data is enforced through RBAC.
- Meeting content, such as content users upload during Skype for Business meetings, is stored on Distributed File System shares. This content can also be archived in Exchange Online provided archiving is enabled. The DFS shares are not partitioned per-tenant but the content is secured with ACLs and multi-tenancy is enforced through RBAC.
- Call detail records, which is the activity history, such as call history, IM sessions, application sharing, IM history, etc., can also be stored in Exchange Online, but most call detail records are temporarily stored on call detail record (CDR) servers. Content is not partitioned per tenant, but multi-tenancy is enforced through RBAC.

## SharePoint Online
There are several independent mechanisms unique to SharePoint Online that provide data isolation. SharePoint Online stores objects as abstracted code within application databases. For example, when a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.

If a user could gain direct access to the storage containing the data, the content would not be interpretable to a human or any system other than SharePoint Online. These mechanisms include security access control and properties. As described above, all SharePoint Online resources are secured by the authorization code and RBAC policy, including within a tenancy. The access control list (ACL) that secures a resource contains an identity that is authenticated at the tenant level. As with Exchange Online, in SharePoint Online, data for a given tenant are limited to identities authenticated against that tenant's authentication provider, which include only users from that tenant.

In addition to the ACLs, a tenant level property that specifies the authentication provider (which is the tenant-specific Azure Active Directory), is written once and cannot be changed once set. Once the authentication provider tenant property has been set for a tenant, it cannot be changed using any APIs exposed to a tenant.

A unique *SubscriptionId* is also used for each tenant. All customer sites are owned by a tenant and are assigned a *SubscriptionId* unique to the tenant. The *SubscriptionId* property on a site is written once and cannot be changed. Once a site is assigned to a tenant, it cannot be moved to a different tenant later using the content store API. The *SubscriptionId* is also the key that is used to create the security scope for the authentication provider and is tied to the tenant.

SharePoint Online uses SQL Server and Azure storage for the storing of content. At the SQL level, the partition key for the content store is *SiteId*. When running a SQL query, SharePoint Online uses a *SiteId* that has been verified as part of a tenant-level *SubscriptionId* check.

SharePoint Online stores file binary blobs (e.g., the file streams) in Microsoft Azure. Each SharePoint Online farm has its own Microsoft Azure account and all the blobs saved in Azure are encrypted individually using a key that is stored in the SQL content store. The encryption key is not exposed directly to the end user, and is protected in code by the authorization layer. Finally, SharePoint Online has real-time monitoring in place to detect when an HTTP request reads or writes data for more than one tenant. It does this by tracking the *SubscriptionId* of the request identity against the *SubscriptionId* of the resource being accessed. A request accessing resources of more than one tenant should never happen by end-user. It can happen for service requests in a multi-tenant environment, though. For example, the search crawler pulls content changes for an entire database all at once. This usually involves querying sites of more than one tenant in a single service request, which is done for efficiency reasons.
