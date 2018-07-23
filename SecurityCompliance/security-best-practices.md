---
title: "Security best practices for Office 365"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: "Minimize the potential of a data breach or a compromised account by following these recommended best practices."
---

# Security best practices for Office 365

Minimize the potential of a data breach or a compromised account by following these recommended best practices.
  
This article contains a quick list of best practices. For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md). In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant. You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.
  
## Use Office 365 Secure Score

Secure Score is a security analytics tool that recommends what you can do to further reduce risk. Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft. You'll get a score based on how aligned you are with best security practices. For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).
  
Want to try out Secure Score?
  
Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).
  
Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).
  
## Use multi-factor authentication (MFA)

MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised. Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied. A compromised or stolen password is not enough.
  
- [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## Use Office 365 Cloud App Security

Set up policies based on your business needs to track anomalous activity and act on it. Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address. For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away. If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.
  
- [Overview of O365 Cloud App Security](office-365-cas-overview.md)
    
- [Turn on Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
## Secure mail flow

Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.
  
- Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization. 
    
- Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).
    
- [Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).
    
- Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users. 
    
- If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:
    
  - [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).
    
  - [Use DKIM to validate outbound email sent from your custom domain in Office 365](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).
    
  - [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
## Enable mailbox audit logging

Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default. You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell. For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator. For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).
  
For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).
  
## Configure Data Loss Prevention (DLP)

DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data. DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow. For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).
  
## Use Customer Lockbox

As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session. In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request. If you approve it, the engineer can access the data. Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked. Customer Lockbox is included in the Office 365 Enterprise 5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan. For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).
  
## Try it yourself
<a name="SecureScore"> </a>

See these security features working in an Office 365 trial subscription prior to adopting them in production.
  
- [Create an Office 365 trial subscription](https://technet.microsoft.com/library/mt736406.aspx)
    
- [Configure and test MFA for a user account](https://technet.microsoft.com/library/mt492459.aspx)
    
- [Configure and test Office 365 Cloud App Security to notify you of global admin activity](https://technet.microsoft.com/library/mt757250.aspx)
    
- [Configure and test ATP for suspicious email](https://technet.microsoft.com/library/mt490479.aspx)
    
- Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps 
    

