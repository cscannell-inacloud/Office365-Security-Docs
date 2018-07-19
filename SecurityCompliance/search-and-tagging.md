---
title: "Search and Tagging"
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: "In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta."
---

# Search and Tagging

In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## Search the documents in your case

Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (*). These properties are supported in the query language property name:

- caselabel: tags created/applied in Search and Tagging for this case 
- custodians: custodians assigned in the case - subject to limitations
- date: sent date for email, modified date for documents
- fileid: file ID within the case
- filetype: native file extension
- fileclass: email, document, or attachment
- senderauthor: sender for emails, author for documents
- size: size of the file in KB
- subjecttitle: subject for emails, title for documents
- bcc
- cc
- participants: Email addresses of all participants in an email thread, including for missing links
- received: received date
- recipients: email recipient names or addresses (to, cc, bcc)
- sender
- lastmodifieddate: last modified date of a document
- sent: sent date of an email
- to
- author: author of an email
- title: title of a document
- dominanttheme: dominant theme of an item\*
- themeslist: themes that are associated with an item\*
- readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*
- relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*
- relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*

\* Only available if the Themes module has been run
\*\* Only available if the Relevance module has been run
  
## See also

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Understanding Assessment in Relevance](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging and Assessment](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Tracking Relevance analysis](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Deciding based on the results](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testing Relevance analysis](test-relevance-analysis-in-advanced-ediscovery.md)

