---
title: "ATP anti-phishing capabilities in Office 365"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: "ATP anti-phishing is offered as part of Office 365 Advanced Threat Protection. ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators."
---

# ATP anti-phishing capabilities in Office 365

ATP anti-phishing is offered as part of [Office 365 Advanced Threat Protection](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.
  
To learn more, see [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).
  
> [!NOTE]
> ATP anti-phishing is only available in Advanced Threat Protection, available with Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global admin, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053). 
  
 **In this article:**
  
- [How ATP anti-phishing works](atp-anti-phishing.md#Howantiphishworks)
    
- [How to get ATP anti-phishing](atp-anti-phishing.md#Howtogetantiphish)
    
- [How to know if ATP anti-phishing is in place](atp-anti-phishing.md#IsantiphishOn)
    
## How ATP anti-phishing works
<a name="Howantiphishworks"> </a>

ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.
  
ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.
  
ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).
  
## How to get ATP anti-phishing
<a name="Howtogetantiphish"> </a>

ATP anti-phishing is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. Advanced Threat Protection can also be purchased as an add-on to Office 365 Enterprise E1 or Office 365 Enterprise E3. For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053).
  
ATP anti-phishing applies when an anti-phishing policy, such as an impersonation-based policy are set up. (See [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).)
  
## How to know if ATP anti-phishing is in place
<a name="IsantiphishOn"> </a>

ATP anti-phishing policies must be defined in order for protection to be active. For ATP anti-phishing machine learning models to be active for a user, that user must be part of a defined safe attachment, safe links, or anti-phishing policy. The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.
  
|**Example scenario**|**Does ATP anti-phishing apply in this case?**|
|:-----|:-----|
|Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.  <br/> |No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.  <br/> |
|Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.  <br/> |No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.  <br/> |
|Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.  <br/> |Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.  <br/> |
   
## Related topics
<a name="IsantiphishOn"> </a>

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Anti-phishing protection in Office 365](anti-phishing-protection.md)
  
[Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md)
  
[ATP safe links in Office 365](atp-safe-links.md)
  
[Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md)
  
[ATP safe attachments in Office 365](atp-safe-attachments.md)
  
[Set up ATP safe attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)
  
[View the reports for Advanced Threat Protection](view-reports-for-atp.md)
  

