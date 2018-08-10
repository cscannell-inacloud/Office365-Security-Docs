---
title: "Office 365 Data Retention, Deletion, and Destruction Overview"
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
description: "An overview of Microsoft's policies for Office 365 regarding data retention, deletion, and destruction."
---

# Office 365 Data Retention, Deletion, and Destruction Overview

## Introduction
Microsoft has a Data Handling Standard policy for Office 365 that specifies how long customer data will be retained after being deleted. Generally, within Office 365, there are two scenarios in which customer data is deleted:
- **Active Deletion** - A user deletes data, or data private to a user is deleted after that user is deleted by the administrator of an active tenant.
- **Passive Deletion** - The tenant subscription ends.

Microsoft's Data Handling Standard policy for Office 365 specifies how long data will be retained in each of these scenarios. The following sections describe the categories of data (based on Microsoft's Office 365 Asset Classification Standard) and the retention periods for active and passive deletion scenarios.

## Active Deletion Retention

| Data Category | Retain at Least | Retain at Most |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Access Control Data | N/A | N/A |
| Customer Content | 7 days | 30 days |
| End User Identifiable Information | 90 days | 180 days |
| Account Data | 1 year | 3 years |
| Organization Identifiable Information | 90 days | 180 days |
| System Metadata | See Security Logs | See Security Logs |
| Security Logs | Min 1 year | Max 1 year |
| Exchange Online Archiving Logs | Min 3 years | Max 3 years |

## Passive Deletion Retention

| Data Category | Retain at Least | Retain at Most |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Access Control Data | 90 days (for content recovery) | 180 days (for content recovery) |
| Customer Content | 90 days (limited-function account) | 180 days |
| End User Identifiable Information | 90 days | 180 days |
| Account Data | 1 year | 3 years |
| Organization Identifiable Information | 90 days | 180 days |
| System Metadata | See Security Logs | See Security Logs |
| Security Logs | Min 1 year | Max 1 year |
| Exchange Online Archiving Logs | Min 3 years | Max 3 years |

## Subscription Rentention

Customer content is defined as Exchange Online mailbox content (email body, calendar entries, and the content of email attachments, and if applicable, Skype for Business content), SharePoint Online site content and the files stored within sites, and files uploaded to OneDrive for Business or Skype for Business.

At all times during the term of a subscription, a subscriber can access and extract customer data stored in Office 365. Except for free trials and LinkedIn services, Microsoft retains customer data stored in Office 365 in a limited-function account for 90 days after the expiration or termination of the subscription to enable the subscriber to extract the data. (In the case of a free trial, when the trial expires, it moves into a grace period, giving you 30 days (for most trials, in most countries and regions) to purchase Office 365. If you decide not to buy Office 365, you can let your trial expire or cancel it. Soon after the 30-day grace period, your trial account information and data is permanently erased.)

After the 90-day retention period ends, Microsoft disables the account and deletes the customer data. No more than 180 days after expiration or termination of a subscription to Office 365, Microsoft will disable the account and delete all customer data from the account. Once the maximum retention period for any data has elapsed, the data is rendered commercially unrecoverable.

Microsoft also has a Data Handling Standard policy that addresses the recycling and disposal of disk drives and failed or retiring servers. Before re-using any disk drives within Office 365, Microsoft performs a physical sanitization process that is compliant with NIST SP 800-88. Disk drives that cannot be re-used are disposed of using a physical destruction process that is performed on-site within the datacenter containing the disks being destroyed. These procedures are performed by Microsoft Cloud Infrastructure & Operations (MCIO). For more information, see the MCIO audit reports on the [Service Trust Preview](https://aka.ms/STP).

## Expedited Deletion
At all times during the term of a subscription, a subscriber can contact Microsoft Support and request expedited subscription deprovisioning. In this process, all user data, including data in SharePoint Online, Exchange Online that may be under hold or stored in inactive mailboxes, is deleted three days after the administrator enters the lockout code provided by Microsoft. For more information on expedited deprovisioning, see [Cancel Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## Related Links
- [Exchange Online Data Deletion](/office365/enterprise/office-365-exchange-online-data-deletion)
- [SharePoint Online Data Deletion](/office365/enterprise/office-365-sharepoint-online-data-deletion)
- [Skype for Business Data Deletion](/office365/enterprise/office-365-skype-data-deletion)
- [Immutability in Office 365](/office365/enterprise/office-365-data-immutability)
- [Data Destruction](/office365/enterprise/office-365-data-destruction)