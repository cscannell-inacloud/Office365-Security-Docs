---
title: "Keyword queries and search conditions for Content Search"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- 'ms.o365.cc.SearchQueryLearnMore'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3

description: "Learn about email and file properties that you can search in Exchange Online mailboxes and in SharePoint or OneDrive for Business sites using the Content Search tool in the Office 365 Security &amp; Compliance Center. 
"
---

# Keyword queries and search conditions for Content Search

This topic describes the email and document properties that you can search for in email items in Exchange Online and documents stored on SharePoint and OneDrive for Business sites by using the Content Search feature in the Office 365 Security &amp; Compliance Center. You can also use the **\*-ComplianceSearch** cmdlets in Security &amp; Compliance Center PowerShell to search for these properties. The topic also describes: 
  
- Using Boolean search operators, search conditions, and other search query techniques to refine your search results.
    
- Searching for sensitive data types and custom sensitive data types in SharePoint and OneDrive for Business.
    
- Searching for site content that's shared with users outside of your organization
    
||
|:-----|
|For step-by-step instructions on how to create a Content Search, see [Content Search in Office 365](content-search.md). |
   
 **Contents**
  
[Searchable email properties](keyword-queries-and-search-conditions.md#emailproperties)
  
[Searchable site properties](keyword-queries-and-search-conditions.md#siteproperties)
  
[Searchable contact properties](keyword-queries-and-search-conditions.md#contactproperties)
  
[Searchable sensitive data types](keyword-queries-and-search-conditions.md#dlptypes)
  
[Search operators](keyword-queries-and-search-conditions.md#searchoperators)
  
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
[Searching for site content shared with external users](keyword-queries-and-search-conditions.md#external)
  
[Searching for site content shared within your organization](keyword-queries-and-search-conditions.md#internal)
  
[Search tips and tricks](keyword-queries-and-search-conditions.md#searchtips)
  
> [!NOTE]
> Content Search in the Security &amp; Compliance Center and the corresponding **\*-ComplianceSearch** cmdlets in Security &amp; Compliance Center PowerShell use the Keyword Query Language (KQL). For more detailed information, see [Keyword Query Language syntax reference](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## Searchable email properties
<a name="emailproperties"> </a>

The following table lists email message properties that can be searched by using the Content Search feature in the Security &amp; Compliance Center or by using the **New-ComplianceSearch** or the **Set-ComplianceSearch** cmdlet. The table includes an example of the  _property:value_ syntax for each property and a description of the search results returned by the examples. You can type these  `property:value` pairs in the keywords box for a Content Search. 
  
|**Property**|**Property description**|**Examples**|**Search results returned by the examples**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |The names of files attached to an email message.  <br/> |attachmentnames:annualreport.ppt  <br/> attachmentnames:annual\*  <br/> |Messages that have an attached file named annualreport.ppt. In the second example, using the wildcard returns messages with the word "annual" in the file name of an attachment.  <br/> |
|Bcc  <br/> |The BCC field of an email message.<sup>1</sup> <br/> |bcc:pilarp@contoso.com  <br/> bcc:pilarp  <br/> bcc:"Pilar Pinilla"  <br/> |All examples return messages with Pilar Pinilla included in the Bcc field.  <br/> |
|Category  <br/> | The categories to search. Categories can be defined by users by using Outlook or Outlook Web App. The possible values are:  <br/>  blue  <br/>  green  <br/>  orange  <br/>  purple  <br/>  red  <br/>  yellow  <br/> |category:"Red Category"  <br/> |Messages that have been assigned the red category in the source mailboxes.  <br/> |
|Cc  <br/> |The CC field of an email message.<sup>1</sup> <br/> |cc:pilarp@contoso.com  <br/> cc:"Pilar Pinilla"  <br/> |In both examples, messages with Pilar Pinilla specified in the CC field.  <br/> |
|Folderid  <br/> |The folder ID (GUID) of a specific mailbox folder. If you use this property, be sure to search the mailbox that the specified folder is located in. Note that only the specified folder will be searched. Any subfolders in the folder won't be searched. To search sub-folders, you need to use the Folderid property for the sub-folder you want to search.  <br/> For more information about searching for the Folderid property and using a script to obtain the folder IDs for a specific mailbox, see [Use Content Search in Office 365 for targeted collections](use-content-search-for-targeted-collections.md).  <br/> |folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000  <br/> folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com  <br/> |The first example returns all items in the specified mailbox folder. The second example return all items in the specified mailbox folder that were sent or received by garthf@contoso.com.  <br/> |
|From  <br/> |The sender of an email message.<sup>1</sup> <br/> |from:pilarp@contoso.com  <br/> from:contoso.com  <br/> |Messages sent by the specified user or sent from a specified domain.  <br/> |
|HasAttachment  <br/> |Indicates whether or not a message has an attachment. Use the values **true** or **false**.  <br/> |from:pilar@contoso.com AND hasattachment:true  <br/> |Messages sent by the specified user that have attachments.  <br/> |
|Importance  <br/> |The importance of an email message, which a sender can specify when sending a message. By default, messages are sent with normal importance, unless the sender sets the importance as **high** or **low**.  <br/> |importance:high  <br/> importance:medium  <br/> importance:low  <br/> |Messages that are marked as high importance, medium importance, or low importance.  <br/> |
|IsRead  <br/> |Indicates whether or not messages have been read. Use the values **true** or **false**.  <br/> |isread:true  <br/> isread:false  <br/> |The first example returns messages with the IsRead property set to **True**. The second example returns messages with the IsRead property set to **False**.  <br/> |
|ItemClass  <br/> |Use this property to search specific third-party data types that your organization imported to Office 365. Use the following syntax for this property:  `itemclass:ipm.externaldata.<third-party data type>*` <br/> |itemclass:ipm.externaldata.Facebook\* AND subject:contoso  <br/> itemclass:ipm.externaldata.Twitter\* AND from:"Ann Beebe" AND "Northwind Traders"  <br/> |The first example returns Facebook items that contain the word "contoso" in the Subject property. The second example returns Twitter items that were posted by Ann Beebe and that contain the keyword phrase "Northwind Traders".  <br/> For a complete list of values to use for third-party data types for the ItemClass property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).  <br/> |
|Kind  <br/> | The type of email message to search for. Possible values:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  microsoftteams (returns items from chats, meetings, and calls in Microsoft Teams)  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail  <br/> |kind:email  <br/> kind:email OR kind:im OR kind:voicemail  <br/> kind:externaldata  <br/> |The first example returns email messages that meet the search criteria. The second example returns email messages, instant messaging conversations, and voice messages that meet the search criteria.  <br/> The third example returns items that were imported to mailboxes in Office 365 from third-party data sources, such as Twitter, Facebook, and Cisco Jabber, that meet the search criteria. For more information, see [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).  <br/> |
|Participants  <br/> |All the people fields in an email message; these fields are From, To, CC, and BCC.<sup>1</sup> <br/> |participants:garthf@contoso.com  <br/> participants:contoso.com  <br/> |Messages sent by or sent to garthf@contoso.com. The second example returns all messages sent by or sent to a user in the contoso.com domain.  <br/> |
|Received  <br/> |The date that an email message was received by a recipient.  <br/> |received:04/15/2016  <br/> received\>=01/01/2016 AND received\<=03/31/2016  <br/> |Messages that were received on April 15, 2016. The second example returns all messages received between January 1, 2016 and March 31, 2016.  <br/> |
|Recipients  <br/> |All recipient fields in an email message; these fields are To, CC, and BCC.<sup>1</sup> <br/> |recipients:garthf@contoso.com  <br/> recipients:contoso.com  <br/> |Messages sent to garthf@contoso.com. The second example returns messages sent to any recipient in the contoso.com domain.  <br/> |
|Sent  <br/> |The date that an email message was sent by the sender.  <br/> |sent:07/01/2016  <br/> sent\>=06/01/2016 AND sent\<=07/01/2016  <br/> |Messages that were sent on the specified date or sent within the specified date range.  <br/> |
|Size  <br/> |The size of an item, in bytes.  <br/> |size\>26214400  <br/> size:1..1048567  <br/> |Messages larger than 25??MB. The second example returns messages from 1 through 1,048,567 bytes (1 MB) in size.  <br/> |
|Subject  <br/> |The text in the subject line of an email message.  <br/> **Note:** When you use the Subject property in a query, ???the search returns all messages in which the subject line contains the text you're searching for. In other words, the query doesn't return only those messages that have an exact match. For example, if you search for  `subject:"Quarterly Financials"`, your results will include messages with the subject "Quarterly Financials 2018".  <br/> |subject:"Quarterly Financials"  <br/> subject:northwind  <br/> |Messages that contain the phrase "Quarterly Financials" anywhere in the text of the subject line. The second example returns all messages that contain the word northwind in the subject line.  <br/> |
|To  <br/> |The To field of an email message.<sup>1</sup> <br/> |to:annb@contoso.com  <br/> to:annb  <br/> to:"Ann Beebe"  <br/> |All examples return messages where Ann Beebe is specified in the To: line.  <br/> |
   
> [!NOTE]
> <sup>1</sup>??????For the value of a recipient property, you can use the SMTP address, display name, or alias to specify a user. For example, you can use annb@contoso.com, annb, or "Ann Beebe" to specify the user Ann Beebe. 
  
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Searchable site properties
<a name="siteproperties"> </a>

The following table lists some of the SharePoint and OneDrive for Business properties that can be searched by using the Content Search feature in the Security &amp; Compliance Center or by using the **New-ComplianceSearch** or the **Set-ComplianceSearch** cmdlet. The table includes an example of the  _property:value_ syntax for each property and a description of the search results returned by the examples. 
  
For a complete list of SharePoint properties that can be searched, see [Overview of crawled and managed properties in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Properties marked with a **Yes** in the ** Queryable ** column can be searched. 
  
|**Property**|**Property description**|**Example**|**Search results returned by the examples**|
|:-----|:-----|:-----|:-----|
|Author  <br/> |The author field from Office documents, which persists if a document is copied. For example, if a user creates a document and the emails it to someone else who then uploads it to SharePoint, the document will still retain the original author. Be sure to use the user's display name for this property.  <br/> |author:"Garth Fort"  <br/> |All documents that are authored by Garth Fort.  <br/> |
|ContentType  <br/> |The SharePoint content type of an item, such as Item, Document, or Video.  <br/> |contenttype:document  <br/> |All documents would be returned.  <br/> |
|Created  <br/> |The date that an item is created.  <br/> |created\>=06/01/2016  <br/> |All items created on or after June 1, 2016.  <br/> |
|CreatedBy  <br/> |The person that created or uploaded an item. Be sure to use the user's display name for this property.  <br/> |createdby:"Garth Fort"  <br/> |All items created or uploaded by Garth Fort.  <br/> |
|DetectedLanguage  <br/> |The language of an item.  <br/> |detectedlanguage:english  <br/> |All items in English.  <br/> |
|FileExtension  <br/> |The extension of a file; for example, docx, one, pptx, or xlsx.  <br/> |fileextension:xlsx  <br/> |All Excel files (Excel 2007 and later)  <br/> |
|FileName  <br/> |The name of a file.  <br/> |filename:"marketing plan"  <br/> filename:estimate  <br/> |The first example returns files with the exact phrase "marketing plan" in the title. The second example returns files with the word "estimate" in the file name.  <br/> |
|LastModifiedTime  <br/> |The date that an item was last changed.  <br/> |lastmodifiedtime\>=05/01/2016  <br/> lastmodifiedtime\>=05/10/2016 AND lastmodifiedtime\<=06/1/2016  <br/> |The first example returns items that were changed on or after May 1, 2016. The second example returns items changed between May 1, 2016 and June 1, 2016.  <br/> |
|ModifiedBy  <br/> |The person who last changed an item. Be sure to use the user's display name for this property.  <br/> |modifiedby:"Garth Fort"  <br/> |All items that were last changed by Garth Fort.  <br/> |
|Path  <br/> |The path (URL) of a specific folder on a SharePoint or OneDrive for Business site. If you use this property, be sure to search the site that the specified folder is located in.  <br/> To return items located in subfolders in the folder that you specify for the path property, you have to add /\* to the URL of the specified folder; for example,  `path: https://contoso.sharepoint.com/Shared Documents/*`.  <br/> > [!NOTE]> Using the  `Path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results. Use a different site property in your search query to search for media files in OneDrive folders.           For more information about searching for the Path property and using a script to obtain the path URLs for folders on a specific site, see [Use Content Search in Office 365 for targeted collections](use-content-search-for-targeted-collections.md).  <br/> |path:https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private  <br/> path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/\*" AND filename:confidential  <br/> |The first example returns all items in the specified OneDrive for Business folder. The second example returns documents in the specified site folder (and all subfolders) that contain the word "confidential" in the file name.  <br/> |
|SharedWithUsersOWSUser  <br/> |Documents that have been shared with the specified user and displayed on the **Shared with me** page in the user's OneDrive for Business site. These are documents that have been explicitly shared with the specified user by other people in your organization. When you export documents that match a search query that uses the SharedWithUsersOWSUser property, the documents are exported from the original content location of the person who shared the document with the specified user. For more details, see [Searching for site content shared within your organization](keyword-queries-and-search-conditions.md#internal).  <br/> |sharedwithusersowsuser:garthf  <br/> sharedwithusersowsuser:"garthf@contoso.com"  <br/> |Both examples return all internal documents that have been explicitly shared with Garth Fort and that appear on the **Shared with me** page in Garth Fort's OneDrive for Business account.  <br/> |
|Site  <br/> |The URL of a site or group of sites in your organization.  <br/> |site:https://contoso-my.sharepoint.com  <br/> site:https://contoso.sharepoint.com/sites/teams  <br/> |The first example returns items from the OneDrive for Business sites for all users in the organization. The second example returns items from all team sites.  <br/> |
|Size  <br/> |The size of an item, in bytes.  <br/> |size\>=1  <br/> size:1..10000  <br/> |The first example returns items larger than 1 byte. The second example returns items from 1 through 10,000 bytes in size.  <br/> |
|Title  <br/> |The title of the document. The Title property is metadata that's specified in Microsoft Office documents. It's different from the file name of the document.  <br/> |title:"communication plan"  <br/> |Any document that contains the phrase "communication plan" in the Title metadata property of an Office document.  <br/> |
   
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Searchable contact properties
<a name="contactproperties"> </a>

The following table lists the contact properties that are indexed and that you can search for using Content Search. These are the properties that are available for users to configure for the contacts (also called personal contacts) that are located in the personal address book of a user's mailbox. To search for contacts, you can select the mailboxes to search and then use one or more contact properties in the keyword query.
  
> [!TIP]
> To search for values that contain spaces, use double quotation marks ("??") to contain the phrase; for example,  `businessaddress:"123 Main Street"`. 
  
|**Property????????????????????**|**Property description**|
|:-----|:-----|
|BusinessAddress  <br/> |The address in the **Business Address** property. The property is also called the **Work** address on the contact properties page.  <br/> |
|BusinessPhone  <br/> |The phone number in any of the **Business Phone** number properties.  <br/> |
|CompanyName  <br/> |The name in the **Company** property.  <br/> |
|Department  <br/> |The name in the **Department** property.  <br/> |
|DisplayName  <br/> |The display name of the contact. This is the name in the **Full Name** property of the contact.  <br/> |
|EmailAddress  <br/> |The address for any email address property for the contact. Note that users can add multiple email addresses for a contact. Using this property would return contacts that match any of the contact's email addresses.  <br/> |
|FileAs  <br/> |The **File as** property. This property is used to specify how the contact is listed in the user's contact list. For example, a contact could be listed as  *FirstName,LastName*  or  *LastName,FirstName*  .  <br/> |
|GivenName  <br/> |The name in the **First Name** property.  <br/> |
|HomeAddress  <br/> |The address in any of the **Home** address properties.  <br/> |
|HomePhone  <br/> |The phone number in any of the **Home** phone number properties.  <br/> |
|IMAddress  <br/> |The IM address property, which is typically an email address used for instant messaging.  <br/> |
|MiddleName  <br/> |The name in the **Middle** name property.  <br/> |
|MobilePhone  <br/> |The phone number in the **Mobile** phone number property.  <br/> |
|Nickname  <br/> |The name in the **Nickname** property.  <br/> |
|OfficeLocation  <br/> |The value in **Office** or **Office location** property.  <br/> |
|OtherAddress  <br/> |The value for the **Other** address property.  <br/> |
|Surname  <br/> |The name in the **Last** name property.  <br/> |
|Title  <br/> |The title in the **Job title** property.  <br/> |
   
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Searchable sensitive data types
<a name="dlptypes"> </a>

You can use the Content Search feature in the Security &amp; Compliance Center to search for sensitive data, such as credit card numbers or social security numbers, that is stored in documents on SharePoint and OneDrive for Business sites. You can do this by using the  `SensitiveType` property and the name of a sensitive information type in a keyword query. For example, the query  `SensitiveType:"Credit Card Number"` returns documents that contain a credit card number. The query  `SensitiveType:"U.S. Social Security Number (SSN)"` returns documents that contains a U.S. social security number. To see a list of the sensitive data types that you can search for, go to **Classifications** \> **Sensitive information types** in the Security &amp; Compliance Center. Or you can use the **Get-DlpSensitiveInformationType** cmdlet in the Security &amp; Compliance Center PowerShell to display a list of sensitive information types. 
  
You can also use the  `SensitiveType` property to search for the name of a custom sensitive information type that you (or another administrator) created for your organization. Note that you can use the **Publisher** column on the **Sensitive information types** page in the Security &amp; Compliance Center (or the **Publisher** property in PowerShell) to differentiate between built-in and custom sensitive information types. For more information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).
  
For more information about creating queries using the  `SensitiveType` property, see [Form a query to find sensitive data stored on sites](form-a-query-to-find-sensitive-data-stored-on-sites.md).
  
## Search operators
<a name="searchoperators"> </a>

Boolean search operators, such as **AND**, **OR**, and **NOT**, help you define more-precise searches by including or excluding specific words in the search query. Other techniques, such as using property operators (such as \>= or ..), quotation marks, parentheses, and wildcards, help you refine a search query. The following table lists the operators that you can use to narrow or broaden search results. 
  
|**Operator**|**Usage**|**Description**|
|:-----|:-----|:-----|
|AND  <br/> |keyword1 AND keyword2  <br/> |Returns items that include all of the specified keywords or  `property:value` expressions. For example,  `from:"Ann Beebe" AND subject:northwind` would return all messages sent by Ann Beebe that contained the word northwind in the subject line. <sup>2</sup> <br/> |
|+  <br/> |keyword1??+keyword2??+keyword3  <br/> |Returns items that contain  *either*  `keyword2` or  `keyword3` *and*  that also contain  `keyword1`. Therefore, this example is equivalent to the query  `(keyword2 OR keyword3) AND keyword1`.  <br/> Note that the query  `keyword1 + keyword2` (with a space after the **+** symbol) isn't the same as using the ** AND ** operator. This query would be equivalent to  `"keyword1 + keyword2"` and return items with the exact phase  `"keyword1 + keyword2"`.  <br/> |
|OR  <br/> |keyword1 OR keyword2  <br/> |Returns items that include one or more of the specified keywords or  `property:value` expressions. <sup>2</sup> <br/> |
|NOT  <br/> |keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> NOT kind:im  <br/> |Excludes items specified by a keyword or a  `property:value` expression. In the second example excludes messages sent by Ann Beebe. The third example excludes any instant messaging conversations, such as Skype for Business conversations that are saved to the Conversation History mailbox folder. <sup>2</sup> <br/> |
|-  <br/> |keyword1 -keyword2  <br/> |The same as the **NOT** operator. So this query returns items that contain  `keyword1` and would exclude items that contain  `keyword2`.  <br/> |
|NEAR  <br/> |keyword1 NEAR(n) keyword2  <br/> |Returns items with words that are near each other, where n equals the number of words apart. For example,  `best NEAR(5) worst` returns any item where the word "worst" is within five words of "best". If no number is specified, the default distance is eight words. <sup>2</sup> <br/> |
|ONEAR  <br/> |keyword1 ONEAR(n) keyword2  <br/> |Similar to **NEAR**, but returns items with words that are near each other in the specified order. For example,  `best ONEAR(5) worst` returns any item where the word "best" occurs before the word "worst" and the two words are within five words of each other. If no number is specified, the default distance is eight words. <sup>2</sup> <br/> > [!NOTE]> The **ONEAR** operator isn't supported when searching mailboxes; it only works when searching SharePoint and OneDrive for Business sites. If you're searching mailboxes and sites in the same search and the query includes the **ONEAR** operator, the search will return mailbox items as if you were using the **NEAR** operator. In other words, the search returns items in which the specified words are near each other regardless of the order in which the words occur.           |
|:  <br/> |property:value  <br/> |The colon (:) in the  `property:value` syntax specifies that the value of the property being searched for contains the specified value. For example,  `recipients:garthf@contoso.com` returns any message sent to garthf@contoso.com.  <br/> |
|=  <br/> |property=value  <br/> |The same as the **:** operator.  <br/> |
|\<  <br/> |property\<value  <br/> |Denotes that the property being searched is less than the specified value. <sup>1</sup> <br/> |
|\>  <br/> |property\>value  <br/> |Denotes that the property being searched is greater than the specified value.<sup>1</sup> <br/> |
|\<=  <br/> |property\<=value  <br/> |Denotes that the property being searched is less than or equal to a specific value.<sup>1</sup> <br/> |
|\>=  <br/> |property\>=value  <br/> |Denotes that the property being searched is greater than or equal to a specific value.<sup>1</sup> <br/> |
|..  <br/> |property:value1..value2  <br/> |Denotes that the property being searched is greater than or equal to value1 and less than or equal to value2.<sup>1</sup> <br/> |
|"??"  <br/> |"fair value"  <br/> subject:"Quarterly Financials"  <br/> |Use double quotation marks ("??") to search for an exact phrase or term in keyword and  `property:value` search queries.  <br/> |
|\*  <br/> |cat\*  <br/> subject:set\*  <br/> |Prefix wildcard searches (where the asterisk is placed at the end of a word) match for zero or more characters in keywords or  `property:value` queries. For example,  `title:set*` returns documents that contain the word set, setup, and setting (and other words that start with "set") in the document title.  <br/> > [!NOTE]> You can use only prefix wildcard searches; for example, **cat\*** or **set\***. Suffix searches ( **\*cat** ), infix searches ( **c\*t** ), and substring searches ( **\*cat\*** ) are not supported.           |
|(??)  <br/> |(fair OR free) AND (from:contoso.com)  <br/> (IPO OR initial) AND (stock OR shares)  <br/> (quarterly financials)  <br/> |Parentheses group together Boolean phrases,  `property:value` items, and keywords. For example,  `(quarterly financials)` returns items that contain the words quarterly and financials.  <br/> |
   
> [!NOTE]
> <sup>1</sup>??????Use this operator for properties that have date or numeric values. > <sup>2</sup>??????Boolean search operators must be uppercase; for example, **AND**. If you use a lowercase operator, such as **and**, it will be treated as a keyword in the search query. 
  
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Search conditions
<a name="conditions"> </a>

You can add conditions to a search query to narrow a search and return a more refined set of results. Each condition adds a clause to the KQL search query that is created and run when you start the search.
  
[Conditions for common properties](keyword-queries-and-search-conditions.md#commonproperties)
  
[Conditions for mail properties](keyword-queries-and-search-conditions.md#mailproperties)
  
[Conditions for document properties](keyword-queries-and-search-conditions.md#documentproperties)
  
[Operators used with conditions](keyword-queries-and-search-conditions.md#ConditionLogic)
  
[Guidelines for using conditions](keyword-queries-and-search-conditions.md#conditionguidelines)
  
[Examples of using conditions in search queries](keyword-queries-and-search-conditions.md#conditionexamples)
  
### Conditions for common properties
<a name="commonproperties"> </a>

Create a condition using common properties when searching mailboxes and sites in the same search. The following table lists the available properties to use when adding a condition.
  
|**Condition**|**Description**|
|:-----|:-----|
|Date  <br/> |For email, the date a message was received by a recipient or sent by the sender. For documents, the date a document was last modified.  <br/> |
|Sender/Author  <br/> |For email, the person who sent a message. For documents, the person cited in the author field from Office documents. You can type more than one name, separated by commas. Two or more values are logically connected by the **OR** operator.  <br/> |
|Size (in bytes)  <br/> |For both email and documents, the size of the item (in bytes).  <br/> |
|Subject/Title  <br/> |For email, the text in the subject line of a message. For documents, the title of the document. As previously explained, the Title property is metadata specified in Microsoft Office documents. You can type the name of more than one subject/title, separated by commas. Two or more values are logically connected by the **OR** operator.  <br/> |
|Compliance tag  <br/> |For both email and documents, labels that have been assigned to messages and documents automatically by label policies or labels that have been manually assigned by users. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. You can type part of the label name and use a wildcard or type the complete label name. For more information, see [Overview of labels in Office 365](labels.md).  <br/> |
   
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
### Conditions for mail properties
<a name="mailproperties"> </a>

Create a condition using mail properties when searching mailboxes or public folders. The following table lists the email properties that you can use for a condition. Note that these properties are a subset of the email properties that were previously described; these descriptions are repeated for your convenience.
  
|**Condition**|**Description**|
|:-----|:-----|
|Message kind  <br/> | The message type to search. This is the same property as the Kind email property. Possible values:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  microsoftteams  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail  <br/> |
|Participants  <br/> |All the people fields in an email message; these fields are From, To, CC, and BCC.  <br/> |
|Type  <br/> |The message class property for an email item. This is the same property as the ItemClass email property. It's also a multi-value condition. So to select multiple message classes, hold the **CTRL** key and then click two or more message classes in the drop-down list that you want to add to the condition. Each message class that you select in the list will be logically connected by the **OR** operator in the corresponding search query.  <br/> For a list of the message classes (and their corresponding message class ID) that are used by Exchange and that you can select in the **Message class** list, see [Item Types and Message Classes](https://go.microsoft.com/fwlink/?linkid=848143).  <br/> |
|Received  <br/> |The date that an email message was received by a recipient. This is the same property as the Received email property.  <br/> |
|Recipients  <br/> |The person an email message was sent to. This is the same property as the To email property.  <br/> |
|Sender  <br/> |The sender of an email message.  <br/> |
|Sent  <br/> |The date that an email message was sent by the sender. This is the same property as the Sent email property.  <br/> |
|Subject  <br/> |The text in the subject line of an email message.  <br/> |
|To  <br/> |The recipient of an email message.  <br/> |
   
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
### Conditions for document properties
<a name="documentproperties"> </a>

Create a condition using document properties when searching for documents on SharePoint and OneDrive for Business sites. The following table lists the document properties that you can use for a condition. Note that these properties are a subset of the site properties that were previously described; these descriptions are repeated for your convenience.
  
|**Condition**|**Description**|
|:-----|:-----|
|Author  <br/> |The author field from Office documents, which persists if a document is copied. For example, if a user creates a document and the emails it to someone else who then uploads it to SharePoint, the document will still retain the original author.  <br/> |
|Title  <br/> |The title of the document. The Title property is metadata that's specified in Office documents. It's different than the file name of the document.  <br/> |
|Created  <br/> |The date that a document is created.  <br/> |
|Last modified  <br/> |The date that a document was last changed.  <br/> |
|File type  <br/> |The extension of a file; for example, docx, one, pptx, or xlsx. This is the same property as the FileExtension site property.  <br/> |
   
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
### Operators used with conditions
<a name="ConditionLogic"> </a>

When you add a condition, you can select an operator that is relevant to type of property for the condition. The following table describes the operators that are used with conditions and lists the equivalent that is used in the search query.
  
|**Operator**|**Query equivalent**|**Description**|
|:-----|:-----|:-----|
|After  <br/> |property\>date  <br/> |Used with date conditions. Returns items that were sent, received, or modified after the specified date.  <br/> |
|Before  <br/> |property\<date  <br/> |Used with date conditions. Returns items that were sent, received, or modified before the specified date.  <br/> |
|Between  <br/> |date..date  <br/> |Use with date and size conditions. When used with a date condition, returns items there were sent, received, or modified within the specified date range. When used with a size condition, returns items whose size is within the specified range.  <br/> |
|Contains any of  <br/> |(property:value) OR (property:value)  <br/> |Used with conditions for properties that specify a string value. Returns items that contain any part of one or more specified string values.  <br/> |
|Doesn't contain any of  <br/> |-property:value  <br/> NOT property:value  <br/> |Used with conditions for properties that specify a string value. Returns items that don't contain any part of the specified string value.  <br/> |
|Doesn't equal any of  <br/> |-property=value  <br/> NOT property=value  <br/> |Used with conditions for properties that specify a string value. Returns items that don't contain the specific string.  <br/> |
|Equals  <br/> |Size=value  <br/> |Returns items that are equal to the specified size.<sup>1</sup> <br/> |
|Equals any of  <br/> |(property=value) OR (property=value)  <br/> |Used with conditions for properties that specify a string value. Returns items that are an exact match of one or more specified string values.  <br/> |
|Greater  <br/> |Size\>value  <br/> |Returns items where the specified property is greater than the specified value.<sup>1</sup> <br/> |
|Greater or equal  <br/> |Size\>=value  <br/> |Returns items where the specified property is greater than or equal to the specified value.<sup>1</sup> <br/> |
|Less  <br/> |Size\<value  <br/> |Returns items that are greater than or equal to the specific value.<sup>1</sup> <br/> |
|Less or equal  <br/> |Size\<=value  <br/> |Returns items that are greater than or equal to the specific value.<sup>1</sup> <br/> |
|Not equal  <br/> |Size\<\>value  <br/> |Returns items that don't equal the specified size.<sup>1</sup> <br/> |
   
> [!NOTE]
> <sup>1</sup>??????This operator is available only for conditions that use the Size property. 
  
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
### Guidelines for using conditions
<a name="conditionguidelines"> </a>

Keep the following in mind when using search conditions.
  
- A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be included in the results. This is how conditions help to narrow your results. 
    
- If you add two or more unique conditions to a search query (conditions that specify different properties), those conditions are logically connected by the **AND** operator. That means only items that satisfy all the conditions (in addition to any keyword query) are returned. 
    
- If you add more than one condition for the same property, those conditions are logically connected by the **OR** operator. That means items that satisfy the keyword query and any one of the conditions are returned. So, groups of the same conditions are connected to each other by the **OR** operator and then sets of unique conditions are connected by the **AND** operator. 
    
- If you add multiple values (separated by commas or semi-colons) to a single condition, those values are connected by the **OR** operator. That means items are returned if they contain any of the specified values for the property in the condition. 
    
- The search query that is created by using the keywords box and conditions is displayed on the **Search** page, in the details pane for the selected search. In a query, everything to the right of the notation  `(c:c)` indicates conditions that are added to the query. 
    
- Conditions only add properties to the search query; the don't add operators. This is why the query displayed in the detail pane doesn't show operators to the right of the  `(c:c)` notation. KQL adds the logical operators (according to the previously explained rules) when the executing the query. 
    
- You can use the drag and drop control to re-sequence the order of conditions. Just click on the control for a condition and move it up or down.
    
- As previously explained, some condition properties allow you to type multiple values. Each value is logically connected by the **OR** operator. This results in the same logic as having multiple instances of the same condition, where each has a single value. The following illustrations shows an example of a single condition with multiple values and an example of multiple conditions (for the same property) with a single value. Both examples result in the same query:  `(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![One condition with multiple values](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Multiple search conditions for the same property](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> If a condition accepts multiple values, we recommend that you use a single condition and specify multiple values (separated by commas or semi-colons). This helps ensure the query logic that's applied is what you intend. 
  
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
### Examples of using conditions in search queries
<a name="conditionexamples"> </a>

The following examples show the GUI-based version of a search query with conditions, the search query syntax that is displayed in the details pane of the selected search (which is also returned by the **Get-ComplianceSearch** cmdlet), and the logic of the corresponding KQL query. 
  
### Example 1
<a name="conditionexamples"> </a>

This example returns documents on SharePoint and OneDrive for Business sites that contain a credit card number and were last modified before January 1, 2016.
  
 **GUI**
  
![First example of search conditions](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Search query syntax**
  
 `SensitiveType:"Credit Card Number"???(c:c)??????(lastmodifiedtime<2016-01-01)???`
  
 **Search query logic**
  
 `SensitiveType:"Credit Card Number"??? AND (lastmodifiedtime<2016-01-01)`
  
### Example 2
<a name="conditionexamples"> </a>

This example returns email items or documents that contain the keyword "report", that were sent or created before April 1, 2105, and that contain the word "northwind" in the subject field of email messages or in the title property of documents. The query excludes Web pages that meet the other search criteria.
  
 **GUI**
  
![Second example of search conditions](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Search query syntax**
  
 `report???(c:c)??????(date<2016-04-01)??????(subjecttitle:"northwind")??????(-filetype="aspx")???`
  
 **Search query logic**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
### Example 3
<a name="conditionexamples"> </a>

This example returns email messages or calendar meetings that were sent between 12/1/2016 and 11/30/2016 and that contain words that start with "phone" or "smartphone".
  
 **GUI**
  
![Third example of search conditions](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Search query syntax**
  
 `phone* OR smartphone*???(c:c)??????(sent=2016-12-01..2016-11-30)??????(kind="email")??????(kind="meetings")???`
  
 **Search query logic**
  
 `phone* OR smartphone*??? AND ??????(sent=2016-12-01..2016-11-30)??? AND (??????(kind="email") OR ??????(kind="meetings"))`
  
[Search conditions](keyword-queries-and-search-conditions.md#conditions)
  
## Searching for site content shared with external users
<a name="external"> </a>

You can also use the Content Search feature in the Security &amp; Compliance Center to search for documents stored on SharePoint and OneDrive for Business sites that have been shared with people outside of your organization. This can help you identify sensitive or proprietary information that's being shared outside your organization. You can do this by using the  `ViewableByExternalUsers` property in a keyword query. This property will return documents or sites that have been shared with external users by using one of the following sharing methods: 
  
- A sharing invitation that requires users to sign in to your organization as an authenticated user.
    
- An anonymous guest link, which allows anyone with this link to access the resource without having to be authenticated.
    
Here are some examples:
  
- The query  `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` will return all items that have been shared with people outside your organization and contain a credit card number. 
    
- The query  `ViewableByExternalUsers:true AND ContentType:document AND Site:https://contoso.sharepoint.com/Sites/Teams` will return a list of documents on all team sites in the organization that have been shared with external users. 
    
> [!TIP]
> A search query such as  `ViewableByExternalUsers:true AND ContentType:document` might return a lot of .aspx files in the search results. To eliminate these (or other types of files), you can use the  `FileExtension` property to exclude specific file types; for example  `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
What is considered content that is shared with people outside your organization? Documents in your organization's SharePoint and OneDrive for Business sites that are shared by sending a sharing invitations or that are shared in public locations. For example, the following user activities result in content that is viewable by external users:
  
- A user shares a file or folder with a person outside your organization.
    
- A user creates and sends a link to a shared file to a person outside your organization. This link allows the external user to view (or edit) the file.
    
- A user sends a sharing invitation or a guest link to a person outside your organization to view (or edit) a shared file.
    
### Issues using the ViewableByExternalUsers property

While the  `ViewableByExternalUsers` property represents the status of whether a document or site is shared with external users, there are some caveats to what this property does and doesn???t reflect. In the following scenarios, the value of the  `ViewableByExternalUsers` property won't be updated, and the results of a Content Search query that uses this property may be inaccurate. 
  
- Changes to sharing policy, such as turning off external sharing for a site or for the organization. The property will still show previously shared documents as being externally accessible even though external access might have been revoked.
    
- Changes to group membership, such as adding or removing external users to Office 365 Groups or Office 365 security groups. The property won't automatically be updated for items the group has access to.
    
- Sending sharing invitations to external users where the recipient hasn't accepted the invitation, and therefore doesn't yet have access to the content.
    
In these scenarios, the  `ViewableByExternalUsers` property won't reflect the current sharing status until the site or document library is re-crawled and re-indexed. 
  
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Searching for site content shared within your organization
<a name="internal"> </a>

As previously explained, you can use the  `SharedWithUsersOWSUser` property so search for documents that have been shared between people in your organization. When a person shares a file (or folder) with another user inside your organization, a link to the shared file appears on the **Shared with me** page in the OneDrive for Business account of the person who the file was shared with. For example, to search for the documents that have been shared with Sara Davis, you can use the query  `SharedWithUsersOWSUser:"sarad@contoso.com"`. If you export the results of this search, the original documents (located in the content location of the person who shared the documents with Sara) will be downloaded.
  
Note that documents must be explicitly shared with a specific user to be returned in search results when using the  `SharedWithUsersOWSUser` property. For example, when a person shares a document in their OneDrive account, they have the option to share it with anyone (inside or outside the organization), share it only with people inside the organization, or share it with a specific person. Here's a screenshot of the **Share** window in OneDrive, that shows the three sharing options. 
  
![Only files shared with specific people will be returned by a searcj query that uses the SharedWithUsersOWSUser property](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Only documents that are shared by using the third option (shared with **Specific people**) will be returned by a search query that uses the  `SharedWithUsersOWSUser` property. 
  
[Return to top](keyword-queries-and-search-conditions.md#top)
  
## Search tips and tricks
<a name="searchtips"> </a>

- Keyword searches are not case sensitive. For example, **cat** and ** CAT ** return the same results. 
    
- The Boolean operators **AND**, **OR**, **NOT**, **NEAR**, and **ONEAR** must be uppercase. 
    
- A space between two keywords or two  `property:value` expressions is the same as using **AND**. For example,  `from:"Sara Davis" subject:reorganization` returns all messages sent by Sara Davis that contain the word reorganization in the subject line. 
    
- Use syntax that matches the  `property:value` format. Values are not case-sensitive, and they can???t have a space after the operator. If there is a space, your intended value will just be a full-text search. For example **to: pilarp** searches for "pilarp" as a keyword, rather than for messages that were sent to pilarp. 
    
- When searching a recipient property, such as To, From, Cc, or Recipients, you can use an SMTP address, alias, or display name to denote a recipient. For example, you can use pilarp@contoso.com, pilarp, or "Pilar Pinilla".
    
- You can use only prefix wildcard searches; for example, **cat\*** or **set\***. Suffix searches ( **\*cat** ), infix searches ( **c\*t** ), and substring searches ( **\*cat\*** ) are not supported. 
    
- When searching a property, use double quotation marks ("??") if the search value consists of multiple words. For example **subject:budget Q1** returns messages that contain **budget** in the in the subject line and that contain **Q1** anywhere in the message or in any of the message properties. Using **subject:"budget Q1"** returns all messages that contain **budget Q1** anywhere in the subject line. 
    
- To exclude content marked with a certain property value from your search results, place a minus sign (-) before the name of the property. For example, **-from:"Sara Davis"** will exclude any messages sent by Sara Davis. 
    
[Return to top](keyword-queries-and-search-conditions.md#top)
  

