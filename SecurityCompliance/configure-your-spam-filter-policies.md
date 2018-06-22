---
title: "Configure your spam filter policies"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047

description: "Basic spam filter settings include selecting the action to take on messages that are identified as spam, and choosing whether to filter messages that are written in specific languages or sent from specific countries or regions."
---

# Configure your spam filter policies
  
Basic spam filter settings include selecting the action to take on messages that are identified as spam, and choosing whether to filter messages that are written in specific languages or sent from specific countries or regions. Spam filter policy settings are applied to inbound messages only. You can edit the default spam filter policy to configure your company-wide spam filter settings and create custom spam filter policies, and then apply them to specific users, groups, or domains in your organization. Custom policies always take precedence over the default policy. You can change the order in which your custom policies run by changing the priority of each custom policy.
  
> [!IMPORTANT]
> For Exchange Online Protection (EOP) stand-alone customers: By default, the EOP spam filters send spam-detected messages to each recipient's Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action works for on-premises mailboxes, you must configure Exchange Transport rules on your on-premises servers to detect spam headers that are added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
## What you must know before you begin
<a name="sectionSection0"> </a>

Estimated time to complete: 30 minutes
  
You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic. 
  
For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.
  
## Use the Exchange Admin Center (EAC) to configure spam filter policies
<a name="sectionSection1"> </a>

1. In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.
    
2. Do one of the following on the **general** page: 
    
  - Double-click the default policy in order to edit this company-wide policy.
    
  - Click the ![Add Icon](media/ITPro-EAC-AddIcon.png) **New** icon in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization. You can also edit existing custom policies by double-clicking them. 
    
3. For custom policies only, specify a name for this policy. Optionally, you can also specify a more detailed description. You cannot rename the default policy.
    
    > [!NOTE]
    > When you create a policy, all configuration settings appear on a single screen. By contrast, when you edit a policy, you must navigate through multiple screens. The settings are the same in either case, but the rest of this procedure describes how to access these settings when you edit a policy. 
  
