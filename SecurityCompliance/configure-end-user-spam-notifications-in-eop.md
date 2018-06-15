---
title: "Configure end-user spam notifications in EOP"
ms.author: krowley
author: kccross
manager: scotv
ms.date: 11/17/2014
ms.audience: Developer
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
description: "In this articleWhat do you need to know before you begin?Use the EAC to configure end-user spam notificationsFor more information"
---

# Configure end-user spam notifications in EOP

 **In this article**
  
[What do you need to know before you begin?](#sectionSection0.md)
  
[Use the EAC to configure end-user spam notifications](#sectionSection1.md)
  
[For more information](#sectionSection2.md)
  
> [!IMPORTANT]
> This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes. Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.
  
End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.
  
After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team. For more information about how to manage spam-quarantined items after receiving a notification message, see [Use end-user spam notifications to release and report spam-quarantined messages](use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages.md).
  
## What do you need to know before you begin?
<a name="sectionSection0"> </a>

Estimated time to complete: 5 minutes
  
You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](exchange-online-protection-eop/feature-permissions-in-eop.md) topic. 
  
For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.
  
## Use the EAC to configure end-user spam notifications
<a name="sectionSection1"> </a>

1. In the Exchange admin center (EAC), navigate to **Protection** \> **Content filter**.
    
2. Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).
    
3. In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link. 
    
4. In the subsequent dialog box, you can configure the following options:
    
1. **Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.) 
    
2. **Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead. 
    
3. **Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy. 
    
5. Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.
    
> [!NOTE]
>  End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable. 
  
 **Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com: 
  
![Transport rule to test end-user spam notifications](media/EOP_ESN_testspecificusers.jpg)
  
## For more information
<a name="sectionSection2"> </a>

[Configure your spam filter policies](configure-your-spam-filter-policies.md)
  
[Use end-user spam notifications to release and report spam-quarantined messages](use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages.md)
  

