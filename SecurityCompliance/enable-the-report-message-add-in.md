---
title: "Enable the Report Message add-in"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: "Learn how to enable the Report Message add-in for Outlook and Outlook on the web, for individual users or your entire organization."
---

# Enable the Report Message add-in

The Report Message add-in for Outlook enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies.
  
If you're an individual user, you can enable the Report Message add-in for yourself. 
  
If you're an Exchange Online administrator, you can enable the Report Message add-in for your organization.
    
## Get the Report Message add-in for yourself

1. Go to [https://store.office.com](https://store.office.com), and search for the Report Message add-in.
    
2. Choose **Get it now** (or **Add** ). 
    
3. Review the terms of use and privacy policy. Then choose **Continue**. 
    
4. Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).
    
> [!TIP]
> After the add-in is installed and enabled, you'll see the following icons: 
  
Next, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## Get and enable the Report Message add-in for your organization

> [!IMPORTANT]
> You must be an Exchange Online Administrator to perform this task.
  
1. Go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account. 
    
2. Choose **Admin** to go to the Admin center. 
    
3. Choose **Admin centers** \> **Exchange** to go to the Exchange admin center (EAC). 
    
4. Choose **organization** \> **add-ins**. 
    
5. Choose **+** \> **Add from the Office Store**. 
    
6. Search for Report Message.
    
7. In the **App results** list, find **Report Message**, and then choose **Get it now** (or **Add** ). 
    
8. Review the terms of use and privacy policy. Then choose **Continue**. 
    
    ![Click Continue to accept the  terms and privacy policy](media/3c813cd6-1601-4791-97dc-f8edbbd3fb6b.png)
  
9. On the confirmation screen, choose **Yes**. 
    
10. After you have installed the Report Message add-in, you must enable it. To do that, follow these steps:
    
1. Return to the EAC, and refresh your browser window.
    
2. Choose **organization** \> **add-ins**. 
    
3. In the list of add-ins, select **Report Message**. 
    
    ![In the EAC, you can enable the Report Message add-in for Outlook](media/b496743c-55fa-4cdb-aa06-0b2a7aec6dab.png)
  
4. Choose **Edit**, and select an option to enable the add-in. 
    
    ![Enable the Report Message add-in in the EAC](media/578b1b66-3620-4a8a-9819-1c9cc6836f37.png)
  
5. Choose **Save**. 
    
> [!TIP]
> After the add-in is installed and enabled, people in your organization will see the following icons: 
  
Next, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2), and set up a rule to see reported email messages.
  
### Set up a rule to get a copy of email messages reported by your users

> [!IMPORTANT]
> You must be an Exchange Online Administrator to perform this task.
  
You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.
  
1. In the EAC, choose **mail flow** \> **rules**. 
    
2. Choose **+** \> **Create a new rule**. 
    
3. In the **Name** box, type a name, such as Submissions.
    
4. In the **Apply this rule if** list, choose **The recipient address includes...**. 
    
5. In the **specify words or phrases** screen, add junk@office365.microsoft.com and phish@office365.microsoft.com, and then choose **OK**. 
    
    ![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. In the **Do the following...** list, choose **Bcc the message to...**. 
    
7. Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**. 
    
    ![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. Select **Audit this rule with severity level**, and choose **Medium**. 
    
9. Under **Choose a mode for this rule**, choose **Enforce**. 
    
    ![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. Choose **Save**. 
    
With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies. 
  
## Related topics

[Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

