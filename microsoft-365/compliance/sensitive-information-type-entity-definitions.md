---
title: Entitätsdefinitionen für Typen vertraulicher Informationstypen
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) im Security Compliance Center umfasst 80 Typen vertraulicher Informationen, die Sie in Ihren &amp; DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.
ms.openlocfilehash: b70f335fd0742e6bc34957058c6e695530e83507
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927131"
---
# <a name="sensitive-information-type-entity-definitions"></a>Entitätsdefinitionen für Typen vertraulicher Informationstypen

Ein vertraulicher Informationstyp wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann. Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden. Beim Auswertungsprozess können auch die Zuverlässigkeitsstufe und die Näherung herangezogen werden.

Typen vertraulicher Informationen erfordern eines der folgenden Abonnements:
- Microsoft 365 E3
- Microsoft 365 E5

Typen vertraulicher Informationen werden in folgenden Bereichen verwendet:

- [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) 
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](retention.md)
- [Kommunikationscompliance](communication-compliance.md)
- [Richtlinien für die automatische Kennzeichnung](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="aba-routing-number"></a>ABA-Routingnummer

### <a name="format"></a>Format

neun Ziffern, die in einem formatierten oder unformatierten Muster vorliegen können

### <a name="pattern"></a>Muster

Formatiert:
- vier Ziffern beginnend mit 0, 1, 2, 3, 6, 7 oder 8
- Ein Bindestrich
- vier Ziffern
- Ein Bindestrich
- eine Ziffer

Unformatiert: neun aufeinanderfolgende Ziffern beginnend mit 0, 1, 2, 3, 6, 7 oder 8 

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ABA_Routing wurde gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- Routing #
- routing no
- Routingnummer
- routing transit number
- Routing #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Argentinien – Nationale Identitätsnummer (DNI)

### <a name="format"></a>Format

Acht Ziffern mit oder ohne Punkte

### <a name="pattern"></a>Muster

Acht Ziffern:
- zwei Ziffern
- Optionaler Zeitraum
- drei Ziffern
- Optionaler Zeitraum
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_argentina_national_id gefunden.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- cedula 
- cédula 
- dni 
- documento nacional de identidad 
- documento número 
- documento numero 
- registro nacional de las personas 
- rnp 
   
## <a name="australia-bank-account-number"></a>Australische Bankkontonummer

### <a name="format"></a>Format

6 bis 10 Ziffern mit oder ohne Bank bank state branch number

### <a name="pattern"></a>Muster

Die Kontonummer ist sechs bis zehn Ziffern.

Australische Bankleitzahl:
- drei Ziffern 
- Ein Bindestrich 
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_australia_bank_account_number_bsb findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

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

## <a name="australia-business-number"></a>Australische Geschäftsnummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security


### <a name="format"></a>Format

11 Ziffern mit optionalen Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern mit optionalen Trennzeichen:

- zwei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_australian_business_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_australian_business_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_australian_business_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- Geschäftsnummer
- abn #
- businessid #
- Geschäfts-ID
- abn
- businessno #

## <a name="australia-company-number"></a>Australische Unternehmensnummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern mit Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern mit Trennzeichen:

- drei Ziffern
- ein Leerzeichen
- drei Ziffern
- ein Leerzeichen
- drei Ziffern


### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_Australian_Company_Number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Australian_Company_Number gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_Australian_Company_Number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- can
- australia company no
- australia company no #
- australische Unternehmensnummer
- australian company no
- australian company no #
- australische Unternehmensnummer

## <a name="australia-drivers-license-number"></a>Australische Führerscheinnummer

### <a name="format"></a>Format

neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

neun Buchstaben und Ziffern: 

- zwei Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 
- zwei Ziffern 
- fünf Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

OR

- 1 bis 2 optionale Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 
- vier bis neun Ziffern

OR

- neun Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_australia_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_australia_drivers_license_number wurde gefunden.
- Es wurde kein Schlüsselwort aus Keyword_australia_drivers_license_number_exclusions gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
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
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

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
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Driver'License #
- Driver'Licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Australische Medical -Kontonummer

### <a name="format"></a>Format

10-11 Ziffern

### <a name="pattern"></a>Muster

10-11 Ziffern:
- Erste Ziffer liegt im Bereich von 2 bis 6
- Neunte Ziffer ist eine Prüfziffer
- Zehnte Ziffer ist die Problemziffer
- Elfte Ziffer (optional) ist die einzelne Zahl.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Australia_Medical_Account_Number wurde gefunden.
- Die Prüfsumme stimmt.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## <a name="australia-passport-number"></a>Australische Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Ein Buchstabe (Groß-/Kleinschreibung irrelevant) gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_australia_passport_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_passport oder Keyword_australia_passport_number wurde gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- ポ .
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

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
   
## <a name="australia-tax-file-number"></a>Australische Steuernummer

### <a name="format"></a>Format

Acht bis neun Ziffern

### <a name="pattern"></a>Muster

Acht bis neun Ziffern werden in der Regel wie folgt mit Leerzeichen dargestellt:
- drei Ziffern 
- Ein optionales Leerzeichen 
- drei Ziffern 
- Ein optionales Leerzeichen 
- zwei bis drei Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_australian_tax_file_number findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_Australia_Tax_File_Number oder Keyword_number_exclusions gefunden.
- Die Prüfsumme stimmt.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>Austria driver's license number

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Der reguläre Ausdruck  `Regex_austria_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_austria_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver A0 s_license_number

- langsamererschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Österreich- Identitätskarte
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Eine 24-stellige Kombination aus Buchstaben, Ziffern und Sonderzeichen
  
### <a name="pattern"></a>Muster

24 Zeichen:
  
-  22 Buchstaben (ohne Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche, Schrägstriche oder Pluszeichen 
    
- zwei Buchstaben (groß-/kleinschreibungsempfindlich), Ziffern, umgekehrte Schrägstriche, Schrägstriche, Pluszeichen oder Gleichheitszeichen
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Der reguläre Ausdruck  `Regex_austria_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_austria_eu_national_id_card` gefunden. 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- Identitätsnummer
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Österreich- Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von einem optionalen Leerzeichen und sieben Ziffern
  
### <a name="pattern"></a>Muster

Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:
  
- Ein Buchstabe (ohne Schreibung)
- Ein Leerzeichen (optional)
- sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_austria_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_austria_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Das Datum im Format TT.MM.JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_austria_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_austria_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reise 2013


## <a name="austria-social-security-number"></a>Sozialversicherungsnummer Österreich

### <a name="format"></a>Format

10 Ziffern im angegebenen Format
  
### <a name="pattern"></a>Muster

10 Ziffern:
  
- drei Ziffern, die einer Seriennummer entsprechen 
- Eine Prüfziffer
- sechs Ziffern, die dem Geburtsdatum entsprechen (DDMMYY)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wird, wenn:
- Die Funktion  `Func_austria_eu_ssn_or_equivalent` findet Inhalte, die dem Muster entsprechen. 
- es wurde ein Schlüsselwort  `Keywords_austria_eu_ssn_or_equivalent` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_austria_eu_ssn_or_equivalent` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- zeit ssn
- ehic number
- ehic no
- Versicherungscode
- insurancecode #
- Versicherungsnummer
- insurance no
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- Sozialversicherung nein
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Steueridentifikationsnummer Für Österreich

### <a name="format"></a>Format

Neun Ziffern mit optionalem Bindestrich und Schrägstrich
  
### <a name="pattern"></a>Muster

neun Ziffern mit optionalem Bindestrich und Schrägstrich:
  
- zwei Ziffern
- Ein Bindestrich (optional)
- drei Ziffern
- Schrägstrich (optional)
- vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_austria_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_austria_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion  `Func_austria_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- Steuernummer
 
## <a name="austria-value-added-tax"></a>Umsatzsteuer für Österreich
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 11 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 11 Zeichen:

- A oder a
- T oder t
- Optionaler Platz
- U oder U
- Optionaler Platz
- zwei oder drei Ziffern
- Optionaler Platz
- vier Ziffern
- Optionaler Platz
- eine oder zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_Austria_Value_Added_Tax findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Austria_Value_Added_Tax gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_Austria_Value_Added_Tax findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- uSt-Nummer
- vat #
- umsatzsteuernummer
- vat no.
- vatno #
- Umsatzsteuernummer
- vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- uSt-Identifikationsnummer
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB-Authentifizierungsschlüssel

### <a name="format"></a>Format

Die Zeichenfolge "DocumentDb" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "DocumentDb"
- Beliebige Kombination aus 3-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Ein Größer-als-Symbol (>), ein Gleichheitszeichen (=), ein Anführungszeichen (") oder ein Apostroph (')
- Eine beliebige Kombination aus 86 Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck CEP_Regex_AzureDocumentDBAuthKey findet Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS-Datenbankverbindungszeichenfolge und Azure SQL Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Server", "Server" oder "Datenquelle", gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen, einschließlich der Zeichenfolge "cloudapp.azure".<!--no-hyperlink-->com" oder "cloudapp.azure.<!--no-hyperlink-->net" oder "database.windows.<!--no-hyperlink-->"net" und die Zeichenfolge "Password" oder "password" oder "pwd".

### <a name="pattern"></a>Muster

- Die Zeichenfolge "Server", "Server" oder "Datenquelle"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" oder "database.windows.<!--no-hyperlink-->net"
- Beliebige Kombination aus 1-300 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "Password", "password" oder "pwd"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Ein oder mehrere Zeichen, die kein Semikolon (;), Anführungszeichen (") oder Apostroph (') sind
- Ein Semikolon (;), Anführungszeichen (") oder Apostroph (')

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck CEP_Regex_AzureConnectionString inhalt, der dem Muster entspricht.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Azure IoT-Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "HostName" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen, einschließlich der Zeichenfolgen "azure-devices.<!--no-hyperlink-->net" und "SharedAccessKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "HostName"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "azure-devices.<!--no-hyperlink-->net"
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "SharedAccessKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 43 Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureIoTConnectionString findet Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Kennwort für Azure-Veröffentlichungseinstellung

### <a name="format"></a>Format

Die Zeichenfolge "userpwd=", gefolgt von einer alphanumerischen Zeichenfolge.

### <a name="pattern"></a>Muster

- die Zeichenfolge "userpwd="
- Beliebige Kombination aus 60 Kleinbuchstaben oder Ziffern
- Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck CEP_Regex_AzurePublishSettingPasswords findet Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Azure Redis cache connection string

### <a name="format"></a>Format

Die Zeichenfolge "redis.cache.windows.<!--no-hyperlink-->net" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen, einschließlich der Zeichenfolge "password" oder "pwd".

### <a name="pattern"></a>Muster

- die Zeichenfolge "redis.cache.windows.<!--no-hyperlink-->net"
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "password" oder "pwd"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 43 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+) sind
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureRedisCacheConnectionString inhalt, der dem Muster entspricht.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Format

Die Zeichenfolge "sig" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen.

### <a name="pattern"></a>Muster

- die Zeichenfolge "sig"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 43 bis 53 Zeichen, die Klein- oder Großbuchstaben, Ziffern oder das Prozentzeichen (%) sind
- die Zeichenfolge "%3d"
- Ein beliebiges Zeichen, bei dem es sich nicht um Klein- oder Großbuchstaben, Ziffern oder Prozentzeichen (%) handelt

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureSAS inhalt, der dem Muster entspricht.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Verbindungszeichenfolge für Azure-Dienstbus

### <a name="format"></a>Format

Die Zeichenfolge "EndPoint" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen, einschließlich der Zeichenfolgen "servicebus.windows.<!--no-hyperlink-->net" und "SharedAccesKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "EndPoint"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "servicebus.windows.<!--no-hyperlink-->net"
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "SharedAccessKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 43 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+) sind
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureServiceBusConnectionString inhalt, der dem Muster entspricht.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Azure Storage Account Key

### <a name="format"></a>Format

Die Zeichenfolge "DefaultEndpointsProtocol" gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen, einschließlich der Zeichenfolge "AccountKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "DefaultEndpointsProtocol"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "AccountKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 86 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+) sind
- zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKey findet Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_AzureEmulatorStorageAccountFilter **findet keine** Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Azure Storage-Kontoschlüssel (generisch)

### <a name="format"></a>Format

Eine beliebige Kombination aus 86 Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+), vor oder gefolgt von den Im folgenden Muster beschriebenen Zeichen.

### <a name="pattern"></a>Muster

- Null bis zu einem der Größer-als-Zeichen (>), Apostroph ('), Gleichheitszeichen (=), Anführungszeichen (") oder Nummernzeichen (#)
- Eine beliebige Kombination aus 86 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+) sind
- zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKeyGeneric findet Inhalte, die dem Muster entsprechen.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Belgische Führerscheinnummer

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

zehn Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_belgium_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus `Keywords_eu_driver's_license_number` oder `Keywords_belgium_eu_driver's_license_number` wurde gefunden.
    
```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver A0 s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füscheinerscheinnummer
- langsamererschein
- fuscheinerschein
- langsamererscheinnummer
- fugifterscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Nationale belgische Nummer

### <a name="format"></a>Format

11 Ziffern plus optionale Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern plus Trennzeichen:
- sechs Ziffern und zwei optionale Punkte im Format YY. MM.DD für das Geburtsdatum 
- Ein optionales Trennzeichen von Punkt, Strich, Leerzeichen 
- drei fortlaufende Ziffern (ungerade für 15- und 15-5-800er-Ziffern, auch für Frauen) 
- Ein optionales Trennzeichen von Punkt, Strich, Leerzeichen 
- Zwei Prüfziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_belgium_national_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_belgium_national_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion Func_belgium_national_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- vorn
- nationale Nummer
- national register
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- Persönliche ID-Nummer
- personalausweis
- personalidnumber #
- registratie
- registrierung
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="belgium-passport-number"></a>Belgische Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

zwei Buchstaben und gefolgt von sechs Ziffern
  
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

 Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_belgium_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_belgium_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet Datum im Format TT MM JJ oder ein `Regex_eu_passport_date2` Schlüsselwort aus oder wird `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` gefunden

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_belgium_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_belgium_eu_passport_number` wurde gefunden. 

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport 2013
- Pass-Nr
- Passnummer
- reisepass kein


## <a name="belgium-value-added-tax-number"></a>Umsatzsteuernummer für Belgien
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 12 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 12 Zeichen:

- Ein Buchstabe B oder b
- Ein Buchstabe E oder e
- Eine Ziffer 0
- eine Ziffer von 1 bis 9
- Optionaler Punkt oder Bindestrich oder Leerzeichen
- vier Ziffern
- Optionaler Punkt oder Bindestrich oder Leerzeichen
- vier Ziffern


### <a name="checksum"></a>Prüfsumme

Ja


### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_belgium_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_belgium_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_belgium_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- uSt-Nummer
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Brasilien CPF-Nummer

### <a name="format"></a>Format

11 Ziffern, die eine Prüfziffer umfassen und die formatiert oder unformatiert sein können

### <a name="pattern"></a>Muster

Formatiert:
- drei Ziffern
- ein Zeitraum
- drei Ziffern
- ein Zeitraum
- drei Ziffern
- Ein Bindestrich
- zwei Ziffern, bei denen es sich um Prüfziffern handelt

Unformatiert:
- 11 Ziffern, wobei die letzten beiden Ziffern Prüfziffern sind

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_brazil_cpf findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_brazil_cpf gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_brazil_cpf findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identifikation
- Registrierung
- Umsatz
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Brazil legal entity number (CNPJ)

### <a name="format"></a>Format

14 Ziffern, die eine Registrierungsnummer, eine Zweignummer und Prüfnziffern sowie Trennzeichen umfassen

### <a name="pattern"></a>Muster

14 Ziffern plus Trennzeichen:

- zwei Ziffern 
- ein Zeitraum 
- drei Ziffern 
- ein Zeitraum 
- drei Ziffern (diese ersten acht Ziffern sind die Registrierungsnummer) 
- Schrägstrich 
- Vierstellige Zweigstellennummer 
- Ein Bindestrich 
- zwei Ziffern, bei denen es sich um Prüfziffern handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_brazil_cnpj findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_brazil_cnpj gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_brazil_cnpj findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

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

   
## <a name="brazil-national-identification-card-rg"></a>Brasilien – Nationale Identifikationskarte (RG)

### <a name="format"></a>Format

Registro Geral (altes Format): Neun Ziffern

Registro de Identidade (RIC) (neues Format): 11 Ziffern

### <a name="pattern"></a>Muster

Registro Geral (altes Format):
- zwei Ziffern 
- ein Zeitraum 
- drei Ziffern 
- ein Zeitraum 
- drei Ziffern 
- Ein Bindestrich 
- Eine Ziffer, die eine Prüfziffer ist

Registro de Identidade (RIC) (neues Format):
- zehn Ziffern 
- Ein Bindestrich 
- Eine Ziffer, die eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_brazil_rg findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_brazil_rg gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_brazil_rg findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden) 
- RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden) 


## <a name="bulgaria-drivers-license-number"></a>Bulgarien - Führerscheinnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_bulgaria_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>    
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver A0 s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Bulgarien uniform civil number
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
- sechs Ziffern, die dem Geburtsdatum entsprechen (YYMMDD) 
- zwei Ziffern, die der Geburtsreihenfolge entsprechen
- eine Ziffer, die dem Geschlecht entspricht: Eine gleichmäßige Ziffer für männlich und eine ungerade Ziffer für Eine Frau
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_bulgaria_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_bulgaria_eu_national_id_card` gefunden. 

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_bulgaria_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinen druckerhdanski nomer
- egn #
- egn
- identification number
- national id
- nationale Nummer
- nationalnumber #
- nationalnumber
- Persönliche ID
- persönlich nein
- Persönliche Nummer
- personalidnumber #
- social security number
- ssn #
- ssn
- Uniform civil id
- Uniform civil no
- Uniform civil number
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- Eindeutige Nummer der Bürgerschaft
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Bulgarien - Reisepassnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_bulgaria_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Das Datum im Format TT.MM.JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_bulgaria_eu_passport_number` wurde gefunden. 

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum

## <a name="canada-bank-account-number"></a>Kanadische Bankkontonummer

### <a name="format"></a>Format

sieben oder zwölf Ziffern

### <a name="pattern"></a>Muster

Eine kanadische Kontonummer umfasst sieben oder zwölf Ziffern.

Eine kanadische Bankkontonummer setzt sich wie folgt zusammen:
- fünf Ziffern 
- Ein Bindestrich 
- drei Ziffern ODER
- a zero "0" 
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_canada_bank_account_transit_number findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

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

   
## <a name="canada-drivers-license-number"></a>Kanadische Führerscheinnummer

### <a name="format"></a>Format

Variiert je nach Provinz

### <a name="pattern"></a>Muster

Verschiedene Muster in Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec und Saskatchewan

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_[province_name]_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_[province_name]_drivers_license_name wurde gefunden.
- Ein Schlüsselwort aus Keyword_canada_drivers_license wurde gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- Die Abkürzung für die Provinz, z. B. AB
- Der Name der Provinz, beispielsweise „Alberta“

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

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
- Driver'Lic
- Driver'Lics
- Driver' License
- Driver' Licenses
- Driver'Licence
- Driver'Licences
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
- DL #
- DLS # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver'Licence # 
- Driver'Licences # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver' Licence# 
- Driver' Licences# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- id # 
- ids # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- identification # 

   
## <a name="canada-health-service-number"></a>Kanadische Gesundheitsdienstnummer

### <a name="format"></a>Format

zehn Ziffern

### <a name="pattern"></a>Muster

zehn Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_canada_health_service_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_health_service_number wurde gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- trigiatrist
- workers compensation
- Disability

      
## <a name="canada-passport-number"></a>Kanadische Reisepassnummer

### <a name="format"></a>Format

zwei Großbuchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

zwei Großbuchstaben gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_canada_passport_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_passport_number oder Keyword_passport wurde gefunden.

```xml 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- ポ .
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Kanadische Personal Health Identification Number (PHIN)

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_canada_phin findet Inhalte, die dem Muster entsprechen.
- Es werden mindestens zwei Schlüsselwörter aus Keyword_canada_phin oder Keyword_canada_provinces gefunden.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

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

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Toronto
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Kanada

   
## <a name="canada-social-insurance-number"></a>Kanadische Sozialversicherungsnummer

### <a name="format"></a>Format

neun Ziffern mit optionalen Bindestrichen oder Leerzeichen

### <a name="pattern"></a>Muster

Formatiert:
- drei Ziffern 
- Ein Bindestrich oder Leerzeichen 
- drei Ziffern 
- Ein Bindestrich oder Leerzeichen 
- drei Ziffern

Unformatiert: neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_canadian_sin findet Inhalte, die dem Muster entsprechen.
- Mindestens zwei dieser eine beliebige Kombination der folgenden Aktionen aus:
    - Ein Schlüsselwort aus Keyword_sin wurde gefunden.
    - Ein Schlüsselwort aus Keyword_sin_collaborative wurde gefunden.
    - Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_unformatted_canadian_sin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_sin wurde gefunden.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_sin"></a>Keyword_sin

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
- sin # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Geburtsdatum 
- Geburtstag 
- Date of Birth 

   
## <a name="chile-identity-card-number"></a>Chile Identity Card Number

### <a name="format"></a>Format

Sieben bis acht Ziffern plus Trennzeichen für eine Prüfziffer oder einen Buchstaben

### <a name="pattern"></a>Muster

Sieben bis acht Ziffern plus Trennzeichen:
- ein bis zwei Ziffern 
- Optionaler Zeitraum 
- drei Ziffern 
- Optionaler Zeitraum 
- drei Ziffern 
- Ein Bindestrich 
- Eine Ziffer oder ein Buchstabe (ohne Schreibung), bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_chile_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_chile_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_chile_id_card findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único enario
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol UnicoArio
- RUN #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Chilean identity no.
- Chileische Identitätsnummer
- Chileische Identität #
- Eindeutiges Steuerregistrierungsregister
- Eindeutige Rolle "Auf dem När"
- Eindeutige Steuerrolle
- Eindeutige Aufr nnungsnummer
- Eindeutige nationale Nummer
- Eindeutige nationale Rolle
- National eindeutige Rolle
- Chile identity no.
- Chile Identity Number
- Chile identity #

   
## <a name="china-resident-identity-card-prc-number"></a>China Resident Identity Card (PRC) number

### <a name="format"></a>Format

18 Ziffern

### <a name="pattern"></a>Muster

18 Ziffern:
- sechs Ziffern, bei denen es sich um einen Adresscode handelt 
- Acht Ziffern im Format "YYYYMMDD", die das Geburtsdatum sind 
- Drei Ziffern, bei denen es sich um einen Bestellcode handelt 
- Eine Ziffer, die eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_china_resident_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_china_resident_id gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_china_resident_id findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

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

   
## <a name="credit-card-number"></a>Kreditkartennummern

### <a name="format"></a>Format

14 bis 16 Ziffern, die formatiert oder unformatiert (dddd) sein können und den Luhn-Test bestehen müssen.

### <a name="pattern"></a>Muster

Sehr komplexe und robuste Muster, die Karten aller wichtigen Marken weltweit, einschließlich Visa, MasterCard, Discover-Karte, JCB, American Express, Geschenkgutscheine und Restaurantkarten erkennen.

### <a name="checksum"></a>Prüfsumme

Ja, die Luhn-Prüfsumme

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_cc_verification wurde gefunden.
    - Ein Schlüsselwort aus Keyword_cc_name wurde gefunden.
    - Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

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
- Sicherheitskode
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
- cod. seguranca
- cod. segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- Gültig bis
- gültigkeitsdatum
- Gultig bis
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
- transaction
- Transaktionsnummer
- Referenznummer
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- zu
- master card
- mc
- unter
- master cards
- diner's Club
- diners club
- diners in
- discover
- discover card
- discovercard
- discover cards
- JON
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc #
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
- Cardmember Acct
- cardmember-Konto
- Cardno
- Unternehmenskarte
- Unternehmenskarten
- Kartentyp
- Kartenkontonummer
- Kartenmitgliedskonto
- Cardmember Acct.
- card no.
- card no
- card number
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
- n. carta
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
- Nein. de tarjeta
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
- Nein. do cartão
- Nein. do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visa
- Visa
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Croatia driver's license number

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
  
- Der reguläre Ausdruck  `Regex_croatia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus `Keywords_eu_driver's_license_number` oder `Keywords_croatia_eu_driver's_license_number` wurde gefunden. 

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver A0 s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Kreditkartennummer für Kroatien
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "Nationale Identifikationsnummer" der EU enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_croatia_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_croatia_id_card gefunden.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- grammstorski broj đana
- Haupt-Citizen-Nummer
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- Persönliche Identifikationsnummer
- zeitzni broj
- nimzni identifikacijski broj
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="croatia-passport-number"></a>Kroatien - Reisepassnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_croatia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_croatia_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet das Datum im Format "DD.MM.JJJJ" oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_croatia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_croatia_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>Kroatien – Persönliche Identifikationsnummer (OIB)

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- zehn Ziffern 
- Die letzte Ziffer ist eine Prüfziffer.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_croatia_oib_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_croatia_eu_tax_file_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_croatia_oib_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- grammstorski broj đana
- Haupt-Citizen-Nummer
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- Persönliche Identifikationsnummer
- tinzni broj
- zeitzni identifikacijski broj
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="cyprus-drivers-license-number"></a>Führerscheinnummer für Zypern

### <a name="format"></a>Format

12 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

12 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_cyprus_eu_driver's_license_number` wurde gefunden.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver's_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Identitätskarte für Zypern
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

zehn Ziffern 
  
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_cyprus_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_cyprus_eu_national_id_card` gefunden. 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id card number
- Identitätskartennummer
- kimlik karti
- national identification number
- Persönliche ID-Nummer
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Reisepassnummer für Zypern

### <a name="format"></a>Format

Ein Buchstabe gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe gefolgt von sechs bis acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_cyprus_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_cyprus_eu_passport_date` findet Datum im Format TT/MM/JJJJ oder ein Schlüsselwort wurde `Keywords_cyprus_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_cyprus_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_cyprus_eu_passport_number` wurde gefunden.  
    
```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- läuft ab
- ausgestellt am


## <a name="cyprus-tax-identification-number"></a>Steueridentifikationsnummer für Zypern
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern und ein Buchstabe im angegebenen Muster
  
### <a name="pattern"></a>Muster

acht Ziffern und ein Buchstabe:
  
- "0" oder "9"
- sieben Ziffern
- Ein Buchstabe (ohne Schreibung)
    
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_cyprus_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_cyprus_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_cyprus_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- Steueridentifikationscode
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- tin id
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Tschechische Führerscheinnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

acht Buchstaben und Ziffern:
  
- Buchstabe "E" (ohne Schreibung)
- ein Buchstabe
- Ein Leerzeichen (optional)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_czech_republic_eu_driver's_license_number` wurde gefunden. 

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver A0 s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Tschechische Reisepassnummer

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_czech_republic_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet das Datum im Format "DD.MM.JJJJ" oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_czech_republic_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="czech-personal-identity-number"></a>Personal Identity Number (Tschechisch)

### <a name="format"></a>Format

Neun Ziffern mit optionalem Schrägstrich (altes Format) zehn Ziffern mit optionalem Schrägstrich (neues Format)

### <a name="pattern"></a>Muster

neun Ziffern (altes Format):
- sechs Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich
- drei Ziffern

zehn Ziffern (neues Format):
- sechs Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich 
- vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_czech_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_czech_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_czech_id_card_new_format findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- Geburtsnummer
- tschechische Republik-ID
- czechidno #
- daňové číslo
- identifikační číslo
- Identity no
- Identitätsnummer
- identityno #
- identityno
- Versicherungsnummer
- national identification number
- nationalnumber #
- nationale Nummer
- osobní číslo
- personalidnumber #
- Persönliche ID-Nummer
- Persönliche Identifikationsnummer
- Persönliche Nummer
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- Eindeutige Identifikationsnummer


## <a name="denmark-drivers-license-number"></a>Führerscheinnummer Dänemark

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_denmark_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_denmark_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver A0 s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Dänemark Reisepassnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_denmark_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_denmark_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date2` findet Datum im Format TT MM JJ oder ein Schlüsselwort gefunden `Keywords_eu_passport_date` wurde

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_denmark_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_denmark_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="denmark-personal-identification-number"></a>Dänemark persönliche Identifikationsnummer

### <a name="format"></a>Format

Zehn Ziffern mit einem Bindestrich

### <a name="pattern"></a>Muster

zehn Ziffern:
- sechs Ziffern im Format DDMMYY, die das Geburtsdatum sind 
- Ein Bindestrich 
- vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Func_denmark_eu_tax_file_number inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keyword_denmark_id gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Func_denmark_eu_tax_file_number inhalt, der dem Muster entspricht.
- Die Prüfsumme stimmt.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringsystem
- cpr
- cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- Integritätskarte
- Health Insurance Card Number
- Health Insurance Number
- identification number
- identifikationsnummer
- identifikationsnummer #
- Identitätsnummer
- krankenkassennummer
- nationalid #
- nationalnumber #
- nationale Nummer
- personalidnumber #
- personalidentityno #
- Persönliche ID-Nummer
- personnummer
- personnummer #
- reiseversicherungnversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- skat id
- skat kode
- skat nummer
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- Steuercode
- Reiseversicherungskarte
- uniqueidentityno #
- Steuernummer
- Steuerregistrierungsnummer
- tax id
- Steueridentifikationsnummer
- zeitd #
- taxnumber #
- tax no
- taxno #
- taxnumber
- steueridentifikation nein
- tin #
- zeitdno #
- zeitdnumber #
- tax no #
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Drug Enforcement Agency (DEA) number

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Ein Buchstabe (ohne Schreibung) aus dieser Gruppe möglicher Buchstaben: abcdefghjklmnprstux, ein Registrantcode 
- ein Buchstabe (ohne Schreibung), bei dem es sich um den ersten Buchstaben des Nachnamens oder der Ziffer "9" des Registranten handelt
- sieben Ziffern, von denen die letzte die Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keyword_dea_number` gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- Verwaltung der Erzwingung von Rauschmittel
- Drug Enforcement Agency


## <a name="estonia-drivers-license-number"></a>Estnisch- Führerscheinnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

zwei Buchstaben und sechs Ziffern:
  
- Die Buchstaben "ET" (Groß-/Kleinschreibung wird nicht beachtet) 
- sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_estonia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_estonia_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver's_license_number

-- permis de conduire
- juhilubade numbrid
- juhiloa number
- juhiluba


## <a name="estonia-personal-identification-code"></a>Estnisch - Personal Identification Code
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- eine Ziffer, die dem Geschlecht und dem Geburtsjahr des Geburtsjahrs entspricht (ungerade Zahl männlich, gleichzahlig frau; 1-2: 19. Geburtstag; 3-4: 20. Jahrjahrjahr; 5.6.
- sechs Ziffern, die dem Geburtsdatum entsprechen (YYMMDD)
- drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am selben Datum stammen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_estonia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_estonia_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_estonia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- nationale Nummer
- Persönlicher Code
- Persönliche ID-Nummer
- Persönlicher Identifikationscode
- Persönliche Identifikationsnummer
- personalidnumber #
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="estonia-passport-number"></a>Estnisch Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_estonia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_estonia_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet das Datum im Format "DD.MM.JJJJ" oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_estonia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_estonia_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="eu-debit-card-number"></a>EU-Debitkartennummern

### <a name="format"></a>Format

16 Ziffern

### <a name="pattern"></a>Muster

Sehr komplexes und robustes Muster

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_eu_debit_card findet Inhalte, die dem Muster entsprechen.
- Mindestens eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_eu_debit_card wurde gefunden.
    - Ein Schlüsselwort aus Keyword_card_terms_dict wurde gefunden.
    - Ein Schlüsselwort aus Keyword_card_security_terms_dict wurde gefunden.
    - Ein Schlüsselwort aus Keyword_card_expiration_terms_dict wurde gefunden.
    - Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- cc # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

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
- undekaart 
- cirrus 
- cirrus-edc-eines 
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
- diners in 
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
- jon 
- kaart 
- kaart num 
- kaartaantal 
- kaartattallen 
- kaoudouder 
- kaoudouders 
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
- unter 
- mc 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Nein. de tarjeta 
- Nein. do cartao 
- Nein. do cartão 
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

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

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
- Nein. dell'edizione 
- Nein. di sicurezza 
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
- Sicherheitskode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- igheidsaantal 
- codigheidscode 
- igheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

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
- läuft ab 
- expiry 
- fecha de expiracion 
- fecha de venc 
- Gultig bis 
- gultigkeitsdatum 
- Gültig bis 
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


## <a name="eu-drivers-license-number"></a>EU-Führerscheinnummer

Dies sind die Entitäten im vertraulichen Informationstyp "EU Driver's License Number".

- [Österreich](#austria-drivers-license-number) 
- [Belgien](#belgium-drivers-license-number)
- [Bulgarien](#bulgaria-drivers-license-number)
- [Kroatien](#croatia-drivers-license-number)
- [Zypern](#cyprus-drivers-license-number)
- [Tschechisch](#czech-drivers-license-number)
- [Dänemark](#denmark-drivers-license-number)
- [Estland](#estonia-drivers-license-number)
- [Finnland](#finland-drivers-license-number)
- [Frankreich](#france-drivers-license-number) 
- [Deutschland](#germany-drivers-license-number)
- [Griechenland](#greece-drivers-license-number)
- [Ungarn](#hungary-drivers-license-number)
- [Irland](#ireland-drivers-license-number)
- [Italien](#italy-drivers-license-number)
- [Lettland](#latvia-drivers-license-number)
- [Litauen](#lithuania-drivers-license-number)
- [Luxemburg](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Niederlande](#netherlands-drivers-license-number)
- [Polen](#poland-drivers-license-number) 
- [Portugal](#portugal-drivers-license-number)
- [Rumänien](#romania-drivers-license-number)
- [Slowakei](#slovakia-drivers-license-number)
- [Slowenien](#slovenia-drivers-license-number)
- [Spanien](#spain-drivers-license-number)
- [Schweden](#sweden-drivers-license-number)
- [Vereinigtes Königreich](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Nationale EU-Identifikationsnummer

Dies sind die Entitäten im vertraulichen Informationstyp "Eu-nationale Identifikationsnummer".

- [Österreich](#austria-identity-card)
- [Belgien](#belgium-national-number)
- [Bulgarien](#bulgaria-uniform-civil-number)
- [Kroatien](#croatia-identity-card-number)
- [Zypern](#cyprus-identity-card)
- [Tschechisch](#czech-personal-identity-number)
- [Dänemark](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finnland](#finland-national-id)
- [Frankreich](#france-national-id-card-cni)
- [Deutschland](#germany-identity-card-number)
- [Griechenland](#greece-national-id-card)
- [Ungarn](#hungary-personal-identification-number)
- [Irland](#ireland-personal-public-service-pps-number)
- [Italien](#italy-fiscal-code)
- [Lettland](#latvia-personal-code)
- [Litauen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Niederlande](#netherlands-citizens-service-bsn-number)
- [Polen](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Rumänien](#romania-personal-numeric-code-cnp)
- [Slowakei](#slovakia-personal-number)
- [Slowenien](#slovenia-unique-master-citizen-number)
- [Spanien](#spain-dni)
- [Vereinigtes Königreich](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU-Reisepassnummer 

Dies sind die Entitäten im Vertraulichen Informationstyp "EU-Reisepassnummer". Dies sind die Entitäten im EU-Reisepass-Nummernbundl.

- [Österreich](#austria-passport-number)
- [Belgien](#belgium-passport-number)
- [Bulgarien](#bulgaria-passport-number)
- [Kroatien](#croatia-passport-number)
- [Zypern](#cyprus-passport-number)
- [Tschechisch](#czech-passport-number)
- [Dänemark](#denmark-passport-number)
- [Estland](#estonia-passport-number)
- [Finnland](#finland-passport-number)
- [Frankreich](#france-passport-number)
- [Deutschland](#germany-passport-number)
- [Griechenland](#greece-passport-number)
- [Ungarn](#hungary-passport-number)
- [Irland](#ireland-passport-number)
- [Italien](#italy-passport-number)
- [Lettland](#latvia-passport-number)
- [Litauen](#lithuania-passport-number)
- [Luxemburg](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Niederlande](#netherlands-passport-number)
- [Polen](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Rumänien](#romania-passport-number)
- [Slowakei](#slovakia-passport-number)
- [Slowenien](#slovenia-passport-number)
- [Spanien](#spain-passport-number)
- [Schweden](#sweden-passport-number)
- [Vereinigtes Königreich](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Sozialversicherungsnummer der EU oder gleichwertige Identifikation

Dies sind die Entitäten, die sich in der EU-Sozialversicherungsnummer oder einem gleichwertigen Typ vertraulicher Informationen zur Identifizierung befinden.

- [Österreich](#austria-social-security-number)
- [Belgien](#belgium-national-number)
- [Kroatien](#croatia-personal-identification-oib-number)
- [Tschechisch](#czech-personal-identity-number)
- [Dänemark](#denmark-personal-identification-number)
- [Finnland](#finland-national-id)
- [Frankreich](#france-social-security-number-insee-or-equivalent-identification)
- [Deutschland](#germany-identity-card-number)
- [Griechenland](#greece-national-id-card)
- [Ungarn](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [Spanien](#spain-social-security-number-ssn)
- [Schweden](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU-Steuernummer

Diese Entitäten befinden sich im Vertraulichen Informationstyp "EU-Steuernummer".

- [Österreich](#austria-tax-identification-number)
- [Belgien](#belgium-national-number)
- [Bulgarien](#bulgaria-uniform-civil-number)
- [Kroatien](#croatia-identity-card-number)
- [Zypern](#cyprus-tax-identification-number)
- [Tschechisch](#czech-personal-identity-number)
- [Dänemark](#denmark-personal-identification-number)
- [Estland](#estonia-personal-identification-code)
- [Finnland](#finland-national-id)
- [Frankreich](#france-tax-identification-number)
- [Deutschland](#germany-tax-identification-number)
- [Griechenland](#greece-tax-identification-number)
- [Ungarn](#hungary-tax-identification-number)
- [Irland](#ireland-personal-public-service-pps-number)
- [Italien](#italy-fiscal-code)
- [Lettland](#latvia-personal-code)
- [Litauen](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Niederlande](#netherlands-tax-identification-number)
- [Polen](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Rumänien](#romania-personal-numeric-code-cnp)
- [Slowakei](#slovakia-personal-number)
- [Slowenien](#slovenia-tax-identification-number)
- [Spanien](#spain-tax-identification-number)
- [Schweden](#sweden-tax-identification-number)
- [Vereinigtes Königreich](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Finnische Führerscheinnummer

### <a name="format"></a>Format

zehn Ziffern und Buchstaben mit einem Bindestrich
  
### <a name="pattern"></a>Muster

zehn Ziffern und Buchstaben mit einem Bindestrich:
  
- sechs Ziffern 
- Ein Bindestrich
- drei Ziffern 
- Eine Ziffer oder ein Buchstabe
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_finland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_finland_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver A0 s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Finnische Europäische Krankenversicherungsnummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

20 Ziffern

### <a name="pattern"></a>Muster

20-stellige Nummer:

- zehn Ziffern – 8024680246
- Ein optionaler Leerzeichen oder Bindestrich
- zehn Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Regex_Finland_European_Health_Insurance_Number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Finland_European_Health_Insurance_Number gefunden.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- Integritätskarte
- Krankenversicherungskarte
- Health Insurance Number
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terttiskortti


## <a name="finland-national-id"></a>Nationale finnische ID

### <a name="format"></a>Format

sechs Ziffern plus ein Zeichen, das ein Hunderterzeichen plus drei Ziffern plus eine Prüfziffer angibt

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- sechs Ziffern im Format DDMMYY, die ein Geburtsdatum sind 
- 1.000er-Markierung (entweder '-', '+' oder 'a') 
- Dreistellige persönliche Identifikationsnummer 
- Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung wird nicht beachtet), bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion, Func_finnish_national_id Inhalt findet, der dem Muster entspricht
- Ein Schlüsselwort aus Keyword_finnish_national_id gefunden
- Prüfsummenprüfungen

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion, Func_finnish_national_id Inhalt findet, der dem Muster entspricht
- Prüfsummenprüfungen

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identiteetti numero
- Identitätsnummer
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- national id card
- national id no.
- Persönliche ID
- Personal Identity Code
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- tunnistenumero
- tunnus numero
- tunnuslbrüche
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Finnische Reisepassnummer

### <a name="format"></a>Format
Kombination aus neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster
Kombination aus neun Buchstaben und Ziffern:
- zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_finland_passport_number inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keywords_eu_passport_number_common oder Keyword_finland_passport_number wurde gefunden.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- passi number


## <a name="france-drivers-license-number"></a>Französische Führerscheinnummer

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern mit Validierung, um ähnliche Muster ( z. B. französische Telefonnummern) auszuschließen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_french_drivers_license findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_french_drivers_license gefunden.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Französische Gesundheitsversicherungsnummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

21 Ziffern

### <a name="pattern"></a>Muster

21 Ziffern:

- zehn Ziffern
- Ein optionales Leerzeichen
- zehn Ziffern
- Ein optionales Leerzeichen
- eine Ziffer


### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Regex_France_Health_Insurance_Number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_France_Health_Insurance_Number gefunden.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- Insurance Card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Französische National-ID-Karte (CNI)

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_france_cni findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_france_eu_national_id_card gefunden.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- nationale Identität
- nationalidno #
- numéro d'assuranceérdie
- numéro de carte vitale

   
## <a name="france-passport-number"></a>Französische Reisepassnummer
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "EU Passport Number" verfügbar und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

neun Ziffern und Buchstaben

### <a name="pattern"></a>Muster

neun Ziffern und Buchstaben:
- zwei Ziffern 
- zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_fr_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_passport wurde gefunden.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- ポ .
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Französische Sozialversicherungsnummer (INSEE) oder gleichwertige Identifikation
Diese Entität des Typs "Vertrauliche Informationen" ist im Vertraulichen Informationstyp "Sozialversicherungsnummer" und "Äquivalente ID" der EU enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

15 Ziffern

### <a name="pattern"></a>Muster

Muss einem von zwei Mustern entsprechen:
- 13 Ziffern gefolgt von einem Leerzeichen gefolgt von zwei Ziffern<br/>
oder
- 15 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_fr_insee wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_fr_insee gefunden.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- Nein. d'identité
- numero d'identite
- no d'identite
- Nein. d'identite
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

## <a name="france-tax-identification-number"></a>Französische Steuernummer

### <a name="format"></a>Format

13 Ziffern
  
### <a name="pattern"></a>Muster

13 Ziffern
  
- Eine Ziffer, die 0, 1, 2 oder 3 sein muss
- 1 Ziffer
- Ein Leerzeichen (optional) 
- 2 Ziffern 
- Ein Leerzeichen (optional) 
- 3 Ziffern 
- Ein Leerzeichen (optional) 
- 3 Ziffern 
- Ein Leerzeichen (optional) 
- 3 Prüfziffern 

  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_france_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_france_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_france_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Französische Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 13 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 13 Zeichen:

- zwei Buchstaben - FR (Groß-/Kleinschreibung wird nicht beachtet)
- Ein optionaler Leerzeichen oder Bindestrich
- zwei Buchstaben oder Ziffern
- Ein optionales Leerzeichen, ein Punkt, ein Bindestrich oder ein Komma
- drei Ziffern
- Ein optionales Leerzeichen, ein Punkt, ein Bindestrich oder ein Komma
- drei Ziffern
- Ein optionales Leerzeichen, ein Punkt, ein Bindestrich oder ein Komma
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_france_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_france_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_france_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- uSt-Nummer
- vat no
- vat #
- Umsatzsteuer
- siren identification no numéro d'identification taxe sur valeur atétée
- taxe valeur atétée
- taxe sur la valeur atétée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Deutsche Führerscheinnummer

### <a name="format"></a>Format

Kombination aus 11 Ziffern und Buchstaben

### <a name="pattern"></a>Muster

11 Zahlen und Buchstaben (ohne Beachtung der Groß-/Kleinschreibung):
- Eine Ziffer oder ein Buchstabe 
- zwei Ziffern 
- sechs Ziffern oder Buchstaben 
- eine Ziffer 
- Eine Ziffer oder ein Buchstabe

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_german_drivers_license findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_german_drivers_license_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- Ausstellende Behöde
- Ausstellende Behorde
- ausstellende behoerde
- führerschein
- langsamererschein
- fuscheinerschein
- führerscheinnummer
- langsamererscheinnummer
- fugifterscheinnummer
- führerschein- 
- langsamererschein- 
- fuscheinerschein- 
- führerscheinnummernr
- langsamererscheinnummernr
- fuscheinerscheinnummernr
- führerscheinnummerklasse
- langsamererscheinnummerklasse
- fuscheinerscheinnummerklasse
- nr-führerschein
- nr-wiedererschein
- nr-fugifterschein
- no-führerschein
- no-wiedererschein
- no-fugifterschein
- n-führerschein
- n-wiedererschein
- n-fugifterschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dlno


## <a name="germany-identity-card-number"></a>Deutschland - Personalausweisnummer

### <a name="format"></a>Format

seit 1. November 2010: Neun Buchstaben und Ziffern

vom 1. April 1987 bis zum 31. Oktober 2010: 10 Ziffern

### <a name="pattern"></a>Muster

seit dem 1. November 2010:
- Ein Buchstabe (ohne Schreibung) 
- acht Ziffern

vom 1. April 1987 bis zum 31. Oktober 2010:
- zehn Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_germany_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_germany_id_card gefunden.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identification
- identifikation
- identifizierungsnummer
- identity card
- Identitätsnummer
- id-nummer
- Persönliche ID
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Deutsche Reisepassnummer

### <a name="format"></a>Format

zehn Ziffern oder Buchstaben

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Das erste Zeichen ist eine Ziffer oder ein Buchstabe aus diesem Satz (C, F, G, H, J, K) 
- drei Ziffern 
- fünf Ziffern oder Buchstaben aus diesem Satz (C, -H, J-N, P, R, T, V-Z) 
- eine Ziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_german_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus `Keyword_german_passport` oder `Keywords_eu_passport_number_common` wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_german_passport_data findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus `Keyword_german_passport` oder `Keywords_eu_passport_number_common` wurde gefunden.
- Die Prüfsumme stimmt.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reise ohne
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern


## <a name="germany-tax-identification-number"></a>Deutsche Steueridentifikationsnummer

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- Zwei Ziffern 
- Ein optionales Leerzeichen
- Drei Ziffern 
- Ein optionales Leerzeichen
- Drei Ziffern 
- Ein optionales Leerzeichen
- Zwei Ziffern
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_germany_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_germany_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_germany_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zeit #
- zeit
- wiedererdingnummer


## <a name="germany-value-added-tax-number"></a>Deutsche Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 11 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 11 Zeichen:

- Ein Buchstabe D oder d
- Ein Buchstabe E oder e
- Ein optionales Leerzeichen
- drei Ziffern
- Ein optionales Leerzeichen oder Komma
- drei Ziffern
- Ein optionales Leerzeichen oder Komma
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_germany_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_germany_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_germany_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- uSt-Nummer
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Führerscheinnummer für Griechenland

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_greece_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_greece_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver A0 s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Griechenland - Personalausweis

### <a name="format"></a>Format

Kombination von 7-8 Buchstaben und Zahlen plus einem Gedankenstrich

### <a name="pattern"></a>Muster

Sieben Buchstaben und Zahlen (altes Format):
- Ein Buchstabe (jeder Buchstabe des griechischen Alphabets)  
- Ein Bindestrich 
- Sechs Ziffern

Acht Buchstaben und Zahlen (neues Format):
- Zwei Buchstaben, deren Großbuchstabe sowohl im griechischen als auch lateinischen Alphabet (ABEZHIKMNOPTYX) vorkommt  
- Ein Bindestrich 
- Sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_greece_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_greece_id_card gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_greece_id_card findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- greek id
- Greek national id
- Greek personal id card
- Greek police id
- identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Reisepassnummer für Griechenland

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_greece_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_greece_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_greece_eu_passport_date` findet datums im Format TT MMM JJ (Beispiel - 28 August 19) oder ein Schlüsselwort `Keywords_greece_eu_passport_date` gefunden wurde

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_greece_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_greece_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Griechenland Sozialversicherungsnummer (AMKA)
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Elf Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

- 6 Ziffern als Geburtsdatum YYMMDD
- 4 Ziffern
- Eine Prüfziffer
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_greece_eu_ssn` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_greece_eu_ssn_or_equivalent` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_greece_eu_ssn` findet Inhalte, die dem Muster entsprechen. 

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- Sozialversicherung nein
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Steueridentifikationsnummer für Griechenland
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Der reguläre Ausdruck  `Regex_greece_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_greece_eu_tax_file_number` gefunden. 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm #
- afm
- aφμ|aφμ αριθμός
- aφμ
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- steuerregistrierung nein
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- tin id
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Hong Kong Identity Card (HKID) number

### <a name="format"></a>Format

Kombination aus 8-9Buchstaben und Zahlen sowie optionale Klammern um das letzte Zeichen

### <a name="pattern"></a>Muster

Kombination aus Buchstaben 8-9 Buchstaben:
- 1-2 Buchstaben (Groß-/Kleinschreibung irrelevant)  
- Sechs Ziffern 
- Das letzte Zeichen (eine Ziffer oder der Buchstabe A), bei dem es sich um die Prüfziffer handelt, die optional in Klammern eingeschlossen werden kann.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_hong_kong_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_hong_kong_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion Func_hong_kong_id_card findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- hong kong identity card
- HKIDC
- id card
- identity card
- hk identity card
- hong kong id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証

   
## <a name="hungary-drivers-license-number"></a>Führerscheinnummer für Ungarn

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Zwei Buchstaben und sechs Ziffern:
  
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Der reguläre Ausdruck  `Regex_hungary_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_hungary_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver's_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Personal Identification Number (Ungarn)
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- Eine Ziffer, die dem Geschlecht entspricht (1-männlich, 2-frau, andere Nummern sind auch für Bürger möglich, die vor 1900 oder Mitberechtigerechten sind) 
- Sechs Ziffern, die dem Geburtsdatum entsprechen (YYMMDD)
- Drei Ziffern, die einer Seriennummer entsprechen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
  
- Die Funktion  `Func_hungary_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_hungary_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
  
- Die Funktion  `Func_hungary_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igkrüvány
- személyi igidovány


## <a name="hungary-passport-number"></a>Ungarn - Reisepassnummer

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_hungary_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_hungary_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet Datum im Format `Regex_hungary_eu_passport_date` TT MMM/MMM JJ (Beispiel - 01 MÁR/MRT 12) oder ein Schlüsselwort `Keywords_eu_passport_date` wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_hungary_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_hungary_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám


## <a name="hungary-social-security-number-taj"></a>Ungarn sozialversicherungsnummer (TAJ)

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Die Funktion  `Func_hungary_eu_ssn_or_equivalent` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_hungary_eu_ssn_or_equivalent` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Die Funktion  `Func_hungary_eu_ssn_or_equivalent` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- ungarisch sozialversicherungsnummer
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- ssn
- ssn #
- Sozialversicherung nein
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Steueridentifikationsnummer für Ungarn
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zehn Ziffern:
  
- Eine Ziffer, die "8" sein muss 
- Acht Ziffern
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Die Funktion  `Func_hungary_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_hungary_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
  
- Die Funktion  `Func_hungary_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- ungarisch tin
- hungatiantin #
- Steuerbehörde nein
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- uSt-Nummer


## <a name="hungary-value-added-tax-number"></a>Ungarn - Mehrwert-Steuernummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 10 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 10 Zeichen:

- 2 Buchstaben - HU oder Hu
- Optionaler Speicherplatz
- 8 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_hungarian_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_hungarian_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_hungarian_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- Umsatzsteuernummer
- vat #
- vatno #
- ungarischvatno #
- tax no.
- value added tax áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Indien – permanente Kontonummer (PAN)

### <a name="format"></a>Format

10 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

10 Buchstaben oder Ziffern:
- Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- Ein Buchstabe in C, P, H, F, A, T, B, L, J, G (ohne Schreibung)
- Ein Buchstabe
- Vier Ziffern 
- Ein Buchstabe (ohne Schreibung)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_india_permanent_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_india_permanent_account_number gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_india_permanent_account_number findet Inhalte, die dem Muster entsprechen.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- PAN 
   
## <a name="india-unique-identification-aadhaar-number"></a>Indien – eindeutige Identifikationsnummer (Aadhaar)

### <a name="format"></a>Format

12 Ziffern mit optionalen Leerzeichen oder Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- Eine Ziffer, die nicht 0 oder 1 ist
- Drei Ziffern 
- Eine optionales Leerzeichen oder ein Bindestrich  
- Vier Ziffern 
- Eine optionales Leerzeichen oder ein Bindestrich  
- Die letzte Ziffer, die eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_india_aadhaar findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_india_aadhar gefunden.
- Die Prüfsumme stimmt.
- 
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_india_aadhaar findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai
   
## <a name="indonesia-identity-card-ktp-number"></a>Indonesische Personalausweisnummer (KTP)

### <a name="format"></a>Format

16 Ziffern mit optionalen Punkten

### <a name="pattern"></a>Muster

16 Ziffern:
- Zweistelliger Provinzcode  
- Ein Punkt (optional)  
- Zweistelliger Regency- oder Stadtcode  
- Zweistelliger Subdistrict-Code  
- Ein Punkt (optional)  
- Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben  
- Ein Punkt (optional)  
- Vier Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_indonesia_id_card gefunden.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Internationale Bankkontonummer (IBAN)

### <a name="format"></a>Format

Ländercode (zwei Buchstaben) plus Prüfziffern (zwei Ziffern) plus Bban-Nummer (bis zu 30 Zeichen)

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:

- Zwei Buchstaben Ländercode
- Zwei Prüfziffern (gefolgt von einem optionalen Leerzeichen) 
- 1-7 Gruppen mit vier Buchstaben oder Ziffern (kann durch Leerzeichen getrennt werden)
- 1 bis 3 Buchstaben oder Ziffern

Das Format für jedes Land ist etwas anders. Der Typ vertraulicher IBAN-Informationen deckt die folgenden 60 Länder ab:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:

- Die Funktion Func_iban findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Keine

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Internationale Klassifikation von Krankheit (ICD-10-CM)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Ein Schlüsselwort aus Dictionary_icd_10_updated gefunden.
- Ein Schlüsselwort aus Dictionary_icd_10_codes gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Ein Schlüsselwort aus Dictionary_icd_10_ wurde gefunden.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Schlüsselwörter

Ein beliebiger Begriff aus Dictionary_icd_10_updated Schlüsselwörterbuch, der auf der International [Classification of Diseases, Tenth Revision, Modification Modification (ICD-10-CM) basiert.](https://go.microsoft.com/fwlink/?linkid=852604) Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungscodes.

Ein beliebiger Begriff aus Dictionary_icd_10_codes Schlüsselwörterbuch, der auf der International [Classification of Diseases, Tenth Revision, Modification Modification (ICD-10-CM) basiert.](https://go.microsoft.com/fwlink/?linkid=852604) Dieser Typ sucht nur nach Versicherungscodes, nicht nach der Beschreibung.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Internationale Klassifikation von Krankheit (ICD-9-CM)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Ein Schlüsselwort aus Dictionary_icd_9_updated gefunden.
- Ein Schlüsselwort aus Dictionary_icd_9_codes gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Ein Schlüsselwort aus Dictionary_icd_9_updated gefunden.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Ein beliebiger Begriff aus Dictionary_icd_9_updated Schlüsselwörterbuch, der auf der [International Classification of Diseases,Ninth Revision, Modification Modification (ICD-9-CM) basiert.](https://go.microsoft.com/fwlink/?linkid=852605) Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungscodes.

Ein beliebiger Begriff aus Dictionary_icd_9_codes Schlüsselwörterbuch, der auf der [International Classification of Diseases,Ninth Revision, Modification Modification (ICD-9-CM) basiert.](https://go.microsoft.com/fwlink/?linkid=852605) Dieser Typ sucht nur nach Versicherungscodes, nicht nach der Beschreibung.

## <a name="ip-address"></a>IP-Adresse

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4:
Komplexes Muster, das formatierte (Punkte) und unformatierte (keine Punkte) Versionen der IPv4-Adressen angibt

#### <a name="ipv6"></a>IPv6:
 Komplexes Muster, das formatierte IPv6-Nummern angibt (schließt Doppelpunkte ein)

### <a name="pattern"></a>Muster

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Für IPv6 hat eine DLP-Richtlinie eine hohe Sicherheit, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in der Nähe von 300 Zeichen:
- Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.

Für IPv4 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_ipv4_address findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ipaddress wurde gefunden.

Für IPv6 ist eine DLP-Richtlinie zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden)
- ip address 
- IP-Adressen
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Führerscheinnummer Irland

### <a name="format"></a>Format

Sechs Ziffern, gefolgt von vier Buchstaben
  
### <a name="pattern"></a>Muster

Sechs Ziffern und vier Buchstaben:
  
- Sechs Ziffern
- Vier Buchstaben (groß-/klein geschrieben)
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
  
- Der reguläre Ausdruck  `Regex_ireland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_ireland_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver A0 s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Irland - Reisepassnummer

### <a name="format"></a>Format

Zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:
  
- Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)
- Sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_ireland_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_ireland_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet datums im Format `Regex_ireland_eu_passport_date` TT MMM/MMM JJJJ (Beispiel - 01 BEA/MAI 1988) oder ein Schlüsselwort gefunden `Keywords_eu_passport_date` wurde

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_ireland_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_ireland_eu_passport_number` wurde gefunden.
    
```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasrea
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="ireland-personal-public-service-pps-number"></a>Ireland Personal Public Service (PPS) number

### <a name="format"></a>Format

Altes Format (bis 31. Dezember 2012):
- sieben Ziffern gefolgt von 1-2 Buchstaben 

Neues Format (1. Januar 2013 und danach):
- sieben Ziffern gefolgt von zwei Buchstaben

### <a name="pattern"></a>Muster

Altes Format (bis 31. Dezember 2012):
- sieben Ziffern 
- 1 bis 2 Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 

Neues Format (1. Januar 2013 und danach):
- sieben Ziffern 
- Ein Buchstabe (ohne Schreibung), bei dem es sich um eine alphabetische Prüfziffer handelt 
- Ein optionaler Buchstabe im Bereich A-I oder "W"

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_ireland_pps findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_ireland_eu_national_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_ireland_pps findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- Clientidentitätsdienst
- identification number
- Persönliche ID-Nummer
- Persönliche öffentliche Dienstnummer
- Persönlicher Dienst nein
- phearsane seirbhíse poiblí
- pps no
- pps number
- pps num
- pps service no
- ppsn
- ppsno #
- ppsno
- psp
- Öffentlicher Dienst nein
- publicserviceno #
- publicserviceno
- Umsatz- und Sozialversicherungsnummer
- rsi no
- rsi number
- rsin
- seirbhís aithekliis client
- uimh
- uimhir aithemieis chánach
- uimhir aithemieis phearsane
- uimhir phearsphe seirbhíse poiblí
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Israel bank account number

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

Formatiert:
- zwei Ziffern 
- Ein Bindestrich 
- drei Ziffern 
- Ein Bindestrich 
- acht Ziffern

Unformatiert:
- 	13 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_israel_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_israel_bank_account_number wurde gefunden.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Nationale Identifikationsnummer Israels

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_israeli_national_id_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Israel_National_ID wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   id number
-   Identity no        
-   identitynumber #
-   Identitätsnummer
-   zeitidentitynumber       
-   Persönliche ID
-   eindeutige ID  

   
## <a name="italy-drivers-license-number"></a>Italienische Führerscheinnummer

### <a name="format"></a>Format

Eine Kombination aus 10 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

eine Kombination aus 10 Buchstaben und Ziffern:
- Ein Buchstabe (ohne Schreibung) 
- Der Buchstabe "A" oder "V" (ohne Schreibung) 
- sieben Ziffern
- Ein Buchstabe (ohne Schreibung)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_italy_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_italy_drivers_license_number wurde gefunden.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patent
- patente di guida 
- patent guida
- patenti di guida
- patenti guida

## <a name="italy-fiscal-code"></a>Finanzcode für Italien
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Eine 16-stellige Kombination aus Buchstaben und Ziffern im angegebenen Muster
  
### <a name="pattern"></a>Muster

Eine 16-stellige Kombination aus Buchstaben und Ziffern:
- drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen
- drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen
- zwei Ziffern, die den letzten Ziffern des Geburtsjahrs entsprechen
- Ein Buchstabe, der dem Buchstaben für den Geburtsmonat entspricht– Buchstaben werden in alphabetischer Reihenfolge verwendet, es werden jedoch nur die Buchstaben A bis E, H, L, M, P, R bis T verwendet (also ist Januar A und Oktober ist R).
- zwei Ziffern, die dem Tag des Geburtsmonats entsprechen– um zwischen den Geschlechten zu unterscheiden, werden 40 zum Geburtstag für Frauen hinzugefügt.
- vier Ziffern, die der Ortswahl entsprechen, die für die Herkunft der Person spezifisch ist (länderweite Codes werden für fremde Länder verwendet)
- Eine Paritätsziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_italy_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_italy_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_italy_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- Finanzcode
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- Persönliche Zertifikatnummer
- Persönlicher Code
- Personal -ID-Code
- Persönliche ID-Nummer
- personalcodeno #
- Steuercode
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- Steueridentitätsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="italy-passport-number"></a>Italienische Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:
  
- zwei Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_italy_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_italy_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet Datum im Format `Regex_italy_eu_passport_date` TT MMM/MMM JJJJ (Beispiel - 01 GEN/JAN 1988) oder ein Schlüsselwort `Keywords_eu_passport_date` wurde gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_italy_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_italy_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="italy-value-added-tax-number"></a>Italienische Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 13 Zeichen und optionalen Trennzeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 13 Zeichen und optionalen Trennzeichen:

- I oder i
- T oder t
- Optionales Leerzeichen, Punkt, Bindestrich oder Komma
- 11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_italy_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_italy_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_italy_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- uSt-Nummer
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Japanische Bankkontonummer

### <a name="format"></a>Format

sieben oder acht Ziffern

### <a name="pattern"></a>Muster

Bankkontonummer:
- sieben oder acht Ziffern
- Bankfiliale:
- vier Ziffern 
- Leerzeichen oder Gedankenstriche (optional) 
- drei Ziffern

Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.
- Eine der folgenden Bedingungen trifft zu:
- Die Funktion Func_jp_bank_account_branch_code findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_branch_code wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Japanische Führerscheinnummer

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_jp_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_drivers_license_number wurde gefunden.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Japan – Meine Nummer – Unternehmen
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffernnummer:

- Eine Ziffer von 1 bis 9
- 12 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_japanese_my_number_corporate findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_japanese_my_number_corporate gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_japanese_my_number_corporate findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- Unternehmensnummer
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Japan – Eigene Nummer – Persönlich
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffernnummer:

- vier Ziffern
- Ein optionales Leerzeichen, ein Punkt oder ein Bindestrich
- vier Ziffern
- Ein optionales Leerzeichen, ein Punkt oder ein Bindestrich
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_japanese_my_number_personal findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_japanese_my_number_personal gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_japanese_my_number_personal findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- Meine Nummer
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Japanische Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet), gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_jp_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_passport wurde gefunden.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Passport
- Passport Number
- Passport No.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- ポ .
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Japanische Wohnsitzkartennummer

### <a name="format"></a>Format

12 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

12 Buchstaben und Ziffern:
- zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- acht Ziffern 
- zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_jp_residence_card_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_residence_card_number gefunden.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Nummer der Wohnortkarte
- Wohnortkarte nein
- Wohnortkarte #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Japanische Einwohnerregistrierungsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_jp_resident_registration_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_resident_registration_number wurde gefunden.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証

   
## <a name="japan-social-insurance-number-sin"></a>Japanische Sozialversicherungsnummer (SIN)

### <a name="format"></a>Format

7-12 Ziffern

### <a name="pattern"></a>Muster

7 bis 12 Ziffern:
- vier Ziffern 
- Ein Bindestrich (optional) 
- sechs Ziffern ODER
- 7-12 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_jp_sin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_jp_sin_pre_1997 findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- Oder 保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Führerscheinnummer für Lettland

### <a name="format"></a>Format

drei Buchstaben gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

drei Buchstaben und sechs Ziffern:
  
- drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_latvia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_latvia_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver A0 s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Persönlicher Code für Lettland

### <a name="format"></a>Format

11 Ziffern und ein optionaler Bindestrich
  
### <a name="pattern"></a>Muster

Altes Format

11 Ziffern und ein Bindestrich:
  
- sechs Ziffern, die dem Geburtsdatum entsprechen (DDMMYY) 
- Ein Bindestrich
- eine Ziffer, die dem Geburtsjahrjahr entspricht ("0" für das 19. Und "1" für das 20. Und "2" für das 21.
- Vier Ziffern, nach dem Zufallsprinzip generiert

Neues Format

11 Ziffern

- Zwei Ziffern "32"
- Neun Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_latvia_eu_national_id_card` oder der reguläreEx findet `Regex_latvia_eu_national_id_card_new_format` Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_latvia_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_latvia_eu_national_id_card` oder der reguläreEx findet `Regex_latvia_eu_national_id_card_new_format` Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- administrative Nummer
- asils nē
- Geburtsnummer
- Citizen Number
- standesamt.nn.
- Elektronische Zählungsnummer
- elektronische Nummer
- Finanzcode
- Benutzernummer im Gesundheitswesen
- id #
- id-code
- identification number
- identifikācijas numurs
- id-number
- einzelne Zahl
- latvija avas
- nacionālais id
- national id
- Nationale Identifikationsnummer
- national identity number
- national insurance number
- national register number
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- Persönliche Zertifikatnummer
- Persönlicher Code
- Personal -ID-Code
- Persönliche ID-Nummer
- Persönlicher Identifikationscode
- Persönlicher Bezeichner
- Persönliche Identitätsnummer
- Persönliche Nummer
- Persönlicher numerischer Code
- personalcodeno #
- personas kods
- Grundgesamtheitsidentifikationscode
- Öffentliche Dienstnummer
- registration number
- Umsatznummer
- social insurance number
- social security number
- Steuercode des Bundeslandes
- tax file number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- Wählernummer

## <a name="latvia-passport-number"></a>Lettisch - Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:
  
- zwei Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_latvia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_latvia_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Das Datum im Format TT.MM.JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_latvia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_latvia_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="lithuania-drivers-license-number"></a>Litauisch - Führerscheinnummer

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_lithuania_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver A0 s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Persönlicher Code für Litauen
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern ohne Leerzeichen und Trennzeichen:
  
- eine Ziffer (1-6), die dem Geschlecht und dem Geburtsjahr des Menschen entspricht
- sechs Ziffern, die dem Geburtsdatum entsprechen (YYMMDD) 
- drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_lithuania_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_lithuania_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_lithuania_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis öks
- asmens öks
- Citizen Service Number
- mokesčių id
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- national identification number
- Persönlicher Code
- Persönlicher numerischer Code
- piliečio paslaugos numeris
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- unikalus identifikavimo ikis
- unikalus identifikavimo numeris
- Eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Reisepassnummer für Litauen

### <a name="format"></a>Format

Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
  
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_lithuania_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date3` findet Das Datum im Format TT MM JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_lithuania_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="luxemburg-drivers-license-number"></a>Luxemburger Führerscheinnummer

### <a name="format"></a>Format

sechs Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

sechs Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_luxemburg_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver A0 s_license_number

- fahr
- Zungeschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Nationale Identifikationsnummer luxemburgisch (natürliche Personen)
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern:
  
- 11 Ziffern 
- Zwei Prüfziffern
    
### <a name="checksum"></a>Prüfsumme

ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_luxemburg_eu_national_id_card` gefunden. 

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- Einzelner Code
- individuelle ID
- Einzelidentifikation
- individuelle Identität
- numéro d'identification personnel
- Persönliche ID
- Persönliche Identifikation
- Persönliche Identität
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- eindeutige ID
- Eindeutige Identität
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Luxemburg passport number

### <a name="format"></a>Format

Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

acht Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_luxemburg_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date3` findet Das Datum im Format TT MM JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_luxemburg_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- luxemburg pass
- luxemburg passeport
- luxemburg passport
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reise 2013
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Nationale Identifikationsnummer luxemburgisch (nicht natürliche Personen)

### <a name="format"></a>Format

11 Ziffern
  
### <a name="pattern"></a>Muster

11 Ziffern
  
- zwei Ziffern
- Ein optionales Leerzeichen 
- drei Ziffern 
- Ein optionales Leerzeichen
- drei Ziffern 
- Ein optionales Leerzeichen
- zwei Ziffern
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_luxemburg_eu_tax_file_number_non_natural` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_luxemburg_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_luxemburg_eu_tax_file_number_non_natural` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxemburg tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxemburgeois
- numéro d'identification fiscale
- social security
- sozialeunterstützung
- sozialeversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- zeit #
- zeit
- zeitzahl


## <a name="malaysia-identification-card-number"></a>Malaysia - Identifikationskartennummer

### <a name="format"></a>Format

12 Ziffern mit optionalen Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- sechs Ziffern im Format "YYMMDD", die das Geburtsdatum sind 
- Bindestrich (optional) 
- Aus zwei Buchstaben geerbte Geburtscode 
- Bindestrich (optional) 
- Drei zufällige Ziffern 
- Einstelliger Gendercode

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_malaysia_id_card_number inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keyword_malaysia_id_card_number gefunden.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- Digitale Anwendungskarte
- i/c
- i/c no
- ic
- ic no
- id card
- identification Card
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- malaysia identity card
- malaysian identity card
- nric
- Persönliche Identifikationskarte

## <a name="malta-drivers-license-number"></a>Malta driver's license number

### <a name="format"></a>Format

Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster
  
### <a name="pattern"></a>Muster

Kombination aus zwei Zeichen und sechs Ziffern:
  
- zwei Zeichen (Ziffern oder Buchstaben, groß-/klein geschrieben)
- Ein Leerzeichen (optional)
- drei Ziffern
- Ein Leerzeichen (optional)
- drei Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_malta_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver A0 s_license_number

- lisenzja tas-sewqan
- lisenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Malta Identity Card Number
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

sieben Ziffern gefolgt von einem Buchstaben
  
### <a name="pattern"></a>Muster

sieben Ziffern gefolgt von einem Buchstaben:
  
- sieben Ziffern 
- ein Buchstabe in "M, G, A, P, L, H, B, Z" (Groß-/Kleinschreibung wird nicht beachtet)
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_malta_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_malta_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- Citizen Service Number
- id tat-taxxa
- identifika numru tal-biljett
- kodiei numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz ta
- numru tat-taxxa
- Persönlicher numerischer Code
- Eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #


## <a name="malta-passport-number"></a>Malta Passport number

### <a name="format"></a>Format

sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

sieben Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_malta_eu_passport_number` wurde gefunden. 
- Ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_malta_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_malta_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="malta-tax-identification-number"></a>Steuerkennnummer für Malta

### <a name="format"></a>Format

Für Nser aus Malta:
- sieben Ziffern und ein Buchstabe im angegebenen Muster
  
Nischisch-nisch-nisch(n) und -Entitäten(n):
- neun Ziffern
  
### <a name="pattern"></a>Muster

Deutsche Nser: sieben Ziffern und ein Buchstabe
  
- sieben Ziffern 
- Ein Buchstabe (ohne Schreibung)
    
Ns-nisch-deutsche und -deutsche Entitäten: neun Ziffern
  
- neun Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläreEx  `Regex_malta_eu_tax_file_number`  oder `Regex_malta_eu_tax_file_number_non_maltese_national` der gefundene Inhalt, der dem Muster entspricht. 
- Es wurde ein Schlüsselwort  `Keywords_malta_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Der reguläreEx  `Regex_malta_eu_tax_file_number` oder `Regex_malta_eu_tax_file_number_non_maltese_national` der gefundene Inhalt, der dem Muster entspricht. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- Citizen Service Number
- id tat-taxxa
- identifika numru tal-biljett
- kodiei numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz ta
- numru tat-taxxa
- Persönlicher numerischer Code
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- Eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Nummer des niederländischen Citizen's Service (BSN)

### <a name="format"></a>Format

89 Ziffern mit optionalen Leerzeichen

### <a name="pattern"></a>Muster

89 Ziffern:
- drei Ziffern 
- Ein Leerzeichen (optional) 
- drei Ziffern 
- Ein Leerzeichen (optional) 
- zwei-drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_netherlands_bsn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_netherlands_bsn gefunden.
- Die Prüfsumme stimmt.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- bsn #
- bsn
- ungservicenummer
- Citizen Service Number
- Personennummer
- Persönliche Nummer
- Persönlicher numerischer Code
- Personenbezogene Nummer
- persoonlijk nummer
- persoonlijke num codiert
- persoonsgeagaen
- persoonsnummer
- sociaal-fiscaal nummer
- Social-Fiscal-Nummer
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- Eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Niederländische Führerscheinnummer

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

zehn Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_netherlands_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_netherlands_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver A0 s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Niederländische Reisepassnummer

### <a name="format"></a>Format

neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

neun Buchstaben oder Ziffern
  
### <a name="checksum"></a>Prüfsumme

nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_netherlands_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_netherlands_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet Datum im Format `Regex_netherlands_eu_passport_date` TT MMM/MMM JJJJ (Beispiel - 26 MAA/MAR 2012)

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_netherlands_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_netherlands_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Niederländische Steueridentifikationsnummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_netherlands_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_netherlands_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion  `Func_netherlands_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- zeitânske tax identification
- huweise impuesto id number
- hubild impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto identification number
- impuesto number
- untere unterlasting id nummer
- unterding identificatie
- unter anderem belasting identificatienummer
- untere unterlastingnummer
- phantomse belasting identificatie
- niederlande steueridentifikation
- Steueridentifikation von Netherland
- netherlands tin
- Netherland's tin
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- Steueridentifikationssatz
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- tax tal
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Niederländische Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 14 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 14 Zeichen:

- N oder n
- L oder l
- Optionaler Leerzeichen, Punkt oder Bindestrich
- neun Ziffern
- Optionaler Leerzeichen, Punkt oder Bindestrich
- B oder b
- zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_netherlands_value_added_tax_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_netherlands_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_netherlands_value_added_tax_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- uSt-Nummer
- vat no
- vat #
- wearde tafoege tax getal
- btw n'mer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Bankkontonummer für Neuseeland
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Muster mit 14 bis 16 Ziffern mit optionalem Trennzeichen

### <a name="pattern"></a>Muster

Muster mit 14 bis 16 Ziffern mit optionalem Trennzeichen:

- zwei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei bis vier Ziffern
- Optionaler Bindestrich oder Leerzeichen
- sieben Ziffern
- Optionaler Bindestrich oder Leerzeichen
- zwei bis drei Ziffern
- Ein Optionsbindestrich oder Leerzeichen

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_new_zealand_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_new_zealand_bank_account_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_new_zealand_bank_account_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- Bankkonto
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>New Zealand driver's license number
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit acht Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit acht Zeichen

- zwei Buchstaben 
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_newzealand_driver_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_newzealand_driver_license_number gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion Func_newzealand_driver_license_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's licence #
- Driver's licences #
- international driving permit
- international driving permits
- nz automobile association
- Neuseeländischer Autoverbund


## <a name="new-zealand-inland-revenue-number"></a>New Zealand inland revenue number
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht oder neun Ziffern mit optionalen Trennzeichen

### <a name="pattern"></a>Muster

Acht oder neun Ziffern mit optionalen Trennzeichen

- zwei oder drei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- drei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_new_zealand_inland_revenue_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_new_zealand_inland_revenue_number gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_new_zealand_inland_revenue_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird no.
- ird no #
- nz ird
- Neuseeland ird
- ird number
- Inlandsumsatznummer


## <a name="new-zealand-ministry-of-health-number"></a>Gesundheitsministeriumsnummer neuseelands

### <a name="format"></a>Format

drei Buchstaben, ein Leerzeichen (optional) und vier Ziffern

### <a name="pattern"></a>Muster

- Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet), mit Ausnahme von "I" und "O"
- Ein Leerzeichen (optional) 
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_nz_terms wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- Gesundheitswesen
- behandlung
- National Health Index Number
- nhi number
- nhi nein.
- NHI #
- National Health Index No.
- National Health Index Id
- National Health Index #

## <a name="new-zealand-social-welfare-number"></a>Telefonnummer für soziale Netzwerke in Neuseeland

Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

- drei Ziffern
- Optionaler Bindestrich
- drei Ziffern
- Ein optionaler Bindestrich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_newzealand_social_welfare_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_newzealand_social_welfare_number gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion Func_newzealand_social_welfare_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- soziale Netzwerke #
- soziale Netzwerke #
- Soziale Netzwerke Nein.
- Social social social social number
- swn #

   
## <a name="norway-identification-number"></a>Norwegische Identifikationsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- sechs Ziffern im Format DDMMYY, die das Geburtsdatum sind 
- Dreistellige einzelne Zahl 
- Zwei Prüfziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_norway_id_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_norway_id_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_norway_id_numbe findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Identifikation
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Philippinen einheitliche mehrzweckige Identifikationsnummer

### <a name="format"></a>Format

12 Ziffern, durch Bindestriche getrennt

### <a name="pattern"></a>Muster

12 Ziffern:
- vier Ziffern 
- Ein Bindestrich 
- sieben Ziffern 
- Ein Bindestrich 
- Eine Ziffer

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_philippines_unified_id inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keyword_philippines_id gefunden.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- UMID 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Polnische Führerscheinnummer

### <a name="format"></a>Format

14 Ziffern mit 2 Schrägstrichen
  
### <a name="pattern"></a>Muster

14 Ziffern und 2 Schrägstriche:
  
- fünf Ziffern 
- Schrägstrich
- zwei Ziffern
- Schrägstrich
- sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_poland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_poland_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver A0 s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Polnische Identitätskarte

### <a name="format"></a>Format

drei Buchstaben und sechs Ziffern

### <a name="pattern"></a>Muster

drei Buchstaben (Groß-/Kleinschreibung nicht beachtet), gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_polish_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osofelderty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.

   
## <a name="poland-national-id-pesel"></a>Nationale polnische ID (PESEL)

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

- 6 Ziffern, die das Geburtsdatum im Format "YYMMDD" darstellen
- 4 Ziffern
- 1 Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_pesel_identification_number wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osofelderty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>Polnische Reisepassnummer
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "EU Passport Number" enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

zwei Buchstaben und sieben Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_polish_passport_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Polen -REGON-Nummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern oder 14 Ziffern

### <a name="pattern"></a>Muster

neunstellige oder 14-stellige Nummer:

- neun Ziffern oder 
- neun Ziffern
- Bindestrich
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_polish_regon_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_polish_regon_number gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_polish_regon_number findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- Statistische Zahl
- Statistische ID
- statistisches Nein
- Regonnummer
- regonid #
- regonno #
- Unternehmens-ID
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Polnische Steueridentifikationsnummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_poland_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_poland_eu_tax_file_number` gefunden. 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- vat id #
- vat id
- vat no
- uSt-Nummer
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Portugal Citizen Card Number

### <a name="format"></a>Format

acht Ziffern

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_portugal_citizen_card findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_portugal_citizen_card gefunden.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- Citizen Card
- Dokumentnummer
- documento de identificação
- id number
- identification no
- identification number
- identity card no
- Identitätskartennummer
- national id card
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>Portugal driver's license number

### <a name="format"></a>Format

zwei Muster – zwei Buchstaben gefolgt von 5-8 Ziffern mit Sonderzeichen
  
### <a name="pattern"></a>Muster

Muster 1: Zwei Buchstaben gefolgt von 5/6 mit Sonderzeichen:
- Zwei Buchstaben (groß-/kleinschreibungsempfindlich)
- Ein Bindestrich 
- Fünf oder sechs Ziffern
- Ein Leerzeichen
- Eine Ziffer

Muster 2: Ein Buchstabe gefolgt von 6/8 Ziffern mit Sonderzeichen:
- Ein Buchstabe (ohne Schreibung)
- Ein Bindestrich 
- Sechs oder acht Ziffern
- Ein Leerzeichen
- Eine Ziffer

    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_portugal_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver A0 s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Portugal - Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe gefolgt von sechs Ziffern:
  
- Ein Buchstabe (ohne Schreibung)
- sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_portugal_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet das Datum im Format "DD.MM.JJJJ" oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_portugal_eu_passport_number` wurde gefunden.
    
```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- portugiesischer Reisepass
- portugiesischer Passeport
- portugiesisch passaporte
- passaporte nº
- passeport nº
- números de passaporte
- portugiesischen Passes
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="portugal-tax-identification-number"></a>Portugal Steueridentifikationsnummer

### <a name="format"></a>Format

neun Ziffern mit optionalen Leerzeichen
  
### <a name="pattern"></a>Muster

- 3 Ziffern
- Ein optionales Leerzeichen
- 3 Ziffern
- Ein optionales Leerzeichen
- 3 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_portugal_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_portugal_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_portugal_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- numero fiscal
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Führerscheinnummer für Rumänien

### <a name="format"></a>Format

Ein Zeichen gefolgt von acht Ziffern
  
### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von acht Ziffern:
- Ein Buchstabe (ohne Schreibung) oder Ziffer 
- acht Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_romania_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_romania_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver A0 s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Rumänien – persönlicher numerischer Code (CNP)
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

- 1 Ziffer von 1 bis 9
- 6 Ziffern, die das Geburtsdatum darstellen (YYMMDD)
- 2 Ziffern, die 01-52 oder 99 sein können
- 4 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_romania_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_romania_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_romania_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- Versicherungsnummer
- insurancenumber #
- national id #
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- Persönlicher numerischer Code
- pin #
- pin
- Steuerdatei nein
- tax file number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #
- Eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Rumänien – Reisepassnummer

### <a name="format"></a>Format

Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

acht oder neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_romania_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_romania_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck findet Das Datum im Format `Regex_romania_eu_passport_date` TT MMM/MMM JJ (Beispiel- 01 FEB/FEB 10) oder ein Schlüsselwort `Keywords_eu_passport_date` gefunden wurde

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_romania_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_romania_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="russia-passport-number-domestic"></a>Russische Reisepassnummer Inland
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Zehnstellige Nummer

### <a name="pattern"></a>Muster

Zehnstellige Nummer:

- zwei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- zwei Ziffern
- Ein optionales Leerzeichen
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Regex_Russian_Passport_Number_Domestic findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Russian_Passport_Number gefunden.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Russische Reisepassnummer international
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neunstellige Zahl

### <a name="pattern"></a>Muster

neunstellige Zahl:

- zwei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Regex_Russian_Passport_Number_International findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Russian_Passport_Number gefunden.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- passport no
- passport #
- passport id
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>Saudi-Arabische Ausweisnummer

### <a name="format"></a>Format

zehn Ziffern

### <a name="pattern"></a>Muster

Zehn aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_saudi_arabia_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_saudi_arabia_national_id wurde gefunden.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Singapore national registration identity card (NRIC) number

### <a name="format"></a>Format

neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

- neun Buchstaben und Ziffern:
- Der Buchstabe "F", "G", "S" oder "T" (ohne Schreibung) 
- sieben Ziffern 
- Eine alphabetische Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_singapore_nric gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- IC 
- Foreign Identification Number 
- FIN 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Führerscheinnummer der Slowakei

### <a name="format"></a>Format

Ein Zeichen gefolgt von sieben Ziffern
  
### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von sieben Ziffern
  
- Ein Buchstabe (ohne Schreibung) oder Ziffer
- sieben Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_slovakia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_slovakia_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver A0 s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Persönliche Rufnummer der Slowakei
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun oder zehn Ziffern mit optionalem umgekehrten Schrägstrich
  
### <a name="pattern"></a>Muster

- 6 Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich (/)
- 3 Ziffern
- 1 optionale Prüfziffer
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_slovakia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_slovakia_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion  `Func_slovakia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- Geburtsnummer
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id number
- identification no
- identification number
- identifikačná karta č
- identifikačné číslo
- identity card no
- Identitätskartennummer
- národná identifikačná značka č
- nationale Nummer
- nationalnumber #
- nemzeti személyazonosító igkrüvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igkrüvány szám
- személyi igkrüvány száma
- személyigamentovány szám
- Steuerdatei nein
- tax file number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Slowakei - Reisepassnummer

### <a name="format"></a>Format

Eine Ziffer oder ein Buchstabe gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Eine Ziffer oder ein Buchstabe (ohne Schreibung) gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_slovakia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_slovakia_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Das Datum im Format TT.MM.JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_slovakia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_slovakia_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="slovenia-drivers-license-number"></a>Slowenisch - Führerscheinnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_slovenia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_slovenia_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver A0 s_license_number

- vozniško dovoljenje
- vozniška številka licence
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Slowenien Eindeutige Master Citizen Number
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern im angegebenen Muster:
  
- sieben Ziffern, die dem Geburtsdatum (DDMMLLL) entsprechen, wobei "LLL" den letzten drei Ziffern des Geburtsjahrs entspricht 
- zwei Ziffern, die dem Geburtsbereich "50" entsprechen
- drei Ziffern, die einer Kombination aus Geschlecht und Seriennummer für Personen entsprechen, die am selben Tag auf die Welt gekommen sind (000-499 für Männlich und 500-999 für Frauen)
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_slovenia_eu_national_id_card` gefunden. 
    
Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_national_id_card` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- identity card
- nacionalna id
- nacionalni potni list
- national id
- osebna izkaznica
- osebni iba
- osebni ne
- osebni številka
- Persönlicher Code
- Persönliche Nummer
- Persönlicher numerischer Code
- številka državljana
- Eindeutige Citizen Number
- Eindeutige ID-Nummer
- Eindeutige Identitätsnummer
- Eindeutige Haupt-Citizen-Nummer
- Eindeutige Registrierungsnummer
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Slowenien - Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

zwei Buchstaben gefolgt von sieben Ziffern:
  
- Der Buchstabe "P"
- Ein Großbuchstabe
- sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_slovenia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_slovenia_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Das Datum im Format TT.MM.JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovenia_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_slovenia_eu_passport_number` wurde gefunden. 
    
```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni list #
- datum rojstva
- potni list
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="slovenia-tax-identification-number"></a>Slowenien - Steueridentifikationsnummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

- Eine Ziffer von 1 bis 9
- sechs Ziffern
- Eine Prüfziffer
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_slovenia_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie ist nur wenig sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn:
- Die Funktion  `Func_slovenia_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- Steuerdatei nein
- tax file number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Südafrika - Identifikationsnummer

### <a name="format"></a>Format

13 Ziffern, die Leerzeichen enthalten können

### <a name="pattern"></a>Muster

13 Ziffern:
- sechs Ziffern im Format "YYMMDD", die das Geburtsdatum sind 
- vier Ziffern 
- Ein einstelliger Indikator für die Bürgerschaft 
- die Ziffer "8" oder "9" 
- Eine Ziffer, bei der es sich um eine Prüfsummenziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_south_africa_identification_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_south_africa_identification_number gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Identifikation 
   
## <a name="south-korea-resident-registration-number"></a>South Korea resident registration number

### <a name="format"></a>Format

13 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

13 Ziffern:
- sechs Ziffern im Format "YYMMDD", die das Geburtsdatum sind 
- Ein Bindestrich 
- Eine Ziffer, die durch das Geschlecht und das Geschlecht bestimmt wird 
- Vierstelliger Code für Geburtsregion 
- Eine Ziffer, die verwendet wird, um Personen zu unterscheiden, für die die vorherigen Nummern identisch sind 
- eine Prüfziffer.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_south_korea_resident_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_south_korea_resident_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_south_korea_resident_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Spanische Führerscheinnummer

### <a name="format"></a>Format

Acht Ziffern gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

acht Ziffern gefolgt von einem Zeichen:
  
- acht Ziffern 
- Eine Ziffer oder ein Buchstabe (ohne Schreibung)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_spain_eu_driver's_license_number` wurde gefunden. 

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- Driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- Driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver A0 s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>Spanien DNI
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

sieben Ziffern gefolgt von einem Zeichen
  
- acht Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- Ein Prüfbuchstabe (ohne Schreibung)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_spain_eu_national_id_card"` gefunden. 

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` findet Inhalte, die dem Muster entsprechen. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- Versicherungsnummer
- national identification number
- nationale Identität
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- Persönliche Identifikationsnummer
- Persönliche Identität nein
- Eindeutige Identitätsnummer
- uniqueid #

## <a name="spain-passport-number"></a>Spanische Reisepassnummer

### <a name="format"></a>Format

Eine kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Eine kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:
  
- zwei Ziffern oder Buchstaben 
- Eine Ziffer oder ein Buchstabe (optional)
- sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_spain_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_spain_eu_passport_number` wurde gefunden. 
- Der reguläre Ausdruck `Regex_spain_eu_passport_date` findet Datum im Format TT-MM-JJJJ oder ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_spain_eu_passport_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_passport_number` oder `Keywords_spain_eu_passport_number` wurde gefunden.
    
```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- Passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- Reisepassnummern

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- zeitiertta pasaporte
- número pasaporte
- espña pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- spanien passport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="spain-social-security-number-ssn"></a>Spanische Sozialversicherungsnummer (SSN)

### <a name="format"></a>Format

11-12 Ziffern

### <a name="pattern"></a>Muster

11-12 Ziffern:
- zwei Ziffern 
- Schrägstrich (optional) 
- sieben bis acht Ziffern 
- Schrägstrich (optional) 
- zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_spanish_social_security_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Keine

## <a name="spain-tax-identification-number"></a>Spanische Steueridentifikationsnummer
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster
  
### <a name="pattern"></a>Muster

Spanische natürliche Personen mit spanischem Personalausweis:
  
- acht Ziffern 
- Ein Großbuchstabe (Groß-/Kleinschreibung wird beachtet) 
    
Gebietsansässige Spaniards ohne spanische Personalausweis
  
- Ein Großbuchstabe "L" (Groß-/Kleinschreibung wird beachtet)
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung wird beachtet) 
    
Gebietsansässige Spaniarden unter 14 Jahren ohne spanische Personalausweis:
  
- ein Großbuchstabe "K" (Groß-/Kleinschreibung wird beachtet)
- sieben Ziffern 
- Ein Großbuchstabe (Groß-/Kleinschreibung wird beachtet)
    
Mit einer Identifikationsnummer des Identifizierungszeichens
  
- Ein Großbuchstabe, der "X", "Y" oder "Z" ist (Groß-/Kleinschreibung wird beachtet) 
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung wird beachtet) 
    
Bezahlzeichen ohne Identifikationsnummer des Identifizierungszeichens
  
- Ein Großbuchstabe, der "M" ist (Groß-/Kleinschreibung wird beachtet) 
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung wird beachtet) 
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_spain_eu_tax_file_number` oder `Func_spain_eu_DL_and_NI_number_citizen` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_spain_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_spain_eu_tax_file_number` oder `Func_spain_eu_DL_and_NI_number_citizen` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- Steuerdatei nein
- tax file number
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "User ID", "User ID", "uid" oder "UserId", gefolgt von den Im folgenden Muster beschriebenen Zeichen und Zeichenfolgen.

### <a name="pattern"></a>Muster

- die Zeichenfolge "User ID", "User ID", "uid" oder "UserId"
- Beliebige Kombination aus 1-200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "Password" oder "pwd", wobei "pwd" keinem Kleinbuchstaben vorangehen
- Ein Gleichheitszeichen (=)
- Ein beliebiges Zeichen, das kein Dollarzeichen ($), Prozentzeichen (%) größer als Symbol (>), bei Symbol (@), Anführungszeichen ("), Semikolon (;), linke geschweifte Klammer([) oder linke Klammer ({) ist
- Beliebige Kombination aus 7 bis 128 Zeichen, die kein Semikolon (;), Schrägstrich (/) oder Anführungszeichen (") sind
- Ein Semikolon (;) oder Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck CEP_Regex_SQLServerConnectionString findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus CEP_GlobalFilter **wurde nicht** gefunden.
- Der reguläre Ausdruck CEP_PasswordPlaceHolder **findet keine** Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords **findet keine** Inhalte, die dem Muster entsprechen.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- Beispiel

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- Kennwort oder Pwd gefolgt von 0-2 Leerzeichen, einem Gleichheitszeichen (=), 0-2 Leerzeichen und einem Sternchen (*) --OR--
- Kennwort oder Pwd gefolgt von:
    - Gleichheitszeichen (=)
    - Kleiner als Symbol (<)
    - Eine beliebige Kombination aus 1 bis 200 Zeichen, die Groß- oder Kleinbuchstaben, Ziffern, Ein Sternchen (*), Bindestrich (-), Unterstreichung (_) oder Leerzeichen sind
    - Größer als Symbol (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mithilfe eines regulären Ausdrucks und nicht einer Schlüsselwortliste identifiziert.)

- contoso
- fabrikam
- northwind
- Sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Führerscheinnummer Für Schweden

### <a name="format"></a>Format

Zehn Ziffern mit einem Bindestrich
  
### <a name="pattern"></a>Muster

zehn Ziffern mit einem Bindestrich:
  
- sechs Ziffern 
- Ein Bindestrich
- vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck  `Regex_sweden_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen. 
- Ein Schlüsselwort aus  `Keywords_eu_driver's_license_number` oder `Keywords_sweden_eu_driver's_license_number` wurde gefunden. 
    
```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver A0 s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- Driver' license
- driver' licenses
- Driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- Driver's lics
- driver's license
- driver's licenses
- driver's licence
- Driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver' lic #
- driver' lics #
- driver' license #
- driver' licenses #
- Driver' licence #
- driver' licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- driver's lic #
- Driver's lics #
- Driver's license #
- Driver's licenses #
- Driver's licence #
- driver's licences #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- driv license
- driv licenses
- driv licence
- driv licences
- driver licen
- drivers licen
- Driver's licen
- driving lic
- Driving licen
- Driving Licenses
- driving licence
- driving licences
- Driving Permit
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver A0 s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Nationale Id für Schweden

### <a name="format"></a>Format

zehn oder 12 Ziffern und ein optionales Trennzeichen

### <a name="pattern"></a>Muster

zehn oder 12 Ziffern und ein optionales Trennzeichen:
- zwei Ziffern (optional) 
- Sechs Ziffern im Datumsformat JJMMTT 
- Trennzeichen von "-" oder "+" (optional)
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion `Func_swedish_national_identifier` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keywords_swedish_national_identifier` gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion `Func_swedish_national_identifier` findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id number
- id #
- identification no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- Identitätsdokument
- Identity no
- Identitätsnummer
- id-nummer
- Persönliche ID
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Reisepassnummer Für Schweden
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "EU Passport Number" enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

acht Ziffern

### <a name="pattern"></a>Muster

Acht aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_sweden_passport_number inhalt, der dem Muster entspricht.
- Eine der folgenden Bedingungen ist wahr:
    - Ein Schlüsselwort aus Keyword_passport gefunden.
    - Ein Schlüsselwort aus Keyword_sweden_passport gefunden.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- ポ . 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- Passeport # 
- PasseportNon 
- Passeportn ° 


## <a name="sweden-tax-identification-number"></a>Steueridentifikationsnummer für Schweden
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Zehn Ziffern und ein Symbol im angegebenen Muster
  
### <a name="pattern"></a>Muster

zehn Ziffern und ein Symbol:
  
- sechs Ziffern, die dem Geburtsdatum entsprechen (YYMMDD) 
- Ein Plus- oder Minuszeichen
- drei Ziffern, die die Identifikationsnummer eindeutig machen, wobei: 
  - für Nummern, die vor 1990 ausgestellt wurden, identifizieren die siebte und die achte Ziffer den Geburtslandkreis oder fremde Personen.
  - Die Ziffer an der neunten Position gibt das Geschlecht entweder ungerade für Männlich oder sogar für Frau an.
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_sweden_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_sweden_eu_tax_file_number` gefunden. 
    
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion  `Func_sweden_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
    
```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- Persönliche ID-Nummer
- personnummer
- skatt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- Steuerdatei
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuernummer
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #


## <a name="swift-code"></a>SWIFT-Codes

### <a name="format"></a>Format

vier Buchstaben gefolgt von 5-31 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

vier Buchstaben gefolgt von 5-31 Buchstaben oder Ziffern:
- Vierbuchstaben-Bankleitzahl (Groß-/Kleinschreibung nicht beachtet) 
- Ein optionales Leerzeichen 
- 4 bis 28 Buchstaben oder Ziffern (BBAN, Basic Bank Account Number) 
- Ein optionales Leerzeichen 
- ein bis drei Buchstaben oder Ziffern (rest der BBAN)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_swift findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_swift wurde gefunden.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFT.
- SWIFT番
- BIC番
- BIC
- SWIFT
- SWIFT 番
- BIC 番
- BIC
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Schweiz SSN AHV-Nummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffernnummer:

- drei Ziffern – 756
- Optionaler Punkt
- vier Ziffern
- Optionaler Punkt
- vier Ziffern
- Optionaler Punkt
- zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_swiss_social_security_number_ahv findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keywords_swiss_social_security_number_ahv gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_swiss_social_security_number_ahv findet Inhalte, die dem Muster entsprechen.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- Versicherungsnummer
- personalidno #
- social security number
- Persönliche ID-Nummer
- Persönliche Identifikation nein.
- insuranceno #
- uniqueidno #
- eindeutige Identifikation nein.
- avs number
- Persönliche Identität no versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- identification personnelle id
- numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Taiwan national identification number

### <a name="format"></a>Format

Ein Buchstabe (in Englisch), gefolgt von neun Ziffern

### <a name="pattern"></a>Muster

Ein Buchstabe (in Englisch), gefolgt von neun Ziffern:
- ein Buchstabe (in Englisch, ohne Schreibung zu beachtet) 
- Die Ziffer "1" oder "2" 
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Taiwan Passport Number

### <a name="format"></a>Format

- Biometrische Reisepassnummer: neun Ziffern
- Nicht biometrische Reisepassnummer: neun Ziffern

### <a name="pattern"></a>Muster
Biometrische Reisepassnummer:
- Das Zeichen "3" 
- acht Ziffern

Nicht biometrische Reisepassnummer:
- neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_taiwan_passport inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keyword_taiwan_passport gefunden.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan resident certificate (ARC/TARC) number

### <a name="format"></a>Format

zehn Buchstaben und Ziffern

### <a name="pattern"></a>Muster

zehn Buchstaben und Ziffern:
- zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet) 
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_taiwan_resident_certificate inhalt, der dem Muster entspricht.
- Ein Schlüsselwort aus Keyword_taiwan_resident_certificate gefunden.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate 
- Resident Cert 
- Resident Cert. 
- Identification card 
- Alien Resident Certificate 
- ARC 
- Taiwan Area Resident Certificate 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Identifikationscode für thailändische Grundgesamtheiten

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffern:
- Erste Ziffer ist nicht null oder neun 
- 12 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_Thai_Citizen_Id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Thai_Citizen_Id gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_Thai_Citizen_Id findet Inhalte, die dem Muster entsprechen.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID Number
- Identifikationsnummer
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Nationale identifikationsnummer für Türkisch

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_Turkish_National_Id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Turkish_National_Id gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_Turkish_National_Id findet Inhalte, die dem Muster entsprechen.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik numarası
- Vatșşlık numarası
- Vatșşlık no

## <a name="uk-drivers-license-number"></a>Vereinigtes Königreich Driver's license number
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "EU Driver's License Number" enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

Kombination aus 18 Buchstaben und Ziffern im angegebenen Format

### <a name="pattern"></a>Muster

18 Buchstaben und Ziffern:
- fünf Buchstaben (Groß-/Kleinschreibung nicht beachtet) oder die Ziffer "9" statt eines Buchstabens 
- Eine Ziffer 
- fünf Ziffern im Datumsformat MMDDY für das Geburtsdatum (7. Zeichen wird um 50 erhöht, wenn der Treiber frau ist, d. h. 51 bis 62 anstelle von 01 bis 12)
- zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) oder die Ziffer "9" statt eines Buchstabens 
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_uk_drivers_license findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_uk_drivers_license wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quad aus 
- motor cars 
- 125cc 
- sidecar 
- tricycles 
- motorcycles 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>Vereinigtes Königreich die Nummer des Rollenrollings

### <a name="format"></a>Format

zwei Buchstaben gefolgt von 1-4 Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet), gefolgt von 1-4 Zahlen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_uk_electoral findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_uk_electoral wurde gefunden.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Vereinigtes Königreich Nationale Gesundheitsdienstnummer

### <a name="format"></a>Format

10-17 Ziffern, durch Leerzeichen getrennt

### <a name="pattern"></a>Muster

10 bis 17 Stellen:
- Drei oder zehn Ziffern 
- Ein Leerzeichen 
- drei Ziffern 
- Ein Leerzeichen 
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_uk_nhs_number findet Inhalte, die dem Muster entsprechen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_uk_nhs_number wurde gefunden.
    - Ein Schlüsselwort aus Keyword_uk_nhs_number1 wurde gefunden.
    - Ein Schlüsselwort aus Keyword_uk_nhs_number_dob wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- nhs 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D.O.B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>Vereinigtes Königreich national insurance number (NINO)
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "EU National Identificaiton Number" enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

sieben Zeichen oder neun Zeichen durch Leerzeichen oder Bindestriche getrennt

### <a name="pattern"></a>Muster

zwei mögliche Muster:

- zwei Buchstaben (gültige NINOs verwenden nur bestimmte Zeichen in diesem Präfix, die dieses Muster überprüft; groß-/klein geschrieben)
- sechs Ziffern
- Entweder 'A', 'B', 'C' oder 'D' (wie das Präfix sind nur bestimmte Zeichen im Suffix zulässig; die Kleinschreibung wird nicht beachtet)

OR

- zwei Buchstaben
- Ein Leerzeichen oder Gedankenstrich
- zwei Ziffern
- Ein Leerzeichen oder Gedankenstrich
- zwei Ziffern
- Ein Leerzeichen oder Gedankenstrich
- zwei Ziffern
- Ein Leerzeichen oder Gedankenstrich
- entweder "A", "B", "C" oder "D"

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art vertraulicher Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_uk_nino wurde gefunden.

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI Number
- NI Nein.
- NI #
- NI #
- insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>Vereinigtes Königreich Eindeutige Steuernummer
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen
 
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
- Die Funktion  `Func_uk_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen. 
- Es wurde ein Schlüsselwort  `Keywords_uk_eu_tax_file_number` gefunden. 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- Steuernummer
- Steuerdatei
- tax id
- steueridentifikation nein
- Steueridentifikationsnummer
- tax no #
- tax no
- Steuerregistrierungsnummer
- zeitd #
- zeitdno #
- zeitdnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- tin #

## <a name="us-bank-account-number"></a>US-Bankkontonummer

### <a name="format"></a>Format

6-17 Ziffern

### <a name="pattern"></a>Muster

6 bis 17 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Ausdruck Regex_usa_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_usa_Bank_Account wurde gefunden.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>US-Führerscheinnummer

### <a name="format"></a>Format

Abhängig vom Bundesstaat

### <a name="pattern"></a>Muster

hängt vom Status ab – z. B. New York:
- Neun Ziffern, die wie ddd ddd ddd formatiert sind, entsprechen.
- Neun Ziffern wie "ddddddd" entsprechen nicht.

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.
- Ein Schlüsselwort aus Keyword_us_drivers_license gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.
- Ein Schlüsselwort aus Keyword_us_drivers_license_abbreviations wurde gefunden.
- Es wurde kein Schlüsselwort aus Keyword_us_drivers_license gefunden.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- DLS 
- CDL 
- CDLS 
- ID 
- IDs 
- DL # 
- DLS # 
- CDL # 
- CDLS # 
- ID #
- IDs # 
- ID number 
- ID numbers 
- LIC 
- LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- Driver'Lic 
- Driver'Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification# 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- Abkürzung für Bundesland (z. B. "NY") 
- Statusname (z. B. "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>US-amerikanische Steuernummer (ITIN)

### <a name="format"></a>Format

neun Ziffern, die mit "9" beginnen und eine "7" oder "8" als vierte Ziffer enthalten, optional mit Leerzeichen oder Bindestrichen formatiert

### <a name="pattern"></a>Muster

formatiert:
- Die Ziffer "9" 
- zwei Ziffern 
- Ein Leerzeichen oder Gedankenstrich 
- "7" oder "8" 
- eine Ziffer 
- ein Leerzeichen oder Bindestrich 
- vier Ziffern

unformatiert:
- die Ziffer "9" 
- zwei Ziffern 
- eine "7" oder "8" 
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_formatted_itin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_itin wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_itin wurde gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_formatted_itin oder Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_itin"></a>Keyword_itin

- taxpayer 
- tax id 
- tax identification 
- itin 
- i.t.i.n.
- ssn 
- tin 
- social security 
- tax payer 
- itins 
- zeitd 
- individual taxpayer 


## <a name="us-social-security-number-ssn"></a>US-Sozialversicherungsnummer (SSN)

### <a name="format"></a>Format

neun Ziffern, die in einem formatierten oder unformatierten Muster vorliegen können

> [!NOTE]
> Wenn ein SSN vor Mitte 2011 ausgestellt wurde, verfügt er über eine starke Formatierung, bei der bestimmte Teile der Zahl innerhalb bestimmter Bereiche liegen müssen, um gültig zu sein (es gibt jedoch keine Prüfsumme).

### <a name="pattern"></a>Muster

Vier Funktionen suchen in vier verschiedenen Mustern nach SSNs:
- Func_ssn sucht SSNs mit starker Formatierung vor 2011, die mit Gedankenstrichen oder Leerzeichen formatiert sind (ddd-dd-dddd OR ddd dddd)
- Func_unformatted_ssn sucht SSNs mit starker Formatierung vor 2011, die als neun aufeinanderfolgende Ziffern unformatiert sind (ddddd)
- Func_randomized_formatted_ssn sucht nach 2011-SSNs, die mit Gedankenstrichen oder Leerzeichen formatiert sind (ddd-dd-dddd OR ddd dddd)
- Func_randomized_unformatted_ssn sucht nach 2011-SSNs, die als neun aufeinanderfolgende Ziffern unformatiert sind (ddddd)

### <a name="checksum"></a>Prüfsumme

Nein


### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist besonders sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_unformatted_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie ist nur wenig sicher, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb von 300 Zeichen:
- Die Funktion Func_randomized_formatted_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie ist zu 55 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_randomized_unformatted_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA Number
- social security number
- Sozialversicherung #
- Sozialversicherung #
- Sozialversicherung nein
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID
   
## <a name="us--uk-passport-number"></a>USA/Vereinigtes Königreich passport number
Vereinigtes Königreich Passport Number sensitive information type entity is available in the EU Passport Number sensitive information type and is available as a stand alone sensitive information type entity.

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Die Funktion Func_usa_uk_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_passport wurde gefunden.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Passport # 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- ポ . 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport# 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>Ukraine passport domestic
Dieser vertrauliche Informationstyp ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Regex_Ukraine_Passport_Domestic findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Ukraine_Passport_Domestic gefunden.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ukraine passport
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Ukraine passport international
Dieser Typ vertraulicher Informationen ist nur für die Verwendung in:
- Richtlinien zur Verhinderung von Datenverlust
- Kommunikationskonformitätsrichtlinien
- Informationssteuerung
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

alphanumerisches Muster mit acht Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit acht Zeichen:
- zwei Buchstaben oder Ziffern
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn:
- Der reguläre Regex_Ukraine_Passport_International findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Ukraine_Passport_International gefunden.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ukraine passport
- passport number
- passport no
- паспорт України
- номер паспорта