---
title: "EU Phone Number"
ms.author: stephow
author: stephow
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: "Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type."
---

# EU Phone Number

Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type. 
  
## Austria

### Format

No standard length
  
### Pattern

- Digits 
    
- Only mobile phone numbers begin with the digit "6" 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern. 
    
- A keyword from  `Keywords_austria_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern. 
    
- A keyword from  `Keywords_austria_eu_telephone_number` is found. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## Belgium

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern. 
    
- A keyword from  `Keywords_belgium_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern. 
    
- A keyword from  `Keywords_belgium_eu_telephone_number` is found. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## Bulgaria

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_bulgaria_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## Croatia

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_croatia_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## Cyprus

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_cyprus_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## Czech Republic

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_czech_republic_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## Denmark

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_denmark_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Estonia

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_estonia_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## Finland

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_finland_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## France

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_france_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Germany

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_germany_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## Greece

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_greece_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## Hungary

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_hungary_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## Ireland

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_ireland_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Italy

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_italy_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## Latvia

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_latvia_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Lithuania

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_lithuania_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Luxemburg

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_luxemburg_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## Malta

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_malta_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## Netherlands

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_netherlands_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## Poland

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_poland_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## Portugal

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_portugal_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## Romania

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_romania_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## Slovakia

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_slovakia_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## Slovenia

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_slovenia_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Spain

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_spain_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## Sweden

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_sweden_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## UK

### Pattern

- Digits 
    
### Checksum

Not applicable
  
### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern. 
    
- A keyword from  `Keywords_uk_eu_telephone_number` is found. 
    
A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
  
- The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## See also

[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)

