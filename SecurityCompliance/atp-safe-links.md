---
title: "Office 365 ATP Safe Links"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- '197503'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: "The Safe Links feature provides time-of-click verification of hyperlinks in Office documents and in email messages. Use Safe links to protect your organization from phishing and other attacks."
---

# Office 365 ATP Safe Links

Office 365 ATP Safe Links (ATP Safe Links) (along with [Office 365 ATP Safe Attachments](atp-safe-attachments.md)) is a set of security features offered as part of [Office 365 Advanced Threat Protection](office-365-atp.md) for enterprise organizations. ATP Safe Links can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents. Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team. 
  
Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.
         
## How ATP Safe Links works with email

At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):
  
1. People receive email messages, some of which contain URLs.
    
2. All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied. 
    
3. Email arrives in people's inboxes.
    
4. A user signs in to Office 365, and goes to their email inbox.
    
5. The user opens an email message, and clicks on a URL in the email message.
    
6. The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.
    
    - If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens. 
    
    - If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens. 
    
    - If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens. 
    
    - If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked. 
    
    - If the URL is determined to be safe, the website opens.
    
## How ATP Safe Links works with Office documents

At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of OneNote, Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, and Office Online):
  
1. People have installed Office 365 ProPlus on their computer, smartphone, or tablet.
    
2. A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.
    
3. When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.
    
  - If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website. 
    
  - If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).
    
  - If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).
    
  - If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked. 
    
  - If the URL is considered safe, the user is taken to the website.

## New features added to ATP Safe Links

We are continuing to add new features to ATP Safe Links. Here are several examples:
  
- Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices. (Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)
    
- Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.
    
- Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.
    
- Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations. 
    
## How to get ATP Safe Links protection

ATP Safe Links features are part of [Advanced Threat Protection](office-365-atp.md), included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).
  
The ATP Safe Links features are active when:
  
- **ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)

- **Office 365 client apps are configured to use Modern Authentication**. (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- **Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- **Your organization's email is hosted in Office 365**, not in an on-premises server. 
    
## Make sure ATP Safe Links protection is in place

One good way to see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md). Additionally, as a global or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.

## Example scenarios where ATP Safe Links protection might or might not be in place
  
The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)
  
|**Example scenario**|**Does ATP Safe Links protection apply in this case?**|
|:-----|:-----|
|Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a presentation that someone sent in PowerPoint 2016, and then clicks a URL in the presentation.  <br/> |Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.  <br/> |
|In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.  <br/> |No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.  <br/> |
|In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.  <br/> |No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  <br/> |It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  <br/> |
|Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.  <br/> |It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  <br/> |
   
## Related topics

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)
  
[ATP Safe Attachments in Office 365](atp-safe-attachments.md)
  
[ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)
  
[View the reports for Advanced Threat Protection](view-reports-for-atp.md)
  

