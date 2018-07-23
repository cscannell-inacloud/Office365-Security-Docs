---
title: "Create a Litigation Hold in Office 365"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44

---

# Create a Litigation Hold in Office 365

You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a retention duration (also called a time-based hold) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. 
  
Here's what happens when you create a Litigation Hold.
  
- Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.
    
- Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.
    
- The storage quota for the Recoverable Items folder is increased from 30 GB to 100 GB.
    
- Items in the user's primary and the archive mailboxes are retained
    
## Before you begin

- To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.
    
- In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.
    
## From EXO overview topic

- **Indefinite hold** The indefinite hold scenario is similar to Litigation Hold. It's intended to preserve mailbox items so you can meet eDiscovery requirements. During the period of litigation or investigation, items are never deleted from the mailbox. The duration isn't known in advance, so no end date is configured. 
    
- **Time-based hold** You can specify a duration of time for which to hold items. The duration is calculated from the date a mailbox item is received or created. 
    
    If your organization requires that all mailbox items be preserved for a specific period, for example 7 years, you can create a time-based hold. You can specify a retention period for items on hold. Items on hold are aged based on their date received. For example, consider a mailbox that's placed on a time-based In-Place Hold and has a retention period set to 365 days. If an item in that mailbox is purged by the user300 days after it was received, it's held for an additional 65 days before being permanently deleted from the mailbox. 
    
## More info

- If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.
    
  - When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.
    
  - The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold. 
    
- 
    
- 
    

