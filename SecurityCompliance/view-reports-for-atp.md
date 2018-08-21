---
title: "View reports for Office 365 Advanced Threat Protection"
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
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: "Learn how to find and use reports for Office 365 Advanced Threat Protection in the Security &amp; Compliance Center."
---

# View reports for Office 365 Advanced Threat Protection

If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the necessary permissions, you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)
  
![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP reports include the [Threat protection status report](view-reports-for-atp.md#advancedthreats), the [ATP File Types report](view-reports-for-atp.md#atpfiletypes), and the [ATP Message Disposition report](view-reports-for-atp.md#atpmessagedisp). This article describes the ATP reports and includes links to [Additional reports to view](view-reports-for-atp.md#addl).
  
## Threat protection status report

The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).
  
To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.
  
![ATP Threat Protection Status report](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
To get detailed status for a day, hover over the graph.
  
![ATP Threat Protection Status data for a day](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days. 
  
![ATP Threat Protection Status filters](media/4f703369-642b-402b-9758-b9c828283410.png)
  
You can also use the **View data by** menu to change what information is displayed in the report. 
  
![Viewing options for ATP Threat Protection Status report](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## ATP File Types report

The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.
  
![ATP File Types report](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).
  
![ATP File Types report data for a day](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## ATP Message Disposition report

The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content. 
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.
  
![ATP Message Disposition Report](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.
  
![ATP Message Disposition Report data for a day](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## Additional reports to view

In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.
  
And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).
  
## What permissions are needed to view these reports?

In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.
  
|**Role group**|**Where assigned**|**Learn more**|
|:-----|:-----|:-----|
| One of the following:  <br/>  Organization Management  <br/>  Security Administrator  <br/>  Security Reader  <br/> |Security &amp; Compliance Center  <br/> |[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md) <br/> |
| One of the following:  <br/>  Organization Management  <br/>  View-only Organization Management  <br/>  View-Only Recipients role  <br/>  Compliance Management  <br/> |Exchange Admin Center  <br/> |[Feature permissions in Exchange Online](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## What if the reports aren't showing data?

If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).
  
## Related topics

[Reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)
  
[Set up and download a custom report in the Security &amp; Compliance Center](set-up-and-download-a-custom-report.md)
  

