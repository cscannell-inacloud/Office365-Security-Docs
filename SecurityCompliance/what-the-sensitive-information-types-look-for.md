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

#### Keyword_brazil_cpf

- CPF
- Identification
- Registration
- Revenue
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## Brazil Legal Entity Number (CNPJ)

### Format

14 digits that include a registration number, branch number, and check digits, plus delimiters

### Pattern
14 digits, plus delimiters:
- Two digits 
- A period 
- Three digits 
- A period 
- Three digits (these first eight digits are the registration number) 
- A forward slash 
- Four-digit branch number 
- A hyphen 
- Two digits which are check digits

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_cnpj finds content that matches the pattern.
- A keyword from Keyword_brazil_cnpj is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_cnpj finds content that matches the pattern.
- The checksum passes.

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- National Registry of Legal Entities 
- Taxpayers Registry 
- Legal entity 
- Legal entities 
- Registration Status 
- Business 
- Company
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 
   
## Brazil National ID Card (RG)

### Format

Registro Geral (old format): Nine digits

Registro de Identidade (RIC) (new format): 11 digits

### Pattern

Registro Geral (old format):
- Two digits 
- A period 
- Three digits 
- A period 
- Three digits 
- A hyphen 
- One digit which is a check digit

Registro de Identidade (RIC) (new format):
- 10 digits 
- A hyphen 
- One digit which is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_rg finds content that matches the pattern.
- A keyword from Keyword_brazil_rg is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_brazil_rg finds content that matches the pattern.
- The checksum passes.

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_brazil_rg

Cédula de identidade
identity card
national id 
número de rregistro
registro de Iidentidade 
registro geral
RG (this keyword is case sensitive) 
RIC (this keyword is case sensitive) 
   
## Canada Bank Account Number

### Format

Seven or twelve digits

### Pattern

A Canada Bank Account Number is seven or twelve digits.

A Canada bank account transit number is:
- Five digits 
- A hyphen 
- Three digits
OR
- A zero "0" 
- Eight digits

### Checksum

No

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_canada_bank_account_number finds content that matches the pattern.
- A keyword from Keyword_canada_bank_account_number is found.
- The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_canada_bank_account_number finds content that matches the pattern.
- A keyword from Keyword_canada_bank_account_number is found.

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### Keywords

#### Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit
   
## Canada Driver's License Number

### Format

Varies by province

### Pattern

Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_[province_name]_drivers_license_number finds content that matches the pattern.
- A keyword from Keyword_[province_name]_drivers_license_name is found.
- A keyword from Keyword_canada_drivers_license is found.

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### Keywords

#### Keyword_[province_name]_drivers_license_name

- The province abbreviation, for example AB
- The province name, for example Alberta

#### Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identification 
- DL#
- DLS# 
- CDL# 
- CDLS# 
- DriverLic# 
- DriverLics# 
- DriverLicense# 
- DriverLicenses# 
- DriverLicence# 
- DriverLicences# 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic# 
- DriversLics# 
- DriversLicense# 
- DriversLicenses# 
- DriversLicence# 
- DriversLicences# 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver'Lic# 
- Driver'Lics# 
- Driver'License# 
- Driver'Licenses# 
- Driver'Licence# 
- Driver'Licences# 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic# 
- Driver'sLics# 
- Driver'sLicense# 
- Driver'sLicenses# 
- Driver'sLicence# 
- Driver'sLicences# 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- id# 
- ids# 
- idcard card# 
- idcard cards# 
- idcard# 
- identification card# 
- identification cards# 
- identification# 
   
## Canada Health Service Number

### Format

10 digits

### Pattern

10 digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_canada_health_service_number finds content that matches the pattern.
- A keyword from Keyword_canada_health_service_number is found.

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- disability
      
## Canada Passport Number

### Format

Two uppercase letters followed by six digits

### Pattern

