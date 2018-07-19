---
title: "Office 365 Certificate Chains"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: "Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see Plan for third-party SSL certificates for Office 365. The following certificate information applies to all worldwide and national cloud instances of Office 365."
---

# Office 365 Certificate Chains

Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.
  

|**Certificate type**|**P7b download**|**CRL Endpoints**|**OCSP Endpoints**|**AIA Endpoints**|
|:-----|:-----|:-----|:-----|:-----|
|[Publicly Trusted Root Certificates​](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[Office 365 Root Certificate Bundle (P7B)​​](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |crl.globalsign.net  <br/> www.d-trust.net  <br/> |N/A  <br/> |N/A  <br/> |
|[Publicly Trusted Intermediate Certificates​](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[Office 365 Intermediate Certificate Bundle​ (​P7B)](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)​​  <br/> |cdp1.public-trust.com  <br/> crl.cnnic.cn  <br/> crl.entrust.net  <br/> crl.globalsign.com  <br/> crl.globalsign.net  <br/> crl.identrust.com  <br/> crl.thawte.com  <br/> crl3.digicert.com  <br/> crl4.digicert.com  <br/> s1.symcb.com  <br/> www.d-trust.net  <br/> |isrg.trustid.ocsp.identrust.com  <br/> ocsp.digicert.com  <br/> ocsp.entrust.net  <br/> ocsp.globalsign.com  <br/> ocsp.omniroot.com  <br/> ocsp.startssl.com  <br/> ocsp.thawte.com  <br/> ocsp2.globalsign.com  <br/> ocspcnnicroot.cnnic.cn  <br/> root-c3-ca2-2009.ocsp.d-trust.net  <br/> root-c3-ca2-ev-2009.ocsp.d-trust.net  <br/> s2.symcb.com  <br/> |aia.startssl.com  <br/> apps.identrust.com  <br/> cacert.omniroot.com  <br/> www.cnnic.cn  <br/> |
   
Expand the root and intermediate sections below to see additional details about the certificate providers.
  
## Office 365 Root Certificate Details
<a name="RootCerts"> </a>

 **Baltimore Cybe​rTrust Root**
  
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **CNNIC ROOT**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **DigiCert Global Root CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **DigiCert High Assurance EV Root CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **D-TRUST Root Class 3 CA 2 2009**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
   
 **D-TRUST Root Class 3 CA 2 EV 2009**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
   
 **DST Root CA X3**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **Entrust Root Certification Authority - G2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **Entrust.net Certification Authority (2048)**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
   
 **GlobalSign Root CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **thawte Primary Root CA - G3**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
 **VeriSign Class 3 Public Primary Certification Authority - G5**
  
||
|:-----|
|**Subject**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
   
## Office 365 Intermediate Certificate Details
<a name="IntermediateCerts"> </a>

 **CNNIC SHA256 SSL**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**AIA URLs**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **D-TRUST SSL Class 3 CA 1 2009**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Subject Alternative Name**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **D-TRUST SSL Class 3 CA 1 EV 2009**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Subject Alternative Name**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **DigiCert Cloud Services CA-1**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **DigiCert SHA2 High Assurance Server CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **DigiCert SHA2 Secure Server CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Entrust Certification Authority - L1C**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Entrust Certification Authority - L1K**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **GlobalSign Extended Validation CA - SHA256 - G2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **GlobalSign Extended Validation CA - SHA256 - G3**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **GlobalSign Organization Validation CA - SHA256 - G2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **GlobalSign Organization Validation CA - SHA256 - G2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Let's Encrypt Authority X3**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**AIA URLs**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Microsoft IT TLS CA 1**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Microsoft IT TLS CA 2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Microsoft IT TLS CA 4**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Microsoft IT TLS CA 5**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Symantec Class 3 EV SSL CA - G3**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Subject Alternative Name**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Symantec Class 3 Secure Server CA - G4**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Subject Alternative Name**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **thawte SHA256 SSL CA**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Subject Alternative Name**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
 **Verizon Akamai SureServer CA G14-SHA2**
  
||
|:-----|
|**Subject**|
|:-----|
|**Issuer**|
|:-----|
|**Serial Number**|
|:-----|
|**Public Key Length**|
|:-----|
|**Signature Algorithm**|
|:-----|
|**Validity Not Before**|
|:-----|
|**Validity Not After**|
|:-----|
|**Subject Key Identifier**|
|:-----|
|**Authority Key Identifier**|
|:-----|
|**Thumbprint (SHA-1)**|
|:-----|
|**Thumbprint (SHA-256)**|
|:-----|
|**Pin (SHA-256)**|
|:-----|
|**AIA URLs**|
|:-----|
|**CRL URLs**|
|:-----|
|**OCSP URLs**|
|:-----|
   
## Additional certificate paths
<a name="IntermediateCerts"> </a>

The following include legacy certificates that aren't included above and will be merged with the list above over time.
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


