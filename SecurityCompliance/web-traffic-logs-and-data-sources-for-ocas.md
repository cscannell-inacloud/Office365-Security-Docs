---
title: "Web traffic logs and data sources for Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: "Office 365 Cloud App Security works with web traffic logs from a wide range of providers. Read this article to learn more about web traffic logs and supported data sources for Office 365 Cloud App Security."
---

# Web traffic logs and data sources for Office 365 Cloud App Security

Office 365 Advanced Security Management is now Office 365 Cloud App Security.
  
|****Evaluation** \>**|****Planning** \>**|****Deployment** \>**|****Utilization****|
|:-----|:-----|:-----|:-----|
|[Start evaluating](office-365-cas-overview.md) <br/> |[Start planning](get-ready-for-office-365-cas.md) <br/> |[Start deploying](turn-on-office-365-cas.md) <br/> |You are here!  <br/> [Next steps](web-traffic-logs-and-data-sources-for-ocas.md#nextsteps) <br/> |
   
> [!NOTE]
> Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
You can use a wide range of web traffic log files and data sources with Office 365 Cloud App Security. However, your web traffic log files must include specific information and be formatted a certain way so that they will work with Office 365 Cloud App Security app discovery reports and the Cloud Discovery dashboard. Use this article as a reference guide for the web traffic logs and data sources you'll use with Office 365 Cloud App Security.
  
> [!NOTE]
> You must be a global administrator, security administrator, or security reader to access the Security &amp; Compliance Center and Office 365 Cloud App Security portal. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## Web traffic log requirements
<a name="BKMK_LogAndData"> </a>

Office 365 Cloud App Security uses data in your web traffic logs to help you understand which apps people in your organization are using. The more details that are included in the log files, the better visibility you'll have into user activity.
  
The following table lists the requirements and attributes that are needed for your web traffic logs to work correctly with Office 365 Cloud App Security:
  
|**Attributes**|**Additional requirements**|
|:-----|:-----|
| Date of the transaction  <br/>  Source IP  <br/>  Source user (recommended)  <br/>  Destination IP address  <br/>  Destination URL (recommended: URLs provide higher accuracy for cloud app detection than IP addresses)  <br/>  Total amount of data (recommended)  <br/>  Amount of uploaded or downloaded data (recommended: provides insights about cloud app usage patterns)  <br/>  Action taken (allowed or blocked)  <br/> | The data source for the log files must be supported.  <br/>  The format the log files use must match the standard format. When the file is uploaded, app discovery will verify this.  <br/>  The events in the log must have taken place no more than 90 days ago.  <br/>  The log file must include outbound traffic information that can be analyzed for network activity.  <br/> |
   
If attributes aren't included in the logs that are loaded, Office 365 Cloud App Security can't show or analyze the information for you. For example, Cisco ASA Firewall's standard log format does not include the amount of uploaded bytes per transaction, the username, or a target URL (only a target IP). Because that information isn't in the Cisco log files, Office 365 Cloud App Security won't include it when analyzing your organization's network traffic.
  
> [!NOTE]
> For some kinds of firewalls, you must set an information level for web traffic logs to include the required attributes. For example, Cisco ASA firewalls must have the information level set to 6. Make sure to confirm that your firewalls are set to deliver the correct information in your web traffic logs. 
  
## Data attributes for different vendors
<a name="BKMK_LogAndData"> </a>

The following table summarizes the information in web traffic logs from various vendors. **Be sure to check with your vendor for the most current information.**
  
|
|
|**Data source**|**Target app URL**|**Target app IP**|**Username**|**Origin IP**|**Total traffic**|**Uploaded bytes**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Barracuda  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |No  <br/> |
|Blue Coat  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Checkpoint  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |No  <br/> |No  <br/> |
|Cisco ASA  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |
|Cisco FWSM  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |
|Cisco Ironport WSA  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Cisco Meraki  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |No  <br/> |No  <br/> |
|Clavister NGFW (Syslog)  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Dell SonicWall  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Fortigate  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Juniper SRX  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Juniper SSG  <br/> |No  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|McAfee SWG  <br/> |**Yes** <br/> |No  <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Meraki (Cisco)  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |No  <br/> |No  <br/> |
|Microsoft Threat Management Gateway  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Palo Alto Networks  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Sophos  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |
|Squid (Common)  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |
|Squid (Native)  <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |**Yes** <br/> |No  <br/> |**Yes** <br/> |
|Websense - Investigative detail report (CSV)  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Websense - Internet activity log (CEF)  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
|Zscaler  <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |**Yes** <br/> |
   
## Supported vendor firewalls and proxies
<a name="BKMK_Supported"> </a>

Office 365 Cloud App Security supports the following firewalls and proxies.
  
- Barracuda - Web App Firewall (W3C)
    
- Blue Coat Proxy SG - Access log (W3C)
    
- Check Point
    
- Cisco ASA Firewall (note that you must set the information level to 6)
    
- Cisco IronPort WSA
    
- Cisco ScanSafe
    
- Cisco Merkai - URLs log
    
- Dell Sonicwall
    
- Fortinet Fortigate
    
- Juniper SRX
    
- Juniper SSG
    
- McAfee Secure Web Gateway
    
- Microsoft Forefront Threat Management Gateway (W3C)
    
- Palo Alto series Firewall
    
- Sophos SG
    
- Sophos Cyberoam
    
- Squid (Common)
    
- Squid (Native)
    
- Websense - Web Security Solutions - Investigative detail report (CSV)
    
- Websense - Web Security Solutions - Internet activity log (CEF)
    
- Zscaler
    
> [!NOTE]
> If a data source that you'd like to use is not included here, you can request that it be added to app discovery. To do that, when you're creating a report, select **Other** for **Data source**. Then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for that log type. 
  
## Troubleshoot errors when log files are uploaded
<a name="BKMK_Troubleshoot"> </a>

After you upload web traffic log files, check the governance log to see if there were any errors. If there are errors, use the information in the following table to resolve those errors.
  
|
|
|**Error**|**Description**|**Resolution**|
|:-----|:-----|:-----|
|Unsupported file type  <br/> |The file uploaded is not a valid log file. For example, an image file.  <br/> |Upload a text, zip, or gzip file that was directly exported from your firewall or proxy.  <br/> |
|Internal error  <br/> |An internal resource failure was detected.  <br/> |Click **Retry** to re-run the task.  <br/> |
|The log format does not match  <br/> |The log format you uploaded does not match the expected log format for this data source.  <br/> |
Verify that the log is not corrupt. Compare and match the log file format to the sample format shown on the upload page. |
|Transactions are more than 90 days old  <br/> |All transaction are more than 90 days old and therefore are being ignored.  <br/> |Export a new log with recent events and re-upload it.  <br/> |
|No transactions to catalogue cloud apps  <br/> |No transaction to any recognized cloud apps are found in the log.  <br/> |Verify that the log contains outbound traffic information.  <br/> |
|Unsupported log type  <br/> |When you select **Data source = Other (unsupported)**, the log is not parsed. Instead, it is sent for review to the [Microsoft Cloud App Security](https://aka.ms/whatiscas) technical team.  <br/> |The [Microsoft Cloud App Security](https://aka.ms/whatiscas) technical team builds a dedicated parser for each data source. Most popular data sources are already supported. When an unsupported data source is uploaded, it is reviewed and added to the list of potential new data source parsers.  <br/> When a new parser is added to the feature, a notification is included in the Microsoft Cloud App Security release notes.  <br/> |
   
## Next steps
<a name="nextsteps"> </a>

- [Review and take action on alerts](review-office-365-cas-alerts.md)
    
- [Create app discovery reports](create-app-discovery-reports-in-ocas.md)
    
- [Review app discovery findings](review-app-discovery-findings-in-ocas.md)
    
- Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

