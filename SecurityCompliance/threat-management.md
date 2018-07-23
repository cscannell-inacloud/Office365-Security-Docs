---
title: "Threat management in the Office 365 Security &amp; Compliance Center"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98

description: "Use Threat management to help control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain."
---

# Threat management in the Office 365 Security &amp; Compliance Center

Use Threat management to help control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.
  
## How to view and use Threat management in the Security &amp; Compliance Center

In Office 365 use the Security &amp; Compliance Center to manage threats in your organization.
  
 **To go directly to the Security &amp; Compliance Center:**
  
1. Go to [https://protection.office.com](https://protection.office.com).
    
2. Sign in to Office 365 using your work or school account.
    
3. In the left pane, select **Threat management**.
    
    ![Office 365 Security &amp; Compliance Center Threat management menu](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **To go to the Security &amp; Compliance Center using the Office 365 app launcher:**
  
1. Sign in to Office 365 using your work or school account.
    
2. Select the app launcher ![The app launcher icon in Office 365](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) in the upper left corner, and then select the **Security &amp; Compliance** tile. 
    
3. In the left pane, select **Threat management**.
    
## About Threat management in Office 365

These options are available under **Threat management** in the Security &amp; Compliance Center. 
  
We're still rolling out Threat management for the Security &amp; Compliance Center, so you might not see all of these yet, or you might see more than the options listed here. During the rollout, some of these, for example Anti-malware, Dkim, and others, will continue to be available through the Exchange Admin Center (EAC).
  
|**Tool**|**Description**|
|:-----|:-----|
|**Dashboard, Threat explorer, and Incidents** <br/> |Once enabled, these panes allow you to manage Office 365 Analytics and threat intelligence. For more information, see [Office 365 Threat Intelligence overview](office-365-ti.md).  <br/> |
|**Mail filtering** <br/> |Fine-tune and monitor settings that help prevent spam in Office 365. Create allow and block lists, determine who is spoofing your domain and why, and configure and view spam filter policies. For more information, see [Office 365 email anti-spam protection](anti-spam-protection.md).  <br/> You can also set up a policy to check that your users aren't sending spam. This can happen, for example, if a user's computer gets infected by malware that is programmed to send email messages. To learn how you can prevent outbound spam, see [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx).  <br/> > [!TIP]> If you are currently experiencing an issue with spam, you can use the [Spam and malware troubleshooter](https://configure.office.com/Scenario.aspx?sid=73).           |
|**Anti-malware** <br/> |Protects against viruses and spyware traveling to or from your organization in Office 365. Viruses are malicious software programs that, when executed, replicate themselves and modify other programs and data on the computer. Viruses spread throughout your computer looking for programs to infect and are also shared from one computer to another, often through email. Spyware gathers your personal information, such as sign-in information, and sends it back to its author. To get started configuring anti-malware policies, see [Configure anti-malware policies](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx).  <br/> > [!TIP]> If you are currently experiencing an issue with malware, you can use the [Spam and malware troubleshooter](https://configure.office.com/Scenario.aspx?sid=73).           |
|**Dkim** <br/> |Intended for more advanced Office 365 administrators, but available to all Office 365 customers, DomainKeys Identified Mail (DKIM) helps ensure that other email systems trust messages that you send from Office 365. DKIM does this by adding a unique digital signature to email messages that you send from your organization. Email systems that receive email from you can use this digital signature to help determine if the email is legitimate.  <br/> Don't worry if the details of how this works seem complicated, because the default that is set up for you in Office 365 should work for most organizations. If you do not set up DKIM yourself, Office 365 uses its default policy and keys that it creates in order to enable DKIM for your domain. Also, if you disable DKIM signing, after a period of time, Office 365 automatically enables the Office 365 default policy for your domain.  <br/> If you want, you can view this page in the Security &amp; Compliance Center and see whether or not DKIM signatures are currently enabled for your domain and you can view the last time the encryption keys used by Office 365 were rotated. You can also manually rotate the keys yourself.  <br/> > [!IMPORTANT]> DKIM is only one email authentication technique used by Office 365. To be most effective, DKIM is used along with other supported techniques such as Sender Policy Framework (SPF) and Domain-based Message Authentication, Reporting, and Conformance (DMARC). Together, these domain-based authentication technologies help prevent spam and unwanted spoofing. > Before making changes to DKIM using the Security &amp; Compliance Center, become comfortable with the technology and how it works. To get started, see [Beyond the basics: More ways to prevent spam in Office 365](anti-spam-protection.md#BeyondBasics).           |
|**Safe Attachments** <br/> |[Safe Attachments](atp-safe-attachments.md) is part of Advanced Threat Protection. When enabled, email attachments are opened in a special, isolated environment that is separate from Office 365 before they are sent to recipient inboxes. Safe Attachments is designed to help detect malicious attachments even before anti-virus signatures are available. To learn more, see [Safe Attachments in Office 365](atp-safe-attachments.md).  <br/> |
|**Safe Links** <br/> |[Safe Links](atp-safe-links.md) is part of Advanced Threat Protection. Safe Links help prevent users from following URLs in email or in Office documents that point to web sites that are recognized as malicious. To learn more, see [Safe Links in Office 365](atp-safe-links.md).  <br/> |
|**Quarantine** <br/> |Set up [Quarantine](http://go.microsoft.com/fwlink/p/?LinkID=809005) for incoming email messages in Office 365 where messages that have been filtered as spam, bulk, phishing, and malware mail can be kept for later review. Both users and admins can work with quarantined messages. Users can work with just their own filtered messages in quarantine. Admins can search for and manage quarantined messages for all users.  <br/> |
|**Advanced threats** <br/> |View the [threat protection status report](https://support.office.com/en-US/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats) to see information about the malicious content found and blocked by Exchange Online Protection and Advanced Threat Protection.  <br/> |
   

