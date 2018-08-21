---
title: "Manage data governance in Office 365"
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid: 
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: "Data governance is all about keeping your data around when you need it and getting rid of it when you don't. With data governance in Office 365, you can manage the full content lifecycle, from importing and storing data at the beginning, to creating policies that retain and then permanently delete content at the end."
---

# Manage data governance in Office 365

Data governance is all about keeping your data around when you need it and getting rid of it when you don't. With data governance in Office 365, you can manage the full content lifecycle, from importing and storing data at the beginning, to creating policies that retain and then permanently delete content at the end.
  
## Import

Some of your data might be stored in places outside the cloud, like on-premises servers or in third-party apps. The Import service makes it easy to bring your messaging, SharePoint, and OneDrive for Business data into Office 365, either by uploading it directly over the network or shipping an encrypted drive to us. You can also use the Intelligent Import feature in the Import service to filter the items in PST files that actually get imported to the target mailboxes. 
  
- [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md)
    
- [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [Use the PST Collection Tool to find, copy, and delete PST files in your organization](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md)
    
- [Upload on-premises content to SharePoint Online using PowerShell cmdlets](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## Govern I: Store data

After you import data, you might need to increase your storage. The unlimited archiving feature in Office 365 (called auto-expanding archiving) provides an unlimited amount of storage in archive mailboxes.
  
- [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md)

- [Overview of unlimited archiving in Office 365](unlimited-archiving.md)
    
- [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md)
    

    
## Govern II: Create policies and labels to retain content

A retention policy helps you to comply proactively with industry regulations and internal policies by ensuring that you retain content as long as required but no longer than that. A single retention policy can cover your entire organization. In addition, you can use labels to implement a file plan by classifying data across your organization for governance, and then enforcing retention rules based on that classification.
  
- [Overview of retention policies](retention-policies.md)
    
- [Overview of labels](labels.md)
    
- [Bulk create and publish labels by using PowerShell](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [Overview of disposition reviews](disposition-reviews.md)
    
- [Overview of event-driven retention](event-driven-retention.md)
    
## Govern III: Retain the email of former employees

When a person leaves your organization, you can retain their email by creating an inactive mailbox. A mailbox becomes inactive when a Litigation Hold, Office 365 retention policy, or other type of hold is applied to it, and then the corresponding Office 365 user account is deleted. Items in an inactive mailbox are retained for the duration of the hold or retention policy that was placed on the mailbox before it was made inactive.
  
- [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md)
    
- [Create and manage inactive mailboxes in Office 365](create-and-manage-inactive-mailboxes.md)

- [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md)
 
- [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md)

- [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md)

## Monitor

Supervision lets you define policies that capture email and 3rd-party communications in your organization so they can be examined by internal or external reviewers. Reviewers can then classify these communications, make sure they're compliant with your organization's policies, and escalate questionable material if necessary.
  
You can also use the data governance reports and the Label Activity Explorer to monitor that your labels are being applied to content as you intended.
  
- [Configure supervision policies for your organization](configure-supervision-policies.md)
    
- [Supervision reports](supervision-reports.md)
    
- [View label activity for documents](view-label-activity-for-documents.md)
    
- [View the data governance reports](view-the-data-governance-reports.md)
    
## More information

- [Watch videos from the Microsoft Data Governance team](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [Watch an overview of data governance in Office 365](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Office 365 Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?linkid=852310)
    

