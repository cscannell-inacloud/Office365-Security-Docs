---
title: "Reports in the Office 365 Security &amp; Compliance Center"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'ms.o365.cc.AuditingHelp'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: "Use the Office 365 Security &amp; Compliance Center to get various reports for your SharePoint Online and Exchange Online organization, plus Azure Active Directory reports. 
"
---

# Reports in the Office 365 Security &amp; Compliance Center

You can use the **View reports** page in the Office 365 Security &amp; Compliance Center to quickly access audit reports for your SharePoint Online and Exchange Online organizations. You can also access Azure Active Directory (AD) user sign-in reports, user activity reports, and the Azure AD audit log from the **View reports** page. This is because your paid Office 365 subscription includes a free subscription to Microsoft Azure. The first time that you try to access these Azure reports, you will have to complete a one-time registration process. 
  
> [!TIP]
> To view additional reports about activity in your Office 365 organization, see [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Before you begin**
  
You need the following permissions to view reports in the Security &amp; Compliance Center.
  
- You have to be assigned the Security Reader role in the Exchange admin center (EAC) to view reports in the Security &amp; Compliance Center. By default, this role is assigned to the Organization Management and Security Reader role groups in the EAC.
    
- You have to be assigned the DLP Compliance Management role in the Security &amp; Compliance Center to view DLP reports (and DLP policies) in the Security &amp; Compliance Center. By default, this role is assigned to the Compliance Administrator, Organization Management, and Security Administrator role groups in the Security &amp; Compliance Center.
    
Additionally, you would have to be assigned the Data Loss Prevention role in the EAC to view DLP reports (and DLP policies) in the EAC. By default, this role is assigned to the Compliance Management and Organization Management role groups in the EAC.
  
 **To open the **View reports** page in the Security &amp; Compliance Center: **
  
1. Go to [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Sign in to Office 365 using the credentials for a user account in your Office 365 organization.
    
On the **View reports** page, you can view the following types of reports: 
  
- [Auditing reports](reports-in-security-and-compliance.md#o365reports)
    
- [Supervisory review report](reports-in-security-and-compliance.md#SupvReview)
    
- [Data loss prevention reports](reports-in-security-and-compliance.md#DLPreports)
    
## Auditing reports
<a name="o365reports"> </a>

The following table describes the reports in the **Auditing** section on the **View reports** page in the Security &amp; Compliance Center. 
  
|**Report**|**Description**|
|:-----|:-----|
|**Office 365 audit log report** <br/> |You can search the Office 365 audit log for user and admin activity in your Office 365 organization. The report contains entries user and admin activity in Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory, which is the directory service for Office 365. For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](http://go.microsoft.com/fwlink/p/?LinkId=708432).  <br/> |
|**Azure AD reports** <br/> |To look for unusual or suspicious sign-in activity in your Office 365 organization, you can use sign-in and activity reports in Microsoft Azure. You can also view events in the Azure AD audit log. The first time that you try to access these reports, you will have to complete a one-time registration process to get access to the reports in the Azure AD management portal. For more information, see [Register for your free Microsoft Azure subscription](http://go.microsoft.com/fwlink/p/?LinkID=527966). After you register this one and only time, just click **View Azure AD reports** to view the reports. For more information about viewing and downloading reports in Azure AD, see [View your access and usage reports](http://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Exchange audit reports** <br/> | You can use the auditing functionality in Office 365 to track changes made to your Exchange Online configuration by your organization's administrators. Changes made to your Exchange Online organization by a Microsoft data center administrator or by a delegated administrator are also logged. For Exchange Online, administrator audit logging is enabled by default, so you don't have to do anything to turn it on. Exchange Online also provides mailbox audit logging to let you track access to mailboxes by someone other than the mailbox owner. You have to enable mailbox audit logging for each mailbox that you want to track non-owner access.  <br/>  For both admin and mailbox audit logging, you can run audit reports to view the audit log entries. You can also export mailbox and admin audit logs, which are sent to you within 24 hours in an XML file that is attached to email message. For more information about exporting audit logs, see:  <br/> [Export mailbox audit logs](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [View and export the datacenter admin audit log](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Search the role group changes or administrator audit logs](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>  For more information about auditing in Exchange Online, see [Auditing reports](http://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## Supervisory review report
<a name="SupvReview"> </a>

With the supervisory review report, you can see the status of all the supervisory review policies in your organization. For more information, see [Configure supervisory review policies for your organization](configure-supervision-policies.md).
  
## Data loss prevention reports
<a name="DLPreports"> </a>

Data loss prevention (DLP) reports contain information about the DLP policies and rules that have been applied to content contain sensitive data in your Office 365 organization. You can also configure the report to display information about DLP actions that were based on your DLP policy and rules. For more information, see [View the report for data loss prevention](view-the-dlp-reports.md).
  
[Return to top](reports-in-security-and-compliance.md#top)
  

