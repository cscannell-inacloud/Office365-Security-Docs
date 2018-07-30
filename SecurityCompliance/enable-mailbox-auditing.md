---
title: "Enable mailbox auditing in Office 365"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: 
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: "In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. After you enable mailbox audit logging for a mailbox, you can search the Office 365 audit log for activities performed on the mailbox."
---

# Enable mailbox auditing in Office 365
  
In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.

## Before you begin
  
- You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.
    
- After you enable mailbox audit logging for a mailbox, access to the mailbox and certain admin and delegate actions are logged by default. To log actions taken by the mailbox owner, you must specify which owner actions to audit. See the "More info" section to see a list of actions that are logged after mailbox audit logging is enabled, and which actions are available for each type of user logon.
    
- You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.
    
- An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.
  
## Step 1: Connect to Exchange Online PowerShell

1. On your local computer, open Windows PowerShell and run the following command.
   
    ```
    $UserCredential = Get-Credential
    ```

2. In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.
    
3. Run the following command:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Run the following command.

    ```
    Import-PSSession $Session
    ```
   
4. To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.
    
    ```
    Get-Mailbox
    ```
  
For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
## Step 2: Enable mailbox audit logging

After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.
  
This example enables mailbox audit logging for Pilar Pinilla's mailbox.
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

This example enables mailbox audit logging for all user mailboxes in your organization.
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## Step 3: Specify owner actions to audit

When you enable auditing for a mailbox, only one action ( **UpdateFolderPermissions** ) performed by the mailbox owner is audited by default. You have to specify other owner actions to audit. See the table in the "Mailbox actions" section for a list and description of owner actions that can be audited. 
  
This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox. 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action. 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes. 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## How do you know this worked?

To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox. 
  
This example retrieves the auditing settings for Pilar Pinilla.

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
This example retrieves the auditing settings for all user mailboxes in your organization.

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled. 
    
## Mailbox auditing actions
  
The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox. As previously stated, the only owner action audited by default when you turn on mailbox auditing is UpdateFolderPermissions. To log other actions taken by the mailbox owner, you must specify additional owner actions to audit. To do this, see [Step 3](#step-3-specify-owner-actions-to-audit) in this topic. 
  
|**Action**|**Description**|**Admin**|**Delegate\*\*\***|**Owner**|
|:-----|:-----|:-----|:-----|:-----|
|**Copy** <br/> |A message was copied to another folder.  <br/> |Yes  <br/> |No  <br/> |No  <br/> |
|**Create** <br/> |An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes  <br/> |
|**FolderBind** <br/> |A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.  <br/> |Yes\*  <br/> |Yes\*\*  <br/> |No  <br/> |
|**HardDelete** <br/> |A message was purged from the Recoverable Items folder.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes  <br/> |
|**MailboxLogin** <br/> |The user signed in to their mailbox.  <br/> |No  <br/> |No  <br/> |Yes  <br/> |
|**MessageBind** <br/> |A message was viewed in the preview pane or opened.  <br/> |Yes  <br/> |No  <br/> |No  <br/> |
|**Move** <br/> |A message was moved to another folder.  <br/> |Yes\*  <br/> |Yes  <br/> |Yes  <br/> |
|**MoveToDeletedItems** <br/> |A message was deleted and moved to the Deleted Items folder.  <br/> |Yes\*  <br/> |Yes  <br/> |Yes  <br/> |
|**SendAs** <br/> |A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.  <br/> |Yes\*  <br/> |Yes\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.  <br/> |Yes\*  <br/> |Yes  <br/> |No  <br/> |
|**SoftDelete** <br/> |A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes  <br/> |
|**Update** <br/> |A message or its properties was changed.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes  <br/> |
|**UpdateCalendarDelegation** <br/> |A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.  <br/> |Yes\*  <br/> |No  <br/> |Yes\*  <br/> |
|**UpdateFolderPermissions** <br/> |A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes\*  <br/> |
|**UpdateInboxRules** <br/> |An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.  <br/> |Yes\*  <br/> |Yes\*  <br/> |Yes\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup> Audited by default if auditing is enabled for a mailbox. > <sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours. > <sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user. 
  
If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the 90-day age limit for audit log entries is reached.
  
## [More info](#tab/)
  
- Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.
    
    ![You can search the Office 365 audit log for mailbox audit actions by selecting "Exchange mailbox activities" in Activities drop-down list](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.
    
    |**Activity in the audit log**|**Mailbox auditing action**|
    |:-----|:-----|
    |Created mailbox item  <br/> |Create  <br/> |
    |Copied messages to another folder  <br/> |Copy  <br/> |
    |User signed in to mailbox  <br/> |MailboxLogin  <br/> |
    |Sent message using Send On Behalf permissions  <br/> |SendOnBehalf  <br/> |
    |Purged messages from the mailbox  <br/> |HardDelete  <br/> |
    |Moved messages to Deleted Items folder  <br/> |MoveToDeletedItems  <br/> |
    |Moved messages to another folder  <br/> |Move  <br/> |
    |Sent message using Send As permissions  <br/> |SendAs  <br/> |
    |Updated message  <br/> |Update  <br/> |
    |Deleted messages from Deleted Items folder  <br/> |SoftDelete  <br/> |
    |Added permissions to folder  <br/> |UpdateFolderPermissions  <br/> |
    |Modified permissions of folder  <br/> |UpdateFolderPermissions  <br/> |
    |Removed permissions from folder  <br/> |UpdateFolderPermissions  <br/> |
    |Added or removed user with delegate access to calendar folder  <br/> |UpdateCalendarDelegation  <br/> |
   
    Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission. 
    
    For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).
    
- Mailboxes are considered to be accessed by an administrator only in the following scenarios:
    
  - In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox. 
    
- When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).
    
- To disable mailbox audit logging, run the following command:

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type. 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).
