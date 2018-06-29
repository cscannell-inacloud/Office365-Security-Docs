---
title: "Review and take action on alerts in Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: "Use the Alerts page in Office 365 Cloud App Security to view potential issues and take action. You can dismiss or resolve alerts, and if necessary, suspend a user account."
---

# Review and take action on alerts in Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |You are here!  <br/> [Next steps](review-office-365-cas-alerts.md#nextsteps) <br/> |
   
You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.
  
> [!NOTE]
> You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## How to get to the Alerts page

1. As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. 
    
2. In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.
    
3. Choose **Go to Office 365 Cloud App Security**.
    
    ![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. In the navigation bar across the top of the screen, choose **Alerts**.
    
    ![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## Review and handle alerts

Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.
  
> [!TIP]
> You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first. 
  
For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:
  
- **Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it. 
    
- **Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it. 
    
- **Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on. 
    
## Next steps
<a name="nextsteps"> </a>

- [Investigate an activity](investigate-an-activity-in-office-365-cas.md)
    
- [Suspend or restore a user account](suspend-or-restore-an-account-in-ocas.md)
    
- View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

