---
title: "Office 365 Auditing and Reporting Overview"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
ms.collection: Strat_O365_Enterprise
description: "Summary: An overview of auditing and reporting features within Office 365, as well as Service Assurance."
---

# Office 365 Auditing and Reporting Overview 

## Introduction
Microsoft cloud services includes several auditing and reporting features that customers can use to track user and administrative activity within their tenant, such as changes made to their Exchange Online and SharePoint Online tenant configuration settings, and changes made by users to documents and other items. Customers can use the audit information and reports available in our cloud services to more effectively manage the user experience, mitigate risk, and fulfill compliance obligations.

## Office 365 Security & Compliance Center
The [Office 365 Security & Compliance Center](https://support.office.com/en-us/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8) is a one-stop portal for protecting your data in Office 365, and it includes many auditing and reporting features. It is an evolution of the Office 365 Compliance Center. The Security & Compliance Center is designed for organizations that have data protection or compliance needs, or that want to audit user and administrator activity. You can use the Security & Compliance Center to manage compliance for all of your organization's Office 365 data. You can access the Security & Compliance Center at [http://protection.office.com](http://protection.office.com/) using your Office 365 admin account.

The Security & Compliance Center includes navigation panes that provide you with access to several features:
- **Alerts** - Enables you to manage alerts, view security-related alerts, and manage advanced alerts using [Advanced Security Management](http://go.microsoft.com/fwlink/?LinkId=786900). 
- **Permissions** - Enables you to [assign permissions](https://support.office.com/en-us/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) such as Compliance Administrator, eDiscovery Manager, and others to people in your organization so that they can perform tasks in the Security & Compliance Center. You can assign permissions for most features in the Security & Compliance Center, but other permissions must be configured using the Exchange admin center and SharePoint admin center.
- **Threat management** - Enables you to create and apply device management policies using [Office 365 Mobile Device Management](https://support.office.com/en-us/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), to set up [Data Loss Prevention](https://support.office.com/en-us/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP) policies for your organization, to configure email filtering, anti-malware, DomainKeys Identified Mail (DKIM), safe attachments, safe links, and app permissions.
- **Data governance** - Enables you to [import email or SharePoint data from other systems into Office 365](https://support.office.com/en-us/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [configure archive mailboxes](https://support.office.com/en-us/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce), and set [retention policies](https://support.office.com/en-us/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) for email and other content within your organization.
- **Search & investigation** - Provides [content search](https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [audit log](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), quarantine, and [eDiscovery case management](https://support.office.com/en-us/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) tools to quickly drill into activity across Exchange Online mailboxes, groups and public folders, SharePoint Online, and OneDrive for Business.
- **Reports** - Enables you to quickly access [reports](https://support.office.com/en-us/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) for SharePoint Online, OneDrive for Business, Exchange Online, and Azure AD.
- **Service assurance** - Provides information about how Microsoft maintains security, privacy, and compliance with global standards for Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune, and other cloud services. Also includes access to third-party ISO, SOC, and other audit reports, as well as Audited Controls, which provides details about the various controls that have been tested and verified by third-party auditors of Office 365.

## Service Assurance
Many of our customers in regulated industries are subject to extensive compliance requirements. To perform their own risk assessments, customers often need in-depth information about how Office 365 maintains the security and privacy of their data. Microsoft is committed to the security and privacy of customer data in its cloud services and to earning customer trust by providing a transparent view of its operations, and easy access to independent compliance reports and assessments.

Service Assurance provides transparency of operations and information about how Microsoft maintains the security, privacy, and compliance of customer data in Office 365. It includes third-party audit reports along with a library of white papers, FAQs, and other materials on Office 365 topics such as data encryption, data resiliency, security incident management and more. Customers can use this information to perform their own regulatory risk assessments. Compliance officers can assign the "Service Assurance User" role to give users access to Service Assurance. The tenant administrator can also provide external users, such as independent auditors, with access to information in the Service Assurance dashboard through the [Microsoft Cloud Service Trust Portal](http://aka.ms/STP) (STP). For details on how to access the STP, visit [Get started with the Service Trust Portal for Office 365 for business, Azure, and Dynamics CRM Online subscriptions](http://aka.ms/STPHelp).

## OneDrive for Business Admin Center Preview
Microsoft recently announced the rollout of the [OneDrive for Business admin center preview](http://fasttrack.microsoft.com/roadmap#R-51678) to First Release customers. Once deployed to a tenant, all tenant and SharePoint Online admins will have permissions to access the OneDrive for Business admin center preview at [https://admin.onedrive.com](https://admin.onedrive.com/).

Key features include a Compliance area that provides administrators with links to the Office 365 Security and Compliance Center for key scenarios like searching the audit log, working with DLP, retention, eDiscovery, and alerting.

## Related Links
- [eDiscovery and Search Features](/office365/enterprise/office-365-ediscovery-and-search-features)
- [Office 365 Reporting Features](/office365/enterprise/office-365-reporting-features)
- [Office 365 Management Activity API](/office365/enterprise/office-365-management-activity-api)
- [Office 365 Mailbox Migrations](/office365/enterprise/office-365-mailbox-migrations)
- [Internal Logging for Office 365 Engineering](/office365/enterprise/office-365-internal-logging)