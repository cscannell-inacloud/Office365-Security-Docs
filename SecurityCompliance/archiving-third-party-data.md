---
title: "Archiving third-party data in Office 365"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: 
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc

description: "Administrators can import third-party data from  social media platforms, instant messaging platforms, and document collaboration platforms to mailboxes in your Office 365 organization. This lets you archive data from Facebook, Twitter and data sources in Office 365. Then you can appply Office 365 compliance features (such as legal hold, content search, and retention policies) to third-party data."
---

# Archiving third-party data in Office 365

Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following: 
  
- **Social** Twitter, Facebook, Yammer, and LinkedIn 
    
- **Instant messaging** Yahoo Messenger, GoogleTalk, and Cisco Jabber 
    
- **Document collaboration** Box and DropBox 
    
- **Vertical industries** Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg) 
    
- **SMS/text messaging** BlackBerry 
    
After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.
  
Here's an overview of the process and the steps necessary to import third-party data to Office 365.
  
[How the third-party data import process works](archiving-third-party-data.md#overview)
  
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
[Step 2: Create and configure a third-party data mailbox in Office 365](archiving-third-party-data.md#step2)
  
[Step 3: Configure user mailboxes for third-party data](archiving-third-party-data.md#step3)
  
[Step 4: Provide your partner with information](archiving-third-party-data.md#step4)
  
See the [More information](archiving-third-party-data.md#moreinfo) see for additional information about importing third-party data to Office 365. 
  
## How the third-party data import process works
<a name="overview"> </a>

The following illustration and description explain how the third-party data import process works.
  
![How the third-party data import process works](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.
    
2. The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](archiving-third-party-data.md#moreinfo) section for a description of the message format schema. 
    
3. Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.
    
4. Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:
    
1. **Items that have a user ID that corresponds to an Office 365 user account** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder. 
    
2. **Items that don't have a user ID that corresponds to an Office 365 user account** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration. 
    
[Return to top](archiving-third-party-data.md#top)
  
## Step 1: Find a third-party data partner
<a name="step1"> </a>

A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages. 
  
The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.
  
[17a-4 LLC](archiving-third-party-data.md#seventeenA4LCC)
  
[Actiance](archiving-third-party-data.md#actiance)
  
[ArchiveSocial](archiving-third-party-data.md#archivesocial)
  
[Globanet](archiving-third-party-data.md#globanet)
  
[OpenText](archiving-third-party-data.md#opentext)
  
[Verba](archiving-third-party-data.md#verba)
  
### 17a-4 LLC
<a name="seventeenA4LCC"> </a>

17a-4 LLC supports the following third-party data sources:
  
- BlackBerry
    
- Bloomberg Data Streams
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs Data Streams
    
- OpenText
    
- Oracle/ATG 'click-to-call' Live Help
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- SQL Databases
    
- Squawker
    
- Thomson Reuters Eikon Messenger
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
### Actiance
<a name="actiance"> </a>

[Actiance](https://www.actiance.com) supports the following third-party data sources: 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- AOL with Pivot client
    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Mail
    
- CellTrust
    
- Chat Import
    
- Chat Real Time Logging and Policy
    
- Chatter
    
- Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Collaboration Import
    
- Collaboration Real Time Logging
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- IM Import
    
- IM Real Time Logging and Policy
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6, v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
### ArchiveSocial
<a name="archivesocial"> </a>

[ ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
### Globanet
<a name="globanet"> </a>

[Globanet](https://www.globanet.com) supports the following third-party data sources: 
  
- AOL with Pivot Client 
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)
    
- Custom delimited text files
    
- Custom XML files
    
- Facebook (corporate fan pages)
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP
    
- Microsoft OneDrive for Business
    
- Microsoft UC (Unified Communications)
    
- Microsoft Yammer
    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter
    
- Skype for Business, versions 2007 R2 - 2016 (on-premises)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
### OpenText
<a name="opentext"> </a>

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
### Verba
<a name="verba"> </a>

[Verba](https://www.verba.com) supports the following third-party data sources: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE Voice
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- Skype for Business / Lync IM
    
- Skype for Business / Lync Video
    
- Skype for Business / Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop Computer Screen
    
[Step 1: Find a third-party data partner](archiving-third-party-data.md#step1)
  
## Step 2: Create and configure a third-party data mailbox in Office 365
<a name="step2"> </a>

Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.
  
 **Complete these tasks in the Office 365 admin center**
  
1. Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.
    
2. Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4. 
  
 **Complete these tasks in the Exchange admin center**
  
1. Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:
    
  ```
  Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
  ```

2. Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Enable the following compliance-related Office 365 features for the third-party data mailbox:
    
1. Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.
    
2. Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. See one of the following: 
    
  - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
  - [Overview of retention policies in Office 365](retention-policies.md)
    
    Placing this mailbox on hold will preserve third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. 
    
3. Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox. 
    
[Return to top](archiving-third-party-data.md#top)
  
## Step 3: Configure user mailboxes for third-party data
<a name="step3"> </a>

The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.
  
1. Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).
    
2. Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics: 
    
  - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
  - [Overview of retention policies in Office 365](retention-policies.md)
    
    As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.
    
[Return to top](archiving-third-party-data.md#top)
  
## Step 4: Provide your partner with information
<a name="step4"> </a>

The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox. 
  
- The endpoint used to connect to the Azure service in Office 365:
    
||
|:-----|
|
```
  https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
```

|
   
- The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.
    
[Return to top](archiving-third-party-data.md#top)
  
## More information
<a name="moreinfo"> </a>

- As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.
    
|**Message property**|**Mandatory?**|**Description**|**Example value**|
|:-----|:-----|:-----|:-----|
|**FROM** <br/> |Yes  <br/> |The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  <br/> The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:  <br/> ||
|:-----|
|
```
  <ResponseMessages>
        <CreateItemResponseMessage ResponseClass="Error">
              <MessageText>One or more messages in the Request failed to be delivered to either From or Sender email address. 
              You will need to resend your entire Request. Error: The request failed. 
              The remote server returned an error: (401) Unauthorized. 
              </MessageText>
              …
        </CreateItemResponseMessage>
  </ResponseMessages>
```

|
   
| `bob@contoso.com` <br/> |
|**TO** <br/> |Yes  <br/> |The user who received an item, if applicable for an item in the data source.  <br/> | `bob@contoso.com` <br/> |
|**SUBJECT** <br/> |No  <br/> |The subject from the source item.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
|**DATE** <br/> |Yes  <br/> |The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.  <br/> | `01 NOV 2015` <br/> |
|**BODY** <br/> |No  <br/> |The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
|**ATTACHMENT** <br/> |No  <br/> |If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  <br/> | `image.gif` <br/> |
|**MESSAGECLASS** <br/> |Yes  <br/> | This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  <br/>  `Source` Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.  <br/>  `Event` Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  <br/>  One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:
    
||
|:-----|
|
```
  HTTP/1.1 200 OK
  Content-Type: text/xml; charset=utf-8
  Server: Microsoft-IIS/8.5
  x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
  X-AspNet-Version: 4.0.30319
  X-Powered-By: ASP.NET
  Date: Tue, 02 Feb 2016 22:55:33 GMT
  
```

|
   
- You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. . 
    
  - ** `kind:externaldata`** Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.
    
  - ** `itemclass:ipm.externaldata.<third-party data type>*`** Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`. For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](https://go.microsoft.com/fwlink/p/?linkid=832871).
    
    For more information about using Content Search and creating keyword search queries, see:
    
  - [Run a Content Search in the Office 365 Security &amp; Compliance Center](https://go.microsoft.com/fwlink/p/?LinkId=615211)
    
  - [Keyword queries and search conditions for Content Search](https://go.microsoft.com/fwlink/p/?linkid=828045)
    
[Return to top](archiving-third-party-data.md#top)
  

