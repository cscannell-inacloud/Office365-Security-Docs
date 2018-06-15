---
title: "Submit spam, non-spam, and phishing scam messages to Microsoft for analysis"
ms.author: krowley
author: kccross
manager: scotv
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1

description: "In this articleSubmit junk or phishing messages that passed through the spam filtersSubmit messages that were tagged as junk but should have been allowed through Spam evaluation and rules deploymentNew to Office 365?For more information"
---

# Submit spam, non-spam, and phishing scam messages to Microsoft for analysis

 **In this article**
  
[Submit junk or phishing messages that passed through the spam filters](#sectionSection0.md)
  
[Submit messages that were tagged as junk but should have been allowed through ](#sectionSection1.md)
  
[Spam evaluation and rules deployment](#sectionSection2.md)
  
[New to Office 365?](#sectionSection3.md)
  
[For more information](#sectionSection4.md)
  
It can be frustrating when users in your organization receive junk messages (spam) or phishing scam messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk. We're constantly fine-tuning our spam filters to be more accurate. You and your users can help this process by submitting false negative and false positive spam messages to Microsoft for analysis. A "false negative" is a spam message that should have been but was not identified as spam. A "false positive" is a legitimate email message that was incorrectly identified as spam. 
  
> [!NOTE]
> Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis. 
  
## Submit junk or phishing messages that passed through the spam filters
<a name="sectionSection0"> </a>

If you receive a message that passed through the spam filters that and should be classified as junk or a phishing scam, you can submit the "false negative" message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams, as appropriate. The analysts will review the message and add it to the service-wide filters if it meets the classification criteria. 
  
For more spam settings that apply to the whole organization, see [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). This article contains tips to help prevent false negatives.
  
You can submit junk email messages in the following ways:
  
- For Outlook users, the primary way to submit junk messages is by using a plug-in known as the Microsoft Junk Email Reporting Add-in for Microsoft Outlook. For information about how to install and use this tool, see [Junk email reporting add-in for Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md). 
    
- For Outlook on the web users, the primary way to submit junk email messages is by using its built-in junk email reporting option. For more information, see [Report junk email and phishing scams in Outlook on the web [EOP]](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). 
    
- You can also use email to submit messages to Microsoft that should be classified as junk or phishing scams, as described in the following procedure.
    
### Use email to submit junk (spam) or phishing scam messages to Microsoft
<a name="Useemailtosubmitjunkspamorphishingscammessages"> </a>

To submit a junk or phishing scam message to Microsoft:
  
1. Create a blank email message.
    
2. Address the message to the Microsoft team that reviews messages, as follows: 
    
  - For junk messages: junk@office365.microsoft.com
    
  - For phishing scam messages: phish@office365.microsoft.com
    
3. Copy and paste the junk or phishing scam message into the new message as an attachment. 
    
    > [!NOTE]
    > You can attach multiple messages to the new message. Make sure that all the messages are the same type — either phishing scam messages or junk email messages. > Leave the body of the new message empty. 
  
4. Click **Send**.
    
## Submit messages that were tagged as junk but should have been allowed through
<a name="sectionSection1"> </a>

If a message was incorrectly identified as junk, you can submit the "false positive" message to the Microsoft Spam Analysis Team. The analysts will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.
  
Administrators can review more spam setting information that applies to a whole organization. See [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224). This information is helpful if you have administrator-level control and you want to prevent false positives.
  
You can submit non-spam messages in the following ways:
  
- If you use the **Move message to Junk Email folder** action when you configure your content filters (this is the default action), users can release false positive messages in their Outlook or OWA Junk Email folder. 
    
  - Outlook users can release false positive messages by using the **Not Junk** right-click menu option. However, they must submit the message to Microsoft through email, as shown in the procedure in this article. 
    
  - OWA users can release false positive messages and submit them to Microsoft for analysis using the **Mark as not junk** action. For more information about how to do this, see [Report junk email and phishing scams in Outlook on the web [EOP]](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
    
- If you use the **Quarantine message** action instead of the **Move message to Junk Email folder** action when you configure your content filters: 
    
  - Administrators can release spam-quarantined messages and report them as false positives from the Exchange Admin Center. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).
    
  - Users can release their own spam-quarantined messages and report them as false positives through the following channels: 
    
  - The Exchange admin center (EAC) user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
    
  - End-user spam notification messages (if they're enabled by your administrator). For more information about how to use this feature, see [Use end-user spam notifications to release and report spam-quarantined messages](use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages.md).
    
- You can also use email to submit messages to Microsoft that should not be classified as spam. When you do this, make sure that you use the steps in the following procedure.
    
### Use email to submit false positive messages

Use the same procedure as described in the "[Use email to submit junk (spam) or phishing scam messages to Microsoft ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)," but send the message to not_junk@office365.microsoft.com.
  
## Spam evaluation and rules deployment
<a name="sectionSection2"> </a>

The spam analysis team examines messages that you submit, and adjusts the spam filters to prevent future junk mail. As a result, Office 365 spam filters areconstantly refined. Any submitted items are evaluated at the network-wide level. False positive submissions are examined and assessed for possible rule adjustment to allow future messages through the spam filters. Therefore, notifying the service of false positives and also false negatives (unfiltered spam) is advantageous for you and all customers who use the global network. The spam team examines indicators within each submitted message, such as the following:
  
- From address
    
- Sending IP address
    
- Keywords
    
- Phrases
    
- Frequency of transmission
    
- Other trends and patterns
    
After they review this information, the spam team might make changes to the service's spam filtering layers. For more information about the spam team, you can watch the following English-only video:
  
[Microsoft Exchange Spam team video](https://youtu.be/-TpX_-GMC7o?hd=1)
  
Spam evaluation is an ongoing process that applies regardless of the originating language or character set. Because a spam message can be vague or even lack text in the subject or message body, the spam team relies on other message characteristics to perform filtering. This means that after the spam team flags a given message as spam and makes the necessary changes to its rule base, that message will be blocked in the future until its characteristics have been modified enough to avoid our filters. New spam rules are deployed continuously. Time frames for rules on individual submissions vary depending on the quantity and quality of submissions. Because new spam rules are set globally for all customers, not all individual spam submissions will result in a new spam rule.
  
## New to Office 365?
<a name="sectionSection3"> </a>

||
|:-----|
|![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning. |
   
## For more information
<a name="sectionSection4"> </a>

[Anti-spam and anti-malware protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)
  
[How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

