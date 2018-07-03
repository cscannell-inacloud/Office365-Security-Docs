---
title: "Dynamic delivery and previewing with Office 365 ATP Safe Attachments"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: "When you set up your ATP safe attachments policies, you choose Dynamic Delivery to avoid message delays and enable people to preview attachments that are being scanned."
---

# Dynamic delivery and previewing with Office 365 ATP Safe Attachments

Dynamic delivery is an option that can be selected for . Read this article to learn about dynamic delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).
  
## How dynamic delivery works

When you [set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md), you can choose from several options, such as **Block**, **Replace**, and **Dynamic Delivery**. Depending on how your policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.
  
The dynamic delivery option eliminates email delays by sending the body of an email message through with a placeholder for each email attachment. The placeholder remains until the attachment is scanned by [ATP Safe Attachments in Office 365](atp-safe-attachments.md). Email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.
  
Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the dynamic delivery previewer, email recipients see the attachment placeholder until ATP Safe Attachments scanning is complete.
  
As each attachment is cleared, it is automatically reattached to the original email message. If an attachment is determined to be malicious, it is sent to quarantine, where an [Office 365 global administrator or security administrator](permissions-in-the-security-and-compliance-center.md) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).
  
## What happens when someone forwards an email that contains an attachment?

Suppose that an organization is using dynamic delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.
  
- If a recipient is covered by an ATP Safe Attachments policy using the dynamic delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.
    
- If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.
    
## What's required for dynamic delivery to work?

- Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)
    
- Policies must be defined for ATP Safe Attachments using the dynamic delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))
    
- Your organization's email must be hosted in Office 365
    
## Are there scenarios for which dynamic delivery is not available?

There are certain scenarios in which dynamic delivery is not supported. These include the following:
  
- Email messages that are in public folders
    
- Email messages that are routed out of and then back into the user's mailbox using custom rules
    
- Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders
    
- Messages that are deleted
    
- A user's mailbox search folder that is in an error state
    
- Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))
    
## Related topics

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP Safe Attachments in Office 365](atp-safe-attachments.md)
  
[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)
  
[ATP Safe Links in Office 365](atp-safe-links.md)
  

