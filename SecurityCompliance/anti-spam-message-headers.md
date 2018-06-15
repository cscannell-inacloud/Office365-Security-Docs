---
title: "Anti-spam message headers"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db

description: "In this articleX-Forefront-Antispam-Report message header fieldsX-Microsoft-Antispam message header fields Authentication-results message header"
---

# Anti-spam message headers

 **In this article**
  
[X-Forefront-Antispam-Report message header fields](#sectionSection0.md)
  
[X-Microsoft-Antispam message header fields ](#sectionSection1.md)
  
[Authentication-results message header](#sectionSection2.md)
  
When Exchange Online Protection scans an inbound email message it inserts the **X-Forefront-Antispam-Report** header into each message. The fields in this header can help provide administrators with information about the message and about how it was processed. The fields in the **X-Microsoft-Antispam** header provide additional information about bulk mail and phishing. In addition to these two headers, Exchange Online Protection also inserts email authentication results for each message it processes in the **Authentication-results** header. 
  
> [!TIP]
> For information about how to view an email message header in various email clients, see [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). You can copy and paste the contents of the message header into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha) tool. When you select a message in the quarantine in the Exchange admin center, the **View message header** link also easily lets you copy and paste the message header text into the tool. Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header. 
  
## X-Forefront-Antispam-Report message header fields
<a name="sectionSection0"> </a>

After accessing the message header information, search for **X-Forefront-Antispam-Report** and then look for these fields. Other fields in this header are used exclusively by the Microsoft anti-spam team for diagnostic purposes. 
  
|||
|:-----|:-----|
|**Header field** <br/> |**Description** <br/> |
|CIP: [IP address]  <br/> |The connecting IP address. You may want to specify this IP address when creating an IP Allow list or an IP Block list in the connection filter. For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).  <br/> |
|CTRY  <br/> |The country from which the message connected to the service. This is determined by the connecting IP address, which may not be the same as the originating sending IP address.  <br/> |
|LANG  <br/> |The language in which the message was written, as specified by the country code (for example, ru_RU for Russian).  <br/> |
|SCL  <br/> |The Spam Confidence Level (SCL) value of the message. For more information about interpreting these values, see [Spam confidence levels](spam-confidence-levels.md).  <br/> |
|PCL  <br/> |The Phishing Confidence Level (PCL) value of the message. See [PCL](anti-spam-message-headers.md#PCL) for more information about PCL values.  <br/> |
|SRV:BULK  <br/> |The message was identified as a bulk email message. If the **Block all bulk email messages advanced spam filtering option** is enabled, it will be marked as spam. If it is not enabled, it will only be marked as spam if the rest of the filtering rules determine that the message is spam.  <br/> |
|SFV:SFE  <br/> |Filtering was skipped and the message was let through because it was sent from an address on an individual's safe sender list.  <br/> |
|SFV:BLK  <br/> |Filtering was skipped and the message was blocked because it was sent from an address on an individual's blocked sender list.  <br/> **Tip:** For more information about how end users can create safe and blocked sender lists, see [Block or allow (junk email settings)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (OWA) and [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).  <br/> |
|IPV:CAL  <br/> |The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.  <br/> |
|IPV:NLI  <br/> |The IP address was not listed on any IP reputation list.  <br/> |
|SFV:SPM  <br/> |The message was marked as spam by the content filter.  <br/> |
|SFV:SKS  <br/> |The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.  <br/> |
|SFV:SKA  <br/> |The message skipped filtering and was delivered to the inbox because it matched an allow list in the spam filter policy, such as the **Sender allow** list.  <br/> |
|SFV:SKB  <br/> |The message was marked as spam because it matched a block list in the spam filter policy, such as the **Sender block** list.  <br/> |
|SFV:SKN  <br/> |The message was marked as non-spam prior to being processed by the content filter. This includes messages where the message matched a transport rule to automatically mark it as non-spam and bypass all additional filtering.  <br/> |
|SFV:SKI  <br/> |Similar to SFV:SKN, the message skipped filtering for another reason such as being intra-organizational email within a tenant.  <br/> |
|SFV:SKQ  <br/> |The message was released from the quarantine and was sent to the intended recipients.  <br/> |
|SFV:NSPM  <br/> |The message was marked as non-spam and was sent to the intended recipients.  <br/> |
|H: [helostring]  <br/> |The HELO or EHLO string of the connecting mail server.  <br/> |
|PTR: [ReverseDNS]  <br/> |The PTR record, or pointer record, of the sending IP address, also known as the reverse DNS address.  <br/> |
|SFTY  <br/> | The message was identified as phishing and will also be marked with one of the following values:  <br/>  9.1 - Default value. The message contains a phishing URL, may contain other phishing content, or may have been marked as phishing by another mail filter such as an on-premises version of Exchange Server before relaying the message to Office 365.  <br/>  9.11 - Message failed anti-spoofing checks where the sending domain in the From: header is the same as, or aligns with, or is part of the same organization as the receiving domain.  <br/>  9.21 - Message failed anti-spoofing checks and the sending domain in the From: header does not authenticate. Used in combination with CompAuth (see Authentication-Results).  <br/>  9.22 - Same as 9.21, except that the user has a safe sender that was overridden.  <br/>  9.23 - Same as 9.22, except that the organization has an allowed sender or domain that was overridden.  <br/>  9.24 - Same as 9.23, except that the user has an Exchange mail flow rule that was overridden.  <br/> |
|X-CustomSpam: [ASFOption]  <br/> |The message matched an advanced spam filtering  option. For example, **X-CustomSpam: Image links to remote sites** denotes that the **Image links to remote sites** ASF option was matched. To find out which X-header text is added for each specific ASF option, see [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md).  <br/> |
   
## X-Microsoft-Antispam message header fields
<a name="sectionSection1"> </a>

The following table describes useful fields in the **X-Microsoft-Antispam** message header. Other fields in this header are used exclusively by the Microsoft anti-spam team for diagnostic purposes. 
  
|||
|:-----|:-----|
|**Header field** <br/> |**Description** <br/> |
|BCL  <br/> |The Bulk Complaint Level (BCL) of the message. For more information, see [Bulk Complaint Level values](bulk-complaint-level-values.md).  <br/> |
|PCL  <br/> | The Phishing Confidence Level (PCL) of the message, which indicates whether it's a phishing message.  <br/>  This status can be returned as one of the following numerical values:  <br/> **0-3** The message's content isn't likely to be phishing.  <br/> **4-8** The message's content is likely to be phishing.  <br/> **-9990** (Exchange Online Protection only) The message's content is likely to be phishing.  <br/>  The values are used to determine what action your email client takes on messages. For example, Microsoft Office Outlook uses the PCL stamp to block the content of suspicious messages. For more information about phishing, and how Outlook processes phishing messages, see [Turn on or off links in email messages](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).  <br/> |
   
## Authentication-results message header
<a name="sectionSection2"> </a>

The results of checks against SPF, DKIM, and DMARC are recorded, or stamped, by Office 365 in the **Authentication-results** message header when our mail servers receive an email message. 
  
### check stamp syntax and examples
<a name="referenceSPFstamp"> </a>

The following syntax examples show a portion of the text "stamp" that Office 365 applies to the message header for each email that undergoes an email authentication check when it is received by our mail servers. The stamp is added to the **Authentication-Results** header. 
  
 **Syntax: SPF check stamp**
  
For SPF, the following syntax applies.
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **Examples: SPF check stamp**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com

```

 **Syntax: DKIM check stamp**
  
For DKIM, the following syntax applies.
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **Examples: DKIM check stamp**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **Syntax: DMARC check stamp**
  
For DMARC, the following syntax applies.
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **Examples: DMARC check stamp**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### Authentication-results message header fields used by Office 365 email authentication
<a name="referenceSPFstamp"> </a>

This table describes the fields and possible values for each email authentication check.
  
|**Header field**|**Description**|
|:-----|:-----|
|spf  <br/> | Describes the results of the SPF check for the message. Possible values include:  <br/> **pass (IP address)** indicates the SPF check for the message passed and includes the sender's IP address. The client is authorized to send or relay email on behalf of the sender's domain.  <br/> **fail (IP address)** indicates the SPF check for the message failed and includes the sender's IP address. This is sometimes called hard fail.  <br/> **softfail (reason)** indicates that the SPF record has designated the host as not being allowed to send but is in transition.  <br/> **neutral** indicates that the SPF record has explicitly stated that it is not asserting whether the IP address is authorized.  <br/> **none** indicates that the domain does not have an SPF record or the SPF record does not evaluate to a result.  <br/> **temperror** indicates that an error has occurred that may be temporary in nature, for example, a DNS error. Trying again later might succeed without any administrator action.  <br/> **permerror** indicates that a permanent error has occurred. This happens when, for example, the domain has a badly formatted SPF record.  <br/> |
|smtp.mailfrom  <br/> |Contains the source domain from which the message was sent. Any errors about this email message will be sent to the postmaster or the entity responsible for the domain. This is sometimes called the 5321.MailFrom address or the reverse-path address on the message envelope.  <br/> |
|dkim  <br/> | Describes the results of the DKIM check for the message. Possible values include:  <br/> **pass** indicates the DKIM check for the message passed.  <br/> **fail (reason)** indicates the DKIM check for the message failed and why. For example, if the message was not signed or the signature was not verified.  <br/> **none** indicates that the message was not signed. This may or may not indicate that the domain has a DKIM record or the DKIM record does not evaluate to a result, only that this message was not signed.  <br/> |
|header.d  <br/> |Domain identified in the DKIM signature if any. This is the domain that's queried for the public key.  <br/> |
|dmarc  <br/> | Describes the results of the DMARC check for the message. Possible values include:  <br/> **pass** indicates the DMARC check for the message passed.  <br/> **fail** indicates the DMARC check for the message failed.  <br/> **bestguesspass** indicates that no DMARC TXT record for the domain exists, but if one had existed, the DMARC check for the message would have passed. This is because the domain in the 5321.MailFrom address matches the domain in the 5322.From address.  <br/> **none** indicates that no DKIM TXT record exists for the sending domain in DNS.  <br/> |
|action  <br/> | Indicates the action taken by the spam filter based on the results of the DMARC check. For example:  <br/> **permerror** A permanent error occurred during DMARC evaluation, such as encountering an incorrectly formed DMARC TXT record in DNS. Attempting to resend this message isn't likely to end with a different result. Instead, you may need to contact the domain's owner in order to resolve the issue.  <br/> **temperror** A temporary error occurred during DMARC evaluation. You may be able to request that the sender resend the message later in order to process the email properly.  <br/> **oreject** or **o.reject** Stands for override reject. In this case Office 365 uses this action when it receives a message that fails the DMARC check from a domain whose DMARC TXT record has a policy of p=reject. Instead of deleting or rejecting the message, Office 365 marks the message as spam. For more information on why Office 365 is configured this way, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).  <br/> **pct.quarantine** Indicates that a percentage less than 100% of messages that do not pass DMARC will be delivered anyway. This means that the message failed DMARC and the policy was set to quarantine, but the pct field was not set to 100% and the system randomly determined not to apply the DMARC action, as per the specified domain's policy.  <br/> **pct.reject** Indicates that a percentage less than 100% of messages that do not pass DMARC will be delivered anyway. This means that the message failed DMARC and the policy was set to reject, but the pct field was not set to 100% and the system randomly determined not to apply the DMARC action, as per the specified domain's policy.  <br/> |
|header.from  <br/> |The domain of the From address in the email message header. This is sometimes called the 5322.From address.  <br/> |
|compauth  <br/> |Composite authentication result. Used by Office 365 to combine multiple types of authentication such as SPF, DKIM, DMARC, or any other part of the message to determine whether or not the message is authenticated. Uses the From: domain as the basis of evaluation.  <br/> |
|reason  <br/> | The reason the composite authentication passed or failed. The value for the reason is made up of three digits:  <br/>  000 - The message explicitly failed authentication. For example, the message received a DMARC fail with an action of quarantine or reject.  <br/>  001 - The message implicitly failed authentication, and the sending domain did not publish authentication policies. For example, a DMARC policy of p=none.  <br/>  1xx - The message passed authentication. The second two digits are internal codes used by Office 365.  <br/>  2xx - The message soft-passed authentication. The second two digits are internal codes used by Office 365.  <br/>  3xx - The message was not checked for composite authentication.  <br/>  4xx - The message bypassed composite authentication. The second two digits are internal codes used by Office 365.  <br/> |
   
||
|:-----|
|![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning. |
   

