---
title: "View reports for Office 365 Advanced Threat Protection"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 7/17/2018
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

If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)
  
![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP reports include the [Threat protection status report](#threat-protection-status-report), the ATP File Types report, and the ATP Message Disposition report. This article describes the ATP reports and includes links to additional reports in the Security &amp; Compliance Center.
  
## Threat protection status report
The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).

To view the Threat protection status report, the Security &amp; Compliance Center, go to **Reports** > **Dashboard** > **Threat protection status**.

![ATP Threat Protection Status report](media/ATP-TPSReport.png)
  
To get detailed status for a day, hover over the graph. 

![Threat Protection Status view of data for a day](media/ATP-TPSReport-DayStatusHover.png) 

By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days. 

![Filters for Threat Protection Status report](media/ATP-TPSReport-Filters.png)

You can also use the **View data by** menu to change what information is displayed in the report.

![The View Data By menu for the Threat Protection Status report](media/ATP-TPSReport-ViewDataByMenu.png)
    
## ATP File Types report

The **ATP File Types report** shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.
  
![ATP File Types report](media/ATPFileTypesReport.png)
  
When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).

![Data for a day in the ATP File Types report](media/ATPFileTypesReport-DayHover.png)
 
## ATP Message Disposition report

The **ATP Message Disposition** report shows you the actions that were taken for email messages that were found to have malicious files.
  
To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.
  
![ATP Message Disposition report](media/ATPMessageDispositionReport.png)

When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.

![Day view of data in the ATP Message Disposition report](media/ATPMessageDispositionReportDayHover.png)

## Additional reports to view

In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available. Email security reports include a top senders and receivers report, a spoof mail report, a spam detections report, and more. And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).


## What permissions are needed to view these reports?

In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.
  
|**Role group**|**Where assigned**|**Learn more**|
|:-----|:-----|:-----|
| One of the following:  <br/>  Organization Management  <br/>  Security Administrator  <br/>  Security Reader  <br/> |Security &amp; Compliance Center  <br/> |[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md) <br/> |
| One of the following:  <br/>  Organization Management  <br/>  View-only Organization Management  <br/>  View-Only Recipients role  <br/>  Compliance Management  <br/> |Exchange Admin Center  <br/> |[Feature permissions in Exchange Online](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |

## What if the reports aren't showing data?

If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).
  
## Related topics

[Smart reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md)

[Create a schedule for a report in the Security &amp; Compliance Center](create-a-schedule-for-a-report.md)

[Set up and download a custom report in the Security &amp; Compliance Center](set-up-and-download-a-custom-report.md)

[Download existing reports in the Security &amp; Compliance Center](download-existing-reports.md)

[Manage schedules for multiple reports in the Security &amp; Compliance Center](manage-schedules-for-multiple-reports.md)

