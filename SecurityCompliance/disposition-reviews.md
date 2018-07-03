---
title: "Overview of disposition reviews"
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: "When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period."
---

# Overview of disposition reviews

When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:
  
- Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.
    
- Remove content from the disposition list to store in an archive, if that content has research or historical value.
    
- Assign a different retention period to the content, if the original policy was a temporary or provisional solution.
    
- Return the content to clients or transfer it to another organization.
    
When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:
  
- The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.
    
- The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content. 
    
- For each document, the reviewer can:
    
  - Apply a different label.
    
  - Extend its retention period.
    
  - Permanently delete it.
    
- Reviewers can view either pending or historical dispositions, and export that list as a .csv file.
    
Note that disposition reviews require an Office 365 Enterprise E5 subscription.
  
A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.
  
![Disposition page](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## Setting up the disposition review by creating a label

This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.
  
![Chart showing flow of how disposition works](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.
  
For more information about labels, see [Overview of labels](labels.md).
  
![Retention settings for a label](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## Disposing content

When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then: 
  
- Apply a different label.
    
- Extend the retention period.
    
- Permanently delete the item.
    
A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.
  
Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.
  
Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md). 
  
![Disposition options for a document](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## Permissions for disposition

To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)
  
## How long until disposed content is permanently deleted

Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how).
  
This means that:
  
- Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold. 
    
- Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition. 
    
## View pending and completed dispositions

On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions: 
  
- **Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it. 
    
- **Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here. 
    
### Filter the disposition views

You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.
  
![Filter options on Disposition page](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### Export the disposition items

In addition, you can export the items in either view as a .csv file that you can open in Excel.
  
![Exported disposition data in Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

