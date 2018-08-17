---
title: "What the sensitive information types look for"
ms.author: stephow
author: stephow
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- 'ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: "Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes 80 sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type."
---

# What the sensitive information types look for

Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.
  
## ABA Routing Number

### Format

9 digits which may be in a formatted or unformatted pattern

### Pattern

Formatted:
- Four digits beginning with 0, 1, 2, 3, 6, 7, or 8
- A hyphen
- Four digits
- A hyphen
- A digit

Unformatted:
9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8 

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_aba_routing finds content that matches the pattern.
- A keyword from Keyword_ABA_Routing is found.

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### Keywords


|Keyword_ABA_Routing  |
|---------|
|aba</br>aba #</br>aba routing #</br>aba routing number</br>aba#</br>abarouting#</br>aba number</br>abaroutingnumber</br>american bank association routing #</br>american bank association routing number</br>americanbankassociationrouting#</br>americanbankassociationroutingnumber</br>bank routing number</br>bankrouting#</br>bankroutingnumber</br>routing transit number</br>RTN  |

   
## Argentina National Identity (DNI) Number

### Format

Eight digits separated by periods

### Pattern

Eight digits:
- Two digits
- A period
- Three digits
- A period
- Three digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_argentina_national_id finds content that matches the pattern.
- A keyword from Keyword_argentina_national_id is found.

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### Keywords


|Keyword_argentina_national_id  |
|---------|
|Argentina National Identity number</br>Identity</br>Identification National Identity Card</br>DNI</br>NIC National Registry of Persons</br>Documento Nacional de Identidad</br>Registro Nacional de las Personas</br>Identidad</br>Identificación      |

   
## Australia Bank Account Number

### Format

6-10 digits with or without a bank state branch number

### Pattern

Account number is 6-10 digits.
Australia bank state branch number:
- Three digits 
- A hyphen 
- Three digits

### Checksum

No

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_australia_bank_account_number finds content that matches the pattern..
- A keyword from Keyword_australia_bank_account_number is found.
- The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_australia_bank_account_number finds content that matches the pattern..
- A keyword from Keyword_australia_bank_account_number is found.

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### Keywords
   
   
## Australia Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Australia Medical Account Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Australia Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Australia Tax File Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Belgium National Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Brazil CPF Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Brazil Legal Entity Number (CNPJ)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Brazil National ID Card (RG)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Canada Bank Account Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Canada Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Canada Health Service Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
      
## Canada Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Canada Personal Health Identification Number (PHIN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Canada Social Insurance Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Chile Identity Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## China Resident Identity Card (PRC) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Credit Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Croatia Identity Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Croatia Personal Identification (OIB) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Czech National Identity Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Denmark Personal Identification Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Drug Enforcement Agency (DEA) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## EU Debit Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## EU Driver's License Number

To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).
  
## EU National Identification Number

To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).
  
## EU Passport Number

To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).
  
## EU Social Security Number or Equivalent ID

To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).
  
## EU Tax Identification Number

To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).
  
## Finland National ID

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Finland Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## France Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## France National ID Card (CNI)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## France Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
      
## France Social Security Number (INSEE)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## German Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## German Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Germany Identity Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Greece National ID Card

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Hong Kong Identity Card (HKID) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## India Permanent Account Number (PAN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## India Unique Identification (Aadhaar) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Indonesia Identity Card (KTP) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## International Banking Account Number (IBAN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## IP Address

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## International Classification of Diseases (ICD-10-CM)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## International Classification of Diseases (ICD-9-CM)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Ireland Personal Public Service (PPS) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Israel Bank Account Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Israel National ID

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Italy Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Japan Bank Account Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Japan Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Japan Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Japan Resident Registration Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Japan Social Insurance Number (SIN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Malaysia ID Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Netherlands Citizen's Service (BSN) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## New Zealand Ministry of Health Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Norway Identification Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Philippines Unified Multi-Purpose ID Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Poland Identity Card

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Poland National ID (PESEL)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Poland Passport

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Portugal Citizen Card Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Saudi Arabia National ID

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Singapore National Registration Identity Card (NRIC) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## South Africa Identification Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## South Korea Resident Registration Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Spain Social Security Number (SSN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Sweden National ID

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Sweden Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## SWIFT Code

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

   
## Taiwan National ID

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## Taiwan Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## Taiwan Resident Certificate (ARC/TARC) Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.K. Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.K. Electoral Roll Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.K. National Health Service Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## U.K. National Insurance Number (NINO)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## U.S. / U.K. Passport Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.S. Bank Account Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.S. Driver's License Number

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
   
## U.S. Individual Taxpayer Identification Number (ITIN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   
## U.S. Social Security Number (SSN)

### Format

### Pattern

### Checksum

### Definition

### Keywords
   

