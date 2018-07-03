---
title: "eDiscovery solution series Data spillage scenario - Search and purge"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: "What is data spillage and why should you care? Data spillage is when a confidential document is released to untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it and permanently purge the spilled data from the system."
---

# eDiscovery solution series: Data spillage scenario - Search and purge

 **What is data spillage and why should you care?** Data spillage is when a confidential document is released to untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it and permanently purge the spilled data from the system. 
  
## Data spillage scenario

You're a lead information security officer at Contoso. You are informed of a data spillage situation - an employee unknowingly shared a highly confidential document with multiple people through email. You want to quickly assess who received this document internally and externally. Once identified, you would like to share case findings with other investigators to review, and then permanently remove the data from Office 365. After the investigation is complete, you want to generate a report with the evidence of permanent removal and other case details for any future reference.
  
### Scope of this article

This document provides a list of instructions on how to permanently remove a message from Office 365 so that it's not accessible or recoverable. To delete a message and make it recoverable until the deleted item retention period expires, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).
  
## Workflow for managing data spillage incidents
<a name="workflow"> </a>

Here's a how to manage a data spillage incident:
  
[(Optional) Step 1: Manage who can access the case and set compliance boundaries](data-spillage-scenariosearch-and-purge.md#step1)
  
[Step 2: Create an eDiscovery case](data-spillage-scenariosearch-and-purge.md#step2)
  
[Step 3: Search for the spilled data](data-spillage-scenariosearch-and-purge.md#step3)
  
[Step 4: Review and validate case findings](data-spillage-scenariosearch-and-purge.md#step4)
  
[Step 5: Use message trace log to check how spilled data was shared](data-spillage-scenariosearch-and-purge.md#step5)
  
[Step 6: Prepare for deletion by collecting spillage information](data-spillage-scenariosearch-and-purge.md#step6)
  
[Step 7: Permanently delete the spilled data](data-spillage-scenariosearch-and-purge.md#step7)
  
[Step 8: Verify, provide a proof of deletion, and audit](data-spillage-scenariosearch-and-purge.md#step8)
  
## Things to know before you start
<a name="workflow"> </a>

- When a mailbox is on hold, a deleted message remains in the Recoverable Items folder until the retention period expires or the hold is released. [Step 6: Prepare for deletion by collecting spillage information](data-spillage-scenariosearch-and-purge.md#step6) describes how to remove hold from the mailboxes. Check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority. 
    
- To control which user mailboxes an data spillage investigator can search and manage who can access the case, you can set up compliance boundaries and create a custom role group, which is described in [(Optional) Step 1: Manage who can access the case and set compliance boundaries](data-spillage-scenariosearch-and-purge.md#step1). To do this, you have to be a member of the Organization Management role group or be assigned the role management role. If you or in administrator in your organization has already set compliance boundaries, you can skip Step 1.
    
- To create a case, you must be a member of the eDiscovery Manager role group or be a member of a custom role group that's assigned the Case Management role. If you're not a member, ask an Office 365 administrator to [add you to the eDiscovery manager role group](https://support.office.com/article/Assign-eDiscovery-permissions-in-the-Office-365-Security-Compliance-Center-5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7).
    
- To delete data that's spilled into your organization, you need to use the [Search-Mailbox -DeleteContent](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) command in Exchange Online PowerShell. Additionally, to use the  _DeleteContent_ parameter, you also have to be a member of a role group in Exchange Online that's assigned the Mailbox Import Export role. See the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).
    
- To search the Office 365 audit log for eDiscovery activities, auditing must be turned on for your organization. You can search for activities that were performed within the last 90 days. To learn more about how to enable and use auditing, see the [Audit the data spillage investigation process](data-spillage-scenariosearch-and-purge.md#dataspillageaudit) section in Step 8. 
    
## (Optional) Step 1: Manage who can access the case and set compliance boundaries
<a name="step1"> </a>

Depending on your organizational practice, you need to control who can access the eDiscovery case used to investigate a data spillage incident and set compliance boundaries. The easiest way to do this is to add investigators as members of an existing role group in the Office 365 Security &amp; Compliance Center and then add them a member of the eDiscovery case. For information about the existing eDiscovery role groups and how to add members to an eDiscovery case, see [Assign eDiscovery permissions in the Office 365 Security and Compliance Center](5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7.md).
  
You can also create a new role group that aligns with your organizational needs. For example, you might want a group of data spillage investigators in the organization to access and share all data spillage cases. You can do this by creating a "Data Spillage Investigator" role group, assigning appropriate roles (Export, RMS Decrypt, Review, Preview, Compliance Search, and Case Management), adding the data spillage investigators to the role group, and then adding the role group as a member of the data spillage eDiscovery case. See [Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md) for detailed instructions on how to do this. 
  
## Step 2: Create an eDiscovery case
<a name="step2"> </a>

An eDiscovery case provides an effective way to manage your data spillage investigation. You can add members to the role group that you created in Step 1, add the role as a member of new eDiscovery case, perform iterative searches to find the information of your interest, export a report to share, track the status of the case, and then refer back to the details of the case if needed. Consider establishing a naming convention for eDiscovery cases used for data spillage incidents, and provide as much information as you can in the case name and description so you can locate and refer to in the future if necessary.
  
To create a new case, you can use eDiscovery in the Security &amp; Compliance Center. See [Step 2: Create a new case](ediscovery-cases.md#step2_1).
  
## Step 3: Search for the spilled data
<a name="step3"> </a>

Now that you've created a case and managed access, you can use the case to iteratively search to find the spilled data and identify the mailboxes that contain the spilled data. You will use the same search query that you used to find the email messages to delete those same messages in [Step 7: Permanently delete the spilled data](data-spillage-scenariosearch-and-purge.md#step7).
  
To create a content searches associated with an eDiscovery case, see [Step 5: Create and run a Content Search associated with a case](ediscovery-cases.md#step4_1).
  
 **Important:** The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use the it as search keyword, you must delete the query afterwards to avoid further spillage. See the [Delete the search query](data-spillage-scenariosearch-and-purge.md#deletesearchquery) in Step 8. 
  
## Step 4: Review and validate case findings
<a name="step4"> </a>

After you create a content search, you need to review and validate that the search results and verify that they consist only of the email messages ﻿that must be deleted. Without exporting the search results to avoid further data spillage, you can preview a random sampling of 1000 messages. If you have more than 1000 messages to review, you can divide the initial search into multiple searches by using additional keywords or conditions and review the results of each search individually. Make sure to note down all search queries to use when you delete messages in [Step 7: Permanently delete the spilled data](data-spillage-scenariosearch-and-purge.md#step7).
  
If a custodian or end user is assigned an Office 365 E5 license, you can examine all search results at once using Advanced eDiscovery. In Advanced eDiscovery, if a sender sent a message to 100 recipients, it will show as one de-duplicated email message to review. By using analytics tools in Advanced eDiscovery, such as optical character recognition, email threading, and predictive coding, you can quickly process and review thousands of messages and tag them for further review. See [Quick setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).
  
When you find an email message that contains spilled data, check the recipients of the message to determine if it was shared externally. To further trace an message, you can collect sender information and date range so you can use the message trace logs, which is described in [Step 5: Use message trace log to check how spilled data was shared](data-spillage-scenariosearch-and-purge.md#step5).
  
Afer you verified the search results, you may want to share your findings with others for a secondary review. People who you assigned to the case in [(Optional) Step 1: Manage who can access the case and set compliance boundaries](data-spillage-scenariosearch-and-purge.md#step1) can review the case content in both eDiscovery and Advanced eDiscovery and approve case findings. You can also generate a report without exporting the actual content that identifies the messages returned by the search query that will be deleted. You can use this same report as a proof of deletion, which is described in [Step 8: Verify, provide a proof of deletion, and audit](data-spillage-scenariosearch-and-purge.md#step8).
  
 **To generate a statistical report:**
  
1. Go to Search page on eDiscovery, and click the search that you would like to generate report for. On the flyout, click "More" and "Export report." The Export report page is displayed.
    
2. Select "All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons" and click "Generate report."
    
3. In the eDiscovery case, click "Export" to display the list of export jobs. You might have to click Refresh to update the list with the export job that you just created.
    
4. Click the export job that you just created and "[Download report.](.md) " 
    
5. "Export Summary.csv" will contain the number of locations found with result and the size of the search result. You can use this to compare with report generated after deletion and provide as a proof of deletion. "Results.csv" contains more detailed summary of search result including subject, sender, recipients, if the email was read, dates and size.  *If any of this detail contains spilled data, make sure to discard "Results.csv".* 
    
## Step 5: Use message trace log to check how spilled data was shared
<a name="step5"> </a>

To further investigate if email with spilled data was shared, you can optionally query message trace logs with the sender information and/or date range that you gathered in Step 4. The retention period for message traces is 30 days for real time data and 90 days for historical data.
  
You can use message tracing in the Security &amp; Compliance Center or use the corresponding cmdlets in Exchange Online PowerShell. It's important to note that message trace doesn't offer full guarantees on the completeness of data returned. For more information about using message trace, see: 
  
- [Message trace in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [New Message Trace in Office 365 Security &amp; Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## Step 6: Prepare for deletion by collecting spillage information
<a name="step6"> </a>

After you review and validate that the search results contains only the messages that must be deleted, you need to collect a list of the email addresses of the impacted mailboxes to use in Step 7 when you run the **Search-Mailbox -DeleteContent** command. There are two ways to do this. 
  
### Option 1: Get mailbox locations from search statistics

1. Open the eDiscovery case, go to the **Search** page and select the appropriate content search. 
    
2. On the flyout page, click **View results**.
    
3. In the **Individual results** drop down list, click **Search statistics**.
    
4. In the **Type** drop down list, click **Top locations**.
    
    A list of mailboxes that contain search results is displayed. The number of items in each mailbox that match the search query is also displayed.
    
5. Copy the information in the and save it to a file or click **Download** to download the information to a CSV file. 
    
### Option 2: Get mailbox locations from the export report

Open the Export Summary report that you downloaded in [Step 4: Review and validate case findings](data-spillage-scenariosearch-and-purge.md#step4). In the first column in the report, the email address of each mailbox is listed under **Locations**.
  
## Step 7: Permanently delete the spilled data
<a name="step7"> </a>

Depending on whether single item recovery is enabled on the mailboxes that contain the spilled data or if any of those mailboxes are on hold, you may have prepare the mailboxes before you can permanently delete email messages.
  
### Prepare the mailboxes

If single item recovery is enabled or a mailbox is placed on hold, a permanently deleted (purged) message will be retained in Recoverable Items folder. So before you can purged spilled data, you need to check the existing mailbox configurations and disable single item recovery and remove any hold or Office 365 retention policy. Keep in mind that you can prepare one mailbox at a time, run the same command on different mailboxes or create PowerShell script to prepare multiple mailboxes.
  
- See "Step 1: Collect information about the mailbox" in [Step 1: Collect information about the mailbox](a85e1c87-a48e-4715-bfa9-d5275cde67b0.md#step1) for instructions about how to check if single item recovery is enabled or if the mailbox is placed on hold or it's assigned to a retention policy. 
    
- See "Step 2: Prepare the mailbox" in [Step 2: Prepare the mailbox ](a85e1c87-a48e-4715-bfa9-d5275cde67b0.md#step2) for instructions about disabling single item recovery. 
    
- See "Step 3: Remove all holds from the mailbox" in [Step 3: Remove all holds from the mailbox](a85e1c87-a48e-4715-bfa9-d5275cde67b0.md#step3) for instructions about how to remove a hold or retention policy from a mailbox. 
    
 **Important:** Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority. 
  
Be sure to revert the mailbox to previous configurations after you verify that the spilled data has been permanently deleted. See the details in [Step 7: Permanently delete the spilled data](data-spillage-scenariosearch-and-purge.md#step7).
  
### Permanently delete messages

[Using](.md) the mailbox identity and the search query used in Step 3 to find the message, you can now permanently delete the spilled data by: 
  
1. [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
2. Run below command:
    
Search-Mailbox -Identity ** * \<mailbox identity\> * ** -SearchDumpster -DeleteContent $true -SearchQuery ** *\<search query\>* **
  
More examples on Search-Mailbox deletion command can be found on [Delete items in the Recoverable Items folder](https://support.office.com/en-us/article/Delete-items-in-the-Recoverable-Items-folder-of-cloud-based-mailboxes-on-hold-Admin-Help-a85e1c87-a48e-4715-bfa9-d5275cde67b0#step4).
  
Keep in mind that you can permanently delete messages from one mailbox at a time. You can re-run the same command and replace the target mailbox each time you run it or create a [powershell script](https://docs.microsoft.com/en-us/powershell/scripting/powershell-scripting?view=powershell-6) to run against a list of mailboxes. 
  
## Step 8: Verify, provide a proof of deletion, and audit
<a name="step8"> </a>

To verify that the spilled data was permanently removed, go to the case and re-run the same search query to confirm that there are no results returned. You can export a report and provide it along with the original report as a proof of deletion. You can [close the case](https://support.office.com/en-us/article/manage-ediscovery-cases-in-the-office-365-security-compliance-center-9a00b9ea-33fd-4772-8ea6-9d3c65e829e6?ui=en-US&amp;rs=en-US&amp;ad=US#closecase_1) and if necessary refer to it any time in the future. 
  
### Reconfigure the mailbox to its previous state

If you changed any mailbox configurations in [Step 6: Permanently delete the spilled data so that it's not accessible or recoverable](https://microsoft-my.sharepoint.com/personal/sepa_microsoft_com/Documents/Data%20Spillage%20Solution%20Documentation.docx#_Configuring_mailboxes_1), you need to revert the mailbox to its previous state. See [Revert the mailbox to its previous state](https://support.office.com/en-us/article/Delete-items-in-the-Recoverable-Items-folder-of-cloud-based-mailboxes-on-hold-Admin-Help-a85e1c87-a48e-4715-bfa9-d5275cde67b0#step5)
  
### Delete the search query
<a name="deletesearchquery"> </a>

If the search keywords used in step 3 contain data that need to be purged, you must delete the search query to prevent further spillage.
  
Using eDiscovery in SCC:
  
1. Select the search that contains keywords to be deleted.
    
2. Click on Delete.
    
### Audit the data spillage investigation process
<a name="dataspillageaudit"> </a>

You can audit eDiscovery activities and permanent deletion in Security &amp; Compliance Center. You can see all audited eDiscovery activities and Exchange mail activities on [Audited activities](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#exchangemailboxactivities&amp;PickTab=Activities). To search for the audited activities, see [Search for eDiscovery activities in the Office 365 audit log](https://support.office.com/en-us/article/search-for-ediscovery-activities-in-the-office-365-audit-log-67cc7f42-a53d-4751-b929-6005c80798f7)
  

