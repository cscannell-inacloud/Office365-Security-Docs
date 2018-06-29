---
title: "Anomaly detection policies in Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: "Anomaly detection policies in Office 365 Cloud App Security use built-in algorithms to help uncover potential problems. You should have at least one anomaly detection policy, which you can tune (when you create it) by using filters. "
---

# Anomaly detection policies in Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |You are here!  <br/> [Next step](integrate-your-siem-server-with-office-365-cas.md) <br/> |[Start utilizing](utilization-activities-for-ocas.md) <br/> |
   
Beginning with [Microsoft Cloud App Security release 116](https://docs.microsoft.com/en-us/cloud-app-security/release-notes), Office 365 Cloud App Security includes several predefined anomaly detection policies ("out of the box") that include user and entity behavioral analytics (UEBA) and machine learning (ML).
  
![To view your anomaly detection policies, choose Control \> Policies.](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
These anomaly detection policies provide immediate results by providing immediate detections, targeting numerous behavioral anomalies across your users and the machines and devices connected to your network. In addition, the new policies expose more data from the Cloud App Security detection engine to help you speed up the investigation process and contain ongoing threats.
  
As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), you can review, and if necessary, revise the default policies that are available with Office 365 Cloud App Security.
  
 **In this article**: 
  
- [View your anomaly detection policies](anomaly-detection-policies-in-ocas.md#seethedefaults)
    
- [Learn more about anomaly detection policies](anomaly-detection-policies-in-ocas.md#whatsin)
    
- [Triage anomaly detection alerts](anomaly-detection-policies-in-ocas.md#triage)
    
- [Next steps](anomaly-detection-policies-in-ocas.md#nextsteps)
    
> [!IMPORTANT]
> There is an initial learning period of seven (7) days during which anomalous behavior alerts are not triggered. The anomaly detection algorithm is optimized to reduce the number of false positive alerts. 
  
## Before you begin

Make sure that:
  
- Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).
    
- [Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment. 
    
- You are a global administrator or security administrator for Office 365.
    
## View your anomaly detection policies
<a name="seethedefaults"> </a>

1. As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. 
    
2. In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.
    
3. Choose **Go to Office 365 Cloud App Security**.
    
    This takes you to the Office 365 Cloud App Security Policies page.
    
4. In the **TYPE** list, choose **Anomaly detection policy**.
    
    Your organization's default (or existing) anomaly detection policies are displayed.
    
    ![Several anomaly detection policies are available by default in Office 365 Cloud App Security](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
5. Select a policy to review or edit its settings.
    
6. Choose **Update** to save your changes. 
    
## Learn more about anomaly detection policies
<a name="whatsin"> </a>

Anomaly detection policies are automatically enabled; however, Office 365 Cloud App Security has an initial learning period of seven days during which not all anomaly detection alerts are raised. After that, each session is compared to the activity, when users were active, IP addresses, devices, etc. detected over the past month and the risk score of these activities. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity. These detections also leverage machine learning algorithms designed to profile the users and log-in patterns to reduce false positives.
  
Anomalies are detected by scanning user activity. The risk is evaluated by looking at over 30 different risk indicators, grouped into multiple risk factors, such as risky IP address, login failures, admin activity, inactive accounts, location, impossible travel, device and user agent, and activity rate.
  
Based on the policy results, security alerts are triggered. Office 365 Cloud App Security looks at every user session in Office 365, and alerts you whenever something happens that is different from the baseline of your organization or from a user's regular activity.
  
The following table describes the default anomaly detection policies, what they do, and how they work.
  
|**Anomaly detection policy name**|**How it works**|
|:-----|:-----|
|Impossible travel  <br/> |Identifies two user activities (is a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. This detection leverages a machine learning algorithm that ignores obvious "false positives" contributing to the impossible travel condition, such as VPNs and locations regularly used by other users in the organization. The detection has an initial learning period of seven days during which it learns a new user's activity pattern.  <br/> |
|Activity from infrequent country  <br/> |Considers past activity locations to determine new and infrequent locations. The anomaly detection engine stores information about previous locations used by users in the organization. An alert is triggered when an activity occurs from a location that was not recently or never visited by the user or by any user in the organization.  <br/> |
|Activity from anonymous IP addresses  <br/> |Identifies that users were active from an IP address that has been identified as an anonymous proxy IP address. These proxies are used by people who want to hide their device's IP address, and may be used for malicious intent. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.  <br/> |
|Activity from suspicious IP addresses  <br/> |Identifies that users were active from an IP address that has been identified as risky by Microsoft Threat Intelligence. These IP addresses are involved in malicious activities, such as Botnet C&amp;C, and may indicate compromised account. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.  <br/> |
|Unusual activities (by user)  <br/> | Identifies users who perform unusual activities, such as:  <br/>  Multiple file downloads  <br/>  File sharing activities  <br/>  File deletion activities  <br/>  Impersonation activities  <br/>  Administrative activities  <br/>  These policies look for activities within a single session with respect to the baseline learned, which could indicate on a breach attempt. These detections leverage a machine learning algorithm that profiles the users log on pattern and reduces false positives. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity.  <br/> |
|Multiple failed login attempts  <br/> |Identifies users that failed multiple login attempts in a single session with respect to the baseline learned, which could indicate on a breach attempt.  <br/> |
   
## Triage anomaly detection alerts
<a name="triage"> </a>

As alerts come in, you can triage those alerts quickly and determine which ones to handle first. Having context for an alert enables you to see the bigger picture and determine whether something malicious is indeed happening. Use the following procedure to get started exploring an alert:
  
1. As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. 
    
2. In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.
    
3. Choose **Go to Office 365 Cloud App Security**.
    
4. Choose **Alerts** to view your alerts. 
    
5. To get context for an alert, follow these steps:
    
1. Choose **Investigate** \> **Activity log**.
    
2. Select an item, such as a user or IP address. This opens the relevant insights drawer.
    
    ![In the Activity log, you can investigate an IP address.](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
3. In the relevant insights drawer, click an available command, such as an icon in the **SHOW SIMILAR** section. 
    
    ![In the relevant insights drawer, you can click the clock icon to see activities performed within 48 hours of a selected activity](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
4. Gain insight about the selected item by continuing to explore details for that item.
    
An alert on multiple failed logins might indeed be suspicious, and can indicate a potential brute-force attack. However, such an alert can also be an application misconfiguration, causing the alert to be a benign true positive. If you see a multiple-failed-logins alert with additional suspicious activities, then there is a higher probability that an account is compromised. For example, suppose that a multiple-failed-login alert is followed by activity from a TOR IP address and impossible travel activity, both strong indicators of compromise. You might even see that the same user performed a mass download activity, which is often an indicator of the attacker performing exfiltration of data. It's things like that that you can explore in Office 365 Cloud App Security to view and triage your alerts, and take action where needed.
  
## Next steps
<a name="nextsteps"> </a>

- [Integrate your SIEM server](integrate-your-siem-server-with-office-365-cas.md)
    
- [Review and take action on alerts](review-office-365-cas-alerts.md)
    
- [Group your IP addresses to simplify management](group-your-ip-addresses-in-ocas.md)
    

