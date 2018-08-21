---
title: "View email security reports in the Security &amp; Compliance Center"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: "Learn how to find and use email security reports for your organization with Office 365 Enterprise. Email security reports are available in the Security &amp; Compliance Center."
---

# View email security reports in the Security &amp; Compliance Center

A variety of email security reports are available in the Security &amp; Compliance Center to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the necessary permissions, you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.
  
![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Your email security reports include the following:
  
- [Threat protection status report](view-email-security-reports.md#tps) (new!) 
    
- [Malware Detections report](view-email-security-reports.md#maldet)
    
- [Top Malware report](#top-malware-report)
    
- [Top Senders and Recipients report](view-email-security-reports.md#topsenders)
    
- [Spoof Mail report](#spoof-mail-report)
    
- [Spam Detections report](#spam-detections-report)
    
- [Sent and received email report](view-email-security-reports.md#sentreceivedemail)
    
- [User-reported messages report](view-email-security-reports.md#userreported) (new!) 
    
## Threat protection status report (new!)

The new **Threat protection status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.
  
![Threat Protection Status report](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
When you first open the Threat protection status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending. 
  
![Threat Protection Status report filters](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.
  
![Threat Protection Status report view options](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## Malware Detections report

The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Malware Detections**.
  
![Malware Detections Report example](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Similar to other reports, like the Threat protection status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range. 
  
## Top Malware report

The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Malware**.
  
![SCC - EOP Top Malware](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.
  
Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.
  
![This report shows the top malware detected for your organization](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.
  
## Top Senders and Recipients report

The **Top Senders and Recipients** report is a pie chart showing your top email senders. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.
  
![To view this report, in the Security &amp; Compliance Center, go to Reports \> Dashboard \> Top Senders and Recipients](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
When you hover over a wedge in the pie chart, you can see a count of messages sent or received.
  
Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.
  
Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection. 
  
![Use the Show Data For list to view specific information](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.
  
## Spoof Mail report

The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons). 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spoof Mail**.
  
![To view this report, in the Security &amp; Compliance Center, go to Reports \> Dashboard \> Spoof Mail](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
When you hover over a day in the chart, you can see how many spoof mail messages came through.
  
Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.
  
## Spam Detections report

The **Spam Detections** report shows all the spam content blocked by Exchange Online. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spam Detections**.
  
![To view this report, in the Security &amp; Compliance Center, go to Reports \> Dashboard \> EOP Spam Detections](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.
  
Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.
  
![The Spam Detections report tells you how many spam messages were blocked or filtered out](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.
  
## Sent and received email report

The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good." 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Sent and received email**.
  
![To view this report, in the Security &amp; Compliance Center, go to Reports \> Dashboard \> Sent and received email](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.
  
Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.
  
You can use the **Break down by** list to view information by type or by direction (incoming and outgoing). 
  
![Use the Break Down By list to view information by type or direction](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.
  
![This report tells you about anti-malware, anti-spam, and other message detections](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## User-reported messages report (new!)

The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).
  
Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs. 
  
![The User-Reported Messages report shows messages users labeled as junk, not junk, or phishing attempts.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
To view this report, in the Security &amp; Compliance Center, do one of the following:
  
- Go to **Threat management** \> **Dashboard** \> **User-reported messages**.
    
- Go to **Threat management** \> **Review** \> **User-reported messages**.
    
![In the Security &amp; Compliance Center, choose Threat management \> Review \> User reported messages](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md). 
  
## What permissions are needed to view these reports?

In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.
  
|**Role group**|**Where assigned**|**Learn more**|
|:-----|:-----|:-----|
| One of the following:  <br/>  Organization Management  <br/>  Security Administrator  <br/>  Security Reader  <br/> |Security &amp; Compliance Center  <br/> |[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md) <br/> |
| One of the following:  <br/>  Organization Management  <br/>  View-only Organization Management  <br/>  View-Only Recipients role  <br/>  Compliance Management  <br/> |Exchange Admin Center  <br/> |[Feature permissions in Exchange Online](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## What if the reports aren't showing data?

If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).
  
## Related topics

[Office 365 Email Anti-Spam Protection](anti-spam-protection.md)
  
[Reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)
  
[Set up and download a custom report in the Security &amp; Compliance Center](set-up-and-download-a-custom-report.md)
  

