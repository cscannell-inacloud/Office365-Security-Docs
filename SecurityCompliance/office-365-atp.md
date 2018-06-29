---
title: "Office 365 Advanced Threat Protection"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: "Office 365 Advanced Threat Protection includes spoof intelligence, safe links, safe attachments, and advanced anti-phishing capabilities. Advanced Threat Protection is also being extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams."
---

# Office 365 Advanced Threat Protection

Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:
  
- Scanning email attachments with [ATP Safe Attachments](atp-safe-attachments.md)
    
- Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)
    
- Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)
    
- Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)
    
- Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)
    
Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. And, you can [submit suspicious files to Microsoft for analysis](office-365-atp.md#submitlalware).
  
> [!IMPORTANT]
> Office 365 ATP is included in subscriptions, such as Office 365 Enterprise E5 and Office 365 Education A5, and, as of April 30, 2018, also [Microsoft 365 Business security features](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx). 
      
## Get Office 365 ATP
<a name="getatp"> </a>

1. As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365. 
    
2. Choose **Admin** \> **Billing** to see what your current subscription includes. 
    
    ![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP. 
    
    If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.
    
Once you have ATP, the next step is for your security team to define policies for [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-atp-anti-phishing-policies.md) protection. 
  
[What do you want to do?](office-365-atp.md#TOC)
  
## Define policies for ATP
<a name="policies"> </a>

- **[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
- **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [dynamic delivery and previewing](dynamic-delivery-and-previewing.md)
    
- **[Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains 
    
- 
    
[What do you want to do?](office-365-atp.md#TOC)
  
## See how ATP is working by viewing reports
<a name="reports"> </a>

After your ATP policies are in place, reports are available to show how the service is working.
  
****

[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)
    
2. [View reports for Advanced Threat Protection and Exchange Online Protection](view-reports-for-atp.md) , including the [](view-reports-for-atp.md#advancedthreats_1_1_1_1_1).
    
3. If needed, make adjustments to your security policies. See the following resources:
    
  - [ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)
    
  - [ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)
    
  - [ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md)
    
[What do you want to do?](office-365-atp.md#TOC)
  
## Submit a suspicious file to Microsoft for analysis
<a name="submitfile"> </a>

If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).
  
[What do you want to do?](office-365-atp.md#TOC)
  
## Related topics
<a name="submitfile"> </a>

[Overview of the Office 365 Security &amp; Compliance Center](https://support.office.com/article/a5f2fd18-b029-4257-b5a8-ae83e7768c85)
  
[View the reports for Advanced Threat Protection](view-reports-for-atp.md)
  
[Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md)
  

