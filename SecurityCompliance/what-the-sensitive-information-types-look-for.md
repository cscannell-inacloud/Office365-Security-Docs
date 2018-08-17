---
title: "What the sensitive information types look for"
ms.author: stephow
author: stephow-MSFT
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

#### Keyword_ABA_Routing

- aba
- aba #
- aba routing #
- aba routing number
- aba#
- abarouting#
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bank routing number
- bankrouting#
- bankroutingnumber
- routing transit number
- RTN 
   
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

#### Keyword_argentina_national_id

- Argentina National Identity number 
- Identity 
- Identification National Identity Card 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
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

#### Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

   
## Australia Driver's License Number

### Format

Nine letters and digits

### Pattern

Nine letters and digits: 

- Two digits or letters (not case sensitive) 
- Two digits 
- Five digits or letters (not case sensitive)

OR

- 1-2 optional letters (not case sensitive) 
- 4-9 digits

OR

- Nine digits or letters (not case sensitive)

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.
- A keyword from Keyword_australia_drivers_license_number is found.
- No keyword from Keyword_australia_drivers_license_number_exclusions is found.

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- sydney nsw
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic#
- DriverLics#
- DriverLicence#
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic#
- DriversLics#
- DriversLicence#
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic#
- Driver'Lics#
- Driver'Licence#
- Driver'Licences#
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicence#
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense#
- DriverLicenses#
- Driver License#
- Driver Licenses#
- DriversLicense#
- DriversLicenses#
- Drivers License#
- Drivers Licenses#
- Driver'License#
- Driver'Licenses#
- Driver' License#
- Driver' Licenses#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's License#
- Driver's Licenses#
   
## Australia Medical Account Number

### Format

10-11 digits

### Pattern

10-11 digits:
- First digit is in the range 2-6
- Ninth digit is a check digit
- Tenth digit is the issue digit
- Eleventh digit (optional) is the individual number

### Checksum

Yes

### Definition

A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_australian_medical_account_number finds content that matches the pattern.
- A keyword from Keyword_Australia_Medical_Account_Number is found.
- The checksum passes.

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_australian_medical_account_number finds content that matches the pattern.
- The checksum passes.

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## Australia Passport Number

### Format

A letter followed by seven digits

### Pattern

A letter (not case sensitive) followed by seven digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_australia_passport_number finds content that matches the pattern.
- A keyword from Keyword_passport or Keyword_australia_passport_number is found.

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### Keywords

#### Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passport#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

#### Keyword_australia_passport_number

- passport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- visa
- national identity card
- passport number
- travel document
- issuing authority
   
## Australia Tax File Number

### Format

8-9 digits

### Pattern

8-9 digits typically presented with spaces as follows:
- Three digits 
- An optional space 
- Three digits 
- An optional space 
- 2-3 digits where the last digit is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_australian_tax_file_number finds content that matches the pattern.
- No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.
- The checksum passes.

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number

#### Keyword_number_exclusions

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999
   
## Belgium National Number

### Format

11 digits plus delimiters

### Pattern

11 digits plus delimiters:
- Six digits and two periods in the format YY.MM.DD for date of birth 
- A hyphen 
- Three sequential digits (odd for males, even for females) 
- A period 
- Two digits that are a check digit

### Checksum

Yes

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_belgium_national_number finds content that matches the pattern.
- A keyword from Keyword_belgium_national_number is found.
- The checksum passes.

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_belgium_national_number

- Identity
- Registration
- Identification 
- ID 
- Identiteitskaart
- Registratie nummer 
- Identificatie nummer 
- Identiteit
- Registratie
- Identificatie 
- Carte d’identité 
- numéro d'immatriculation
- numéro d'identification
- identité 
- inscription 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## Brazil CPF Number

### Format

11 digits that include a check digit and can be formatted or unformatted

### Pattern

Formatted:
- Three digits 
- A period 
- Three digits 
- A period 
- Three digits 
- A hyphen 
- Two digits which are check digits

Unformatted:
- 11 digits where the last two digits are check digits

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_cpf finds content that matches the pattern.
- A keyword from Keyword_brazil_cpf is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_cpf finds content that matches the pattern.
- The checksum passes.

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

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
   

