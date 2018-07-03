---
title: "Office 365 Message Encryption"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: "With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization. Email message encryption helps ensure that only intended recipients can view message content."
---

# Office 365 Message Encryption

With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization. Office 365 Message Encryption works with Outlook.com, Yahoo!, Gmail, and other email services. Email message encryption helps ensure that only intended recipients can view message content.
  
This article is part of a larger series of articles about Office 365 Message Encryption. Use the following table to quickly find the information you need.
  
|||
|:-----|:-----|
|Read this article...  <br/> |If you are...  <br/> |
|[Learn about protected messages in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |An end user that wants to learn more about how encrypted messages work and what options are available to you.  <br/> |
|[How do I open a protected message?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |An end user that wants to read a protected message that was sent to you. This article includes information about reading messages in several versions of Outlook and from different email accounts, including those outside of Office 365 such as gmail and Yahoo! accounts.  <br/> |
|[Send, view, and reply to encrypted messages in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |An end user that wants to send, view, or reply to an encrypted message from Outlook. Even if you're not a member of an Office 365 organization, you still receive notification of encrypted messages sent to you in Outlook. Use this article for instructions on how to to view and reply to encrypted messages sent from Office 365.  <br/> |
|[Send a digitally signed or encrypted message](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |An end user that wants to send, view, or reply to encrypted messages using Outlook for Mac. This article also covers using encryption methods other than OME, such as S/MIME.  <br/> |
|[View encrypted messages on your Android device](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |An end user who has received a message encrypted with Office 365 Message Encryption on your Android device, you can use the free OME Viewer app to view the message and send an encrypted reply. This article explains how.  <br/> |
|[View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |An end user who has received a message encrypted with Office 365 Message Encryption on your iPhone or iPad, you can use the free OME Viewer app to view the message and send an encrypted reply. This article explains how.  <br/> |
|Office 365 Message Encryption (OME) (this article)  <br/> |An Office 365 or Exchange Online Protection administrator that wants to learn where you can find additional resources.  <br/> |
|[Office 365 Message Encryption FAQ](ome-faq.md) <br/> |An Office 365 or Exchange Online Protection administrator who wants answers to commonly asked questions including licensing and a comparison between the new capabilities and legacy OME.  <br/> |
|[Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) <br/> |An Office 365 or Exchange Online Protection administrator who wants to learn how to set up the new Office 365 Message Encryption capabilities for your Office 365 organization.  <br/> |
|[Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) <br/> |An Office 365 or Exchange Online Protection administrator who has already set up Office 365 Message Encryption and you are ready to define mail flow rules to automatically encrypt email messages sent from your organization.  <br/> |
|[Manage Office 365 Message Encryption](manage-office-365-message-encryption.md) <br/> |An Office 365 or Exchange Online Protection administrator who has already set up Office 365 Message Encryption and wants to configure optional settings for OME.  <br/> |
|[Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md) <br/> |An Office 365 or Exchange Online Protection administrator who wants to apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the OME portal.  <br/> |
|Office 365 Message Encryption in the [Message Policy and Compliance service description](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption) <br/> |Looking for a detailed description of the Office 365 Message Encryption feature, including supported SKUs, available from Office 365.  <br/> |
|[Legacy information for Office 365 Message Encryption](legacy-information-for-message-encryption.md) <br/> |An Office 365 or Exchange Online Protection administrator who has already set up Office 365 Message Encryption and you want information about how OME worked before the release of the new capabilities. While you cannot set up a new deployment using OME without the new capabilities, Microsoft continues to support existing deployments.  <br/> |
   
The rest of this article applies to the new OME capabilities.
  
## How Office 365 Message Encryption works

Office 365 Message Encryption is an online service that's built on Microsoft Azure Rights Management (Azure RMS) which is part of Azure Information Protection. Office 365 administrators can define mail flow rules to determine the conditions for encryption. For example, a rule can require the encryption of all messages addressed to a specific recipient.
  
When someone sends an email message in Exchange Online that matches an encryption mail flow rule, the message is encrypted before it's sent. All Office 365 end-users that use Outlook clients to read mail receive native, first-class reading experiences for encrypted and rights-protected mail even if they're not in the same organization as the sender. Supported Outlook clients include Outlook desktop, Outlook Mac, Outlook mobile on iOS and Android, and Outlook Web App.
  
Recipients of encrypted messages who receive encrypted or rights-protected mail sent to their Outlook.com, Gmail, and Yahoo accounts can easily authenticate to the OME portal using their Microsoft account, or Gmail or Yahoo credentials.
  
End-users that read encrypted or rights-protected mail on clients other than Outlook also use the OME portal to view encrypted and rights-protected messages that they receive.
  
We've increased the size limits for messages and attachments that you can encrypt using Office 365 Message Encryption. For more information about limits, see [Exchange Online Limits.](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
  
## Defining rules for Office 365 Message Encryption
<a name="Rules"> </a>

One way to enable the new capabilities for Office 365 Message Encryption is for Exchange Online and Exchange Online Protection administrators to define mail flow rules. These rules determine under what conditions email messages should be encrypted. When an encryption action is set for a rule, any messages that match the rule conditions are encrypted before they're sent.
  
Mail flow rules are flexible, letting you combine conditions so you can meet specific security requirements in a single rule. For example, you can create a rule to encrypt all messages that contain specified keywords and are addressed to external recipients. The new capabilities for Office 365 Message Encryption also encrypt replies from recipients of encrypted email.
  
For more information about how to create mail flow rules to take advantage of the new OME capabilities, see [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).
  
## Sending, viewing, and replying to encrypted email messages
<a name="SendRecip"> </a>

With Office 365 Message Encryption, users can send encrypted email from Outlook and Outlook on the web. Additionally, admins can set up mail flow rules in Office 365 to automatically encrypt emails based on keyword matching or other conditions.
  
Recipients of encrypted messages who are in Office 365 organizations will be able to read those messages seamlessly in any version Outlook, including Outlook for PC, Outlook for Mac, Outlook on the web, Outlook for iOS, and Outlook for Android. Users that receive encrypted messages on other email clients can view the messages in the OME portal.
  
For detailed guidance about how to send and view encrypted messages, take a look at these articles:
  
- [How do I open a protected message?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)
    
- [Send, view, and reply to encrypted messages in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
    
## Get started with the new OME capabilities
<a name="SendRecip"> </a>

If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).
  

