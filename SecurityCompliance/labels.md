---
title: "Overview of labels"
ms.author: stephow
author: stephow
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: "Labels in Office 365 can help you take the right actions on the right content. With labels, you can classify data across your organization for governance, and enforce retention rules based on that classification. You can also use labels to implement records management across Office 365."
---

# Overview of labels

Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:
  
- Tax forms that need to be **retained** for a minimum period of time. 
    
- Press materials that need to be **permanently deleted** when they reach a certain age. 
    
- Competitive research that needs to be both **retained** and then **permanently deleted**. 
    
- Work visas that must be **marked as a record** so that they can't be edited or deleted. 
    
In all of these cases, labels in Office 365 can help you take the right actions on the right content. With labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.
  
With labels, you can:
  
- **Enable people in your organization to apply a label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied. 
    
- **Apply labels to content automatically** if it matches specific conditions, such as when the content contains: 
    
  - Specific types of sensitive information.
    
  - Specific keywords that match a query you create.
    
    The ability to apply labels to content automatically is important because:
    
  - You don't need to train your users on all of your classifications.
    
  - You don't need to rely on users to classify all content correctly.
    
  - Users no longer need to know about data governance policies - they can instead focus on their work.
    
    Note that auto-apply labels require an Office 365 Enterprise E5 subscription.
    
- **Apply a default label to a document library** in SharePoint and Office 365 group sites, so that all documents in that library get the default label. 
    
- **Implement records management across Office 365**, including both email and documents. You can use a label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted. 
    
You create and manage labels on the **Labels** page in the Office 365 Security &amp; Compliance Center. 
  
![Labels page](media/42d1865d-f0f5-436d-8e09-0e547302c816.png)
  
## Contents

