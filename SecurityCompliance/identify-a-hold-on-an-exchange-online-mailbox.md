---
title: "How to identify the type of hold placed on an Exchange Online mailbox"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128

---

# How to identify the type of hold placed on an Exchange Online mailbox

### Litigation Hold

The  *LitigationHoldEnabled*  property is set to  `True`.
  
||
|:-----|
|
```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

|
   
> [!TIP]
> If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line. 
  
### Office 365 retention policies

Run the following command to get information about any organization-wide Office 365 retention policies. 
  
||
|:-----|
|
```
Get-OrganizationConfig | FL InPlaceHolds
```

|
   
If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.
  
### eDiscovery holds

Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold. 
  
||
|:-----|
|
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

|
   
||
|:-----|
|
```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

|
   
||
|:-----|
|
```
$CaseHold.Name
```

|
   
Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder. 
  
|**Hold type**|**Example value**|**How to identify the hold**|
|:-----|:-----|:-----|
|Litigation Hold  <br/> | `True` <br/> |The  *LitigationHoldEnabled*  property is set to  `True`.  <br/> |
|In-Place Hold  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  <br/> You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.  <br/> |
| Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> or  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  <br/> To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/> ||
|:-----|
|
```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

|
   
Be sure to remove the  `mbx` or  `skp` prefix when you run this command.  <br/> |
|Organization-wide Office 365 retention policies in the Security &amp; Compliance Center  <br/> |No value  <br/> or  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)  <br/> |Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.  <br/> To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/> ||
|:-----|
|
```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

|
   
Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery case hold in the Security &amp; Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  <br/> You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands.  <br/> ||
|:-----|
|
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

|
   
||
|:-----|
|
```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

|
   
|
   