Two uppercase letters followed by six digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_canada_passport_number finds content that matches the pattern.
- A keyword from Keyword_canada_passport_number or Keyword_passport is found.

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

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
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °
   
## Canada Personal Health Identification Number (PHIN)

### Format

Nine digits

### Pattern

Nine digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
The regular expression Regex_canada_phin finds content that matches the pattern.
At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Ontario
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Canada
   
## Canada Social Insurance Number

### Format

Nine digits with optional hyphens or spaces

### Pattern

Formatted:
- Three digits 
- A hyphen or space 
- Three digits 
- A hyphen or space 
- Three digits

Unformatted: Nine digits

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_canadian_sin finds content that matches the pattern.
- At least two of any combination of the following:
    - A keyword from Keyword_sin is found.
    - A keyword from Keyword_sin_collaborative is found.
    - The function Func_eu_date finds a date in the right date format.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_unformatted_canadian_sin finds content that matches the pattern.
- A keyword from Keyword_sin is found.
- The checksum passes.

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- sins 
- ssn 
- ssns 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- sin# 
- soc ins 
- social ins 

#### Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Birthdate 
- Birthday 
- Date of Birth 
   
## Chile Identity Card Number

### Format

7-8 digits plus delimiters a check digit or letter

### Pattern

7-8 digits plus delimiters:
- 1-2 digits 
- A period 
- Three digits 
- A period 
- Three digits 
- A dash 
- One digit or letter (not case sensitive) which is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_chile_id_card finds content that matches the pattern.
- A keyword from Keyword_chile_id_card is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_chile_id_card finds content that matches the pattern.
- The checksum passes.

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_chile_id_card

- National Identification Number 
- Identity card 
- ID 
- Identification 
- Rol Único Nacional 
- RUN 
- Rol Único Tributario 
- RUT 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## China Resident Identity Card (PRC) Number

### Format

18 digits

### Pattern

18 digits:
- Six digits which are an address code 
- Eight digits in the form YYYYMMDD which are the date of birth 
- Three digits which are an order code 
- One digit which is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_china_resident_id finds content that matches the pattern.
- A keyword from Keyword_china_resident_id is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_china_resident_id finds content that matches the pattern.
- The checksum passes.

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### Keywords

### Keyword_china_resident_id

- Resident Identity Card 
- PRC 
- National Identification Card 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 
   
## Credit Card Number

### Format

16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.

### Pattern

Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.

### Checksum

Yes, the Luhn checksum

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_credit_card finds content that matches the pattern.
- One of the following is true:
    - A keyword from Keyword_cc_verification is found.
    - A keyword from Keyword_cc_name is found.
    - The function Func_expiration_date finds a date in the right date format.
- The checksum passes.

A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_credit_card finds content that matches the pattern.
- The checksum passes.

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- cod. seguranca cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- Venc 

#### Keyword_cc_name

- amex
- american express
- americanexpress
- Visa
- mastercard
- master card
- mc 
- mastercards
- master cards
- diner's Club
- diners club
- dinersclub
- discover card
- discovercard
- discover cards
- JCB
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc#
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr 
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- no. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão 
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- no. do cartão
- no. do cartao 
   
## Croatia Identity Card Number

### Format

Nine digits

### Pattern

Nine consecutive digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_croatia_id_card finds content that matches the pattern.
- A keyword from Keyword_croatia_id_card is found.

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_croatia_id_card

- Croatian identity card
- Osobna iskaznica

   
## Croatia Personal Identification (OIB) Number

### Format

10 digits

### Pattern

10 digits:
- Six digits in the form DDMMYY which are the date of birth 
- Four digits where the final digit is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_croatia_oib_number finds content that matches the pattern.
- A keyword from Keyword_croatia_oib_number is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_croatia_oib_number finds content that matches the pattern.
- The checksum passes.

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_croatia_oib_number

