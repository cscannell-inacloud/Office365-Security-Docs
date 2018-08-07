---
title: "What is new in Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: "See what's new in Office 365 Cloud App Security"
---

# What is new in Office 365 Cloud App Security

Read this article to get a quick overview of updates and new features in Office 365 Cloud App Security (formerly known as Office 365 Advanced Security Management), which is powered by [Microsoft Cloud App Security](https://aka.ms/whatiscas).
  
This article is updated frequently, as features are added or improved. Office 365 Cloud App Security updates are released approximately two weeks after Microsoft Cloud App Security updates, and not all Microsoft Cloud App Security updates apply to Office 365 Cloud App Security. In addition, new features might take a week or more after their release date to show up in your Office 365 Cloud App Security environment.
  
## Office 365 Cloud App Security release 128

 *Releases August 5, 2018* 
  
 **Releasing with [Microsoft Cloud App Security release 128](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **App permissions across multiple apps** For apps that have been granted app permissions, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps. 
    
- **New suggested query: GDPR ready** There is a new suggested query to enable you to identify discovered apps that are GDPR ready. GDPR has recently became a top priority for security admins. This query helps you easily identify apps that are GDPR ready, and mitigate threat by assessing the risk of the apps that aren't. 
    
## Office 365 Cloud App Security release 126

 *Released July 7, 2018* 
  
 **Released with [Microsoft Cloud App Security release 126](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Automated remediation for suspicious activities** You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and apply governance actions automatically, such as suspend user. For more information, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).
    
- **Automated detection of risky OAuth Apps** In addition to the existing investigate of OAuth apps connected to your environment, Office 365 Cloud App Security now allows you to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).
    
- **Managed Security Service Provider management (MSSP) support** Office 365 Cloud App Security now provides a better management experience to MSSPs, and allows you to configure external partners as administrators with any of the roles currently available in Office 365 Cloud App Security. In addition, Administrators with access rights to more than one tenant can now easily pivot between the tenants. 
    
## Office 365 Cloud App Security release 124

 *Released June 10, 2018* 
  
 **Released with [Microsoft Cloud App Security release 124](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Scoped deployments** Enterprise organizations can granularly determine which users to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. Scoped monitoring is especially useful for compliance and licensing. Some compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations. And, you can monitor fewer users to stay within the limits of your Office 365 Cloud App Security licenses. 
    
- **New email server** The email server for Office 365 Cloud App Security has changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For organizations who customize their notifications, Cloud App Security enables this for you using MailChimp, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) and [Mail settings (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## Office 365 Cloud App Security release 121

 *Released May 6, 2018* 
  
 **Released with [Microsoft Cloud App Security release 121](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Anomaly detection policy improvements**. Office 365 Cloud App Security's anomaly detection policies have been improved to include two new types of threat detection that are gradually rolling out: 
    
  - **Ransomware activity.** Ransomware detection capabilities are extended with anomaly detection to give you more comprehensive coverage against sophisticated ransomware attacks. 
    
  - **Terminated user activity.** Terminated user activity enables you to monitor the accounts of terminated users who may have been de-provisioned from corporate applications, but who might still have access to certain corporate resources. 
    
    To view your [Anomaly detection policies](anomaly-detection-policies-in-ocas.md), in the Office 365 Cloud App Security portal, choose **Control** \> **Policies**.
    
## Office 365 Cloud App Security release 120

 *Released April 22, 2018* 
  
 **Released with [Microsoft Cloud App Security release 120](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Internal applications as user activities**. For Office 365 and Azure Active Directory (Azure AD), we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies to alert you if an application performs unexpected and unauthorized activities. 
    
- **More fields in app permissions list export**. When exporting an app permissions list to csv, additional fields such as publisher, permissions level and community usage are included to assist with the compliance and investigation process. 
    
## Office 365 Cloud App Security release 119

 *Released April 1, 2018* 
  
 **Released with [Microsoft Cloud App Security release 119](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Improvements to Cloud Discovery**. The Cloud Discovery provides more information about top users and IP addresses, making it easier to view usage details about Office 365 and other apps. To learn more, see [Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).
    
    ![The Cloud Discovery dashboard has been updated](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## Office 365 Cloud App Security release 118

 *Released March 18, 2018* 
  
 **Released with [Microsoft Cloud App Security release 118](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Barracuda support**. Cloud Discovery now supports Barracuda F Series firewalls and Barracuda F-Series firewall web log streaming. 
    
## Office 365 Cloud App Security release 117

 *Released March 6, 2018* 
  
 **Released with [Microsoft Cloud App Security release 117](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i-FILTER support**. Cloud Discovery now supports i-FILTER. 
    
## Office 365 Cloud App Security release 116

 *Released February 18, 2018* 
  
 **Released with [Microsoft Cloud App Security release 116](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Anomaly detection policy enhancements**. Anomaly detection polices in Office 365 Cloud App Security were enhanced with new scenario-based detections including impossible travel, activity from a suspicious IP address and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Office 365 Cloud App Security detection engine, which can help speed up the investigation process and contain ongoing threats. To learn more, see the Microsoft Cloud App Security article, [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).
    
- **Log parser support for Checkpoint formats**. The Cloud Discovery log parsers now support two additional Checkpoint formats: XML, and KPC. 
    
## Office 365 Cloud App Security release 114

 *Released January 21, 2018* 
  
 **Released with [Microsoft Cloud App Security release 114](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Service status**. You can now check the current Office 365 Cloud App Security service status by going to **Help** \> **System status**. 
    
    ![Click Help \> System Status to view system health status](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Custom queries for Activity log**. Beginning in version 114, the ability to create and save custom queries in the Activity log is rolling out gradually. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, suggested queries have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. Suggested queries include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. Use the suggested queries as a starting point, modify them as needed, and then save them as a new query. 
    
## Office 365 Cloud App Security release 113

 *Released January 8, 2018* 
  
 **Released with [Microsoft Cloud App Security release 113](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Log parser support for generic formats**. The Cloud Discovery log parsers now support the following generic formats: LEEF, CEF, and W3C. 
    
## Office 365 Cloud App Security release 112

 *Released December 24, 2017* 
  
 **Released with [Microsoft Cloud App Security release 112](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-112)**: 
  
- **Relevant insight drawer**. In the Activity log, you can now access the relevant insight drawer by clicking on a user name or IP address. 
    
    ![Click on a user name or IP address to see the relevant insight drawer in the Activity log.](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- **Ability to view more activities with a click**. In the relevant insight drawer, you can click the clock icon to view all activities performed within 48 hours of a selected activity. 
    
    ![In the relevant insights drawer, you can click the clock icon to see activities performed within 48 hours of a selected activity](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- **Log parser improvements for Juniper SRX**. Improvements were made to the Cloud Discovery log parser for Juniper SRX. 
    
## Office 365 Cloud App Security release 111

 *Released December 10, 2017* 
  
 **Released with [Microsoft Cloud App Security release 111](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-111)**: 
  
- **Time filter improvements**. Time filters are now easier to use. To access a time filter, in a view, such as Activity log, Policies, Alerts, using the Advanced view, choose **Date** in the list of filters. Then choose an option, such as before, after, or in between to apply the time filter. 
    
    ![Use the Date filter to view information before, after, or in between dates.](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## Office 365 Cloud App Security release 110

 *Released November 26, 2017* 
  
 **Released with [Microsoft Cloud App Security release 110](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-110)**: 
  
- **SIEM server integration now generally available**. Connect your SIEM server to Office 365 Cloud App Security. You can now send alerts and activities automatically to your SIEM server of choice by configuring SIEM Agents. See [Integrate your SIEM server with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).
    
- **Easier access to help content**. Using the new question mark in the upper right corner, you can now access the help content from within the pages of the Office 365 Cloud App Security portal. Each link is context-sensitive, taking you to the information you need, based on the page you're on. 
    
- **Send us feedback**. Using the smiley face in the upper right corner, you can now send feedback from every page of the Office 365 Cloud App Security portal. This enables you to report bugs, request new features and share your experience directly with the Office 365 Cloud App Security team. 
    
## Office 365 Cloud App Security release 102

 *Released August 13, 2017* 
  
 **Released with [Microsoft Cloud App Security release 102](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-102)**: 
  
- **New user investigation actions** enable an added level of drill-down to user investigations. On an Investigate page, you can hover on an activity, user, or account and apply it as a filter, and from there, you can view related activities or events. 
    
## Office 365 Cloud App Security release 100

 *Released July 17, 2017* 
  
 **Released with [Microsoft Cloud App Security release 100](https://docs.microsoft.com/en-us/cloud-app-security/release-notes#cloud-app-security-release-100)**: 
  
- **Security extensions** is a new dashboard where you can centrally manage all your security extensions for Office 365 Cloud App Security, including API tokens and SIEM agents. To view the Security extensions dashboard, follow these steps: 
    
1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.) 
    
2. Go to **Alerts** \> **Manage advanced alerts**.
    
3. Choose **Go to Office 365 Cloud App Security**.
    
    ![In the Security &amp; Compliance Center, choose Alerts \> Manage advanced alerts \> Go to Advanced Security Management](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. Choose **Settings** \> **Security extensions**.
    
    ![In the ASM portal, choose Settings \> Security extensions](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- **Improved parsing**. Improvements were made in the Cloud Discovery log parsing mechanism. Internal errors are significantly less likely to occur. 
    
- **Expected log formats**. The expected log format for Cloud Discovery logs now provides examples for both Syslog format and FTP format. 
    
## Related topics

[Office 365 Cloud App Security help content](office-365-cas-help.md)
  
[Utilization activities after rolling out Office 365 Cloud App Security](utilization-activities-for-ocas.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  

