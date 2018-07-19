---
title: "Office 365 Mailbox Migrations"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "Summary: A brief summary of the cmdlets used for Office 365 mailbox migrations."
---

# Office 365 Mailbox Migrations
With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an Exchange Online organization or move Exchange Online mailboxes to an Exchange on-premises organization. Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations. Customers can review statistics and other information about mailbox migrations using the following cmdlets:

- [Get-MoveRequestStatistics](https://technet.microsoft.com/en-us/library/ee332315%28v=exchg.160%29.aspx) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.
- [Get-Mailbox](https://technet.microsoft.com/en-us/library/bb123685%28v=exchg.160%29.aspx) - Provides a summary list of mailbox objects and attributes in the organization.
- [Get-Recipient](https://technet.microsoft.com/en-us/library/aa996921%28v=exchg.160%29.aspx) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.
- [Get-MoveRequest](https://technet.microsoft.com/en-us/library/dd335227%28v=exchg.160%29.aspx) - Provides a detailed status of an ongoing mailbox migration.
- [Get-MigrationUser](https://technet.microsoft.com/en-us/library/jj218702%28v=exchg.160%29.aspx) - Provides information about the mailbox move and migration users.
- [Get-MigrationBatch](https://technet.microsoft.com/en-us/library/jj219164%28v=exchg.160%29.aspx) - Provides information on the status of current migration batch.
- [Get-MigrationUserStatistics](https://technet.microsoft.com/en-us/library/jj218695%28v=exchg.160%29.aspx) - Provides detailed information about the migration status for a specific user.
- [Get-MailboxStatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.

For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://technet.microsoft.com/en-us/library/dn641236(v=exchg.160).aspx).