- Personal Identification Number
- Osobni identifikacijski broj 
- OIB 

   
## Czech National Identity Card Number

### Format

10 digits containing a forward slash

### Pattern

10 digits:
- Six digits which are the date of birth 
- A forward slash 
- Four digits where the final digit is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
The function Func_czech_id_card finds content that matches the pattern.
A keyword from Keyword_czech_id_card is found.
The checksum passes.

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### Keywords

- Keyword_czech_id_card
- Czech national identity card
- Občanský průka
   
## Denmark Personal Identification Number

### Format

10 digits containing a hyphen

### Pattern

10 digits:
- Six digits in the format DDMMYY which are the date of birth 
- A hyphen 
- Four digits where the final digit is a check digit

### Checksum

Yes

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
The regular expression Regex_denmark_id finds content that matches the pattern.
A keyword from Keyword_denmark_id is found.
The checksum passes.

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_denmark_id

- Personal Identification Number
- CPR
- Det Centrale Personregister
- Personnummer
   
## Drug Enforcement Agency (DEA) Number

### Format

Two letters followed by seven digits

### Pattern

Pattern must include all of the following:
- One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code 
- One letter (not case sensitive), which is the first letter of the registrant's last name 
- Seven digits, the last of which is the check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_dea_number finds content that matches the pattern.
- The checksum passes.

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### Keywords

None

   
## EU Debit Card Number

### Format

16 digits

### Pattern

Very complex and robust pattern

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_eu_debit_card finds content that matches the pattern.
- At least one of the following is true:
    - A keyword from Keyword_eu_debit_card is found.
    - A keyword from Keyword_card_terms_dict is found.
    - A keyword from Keyword_card_security_terms_dict is found.
    - A keyword from Keyword_card_expiration_terms_dict is found.
    - The function Func_expiration_date finds a date in the right date format.
- The checksum passes.

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### Keywords

#### Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- cc# 

#### Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- amex 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- cardholder 
- cardholders 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- ccn 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- creditcard 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- dinersclub 
- discover 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- jcb 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- master card 
- master cards 
- mastercard 
- mastercards 
- mc 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- no. de tarjeta 
- no. do cartao 
- no. do cartão 
- nr carta 
- nr. carta 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- nº. do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- solo 
- supporti di scheda 
- supporto di scheda 
- switch 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-pay 
- visa 
- visa plus 
- visa electron 
- visto 
- visum 
- vpay   

#### Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- cid 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- cod. seg 
- cod. seguranca 
- cod. segurança 
- cod. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- código 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- no. dell'edizione 
- no. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- prufziffer 
- prüfziffer 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### Keyword_card_expiration_terms_dict

- ablauf 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp date 
- exp datum 
- expiration 
- expire 
- expires 
- expiry 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- valor 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 
   
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

Six digits plus a character indicating a century plus three digits plus a check digit

### Pattern

Pattern must include all of the following:
- Six digits in the format format DDMMYY which are a date of birth 
- Century marker (either '-', '+' or 'a') 
- Three-digit personal identification number 
- A digit or letter (case insensitive) which is a check digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_finnish_national_id finds content that matches the pattern.
- A keyword from Keyword_finnish_national_id is found.
- The checksum passes.

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### Keywords

- Keyword_finnish_national_id
- Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## Finland Passport Number

Format
Combination of nine letters and digits
Pattern
Combination of nine letters and digits:
Two letters (not case sensitive) 
Seven digits
Checksum
No
Definition
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
The regular expression Regex_finland_passport_number finds content that matches the pattern.
A keyword from Keyword_finland_passport_number is found.
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
Keywords
Keyword_finland_passport_number
Passport
Passi
   
## France Driver's License Number

### Format

12 digits

### Pattern

12 digits with validation to discount similar patterns such as French telephone numbers

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_french_drivers_license finds content that matches the pattern.
- At least one of the following is true:
- A keyword from Keyword_french_drivers_license is found.
- The function Func_eu_date finds a date in the right date format.

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## France National ID Card (CNI)

