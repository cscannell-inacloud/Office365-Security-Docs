---
title: "Outbound spam controls in Office 365"
ms.author: deniseb
author: deniseb-msft
manager: laurawi
ms.date: 09/12/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: "If your organization sends a lot of bulk mail that's marked as spam, you could get blocked from sending email with Office 365. Read this article to learn more about why this happens and what you can do about it."
---

# Outbound spam controls in Office 365

*This article is based on a blog authored by Terry Zink, a program manager for Microsoft.*

As a Program Manager of Antispam in Office 365, one of the questions I am frequently asked is “How many messages outbound are we permitted to send per minute? Per hour? Per day?”

When I use the term “Office 365” I mean both our existing Forefront Online Protection for Exchange (FOPE) service, and our newer Exchange Online Protection (EOP) service. The following description applies to both of these services.

We take managing outbound spam seriously because ours is a shared service; there are many customers behind a shared pool of resources. If one customer sends outbound spam, it can degrade the outbound IP reputation of the service. This affect the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses. The actions of one directly affect the other.

FOPE and EOP do the following to control outbound spam: 

1. **Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the Higher Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.<br/>Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal. 

2. **Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted as well as troubleshooting steps to disable the spamming account that caused us to get listed in the first place. 

3. **Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds a limit, the account is blocked from sending spam.<br/>A single message marked as spam may be a misclassification by the spam engine. This is why we send it through the High Risk Pool. However, a large number of messages in a smaller time frame is indicative of a problem and when that occurs, we block the account from sending any more email. 
There are different thresholds that exist for individual email accounts as well as in aggregate for the entire customer. 

4. **Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam.<br/>The reason this limit exists is because sometimes a compromised account sends zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.<br/>There are different thresholds that exist for individual email accounts as well as in aggregate for the entire customer. 
**For both #3 and #4, we do not advertise the exact limits**. This is for two reasons: 
    a. **To prevent spammers from gaming the system**. We do not want spammers to send (limit – 1) messages through the system. If they knew the limits, they would do this. We know they would do this because we have seen spammers figure it out using trial-and-error. 
    b. **To ensure that we can change the limits when we need to**. If we were to advertise the exact limits, customers would expect that these limits were always in place. Because outbound spam requires agility to react quickly, there are situations where we might decide to change the limits in a short period of time to stop spam. If customers knew the exact limits, they may expect to be warned in advance. We cannot do this because we must move quickly to contain possible damage. Therefore, we have avoided setting expectations.

For #4, the limits are high enough such that an average business user will never hit them. There is only so much email a person can physically type in a day. However, the limits are low enough that it contains most of the damage a spammer can do; it ends their spam campaign quicker than they intended. 

5. **Recommended workarounds for customers who want to send outbound bulk email through FOPE or EOP**. It is difficult to strike a balance between customers who want to send much bulk email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices.<br/>On the one hand, it is inconvenient for some customers to not being able to send as much email as they want through the service. On the other hand, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. In the former case, it is a single customer that is affected  but in the latter, it is multiple customers.<br/>Using FOPE or EOP to send bulk email is not a recommended or supported use of the service. It is permitted on a “best-effort” basis. It may or may not work. For customers who do want to send bulk email, we recommend the following: 
    a. **Send the bulk email through its own on-premise mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email. 
    b. **Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it. 

The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster here: http://www.maawg.org/about/roster 
Several bulk email providers are on the list and are known to be responsible Internet citizens. 

6. **Notifications when an account is sending spam, or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk Pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network, or if the spam filter is mistakenly marking their email as spam. 
In addition, whenever #3 or #4 is executed above using an automated process, an email alert is sent to the Customer Support team who will contact the customer, informing them that we have shut down the account. However, an administrator can instead opt for an email notification directly that says that email account X has been blocked for sending outbound spam.<br/>To find these settings in the EOP service, click on Admin drop down arrow –> protection –> outbound spam –> Edit –> outbound spam preferences:<br/>![outbound spam preferences](media/outboundspampreferences.png)<br/> 
 
7. **Manually reviewing spam complaints from users at 3rd party email providers**. The above #3 and #4 account shut downs are automated, however, we also have manual processes.<br/>Many 3rd party email services like Hotmail, Yahoo and AOL provide a Feedback Loop wherein if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review.<br/>If any one of our spam analysts reviews these messages and finds a malicious spam message (phishing, lottery, pharmaceutical spam, malware), they will take steps to disable the account.<br/>The notification process is slightly different than #6 and we are working to make it uniform for both automated and manual blocking.

The above is a summary of the most common controls we implement to reduce outbound spam.
  
## For more information

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Anti-spoofing protection in Office 365](anti-spoofing-protection.md)

[Spam confidence levels](spam-confidence-levels.md)
