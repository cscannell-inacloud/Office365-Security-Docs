---
title: "Technical reference details about encryption in Office 365"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: "View technical details about encyption in Office 365."
---

# Technical reference details about encryption in Office 365

Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md). This article also provides details about planned deprecations.
  
- If you're looking for overview information, see [Encryption in Office 365](encryption.md).
    
- If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).
    
## Microsoft Office 365 certificate ownership and management

You do not need to purchase or maintain certificates for Office 365 because Microsoft uses its own certificates.
  
## Current encryption standards and planned deprecations

In order to continue to provide best-in-class encryption for Office 365, Microsoft regularly reviews supported encryption standards. Sometimes, we need to deprecate old standards as they become out of date and therefore less secure. This topic describes currently supported cipher suites and other standards as well as details about planned deprecations.
  
## Versions of TLS supported by Office 365

Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. Office 365 supports several versions of TLS, including:
  
- TLS version 1.2 (TLS 1.2)
    
- TLS version 1.1 (TLS 1.1)
    
- TLS version 1.0 (TLS 1.0)
    
 TLS 1.0 and TLS 1.1 support will be deprecated October 31, 2018. See [Deprecating support for TLS 1.0 and 1.1 and what this means for you](technical-reference-details-about-encryption.md#TLS11and12deprecation) for more information. 
  
## Deprecating support for TLS 1.0 and 1.1 and what this means for you
<a name="TLS11and12deprecation"> </a>

Important changes are coming to supported encryption options for Office 365. As of October 31, 2018, Office 365 will no longer support the use of TLS 1.0 or 1.1 for communication to Office 365. Once Office 365 deprecates support for these protocols, all communication to and from Office 365 servers will need to use TLS 1.2. For information about how this impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365). Servers and clients communicating with O365 after this date must support TLS 1.2.
  
## Deprecating support for 3DES
<a name="TLS11and12deprecation"> </a>

As of October 31, 2018, Office 365 will no longer support the use of 3DES cipher suites for communication to Office 365. More specifically, Office 365 will no longer support the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Clients and servers communicating with O365 after this date must support at least one of the more secure ciphers listed in this topic (see [TLS cipher suites supported by Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## Deprecating SHA-1 certificate support in Office 365
<a name="TLS11and12deprecation"> </a>

As of June 2016, Office 365 no longer accepts a SHA-1 certificate for outbound or inbound connections. If you are currently using a certificate with SHA-1 in the certificate chain, you will need to update the chain to use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm.
  
## Deprecating RC4 support in Office 365
<a name="TLS11and12deprecation"> </a>

In July 2015, support for the following RC4 cipher suites was discontinued:
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## Deprecating Secure Sockets Layer (SSL) 3.0 support in Office 365
<a name="TLS11and12deprecation"> </a>

Starting December 1, 2014, Office 365 began disabling support for Secure Sockets Layer (SSL) 3.0, the predecessor to TLS. For more information, see [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx). For instructions on how to ensure clients are using TLS 1.0 or higher and to disable SSL 3.0, see [Protecting SSL 3.0 vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).
  
## TLS cipher suites supported by Office 365
<a name="TLSCipherSuites"> </a>

A cipher suite is a collection of encryption algorithms that TLS uses to establish secure connections. Cipher suites supported by Office 365 are listed in the following table in order of strength with the strongest cipher suite listed first. When Office 365 receives a connection request, Office 365 first attempts to connect using the topmost cipher suite then, if unsuccessful, tries the second cipher suite in the list and so on down the list. When Office 365 sends a connection request to another server or to a client, it's up to the receiving server or client to choose the cipher suite or whether TLS will be used at all.
  
|**Protocols**|**Cipher suite name**|**Key exchange algorithm/Strength**|**Perfect Forward Secrecy support**|**Authentication algorithm/Strength**|**Cipher/Strength**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Yes  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Yes  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Yes  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Yes  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_3DES_EDE_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |3DES/192  <br/> |
   
## Related topics
<a name="TLSCipherSuites"> </a>

[Encryption in Office 365](encryption.md)
  
[Set up encryption in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

