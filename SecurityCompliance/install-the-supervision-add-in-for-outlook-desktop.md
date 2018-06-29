---
title: "Install the Supervision add-in for Outlook desktop"
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: "Install the Office 365 Supervision add-in for the desktop version of Outlook"
---

# Install the Supervision add-in for Outlook desktop

To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.
  
> [!NOTE]
> Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## Step 1: Copy the address for the supervision mailbox

To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup. 
  
> [!NOTE]
> If someone else created the policy, you'll need to get this address from them to install the add-in. 
  
 **To find the supervision mailbox address**
  
1. Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization. 
    
2. Go to **Data governance** \> **Supervision**.
    
3. Click the supervision policy that's gathering the communications you want to review.
    
4. In the policy details flyout, under ** Supervision mailbox **, copy the address. 
    
    ![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## Step 2: Configure the supervision mailbox for Outlook desktop access

Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.
  
1. Connect to Exchange Online PowerShell. [How do I do this?](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)
    
2. Run the following commands.
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    Where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in the next step. 
    
3. Wait at least an hour before moving on to Step 3 below.
    
## Step 3: Create an Outlook profile to connect to the supervision mailbox

For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox. 
  
> [!NOTE]
> To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed. 
  
1. Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**. 
    
    > [!NOTE]
    > Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. Open the **Mail** app. 
    
3. In **Mail Setup - Outlook**, click **Show Profiles**.
    
    ![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).
    
    ![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. In **Connect Outlook to Office 365**, click **Connect to a different account**.
    
    ![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.
    
7. In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously. 
    
    ![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. When prompted, enter your Office 365 credentials.
    
9. If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook. 
    

