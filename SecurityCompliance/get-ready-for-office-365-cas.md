---
title: "Get ready for Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: "Get started using Office 365 Cloud App Security"
---

# Get ready for Office 365 Cloud App Security
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |You are here!  <br/> [Next step](turn-on-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |[Start utilizing](utilization-activities-for-ocas.md) <br/> |
   
As you prepare to turn on and implement Office 365 Cloud App Security (formerly known as Advanced Security Management) for your organization, there are a few things to take into account. Use this article as a guide to plan for Office 365 Cloud App Security.
    
## Step 1: Identify and protect your global and security administrator accounts

Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports. Global administrators and security administrators can define policies and take other actions to protect your organization. (For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution. 
  
 **[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**. 
  
## Step 2: Turn on audit logging for your organization

In order for Office 365 Cloud App Security to work correct, audit logging must be turned on. This is typically done by an Exchange Online administrator or a global administrator.
  
 **[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**. 
  
## Step 3: Go to the Office 365 Cloud App Security portal

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.) 
    
2. Go to **Alerts** \> **Manage advanced alerts**.
    
3. Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal. 
    
    ![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:
    
    ![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
## Step 4: Define policies and set up alerts &amp; actions

Global administrators and security administrators define policies in Office 365 Cloud App Security. During the process of defining policies, alerts and actions are also set. An alert is a criteria-based notification that appears in a view or is sent via email. 
  
There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization. Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.
  
See the following resources to learn more:
  
- [Activity policies and alerts in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Review and take action on Office 365 Cloud App Security alerts](review-office-365-cas-alerts.md)
    
## Step 5: Learn about your organization's cloud usage

As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery). This dashboard shows information about users, apps, web traffic, and risk levels.
  
![In the Office 365 CAS portal, choose Discover \> Cloud Discovery dashboard](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.
  
![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
To populate reports with the information you need, upload your log files from your organization's firewalls and proxies. To learn more, see the following resources:
  
- [Create app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md)
    
- [Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
## Step 6: Manage apps that your organization is using to access Office 365

As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365. For example, suppose that someone has downloaded a custom app they want to use with Office 365. You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes. [Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).
  
## Step 7: Use your SIEM server with Office 365 Cloud App Security

Is your organization using a security information and event management (SIEM) server? Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server. See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).
  
## Next steps

- [Turn on Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
- Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept. 
    