4. On the **spam and bulk email actions** page, under **Spam** and **High confidence spam**, select the action to take for incoming spam and bulk email. By default, **Move messages to Junk Email folder** is selected. The other possible values are: 
    
  - **Delete message** Deletes the entire message, including all attachments. 
    
  - **Quarantine message** Sends the message to quarantine instead of to the intended recipients. If you select this option, in the **Retain spam for (days)** input box, specify the number of days during which the spam message will be quarantined. (It will automatically be deleted after the time elapses. The default value is 15 days which is the maximum value. The minimum value is 1 day.) 
    
    > [!TIP]
    >  For information about how administrators can manage email messages that reside in the quarantine in the EAC, see [Quarantine](quarantine.md) and [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md). >  For information about how to configure spam notification messages to be sent to users, see [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md) or [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
  - **Move message to Junk Email folder** Sends the message to the Junk Email folder of the specified recipients. This is the default action for both confidence threshold levels. 
    
    > [!IMPORTANT]
    > For Exchange Online Protection (EOP) customers: In order for this action to work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
  - **Add X-header** Sends the message to the specified recipients, but adds X-header text to the message header in order to identify the message as spam. Using this text as an identifier, you can optionally create inbox rules or use a downstream device to act on the message. The default X-header text is **This message appears to be spam**.
    
    You can customize the X-header text by using the **Add this X-header text** input box. If you customize the X-header text, be aware of the following conditions: 
    
  - If you specify only the header in the format \< *header*  \>, where there are no spaces within the \<  *header*  \>, a colon will be appended to the custom text, followed by the default text. For example, if you specify "This-is-my-custom-header," the X-header text will appear as "This-is-my-custom-header: This message appears to be spam." 
    
  - If you include spaces within the custom header text, or if you add the colon yourself (such as "X This is my custom header" or "X-This-is-my-custom-header:"), the X-header text reverts to the default as "X-This-Is-Spam: This message appears to be spam."
    
  - You can't specify the header text in the format \< *header*  \>:\<  *value*  \>. If you do this, both values before and after the colon will be ignored, and the default X-header text appears instead: "X-This-Is-Spam: This message appears to be spam." 
    
  - **Prepend subject line with text** Sends the message to the intended recipients but prepends the subject line with the text that you specify in the **Prefix subject line with this text** input box. Using this text as an identifier, you can optionally create rules to filter or route the messages as necessary. 
    
  - **Redirect message to email address** Sends the message to a designated email address instead of to the intended recipients. Specify the "redirect" address in the **Redirect to this email address** input box. 
    
    > [!NOTE]
    > For more information about spam confidence levels, see [Spam confidence levels](spam-confidence-levels.md). 
  
5. Under **Bulk email**, you can select a threshold to treat bulk email as spam. This threshold is based on the bulk complaint level of the message. You can choose a threshold setting from 1 to 9, where 1 indicates most bulk email as spam, and 9 allows the most bulk email to be delivered. The service then performs the configured action, such as sending the message to the recipient's Junk Email folder. See [Bulk Complaint Level values](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) for more details. 
    
6. On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries. 
    
  - Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page. 
    
  - Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page. 
    
    > [!CAUTION]
    > If you block top-level domains, it's likely that email you want will be marked as spam. 
  
7. On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. 
    
  - Add trusted senders to the Sender allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page. 
    
  - Add trusted domains to the Domain allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page. 
    
    > [!CAUTION]
    > If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox. 
  
8. On the **International Spam** page you can filter email messages that are written in specific languages or sent from specific countries or regions. You can configure up to 86 different languages and 250 different regions. The service will apply the configured action for high-confidence spam. 
    
1. Select the **Filter email messages written in the following languages** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter messages written in Arabic (AR), and **Quarantine message** is your configured action for high confidence spam messages, any messages written in Arabic will be quarantined. Click **ok** to return to the **International Spam** pane. 
    
2. Select the **Filter email messages sent from the following countries or regions** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter all messages that are sent from Australia (AU), and **Quarantine message** is your configured action for high-confidence spam messages, then any messages that is sent from Australia will be quarantined. Click **ok** to return to the **International Spam** pane. 
    
    > [!NOTE]
    > By default, if no international spam options are selected, the service performs normal spam filtering on messages sent in all languages and from all regions. Messages are analyzed and the configured actions are applied if the message is determined to be spam or high confidence spam. 
  
9. On the **Advanced Options** page, you can select **On**, **Off**, or **Test** for each advanced spam filtering option. 
    
1. **On** Messages are actively filtered according to the rule that is associated with that option. Messages are either marked as spam or will have their spam scores increased, depending on which options you turn on. 
    
2. **Off** No action is taken on messages that meet the spam filter criteria. All options are turned off by default. 
    
3. **Test** No action is taken on messages that meet the spam filter criteria. However, messages can be tagged by adding an X-header before they are delivered to the intended recipient. This X-header lets you know which ASF option was matched. If you specified **Test** for any of the advanced options, you can configure the following test mode settings to be applied when a match is made to a test-enabled option: 
    
  - **None** Take no test mode action on the message. This is the default. 
    
  - **Add the default test X-header text** Selecting this option sends the message to the specified recipients, but also adds a special X-header to the message to identify it as having matched a specific advanced spam filtering option. 
    
  - **Send a Bcc message to this address** Selecting this option sends a blind carbon copy of the message to the email address that you specify in the input box. 
    
    > [!TIP]
    > For more information about the advanced spam filtering options, including descriptions about each option and the X-header text that is associated with each one, see [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md). 
  
10. For custom policies only, click the **Apply to** menu item, and then create a condition-based rule to specify the users, groups, and domains to which to apply this policy. You can create multiple conditions, if they are unique. 
    
  - To select users, select **The recipient is**. In the subsequent dialog box, select one or more senders from your company from the user picker list, and then click **add**. To add senders who aren't on the list, type their email addresses, and then click **Check names**. In this box, you can also use wildcards for multiple email addresses (for example: \*@ _domainname_). When you are done making your selections, click **ok** to return to the main screen. 
    
  - To select groups, select **The recipient is a member of**. Then, in the subsequent dialog box, select or specify the groups. Click **ok** to return to the main screen. 
    
  - To select domains, select **The recipient domain is**. Then, in the subsequent dialog box, add the domains. Click **ok** to return to the main screen. 
    
    You can create exceptions within the rule. For example, you can filter messages from all domains except for a certain domain. Click **add exception**, and then create your exception conditions similar to the way that you created the other conditions.
    
    > [!TIP]
    > Applying a spam policy to a group is supported only for **Mail Enabled Security Groups**. 
  
11. Click **save**. A summary of your policy settings appears in the right pane.
    
> [!TIP]
>  You can select or clear the check boxes in the **ENABLED** column to enable or disable your custom policies. By default, all policies are enabled. The default policy cannot be disabled. >  To delete a custom policy, select the policy, click the ![Delete icon](media/ITPro-EAC-DeleteIcon.png) **Delete** icon, and then confirm that you want to delete the policy. The default policy cannot be deleted. >  Custom policies always take precedence over the default policy. Custom policies run in the reverse order in which you created them (from oldest to newest), but you can change the priority (running order) of your custom policies by clicking the ![Up Arrow Icon](media/ITPro-EAC-UpArrowIcon.png) up arrow and ![Down Arrow Icon](media/ITPro-EAC-DownArrowIcon.png) down arrow. The policy that has a **PRIORITY** of **0** will run first, followed by **1**, then **2**, and so on. 
  
## Use remote PowerShell to configure spam filter policies
<a name="sectionSection2"> </a>

You can also configure and apply spam filter policies in PowerShell. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) View your spam filter settings. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Edit your spam filter settings. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Create a new custom spam filter policy. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Delete a custom spam filter policy. 
    
To apply a custom spam filter policy to users, groups, and/or domains, use the [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet (to create a new filter rule that can be applied to custom policies) or the [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet (to edit an existing filter rule that can be applied to custom policies). Use the [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet or the [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet to enable or disable the rule applied to the policy. 
  
## How do you know this worked?
<a name="sectionSection3"> </a>

To ensure that spam is being properly detected and acted upon, you can send a GTUBE message through the service. Similar to the EICAR antivirus test file, GTUBE provides a test by which you can verify that the service is detecting incoming spam. A GTUBE message should always be detected as spam by the spam filter, and the actions that are performed upon the message should match your configured settings.
  
Include the following GTUBE text in a mail message on a single line, without any spaces or line breaks:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## Fine tuning your spam filter policy to prevent false positives and false negatives
<a name="sectionSection4"> </a>

You can enable advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. For general spam settings that apply to the whole organization, take a look at [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.
  
## New to Office 365?
<a name="sectionSection5"> </a>

||
|:-----|
|![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning. |
   
## For more information
<a name="sectionSection6"> </a>

[Configure the connection filter policy](configure-the-connection-filter-policy.md)
  
[Configure the outbound spam policy](configure-the-outbound-spam-policy.md)
  
[Quarantine](quarantine.md)
  
[Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