### Format

12 digits

### Pattern

12 digits

### Checksum

No

### Definition

A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_france_cni finds content that matches the pattern.

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### Keywords

None
   
## France Passport Number

### Format

Nine digits and letters

### Pattern

Nine digits and letters:
- Two digits 
- Two letters (not case sensitive) 
- Five digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_fr_passport finds content that matches the pattern.
- A keyword from Keyword_passport is found.

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
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

      
## France Social Security Number (INSEE)

### Format

15 digits

### Pattern

Must match one of two patterns:
- 13 digits followed by a space followed by two digits</br>
or
- 15 consecutive digits

### Checksum

Yes

### Definition

A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_french_insee or Func_fr_insee finds content that matches the pattern.
- A keyword from Keyword_fr_insee is found.
- The checksum passes.

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_french_insee or Func_fr_insee finds content that matches the pattern.
- No keyword from Keyword_fr_insee is found.
- The checksum passes.

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- no. d'identité
- numero d'identite
- no d'identite
- no. d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 
   
## German Driver's License Number

### Format

Combination of 11 digits and letters

### Pattern

11 digits and letters (not case sensitive):
- A digit or letter 
- Two digits 
- Six digits or letters 
- A digit 
- A digit or letter

### Checksum

Yes

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_german_drivers_license finds content that matches the pattern.
- At least one of the following is true:
    - A keyword from Keyword_german_drivers_license_number is found.
    - A keyword from Keyword_german_drivers_license_collaborative is found.
    - A keyword from Keyword_german_drivers_license is found.
- The checksum passes.

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- DL 
- DLS
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
   
## German Passport Number

### Format

10 digits or letters

### Pattern

Pattern must include all of the following:
- First character is a digit or a letter from this set (C, F, G, H, J, K) 
- Three digits 
- Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z) 
- A digit

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_german_passport finds content that matches the pattern.
- A keyword from any of the five keyword lists is found.
- The checksum passes.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_german_passport_data finds content that matches the pattern.
- A keyword from any of the five keyword lists is found.
- The checksum passes.

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- passport
- passports

#### Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### Keyword_german_passport_number

No-Reisepass 
Nr-Reisepass

#### Keyword_german_passport1

Reisepass-Nr

#### Keyword_german_passport2

bnationalit.t
   
## Germany Identity Card Number

### Format

Since 1 November 2010: Nine letters and digits

From 1 April 1987 until 31 October 2010: 10 digits

### Pattern

Since 1 November 2010:
- One letter (not case sensitive) 
- Eight digits

From 1 April 1987 until 31 October 2010:
- 10 digits

### Checksum

No

### Definition

A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_germany_id_card finds content that matches the pattern.
- A keyword from Keyword_germany_id_card is found.

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_germany_id_card

- Identity Card
- ID
- Identification
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## Greece National ID Card

### Format

Combination of 7-8 letters and numbers plus a dash

### Pattern

Seven letters and numbers (old format):
- One letter (any letter of the Greek alphabet) 
- A dash 
- Six digits

Eight letters and numbers (new format):
- Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX) 
- A dash 
- Six digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_greece_id_card finds content that matches the pattern.
- A keyword from Keyword_greece_id_card is found.

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### Keywords

#### Keyword_greece_id_card

- Greek identity Card
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## Hong Kong Identity Card (HKID) Number

### Format

Combination of 8-9 letters and numbers plus optional parentheses around the final character

### Pattern

Combination of 8-9 letters:
- 1-2 letters (not case sensitive) 
- Six digits 
- The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.

### Checksum

Yes

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_hong_kong_id_card finds content that matches the pattern.
- A keyword from Keyword_hong_kong_id_card is found.
- The checksum passes.

A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_hong_kong_id_card finds content that matches the pattern.
- The checksum passes.

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

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
   

