---
title: "Use Explorer in the Security &amp; Compliance Center"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d

description: "Learn about Explorer (also called Threat Explorer) in the Security &amp; Compliance Center."
---

# Use Explorer in the Security &amp; Compliance Center

If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary [permissions in the Office 365 Security and Compliance Center](permissions-in-the-security-and-compliance-center.md), you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.
  
![Go to Threat management \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.
      
## Explorer overview

Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md).
  
![Explorer shows info about top malware and targeted users](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
Use the View menu to change what information is displayed.
  
![The View menu for Explorer](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data, as described in the following table.
  
|**Choose this option**|**To view this data**|
|:-----|:-----|
|**Email** \> **Malware** <br/> |Email messages identified as containing malware.  <br/> View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).  <br/> ![View data about detected malware](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> Below the chart, view details about top malware families, top targeted users, and more details about specific messages.  <br/> |
|**Email** \> **Phish** <br/> |Email messages identified as phishing attempts.  <br/> View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).  <br/> ![View data about email identified as phishing attempts](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png)           <br/> Below the chart, view more details about specific messages.  <br/> |
|**Email** \> **User-reported** <br/> |Email that users have reported as junk, not junk, or phishing email.  <br/> View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).  <br/> ![View data about email users reported as junk, not junk, or phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)           <br/> Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.  <br/> |
|**Email** \> **All mail** <br/> |An all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).  <br/> > [!NOTE]> If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing. To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available).           View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.  <br/> ![View data about detected email by detection technology](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)           <br/> Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.  <br/> |
|**Content** \> **Malware** <br/> |Files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.  <br/> View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).  <br/> ![View data about detected malware](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.  <br/> |
  
## (New!) Click-to-filter capabilities

New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:
  
![Go to Threat management \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Clicking **ATP Detonation** in this chart results in a view like this: 
  
![Explorer filtered to display only ATO Detonation results](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.
  
![Specific details about email messages with detected attachments](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s). 
  
![Selecting an item activates the Actions menu](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.
  
## How do I get Explorer?

Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md). You must have appropriate [permissions assigned in the Office 365 Security and Compliance Center](permissions-in-the-security-and-compliance-center.md), such as security administrator or security reader, in order to view and use Explorer.
  
## Related topics

[Reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)](investigate-malicious-email-that-was-delivered.md)
  
[Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md)
  

