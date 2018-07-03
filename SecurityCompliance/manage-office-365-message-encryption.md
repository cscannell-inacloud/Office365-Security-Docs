---
title: "Manage Office 365 Message Encryption"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: "Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the Protect button in Outlook on the web, and more. The tasks in this article describe how."
---

# Manage Office 365 Message Encryption

Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how. 
  
||
|:-----|
|This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and IT Pros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs. |
   
## Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal
<a name="PermitSocialID"> </a>

By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a  *social ID*  such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal. 
  
 **To manage whether or not to allow recipients to use social IDs to sign in to the OME portal**
  
1. [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    For example, to disable social IDs:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    To enable social IDs:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal
<a name="GenerateOTPC"> </a>

By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.
  
 **To manage whether or not one-time pass codes are generated for OME**
  
1. [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter as follows:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    For example, to disable one-time pass codes:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    To enable one-time pass codes:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## Managing the display of the Protect button in Outlook on the web
<a name="DisplayProtectButton"> </a>

By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users. 
  
 **To manage whether or not the Protect button appears in Outlook on the web**
  
1. [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter as follows:
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    For example, to disable the **Protect** button: 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    To enable the **Protect** button: 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## Enable service-side decryption of email messages for iOS mail app users
<a name="EnableServiceSideDecrypt"> </a>

The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.
  
If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.
  
For more information, and for a view of the client experience, see the section, "[View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)" in [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
 **To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption**
  
1. [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter as follows:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    For example, to configure the service not to send decrypted messages to unenlightened apps:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## Enable service-side decryption of email attachments for web browser mail clients
<a name="EnableServiceSideDecrypt"> </a>

Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser. 
  
When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.
  
Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.
  
If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment. \*\*\* insert picture?
  
For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
 **To manage whether or not email attachments are decrypted on download from a web browser**
  
1. [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter as follows:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    To configure the service to leave encrypted email attachments as they are upon download:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## Customizing the appearance of email messages and the OME portal
<a name="CustomizeAppearance"> </a>

For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
## Disabling the new capabilities for OME
<a name="CustomizeAppearance"> </a>

We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.
  
 **To disable the new capabilities for OME**
  
1. [Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).
    
2. If you enabled the Protect button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter as follows:
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. Run the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter as follows:
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


