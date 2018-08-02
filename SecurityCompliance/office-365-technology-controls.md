---
title: "Office 365 Technology Controls"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "Summary: An overview of Microsoft's technology control practices for Office 365."
---

# Office 365 Technology Controls 

Microsoft uses several tools and technologies to control, manage, and audit access to Customer Data in Exchange Online and SharePoint Online, including Lockbox and Customer Lockbox, multi-factor authentication, and more. Yammer Enterprise uses similar controls, as described in [Yammer Enterprise Access Controls](/office365/enterprise/office-365-yammer-enterprise-access-controls).

Office 365 engineers have zero standing access to Office 365 Customer Data, and they must go through an approval process that includes both Microsoft and – if the customer licenses the Customer Lockbox feature for Exchange Online and SharePoint Online – customer approval, before access to Customer Data for service operations can occur. When approval is granted, service-specific administrative accounts are provisioned just-in-time with just enough access to perform the tasks required by the service request.

## Lockbox and Customer Lockbox
Although it is extremely rare, a customer could request assistance from Microsoft that may expose a Microsoft engineer to the customer's content to assist them with an issue. To control access to Exchange Online (which includes any Skype for Business data stored in the users' mailboxes (Skype for Business coverage does not include Skype Meeting Broadcast recordings or content uploaded to meetings by users)) and SharePoint Online (which includes OneDrive for Business), Microsoft uses an access control system called Lockbox. Before any Microsoft engineer can access any Exchange Online or SharePoint Online systems or data, they must submit an access request using Lockbox. Using Lockbox is required for all elevated access to Exchange Online or SharePoint Online.

Lockbox processes requests for permissions that grant engineers the ability to perform operational and administrative functions within the service. Engineers submit requests through Lockbox, which must be approved by a manager prior to the engineer gaining the ability to access Customer Data. Upon manager approval, the engineer has time-limited and scope-limited access to Customer Data to work on the customer's issue.

Customer Lockbox for Office 365 can help you meet compliance obligations, such as those found in FedRAMP and HIPAA, if you need procedures in place for explicit data access authorization. In the rare instance when a Microsoft service engineer needs access to your data, you grant that access only to data required to resolve the issue and for a limited amount of time. Actions taken by the support engineer are logged for auditing purposes and are accessible via the [Office 365 Management Activity API](https://msdn.microsoft.com/en-us/library/office/dn707383.aspx) and the [Security and Compliance Center](http://protection.office.com/). Customer Lockbox inserts the customer into the Lockbox approval process and provides them with the ability to control authorization of Microsoft access to their Exchange Online or SharePoint Online content for service operations.

>**NOTE**: Customer Lockbox is available in [Office 365 Enterprise E5](https://products.office.com/en-us/business/office-365-enterprise-e5-business-software) and as an add-on purchase, but manual action must be taken in the Office 365 admin center (under Service Settings | Customer Lockbox) to enable it. For more information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

All service requests for Exchange Online and SharePoint Online are handled by the Lockbox system. And with Customer Lockbox, any service operation necessitating access to these services with exposure to Customer Data goes through the Lockbox approval process, and then enables the customer to approve or reject the request thereafter.
 
*Figure 1 - Customer Lockbox Workflow*

If the request is rejected by the customer, the Microsoft engineer will not have access to the customer's content and will not be able to complete the service operation. If the request is approved by the customer, the Microsoft engineer will have limited just-in-time access to the customer's content through monitored and constrained management interfaces. With both Lockbox and Customer Lockbox, all approved access is traceable to a unique user, making engineers accountable for their handling of Customer Data.

## Just-in-Time Access
Microsoft uses the just-in-time (JIT) access principle for Office 365 to further mitigate the risk of credential tampering and lateral attacks. JIT removes persistent administrative access to services and replaces those entitlements with the ability to elevate into those roles on demand. Removing persistent rights from administrators ensures that credentials are available only when they are needed, and removes the risk posed to the company in cases of credential theft.

The JIT access model requires engineers to request elevated privileges for a limited period to perform administrative duties. In addition, OCEs use temporary accounts that are created with machine-generated complex passwords and granted only those roles that allow them to perform the necessary tasks. For example, administrative access granted by Lockbox is time-bound, and the amount of time access is granted depends on the role being requested. An engineer specifies the duration of time access needed during the request to the Lockbox system. The Lockbox system will reject requests where the time requested exceeds the maximum permitted time for the elevation. After expiration of the elevation request, administrative access is removed and the temporary account is expired.

When authorized and approved for access (for example, to debug a system), engineers receive a one-time use administrative password that is generated by the authorization system each time a request for elevated access is approved. This password is copied by the engineer into a password safe, is separate from the engineer's credentials for the Microsoft corporate environment, and is good only for the session for which elevated access was approved.

## Constrained Management Interfaces
OCEs use two management interfaces to perform administrative tasks: Remote Desktop through secured Terminal Service Gateways (TSGs) and Remote PowerShell. Within these management interfaces there are software policies and access controls that place significant restrictions on what applications can be executed and what commands and cmdlets are available. 

Office 365 servers restrict concurrent sessions to one session per-service team administrator, per-server. TSGs are configured to allow only a single concurrent session for users, and they do not allow multiple sessions. TSGs allow Office 365 service team administrators to connect to multiple servers concurrently, using a single session per server, so that administrators can effectively perform their duties. Service team administrators do not have any permissions on the TSGs themselves. The TSG is used only to enforce multi-factor authentication (MFA) and encryption requirements. Once the service team administrator connects to a specific server through a TSG, the specific server will enforce a session limit of one per administrator.

Usage restrictions and connection and configuration requirements for Office 365 personnel are established by Active Directory group policies. These policies include the following characteristics:
- TSGs are configured to use only [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 validated encryption
- TSG sessions are configured to disconnect after 30 minutes of inactivity
- TSG sessions are configured to automatically log off after 24 hours

Connections to TSGs also require MFA using a separate physical smart card and an account that is separate from the engineer's Microsoft corporate credentials. Engineers are issued different smart cards for various platforms and secrets management platforms are used to ensure secure storage of credentials. TSGs use Active Directory group policies to control who can login to remote servers, the number of allowed sessions, and idle timeout settings. Additional polices are in place to limit access to allowed applications and to restrict Internet access.

In addition to remote access using specially-configured TSGs, Exchange Online allows users with the Service Engineer Operations role to access certain administrative functionality on production servers using Remote PowerShell. To do this, the user must be authorized for read-only (debug) access to the Office 365 production environment. Privilege escalation is enabled the same way it is enabled for TSGs using the Lockbox process.

For remote access, there is a load-balanced virtual IP at each datacenter that serves as a single point of access. The Remote PowerShell cmdlets that can be executed are based on the privilege level identified in the access claim obtained during authentication. These cmdlets are the only administrative functionality that can be accessed and executed by users connecting using this method. Remote PowerShell is used to limit the scope of commands available to the engineer, which is based upon the level of access granted via the Lockbox process. For example, in Exchange Online, Get-Mailbox might be available, but Set-Mailbox would not be.
