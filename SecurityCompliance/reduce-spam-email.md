---
title: "How to reduce spam email in Office 365"
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: "Learn the most common ways to help reduce spam and junk mail in Office 365."
---

# How to reduce spam email in Office 365

 **Are you getting too much spam in Office 365? Do this.**
  
Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. If you see a message header named X-Forefront-Antispam-Report that contains the string SFV:NSPM, this means that Exchange Online Protection (EOP) scanned the message and didn't think it was spam. In this case, we strongly recommend that you [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. If you don't see this value in the headers, it could mean either that the mail didn't pass through spam scanning, or that there was a configuration issue that caused the message to be ignored. In this case, consult the info below. 
  
You can learn more about [anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
## Solutions to common causes of getting too much spam

In order to protect you from getting too much spam, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.
  
### For admins

- **Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your [MX does not point to Office 365](https://blogs.msdn.microsoft.com/tzink/2017/12/28/if-you-use-office-365-but-your-mx-record-doesnt-point-to-office-you-may-want-to-close-down-your-security-settings/), then EOP will not provide spam filtering for your users. See [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Enable the junk mail rule on all mailboxes** By default, the spam filtering action is set to **Move message to Junk Email folder**. If this is the preferred and current spam policy action, then each mailbox [must also have the junk mail rule enabled](https://blogs.msdn.microsoft.com/tzink/2017/12/14/making-sure-your-junk-email-filtering-is-enabled-in-office-365/). To check this, you can run the Get-MailboxJunkEmailConfiguration cmdlet against one or more mailboxes. For example, you might check all mailboxes for this by running the following: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    When viewing the output, the Enable property should be set to True. If it is set to False, you can run Set-MailboxJunkEmailConfiguration to change it to True.
    
- **Check your mail flow rules and safe lists** Look at the message header for a message that should have been marked as spam. Find the SCL property in the X-Forefront-Antispam-Report header. If the SCL value is -1, this indicates that the message was safe listed and bypassed EOP spam filtering. Investigate mail flow rules, allow lists, and the recipient's allowed senders list. A [Find and fix email delivery issues as an Office 365 for business admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) will also be useful in providing details about why a message received an SCL of -1. 
    
- **Create mail flow rules in on-premises Exchange Server** If you are using Exchange Online Protection, but your mailboxes are located in on-premises Exchange Server, then you will need to create a couple of mail flow rules in on-premises Exchange Server. See the [instructions for EOP-only](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0).
    
- **Mark bulk email as spam** Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the spam filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/) is handled. You can create different policies or rules for different user preferences. 
    
- **Immediately block a sender** In the case where you need to immediately block a sender, you can block by email address, domain, or IP address. See [Block email spam with the Office 365 spam filter to prevent false negative issues](block-email-spam-to-prevent-false-negatives.md). An entry in an end-user allow list can override a block set by the administrator.
    
- **Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.
    
### For users

- **Enable the junk mail rule and check your allow list** Check that the junk mail action rule is enabled and that the sender or sender's domain is not set to bypass in your personal allow list. The best way to access these settings is from [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). While you are there, you may also choose to block the sender's email address or domain.
    
- **Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.
    
    **Important** If you do not forward the messages as attachments, then [the headers will be missing and we will be unable to improve](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) the junk mail filtering in Office 365. 
    
- **Unsubscribe from bulk email** If the message was something that you signed up for (newsletters, product announcements, etc.) and contains an unsubscribe link from a reputable source, you may want to simply unsubscribe. Office 365 does not typically treat these messages as spam. You can also choose to block the sender, or ask your administrator to make a change that will cause all bulk mail to be treated as spam. 
    

