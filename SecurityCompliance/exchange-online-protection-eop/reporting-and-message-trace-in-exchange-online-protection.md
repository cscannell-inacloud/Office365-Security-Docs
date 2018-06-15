---
title: "Reporting and message trace in Exchange Online Protection"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: "Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements. The following table describes the reports and troubleshooting tools available to EOP admins."
---

# Reporting and message trace in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements. The following table describes the reports and troubleshooting tools available to EOP admins.
  
|||||
|:-----|:-----|:-----|:-----|
|**Feature** <br/> |**Description** <br/> |**Where you can find it** <br/> |**For more information** <br/> |
|**Usage reports in the Office 365 admin center** <br/> |**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.  <br/> **Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.  <br/> **Email app usage** View information about the email apps that are used. This include the total number of connections for each app, and the versions of Outlook that are connecting.  <br/> **Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.  <br/> |
In the Office 365 admin center at https://portal.office.com/adminportal/home, click Reports \> Usage. At the top of the dashboard, click Select a report.  In the  in the drop-down list that appears, make one of these selections:  Office 365 section: Office 365 groups activityExchange section:  Email activityEmail app usageMailbox usage|[Office 365 Reports in the admin center - Office 365 groups](https://go.microsoft.com/fwlink/p/?linkid=861610) <br/> [Office 365 Reports in the Admin Center - Email activity](https://go.microsoft.com/fwlink/p/?linkid=859706) <br/> [Office 365 Reports in the Admin Center - Email apps usage](https://go.microsoft.com/fwlink/p/?linkid=859707) <br/> [Office 365 Reports in the Admin Center - Mailbox usage](https://go.microsoft.com/fwlink/p/?linkid=859708) <br/> |
|**Security &amp; compliance reports in the Office 365 admin center** <br/> | These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.  <br/> **Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.  <br/> **Note**: You can purchase ATP as an add-on to other subscription plans. For more information, see [Office 365 Advanced Threat Protection Service Description](https://go.microsoft.com/fwlink/p/?linkid=826069).  <br/> ** EOP ** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.  <br/> |
In the Office 365 Security &amp; Compliance Center at https://protection.office.com, click Reports \> Dashboard.  Select one of the reports that are available on the page:   ATP reports: ATP file types, ATP message disposition, and Threat protection status.   EOP reports: Malware detections, Top malware, Top senders and recipients, Spoof mail, Spam detections, and Sent and received mail.  |[View reports for Advanced Threat Protection and Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=852409) <br/> |
|**Custom reports using Microsoft Graph** <br/> |Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  <br/> |n/a  <br/> |The subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135) <br/> |
|**Custom reports using reporting web services** <br/> |Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.  <br/> |[https://reports.office365.com/ecp/reportingwebservice/reporting.svc](https://reports.office365.com/ecp/reportingwebservice/reporting.svc) <br/> |[Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926) <br/> |
|**Message trace** <br/> |Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.  <br/> You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.  <br/> |
In the Office 365 admin center at https://portal.office.com/adminportal/home, click Admin centers \> Exchange Online Protection. In the new Exchange admin center page that opens, go to Mail flow \> Message trace. |[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) <br/> |
|**Audit logging** <br/> |Tracks specific changes made by admins to your organization. These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.  <br/> |
In the Office 365 admin center at https://portal.office.com/adminportal/home, click Admin centers \> Exchange Online Protection. In the new Exchange admin center page that opens, go to Compliance management \> Auditing. |[Auditing reports in EOP](auditing-reports-in-eop.md) <br/> |
   
## Reporting and message trace data availability and latency

The following table describes when EOP reporting and message trace data is available and for how long.
  
||||
|:-----|:-----|:-----|
|**Report type** <br/> |**Data available for (look back period)** <br/> |**Latency** <br/> |
|Mail protection summary reports  <br/> |90 days  <br/> |Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.  <br/> |
|Mail protection detail reports  <br/> |90 days  <br/> |For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.  <br/> To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.  <br/> |
|Message trace data  <br/> |90 days  <br/> |When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.  <br/> When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.  <br/> |
   
> [!NOTE]
> Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell. 
  

