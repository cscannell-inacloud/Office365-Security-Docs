---
title: "Set up new Office 365 Message Encryption capabilities"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: 
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: "New Office 365 Message Encryption capabilities built on top of Azure Information Protection, your organization can use protected email communication with people inside and outside your organization. The new OME capabilities work with other Office 365 organizations, Outlook.com, Gmail, and other email services."
---

# Set up new Office 365 Message Encryption capabilities

With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.
  
## Get started with OME by activating Azure Rights Management, part of Azure Information Protection

It's now easy to get started with the new OME capabilities. As of February 2018, Office 365 automatically enables the new OME capabilities for eligible organizations within our datacenters. Your organization is eligible if it is a new Office 365 tenant and your organization has the appropriate subscriptions. ** If ** ** you have enabled Azure Rights Management (Azure RMS), part of Azure Information Protection, then we automatically enable Office 365 Message Encryption for you. ** You don't have to do anything else to enable OME. To activate Azure Rights Management, see [Activating Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/deploy-use/activate-service).﻿ For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ](ome-faq.md).﻿ For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).
  
If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to migrate from AD RMS to Azure Information Protection first. When you've finished the migration, you can successfully complete these steps.
  
If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.
  
## How the new capabilities for OME work

The new Office 365 Message Encryption capabilities use the protection capabilities, also called Azure Rights Management (Azure RMS), from Azure Information Protection. This includes encryption, identity, and authorization policies to help secure your email. You can encrypt messages by using rights management templates, the [Do Not Forward option](https://docs.microsoft.com/en-us/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails), and the [encrypt-only option](https://docs.microsoft.com/en-us/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Users can then encrypt email messages and a variety of Office 365 attachments by using these options. For a full list of supported attachment types, see ["File types covered by IRM policies when they are attached to messages" in Introduction to IRM for email messages](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). As an administrator, you can also define mail flow rules to apply this protection. For example, you can define a rule where all unprotected messages that are addressed to a specific recipient or that contain specific words in the subject line are protected from unauthorized access, and the recipients can't copy or print the contents of the message.
  
Unlike the previous version of OME, these new capabilities provide a unified sender experience whether you're sending mail inside your organization or to recipients outside of Office 365. In addition, recipients who receive a protected email message sent to an Office 365 account in Outlook 2016 or Outlook on the web, don't have to take any additional action to view the message. It works seamlessly. Recipients using other email clients and email service providers also have an improved experience. For information, see [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) and [How do I open a protected message](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).
  
## Steps to manually set up the new capabilities for OME

If your organization does not automatically have OME enabled, or if you turned OME off, follow these steps to manually set up the new capabilities for OME.
  
### To manually set up the new capabilities for OME

1. Ensure you have the right subscription for your organization. For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ.](ome-faq.md)﻿ For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).
    
2. Decide whether you want Microsoft to manage the root key for Azure Information Protection (the default), or generate and manage this key yourself (known as bring your own key, or BYOK). If you want to generate and manage this key yourself, you need to complete some steps before you set up the new capabilities for OME. For more information, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key). Microsoft recommends that you complete these steps before you set up OME.
    
3. Enable the new capabilities for OME by activating Azure Rights Management. For instructions, see [Activating Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/deploy-use/activate-service).﻿ When you do this, Office 365 automatically enables the new OME capabilities for you.
    
    > [!TIP]
    > Outlook on the Web caches its UI, so it's a good idea to wait a day before you try applying the new capabilities for OME to email messages using this client. Before the UI updates to reflect the new configuration, the new capabilities for OME won't be available. After the UI updates, users can protect email messages by using the new capabilities for OME. 
  
4. (Optional) Set up new mail flow rules or update existing mail flow rules that define how and when you want Office 365 to encrypt messages sent from your organization.
    
## Verify that the new capabilities for OME are configured properly by using Windows PowerShell

Follow these steps to verify that your tenant is properly configured to use the new capabilities for OME through Exchange Online PowerShell.
  
1. Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Run the Test-IRMConfiguration cmdlet using the following syntax:
    
  ```
  Test-IRMConfiguration [-Sender <email address >]
  ```

    For example:
    
  ```
  Test-IRMConfiguration -Sender securityadmin@contoso.com
  ```

    Where email address is the email address of a user in your Office 365 organization. While optional, providing a sender email address forces the system to perform additional checks.
    
    Your results should look like these:
    
  ```
  Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.
            
            OVERALL RESULT: PASS
  ```

    Where  *Contoso*  is replaced with the name of your Office 365 organization. 
    
    The names of the default templates returned in the results may be different from those displayed in the results above.
    
    For an introduction to templates and information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the Do Not Forward option, encrypt-only option, and how to create additional templates, or find out what rights are included in an existing template, see [Configuring usage rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).
    
3. Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.
    
  ```
  Remove-PSSession $session
  ```

## Next steps: Define new mail flow rules that use the new OME capabilities
<a name="Rules_1"> </a>

This step is optional for new OME deployments, however, this step is required for existing OME deployments that already have mail flow rules set up to encrypt outgoing mail. If you want to take advantage of the new OME capabilities, you must update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.
  
Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption. When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.
  
For more information about mail flow rules, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## Related Topics
<a name="Rules_1"> </a>

[Send, view, and reply to encrypted messages in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[Enable-Aadrm](https://docs.microsoft.com/en-us/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md)
  

