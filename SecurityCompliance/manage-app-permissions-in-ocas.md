---
title: "Manage app permissions using Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: "App permissions in Office 365 Cloud App Security help you manage the apps your users download for use with Office 365 data"
---

# Manage app permissions using Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |You are here!  <br/> [Next steps](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more. 
  
This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.
  
## How to find the Manage app permissions page
<a name="findappperms"> </a>

> [!NOTE]
> App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.) 
    
2. Go to **Alerts** \> **Manage advanced alerts**.
    
3. Click (or tap) **Go to Office 365 Cloud App Security**.
    
    ![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md). 
  
4. Choose **Investigate** \> **App permissions**.
    
    ![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## What you'll see on the Manage app permissions page
<a name="whatsonpage"> </a>

The following table describes the controls and options available on the Manage app permissions page.
  
|**Item**|**Description**|
|:-----|:-----|
|Basic icon in the app query bar  <br/> ![Icon that indicates basic query view for querying app permissions](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|Select this to switch to the Advanced view.  <br/> (If you see **Basic**, you are using the Advanced view)  <br/> |
|Advanced icon in the app query bar  <br/> ![Icon that indicates advanced query view for querying app permissions](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|Select this to switch to the Basic view.  <br/> (If you see **Advanced**, you are using the Basic view.)  <br/> |
|Open or close all details icon in the app list  <br/> ![Click this icon to open or close all details for all apps](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|Select this icon to view more or fewer details about each app.  <br/> |
|Export icon in the app list  <br/> ![Click this icon to export a csv file of all apps](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.  <br/> |
|Name  <br/> |Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.  <br/> |
|Authorized by  <br/> |Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.  <br/> |
|Permissions Level  <br/> ![Icon that indicates the permisiions level for an app](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  <br/> |
|App state ( **Banned**, **Approved**, or **Undetermined**)  <br/> ![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)|Use this to mark an app as Approved or Banned, or leave it as undetermined.  <br/> |
   
## Mark an app as approved
<a name="approveapp"> </a>

On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon. 
  
![Choose the Mark app as approved icon](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
The icon turns green, and the app is approved for all your Office 365 users.
  
> [!NOTE]
> When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet. 
  
## Ban an app
<a name="banapp"> </a>

1. On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon. 
    
    ![Choose the Mark app as banned icon](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. Choose whether to let users know that their app has been banned.
    
    (Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.
    
    To not let users know, clear **Notify users who granted access to this banned app**.
    
    ![The mail template for a banned app](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. Choose **Ban app**.
    
## Create an app query
<a name="createapp"> </a>

1. In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)
    
2. Use the **Select a filter** list to choose an option. The following table summarizes your available filter options. 
    
|**Use this filter**|**To display**|
|:-----|:-----|
|**App** <br/> |Apps with certain names  <br/> |
|**App state** <br/> |Apps based on their state (Approved, Banned, or Undetermined)  <br/> |
|**Community use** <br/> |Apps based on community use levels (Rare, Uncommon, or Common)  <br/> |
|**Permission level** <br/> |Apps based on certain permission levels  <br/> |
|**Permissions** <br/> |Apps that require certain permissions  <br/> |
|**Publisher** <br/> |Apps from certain publishers  <br/> |
|**User** <br/> |Apps that a certain user authorized  <br/> |
   
3. Select **equals** or **does not equal**, and then specify a value for your filter.
    
4. To add more filters, select the plus sign (![Add a filter icon for querying apps](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)), and then repeat steps 2 and 3.
    
5. To remove a filter, select the x (![Remove a filter icon for querying apps](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) next to a filter name.
    
The filters are applied automatically, and the apps list is updated accordingly.
  
## Next steps
<a name="nextsteps"> </a>

- [Review and take action on alerts](review-office-365-cas-alerts.md)
    
- Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

