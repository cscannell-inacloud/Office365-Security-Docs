---
title: "Review app discovery findings in Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: "Reviewing app discovery reports in Advanced Security Management can help you learn more about how people in your organization use cloud apps. After you've created app discovery reports using log files from your firewalls and proxies, review the results in the app discovery dashboard."
---

# Review app discovery findings in Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |You are here!  <br/> [Next steps](review-app-discovery-findings-in-ocas.md#nextsteps) <br/> |
   
The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)
  
 **As of March 2018, the Cloud Discovery dashboard has new features** that make it easier to view detailed information about how people in your organization are using Office 365 and other apps. 
  
![The Cloud Discovery dashboard has been updated](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
 **In this article**: 
  
- [Go to the Cloud Discovery dashboard](review-app-discovery-findings-in-ocas.md#gotodash)
    
- [See your top users, IP addresses, apps, and risk levels](review-app-discovery-findings-in-ocas.md#reviewdash)
    
- [Dive deeper into the information](review-app-discovery-findings-in-ocas.md#divedeeper)
    
- [Exclude entities](review-app-discovery-findings-in-ocas.md#excludeentities)
    
- [Next steps](review-app-discovery-findings-in-ocas.md#nextsteps)
    
## Go to the Cloud Discovery dashboard
<a name="gotodash"> </a>

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.) 
    
2. In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.
    
    (If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)
    
3. Choose **Go to Office 365 Cloud App Security**.
    
4. Go to **Discover** \> **Cloud Discovery dashboard**.
    
## See your top users, IP addresses, apps, and risk levels
<a name="reviewdash"> </a>

The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.
  
![Cloud Discovery dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen. 
    
2. See the **Office 365 categories** for apps that are used in your organization. 
    
3. Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view. 
    
4. Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization. 
    
5. See where the apps people are using are by geographical location by using the **Apps headquarters location** map. 
    
6. Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps. 
    
## Dive deeper into the information
<a name="divedeeper"> </a>

You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.
  
1. In the Cloud Discovery dashboard, choose the **Discovered apps** tab. 
    
2. Use the filters section to view apps by name, category, usage level, or last seen date.
    
3. In the list of results, hover by an app name to reveal the **View sub-domains** link. 
    
    ![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)
  
    Detailed information about the selected app will appear.
    
4. To view details about IP addresses, choose the **IP addresses** tab. 
    
    ![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)
  
    In the list of results, select an individual IP address to view more detailed information.
    
5. To view details about Office 365 users within your organization, choose the **Users** tab. 
    
    ![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## Exclude entities
<a name="excludeentities"> </a>

You can exclude certain system users or IP addresses in order to focus on more specific information.
  
1. Choose **Settings** \> **Cloud Discovery settings**.
    
2. Choose **Exclude entities**.
    
3. Choose either **Excluded users** or **Excluded IP addresses**.
    
4. Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses. 
    
5. Choose **Add**.
    
## Next steps
<a name="nextsteps"> </a>

- [Review and take action on alerts](review-office-365-cas-alerts.md)
    
- [Create app discovery reports](create-app-discovery-reports-in-ocas.md)
    
- Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

