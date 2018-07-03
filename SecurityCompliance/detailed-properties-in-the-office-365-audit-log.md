---
title: "Detailed properties in the Office 365 audit log"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/8/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- BCS160
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: "Descriptions of additional properties that are included in an Office 365 audit log record."
---

# Detailed properties in the Office 365 audit log

When you export the results of an audit log search from the Office 365 Security &amp; Compliance Center, you have the option to download all the results that meet your search criteria. You do this by selecting **Export results** \> **Download all results** on the **Audit log search** page in the Security &amp; Compliance Center. For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
 When your export all results for an audit log search, the raw data from the Office 365 unified audit log is copied to a comma separated value (CSV) file this is downloaded to your local computer. This file contains additional information from the audit log entry in a column named **Detail**. This column contains a multi-value property for multiple properties from the audit log record. Each of the **property:value** pairs in this multi-value property are separated by a comma. 
  
The following table describes the properties that are included—depending on the Office 365 service in which an event occurs—in the multi-property **Detail** column. The **Office 365 service that has this property** column indicates the service and type of activity (user or admin) that includes the property. For more detailed information about these properties or about properties that might not be listed in this topic, see [Office 365 Management Activity API Schema](https://go.microsoft.com/fwlink/p/?LinkId=717993).
  
> [!TIP]
> You can use the Power Query in Excel to split this column into multiple columns so that each property will have its own column. This will let you sort and filter on one or more of these properties. To learn how to do this, see the "Split a column by delimiter" section in [Split a column of text (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662). 
  
|**Property**|**Description**|**Office 365 service that has this property**|
|:-----|:-----|:-----|
|Actor  <br/> |The user or service account that performed the action. The  <br/> |Azure Active Directory  <br/> |
|AddOnName  <br/> |The name of an add-on that was added, removed, or updated in a team. The type of add-ons in Microsoft Teams are a bot, a connector, or a tab.  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |The type of an add-on that was added, removed, or updated in a team. The following values indicate the type of add-on.  <br/> 1   Indicates a bot. 2   Indicates a connector. 3   Indicates a tab. |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |The type of Azure Active Directory event. The following values indicate the type of event.  <br/> 0   Indicates an account login event. 1   Indicates an Azure application security event. |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |The ID of a Microsoft Teams channel. The team that the channel is located in is identified by the **TeamName** and **TeamGuid** properties.  <br/> |Microsoft Teams  <br/> |
|ChannelName  <br/> |The name of a Microsoft Teams channel. The team that the channel is located in is identified by the **TeamName** and **TeamGuid** properties.  <br/> |Microsoft Teams  <br/> |
|Client  <br/> |The client device, the device OS, and the device browser used for the login event (for example, Nokia Lumnia 920; Windows Phone 8; IE Mobile 11).  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |Information about the email client that was used to perform the operation, such as a browser version, Outlook version, and mobile device information  <br/> |Exchange (mailbox activity)  <br/> |
|ClientIP  <br/> |The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.  <br/> |Exchange and Azure Active Directory  <br/> |
|ClientIPAddress  <br/> |Same as ClientIP.  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |The date and time in Coordinated Universal Time (UTC) when the user performed the activity.  <br/> |All  <br/> |
|DestinationFileExtension  <br/> |The file extension of a file that is copied or moved. This property is displayed only for the FileCopied and FileMoved user activities.  <br/> |SharePoint  <br/> |
|DestinationFileName  <br/> |The name of the file is copied or moved. This property is displayed only for the FileCopied and FileMoved actions.  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |The URL of the destination folder where a file is copied or moved. The combination of the values for the **SiteURL**, the **DestinationRelativeURL**, and the **DestinationFileName** properties is the same as the value for the **ObjectID** property, which is the full path name for the file that was copied. This property is displayed only for the FileCopied and FileMoved user activities.  <br/> |SharePoint  <br/> |
|EventSource  <br/> |Identifies that an event occurred in SharePoint. Possible values are **SharePoint** and **ObjectModel**.  <br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |For Exchange admin activity, specifies whether the cmdlet was run by a user in your organization, by Microsoft datacenter personnel or a datacenter service account, or by a delegated administrator. The value **False** indicates that the cmdlet was run by someone in your organization. The value **True** indicates that the cmdlet was run by datacenter personnel, a datacenter service account, or a delegated administrator.  <br/> For Exchange mailbox activity, specifies whether a mailbox was accessed by a user outside your organization.  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |The extended properties for an the Azure Active Directory event.  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |The ID of the report entry. The ID uniquely identifies the report entry.  <br/> |All  <br/> |
|InternalLogonType  <br/> |Reserved for internal use.  <br/> |Exchange (mailbox activity)  <br/> |
|ItemType  <br/> |The type of object that was accessed or modified. Possible values include **File**, **Folder**, **Web**, **Site**, **Tenant**, and **DocumentLibrary**.  <br/> |SharePoint  <br/> |
|LoginStatus  <br/> |Identifies login failures that might have occurred.  <br/> |Azure Active Directory  <br/> |
|LogonType  <br/> |The type of mailbox access. The following values indicate the type of user who accessed the mailbox.  <br/> 0   Indicates a mailbox owner. 1   Indicates an administrator. 2   Indicates a delegate. 3   Indicates the transport service in the Microsoft datacenter. 4   Indicates a   service account in the Microsoft datacenter. 6   Indicates a delegated administrator. |Exchange (mailbox activity)  <br/> |
|MailboxGuid  <br/> |The Exchange GUID of the mailbox that was accessed.  <br/> |Exchange (mailbox activity)  <br/> |
|MailboxOwnerUPN  <br/> |The email address of the person who owns the mailbox that was accessed.  <br/> |Exchange (mailbox activity)  <br/> |
|Members  <br/> |Lists the users that have been added or removed from a team. The following values indicate the Role type assigned to the user.  <br/> 1   Indicates  the Owner role. 2   Indicates the Member role. 3   Indicates the Guest role. The Members property also includes the name of your organization, and the member's email address.  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (Name, NewValue, OldValue)  <br/> |The property is included for admin events, such as adding a user as a member of a site or a site collection admin group. The property includes the name of the property that was modified (for example, the Site Admin group) the new value of the modified property (such the user who was added as a site admin, and the previous value of the modified object.  <br/> |All (admin activity)  <br/> |
|ObjectID  <br/> |For Exchange admin audit logging, the name of the object that was modified by the cmdlet.  <br/> For SharePoint activity, the full URL path name of the file or folder accessed by a user.  <br/> For Azure AD activity, the name of the user account that was modified.  <br/> |All  <br/> |
|Operation  <br/> |The name of the user or admin activity. The value of this property corresponds to the value that was selected in the **Activities** drop down list. If **Show results for all activities** was selected, the report will included entries for all user and admin activities for all services. For a description of the operations/activities that are logged in the Office 365 audit log, see the **Audited activities** tab in [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).  <br/> For Exchange admin activity, this property identifies the name of the cmdlet that was run.  <br/> |All  <br/> |
|OrganizationID  <br/> |The GUID for your Office 365 organization.  <br/> |All  <br/> |
|Path  <br/> |The name of the mailbox folder where the message that was accessed is located. This property also identifies the folder a where a message is created in or copied/moved to.  <br/> |Exchange (mailbox activity)  <br/> |
|Parameters  <br/> |For Exchange admin activity, the name and value for all parameters that were used with the cmdlet that is identified in the Operation property.  <br/> |Exchange (admin activity)  <br/> |
|RecordType  <br/> |The type of operation indicated by the record. The following values indicate the record type.  <br/> 1   Indicates a record from the  Exchange  admin audit log. 2   Indicates a record from the  Exchange  mailbox audit log for an operation performed on a singled mailbox item. 3   Also indicates a record from the  Exchange  mailbox audit log. This record type indicates the operation was performed on multiple items in the source mailbox (such as moving multiple items to the Deleted Items folder or permanently deleting multiple items). 4   Indicates a site admin operation in SharePoint, such as an administrator or user assigning permissions to a site. 6   Indicates a file or folder-related operation in SharePoint, such as a user viewing or modifying a file. 8   Indicates an admin operation performed in Azure Active Directory. 9   Indicates  OrgId logon events in Azure Active Directory. This record type is being deprecated. 10   Indicates security cmdlet events that were performed by Microsoft personnel in the data center. 11   Indicates Data loss protection (DLP) events in SharePoint. 12   Indicates Sway events. 14   Indicates sharing events in SharePoint. 15   Indicates Secure Token Service (STS) logon events in Azure Active Directory. 18   Indicates Security &amp; Compliance Center events. 20   Indicates Power BI events. 22   Indicates Yammer events. 24   Indicates eDiscovery events. This record type indicates activities that were performed by running content searches and managing eDiscovery cases in the Security &amp; Compliance Center. For more information, see Search for eDiscovery activities in the Office 365 audit log. 25, 26, or 27   Indicates Microsoft Teams events. |All  <br/> |
|ResultStatus  <br/> |Indicates whether the action (specified in the **Operation** property) was successful or not.  <br/> For Exchange admin activity, the value is either **True** (successful) or **False** (failed).  <br/> |All  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indicates that the activity was a Security &amp; Compliance Center event. All Security &amp; Compliance Center activities will have a value of **0** for this property.  <br/> |Office 365 Security &amp; Compliance Center  <br/> |
|SharingType  <br/> |The type of sharing permissions that was assigned to the user that the resource was shared with. This user is identified in the **UserSharedWith** property.  <br/> |SharePoint  <br/> |
|Site  <br/> |The GUID of the site where the file or folder accessed by the user is located.  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |The URL of the site where the file or folder accessed by the user is located.  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |The file extension of the file that was accessed by the user. This property is blank if the object that was accessed is a folder.  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |The name of the file or folder accessed by the user.  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |The URL of the folder that contains the file accessed by the user. The combination of the values for the **SiteURL**, the **SourceRelativeURL**, and the **SourceFileName** properties is the same as the value for the **ObjectID** property, which is the full path name for the file accessed by the user.  <br/> |SharePoint  <br/> |
|Subject  <br/> |The subject line of the message that was accessed.  <br/> |Exchange (mailbox activity)  <br/> |
|TabType  <br/> | The type of tab added, removed, or updated in a team. The possible values for this property are:  <br/> **Excelpin**An Excel tab.  <br/> **Extension** All first-party and third-party apps; such as Planner, VSTS, and Forms.  <br/> **Notes**OneNote tab.  <br/> **Pdfpin**A PDF tab.  <br/> **Powerbi**A PowerBI tab.  <br/> **Powerpointpin**A PowerPoint tab.  <br/> **Sharepointfiles**A SharePoint tab.  <br/> **Webpage**A pinned website tab.  <br/> **Wiki-tab**A wiki tab.  <br/> **Wordpin**A Word tab.  <br/> |Microsoft Teams  <br/> |
|Target  <br/> |The user that the action (identified in the **Operation** property) was performed on. For example, if a guest user is added to SharePoint or a Microsoft Team, that user would be listed in this property.  <br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |The ID of a team in Microsoft Teams.  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |The name of a team in Microsoft Teams.  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |Information about the user's browser. This information is provided by the browser.  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |Identity information about the tenant organization of the user (actor) who performed the action.  <br/> |Azure Active Directory  <br/> |
|UserID  <br/> |The user who performed the action (specified in the **Operation** property) that resulted in the record being logged. Note that records for activity performed by system accounts (such as SHAREPOINT\system or NT AUTHORITY\SYSTEM) are also included in the audit log.  <br/> |All  <br/> |
|UserKey  <br/> |An alternative ID for the user identified in the **UserID** property. For example, this property is populated with the passport unique ID (PUID) for events performed by users in SharePoint. This property also might specify the same value as the **UserID** property for events occurring in other services and events performed by system accounts.  <br/> |All  <br/> |
|UserSharedWith  <br/> |The user that a resource was shared with. This property is included if the value for the **Operation** property is **SharingSet**. This user is also listed in the **Shared with** column in the report.  <br/> |SharePoint  <br/> |
|UserType  <br/> |The type of user that performed the operation. The following values indicate the user type.  <br/> 0   A regular user. 2   An administrator in your Office 365  organization. 3   A Microsoft datacenter administrator or datacenter system account. 4   A system account. 5   An application. 6   A service principal. |All  <br/> |
|Version  <br/> |Indicates the version number of the activity (identified by the **Operation** property) that's logged.  <br/> |All  <br/> |
|Workload  <br/> |The Office 365 service where the activity occurred. The possible values for this property are:  <br/> SharePointOneDriveExchangeAzureActiveDirectoryDataCenterSecurityComplianceSwaySecurityComplianceCenterPowerBIMicrosoftTeams|All  <br/> |
   
Note that the properties described above are also displayed when you click **More information** when viewing the details of a specific event. 
  
![Click More information to view the detailed properties of the audit log event record](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  
[Return to top](detailed-properties-in-the-office-365-audit-log.md#top)
  

