---
title: "Overview of Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: "Office 365 Cloud App Security gives you insights into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. "
---

# Overview of Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|You are here!  <br/> [Next step](get-ready-for-office-365-cas.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |[Start utilizing](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.
  
    
## How to find the Office 365 Cloud App Security portal

> [!NOTE]
> To access the Office 365 Cloud App Security portal, you must be a global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
You can get to the Office 365 Cloud App Security portal through the Office 365 Security &amp; Compliance Center. Here's one good way to do it:
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.) 
    
2. In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**. 
    
    ![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    (If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)
    
3. Choose **Go to Office 365 Cloud App Security**. 
    
## Policies

Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets 10 predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.
  
![In the CAS portal, choose Control \> Templates to view or create policy templates](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**. 
  
![In the O365 CAS portal, choose Control](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
To learn more about policies, see the following resources:
  
- [Activity policies and alerts in Office 365 Cloud App Security](activity-policies-and-alertsc.md)
    
- [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
## Alerts

When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen. 
  
![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.
  
To learn more about alerts, see the following resources:
  
- [Activity policies and alerts in Office 365 Cloud App Security](activity-policies-and-alertsc.md)
    
- [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Review and take action on Office 365 Cloud App Security alerts](review-office-365-cas-alerts.md)
    
## Activity logs

View information about user activities on your Activity log page in Office 365 Cloud App Security.
  
![In the O365 CAS portal, choose Investigate \> Activity log](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**. 
  
![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.
  
[Learn about web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)
  
## App permissions

With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.
  
![In O365 CAS, you can access the Manage App Permissions page from the Investigate menu.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
To get to this page, go to **Investigate** \> **App permissions**. 
  
![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
  
## Cloud Discovery Dashboard

The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image: 
  
![In the Office 365 CAS portal, choose Discover \> Cloud Discovery dashboard](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**. 
  
![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
  
## Next steps

- Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)
    
- [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md)
    

