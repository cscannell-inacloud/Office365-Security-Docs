---
title: "Recover an inactive mailbox in Office 365"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: 
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: "If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of a departed employee, you can recover the contents of the inactive mailbox in Office 365. When you recover an inactive mailbox, it's converted to a new mailbox that contains the contents of the inactive mailbox. "
---

# Recover an inactive mailbox in Office 365

An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user: 
  
- **Recover an inactive mailbox** If the former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the former employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new, active mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. The procedures in this topic describe this method. 
    
- **Restore an inactive mailbox** If another employee takes on the job responsibilities of the former employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. For the procedures for this method, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).
    
See the [More information](recover-an-inactive-mailbox.md#moreinfo) section for more details about the differences between recovering and restoring an inactive mailbox, and for a description of what happens when an inactive mailbox is recovered.
  
> [!NOTE]
> We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold. 
  
## Before you begin

- You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Run the following command to get identity information for the inactive mailboxes in your organization. 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Use the information returned by this command to recover a specific inactive mailbox.
    
- For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    

  
## Recover an inactive mailbox

Use the **New-Mailbox** cmdlet with the  *InactiveMailbox*  parameter to recover an inactive mailbox. 
  
1. Create a variable that contains the properties of the inactive mailbox. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. This example uses the properties obtained in the previous command and recovers the inactive mailbox to an active mailbox for the user Ann Beebe. Be sure that the values specified for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters are unique within your organization. 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    The primary SMTP address for the recovered inactive mailbox will have the same value as the one specified by the  *MicrosoftOnlineServicesID*  parameter. 
    
After you recover an inactive mailbox, a new Office 365 user account is also created. You have to activate this user account by assigning a license. To assign a license in the Office 365 admin center, see [Assign or unassign licenses for Office 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  

  
## Recover an inactive mailbox for a federated user in an Exchange hybrid deployment
<a name="recoverhybrid"> </a>

You can also recover in inactive cloud-based mailbox of an on-premises user (called a federated user) in an Exchange hybrid deployment. First, you have to use the **New-Mailbox -InactiveMailbox** command in Exchange Online PowerShell to recover the inactive mailbox and create a cloud-based active mailbox in a non-federated domain. Then you have to associate (or  *hard match*  ) the on-premises user account with the recovered cloud-based mailbox. This is accomplished by using the getting the value of the **ImmutableId** property of the on-premises user account that's been synchronized to Azure Active Directory, and setting it as the value o f the **ImmutableId** for the cloud-based user account that is created when you recover the inactive mailbox. The final step is to enable the cloud-based mailbox (called a  *remote mailbox*  ) in the on-premises Exchange organization. 
  
This procedure assumes that the user whose inactive mailbox you want to recover is an on-premises user whose account is created and managed in Active Directory in the on-premises organization, and that has been synchronized to Azure Active Directory in Office 365. After completing the following procedure, the inactive mailbox will become an active cloud-based mailbox for the on-premises user. 
  
Here's the high-level process:
  
1. In Exchange Online PowerShell, run the following command to create a variable that contains the properties of the inactive mailbox that you want to recover. Use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox because these properties are unique for each mailbox in your organization. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

2. In Exchange Online PowerShell, run the following command to recover the inactive mailbox and make it an active cloud-based mailbox. The values for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters refer to the on-premises user whose inactive mailbox you are recovering. 
    
    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name <name> -FirstName <first name> -LastName <last name> -DisplayName <display name> -MicrosoftOnlineServicesID <SMTP address for cloud organization> -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```
   
    For the value of the  *Name*  parameter, use the **SamAccountName** or **Alias** of the on-premises user. 
    
    For the value of the  *MicrosoftOnlineServicesID*  parameter in the previous command, be sure to use an email address that uses the domain name for your cloud organization (which is a non-federated domain), such as `contoso.onmicrosoft.com`. Don't use a the domain name of your on-premises organization, which is a federated domain. 
    
3. Assign a license to the new Office 365 user account that's created after you run the command in the previous step. See [Assign or unassign licenses for Office 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
    
4. [Connect to Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell). 
    
5. Run the following command to get the **ImmutableId** for the on-premises user account that's been synchronized to Azure Active Directory. 

    ```
    Get-MsolUser -UserPrincipalName <UPN for the on-premises user account> | FL  ImmutableId 
    ```

    Write down the **ImmutableId** or copy it to a text file. 
    
6. Run the following commands to permanently delete the on-premises user from Azure Active Directory. This step is required so that you can use the ImmutableId from the on-premises user account to set on the cloud-base account (that you created in step 2). Otherwise, you'll received an error when you try to set the ImmutableId on the cloud-based account. 

    ```
    Remove-MsolUser -UserPrincipalName <UPN for the on-premises user account>
    ```

    ```
    Get-MsolUser -UserPrincipalName <UPN for the on-premises user account> -RemoveFromRecyleBin
    ```
   
7. Run the following command to set the **ImmutableId** (from the on-premises user account) on the cloud-based user account that was created for the on-premises user in step 2. This will create a match between the on-premises user account and the cloud-based mailbox. 
    
    ```
    Set-MsolUser -UserPrincipalName <email address for cloud-based account for on-premises user> -ImmutableId <immutableid>  
    ```

    For the  *UserPrincipalName*  parameter, use the same value as the one you used for the  *MicrosoftOnlineServicesID*  parameter in step 2. For the  *ImmutableId*  parameter, use the value that you obtained in step 5. 

    Note that the next time the on-premises Active Directory is synchronized with Azure Active Directory, the on-premises user account will be hard-matched with the cloud-based mailbox, and there will be a single user account in Azure Active Directory for the on-premises user.
    
8. In the Exchange Management Shell in the on-premises Exchange organization, run the following command to enable the remote mailbox in your on-premises organization. A remote mailbox is a cloud-based mailbox for an on-premises user. 

    ```
    Enable-RemoteMailbox  <identity of on-premises user> -RemoteRoutingAddress <SMTP address for cloud-based mailbox> 
    ```

     For the value of the  *RemoteRoutingAddress*  parameter, use one of the values that is return when you run the following command in Office 365 PowerShell: 
    
    ```
    Get-MsolUser -UserPrincipalName <UPN for the on-premises user account> | FL proxy*
    ```
   
    For example, you could use the proxy address for the `contoso.mail.onmicrosoft.com` domain. 
    
After you complete this procedure, the on-premises user can use Outlook (or sign in to Office 365 and use Outlook on the Web) to access the contents of the previous inactive mailbox.
  
## More information

- **What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using In-Place eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. 
    
- **What happens when you recover an inactive mailbox?** When you recover an inactive mailbox, the following things occur: 
    
  - Litigation Hold (if it was enabled for the inactive mailbox) is removed.
    
  - In-Place Holds are removed. This means that the inactive mailbox is removed as a source mailbox from any In-Place Hold or In-Place eDiscovery searches. 
    
  - The inactive mailbox is removed from any Office 365 retention policies that where applied to it.
    
  - The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
  - Retention hold is enabled, and the retention hold duration is set to 30 days. This means that the default Exchange retention policy and any organization-wide or Exchange-wide Office 365 retention policies that are assigned to the new mailbox won't be processed for 30 days. This gives the returning employee or the new owner of the recovered inactive mailbox time to manage the old messages. Otherwise, the Exchange or Office 365 retention policy might delete old mailbox items (or move items to the archive mailbox, if it's enabled) that have expired based on the settings configured for the Exchange or Office 365 retention policies. After 30 days, the retention hold expires, the **RetentionHoldEnabled** mailbox property is set to **False**, and the Managed Folder Assistant starts processing the policies assigned to the mailbox. If you don't need this additional time, you can just remove the retention hold. Alternatively, you can increase the duration of the retention hold by using the **Set-Mailbox -EndDateForRetentionHold** command. For more information, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Put a hold on the recovered mailbox if you need to preserve the original state of the inactive mailbox.** To prevent the new mailbox owner or retention policy from permanently deleting any messages from the recovered inactive mailbox, you can place the mailbox on Litigation Hold For more information, see [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **What user ID can you use when recovering an inactive mailbox?** When you recover an inactive mailbox, the value that you specify for the  *MicrosoftOnlineServicesID*  parameter can be different from the original one that was associated with the inactive mailbox. You can also use the original user ID. But as previously stated, make sure that the values used for  *Name*  and  *MicrosoftOnlineServicesID*  are unique within your organization when you recover the inactive mailbox. 
    
- **What if the mailbox retention period for the inactive mailbox hasn't expired?** If an inactive mailbox was soft-deleted less than 30 days ago, you can't use the **New-Mailbox -InactiveMailbox** command to recover it. You have to recover it by restoring the corresponding Office 365 user account. For more information, see [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **How do you know if the soft-deleted mailbox retention period for an inactive mailbox has expired?** Run the following command. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    If there isn't a value for the **ExternalDirectoryObjectId** property, the mailbox retention period has expired, and you can recover the inactive mailbox by running the **New-Mailbox -InactiveMailbox** command. If there is a value for the **ExternalDirectoryObjectId** property, the soft-deleted mailbox retention period hasn't expired and you have to recover the mailbox by restoring the Office 365 user account. See [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **Consider enabling the archive mailbox after you recover an inactive mailbox.** This lets the returning user or new employee move old messages to the archive mailbox. And when the retention hold expires, the archive policy that is part of the default Exchange retention policy assigned to Exchange Online mailboxes will move items that are two years or older to the archive mailbox. If you don't enable the archive mailbox, items older than two years will remain in the user's primary mailbox. For more information, see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).
 