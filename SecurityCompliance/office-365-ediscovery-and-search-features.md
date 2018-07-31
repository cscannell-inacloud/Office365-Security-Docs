---
title: "Office 365 eDiscovery and Search Features Overview"
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
description: "Summary: An overview of the eDiscovery feature, and other search features within Office 365 for audit use and transparency."
---

# eDiscovery and Search Features 

## eDiscovery
The eDiscovery feature provides a single place for administrators, compliance officers, and other authorized users to conduct a comprehensive investigation into Office 365 user activity. Security officers with the appropriate permissions can perform searches and place holds on content. The search results are the same results you get from a Content Search, except that an eDiscovery case is created for any holds that are applied. The results from eDiscovery searches are encrypted for security, and the exported data can be analyzed using [Advanced eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## Content Search
[Content Search](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) is a new eDiscovery search tool in the Security & Compliance Center that provides improved scaling and performance capabilities over previous eDiscovery search tools. You can use Content Search to search mailboxes, public folders, SharePoint Online sites, and OneDrive for Business locations. Content Search is specifically designed for very large searches. There are no limits on the number of mailboxes and sites that you can search. There are also no limits on the number of searches that can run at the same time. After you run a search, the number of content sources and an estimated number of search results are displayed in the details pane on the search page, where you can preview the results, or export them to a local computer. If your organization has an Office 365 Enterprise E5 subscription, you can also [prepare the results](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) for analysis using the powerful analytics features of [Office 365 Advanced eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## Audit Log Search
In addition to tracking changes in their Office 365 organization, customers can also view audit reports and export audit logs. Once auditing is enabled for an Office 365 tenant, user and administrative activity for that tenant is recorded in event logs and made searchable. For example, you can use mailbox audit logging to track actions performed on a mailbox by users other than the mailbox owner. Further, compliance officers can use the search and filter capabilities to see if a user has viewed or downloaded a specific document, or if an administrator has performed user management activities or made changes to the tenant configuration in the past 90 days. Search results can contain valuable forensic information about specific activities that were conducted by a user or an administrator. See [Audited activities in Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents) for a description of the user and administrative activities that are logged in Office 365.

Events from SharePoint Online and OneDrive for Business are displayed in the log within 15 minutes of their occurrence. Events from Exchange Online appear in the audit logs within 12 hours of occurrence. Login events from Azure AD are available within 15 minutes of occurrence, and other directory events from Azure AD are available within 6 hours of occurrence. Events in audit log search results can also be exported for further analysis. (A maximum of 50,000 entries can be exported from a single audit log search. To export more entries that this limit, either reduce the date range, or run multiple audit log searches.)

The following table details some of the information that is displayed in activity reports.

| Property | Description |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Date | Date and time of the event |
| User | User who performed the action |
| ClientIP | IPv4 or IPv6 address of the device that was used when the activity was logged. |
| CreationTime | Date and time in Coordinated Universal Time (UTC) when the user performed the activity. |
| EventSource | Identifies that an event occurred. Possible values are SharePoint and ObjectModel. |
| ID | ID of the report entry. The ID uniquely identifies the report entry. |
| Operation | Name of the user or activity, which corresponds to the value selected in the Display results for this user activity. |
| OrganizationId | GUID for the organization's Office 365 service where the event occurred. |
| UserAgent | Information about the user's browser as provided by the browser. |
| UserId | User who performed the action (specified in the Operation property) that resulted in the record being logged. |
| UserType | Type of user that performed the operation. The following values indicate the user type. |
|  | 0   Indicates a regular user. |
|  | 2   Indicates an administrator in your Office 365 organization. |
|  | 3   Indicates a Microsoft datacenter administrator or datacenter system account. |
| Workload | Office 365 service in which the activity occurred. Possible values for this property are: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Azure Active Directory Reports |

*Table 1 - Office 365 Activity Report details*

For detailed steps to search Office 365 audit logs, see [Searching audit logs in the Office 365 Security & Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## Search Unified Audit Log
The Audit Log Search feature in the Security & Compliance Center can be used to search the unified audit log. Office 365 also provides the ability to search this log using remote PowerShell. Specifically, the [Search-UnifiedAuditLog cmdlet](https://msdn.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) in Exchange Online PowerShell can be used to search the unified audit log of events relating to user operations from Exchange Online, SharePoint Online, OneDrive for Business, and Azure AD. You can search for all events in a specified date range, or you can filter the results based on specific criteria, such as a specific action, the user who performed the action, or the target object. Administrators can use up to 3 simultaneously running Exchange Online PowerShell sessions to split up large date range searches.
