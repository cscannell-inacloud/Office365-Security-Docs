---
title: "Use mail flow rules to see what your users are reporting to Microsoft"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: "In this articleWhat do you need to know before you begin?Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reportsFor more information"
---

# Use mail flow rules to see what your users are reporting to Microsoft

 **In this article**
  
[What do you need to know before you begin?](#sectionSection0.md)
  
[Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports](#sectionSection1.md)
  
[For more information](#sectionSection2.md)
  
There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.
  
## What do you need to know before you begin?
<a name="sectionSection0"> </a>

Estimated time to complete: 5 minutes
  
You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook Web App mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic. 
  
For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.
  
## Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports
<a name="sectionSection1"> </a>

1. In the EAC, navigate to **Mail flow** \> **Rules**.
    
2. Click ![Add Icon](media/ITPro_EAC_AddIcon.gif) and then select **Create a new rule**.
    
3. Give the rule a name and then click **More options**.
    
4. Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.
    
5. In the **specify words or phrases** box, do the following: 
    
1. Type **abuse@messaging.microsoft.com** and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif), and then type **junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.
    
2. Type **phish@office365.microsoft.com** and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.
    
3. Type **false_positive@messaging.microsoft.com** and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif), and then type **not_junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.
    
4. Click **ok**.
    
6. Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages. 
    
7. If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections. 
    
8. Click the **save** button to save the rule. It appears in your list of rules. 
    
After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.
  
## For more information
<a name="sectionSection2"> </a>

[Turn off junk email reporting in Outlook on the web](turn-off-junk-email-reporting-in-outlook-on-the-web.md) - Provides more information about how to turn off reporting in OWA. 
  

