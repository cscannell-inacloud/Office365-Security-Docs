---
title: "Prevent email from being marked as spam in Office 365 and Exchange Online Protection"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: "Tips for Office 365 Admins to prevent good email marked as spam from being sent to quarantine as a false positive. Customize a safelist and other options to prevent good email marked as spam."
---

# Prevent email from being marked as spam in Office 365 and Exchange Online Protection

Exchange Online or Exchange Online Protection (EOP) administrators with the appropriate access credentials can use these steps to help ensure that an email message traveling through the service isn't marked as spam.
  
It can be frustrating to have legitimate, good email quarantined or blocked as spam and landing in a quarantine folder. You can use a safe sender list or a mail flow rule to bypass spam filtering and prevent good email messages from getting marked as junk mail. When a message is incorrectly marked as spam by the spam filter, it's called a false positive. The Office 365 spam filter also provides some options that end users can customize in order to help prevent false positives.
  
If you're looking for help with false negative mail, that is, a spam message that gets through when it shouldn't, check out the tips in [Block email spam with the Office 365 spam filter to prevent false negative issues](block-email-spam-to-prevent-false-negatives.md).
  
## EOP-only customers: use directory synchronization

EOP is a cloud-based email filtering service that helps protect your organization against spam and malware. If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service. 
  
If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises Exchange Server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
  
## Prevent false positive email by using the connection filter's IP allow list

If you find that a sender's email is always moved to the Junk folders in your organization, you can add the email sender's IP address to your connection filter's IP allow list. Normally, this prevents false positive responses for this sender for all recipients within your organization. The exception is when a user enables the option "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox" in Outlook and does not add that sender to the Safe Sender List. For information on overriding that option, see [Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam).
  
 **To add an IP address to your connection filter's IP allow list**
  
1. Obtain the header from a message sent by the sender that you want to allow. You can do this from your mail client such as Outlook or Outlook on the Web, as described in [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).
    
2. Manually search for the IP address following the CIP tag in the X-Forefront-Antispam-Report header or by using the **Message Analyzer** tab of the [Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).
    
3. Add the IP address to the IP allow list by following the steps in "Use the EAC to edit the default connection filter policy" in [Configure the connection filter policy](https://go.microsoft.com/fwlink/?LinkId=534132).
    
## Prevent false positive email by configuring spam filter policies

You can add domains or individual email addresses to an allow list by following the steps in [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkID=534136).
  
## Review your advanced spam filter policies

If you have special restrictions set up in a spam filter policy, for example, if you have blocked an entire domain, you should review them to check if they may be causing false positives. See [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkId=534136), and turn off additional [Advanced spam filtering options](https://go.microsoft.com/fwlink/?LinkId=534137) that might cause messages to be marked as spam. 
  
## Help your end users create a safe sender list to prevent good email from being marked as spam
<a name="BKMK_email-user-help-safelist"> </a>

Tell your users to add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.
  
![Adding a safe sender in Outlook Web App](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.
  
## Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam
<a name="TroubleshootingJunkEOPNonSpam"> </a>

If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.
  
You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/en-us/kb/2180568).
  
If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.
  
If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting. 
  
 **To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**
  
1. To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Run the following command to view the user's junk email configuration settings:
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    If TrustedListsOnly is set to True, it means that this setting is enabled. If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders. The TrustedSendersAndDomains lists the contents of the user's Safe Senders list.
    
## Still need help?
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![Get help from the Office 365 community forums](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## See also
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[Overview of the Junk Email Filter](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[Block email spam with the Office 365 spam filter to prevent false negative issues](block-email-spam-to-prevent-false-negatives.md)