- [How labels work with label policies](labels.md#howlabels)
    
- [Only one label at a time](labels.md#onlyone)
    
- [How long it takes for labels to take effect](labels.md#howlong)
    
- [Label policies and locations](labels.md#locations)
    
- [How labels enforce retention](labels.md#howlabelsenforce)
    
- [Where published labels can appear to end users](labels.md#wherepublished)
    
- [Applying a label automatically based on conditions](labels.md#applyingauto)
    
- [Applying a default label to all content in a SharePoint library, folder, or document set](labels.md#applyingdefault)
    
- [Applying a label to email by using rules](labels.md#applyrules)
    
- [Classifying content without applying any actions](labels.md#noactions)
    
- [Using labels for records management](labels.md#records)
    
- [Using a label as a condition in a DLP policy](labels.md#label)
    
- [Using the Label Activity Explorer and the data governance reports](labels.md#reports)
    
- [Using Content Search to find all content with a specific label applied to it](labels.md#contentsearch)
    
- [The principles of retention, or what takes precedence?](labels.md#principles)
    
- [Use labels instead of these features](labels.md#features)
    
- [Permissions](labels.md#permissions)
    
- [Find the PowerShell cmdlets for labels](labels.md#powershell)
    
- [More information](labels.md#moreinfo)
    
## How labels work with label policies
<a name="howlabels"> </a>

Making labels available to people in your organization so that they can classify content is a two-step process: first you create the labels, and then you publish them to the locations you choose. When you publish labels, a label policy gets created.
  
![Diagram of roles and tasks for labels](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
Labels are independent, reusable building blocks that are included in a label policy and published to different locations. Labels can be reused across many policies. The primary purpose of the label policy is to group a set of labels and specify the locations where you want those labels to appear.
  
![Diagram of labels, label policies, and locations](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. When you publish labels, they're included in a label policy. A single label can be included in many policies.
    
2. Label policies specify the locations to publish the labels.
    
## Only one label at a time
<a name="onlyone"> </a>

It's important to know that content like an email or document can have only a single label assigned to it at a time:
  
- For labels assigned manually by end users, people can remove or change the label that's assigned.
    
- If content has an auto-apply label assigned, an auto-apply label can be replaced by a label assigned manually by an end user.
    
- If content has a label assigned manually by an end user, an auto-apply label cannot replace the manually assigned label.
    
- If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.
    
Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](labels.md#principles).
  
## How long it takes for labels to take effect
<a name="howlong"> </a>

When you publish or auto-apply labels, they don't take effect immediately:
  
1. First the label policy needs to be synced from the Security &amp; Compliance Center to the locations in the policy.
    
2. Then the location may require time to make manual labels available to end users or auto-apply labels to content. How long this takes depends on the location and type of label.
    
### Manual labels

If you publish labels to SharePoint or OneDrive, it can take one day for those labels to appear for end users. In addition, if you publish labels to Exchange, it can take 7 days for those labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.
  
![Diagram of when manual labels take effect](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### Auto-apply labels

If you auto-apply labels to content matching specific conditions, it can take seven days for the labels to be applied to all content that matches the conditions.
  
![Diagram of when auto-apply labels take effect](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### How to check on the status of Exchange labels

In Exchange Online, labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.
  
1. [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. Run these commands.
    
  ```
  $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
  ```

  ```
  $xmlprops = [xml]($logProps.MailboxLog)
  ```

  ```
  $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
  ```

    In the results, the  `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
    If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    
## Label policies and locations
<a name="locations"> </a>

Different types of labels can be published to different locations, depending on what the label does.
  
|**If the label is…**|**Then the label policy can be applied to…**|
|:-----|:-----|
|Published to end users  <br/> |Exchange, SharePoint, OneDrive, Office 365 groups  <br/> |
|Auto-applied based on sensitive information types  <br/> |Exchange (all mailboxes only), SharePoint, OneDrive  <br/> |
|Auto-applied based on a query  <br/> |Exchange, SharePoint, OneDrive, Office 365 groups  <br/> |
   
Note that in Exchange, auto-apply labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.
  
Note that Exchange public folders and Skype do not support labels.
  
## How labels enforce retention
<a name="howlabelsenforce"> </a>

Labels can enforce exactly the same retention actions that a retention policy can. You can use labels to implement a sophisticated content plan (or file plan). For more information on how retention works, see [Overview of retention policies](retention-policies.md).
  
In addition, a label has two retention options that are available only in a label and not in a retention policy. With a label, you can:
  
- Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Overview of disposition reviews](disposition-reviews.md).
    
- Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.
    
![Retention settings with options specific to labels](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## Where published labels can appear to end users
<a name="wherepublished"> </a>

If your label will be assigned to content by end users, you can publish it to:
  
- Outlook on the web
    
- Outlook 2010 and later
    
- OneDrive
    
- SharePoint
    
- Office 365 groups (both the group site and group mailbox in Outlook on the web)
    
The sections below show how labels will appear in different apps to people in your organization.
  
### Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the label. 
  
![Assign policy menu in Outlook on the web](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the label is applied, you can view that label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
You can also apply labels to folders, in which case:
  
- All items in the folder automatically get the same label, **except** for items that have had a label applied explicitly to them. Explicitly labeled items keep their existing label. For more information, see the below section on the principles of retention. 
    
- If you change or remove the default label for a folder, the label's also changed or removed for all items in the folder, **except** items with explicit labels. 
    
- If you move an item with a default label from one folder to another folder with a different default label, the item will get the new default label.
    
- If you move an item with a default label from one folder to another folder with no default label, the old default label is removed.
    
### Outlook 2010 and later

To label an item in Outlook on the web, right-click the item \> on the **Ribbon** \> **Assign Policy** \> choose the label. 
  
![Assign Policy button](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
After the label is applied, you can view that label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
You can also apply labels to folders. This works the same in Outlook 2010 and later as it does in Outlook on the web -- see the previous section for more info.
  
### OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply label** \> choose the label. 
  
Note that you can also apply a label to a folder or document set, and you can set a default label for a document library - see the section below for more information.
  
![Apply label list for an item in SharePoint](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. 
  
![Library column for labels shown in custom view](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### Office 365 groups

When you publish labels to an Office 365 group, the labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a label to content is identical to that shown above for email and documents.
  
## Applying a label automatically based on conditions
<a name="applyingauto"> </a>

One of the most powerful features of labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the labels - Office 365 does the work for them.
  
![Diagram of roles and tasks for auto-apply labels](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
Auto-apply labels are powerful because:
  
- You don't need to train your users on all of your classifications.
    
- You don't need to rely on users to classify all content correctly.
    
- Users no longer need to know about data governance policies - they can focus on their work.
    
You can choose to apply labels to content automatically when that content contains:
  
- Specific types of sensitive information.
    
- Specific keywords that match a query you create.
    
![Choose condition page for auto-apply label](media/c0b7a3ef-bda0-494c-941d-f1f93753ecdd.png)
  
Note that auto-apply labels require an Office 365 Enterprise E5 subscription, and that it can take up to seven days for auto-apply labels to be applied to all content that matches the conditions, as described above.
  
### Auto-apply labels to content with specific types of sensitive information

When you create auto-apply labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy. Each policy template is preconfigured to look for specific types of sensitive information - for example, the template shown here looks for U.S. ITIN, SSN, and passport numbers. To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).
  
![Policy templates with sensitive information types](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a label will be auto-applied only when:
  
- The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.
    
- The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition. 
    
    If you change the match accuracy (or confidence level), you should use one of confidence levels used in a pattern for that type of sensitive information, as defined in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).
    
![Options for identifying sensitive information types](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### Auto-apply labels to content with specific keywords

You can auto-apply labels to content that satisfies certain conditions. The conditions available now support applying a label to content that contains specific words or phrases. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
Support for adding searchable properties (for example, **subject:** ) is coming soon. 
  
Note that query-based labels use the search index to identify content.
  
![Query editor](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)
  
## Applying a default label to all content in a SharePoint library, folder, or document set
<a name="applyingdefault"> </a>

In addition to enabling people to apply a label to individual documents, you can also apply a default label to a SharePoint library, folder, or document set, so that all documents in that location get the default label.
  
For a document library, this is done on the **Library settings** page for a document library. When you choose the default label, you can also choose to apply it to any existing items in the library. 
  
For example, if you have a tag for marketing materials, and you know a specific document library will contain only that type of content, you can make the Marketing Materials tag the default for all documents in that library.
  
![Apply label option on library Settings page](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
If you apply a default label to existing items in the library, folder, or document set:
  
- All items in the library, folder, or document set automatically get the same label, **except** for items that have had a label applied explicitly to them. Explicitly labeled items keep their existing label. For more information, see the below section on [The principles of retention, or what takes precedence?](labels.md#principles).
    
- If you change or remove the default label for a library, folder, or document set, the label's also changed or removed for all items in the library, folder, or document set, **except** items with explicit labels. 
    
- If you move an item with a default label from one library, folder, or document set to another library, folder, or document set, the item keeps its existing default label, even if the new location has a different default label.
    
## Applying a label to email by using rules
<a name="applyrules"> </a>

In Outlook 2010 or later, you can create rules to apply a label or retention policy.
  
For example, you can create a rule that applies a specific label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## Classifying content without applying any actions
<a name="noactions"> </a>

When you create a label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a label simply as a text label, without enforcing any actions.
  
For example, you can create a label named "Review later" with no actions, and then auto-apply that label to content with sensitive information types or queried content.
  
![Label settings page with retention turned off](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## Using labels for records management
<a name="records"> </a>

At a high level, records management means that:
  
- Important content is classified as a record by users.
    
- A record can't be modified or deleted.
    
- Records are finally disposed of after their stated lifetime is past.
    
You can use labels to implement a single, consistent records-management strategy across Office 365, whereas other records-management features such as the Record Center apply only to SharePoint content. And you can enforce retention actions on records, so that they're disposed of automatically at the end of their lifecycle.
  
When you create a label, you have the option to use the label to classify the content as a record.
  
![Classify content as a Record check box](media/9c300739-d5d0-41d2-88dd-137f1cfc9cb6.png)
  
When an item is labeled as a record, four things happen:
  
- The item can't be permanently deleted.
    
- The item can't be edited.
    
- The label can't be changed.
    
- The label can't be removed.
    
### Who can classify content as a record

For SharePoint content, any user in the default Members group (the Contribute permission level) can apply a record label to content. Only the site collection administrator can remove or change that label after it's been applied. In addition, a label that classifies content as a record needs to be applied manually; it can't be auto-applied.
  
### Records and folders

You can apply a label to a folder in Exchange, SharePoint, or OneDrive. If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record. When you move the item out of the folder, the item will continue to be labeled as a record.
  
### Records can't be deleted

If you attempt to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#how).
  
If you attempt to delete a record in a SharePoint, you see an error that the item wasn't deleted, and the item remains in the library.
  
![Message that item wasn't deleted from SharePoint](media/d0020726-1593-4a96-b07c-89b275e75c49.png)
  
If you attempt to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with content in place](retention-policies.md#how).
  
## Using a label as a condition in a DLP policy
<a name="label"> </a>

A label can enforce **retention** actions on content. In addition, you can use a label as a condition in a data loss prevention (DLP) policy. This means that a DLP policy can enforce **protection** actions, such as restricting access, on content that contains a specific label. 
  
For more information, see [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).
  
## Using the Label Activity Explorer and the data governance reports
<a name="reports"> </a>

After you publish or auto-apply your labels, you'll want to verify that they're being applied to content as you intended. To monitor your labels, you can use the:
  
- **Label Activity Explorer**. With the explorer (shown below), you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).
    
- **Data governance reports**. With these reports, you can quickly view label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).
    
![Label Activity Explorer](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## Using Content Search to find all content with a specific label applied to it
<a name="contentsearch"> </a>

After labels are assigned to content, either by users or auto-applied, you can use content search in the Security &amp; Compliance Center to find all content that's classified with a specific label.
  
![Content search page](media/564d5dfe-285a-4a7e-800e-907b12a1b273.png)
  
When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
![Compliance Tag condition](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## The principles of retention, or what takes precedence?
<a name="principles"> </a>

It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.
  
![Diagram of the principles of retention](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:
  
1. **Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted. 
    
2. **The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period. 
    
3. **Explicit inclusion wins over implicit inclusion.** This means: 
    
1. If a label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that label takes precedence over both a policy assigned at the site or mailbox level and a default label assigned by the document library. For example, if the explicit label says to retain for ten years, but the policy assigned to the site says to retain for only five years, the label takes precedence. Note that auto-apply labels are considered implicit, not explicit, because they're applied automatically by Office 365.
    
2. If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.
    
4. **The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period. 
    
Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.
  
Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.
  
## Use labels instead of these features
<a name="features"> </a>

Labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Office 365 groups. If you need to classify content or manage records anywhere in Office 365, we recommend that you use labels.
  
There are several other features that have previously been used to classify content or manage records in Office 365. These are listed below. These features will continue to work side by side with labels created in the Security &amp; Compliance Center. Note that while there are instances where the implementation of labels differs from previous features, the evolution of labels will drive the future of records management across Office 365. Therefore, moving forward, for data governance, we recommend that you use labels instead of these features.
  
### Exchange Online

- [Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only) 
    
### SharePoint Online and OneDrive for Business

- [Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention) 
    
- [Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention) 
    
- [Information management policies](intro-to-info-mgmt-policies.md) (Deletion only) 
    
## Permissions
<a name="permissions"> </a>

Members of your compliance team who will create labels need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group. 
  
For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).
  
These permissions are required only to create and apply labels and a label policy. Policy enforcement does not require access to the content.
  
## Find the PowerShell cmdlets for labels
<a name="powershell"> </a>

To use the label cmdlets, you need to:
  
1. [Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Use these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
## More information
<a name="moreinfo"> </a>

- [Overview of retention policies](retention-policies.md)
    

