---
title: "Office 365 Administrative Access Controls Overview"
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
description: "Summary: An overview of Office 365's Administrative Access Controls and data categorization."
---

# Office 365 Administrative Access Controls Overview 

## Introduction
Microsoft has invested heavily and accordingly in systems and controls that automate most Office 365 operations while intentionally limiting Microsoft's access to customer content. Humans govern the service, and software operates the service. This enables Microsoft to manage Office 365 at scale, as well as manage the risks of internal threats to customer content such as malicious actors, the spear-phishing of a Microsoft engineer, and so forth.

By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365. A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time, but only when necessary for service operations, and only when approved by a member of Microsoft senior management (and for customers that are licensed for the Customer Lockbox feature, the customer).

Microsoft provides online services, including Office 365, using multiple forms of cloud delivery:

- Public Clouds, which include multi-tenant versions of Office 365, Azure, and other services that are hosted in North America, South America, Europe, Asia, Australia, etc.
- National Clouds, which include all sovereign and third party-operated clouds outside of the United States (except for those noted above), such as Office 365 in China (which is operated by 21Vianet), and Office 365 in Germany (which is operated by Microsoft but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).
- Government Clouds, which include Office 365 and Azure services that are available to United States government customers.

For purposes of this article, Office 365 services include [Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx), [Exchange Online Protection](https://technet.microsoft.com/en-us/library/exchange-online-protection-service-description.aspx), [SharePoint Online](https://technet.microsoft.com/en-us/library/sharepoint-online-service-description.aspx) (including [OneDrive for Business](https://technet.microsoft.com/en-us/library/onedrive-for-business-service-description.aspx)) and [Skype for Business](https://technet.microsoft.com/en-us/library/skype-for-business-online-service-description.aspx), with additional information about some [Yammer Enterprise](https://technet.microsoft.com/en-us/library/yammer-service-description.aspx) access controls. Other Office 365 services are out of scope for this article.

## Office 365 Access Controls
For access control purposes, Office 365 data is categorized as either Customer Data or other types of data. Customer Data is all data provided by or on behalf of a customer through the customer's use of Office 365 services, such as customer content (content directly created or uploaded by Office 365 users including emails, SharePoint Online content, instant messages, calendar items, documents, and contacts stored in Office 365) and end-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content). 

Other types of data include account data (includes administrative data, which is the information provided by administrators when they sign-up or purchase services, and payment data, which is information about payment instruments, such as credit card details), organizationally identifiable information (data that can be used to identify a tenant; or usage data; it is not linkable to an individual user and does not include customer content), and system metadata (includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants).

Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data (used to manage access to other types of data or functions within the environment, including access to customer content or EUII; it includes Microsoft passwords, security certificates, and other authentication-related data) or unapproved physical, logical, or remote access to the Office 365 production environment.

The access controls used by Microsoft for operating Office 365 can be grouped into three categories:
1.	Isolation Controls
2.	Personnel Controls
3.	Technology Controls

When combined, these controls help prevent and detect malicious actions in Office 365. In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.

Office 365 allows you to manage your data much in the same way data is managed in on-premises environments. The person who signs up an organization for Office 365 automatically becomes a global administrator (admin). The global admin has access to all features in the management portals (e.g., admin centers and remote PowerShell), and can create or edit users, assign admin roles to others, reset user passwords, manage user licenses, manage domains, and approve Customer Lockbox requests, among other things. We recommend that each organization designate at least two admin accounts, and depending on the size of your organization, you may want to designate several admins who serve different functions. For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/en-us/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/en-us/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).


## Related Links

- [Isolation Controls](/office365/enterprise/office-365-isolation-controls)
- [Personnel Controls](/office365/enterprise/office-365-personnel-controls)
- [Technology Controls](/office365/enterprise/office-365-technology-controls)
- [Monitoring and Auditing Access Controls](/office365/enterprise/office-365-monitoring-and-auditing-access-controls)
- [Yammer Enterprise Access Controls](/office365/enterprise/office-365-yammer-enterprise-access-controls)