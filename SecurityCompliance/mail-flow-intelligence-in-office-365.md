---
title: "Mail flow intelligence in Office 365"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: "Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. "
---

# Mail flow intelligence in Office 365
  
Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).
  
Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.
  
 **Contents**
  
- [Error code: 450 4.4.312 DNS query failed](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [Error code: 450 4.4.315 Connection timed out](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [Error code: 450 4.4.316 Connection refused](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [Error code: 450 4.4.317 Cannot connect to remote server](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [Error code: 450 4.4.318 Connection was closed abruptly](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [Error code: 450 4.7.320 Certificate validation failed](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## Error code: 450 4.4.312 DNS query failed
<a name="ErrorCode44312"> </a>

Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:
  
- There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).
    
- Your domain has recently expired, so the MX record can't be retrieved.
    
- Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.
    
You need to fix the DNS issue by working with your DNS hosting service.
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Error code: 450 4.4.315 Connection timed out
<a name="ErrorCode44315"> </a>

Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:
  
- Your on-premises messaging server is down.
    
- There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.
    
Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Error code: 450 4.4.316 Connection refused
<a name="ErrorCode44316"> </a>

Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..
  
- If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).
    
- If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue: 
    
  - Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.png), or disable the connector by clicking **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png) and unchecking **Turn it on**.
    
  - Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).
    
    **Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.
    
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Error code: 450 4.4.317 Cannot connect to remote server
<a name="ErrorCode44317"> </a>

Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:
  
- The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.
    
- The connector is configured to require TLS, but the destination messaging server doesn't support TLS.
    
Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Error code: 450 4.4.318 Connection was closed abruptly
<a name="ErrorCode44318"> </a>

Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:
  
- Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.
    
- Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.
    
- There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.
    
Find out which scenario applies to you, and make the necessary corrections.
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Error code: 450 4.7.320 Certificate validation failed
<a name="ErrorCode47320"> </a>

Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:
  
- Certificate expired
    
- Certificate subject mismatch
    
- Certificate is no longer valid
    
Please fix the certificate or the connector so that queued messages in Office 365can be delivered.
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  
## Other error codes
<a name="sectionSection6"> </a>

Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error. 
  
If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.
  

