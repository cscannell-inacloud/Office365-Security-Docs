---
title: "Alert policies in the Office 365 Security &amp; Compliance Center"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/8/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
description: "Create alert policies in the Office 365 Security &amp; Compliance Center to monitor potential threats, data loss, and permissions issue . Then you can view and manage the alerts that are generated when users perform activities that match the conditions of an alert policy."
---

# Alert policies in the Office 365 Security &amp; Compliance Center

You can use the new alert policy and alert dashboard tools in the Office 365 Security &amp; Compliance Center to create alert policies and then view the alerts that are generated when users perform activities that match the conditions of an alert policy. Alert policies build on and expand the functionality of activity alerts by letting you categorize the alert policy, apply the policy to all users in your organization, set a threshold level for when an alert is triggered, and decide whether or not to receive email notifications. There's also a **View alerts** page in the Security &amp; Compliance Center where you can view and filter alerts, set an alert status to help you manage alerts, and then dismiss alerts after you've addressed or resolved the underlying incident. We've also expanded the type of events that you can create alerts for. For example, you can create alert policies to track malware activity and data loss incidents. Finally, we've also included a number of default alert policies that help you monitor assigning admin privileges in Exchange Online, malware attacks, and unusual levels of file deletions and external sharing. 
  
> [!NOTE]
> Alert policies are available for organizations with an Office 365 Enterprise E1, E3, or E5 subscription. However, some advanced functionality is only available for organizations with an E5 subscription, or for organizations that have an E1 or E3 subscription and an Office 365 Threat Intelligence or Office 365 Advanced Compliance add-on subscription. The functionality that requires an E5 or add-on subscription is highlighted in this topic. 
  
 **Contents**
  
