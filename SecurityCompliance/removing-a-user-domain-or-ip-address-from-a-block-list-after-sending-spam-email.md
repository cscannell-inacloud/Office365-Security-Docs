---
title: "Removing a user, domain, or IP address from a block list after sending spam email"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- 'ms.exch.eac.ActionCenter'
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5

description: "If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages."
---

# Removing a user, domain, or IP address from a block list after sending spam email

If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. 
  
When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.
  
Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).
  
You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.
  
## Unblock a blocked Office 365 email account

You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC. 
  
> [!NOTE]
> You won't see the action center unless you're in the EAC for Exchange Online. 
  
1. In the EAC, navigate to **protection** \> **action center**.
    
    ![Navigate to the action center in the Exchange admin center](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. Select the **Search** icon, and then enter the SMTP address of the blocked user. 
    
    ![Search for a blocked user in the action center](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. Click **Unblock Account** in the description pane. 
    
    ![Unblock a user in the action center](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. Click **Yes** to confirm the change. 
    
> [!NOTE]
> There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user. 
  
## Third-party block lists

|**List Name**|**Delisting Portal**|**For more information**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[ URIBL website ](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[Introducing SURBL URI reputation data](http://www.surbl.org/) <br/> |
|Spamhaus  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[Understanding DNSBL Filtering](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[invaluement anti-spam list](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank FAQ](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> Exchange Online Protection also uses third-party block lists for spam filtering. 
   
## For more information

[Configure the outbound spam policy](configure-the-outbound-spam-policy.md)
  
[High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md)

[Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

