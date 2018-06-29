---
title: "Office 365 ATP Safe Attachments"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: "The Safe Attachments feature provides time-of-click verification of email attachments. Use Safe Attachments to protect your organization from malicious files people send or receive in email."
---

# Office 365 ATP Safe Attachments

ATP Safe Attachments (along with [ATP Safe Links](atp-safe-links.md)) is part of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). The ATP Safe Attachments feature checks to see if email attachments are malicious, and then takes action to protect your organization. The ATP Safe Attachments feature protects your organization according to [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) that are set by your Office 365 global or security administrators. 
  
Beginning in late March 2018 and over the next several weeks, ATP protection is being extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams. To learn more, see [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).
  
> [!NOTE]
> ATP Safe Attachments features are only available in Advanced Threat Protection. Office 365 ATP is included in subscriptions, such as Office 365 Enterprise E5 and Office 365 Education A5, and, as of April 30, 2018, also [Microsoft 365 Business security features](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. (As a global admin, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx). 
  
 **In this article**: 
  
- [How it works](atp-safe-attachments.md#howitworks)
    
- [How to get ATP Safe Attachments](atp-safe-attachments.md#howtobuy)
    
- [How to know if ATP Safe Attachments protection is in place](atp-safe-attachments.md#howtosee)
    
## How it works
<a name="howitworks"> </a>

The ATP Safe Attachments feature checks email attachments for people in your organization. When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies. Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.
  
Here are two examples of ATP Safe Attachments at work.
  
- **Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment. It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal the Lee's user credentials. In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago. With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it. If the attachment is determined to be malicious, it will be removed automatically. If the attachment is safe, it will open as expected when Lee clicks on it. 
    
- **Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online. Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious. Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it. A few days later, Chris goes to open the document. Although Chris can see the file is there, Chris cannot open or share it, which prevents Chris's computer and others from the malicious file. 
    
ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain. To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**. 
  
## How to get ATP Safe Attachments
<a name="howtobuy"> </a>

The ATP Safe Attachments feature is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).
  
The ATP Safe Attachments feature applies when:
  
- ATP Safe Attachments policies are set up. (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md).)
    
- Users have signed into Office 365 using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
## How to know if ATP Safe Attachments protection is in place
<a name="howtosee"> </a>

 **[ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) must be defined in order for ATP Safe Attachments protection to be in place **. 
  
One good way to see how the service is working is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).
  
In addition, the following table describes some example scenarios. In all of these cases, we assume the organization has Office 365 Enterprise E5, which includes Advanced Threat Protection.
  
|**Example scenario**|**Does ATP Safe Attachments protection apply in this case?**|
|:-----|:-----|
|Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP Safe Attachments yet.  <br/> |No. Although the feature is available, at least one ATP Safe Attachments policy must be defined in order for ATP Safe Attachments protection to be in place.  <br/> |
|Lee is an employee in the sales department at Contoso. Lee's organization has an ATP Safe Attachments policy in place that applies to finance employees only.  <br/> |No. In this case, finance employees would have ATP Safe Attachments protection, but other employees, including the sales department, would not until policies that include those groups are defined.  <br/> |
|Yesterday, an Office 365 administrator at Jean's organization set up an ATP Safe Attachments policy that applies to all employees. Earlier today, Jean received an email message that includes an attachment.  <br/> |Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP Safe Attachments policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.  <br/> |
|Chris's organization has Office 365 Enterprise E5 with ATP Safe Attachments policies in place for everyone in the organization. Chris receives an email that has an attachment, and forwards the message to others who are outside the organization.  <br/> |ATP Safe Attachments protection is in place for messages that Chris receives. If the recipients' organizations also have ATP Safe Attachments policies in place, then the message that Chris forwards would be subject to those policies when the forwarded message arrives.  <br/> |
|Jamie's organization has ATP Safe Attachments policies in place, and [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) has been turned on. Jamie assumes that every file in SharePoint Online has been scanned and is safe to open or download.  <br/> |ATP Safe Attachments protection is in place according to the policies that are defined; however, this does not mean that every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams is scanned. (To learn more, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).)  <br/> |
   
## Submitting files for malware analysis
<a name="analysis"> </a>

If you receive a file that you want to ask Microsoft to analyze, visit [Submit a file for malware analysis](https://aka.ms/wdsi/submit).
  
## Related topics
<a name="analysis"> </a>

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)
  
[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)
  
[ATP Safe Links in Office 365](atp-safe-links.md)
  
[ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)
  
[View the reports for Advanced Threat Protection](view-reports-for-atp.md)
  