[How alert policies work](alert-policies.md#whatisanalert)
  
[Alert policy settings](alert-policies.md#alertpolicysettings)
  
[Default alert policies](alert-policies.md#builtinalerts)
  
[Viewing alerts](alert-policies.md#viewingalerts)
  
[Managing alerts](alert-policies.md#managingalerts)
  
## How alert policies work
<a name="whatisanalert"> </a>

Here's a quick overview of how alert policies work and the alerts that are triggers when user or admin activity match the conditions of an alert policy.
  
![Overview of how alert policies work](media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)
  
1. An admin in your organization creates, configures, and turns on an alert policy by using the **Alert policies** page in the Security &amp; Compliance Center. You can also create alert policies by using the **New-ProtectionAlert** cmdlet in PowerShell. 
    
2. A user performs an activity that matches the conditions of an alert policy. In the case of malware attacks, infected email messages sent to users in your organization will trigger an alert.
    
3. Office 365 generates an alert that's displayed on the **View alerts** page in the Security &amp; Compliance Center. Also, if email notifications are enabled for the alert policy, Office 365 sends an notification to a list recipients. 
    
4. An admin manages alerts in the Security &amp; Compliance Center. Managing alerts consists of assigning an alert status to help track and manage any investigation.
    
[Return to top](alert-policies.md#top)
  
## Alert policy settings
<a name="alertpolicysettings"> </a>

An alert policy consists of a set of rules and conditions that define the user or admin activity that will generate an alert, a list of users who will trigger the alert if they perform the activity, and threshold that defines how many times the activity has to occur before an alert is triggered. You also categorize the policy and assign it a severity level. These two settings help you manage alert policies (and the alerts that are triggered when the policy conditions are matched) because you can filter on these settings when managing policies and viewing alerts in the Security &amp; Compliance Center. For example, you can view alerts that match the conditions from the same category or view alerts with the same severity level.
  
To view and create alert policies, go to **Alerts** \> **Alert policies** in the Security &amp; Compliance Center. 
  
![In the Security &amp; Complinace Center, click Alerts, then click Alert policies to view and create alert policies](media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)
  
An alert policy consists of the following settings and conditions.
  
- **Activity the alert is tracking**You create a policy to track an activity or in some case a few related activities, such a sharing a file with an external user by sharing it, assigning access permissions, or creating an anonymous link. When a user performs the activity defined by the policy, an alert is triggered based on the alert threshold settings.
    
    > [!NOTE]
    > The activities that you can track depend on your organization's Office 365 Enterprise subscription. In general, activities related to malware campaigns and phishing attacks require an E5 subscription or an E1 or E3 subscription with a Threat Intelligence add-on subscription. 
  
- **Activity conditions**For most activities, you can define additional conditions that must be met for an alert to be triggered. Common conditions include IP addresses (so that an alert is triggered when the user performs the activity on a computer with a specific IP address or within an IP address range), whether an alert is triggered if a specific user or users perform that activity, and whether the activity is performed on a specific file name or URL. You can also configure a condition that triggers an alert when the activity is performed by any user in your organization. Note that the available conditions are dependent on the selected activity.
    
- **When the alert is triggered**You can configure a setting that defines how often an activity can occur before an alert is triggered. This allows you to set up a policy to generate an alert every time an activity matches the policy conditions, when a certain threshold is exceeded, or when the occurrence of the activity the alert is tracking becomes unusual for our organization. 
    
    ![Configure how alerts are triggered, based on when the activity occurs, a threshold, or unusual activity for your organization](media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)
  
    If you select the setting based on unusual activity, Office 365 establishes a baseline value that defines the normal frequency for the selected activity; it takes up to 7 days to establish this baseline, during which alerts won't be generated. After the baseline is established, an alert will be triggered when the frequency of the activity tracked by the alert policy greatly exceeds the baseline value. For auditing-related activities (such as file and folder activities), you can establish a baseline based on a single user or based on all users in your organization; for malware-related activities, you can establish a baseline based on a single malware family, a single recipient, or all messages in your organization.
    
    > [!NOTE]
    > The ability to configure alert policies based on a threshold or based on unusual activity requires an E5 subscription, or an E1 or E3 subscription with a Threat Intelligence or Advanced Compliance add-on subscription. Organizations with an E1 and E3 subscription can only create an alert policy where an alert is triggered every time that an activity occurs. 
  
- **Alert category**To help with tracking and managing the alerts generated by a policy, you can assign one of the following categories to a policy.
    
  - Data governance
    
  - Data loss protection
    
  - Permissions
    
  - Threat management
    
  - Others
    
    When an activity occurs that matches the conditions of the alert policy, the alert that's generated is tagged with the category defined in this setting. This allows you to track and manage alerts that have the same category setting on the **View alerts** page in the Security &amp; Compliance Center because you can sort and filter alerts based on category. 
    
- **Alert severity**Similar to the alert category, you assign a severity attribute ( **Low**, **Medium**, or **High**) to alert policies. Like the alert category, when an activity occurs that matches the conditions of the alert policy, the alert that's generated is tagged with the same severity level that's set for the alert policy. Again, this allows you to track and manage alerts that have the same severity setting on the **View alerts** page. For example, you can filter the list of alerts so that only alerts with a **High** severity are displayed. 
    
    > [!TIP]
    > When setting up an alert policy, consider assigning a higher severity to activities that can result in severely negative consequences, such as detection of malware after delivery to users, viewing of sensitive or classified data, sharing data with external users, or other activities that can result in data loss or security threats. This can help you prioritize alerts and the actions you take to investigate and resolve the underlying causes. 
  
- **Email notifications** You can set up the policy so that email notifications are sent (or not sent) to a list of users when an alert is triggered. You can also set a daily notification limit so that once the maximum number of notifications has been reached, no more notifications are sent for the alert during that day. In additional to email notifications, you or other administrators can view the alerts that are triggered by a policy on the **View alerts** page. Consider enabling email notifications for alert policies of a specific category or that have a higher severity setting. 
    
[Return to top](alert-policies.md#top)
  
## Default alert policies
<a name="builtinalerts"> </a>

Office 365 provides built-in alert policies that help identify Exchange admin permissions abuse, malware activity, and data governance risks. On the **Alert policies** page, the name of these built-in policies are in bold and the policy type is defined as **System**. These policies are turned on by default. You can turn these policies off (or back on again), set up a list of recipients to send email notifications to, and set a daily notification limit. The other settings for these policies can't be edited.
  
The following table lists and describes the available default alert policies and indicates the Office 365 Enterprise subscription required for each one. Note that some default alert policies are available if your organization has the appropriate add-on subscription in addition to an E1 or E3 subscription. 
  
|**Default alert policy**|**Description**|**Office 365 Enterprise subscription**|
|:-----|:-----|:-----|
|**Creation of forwarding/redirect rule** <br/> |Generates an alert when someone in your organization creates an inbox rule for their mailbox that forwards or redirects messages to another email account. This policy only tracks inbox rules that are created using Outlook Web App or Exchange Online PowerShell. This policy has a **Low** severity setting. For more information using inbox rules to forward and redirect email in Outlook Web App, see [Use rules in Outlook Web App to automatically forward messages to another account](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).  <br/> |E1, E3, or E5  <br/> |
|**Elevation of Exchange admin privilege** <br/> |Generates an alert when someone is assigned administrative permissions in your Exchange Online organization; for example, if a user is added to the Organization Management role group in Exchange Online. This policy has a **Low** severity setting.  <br/> |E1, E3, or E5  <br/> |
|**Messages have been delayed** <br/> |Generates an alert when Office 365 can't deliver email messages to your on-premises organization or a partner servers by using a connector. When this happen, the message is queued in Office 365. This alert is triggered when there are 2,000 messages or more that have been queued for more than an hour. This policy has a **High** severity setting.  <br/> |E1, E3, or E5  <br/> |
|**Malware campaign detected after delivery** <br/> |Generates an alert when an unusually large number of messages containing malware are delivered to mailboxes in your organization. If this event occurs, Office 365 removes the infected messages from Exchange Online mailboxes. This policy has a **High** severity setting.  <br/> |E5 or Office 365 Threat Intelligence add-on subscription  <br/> |
|**Malware campaign detected and blocked** <br/> |Generates an alert when someone has attempted to send an unusually large number of email messages containing a certain type of malware to users in your organization. If this event occurs, the infected messages are blocked by Office 365 and not delivered to mailboxes. This policy has a **Low** severity setting.  <br/> |E5 or Office 365 Threat Intelligence add-on subscription  <br/> |
|**Malware campaign detected in SharePoint and OneDrive** <br/> |Generates an alert when an unusually high volume of malware or viruses are detected in files located in SharePoint sites or OneDrive accounts in your organization. This policy has a **High** severity setting.  <br/> |E5 or Office 365 Threat Intelligence add-on subscription  <br/> |
|**Unusual external user file activity** <br/> |Generates an alert when an usually large number of activities are performed on files in SharePoint or OneDrive by users outside of your organization. This includes activities such as accessing files, downloading files, and deleting files. This policy has a **High** severity setting.  <br/> |E5, or Office 365 Threat Intelligence or Advanced Compliance add-on subscription  <br/> |
|**Unusual volume of external file sharing** <br/> |Generates an alert when an usually large number of files in SharePoint or OneDrive are shared with users outside of your organization. This policy has a **Medium** severity setting.  <br/> |E5, or Office 365 Threat Intelligence or Advanced Compliance add-on subscription  <br/> |
|**Unusual volume of file deletion** <br/> |Generates an alert when an unusually large number of files are deleted in SharePoint or OneDrive within a short time frame. This policy has a **Medium** severity setting.  <br/> |E5, or Office 365 Threat Intelligence or Advanced Compliance add-on subscription  <br/> |
|**Unusual increase in email reported as phish** <br/> |Generates an alert when there is a significant increase in the number of people in your organization using the Report Message add-in in Outlook to report messages as phishing mail. This policy has a **High** severity setting. For more information about this add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).  <br/> |E5 or Office 365 Threat Intelligence add-on subscription  <br/> |
   
Note that the unusual activity monitored by some of the built-in policies is based on the same process as the alert threshold setting that was previously described. Office 365 establishes a baseline value that defines the normal frequency for "usual" activity. Alerts are then triggered when the frequency of activities tracked by the built-in alert policy greatly exceeds the baseline value.
  
[Return to top](alert-policies.md#top)
  
## Viewing alerts
<a name="viewingalerts"> </a>

When an activity performed by users in your organization match the settings of an alert policy, an alert is generated and displayed on the **View alerts** page in the Security &amp; Compliance Center. Depending on the settings of an alert policy, an email notification is also sent to a list of specified users when an alert is triggered. For each alert, the dashboard on the **View alerts** page displays the name of the corresponding alert policy, the severity and category for the alert (defined in the alert policy) and the number of times an activity has occurred that resulted in the alert being generated; this value is based on the threshold setting of the alert policy. The dashboard also shows the status for each alert. See the [Managing alerts](alert-policies.md#managingalerts) section for more information about using the status property to manage alerts. 
  
To view alerts, go to **Alerts** \> **View alerts** in the Security &amp; Compliance Center. 
  
![In the Security &amp; Complinace Center, click Alerts, then click View alerts to view alerts](media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)
  
You can use the following filters to view a subset of all the alerts on the **View alerts** page. 
  
- **Status**Use this filter to show alerts that are assigned a particular status; the default status is **Active**. You or other administrators can change the status value.
    
- **Policies**Use this filter to show alerts that match the setting of one or more alert policies. Or, you can just display all alerts for all alert policies.
    
- **Time range**Use this filter to show alerts that were generated within a specific date and time range.
    
- **Severity**Use this filter to show alerts that are assigned a specific severity.
    
- **Category**Use this filter to show alerts from one or more alert categories.
    
[Return to top](alert-policies.md#top)
  
## Managing alerts
<a name="managingalerts"> </a>

After alerts have been generated and displayed on the **View alerts** page in the Security &amp; Compliance Center, you can triage, investigate, and resolve them. Here are some tasks you can perform to manage alerts. 
  
- **Assign a status to alerts**You can assign one of the following statuses to alerts: **Active** (the default value), **Investigating**, **Resolved**, or **Dismissed**. Then, you can filter on this setting to display alerts with the same status setting. This status setting can help track the process of managing alerts.
    
- **View alert details**You can click an alert to display a flyout page with details about the alert. The detailed information depends on the corresponding alert policy, but it typically includes the following: name of the actual operation that triggered the alert (such as a cmdlet), a description of the activity that triggered the alert, the user (or list of users) who triggered the alert, and the name (and link to ) of the corresponding alert policy.
    
  - The name of the actual operation that triggered the alert, such as a cmdlet or an audit log operation.
    
  - A description of the activity that triggered the alert.
    
  - The user who triggered the alert; this is included only for alert policies that are set up to track a single user or a single activity.
    
  - The number of times the activity tracked by the alert was performed. Note that this number might not match that actual number of related alerts listed on the View alerts page because additional alerts might have been triggered.
    
  - A link to an activity list that includes an item for each activity that was performed that triggered the alert. Each entry in this list identifies when the activity occurred, the name of actual operation, (such as "FileDeleted") and the user who performed the activity, the object (such as a file, an eDiscovery case, or a mailbox) that the activity was performed on, and the IP address of the user's computer. For malware related alerts, this links to a message list.
    
  - The name (and link to ) of the corresponding alert policy.
    
- **Suppress email notifications**You can turn off (or suppress) email notifications from the flyout page for an alert. When you suppress email notifications, Office 365 won't send notifications when activities or events that match the conditions of the alert policy. However, alerts will continue to be trigger when activities performed by users match the conditions of the alert policy. You can also turn off email notifications by editing the alert policy.
    
- **Resolve alerts**You can mark an alert as resolved on the flyout page for an alert (which sets the status of the alert to **Resolved**). Unless you change the filter, resolved alerts aren't displayed on the **View alerts** page. 
    
[Return to top](alert-policies.md#top)
  

