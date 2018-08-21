---
title: "Attack Simulator in Office 365"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: "Learn about three different kinds of cyber attacks you can run using Attack Simulator."
---

# Attack Simulator in Office 365

With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.
  
## The Attacks

At preview release we offer three kinds of attack simulations that you can run:
  
- [Display name spear-phishing attack](attack-simulator.md#spearphish)
    
- [Password-spray attack](attack-simulator.md#passwordspray)
    
- [Brute-force password attack](attack-simulator.md#bruteforce)
    
For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.
  
> [!NOTE]
> Support for Conditional Access is coming soon. 
  
To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.
  
## Before you begin...

Make sure that you and your organization meet the following requirements for Attack Simulator:
  
- Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)
    
- Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)
    
- You are an Office 365 global administrator
    
- Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## Display name spear-phishing attack

Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.
  
This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.
  
### To simulate a spear-phishing attack

![Compose Email Body](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML: 
  
1. In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.
    
2. Specify a meaningful campaign name for the attack or select a template.
    
    ![Phishing Start Page](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.
    
    ![Recipient Selection](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configure the Phishing email details.
    
    ![Configure email details](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.
    
1. Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client. 
    
2. Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. 
    
    > [!IMPORTANT]
    > You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension. 
  
3. Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.
    
4. Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.
    
5. Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client. 
    
5. Compose the **Email body** that the target will receive. 
  
 **${username}** inserts the targets name into the Email body 
  
 **${loginserverurl}** inserts the URL we want target users to click 
    
6. Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes. 
    
## Password-spray attack

A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.
  
This attack focuses on letting you specify a common password against a large target base of users.
  
### To simulate a password-spray attack

1. In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.
    
2. Specify a meaningful campaign name for the attack.
    
3. Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.
    
4. Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.
    
5. Choose **Finish** to launch the attack. 
    
## Brute-force password attack

A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.
  
### To simulate a brute-force password attack

1. In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.
    
2. Specify a meaningful campaign name for the attack.
    
3. Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.
    
4. Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.
    
5. Choose **Finish** to launch the attack. 
    
## Related topics

[Office 365 Threat Intelligence](office-365-ti.md)
  

