---
title: "Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7

description: "Assign the permissions required to perform eDiscovery-related tasks using the Security &amp; Compliance Center."
---

# Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center

If you want people to use any of the eDiscovery-related tools in the Office 365 Security &amp; Compliance Center, you have to assign them the appropriate permissions. The easiest way to do this is to add the person the appropriate role group on the **Permissions** page in the Office 365 Security &amp; Compliance Center. This topic describes the permissions required to perform eDiscovery-related tasks using the Security &amp; Compliance Center. 
  
The primary eDiscovery-related role group in Security &amp; Compliance Center is called **eDiscovery Manager**. There are two subgroups within this role group. 
  
- **eDiscovery Managers** An eDiscovery Manager can use the Content Search tool in the Security &amp; Compliance Center to search content locations in the organization, and perform various search-related actions such as preview and export search results. Members can also create and manage eDiscovery cases, add and remove members to a case, create case holds, and run Content Searches associated with a case. An eDiscovery Managers can only access and manage the cases they create. They can't access or manage cases create by other eDiscovery Managers. 
    
- **eDiscovery Administrators** An eDiscovery Administrator is a member of the eDiscovery Manager role group, and can perform the same Content Search and case management-related tasks that an eDiscovery Manager can perform. Additionally, an eDiscovery Administrator can: 
    
  - Access all cases that are listed on the **eDiscovery cases** page in the Security &amp; Compliance Center. 
    
  - Manage any eDiscovery case after they add themself as a member of the case.
    
  - Perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and importing data. This is because a person who is an eDiscovery Administrator in the Security &amp; Compliance Center is automatically added as an administrator in Advanced eDiscovery.
    
    > [!NOTE]
    > To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license. 
  
    See the [More information](assign-ediscovery-permissions.md#moreinfo) section for reasons why you might want eDiscovery Administrators in your organization. 
    
## Before you begin

- You have to be a member of the Organization Management role group (or be assigned the Role Management role) to assign eDiscovery permissions in the Security &amp; Compliance Center.
    
- You can use the [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) cmdlet in Security &amp; Compliance Center PowerShell to add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group. However, you can't add a mail-enabled security group to the eDiscovery Administrators subgroup. See the [More information](assign-ediscovery-permissions.md#moreinfo) section for more details. 
    
## Assign eDiscovery permissions in the Security &amp; Compliance Center

1. Go to [https://protection.office.com](https://protection.office.com).
    
2. Sign in to Office 365 using your work or school account.
    
3. In the left pane of the Security &amp; Compliance Center, click **Permissions**, and then click the checkbox next to **eDiscovery Manager**.
    
4. On the **eDiscovery Manager** flyout page, do one of the following based on the eDiscovery permissions that you want to assign. 
    
  - **To make a user an eDiscovery Manager** Next to **eDiscovery Manager**, click **Edit**. Under **Selected eDiscovery Managers**, click **Edit**, and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery manager, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Manager** flyout page, click **Save** to save the changes to the eDiscovery Manager membership. 
    
  - **To make a user an eDiscovery Administrator** Next to **eDiscovery Administrator**, click **Edit**. Under **Selected eDiscovery Administrators**, click **Edit**, and then click ![Add Icon](media/ITPro_EAC_AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery Administrator, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Administrator** flyout page, click **Save** to save the changes to the eDiscovery Administrator membership. 
    
> [!NOTE]
> You can also use the **Add-eDiscoveryCaseAdmin** cmdlet to make a user an eDiscovery Administrator. However, the user must be assigned the Case Management role before you can use this cmdlet to make them an eDiscovery Administrator. For more information, see [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
On the **Permissions** page in the Security &amp; Compliance Center, you can also assign users eDiscovery-related permissions, by adding them to the Compliance Administrator, Organization Management, and Reviewer role groups. For a list of the eDiscovery-related roles assigned to each of these role groups, see the [More information](assign-ediscovery-permissions.md#moreinfo) section. 
  
[Return to top](assign-ediscovery-permissions.md#top)
  
## More information
<a name="moreinfo"> </a>

- **What are the eDiscovery-related roles in the Security &amp; Compliance Center?** The following table describes the eDiscovery-related roles in the Security &amp; Compliance Center, and indicates the built-in role groups that each role is assigned to, by default. 
    
|**Role**|**Compliance Administrator**|**eDiscovery Manager &amp; Administrator**|**Organization Management**|**Reviewer**|
|:-----|:-----|:-----|:-----|:-----|
|**Case Management** <br/> Lets users create, edit, delete, and control access to eDiscovery cases in the Security &amp; Compliance Center. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).  <br/> As previously explained, a user must be assigned the Case Management role before you can use the **Add-eDiscoveryCaseAdmin** cmdlet to make them an eDiscovery Administrator.  <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> |
|**Compliance Search** <br/> Lets users run the Content Search tool in the Security &amp; Compliance Center to search mailboxes and public folders, SharePoint Online sites, OneDrive for Business sites, Skype for Business conversations, Office 365 Groups, and Microsoft Teams. This role allows a user to get an estimate of the search results, but additional roles are needed to perform actions such as previewing, exporting, or deleting search results.  <br/> For more information, see [Content Search in Office 365](content-search.md).  <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> |
|**Export** <br/> Lets users export the results of a Content Search to a local computer. It also lets them prepare search results for analysis in Advanced eDiscovery.  <br/> For more information about exporting search results, see [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).  <br/> | <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | <br/> |
|**Hold** <br/>  Lets users place content in mailboxes, public folders, sites, Skype for Business conversations, and Office 365 groups on hold. When content is on hold, content owners will still be able to modify or delete the original content, but the content will be preserved until the hold is removed or until the hold duration expires.  <br/>  For more information about holds, see:  <br/> [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md) <br/> [Overview of retention policies](retention-policies.md) <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> |
|**Preview** <br/> Lets users view a list of items that were returned from a Content Search. They'll also be able to open and view each item from the list to view its contents.  <br/> | <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | <br/> |
|**Review** <br/> Lets users see and open the list of the cases on the eDiscovery page in the Security &amp; Compliance Center that they are members of. They can't perform any other case management tasks.  <br/> | <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**RMS Decrypt** <br/> Lets users decrypt RMS-encrypted email messages when exporting search results or preparing search results for analysis in Advanced eDiscovery. For more information about decrypting search results during export, see [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).  <br/> ||![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |||
|**Search And Purge** <br/> Lets users perform bulk removal of data matching the criteria of a content search. For more information, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).  <br/> | <br/> | <br/> |![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> |
   
- **Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes: 
    
  - If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.
    
  - Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated compliance searches. This can help to prevent any misuse of compliance searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a compliance search, you should limit the number of people who are eDiscovery Administrators.
    
    Also, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person must be an eDiscovery Administrator to perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and importing data in to a case.
    
- **Can I add a group as a member of the eDiscovery Manager role group in the Security &amp; Compliance Center?** As previously explained, you can add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group by using the **Add-RoleGroupMember** cmdlet in Security &amp; Compliance Center PowerShell. For example, you can run the following command to add a mail-enabled security group to the eDiscovery Manager role group. 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Note that an Exchange distribution group or an Office 365 group aren't supported. You must use a mail-enabled security group, which you can create in Exchange Online PowerShell by using the ` New-DistributionGroup -Type Security ` command. You can also create a mail-enabled security group (and add members) in the Exchange admin center or in the Office 365 admin center. Note that it might take up to 60 minutes after you create it for a new mail-enabled security to be available to add to the eDiscovery Managers role group. 
    
    Also as previously stated, you can't make a mail-enabled security group an eDiscovery Administrator by using the **Add-eDiscoveryCaseAdmin** cmdlet in Security &amp; Compliance Center PowerShell. You can only add individual users as eDiscovery Administrators. 
    
    Note that you also can't add a mail-enabled security group as a member of a case.
    
[Return to top](assign-ediscovery-permissions.md#top)
  

