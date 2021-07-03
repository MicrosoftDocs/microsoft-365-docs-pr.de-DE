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
recommendations: false
description: Es gibt 200 Typen vertraulicher Informationen, die Sie in Ihren DLP-Richtlinien verwenden können. Dieser Artikel listet alle diese Typen vertraulicher Informationen auf und zeigt, wonach eine DLP-Richtlinie sucht, wenn sie jeden Typ erkennt.
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287467"
---
# <a name="sensitive-information-type-entity-definitions"></a>Entitätsdefinitionen für Typen vertraulicher Informationstypen

In diesem Artikel werden alle Entitätsdefinitionen für Typen vertraulicher Informationen aufgeführt. Jede Definition zeigt, wonach eine DLP-Richtlinie sucht, um jeden Typ zu erkennen. Weitere Informationen zu Typen vertraulicher Informationen finden Sie unter ["Typen vertraulicher Informationen".](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>ABA-Routingnummer

### <a name="format"></a>Format

neun Ziffern, die ein formatiertes oder unformatiertes Muster aufweisen können

### <a name="pattern"></a>Muster

- zwei Ziffern in den Bereichen 00-12, 21-32, 61-72 oder 80
- Zwei Ziffern
- Optionaler Bindestrich
- vier Ziffern
- Optionaler Bindestrich
- eine Ziffer


### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ABA_Routing wurde gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Aba #
- Aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- Americanbankassociationroutingnumber
- Bankrouting #
- Bankroutingnummer
- Routing #
- Routing nein
- Routingnummer
- routing transit number
- Routing #
- Rtn


## <a name="argentina-national-identity-dni-number"></a>Nationale Identität (DNI) für Argentinien

### <a name="format"></a>Format

Acht Ziffern mit oder ohne Punkte

### <a name="pattern"></a>Muster

Acht Ziffern:
- Zwei Ziffern
- Ein optionaler Zeitraum
- drei Ziffern
- Ein optionaler Zeitraum
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_argentina_national_id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_argentina_national_id gefunden.

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
- Cedula
- Cédula
- Dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- Rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Eindeutiger Steueridentifikationsschlüssel für Argentinien (CUIT/CUIL)

### <a name="format"></a>Format

11 Ziffern mit Strich

### <a name="pattern"></a>Muster

11 Ziffern mit einem Strich:
- Zwei Ziffern in 20, 23, 24, 27, 30, 33 oder 34
- Bindestrich (-)
- acht Ziffern
- Bindestrich (-)
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_Argentina_Unique_Tax_Key` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keyword_Argentina_Unique_Tax_Key` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_Argentina_Unique_Tax_Key` sucht Inhalte, die dem Muster entsprechen.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Codaria
- CUIT
- eindeutiger Code für die Identifizierung 
- Clave Única de Identificación Codarien
- eindeutiger Kenncode
- Cuil
- Eindeutiger Steueridentifikationsschlüssel
- Eindeutiger Schlüssel zur Identifizierung
- Eindeutiger Schlüssel der Identifikation
- Eindeutiger Arbeitsidentifikationscode
- Eindeutiger Code der Arbeitsidentifikation
- Eindeutiger Arbeitsschlüssel
- Eindeutiger Schlüssel der Arbeitsidentifikation
- Eindeutiger Steueridentifikationscode
- Eindeutiger Schlüssel der Steueridentifikation
- Eindeutiger Arbeitsidentifikationscode
- Eindeutige Arbeitscode-Identifikation
- Eindeutiger Arbeitsidentifikationsschlüssel
- Eindeutiger Schlüssel der Arbeitsidentifikation
- Steuer-ID
- taxID #
- taxId
- anzahl
- Steuernummer
- Steuernummer
- Steuer #
- Steuer #
- Kennung des Identifikationszeichen
- Zahl der Zahlen
- vererz nein
- Steuerzahler #
- Steuerzahler #
- Steueridentität
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>Bankkontonummer für Australien

### <a name="format"></a>Format

sechs bis 10 Ziffern mit oder ohne Zweigstellennummer des Bankstatus

### <a name="pattern"></a>Muster

Die Kontonummer ist 6 bis 10 Ziffern.

Australische Bankleitzahl:
- drei Ziffern
- Bindestrich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_australia_bank_account_number sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_australia_bank_account_number_bsb findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_australia_bank_account_number sucht Inhalte, die dem Muster entsprechen.

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
- Iaeo

## <a name="australia-business-number"></a>Geschäftliche Nummer für Australien
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security


### <a name="format"></a>Format

11 Ziffern mit optionalen Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern mit optionalen Trennzeichen:

- Zwei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_australian_business_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_australian_business_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_australian_business_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Australien Business No
- Geschäftsnummer
- Abn #
- Businessid #
- Geschäfts-ID
- Abn
- businessno #

## <a name="australia-company-number"></a>Firmennummer Australiens
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Australian_Company_Number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Australian_Company_Number gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Australian_Company_Number nach Inhalten sucht, die dem Muster entsprechen.

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

- Dose
- Australien Unternehmen Nein
- Australien Unternehmen Nein #
- Firmennummer australien
- Australisches Unternehmen Nein
- Australisches Unternehmen Nein #
- Australische Firmennummer

## <a name="australia-drivers-license-number"></a>Australische Führerscheinnummer

### <a name="format"></a>Format

neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

neun Buchstaben und Ziffern:

- zwei Ziffern oder Buchstaben (ohne Groß-/Kleinschreibung)
- Zwei Ziffern
- fünf Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

ODER

- 1 bis 2 optionale Buchstaben (Groß-/Kleinschreibung nicht beachten)
- vier bis neun Ziffern

ODER

- neun Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Führerschein
- Führerschein
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
- Führerschein #
- Führerschein #
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
- Führerschein
- Treiberlizenzen
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
- Führerschein #
- Treiberlizenzen #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#

## <a name="australia-medical-account-number"></a>Medizinische Kontonummer für Australien

### <a name="format"></a>Format

10-11 Ziffern

### <a name="pattern"></a>Muster

10-11 Ziffern:
- Erste Ziffer im Bereich von 2-6
- Neunte Ziffer ist eine Prüfziffer
- Zehnte Ziffer ist die Ausgabeziffer
- Elfte Ziffer (optional) ist die Einzelziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Medicare


## <a name="australia-passport-number"></a>Australische Reisepassnummer

### <a name="format"></a>Format

acht oder neun alphanumerische Zeichen

### <a name="pattern"></a>Muster

- ein Buchstabe (N, E, D, F, A, C, U, X), gefolgt von sieben Ziffern oder
- Zwei Buchstaben (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ), gefolgt von sieben Ziffern.

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck `Regex_australia_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keyword_australia_passport_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck `Regex_australia_passport_number` findet Inhalte, die dem Muster entsprechen.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>Australische Steuernummer

### <a name="format"></a>Format

acht bis neun Ziffern

### <a name="pattern"></a>Muster

Acht bis neun Ziffern werden in der Regel wie folgt mit Leerzeichen dargestellt:
- drei Ziffern
- Ein optionaler Bereich
- drei Ziffern
- Ein optionaler Bereich
- zwei bis drei Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Tfn

## <a name="austria-drivers-license-number"></a>Österreich-Führerscheinnummer

### <a name="format"></a>Format

acht Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_austria_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_austria_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver's_license_number

- umrennen
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Österreich-Identitätskarte
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Eine 24-Zeichen-Kombination aus Buchstaben, Ziffern und Sonderzeichen

### <a name="pattern"></a>Muster

24 Zeichen:

-  22 Buchstaben (ohne Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche, Schrägstriche oder Pluszeichen

- zwei Buchstaben (ohne Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche, Schrägstriche, Pluszeichen oder Gleichheitszeichen

### <a name="checksum"></a>Prüfsumme

Nicht anwendbar

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_austria_eu_national_id_card` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_austria_eu_national_id_card` gefunden.

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
- slowakei republik österreich

## <a name="austria-passport-number"></a>Österreich-Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von einem optionalen Leerzeichen und sieben Ziffern

### <a name="pattern"></a>Muster

Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:

- ein Buchstabe (ohne Groß-/Kleinschreibung)
- ein Leerzeichen (optional)
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

nicht zutreffend

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_austria_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_austria_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_austria_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_austria_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reise wie

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum

## <a name="austria-social-security-number"></a>Sozialversicherungsnummer Österreichs

### <a name="format"></a>Format

10 Ziffern im angegebenen Format

### <a name="pattern"></a>Muster

10 Ziffern:

- drei Ziffern, die einer Seriennummer entsprechen
- eine Prüfziffer
- sechs Ziffern, die dem Geburtsdatum entsprechen (DDMMYY)

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_austria_eu_ssn_or_equivalent` sucht Inhalte, die dem Muster entsprechen.
- es wurde ein Schlüsselwort  `Keywords_austria_eu_ssn_or_equivalent` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_austria_eu_ssn_or_equivalent` sucht Inhalte, die dem Muster entsprechen.

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

- ssn
- ehic number
- ehic no
- Versicherungscode
- insurancecode #
- Versicherungsnummer
- Versicherungsnr.
- deren Nummer
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
- Ssn #
- Ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zovanje

## <a name="austria-tax-identification-number"></a>Steueridentifikationsnummer Österreichs

### <a name="format"></a>Format

Neun Ziffern mit optionalem Bindestrich und Schrägstrich

### <a name="pattern"></a>Muster

neun Ziffern mit optionalem Bindestrich und Schrägstrich:

- Zwei Ziffern
- Bindestrich (optional)
- drei Ziffern
- Schrägstrich (optional)
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_austria_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_austria_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_austria_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- Steuernummer

## <a name="austria-value-added-tax"></a>Österreich-Mehrwertsteuer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 11 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 11 Zeichen:

- A oder a
- T oder t
- Optionaler Speicherplatz
- U oder U
- Optionaler Speicherplatz
- zwei oder drei Ziffern
- Optionaler Speicherplatz
- vier Ziffern
- Optionaler Speicherplatz
- eine oder zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Austria_Value_Added_Tax nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Austria_Value_Added_Tax gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Austria_Value_Added_Tax nach Inhalten sucht, die dem Muster entsprechen.

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

- Umsatzsteuernummer
- Mwst #
- umsatzsteuernummer
- vat no.
- vatno #
- Umsatzsteuernummer
- vat
- kwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- Umsatzsteuer-Identifikationsnummer
- atu number
- uid-Nummer


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB-Authentifizierungsschlüssel

### <a name="format"></a>Format

Die Zeichenfolge "DocumentDb", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "DocumentDb"
- Eine Kombination aus 3 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Ein größer als-Symbol (>), ein Gleichheitszeichen (=), ein Anführungszeichen (") oder ein Apostroph (')
- Eine beliebige Kombination aus 86 Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureDocumentDBAuthKey sucht Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS-Datenbankverbindungszeichenfolge und Azure SQL Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Server", "Server" oder "Datenquelle", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind, einschließlich der Zeichenfolge "cloudapp.azure".<!--no-hyperlink-->com" oder "cloudapp.azure.<!--no-hyperlink-->net" oder "database.windows.<!--no-hyperlink-->net" und die Zeichenfolge "Password" oder "password" oder "pwd".

### <a name="pattern"></a>Muster

- die Zeichenfolge "Server", "Server" oder "Datenquelle"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" oder "database.windows".<!--no-hyperlink-->net"
- Eine beliebige Kombination aus 1 bis 300 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "Password", "password" oder "pwd"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- ein oder mehrere Zeichen, die kein Semikolon (;), Anführungszeichen (") oder Apostroph (') sind
- ein Semikolon (;), Anführungszeichen (") oder Apostroph (')

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureConnectionString sucht Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-iot-connection-string"></a>Azure IoT Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "HostName", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind, einschließlich der Zeichenfolgen "azure-devices".<!--no-hyperlink-->net" und "SharedAccessKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "HostName"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "azure-devices.<!--no-hyperlink-->net"
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "SharedAccessKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Beliebige Kombination aus 43 Klein- oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureIoTConnectionString nach Inhalten sucht, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-publish-setting-password"></a>Kennwort für Azure-Veröffentlichungseinstellung

### <a name="format"></a>Format

Die Zeichenfolge "userpwd=" gefolgt von einer alphanumerischen Zeichenfolge.

### <a name="pattern"></a>Muster

- die Zeichenfolge "userpwd="
- Beliebige Kombination aus 60 Kleinbuchstaben oder Ziffern
- ein Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzurePublishSettingPasswords nach Inhalten sucht, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.


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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-redis-cache-connection-string"></a>Azure Redis-Cacheverbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "redis.cache.windows.<!--no-hyperlink-->net" gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind, einschließlich der Zeichenfolge "password" oder "pwd".

### <a name="pattern"></a>Muster

- die Zeichenfolge "redis.cache.windows.<!--no-hyperlink-->net"
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "password" oder "pwd"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine Kombination aus 43 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstriche (/) oder Pluszeichen (+) sind
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureRedisCacheConnectionString sucht Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Format

Die Zeichenfolge "sig" gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind.

### <a name="pattern"></a>Muster

- die Zeichenfolge "sig"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 43 bis 53 Zeichen, bei denen es sich um Klein- oder Großbuchstaben, Ziffern oder das Prozentzeichen (%)
- die Zeichenfolge "%3d"
- Alle Zeichen, bei denen es sich nicht um klein- oder groß geschriebene Zeichen, Ziffern oder Prozentzeichen handelt (%)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureSAS sucht Inhalte, die dem Muster entsprechen.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Verbindungszeichenfolge für Azure-Servicebus

### <a name="format"></a>Format

Die Zeichenfolge "EndPoint", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind, einschließlich der Zeichenfolgen "servicebus.windows".<!--no-hyperlink-->net" und "SharedAccesKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "EndPoint"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "servicebus.windows.<!--no-hyperlink-->net"
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "SharedAccessKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine Kombination aus 43 Zeichen, die Klein- oder Großbuchstaben, Ziffern, Schrägstriche (/) oder Pluszeichen (+) sind
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureServiceBusConnectionString nach Inhalten sucht, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-storage-account-key"></a>Azure-Speicherkontoschlüssel

### <a name="format"></a>Format

Die Zeichenfolge "DefaultEndpointsProtocol", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind, einschließlich der Zeichenfolge "AccountKey".

### <a name="pattern"></a>Muster

- die Zeichenfolge "DefaultEndpointsProtocol"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "AccountKey"
- Null bis zwei Leerzeichen
- Ein Gleichheitszeichen (=)
- Null bis zwei Leerzeichen
- Eine beliebige Kombination aus 86 Zeichen, bei denen es sich um Klein- oder Großbuchstaben, Ziffern, Schrägstriche (/) oder Pluszeichen (+) handelt
- zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKey nach Inhalten sucht, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_AzureEmulatorStorageAccountFilter findet keine Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Technisch gesehen identifiziert dieser Typ vertraulicher Informationen diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht einer Schlüsselwortliste.)

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="azure-storage-account-key-generic"></a>Azure Storage Kontoschlüssel (generisch)

### <a name="format"></a>Format

Eine Beliebige Kombination aus 86 Klein- oder Großbuchstaben, Ziffern, schrägem Schrägstrich (/) oder Pluszeichen (+), vor oder gefolgt von den Zeichen, die im folgenden Muster umrissen sind.

### <a name="pattern"></a>Muster

- null bis zu einem der Größer-als-Zeichen (>), Apostroph ('), Gleichheitszeichen (=), Anführungszeichen (") oder Nummernzeichen (#)
- Eine beliebige Kombination aus 86 Zeichen, bei denen es sich um Klein- oder Großbuchstaben, Ziffern, den Schrägstrich (/) oder das Pluszeichen (+) handelt
- zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKeyGeneric sucht Inhalte, die dem Muster entsprechen.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Belgien– Führerscheinnummer

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_belgium_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_driver's_license_number` oder `Keywords_belgium_eu_driver's_license_number` wird gefunden.

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


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver's_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- umrennen
- fuehrerschein
- wirderscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Nationale Zahl Belgiens

### <a name="format"></a>Format

11 Ziffern plus optionale Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern plus Trennzeichen:
- sechs Ziffern und zwei optionale Punkte im Format JJ. MM.DD für das Geburtsdatum
- Ein optionales Trennzeichen aus Punkt, Strich, Abstand
- drei sequenzielle Ziffern (ungerade Ziffern für Männchen, sogar für Frau)
- Ein optionales Trennzeichen aus Punkt, Strich, Abstand
- Zwei Prüfziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_belgium_national_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_belgium_national_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_belgium_national_number nach Inhalten sucht, die dem Muster entsprechen.
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
- Bnn #
- Bnn
- carte d'identité
- identifiant national
- identifiantnational #
- identificatie
- Identifizierung
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- Identität
- Inschrift
- nationale Nummer
- Nationales Register
- nationale Zahl #
- nationale Zahl
- Nif #
- Nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational #
- Persönliche ID-Nummer
- - (in)
- Personalidnummer #
- registratie
- Registrierung
- registrationsnumme
- Registrierung
- social security number
- Ssn #
- Ssn
- steuernummer
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #

## <a name="belgium-passport-number"></a>Belgien –Reisepassnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

zwei Buchstaben und gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

nicht zutreffend

### <a name="definition"></a>Definition

 Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_belgium_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_belgium_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date2` sucht datums im Format DD MM JJJ oder ein Schlüsselwort aus `Keywords_eu_passport_date` oder wird `Keywords_belgium_eu_passport_number` gefunden

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_belgium_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_belgium_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport- und Passeport-Kennung
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum

## <a name="belgium-value-added-tax-number"></a>Belgien - Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 12 Zeichen

### <a name="pattern"></a>Muster

12-Zeichen-Alphanumerisches Muster:

- a letter B or b
- ein Buchstabe E oder e
- Eine Ziffer 0
- Eine Ziffer von 1 bis 9
- Optionaler Punkt oder Bindestrich oder Leerzeichen
- vier Ziffern
- Optionaler Punkt oder Bindestrich oder Leerzeichen
- vier Ziffern


### <a name="checksum"></a>Prüfsumme

Ja


### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_belgium_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_belgium_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_belgium_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- nế tva
- Umsatzsteuernummer
- umsatzsteuer-Nr.
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- übrigens
- übrigens #
- Mwst #


## <a name="brazil-cpf-number"></a>Brasilien CPF-Nummer

### <a name="format"></a>Format

11 Ziffern, die eine Prüfziffer umfassen und die formatiert oder unformatiert sein können

### <a name="pattern"></a>Muster

Formatiert:
- drei Ziffern
- ein Punkt
- drei Ziffern
- ein Punkt
- drei Ziffern
- Bindestrich
- Zwei Ziffern, bei denen es sich um Prüfziffern handelt

Unformatierte:
- 11 Ziffern, wobei die letzten beiden Ziffern Prüfziffern sind

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_brazil_cpf nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_brazil_cpf gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_brazil_cpf nach Inhalten sucht, die dem Muster entsprechen.
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

- Cpf
- Identifizierung
- Registrierung
- Einnahmen
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>Brasilianische Juristische Entitätsnummer (CNPJ)

### <a name="format"></a>Format

14 Ziffern, die eine Registrierungsnummer, eine Zweignummer und Prüfnziffern sowie Trennzeichen umfassen

### <a name="pattern"></a>Muster

14 Ziffern plus Trennzeichen:

- Zwei Ziffern
- ein Punkt
- drei Ziffern
- ein Punkt
- drei Ziffern (diese ersten acht Ziffern sind die Registrierungsnummer)
- Schrägstrich
- Vierstellige Verzweigungsnummer
- Bindestrich
- Zwei Ziffern, bei denen es sich um Prüfziffern handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_brazil_cnpj nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_brazil_cnpj gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_brazil_cnpj nach Inhalten sucht, die dem Muster entsprechen.
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
- Unternehmen
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- Cgc
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>Nationale Brasilien-Identifikationskarte (RG)

### <a name="format"></a>Format

Registro Geral (altes Format): Neun Ziffern

Registro de Identidade (RIC) (neues Format): 11 Ziffern

### <a name="pattern"></a>Muster

Registro Geral (altes Format):
- Zwei Ziffern
- ein Punkt
- drei Ziffern
- ein Punkt
- drei Ziffern
- Bindestrich
- Eine Ziffer, bei der es sich um eine Prüfziffer handelt

Registro de Identidade (RIC) (neues Format):
- 10 Ziffern
- Bindestrich
- Eine Ziffer, bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_brazil_rg nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_brazil_rg gefunden.
- Die Prüfsumme stimmt.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
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
- RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet)
- RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet)


## <a name="bulgaria-drivers-license-number"></a>Führerscheinnummer für Bulgarien

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_bulgaria_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>s_license_number Keywords_bulgaria_eu_driver

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Uniform-Notrufnummer für Ungarn
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

10 Ziffern ohne Leerzeichen und Trennzeichen

- sechs Ziffern, die dem Geburtsdatum (JJMMTD) entsprechen
- Zwei Ziffern, die der Geburtsdatumsreihenfolge entsprechen
- Eine Ziffer, die dem Geschlecht entspricht: eine gerade Ziffer für Denk- und eine ungerade Ziffer für die Frau
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_bulgaria_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_bulgaria_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_bulgaria_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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

- Bnn #
- Bnn
- bucn #
- bucn
- edinen kapselnhdanski nomer
- egn #
- egn
- identification number
- national id
- nationale Nummer
- nationale Zahl #
- nationale Zahl
- Persönliche ID
- Persönliches Nein
- Persönliche Nummer
- Personalidnummer #
- social security number
- Ssn #
- Ssn
- Uniform-Standesamt-ID
- Uniform-Bürger nein
- Uniform-Notrufnummer
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- Eindeutige Nummer der Rufnummer
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


## <a name="bulgaria-passport-number"></a>Passport-Nummer für Ungarn

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_bulgaria_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_bulgaria_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_bulgaria_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum

## <a name="canada-bank-account-number"></a>Bankkontonummer kanadas

### <a name="format"></a>Format

7 oder 12 Ziffern

### <a name="pattern"></a>Muster

Eine Kanadische Bankkontonummer ist 7 oder 12 Ziffern.

Eine kanadische Bankkontonummer setzt sich wie folgt zusammen:
- fünf Ziffern
- Bindestrich
- drei Ziffern ODER
- null "0"
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_canada_bank_account_transit_number findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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


## <a name="canada-drivers-license-number"></a>Kanada - Führerscheinnummer

### <a name="format"></a>Format

Variiert je nach Provinz

### <a name="pattern"></a>Muster

Verschiedene Muster, die Folgendes abdecken:
- Alberta
- British Columbia
- Manitoba
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Ontario
- Prince Edward Island
- Quebec
- Saskatchewan

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Dl
- Dls
- Cdl
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
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
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
- Idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- Identifizierung
- Dl #
- Dls #
- Cdl #
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
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
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
- Id #
- Ids #
- idcard card#
- idcard cards#
- Idcard #
- identification card#
- identification cards#
- Identifizierung #


## <a name="canada-health-service-number"></a>Nummer des Kanada-Gesundheitsdiensts

### <a name="format"></a>Format

 10 Ziffern

### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Psychiater
- workers compensation
- Behinderung


## <a name="canada-passport-number"></a>Kanadische Reisepassnummer

### <a name="format"></a>Format

zwei Großbuchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

zwei Großbuchstaben gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_canada_passport_number findet Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_canada_passport_number oder Keyword_passport gefunden.

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
- Pass #
- PassportID
- Passportno
- Passportnummer
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>Canada Personal Health Identification Number (PHIN)

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Kanada


## <a name="canada-social-insurance-number"></a>Kanada Sozialversicherungsnummer

### <a name="format"></a>Format

neun Ziffern mit optionalen Bindestrichen oder Leerzeichen

### <a name="pattern"></a>Muster

Formatiert:
- drei Ziffern
- Bindestrich oder Leerzeichen
- drei Ziffern
- Bindestrich oder Leerzeichen
- drei Ziffern

Unformatiert: neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_canadian_sin findet Inhalte, die dem Muster entsprechen.
- Mindestens zwei der folgenden Muster:
    - Ein Schlüsselwort aus Keyword_sin wurde gefunden.
    - Ein Schlüsselwort aus Keyword_sin_collaborative wurde gefunden.
    - Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Sünden
- Ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- Sünde #
- soc ins
- social ins

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- Dob
- Geburtsdatum
- Geburtstag
- Date of Birth


## <a name="chile-identity-card-number"></a>Chile-Identitätsnummer

### <a name="format"></a>Format

sieben bis acht Ziffern plus Trennzeichen für eine Prüfziffer oder einen Buchstaben

### <a name="pattern"></a>Muster

sieben bis acht Ziffern plus Trennzeichen:
- ein bis zwei Ziffern
- Ein optionaler Zeitraum
- drei Ziffern
- Ein optionaler Zeitraum
- drei Ziffern
- Strich
- eine Ziffer oder ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung), bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_chile_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_chile_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_chile_id_card nach Inhalten sucht, die dem Muster entsprechen.
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
- rol únicoario
- Ausführen
- Rut
- tarjeta de identificación
- Rol Unico Nacional
- Rol UnicoArio
- Ausführen #
- Rut #
- nationaluniqueroleID #
- national identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Chilenische Identität Nein.
- Chilenische Identitätsnummer
- Chilenische Identität #
- Eindeutige Steuerregistrierung
- Eindeutige eindeutige Rolle
- Eindeutige Steuerrolle
- Eindeutige eindeutige Nummer
- Eindeutige nationale Nummer
- Eindeutige nationale Rolle
- Nationale eindeutige Rolle
- Chile-Identität Nein.
- Chile-Identitätsnummer
- Chile-Identität #


## <a name="china-resident-identity-card-prc-number"></a>In China ansässiger Identitätskarte (PRC)-Nummer

### <a name="format"></a>Format

18 Ziffern

### <a name="pattern"></a>Muster

18 Ziffern:
- sechs Ziffern, bei denen es sich um einen Adresscode handelt
- acht Ziffern im Format JJJJMMTD, die das Geburtsdatum sind
- Drei Ziffern, bei denen es sich um einen Auftragscode handelt
- Eine Ziffer, bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_china_resident_id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_china_resident_id gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_china_resident_id nach Inhalten sucht, die dem Muster entsprechen.
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
- Vr china
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

14 bis 16 Ziffern, die formatiert oder unformatiert (ddddd) formatiert werden können und die den Luhn-Test bestehen müssen.

### <a name="pattern"></a>Muster

Erkennt Karten von allen wichtigen Marken weltweit, einschließlich Visa, MasterCard, Discover Card, JCB, American Express, Beschenkungskarten und Dinerkarten.

### <a name="checksum"></a>Prüfsumme

Ja, die Luhn-Prüfsumme

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_cc_verification wurde gefunden.
    - Ein Schlüsselwort aus Keyword_cc_name wurde gefunden.
    - Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Cvn
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
- Sicherheitscode
- Sicherheitsnummer
- verfalldatum
- codice di verifica
- Cod. Sicurezza
- cod sicurezza
- n autorizzazione
- Código
- Codigo
- Cod. Seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
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
- Valor
- vencimento
- Transaktion
- Transaktionsnummer
- Referenznummer
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- Americanexpress
- americano espresso
- Visa
- Mastercard
- master card
- Mc
- Mastercards
- master cards
- diner's Club
- diners club
- dinerslokal
- Entdecken
- discover card
- discovercard
- discover cards
- Jcb
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- Cc #
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- Bankcard
- card number
- card num
- Kartennummer
- Kartennummern
- card numbers
- Kreditkarte
- credit cards
- Kreditkarten
- Ccn
- card holder
- Karteninhaber
- card holders
- Karteninhaber
- check card
- Checkcard
- check cards
- Checkcards
- debit card
- Debitcard
- debit cards
- Debitkarten
- atm card
- atmcard
- atm cards
- atmcards
- Enroute
- en route
- card type
- Cardmember Acct
- Cardmember-Konto
- Cardno
- Unternehmenskarte
- Unternehmenskarten
- Kartentyp
- Kartenkontonummer
- Kartenmitgliedskonto
- Cardmember Acct.
- card no.
- Karte nein
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- Karte
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
- N. Carta
- n carta
- Nr. Carta
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
- nế. do cartão
- no do cartão
- no do cartao
- Nein. do cartão
- no. do cartao

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
- Visaドード
- Visa ドード
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


## <a name="croatia-drivers-license-number"></a>Kroatien-Führerscheinnummer

### <a name="format"></a>Format

acht Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_croatia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_driver's_license_number` oder `Keywords_croatia_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver's_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Kreditkartennummer für Kroatien
Diese Entität ist im vertraulichen Informationstyp der nationalen EU-Identifikationsnummer enthalten. Es ist als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_croatia_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_croatia_id_card gefunden.

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

- jsstorski brojđana
- Master-Citizen-Nummer
- nationalni identifikacijski broj
- national identification number
- Oib #
- Oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- Persönliche Identifikationsnummer
- porezni broj
- porezni identifikacijski broj
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="croatia-passport-number"></a>Reisepassnummer für Kroatien

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_croatia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_croatia_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_croatia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_croatia_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- Br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>Persönliche Identifikationsnummer (OIB) für Kroatien

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- 10 Ziffern
- Letzte Ziffer ist eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_croatia_oib_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_croatia_eu_tax_file_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_croatia_oib_number nach Inhalten sucht, die dem Muster entsprechen.
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

- jsstorski brojđana
- Master-Citizen-Nummer
- nationalni identifikacijski broj
- national identification number
- Oib #
- Oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- Persönliche Identifikationsnummer
- porezni broj
- porezni identifikacijski broj
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #

## <a name="cyprus-drivers-license-number"></a>Lizenznummer für 1/0

### <a name="format"></a>Format

12 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

12 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_cyprus_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>s_license_number Keywords_cyprus_eu_driver

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Identitätskarte für Identitäten
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

nicht zutreffend

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_national_id_card` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_cyprus_eu_national_id_card` gefunden.

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

- ID-Kartennummer
- Identitätskartennummer
- kimlik karti
- national identification number
- Persönliche ID-Nummer
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Passport-Nummer für Denkzeichen

### <a name="format"></a>Format

Ein Buchstabe gefolgt von 6 bis 8 Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

ein Buchstabe gefolgt von sechs bis acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_cyprus_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_cyprus_eu_passport_date` findet Datum im Format DD/MM/JJJJJ, oder es wird ein Schlüsselwort `Keywords_cyprus_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_cyprus_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_cyprus_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
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
- pasaport nubüchersı
- Pasaport nein.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- läuft ab
- ausgestellt am


## <a name="cyprus-tax-identification-number"></a>Steueridentifikationsnummer für Geschäftsjahre
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern und ein Buchstabe im angegebenen Muster

### <a name="pattern"></a>Muster

Acht Ziffern und ein Buchstabe:

- ein "0" oder "9"
- sieben Ziffern
- ein Buchstabe (ohne Groß-/Kleinschreibung)

### <a name="checksum"></a>Prüfsumme

nicht zutreffend

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_cyprus_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_cyprus_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_cyprus_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- Tic #
- Tic
- tin id
- tin no
- Zinn #
- vergi kimlik kodu
- vergi kimlik nu scheisı
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Tschechische Führerscheinnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

acht Buchstaben und Ziffern:

- Buchstabe "E" (Groß-/Kleinschreibung nicht beachtet)
- ein Brief
- ein Leerzeichen (optional)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_czech_republic_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver's_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Tschechische Reisepassnummer

### <a name="format"></a>Format

acht Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_czech_republic_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_czech_republic_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_czech_republic_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
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


## <a name="czech-personal-identity-number"></a>Tschechische persönliche Identitätsnummer

### <a name="format"></a>Format

neun Ziffern mit optionalem Schrägstrich (altes Format) 10 Ziffern mit optionalem Schrägstrich (neues Format)

### <a name="pattern"></a>Muster

neun Ziffern (altes Format):
- sechs Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich
- drei Ziffern

10 Ziffern (neues Format):
- sechs Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich
- Vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion Func_czech_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_czech_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion Func_czech_id_card_new_format nach Inhalten sucht, die dem Muster entsprechen.
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

- Geburtsdatum
- tschechische Republik-ID
- czechidno #
- daňové číslo
- identifikační číslo
- Identität nein
- Identitätsnummer
- identityno #
- identityno
- Versicherungsnummer
- national identification number
- nationale Zahl #
- nationale Nummer
- osobní číslo
- Personalidnummer #
- Persönliche ID-Nummer
- Persönliche Identifikationsnummer
- Persönliche Nummer
- Pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- Ssn
- Ssn #
- social security number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- eindeutige Identifikationsnummer


## <a name="denmark-drivers-license-number"></a>Dänemark – Führerscheinnummer

### <a name="format"></a>Format

acht Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_denmark_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_denmark_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver's_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Reisepassnummer für Dänemark

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_denmark_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_denmark_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date2` sucht datums im Format DD MM JJJ oder ein Schlüsselwort von `Keywords_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_denmark_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_denmark_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="denmark-personal-identification-number"></a>Dänemark – persönliche Identifikationsnummer

### <a name="format"></a>Format

10 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

10 Ziffern:
- sechs Ziffern im Format DDMMYY, die das Geburtsdatum darstellen
- Bindestrich
- vier Ziffern, bei denen die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Func_denmark_eu_tax_file_number sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_denmark_id gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Func_denmark_eu_tax_file_number sucht Inhalte, die dem Muster entsprechen.
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
- Cpr
- Cpr #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- Integritätskarte
- Kreditkartennummer der Krankenversicherung
- Health Insurance Number
- identification number
- identifikationsnummer
- identifikationsnummer #
- Identitätsnummer
- deren Nummer
- nationalid #
- nationale Zahl #
- nationale Nummer
- Personalidnummer #
- personalidentityno #
- Persönliche ID-Nummer
- Personnummer
- Personnummer #
- reiseplantnversicherungskartenummer
- rejsesygesikringskort
- Ssn
- Ssn #
- SKAT-ID
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
- Reise-Krankenversicherungskarte
- uniqueidentityno #
- Steuernummer
- Steuerregistrierungsnummer
- tax id
- Steueridentifikationsnummer
- umzingen #
- Steuernummer #
- Steuernummer
- taxno #
- Steuernummer
- Steueridentifikationsnummer
- Zinn #
- vererzteno #
- anzahl #
- Steuernummer #
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- Personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="drug-enforcement-agency-dea-number"></a>Dea-Nummer (Drug Enforcement Agency)

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung) aus dieser Reihe möglicher Buchstaben: abcdefghjklmnprstux, bei dem es sich um einen Code handelt.
- ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung), bei dem es sich um den ersten Buchstaben des Nachnamens oder der Ziffer "9" des Unternehmens handelt.
- sieben Ziffern, von denen die letzte die Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keyword_dea_number` gefunden
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Dea
- Dea #
- Verwaltung von Betäuzungszwingung
- Behörde für die Durchsetzung von Betäuzungsz


## <a name="estonia-drivers-license-number"></a>Estnisch-Führerscheinnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

zwei Buchstaben und sechs Ziffern:

- die Buchstaben "ET" (Groß-/Kleinschreibung nicht beachtet)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_estonia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_estonia_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keywords_estonia_eu_drivers_license_number"></a>s_license_number Keywords_estonia_eu_driver

-- permis de conduire
- juhilubade numbrid
- juh siloa number
- juhiluba


## <a name="estonia-personal-identification-code"></a>Persönliche Identifikationscode für Estnisch
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern:

- eine Ziffer, die dem Geschlecht und dem Geburtsdatum entspricht (ungerade Zahl männlich, gerade Zahl; 1-2: 19. Jh.; 3-4: 20. Jh.; 5-6: 21. Jhd.)
- sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTD)
- drei Ziffern, die einer seriennummerntrennenden Person entsprechen, die am selben Datum stammt
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_estonia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_estonia_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_estonia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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
- Ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- nationale Nummer
- Persönlicher Code
- Persönliche ID-Nummer
- Code zur persönlichen Identifikation
- Persönliche Identifikationsnummer
- Personalidnummer #
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="estonia-passport-number"></a>Passport-Nummer für Estnisch

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

ein Buchstabe gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_estonia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_estonia_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_estonia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_estonia_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti enumerationniku pass passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="eu-debit-card-number"></a>EU-Debitkartennummern

### <a name="format"></a>Format

16 Ziffern

### <a name="pattern"></a>Muster

Komplexes und robustes Muster

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Cc #

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct num
- acct no
- american express
- Americanexpress
- americano espresso
- Amex
- atm card
- atm cards
- atm kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- Bancontact
- bank card
- Bankkaart
- card holder
- card holders
- card num
- card number
- card numbers
- card type
- cardano numerico
- Karteninhaber
- Karteninhaber
- Kartennummer
- Kartennummern
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
- Ccn
- check card
- check cards
- Checkcard
- Checkcards
- unterstellenkaart
- Cirrus
- laufzeitrus-edc-codiert
- controlekaart
- controlekaarten
- credit card
- credit cards
- Kreditkarte
- Kreditkarten
- debetkaart
- debetkaarten
- debit card
- debit cards
- Debitcard
- Debitkarten
- debito automatico
- diners club
- dinerslokal
- Entdecken
- discover card
- discover cards
- discovercard
- discovercards
- débito automático
- Edc
- eigentümername
- european debit card
- Hoofdkaart
- Hoofdkaarten
- in viaggio
- japanese card bureau
- japanse kaartdienst
- Jcb
- kaart
- kaart num
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- Karte
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
- Maestro
- master card
- master cards
- Mastercard
- Mastercards
- Mc
- mister cash
- n carta
- Carta
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
- Solo
- supporti di scheda
- supporto di scheda
- Wechseln
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
- V-Pay
- Visa
- visa plus
- visa electron
- Visto
- mit
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
- Codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- Kryptogramm
- cryptogramme
- cv2
- Cvc
- cvc2
- Cvn
- Cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca

- cód. segurança

- Código
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
- Sicherheitskode
- Sicherheitscode
- Sicherheitsnummer
- speldblok
- veiligheid nr
- cursorigheidsaantal
- principaligheidscode
- cursorigheidsnummer
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
- Espira
- Espira
- exp date
- exp datum
- Ablauf
- verfallen
- Abläuft
- Ablauf
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
- Valor
- Venc
- vencimento
- vencimiento
- Verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>EU-Führerscheinnummer

Diese Entitäten befinden sich in der EU-Führerscheinnummer und sind typen vertraulicher Informationen.

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
- [Großbritannien.](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Nationale EU-Identifikationsnummer

Diese Entitäten befinden sich in der nationalen EU-Identifikationsnummer und sind vertrauliche Informationstypen.

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
- [Großbritannien.](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>EU-Reisepassnummer

Diese Entitäten befinden sich in der EU-Reisepassnummer und sind typen vertraulicher Informationen. Diese Entitäten befinden sich im EU-Passport-Nummernpaket.

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
- [Großbritannien.](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU-Sozialversicherungsnummer oder gleichwertige Identifikation

Diese Entitäten, die sich in der EU-Sozialversicherungsnummer oder einer gleichwertigen Identifikation befinden und vertrauliche Informationstypen sind.

- [Österreich](#austria-social-security-number)
- [Belgien](#belgium-national-number)
- [Kroatien](#croatia-personal-identification-oib-number)
- [Tschechisch](#czech-personal-identity-number)
- [Dänemark](#denmark-personal-identification-number)
- [Finnland](#finland-national-id)
- [Frankreich](#france-social-security-number-insee)
- [Deutschland](#germany-identity-card-number)
- [Griechenland](#greece-national-id-card)
- [Ungarn](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [Spanien](#spain-social-security-number-ssn)
- [Schweden](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>EU-Steueridentifikationsnummer

Diese Entitäten befinden sich im Vertraulichen Informationstyp der EU-Steueridentifikationsnummer.

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
- [Großbritannien.](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Finnland – Führerscheinnummer

### <a name="format"></a>Format

10 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

10 Ziffern, die einen Bindestrich enthalten:

- sechs Ziffern
- Bindestrich
- drei Ziffern
- eine Ziffer oder ein Buchstabe

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_finland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_finland_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_finland_eu_drivers_license_number"></a>s_license_number Keywords_finland_eu_driver

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Europäische Krankenversicherungsnummer Für Finnland
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

20-stellige Zahl

### <a name="pattern"></a>Muster

20-stellige Zahl:

- 10 Ziffern - 8024680246
- Ein optionaler Leerzeichen oder Bindestrich
- 10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_Finland_European_Health_Insurance_Number sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Finland_European_Health_Insurance_Number gefunden.

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

- Ehic #
- Ehic
- finnehicnumber #
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
- terveyskortti


## <a name="finland-national-id"></a>Nationale NATIONALE ID Für Finnland

### <a name="format"></a>Format

sechs Ziffern plus ein Zeichen, das ein Hunderter-Zeichen plus drei Ziffern plus eine Prüfziffer angibt

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- sechs Ziffern im Format DDMMYY, bei denen es sich um ein Geburtsdatum handelt
- Hundertermarker (entweder '-', '+' oder 'a')
- Dreistellige persönliche Identifikationsnummer
- Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung wird nicht beachtet), bei der es sich um eine Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- die Funktion, Func_finnish_national_id Inhalte findet, die dem Muster entsprechen
- Ein Schlüsselwort aus Keyword_finnish_national_id gefunden wird
- die Prüfsummendurchläufe

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- die Funktion, Func_finnish_national_id Inhalte findet, die dem Muster entsprechen
- die Prüfsummendurchläufe

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
- Hetu
- ID Nein
- ID-Nummer
- identification number
- identiteetti numero
- Identitätsnummer
- ID-Nummer
- kansallinen henkilötunnus
- kansallisen henkilökortin
- Nationale ID-Karte
- nationale ID-Nr.
- Persönliche ID
- Code zur persönlichen Identität
- Personalidnummer #
- Personbeteckning
- Personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Reisepassnummer für Finnland

Diese Entität ist im Vertraulichen Informationstyp "EU Passport Number" und als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format
Kombination aus neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster
Kombination aus neun Buchstaben und Ziffern:
- zwei Buchstaben (groß- und kleingeschrieben)
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck `Regex_finland_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_finland_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck `Regex_finland_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_finland_passport_number` wird gefunden.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- Passi #
- Passi-Nummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum

## <a name="france-drivers-license-number"></a>Französische Führerscheinnummer

Diese Entität ist im Vertraulichen Informationstyp "EU-Führerscheinnummer" verfügbar und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern mit Validierung, um ähnliche Muster ( z. B. französische Telefonnummern) auszuschließen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- die Funktion Func_french_drivers_license nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_french_drivers_license gefunden.

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
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Französische Krankenversicherungsnummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

21-stellige Zahl

### <a name="pattern"></a>Muster

21-stellige Zahl:

- 10 Ziffern
- Ein optionaler Bereich
- 10 Ziffern
- Ein optionaler Bereich
- eine Ziffer


### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- der reguläre Ausdruck Regex_France_Health_Insurance_Number sucht Inhalte, die dem Muster entsprechen.
- ein Schlüsselwort aus Keyword_France_Health_Insurance_Number gefunden wird.

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

- Versicherungskarte
- karteswichtig
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>Französische nationale ID-Karte (CNI)

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_france_cni findet Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_france_eu_national_id_card gefunden.

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
- Cni #
- Cni
- compte bancaire
- national identification number
- Nationale Identität
- nationalidno #
- numéro d'assurance malaidie
- numéro de carte vitale


## <a name="france-passport-number"></a>Französische Reisepassnummer
Diese Entität ist im Vertraulichen Informationstyp "EU Passport Number" verfügbar. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

neun Ziffern und Buchstaben

### <a name="pattern"></a>Muster

neun Ziffern und Buchstaben:
- Zwei Ziffern
- zwei Buchstaben (groß- und kleingeschrieben)
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_fr_passport` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keywords_france_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date3` sucht das Datum im Format DD MM JJJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_fr_passport` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keywords_france_eu_passport_number` wird gefunden.


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport ciçais
- passeport glanzre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="france-social-security-number-insee"></a>Französische Sozialversicherungsnummer (INSEE)

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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_french_insee` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_fr_insee wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_french_insee oder Func_fr_insee Inhalte findet, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- Insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- Ssn
- Ssn #
- sécurité sociale
- securité sociale
- securite sociale
- Sozialversicherungsnummer
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>Französische Steueridentifikationsnummer

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffern

- Eine Ziffer, die 0, 1, 2 oder 3 sein muss
- Eine Ziffer
- Ein Leerzeichen (optional) 
- Zwei Ziffern
- Ein Leerzeichen (optional) 
- Drei Ziffern
- Ein Leerzeichen (optional) 
- Drei Ziffern
- Ein Leerzeichen (optional) 
- Drei Prüfziffern


### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_france_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_france_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_france_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="france-value-added-tax-number"></a>Französische Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 13 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 13 Zeichen:

- zwei Buchstaben – FR (Groß-/Kleinschreibung nicht beachtet)
- Ein optionaler Leerzeichen oder Bindestrich
- zwei Buchstaben oder Ziffern
- Optionaler Leerzeichen, Punkt, Bindestrich oder Komma
- drei Ziffern
- Optionaler Leerzeichen, Punkt, Bindestrich oder Komma
- drei Ziffern
- Optionaler Leerzeichen, Punkt, Bindestrich oder Komma
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_france_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_france_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_france_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Umsatzsteuernummer
- umsatzsteuer-Nr.
- Mwst #
- Mehrwertsteuer
- siren identification no numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Deutsche Führerscheinnummer

Diese Entität für vertrauliche Informationstypen ist im Vertraulichen Informationstyp "EU-Führerscheinnummer" enthalten. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

Kombination aus 11 Ziffern und Buchstaben

### <a name="pattern"></a>Muster

11 Ziffern und Buchstaben (Groß-/Kleinschreibung wird nicht beachtet):
- eine Ziffer oder ein Buchstabe
- Zwei Ziffern
- sechs Ziffern oder Buchstaben
- eine Ziffer
- eine Ziffer oder ein Buchstabe

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- umrennen
- fuehrerschein
- führerscheinnummer
- wirderscheinnummer
- fuehrerscheinnummer
- führerschein- 
- benutzerdefinierterschein- 
- fuehrerschein- 
- führerscheinnummernr
- hellererscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- intelligentererscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-doppelklickerschein
- nr-fuehrerschein
- no-führerschein
- no-wieserschein
- no-fuehrerschein
- n-führerschein
- n-wieserschein
- n-fuehrerschein
- permis de conduire
- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dlno


## <a name="germany-identity-card-number"></a>Deutschland-Identitätsnummer

### <a name="format"></a>Format

seit 1. November 2010: Neun Buchstaben und Ziffern

vom 1. April 1987 bis zum 31. Oktober 2010: 10 Ziffern

### <a name="pattern"></a>Muster

seit dem 1. November 2010:
- ein Buchstabe (ohne Groß-/Kleinschreibung)
- acht Ziffern

vom 1. April 1987 bis zum 31. Oktober 2010:
- 10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_germany_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_germany_id_card gefunden.

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
- Identifizierung
- identifikation
- identifizierungsnummer
- identity card
- Identitätsnummer
- id-nummer
- Persönliche ID
- - (in)
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Deutsche Reisepassnummer

Diese Entität ist im Vertraulichen Informationstyp "EU Passport Number" enthalten und steht als eigenständige Entität für vertrauliche Informationstypen zur Verfügung.

### <a name="format"></a>Format

10 Ziffern oder Buchstaben

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Das erste Zeichen ist eine Ziffer oder ein Buchstabe aus dieser Gruppe (C, F, G, H, J, K)
- drei Ziffern
- fünf Ziffern oder Buchstaben aus dieser Gruppe (C, -H, J-N, P, R, T, V-Z)
- eine Ziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_german_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keyword_german_passport` oder `Keywords_eu_passport_number_common` wird gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_german_passport_data findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keyword_german_passport` oder `Keywords_eu_passport_number_common` wird gefunden.
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
- reise wie
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern


## <a name="germany-tax-identification-number"></a>Steueridentifikationsnummer deutschlandweit

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern

- Zwei Ziffern
- Ein optionales Leerzeichen
- Drei Ziffern
- Ein optionales Leerzeichen
- Drei Ziffern
- Ein optionales Leerzeichen
- Zwei Ziffern
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_germany_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_germany_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_germany_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Steuer-ID
- steueridentifikationsnummer
- steuernummer
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Deutsche Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 11 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 11 Zeichen:

- ein Buchstabe D oder d
- ein Buchstabe E oder e
- Ein optionaler Bereich
- drei Ziffern
- Ein optionales Leerzeichen oder Komma
- drei Ziffern
- Ein optionales Leerzeichen oder Komma
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_germany_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_germany_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_germany_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Umsatzsteuernummer
- umsatzsteuer-Nr.
- Mwst #
- vat# mehrwertsteuer
- kwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Führerscheinnummer für Griechenland

Diese Entität ist im Vertraulichen Informationstyp "EU-Führerscheinnummer" enthalten. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_greece_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_greece_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver's_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>Nationale ID-Karte für Griechenland

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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_greece_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_greece_id_card gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_greece_id_card nach Inhalten sucht, die dem Muster entsprechen.

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

- griechisch-ID
- nationale id für Griechisch
- griechisch persönliche ID-Karte
- id der griechisch-Regierung
- identity card
- Tautotita
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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_greece_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_greece_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_greece_eu_passport_date` sucht datums im Format DD MMM JJJ (Beispiel - 28 Aug 19) oder ein Schlüsselwort von `Keywords_greece_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_greece_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_greece_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Sozialversicherungsnummer Für Griechenland (AMKA)
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

- Sechs Ziffern als Geburtsdatum JJMMTD
- Vier Ziffern
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_greece_eu_ssn` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_greece_eu_ssn_or_equivalent` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_greece_eu_ssn` sucht Inhalte, die dem Muster entsprechen.

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

- Ssn
- Ssn #
- Sozialversicherung nein
- socialsecurityno #
- social security number
- Amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Steueridentifikationsnummer für Griechenland
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

Neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nicht anwendbar

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_greece_eu_tax_file_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_greece_eu_tax_file_number` gefunden.

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

- Afm #
- Afm
- aφμ|aφμ αριθμόσ
- aφμ
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- Steuerregistrierungsnr.
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- taxregistryno #
- tin id
- tin no
- Zinn #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>HKID-Nummer (Hong Kong Identity Card)

### <a name="format"></a>Format

Kombination aus 8-9Buchstaben und Zahlen sowie optionale Klammern um das letzte Zeichen

### <a name="pattern"></a>Muster

Kombination aus Buchstaben 8-9 Buchstaben:
- 1 bis 2 Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- Sechs Ziffern
- Das letzte Zeichen (eine Ziffer oder der Buchstabe A), bei dem es sich um die Prüfziffer handelt, die optional in Klammern eingeschlossen werden kann.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_hong_kong_id_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_hong_kong_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_hong_kong_id_card nach Inhalten sucht, die dem Muster entsprechen.
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
- Hongkong-Identitätskarte
- HKIDC
- id card
- identity card
- hk-Identitätskarte
- Hongkong-ID
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


## <a name="hungary-drivers-license-number"></a>Ungarn – Führerscheinnummer

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben und sechs Ziffern:

- Zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- Sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_hungary_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_hungary_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver's_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Persönliche Identifikationsnummer für Ungarn
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:

- Eine Ziffer, die dem Geschlecht entspricht, 1 für Männlich, 2 für Frau. Weitere Nummern sind auch für Bürger mit vor 1900 Jahren oder für Bürger mit doppelter Stämmung möglich.
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTD)
- Drei Ziffern, die einer Seriennummer entsprechen
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_hungary_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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

- ID-Nummer
- identification number
- sz ig
- Sz. Ig.
- sz.ig.
- személyazonosító ig telemetrvány
- személyi ig telemetrvány


## <a name="hungary-passport-number"></a>Reisepassnummer für Ungarn

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

Zwei Buchstaben gefolgt von sechs oder sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_hungary_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_hungary_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_hungary_eu_passport_date` sucht datums im Format DD MMM/MMM JJ (Beispiel - 01 MÁR/MAR 12) oder ein Schlüsselwort von `Keywords_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_hungary_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_hungary_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="hungary-social-security-number-taj"></a>Ungarn Sozialversicherungsnummer (TAJ)

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

Neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_ssn_or_equivalent` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_hungary_eu_ssn_or_equivalent` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_ssn_or_equivalent` sucht Inhalte, die dem Muster entsprechen.

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

- Sozialversicherungsnummer
- social security number
- Sozialversicherungsnummer #
- hssn #
- socialsecuritynno
- hssn
- Taj
- Taj #
- Ssn
- Ssn #
- Sozialversicherung nein
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Steueridentifikationsnummer für Ungarn
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

10 Ziffern:

- Eine Ziffer, die "8" sein muss
- Acht Ziffern
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_hungary_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion  `Func_hungary_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- kontinent
- hungatiantin #
- Steuerbehörde Nein
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- Umsatzsteuernummer


## <a name="hungary-value-added-tax-number"></a>Umsatzsteuernummer für Ungarn
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit 10 Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit 10 Zeichen:

- zwei Buchstaben – HU oder Hu
- Optionaler Speicherplatz
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion Func_hungarian_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_hungarian_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion Func_hungarian_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Mwst
- Umsatzsteuernummer
- Mwst #
- vatno #
- auswendigenvatno #
- Steuernummer.
- Umsatzsteuer áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Permanente Kontonummer indiens (PAN)

### <a name="format"></a>Format

10 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

10 Buchstaben oder Ziffern:
- Drei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- Ein Buchstabe in C, P, H, F, A, T, B, L, J, G (Groß-/Kleinschreibung nicht beachtet)
- ein Brief
- Vier Ziffern
- Ein Buchstabe, bei dem es sich um eine alphabetische Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_india_permanent_account_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_india_permanent_account_number gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_india_permanent_account_number nach Inhalten sucht, die dem Muster entsprechen.


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
- Pfanne

## <a name="india-unique-identification-aadhaar-number"></a>Eindeutige Identifikationsnummer für Indien (Aadkat)

### <a name="format"></a>Format

12 Ziffern mit optionalen Leerzeichen oder Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- Eine Ziffer, die nicht 0 oder 1 ist
- Drei Ziffern
- Eine optionales Leerzeichen oder ein Bindestrich 
- Vier Ziffern
- Eine optionales Leerzeichen oder ein Bindestrich 
- Die letzte Ziffer, bei der es sich um die Prüfziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_india_aadhaar nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_india_aadhar gefunden.
- Die Prüfsumme stimmt.
-
Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Die Funktion Func_india_aadhaar nach Inhalten sucht, die dem Muster entsprechen.
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
- aad zwischen
- aadhar
- aadhar #
- uid
- आधार
- uidai

## <a name="indonesia-identity-card-ktp-number"></a>Indonesisch-Identitätskarte (KTP)-Nummer

### <a name="format"></a>Format

16 Ziffern mit optionalen Punkten

### <a name="pattern"></a>Muster

16 Ziffern:
- Zweistelliger Provinzcode 
- Ein Punkt (optional) 
- Zweistelliger Regency- oder Stadtcode 
- Zweistelliger Subdistrict-Code 
- Ein Punkt (optional) 
- Sechs Ziffern im Format DDMMYY, die das Geburtsdatum sind
- Ein Punkt (optional) 
- Vier Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck Regex_indonesia_id_card sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_indonesia_id_card gefunden.

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

- Ktp
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan

## <a name="international-banking-account-number-iban"></a>International Banking Account Number (IBAN)

### <a name="format"></a>Format

Ländercode (zwei Buchstaben) plus Prüfziffern (zwei Ziffern) plus Bbannummer (bis zu 30 Zeichen)

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:

- Aus zwei Buchstaben bestehender Ländercode
- Zwei Prüfziffern (gefolgt von einem optionalen Leerzeichen)
- 1 bis 7 Gruppen von vier Buchstaben oder Ziffern (können durch Leerzeichen getrennt werden)
- 1 bis 3 Buchstaben oder Ziffern

Das Format für jedes Land unterscheidet sich geringfügig. Der IBAN-Typ vertraulicher Informationen umfasst die folgenden 60 Länder:

- ad
- Ae
- Al
- Auf
- Az
- Ba
- Werden
- bg
- bh
- Ch
- Cr
- Cy
- Cz
- de
- Dk
- tun
- Ee
- es
- fi
- Fo
- fr
- Gb
- ge
- Gi
- gl
- Gr
- hr
- hu
- Ie
- Il
- is
- it
- Kw
- Kz
- Lb
- Li
- lt
- Lu
- lv
- Mc
- MD
- me
- mk
- mr
- Mt
- Mu
- nl
- Nein
- pl
- pt
- ro
- rs
- Sa
- Se
- si
- sk
- Sm
- Tn
- tr
- Vg

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

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

Keiner


## <a name="international-classification-of-diseases-icd-10-cm"></a>Internationale Klassifizierung von Infektionen (ICD-10-CM)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Es wird ein Schlüsselwort aus Dictionary_icd_10_updated gefunden.
- Es wird ein Schlüsselwort aus Dictionary_icd_10_codes gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Ein Schlüsselwort aus Dictionary_icd_10_ aktualisiert wurde gefunden.

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

Ein beliebiger Begriff aus dem Dictionary_icd_10_updated Schlüsselwortwörterbuch, das auf der [internationalen Klassifizierung von Störungen, zehnter Revision, klinikischer Änderung (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)basiert. Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungscodes.

Ein beliebiger Begriff aus dem Dictionary_icd_10_codes Schlüsselwörterbuch, das auf der [internationalen Klassifizierung von Störungen, zehnter Revision, medizinischer Änderung (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604)basiert. Dieser Typ sucht nur nach Versicherungscodes, nicht nach der Beschreibung.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Internationale Klassifizierung von Infektionen (ICD-9-CM)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Es wird ein Schlüsselwort aus Dictionary_icd_9_updated gefunden.
- Es wird ein Schlüsselwort aus Dictionary_icd_9_codes gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Es wird ein Schlüsselwort aus Dictionary_icd_9_updated gefunden.

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

Jeder Begriff aus dem Dictionary_icd_9_updated Schlüsselwortwörterbuchs, das auf der [internationalKlassifizierung von Störungen, neunter Revision, klinikischer Änderung (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)basiert. Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungscodes.

Ein beliebiger Begriff aus dem Dictionary_icd_9_codes Schlüsselwortwörterbuch, das auf der [internationalKlassifizierung von Störungen, neunter Revision, klinikischer Änderung (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605)basiert. Dieser Typ sucht nur nach Versicherungscodes, nicht nach der Beschreibung.

## <a name="ip-address"></a>IP-Adresse

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4:
Komplexes Muster, das formatierte Versionen (Perioden) und unformatierte Versionen (keine Perioden) der IPv4-Adressen berücksichtigt

#### <a name="ipv6"></a>IPv6:
Komplexes Muster, das formatierte IPv6-Zahlen berücksichtigt (einschließlich Doppelpunkte)

### <a name="pattern"></a>Muster

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Bei IPv6 ist eine DLP-Richtlinie sehr sicher, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_ipv6_address findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_ipaddress gefunden.

Bei IPv4 ist eine DLP-Richtlinie sehr sicher, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_ipv4_address findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ipaddress wurde gefunden.

Bei IPv6 ist eine DLP-Richtlinie sehr sicher, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet)
- ip address
- IP-Adressen
- internet protocol
- IP-כתובת ה

## <a name="ireland-drivers-license-number"></a>Irland – Führerscheinnummer

### <a name="format"></a>Format

Sechs Ziffern gefolgt von vier Buchstaben

### <a name="pattern"></a>Muster

Sechs Ziffern und vier Buchstaben:

- Sechs Ziffern
- Vier Buchstaben (ohne Groß-/Kleinschreibung)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:

- Der reguläre Ausdruck  `Regex_ireland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_ireland_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver's_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Reisepassnummer für Irland

### <a name="format"></a>Format

Zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

Zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:

- Zwei Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- Sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_ireland_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_ireland_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_ireland_eu_passport_date` sucht datums im Format DD MMM/MMM JJJJ (Beispiel - 01 BEA/MAY 1988) oder ein Schlüsselwort von `Keywords_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_ireland_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_ireland_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasava
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="ireland-personal-public-service-pps-number"></a>Nummer des persönlichen öffentlichen Dienstes (Personal Public Service, PPS) in Irland

### <a name="format"></a>Format

Altes Format (bis 31. Dezember 2012):
- sieben Ziffern gefolgt von 1 bis 2 Buchstaben

Neues Format (1. Januar 2013 und danach):
- sieben Ziffern gefolgt von zwei Buchstaben

### <a name="pattern"></a>Muster

Altes Format (bis 31. Dezember 2012):
- sieben Ziffern
- 1 bis 2 Buchstaben (Groß-/Kleinschreibung nicht beachten)

Neues Format (1. Januar 2013 und danach):
- sieben Ziffern
- ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung), bei dem es sich um eine alphabetische Prüfziffer handelt
- Ein optionaler Buchstabe im Bereich A-I oder "W"

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_ireland_pps nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_ireland_eu_national_id_card gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_ireland_pps nach Inhalten sucht, die dem Muster entsprechen.
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
- Persönlichen Dienst nein
- phearsane seirbhíse poiblí
- pps no
- pps-Zahl
- pps num
- pps-Dienst nein
- ppsn
- ppsno #
- ppsno
- Psp
- Public Service No
- publicserviceno #
- publicserviceno
- Umsatz- und Sozialversicherungsnummer
- rsi no
- rsi number
- rsin
- seirbhís aitheigneis client
- uimh
- uimhir aithezimis chánach
- uimhir aithezimis phearszim
- uimhir phears poiblí seirbhíse poiblí
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="israel-bank-account-number"></a>Israel-Bankkontonummer

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

Formatiert:
- Zwei Ziffern
- Strich
- drei Ziffern
- Strich
- acht Ziffern

Unformatierte:
- 	13 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

## <a name="israel-national-identification-number"></a>Nationale Kennnummer von Israel

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
-   ID-Nummer #
-   ID-Nummer
-   Identität nein        
-   Identitätsnummer #
-   Identitätsnummer
-   identitätidentitynumber       
-   Persönliche ID
-   Eindeutige ID  


## <a name="italy-drivers-license-number"></a>Führerscheinnummer für Italien

Diese Typentität ist im Vertraulichen Informationstyp "EU-Führerscheinnummer" enthalten. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

eine Kombination aus 10 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

Eine Kombination aus 10 Buchstaben und Ziffern:
- ein Buchstabe (ohne Groß-/Kleinschreibung)
- der Buchstabe "A" oder "V" (Groß-/Kleinschreibung nicht beachtet)
- sieben Ziffern
- ein Buchstabe (ohne Groß-/Kleinschreibung)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck `Regex_italy_drivers_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_driver's_license_number` oder `Keyword_italy_drivers_license_number` wird gefunden.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>Steuercode für Italien
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Eine 16-Zeichen-Kombination aus Buchstaben und Ziffern im angegebenen Muster

### <a name="pattern"></a>Muster

Eine Kombination aus 16 Zeichen und Ziffern:
- drei Buchstaben, die den ersten drei Konsonanten im Nachnamen entsprechen
- drei Buchstaben, die dem ersten, dritten und vierten Konsonanten im Vornamen entsprechen
- zwei Ziffern, die den letzten Ziffern des Geburtsdatums entsprechen
- Ein Buchstabe, der dem Brief für den Monat der Geburtsdatum entspricht– Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben A bis E, H, L, M, P, R bis T werden verwendet (also ist Januar A und Oktober ist R)
- Zwei Ziffern, die dem Tag des Monats der Geburtsdatum entsprechen, um zwischen den Geschlechten zu unterscheiden, 40 werden zum Geburtsdatum für Kinder hinzugefügt.
- vier Ziffern, die der ortsspezifischen Ortsvorwahl entsprechen, in der die Person zur Welt kam (für fremde Länder werden landesweite Codes verwendet).
- eine Paritätsziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_italy_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_italy_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_italy_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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

- Codice Fiscal
- codice fiscale
- codice id personale
- codice personale
- Steuercode
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- Persönliche Zertifikatnummer
- Persönlicher Code
- Code für persönliche IDs
- Persönliche ID-Nummer
- personalcodeno #
- Steuercode
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="italy-passport-number"></a>Reisepassnummer für Italien

### <a name="format"></a>Format

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:

- zwei Ziffern oder Buchstaben (ohne Groß-/Kleinschreibung)
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

nicht zutreffend

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_italy_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_italy_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_italy_eu_passport_date` sucht datums im Format DD MMM/MMM JJJJ (Beispiel - 01 GEN/JAN 1988) oder ein Schlüsselwort von `Keywords_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_italy_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_italy_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
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


## <a name="italy-value-added-tax-number"></a>Umsatzsteuernummer für Italien
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Zeichen alphanumerisches Muster mit optionalen Trennzeichen

### <a name="pattern"></a>Muster

13 Zeichen alphanumerisches Muster mit optionalen Trennzeichen:

- I oder i
- T oder t
- Optionaler Leerzeichen, Punkt, Bindestrich oder Komma
- 11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_italy_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_italy_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_italy_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Umsatzsteuernummer
- umsatzsteuer-Nr.
- Mwst #
- Iva
- Iva #


## <a name="japan-bank-account-number"></a>Japanische Bankkontonummer

### <a name="format"></a>Format

sieben oder acht Ziffern

### <a name="pattern"></a>Muster

Bankkontonummer:
- sieben oder acht Ziffern
- Bankverbindungscode:
- vier Ziffern
- Leerzeichen oder Gedankenstriche (optional)
- drei Ziffern

Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.
- Eine der folgenden Bedingungen trifft zu:
- Die Funktion Func_jp_bank_account_branch_code findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_branch_code wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Driverlicense
- driverslicense
- Driver'slicense
- driverslicenses
- Segmente des Treibers
- Driverlicenses
- Dl #
- Dls #
- Lic #
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


## <a name="japan-my-number---corporate"></a>Japan Meine Nummer – Unternehmen
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13-stellige Zahl

### <a name="pattern"></a>Muster

13-stellige Zahl:

- Eine Ziffer von 1 bis 9
- 12 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_japanese_my_number_corporate nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_japanese_my_number_corporate gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_japanese_my_number_corporate nach Inhalten sucht, die dem Muster entsprechen.

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


## <a name="japan-my-number---personal"></a>Japan Meine Nummer – Persönlich
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

12-stellige Zahl

### <a name="pattern"></a>Muster

12-stellige Zahl:

- vier Ziffern
- Optionaler Leerzeichen, Punkt oder Bindestrich
- vier Ziffern
- Optionaler Leerzeichen, Punkt oder Bindestrich
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_japanese_my_number_personal nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_japanese_my_number_personal gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_japanese_my_number_personal nach Inhalten sucht, die dem Muster entsprechen.

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

- meine Nummer
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

zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Pass
- Passport Number
- Passport-Nr.
- Passport#
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Japanische Wohnsitzkartennummer

### <a name="format"></a>Format

12 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

12 Buchstaben und Ziffern:
- zwei Buchstaben (groß- und kleingeschrieben)
- acht Ziffern
- zwei Buchstaben (groß- und kleingeschrieben)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_jp_residence_card_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_jp_residence_card_number gefunden.

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

- Nummer der Wohnsitzkarte
- Wohnsitzkarte Nein
- Wohnsitzkarte #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>In Japan ansässigen Registrierungsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Bindestrich (optional)
- sechs Ziffern ODER
- 7-12 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_jp_sin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Lettisch-Führerscheinnummer

### <a name="format"></a>Format

drei Buchstaben gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

drei Buchstaben und sechs Ziffern:

- drei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_latvia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_latvia_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver's_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Persönlicher Code für Lettisch

### <a name="format"></a>Format

11 Ziffern und optionaler Bindestrich

### <a name="pattern"></a>Muster

Altes Format

11 Ziffern und ein Bindestrich:

- sechs Ziffern, die dem Geburtsdatum entsprechen (DDMMYY)
- Bindestrich
- Eine Ziffer, die dem Geburtsdatum entspricht ("0" für das 19. Jh., "1" für das 20. Und "2" für das 21. Jhd.)
- vier Ziffern, nach dem Zufallsprinzip generiert

Neues Format

11 Ziffern

- Zwei Ziffern "32"
- Neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_latvia_eu_national_id_card` oder der reguläre Ausdruck sucht `Regex_latvia_eu_national_id_card_new_format` Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_latvia_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_latvia_eu_national_id_card` oder der reguläre Ausdruck sucht `Regex_latvia_eu_national_id_card_new_format` Inhalte, die dem Muster entsprechen.

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

- Administrative Nummer
- alvas nē
- Geburtsdatum
- Bürgernummer
- standesamtliche Nummer
- Elektronische Zählungsnummer
- elektronische Nummer
- Steuercode
- Benutzernummer im Gesundheitswesen
- Id #
- ID-Code
- identification number
- identifikācijas numurs
- ID-Nummer
- Einzelne Zahl
- latvija aves
- nacionālais id
- national id
- nationale Identifikationsnummer
- Nationale Identitätsnummer
- national insurance number
- Nationale Registernummer
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- Persönliche Zertifikatnummer
- Persönlicher Code
- Code für persönliche IDs
- Persönliche ID-Nummer
- Code zur persönlichen Identifikation
- Persönlicher Bezeichner
- Persönliche Identitätsnummer
- Persönliche Nummer
- Persönlicher numerischer Code
- personalcodeno #
- personas kods
- Code zur Populationsidentifikation
- Öffentliche Dienstnummer
- registration number
- Umsatznummer
- social insurance number
- social security number
- Landessteuercode
- tax file number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- Zahl des Wahlwerts

## <a name="latvia-passport-number"></a>Reisepassnummer für Lettisch

### <a name="format"></a>Format

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

zwei Buchstaben oder Ziffern gefolgt von sieben Ziffern:

- zwei Ziffern oder Buchstaben (ohne Groß-/Kleinschreibung)
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_latvia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_latvia_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_latvia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_latvia_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
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


## <a name="lithuania-drivers-license-number"></a>Führerscheinnummer für Litauau

### <a name="format"></a>Format

acht Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_lithuania_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver's_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Privater Code für Litauen
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern ohne Leerzeichen und Trennzeichen:

- eine Ziffer (1-6), die dem Geschlecht und dem Geburtsdatum der Person entspricht
- sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTD)
- drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_lithuania_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_lithuania_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_lithuania_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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

- asmeninis skaitmeninis codiert
- asmens codiert
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
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- unikalus identifikavimo skalas
- unikalus identifikavimo numeris
- eindeutige Identifikationsnummer
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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_lithuania_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date3` sucht das Datum im Format DD MM JJJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_lithuania_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_lithuania_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="luxemburg-drivers-license-number"></a>Luxemburg-Führerscheinnummer

### <a name="format"></a>Format

sechs Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_luxemburg_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver's_license_number

- derEntwerdung
- Wiesschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Nationale Identifikationsnummer Luxemburg (natürliche Personen)
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_luxemburg_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.


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

- eindeutige ID
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- Einzelner Code
- Individuelle ID
- Individuelle Identifikation
- Individuelle Identität
- numéro d'identification personnel
- Persönliche ID
- Persönliche Identifikation
- Persönliche Identität
- Personalidno #
- Personalidnummer #
- persönliche identifikationsnummer
- Eindeutige ID
- Eindeutige Identität
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Luxemburg-Reisepassnummer

### <a name="format"></a>Format

Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

acht Ziffern oder Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_luxemburg_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date3` sucht das Datum im Format DD MM JJJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_luxemburg_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_luxemburg_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- luxemburgpass
- luxemburg passeport
- passport
- no de passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reise wie
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Nationale Kennnummer von Luxemburg (nicht natürliche Personen)

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern

- Zwei Ziffern
- Ein optionaler Bereich
- drei Ziffern
- Ein optionaler Bereich
- drei Ziffern
- Ein optionaler Bereich
- Zwei Ziffern
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number_non_natural` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_luxemburg_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_luxemburg_eu_tax_file_number_non_natural` sucht Inhalte, die dem Muster entsprechen.

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
- tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxemburgeois
- numéro d'identification fiscale
- social security
- wiedererzunterstützung
- mausversécherung
- sozialversicherungsmelder
- steier id
- steier identifikatiounsnummer
- steier nummer
- Steuer-ID
- steueridentifikationsnummer
- steuernummer
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Malaysia-Identifikationskartennummer

### <a name="format"></a>Format

12 Ziffern mit optionalen Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- sechs Ziffern im Format JJMMTD, die das Geburtsdatum darstellen
- Strich (optional)
- Aus zwei Buchstaben bestehender Ort-der-Geburtsdatum-Code
- Strich (optional)
- drei zufällige Ziffern
- Einstelliger Geschlechtcode

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_malaysia_id_card_number sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_malaysia_id_card_number gefunden.

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
- i/c nein
- Ic
- ic no
- id card
- Identifikationskarte
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malaysia
- Kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- Malaysia Identity Card
- Malaysian-Identitätskarte
- nric
- Persönliche Identifikationskarte

## <a name="malta-drivers-license-number"></a>Führerscheinnummer von Ungarn

### <a name="format"></a>Format

Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster

### <a name="pattern"></a>Muster

Kombination aus zwei Zeichen und sechs Ziffern:

- zwei Zeichen (Ziffern oder Buchstaben ohne Groß-/Kleinschreibung)
- ein Leerzeichen (optional)
- drei Ziffern
- ein Leerzeichen (optional)
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_malta_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_malta_eu_drivers_license_number"></a>s_license_number Keywords_malta_eu_driver

- lienzja tas-sewqan
- lienzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Kreditkartennummer für Ungarn
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

sieben Ziffern gefolgt von einem Buchstaben

### <a name="pattern"></a>Muster

sieben Ziffern gefolgt von einem Buchstaben:

- sieben Ziffern
- ein Buchstabe in "M, G, A, P, L, H, B, Z" (Groß-/Kleinschreibung nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Nicht anwendbar

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_national_id_card` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_malta_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- kodii numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz ta-ittadin
- numru tat-taxxa
- Persönlicher numerischer Code
- eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #


## <a name="malta-passport-number"></a>Reisepassnummer für Ungarn

### <a name="format"></a>Format

sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_malta_eu_passport_number` wird gefunden.
- Ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_malta_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="malta-tax-identification-number"></a>Umsatzsteueridentifikationsnummer

### <a name="format"></a>Format

Für Diess:
- sieben Ziffern und ein Buchstabe im angegebenen Muster

Nicht-Wiesn-Entitäten und -Entitäten:
- neun Ziffern

### <a name="pattern"></a>Muster

Folien: sieben Ziffern und ein Buchstabe

- sieben Ziffern
- ein Buchstabe (ohne Groß-/Kleinschreibung)

Nicht-Gemeinnützige Entitäten und Entitäten der Entitäten": neun Ziffern

- neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nicht anwendbar

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_tax_file_number`  oder `Regex_malta_eu_tax_file_number_non_maltese_national` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_malta_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_malta_eu_tax_file_number` oder `Regex_malta_eu_tax_file_number_non_maltese_national` sucht Inhalte, die dem Muster entsprechen.

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
- kodii numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz ta-ittadin
- numru tat-taxxa
- Persönlicher numerischer Code
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Bezeichnerkarte (MBI)

### <a name="format"></a>Format

Alphanumerisches Muster mit 11 Zeichen

### <a name="pattern"></a>Muster

- Eine Ziffer zwischen 1 und 9
- ein Buchstabe ohne S, L, O, I, B, Z
- eine Ziffer oder ein Buchstabe ohne S, L, O, I, B, Z
- eine Ziffer
- Optionaler Bindestrich
- ein Buchstabe ohne S, L, O, I, B, Z
- eine Ziffer oder ein Buchstabe ohne S, L, O, I, B, Z
- eine Ziffer
- Optionaler Bindestrich
- zwei Buchstaben ohne S, L, O, I, B, Z
- Zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_mbi_card` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keyword_mbi_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_mbi_card` findet Inhalte, die dem Muster entsprechen.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- Mbi
- Mbi #
- Nehmerempfänger #
- bezeichner des Empfängers
- empfängerempfänger nein
- Zahl der Empfänger
- Nehmerempfänger #


## <a name="mexico-unique-population-registry-code-curp"></a>Unique Population Registry Code (CURP) für Mexiko

### <a name="format"></a>Format

Alphanumerisches Muster mit 18 Zeichen

### <a name="pattern"></a>Muster

- vier Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- sechs Ziffern, die ein gültiges Datum angeben
- ein Buchstabe – H/h oder M/m
- zwei Buchstaben, die einen gültigen Zustandscode für die Zustandsvariatur angeben
- drei Buchstaben
- ein Buchstabe oder eine Ziffer
- eine Ziffer

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_mexico_population_registry_code` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keyword_mexico_population_registry_code` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_mexico_population_registry_code` sucht Inhalte, die dem Muster entsprechen.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Eindeutiger Registrierungscode für grundlose Populationen 
- Eindeutiger Populationscode
- CURP
- Persönliche ID
- Eindeutige ID
- personalid
- Personalidnummer
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- Personal Identidad Clave
- ClaveÚnica
- warteschlangen
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>Dienstnummer des niederländischen Bürgers (BSN)

### <a name="format"></a>Format

acht oder neun Ziffern mit optionalen Leerzeichen

### <a name="pattern"></a>Muster

acht bis neun Ziffern:
- drei Ziffern
- ein Leerzeichen (optional)
- drei Ziffern
- ein Leerzeichen (optional)
- Zwei-drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_netherlands_bsn nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_netherlands_bsn gefunden.
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

- Bsn #
- Bsn
- überzählservicenummer
- Citizen Service Number
- Personennummer
- Persönliche Nummer
- Persönlicher numerischer Code
- Personenbezogene Nummer
- persoonlijk nummer
- persoonlijke numerieke code
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- Sozialversicherungsnummer
- Sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Niederländische Führerscheinnummer

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_netherlands_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_netherlands_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>s_license_number Keywords_netherlands_eu_driver

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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_netherlands_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_netherlands_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_netherlands_eu_passport_date` findet Datum im Format DD MMM/MMM JJJJ (Beispiel - 26 MAA/MRT 2012)

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_netherlands_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_netherlands_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Niederländische Steueridentifikationsnummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_netherlands_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_netherlands_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_netherlands_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- schützenânske-Steueridentifikation
- hu über impuesto id number
- hukennung impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto-Identifikationsnummer
- impuesto number
- belasting id nummer
- belasting identificatie
- emirates belasting identificatienummer
- belastingnummer
- belasting identificatie
- Niederländische Steueridentifikation
- Steueridentifikation des Landes
- Netherlands tin
- Netherland's tin
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steueridentifikations-Tal
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- tax tal
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="netherlands-value-added-tax-number"></a>Niederländische Umsatzsteuernummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
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
- Zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_netherlands_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_netherlands_value_added_tax_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_netherlands_value_added_tax_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Umsatzsteuernummer
- umsatzsteuer-Nr.
- Mwst #
- wearde tafoege tax getal
- btw nếmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Neuseeländische Bankkontonummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

14-stelliges bis 16-stelliges Muster mit optionalem Trennzeichen

### <a name="pattern"></a>Muster

14-stelliges bis 16-stelliges Muster mit optionalem Trennzeichen:

- Zwei Ziffern
- Optionaler Bindestrich oder Leerzeichen
- drei bis vier Ziffern
- Optionaler Bindestrich oder Leerzeichen
- sieben Ziffern
- Optionaler Bindestrich oder Leerzeichen
- zwei bis drei Ziffern
- Einen Optionsstrich oder Leerzeichen

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_zealand_bank_account_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_new_zealand_bank_account_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_zealand_bank_account_number nach Inhalten sucht, die dem Muster entsprechen.

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


## <a name="new-zealand-drivers-license-number"></a>Neuseeländische Führerscheinnummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
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

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_newzealand_driver_license_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_newzealand_driver_license_number gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_newzealand_driver_license_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslicence
- Treiberlizenzen
- Drivers lic
- Treiberlizenzen
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's licence
- Führerschein
- driverlic #
- Treiber #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- international driving permit
- international driving permits
- nz automobile association
- New zealand automobile association


## <a name="new-zealand-inland-revenue-number"></a>Neuseeländische Inlandsumsatznummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

acht oder neun Ziffern mit optionalen Trennzeichen

### <a name="pattern"></a>Muster

acht oder neun Ziffern mit optionalen Trennzeichen

- zwei oder drei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- drei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_zealand_inland_revenue_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_new_zealand_inland_revenue_number gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_zealand_inland_revenue_number nach Inhalten sucht, die dem Muster entsprechen.

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
- Dritte Zahl
- Inlandsumsatznummer


## <a name="new-zealand-ministry-of-health-number"></a>Neuseeländisches Gesundheitsministerium

### <a name="format"></a>Format

drei Buchstaben, ein Leerzeichen (optional) und vier Ziffern

### <a name="pattern"></a>Muster

- drei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) außer "I" und "O"
- ein Leerzeichen (optional)
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_nz_terms wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Nhi
- New Zealand
- Gesundheitswesen
- Behandlung
- Indexnummer des nationalen Gesundheitszustands
- nhi-Zahl
- nhi nein.
- Nhi #
- National Health Index No.
- Nationale Integritätsindex-ID
- National Health Index #

## <a name="new-zealand-social-welfare-number"></a>Neuseeländische soziale Netzwerke ( Social Number)

Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

- drei Ziffern
- Optionaler Bindestrich
- drei Ziffern
- Optionaler Bindestrich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_newzealand_social_welfare_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_newzealand_social_welfare_number gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_newzealand_social_welfare_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Sozialhilfe #
- Sozialhilfe #
- soziale Netzwerke Nein.
- soziale Zahl
- swn #


## <a name="norway-identification-number"></a>Norwegen-Identifikationsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- sechs Ziffern im Format DDMMYY, die das Geburtsdatum darstellen
- Dreistellige Einzelnummer
- Zwei Prüfziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_norway_id_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_norway_id_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_norway_id_numbe nach Inhalten sucht, die dem Muster entsprechen.
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
- Identifizierung
- Personennummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>Unified Multi-Purpose Identification Number (Unified Multi-Purpose Identification Number) auf den Philippinen

### <a name="format"></a>Format

12 Ziffern, durch Bindestriche getrennt

### <a name="pattern"></a>Muster

12 Ziffern:
- vier Ziffern
- Bindestrich
- sieben Ziffern
- Bindestrich
- eine Ziffer

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_philippines_unified_id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_philippines_id gefunden.

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

## <a name="poland-drivers-license-number"></a>Polen– Führerscheinnummer

### <a name="format"></a>Format

14 Ziffern mit zwei Schrägstrichen

### <a name="pattern"></a>Muster

14 Ziffern und zwei Schrägstriche:

- fünf Ziffern
- Schrägstrich
- Zwei Ziffern
- Schrägstrich
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_poland_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_poland_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_poland_eu_drivers_license_number"></a>s_license_number Keywords_poland_eu_driver

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Polen-Identitätskarte

### <a name="format"></a>Format

drei Buchstaben und sechs Ziffern

### <a name="pattern"></a>Muster

drei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Aufzingód osobosty
- Numer dowodu osobostego
- Nazwa i numer dowodu osobostego
- Nazwa i nr dowodu osobostego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>Nationale POLEN-ID (PESEL)

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

- sechs Ziffern, die das Geburtsdatum im Format JJMMTD darstellen
- vier Ziffern
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_pesel_identification_number wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- für "osobosty"
- eigenschaftódosobosty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>Reisepassnummer für Polen
Diese Entität für vertrauliche Informationstypen ist im Vertraulichen Informationstyp "EU Passport Number" enthalten. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

zwei Buchstaben und sieben Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_polish_passport_number_v2` sucht Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_polish_national_passport_number` wird gefunden.
- Ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_polish_passport_number_v2` sucht Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_polish_national_passport_number` wird gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_polish_passport_number_v2` sucht Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- Nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="poland-regon-number"></a>Polen REGON-Nummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

9- oder 14-stellige Zahl

### <a name="pattern"></a>Muster

neunstellige oder 14-stellige Nummer:

- neun Ziffern oder
- neun Ziffern
- Bindestrich
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_polish_regon_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_polish_regon_number gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_polish_regon_number nach Inhalten sucht, die dem Muster entsprechen.

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

- Regon-ID
- statistische Zahl
- statistische ID
- statistisches Nein
- Regon-Zahl
- regonid #
- regonno #
- Unternehmens-ID
- Firmen-ID #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Steueridentifikationsnummer für Polen
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_poland_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_poland_eu_tax_file_number` gefunden.


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

- Nip #
- Nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- Umsatzsteuer-ID #
- Umsatzsteuer-ID
- umsatzsteuer-Nr.
- Umsatzsteuernummer
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>Portugal - Bürgerkartennummer

### <a name="format"></a>Format

acht Ziffern

### <a name="pattern"></a>Muster

acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_portugal_citizen_card nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_portugal_citizen_card gefunden.

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
- Bürgerkarte
- Dokumentnummer
- documento de identificação
- ID-Nummer
- Idnr.
- identification number
- Identitätskarte nein
- Identitätskartennummer
- Nationale ID-Karte
- Nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>Portugal- Führerscheinnummer

### <a name="format"></a>Format

zwei Muster – zwei Buchstaben gefolgt von 5 bis 8 Ziffern mit Sonderzeichen

### <a name="pattern"></a>Muster

Muster 1: Zwei Buchstaben gefolgt von 5/6 mit Sonderzeichen:
- Zwei Buchstaben (Groß-/Kleinschreibung wird nicht beachtet)
- Ein Bindestrich 
- Fünf oder sechs Ziffern
- Ein Leerzeichen
- Eine Ziffer

Muster 2: Ein Buchstabe gefolgt von 6/8 Ziffern mit Sonderzeichen:
- Ein Buchstabe (Groß-/Kleinschreibung wird nicht beachtet)
- Ein Bindestrich 
- Sechs oder acht Ziffern
- Ein Leerzeichen
- Eine Ziffer


### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_portugal_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver's_license_number

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

## <a name="portugal-passport-number"></a>Portugiesisch -Reisepassnummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

ein Buchstabe gefolgt von sechs Ziffern:

- ein Buchstabe (ohne Groß-/Kleinschreibung)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_portugal_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_portugal_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_portugal_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- Portugiesischer Passport
- portugiesischer Passeport
- portugiesischer Passaporte
- passaporte nế
- passeport nế
- números de passaporte
- Portugiesen- Passports
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="portugal-tax-identification-number"></a>Portugal- Steueridentifikationsnummer

### <a name="format"></a>Format

neun Ziffern mit optionalen Leerzeichen

### <a name="pattern"></a>Muster

- drei Ziffern
- Ein optionaler Bereich
- drei Ziffern
- Ein optionaler Bereich
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_portugal_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_portugal_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_portugal_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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

- Cpf #
- Cpf
- Nif #
- Nif
- número de identificação fisca
- numero fiscal
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="romania-drivers-license-number"></a>Führerscheinnummer für Rumänien

### <a name="format"></a>Format

ein Zeichen gefolgt von acht Ziffern

### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von acht Ziffern:
- ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung) oder eine Ziffer
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_romania_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_romania_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver's_license_number

- permis dekonsensere
- permisului de subsetere
- permisului subsetere
- permisele de exponentialere
- permiseles Gerüst
- permis vereistere

## <a name="romania-personal-numeric-code-cnp"></a>Numerischer Code für Rumänien (Personal Numeric Code, CNP)
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

- Eine Ziffer von 1 bis 9
- sechs Ziffern, die das Geburtsdatum darstellen (JJMMTD)
- zwei Ziffern, die 01-52 oder 99 sein können
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_romania_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_romania_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_romania_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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

- Cnp #
- Cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- Versicherungsnummer
- Versicherungsnummer #
- Nationale ID #
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
- Pin #
- Pin
- Steuerdatei Nein
- tax file number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #
- eindeutige Identifikationsnummer
- Eindeutige Identitätsnummer
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Reisepassnummer für Rumänien

### <a name="format"></a>Format

acht oder neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

acht oder neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_romania_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_romania_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_romania_eu_passport_date` sucht datums im Format DD MMM/MMM JJ (Beispiel- 01 FEB/FEB 10) oder ein Schlüsselwort von `Keywords_eu_passport_date` gefunden wird

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_romania_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_romania_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="russia-passport-number-domestic"></a>Russische Reisepassnummer für Inland
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10-stellige Zahl

### <a name="pattern"></a>Muster

10-stellige Zahl:

- Zwei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- Zwei Ziffern
- Ein optionaler Bereich
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_Russian_Passport_Number_Domestic sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Russian_Passport_Number gefunden.

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
- Passport No
- Pass #
- Passport-ID
- Passportno #
- Passportnummer #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Internationale Reisepassnummer für Russland
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Neunstellige Zahl

### <a name="pattern"></a>Muster

Neunstellige Zahl:

- Zwei Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_Russian_Passport_Number_International sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Russian_Passport_Number gefunden.

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
- Passport No
- Pass #
- Passport-ID
- Passportno #
- Passportnummer #
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

10 Ziffern

### <a name="pattern"></a>Muster

10 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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


## <a name="singapore-national-registration-identity-card-nric-number"></a>Nummer der nationalen Registrierungsidentitätskarte (NRIC) singapurisch

### <a name="format"></a>Format

neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

- neun Buchstaben und Ziffern:
- der Buchstabe "F", "G", "S" oder "T" (groß- und kleingeschrieben)
- sieben Ziffern
- Eine alphabetische Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_singapore_nric nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_singapore_nric gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_singapore_nric nach Inhalten sucht, die dem Muster entsprechen.
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
- Ic
- Foreign Identification Number
- Fin
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>Führerscheinnummer der Slowakei

### <a name="format"></a>Format

ein Zeichen gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

ein Zeichen gefolgt von sieben Ziffern

- ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung) oder eine Ziffer
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovakia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_slovakia_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>s_license_number Keywords_slovakia_eu_driver

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Slowakei – persönliche Nummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun oder 10 Ziffern mit optionalem umgekehrten Schrägstrich

### <a name="pattern"></a>Muster

- sechs Ziffern, die das Geburtsdatum darstellen
- Optionaler Schrägstrich (/)
- drei Ziffern
- Eine optionale Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovakia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_slovakia_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovakia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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
- Geburtsdatum
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- ID-Nummer
- Idnr.
- identification number
- identifikačná karta č
- identifikačné číslo
- Identitätskarte nein
- Identitätskartennummer
- národná identifikačná značka č
- nationale Nummer
- nationale Zahl #
- nemzeti személyazonosító ig telemetrvány
- Personalidnummer #
- rč
- rodne cislo
- rodné číslo
- social security number
- Ssn #
- Ssn
- személyi ig telemetrvány szám
- személyi ig telemetrvány száma
- személyigvezvány szám
- Steuerdatei Nein
- tax file number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #

## <a name="slovakia-passport-number"></a>Reisepassnummer der Slowakei

### <a name="format"></a>Format

Eine Ziffer oder ein Buchstabe gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

Eine Ziffer oder ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung) gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovakia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_slovakia_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovakia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_slovakia_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
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


## <a name="slovenia-drivers-license-number"></a>Slowenien- Führerscheinnummer

### <a name="format"></a>Format

neun Ziffern ohne Leerzeichen und Trennzeichen

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovenia_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_slovenia_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>s_license_number Keywords_slovenia_eu_driver

- vozniško dovoljenje
- vozniška številka licence
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Eindeutige Master-Citizen-Nummer für Slowenien
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

13 Ziffern im angegebenen Muster:

- sieben Ziffern, die dem Geburtsdatum (DDMMLLL) entsprechen, wobei "LLL" den letzten drei Ziffern des Geburtsdatums entspricht.
- Zwei Ziffern, die dem Geburtsdatum "50" entsprechen
- drei Ziffern, die einer Kombination aus Geschlecht und Seriennummer für Personen entsprechen, die am selben Tag zur Welt kommen. 000-499 für Männlich und 500-999 für Frau.
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_slovenia_eu_national_id_card` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_national_id_card` sucht Inhalte, die dem Muster entsprechen.

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

- durnstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- identity card
- nationalna id
- nationalni potni list
- national id
- osebna izkaznica
- osebni cod
- osebni ne
- osebni številka
- Persönlicher Code
- Persönliche Nummer
- Persönlicher numerischer Code
- številka državljana
- eindeutige Bürgernummer
- Eindeutige ID-Nummer
- Eindeutige Identitätsnummer
- eindeutige Master-Citizen-Nummer
- Eindeutige Registrierungsnummer
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Reisepassnummer für Slowenien

### <a name="format"></a>Format

zwei Buchstaben gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

zwei Buchstaben gefolgt von sieben Ziffern:

- der Buchstabe "P"
- Ein Großbuchstabe
- sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovenia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_slovenia_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_eu_passport_date1` findet Datum im Format DD.MM.JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_slovenia_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_slovenia_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- Potni-Liste #
- datum rojstva
- Potni-Liste
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="slovenia-tax-identification-number"></a>Steueridentifikationsnummer Für Slowenien
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

- Eine Ziffer von 1 bis 9
- sechs Ziffern
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_slovenia_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_slovenia_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Steuerdatei Nein
- tax file number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="south-africa-identification-number"></a>Südafrika-Identifikationsnummer

### <a name="format"></a>Format

13 Ziffern, die Leerzeichen enthalten können

### <a name="pattern"></a>Muster

13 Ziffern:
- sechs Ziffern im Format JJMMTD, die das Geburtsdatum darstellen
- vier Ziffern
- ein einstelliger Indikator für die Zugehörigkeit
- die Ziffer "8" oder "9"
- eine Ziffer, bei der es sich um eine Prüfsummenziffer handelt

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_south_africa_identification_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_south_africa_identification_number gefunden.
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
- Identifizierung

## <a name="south-korea-resident-registration-number"></a>In Südkorea ansässigen Registrierungsnummer

### <a name="format"></a>Format

13 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

13 Ziffern:
- sechs Ziffern im Format JJMMTD, die das Geburtsdatum darstellen
- Bindestrich
- Eine Ziffer, die durch das Jahr 100 und das Geschlecht bestimmt wird
- Vierstelliger Code für die Region der Geburtsdatum
- Eine Ziffer, die verwendet wird, um Personen zu unterscheiden, für die die vorherigen Zahlen identisch sind
- eine Prüfziffer.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_south_korea_resident_number nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_south_korea_resident_number gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_south_korea_resident_number nach Inhalten sucht, die dem Muster entsprechen.
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

Acht Ziffern gefolgt von einem Zeichen:

- acht Ziffern
- Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung wird nicht beachtet)

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_spain_eu_driver's_license_number` wird gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` sucht Inhalte, die dem Muster entsprechen.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_spain_eu_drivers_license_number"></a>s_license_number Keywords_spain_eu_driver

- permiso de enviroción
- permiso enviroción
- licencia de vivair
- licencia vivair
- permisosynir
- permiso dekonshentir
- permisos dekonshentir
- permisos vererzir
- Carnet- und Carnet-6000
- carnet dekonsensir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>Spanien DNI
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Acht Ziffern gefolgt von einem Zeichen

### <a name="pattern"></a>Muster

sieben Ziffern gefolgt von einem Zeichen

- acht Ziffern
- Ein optionaler Leerzeichen oder Bindestrich
- ein Prüfbuchstabe (ohne Groß-/Kleinschreibung)

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_spain_eu_national_id_card"` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_DL_and_NI_number_citizen` oder `Func_spain_eu_DL_and_NI_number_foreigner` sucht Inhalte, die dem Muster entsprechen.


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
- Dni #
- Dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- Versicherungsnummer
- national identification number
- Nationale Identität
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
- Uniqueid #

## <a name="spain-passport-number"></a>Spanische Reisepassnummer

### <a name="format"></a>Format

eine Kombination aus acht oder neun Zeichen aus Buchstaben und Zahlen ohne Leerzeichen oder Trennzeichen

### <a name="pattern"></a>Muster

eine acht- oder neunstellige Kombination aus Buchstaben und Zahlen:

- zwei Ziffern oder Buchstaben
- eine Ziffer oder ein Buchstabe (optional)
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nicht anwendbar

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_spain_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_spain_eu_passport_number` wird gefunden.
- Der reguläre Ausdruck `Regex_spain_eu_passport_date` findet Datum im Format DD-MM-JJJJ, oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_spain_eu_passport_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_passport_number` oder `Keywords_spain_eu_passport_number` wird gefunden.

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

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- Spanisches Passport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="spain-social-security-number-ssn"></a>Spanische Sozialversicherungsnummer (SSN)


### <a name="format"></a>Format

11-12 Ziffern

### <a name="pattern"></a>Muster

11-12 Ziffern:
- Zwei Ziffern
- Schrägstrich (optional)
- sieben bis acht Ziffern
- Schrägstrich (optional)
- Zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_spanish_social_security_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.
- - Ein Schlüsselwort wurde  `Keywords_spain_eu_ssn_or_equivalent` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_spanish_social_security_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- Ssn
- Ssn #
- socialsecurityno
- Sozialversicherung nein
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>Steueridentifikationsnummer Spaniens
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster

### <a name="pattern"></a>Muster

Spanische natürliche Personen mit einer nationalen Spanisch-Identitätskarte:

- acht Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung beachten)

Nicht-Gebietsansässige S sinusards ohne nationale Spanische Identitätskarte

- Großbuchstaben "L" (Groß-/Kleinschreibung beachten)
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung beachten)

Gebietsansässige Personen unter 14 Jahren ohne nationale Spanische Identitätskarte:

- Großbuchstaben "K" (Groß-/Kleinschreibung beachten)
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung beachten)

Zuordnen mit der Identifikationsnummer eines Fremden

- Ein Großbuchstabe, der "X", "Y" oder "Z" ist (Groß-/Kleinschreibung beachten)
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung beachten)

Zählung ohne Identifikationsnummer eines Fremden

- Ein Großbuchstabe mit dem Wert "M" (Groß-/Kleinschreibung beachten)
- sieben Ziffern
- Ein Großbuchstabe (Groß-/Kleinschreibung beachten)

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_tax_file_number` oder `Func_spain_eu_DL_and_NI_number_citizen` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_spain_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_spain_eu_tax_file_number` oder `Func_spain_eu_DL_and_NI_number_citizen` sucht Inhalte, die dem Muster entsprechen.

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

- Cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- Steuerdatei Nein
- tax file number
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="sql-server-connection-string"></a>SQL Server Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "User Id", "User ID", "uid" oder "UserId", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster beschrieben sind.

### <a name="pattern"></a>Muster

- die Zeichenfolge "User Id", "User ID", "uid" oder "UserId"
- Eine beliebige Kombination aus 1 bis 200 Klein- oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- die Zeichenfolge "Password" oder "pwd", wobei "pwd" kein Kleinbuchstabe vorangestellt ist
- Ein Gleichheitszeichen (=)
- Ein beliebiges Zeichen, bei dem es sich nicht um ein Dollarzeichen ($), ein Prozentsymbol (≡ größer als Symbol (>), an einem Symbol (@), anführungszeichen (), ein Semikolon (;), eine linke Klammer([) oder eine linke Klammer ({) handelt
- Eine beliebige Kombination aus 7 bis 128 Zeichen, die kein Semikolon (;), Schrägstrich (/) oder Anführungszeichen (") sind
- ein Semikolon (;) oder Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck CEP_Regex_SQLServerConnectionString nach Inhalten sucht, die dem Muster entsprechen.
- Ein Schlüsselwort aus CEP_GlobalFilter wurde nicht gefunden.
- Der reguläre Ausdruck CEP_PasswordPlaceHolder findet keine Inhalte, die dem Muster entsprechen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet keine Inhalte, die dem Muster entsprechen.

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

- Some-Password
- somepassword
- secretPassword
- Beispiel

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Dieser Typ vertraulicher Informationen identifiziert diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht anhand einer Schlüsselwortliste.

- Kennwort oder Pwd gefolgt von 0-2 Leerzeichen, einem Gleichheitszeichen (=), 0-2 Leerzeichen und einem Sternchen (*) -OR-
- Kennwort oder Pwd gefolgt von:
    - Gleichheitszeichen (=)
    - Kleiner als Symbol (<)
    - Eine Beliebige Kombination aus 1 bis 200 Zeichen, die Groß- oder Kleinbuchstaben, Ziffern, ein Sternchen (*), Bindestrich (-), Unterstreichungszeichen (_) oder Leerzeichen sind
    - Größer als Symbol (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Dieser Typ vertraulicher Informationen identifiziert diese Schlüsselwörter mithilfe eines regulären Ausdrucks, nicht anhand einer Schlüsselwortliste.

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->netto

## <a name="sweden-drivers-license-number"></a>Schweden-Führerscheinnummer

### <a name="format"></a>Format

10 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

10 Ziffern, die einen Bindestrich enthalten:

- sechs Ziffern
- Bindestrich
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck  `Regex_sweden_eu_driver's_license_number` findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von  `Keywords_eu_driver's_license_number` oder `Keywords_sweden_eu_driver's_license_number` wird gefunden.

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

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver's_license_number

- ajokortti
- permis dekonsensere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de subsetere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>Nationale id für Schweden

### <a name="format"></a>Format

10 oder 12 Ziffern und ein optionales Trennzeichen

### <a name="pattern"></a>Muster

10 oder 12 Ziffern und ein optionals Trennzeichen:
- zwei Ziffern (optional)
- Sechs Ziffern im Datumsformat JJMMTT
- Trennzeichen von "-" oder "+" (optional)
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_swedish_national_identifier` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keywords_swedish_national_identifier` gefunden
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_swedish_national_identifier` sucht Inhalte, die dem Muster entsprechen.
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

- ID Nein
- ID-Nummer
- Id #
- Idnr.
- identification number
- identifikationsnumret #
- identifikationsnumret
- Identitetshandling
- Identitätsdokument
- Identität nein
- Identitätsnummer
- id-nummer
- Persönliche ID
- Personnummer #
- Personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>Reisepassnummer für Schweden

### <a name="format"></a>Format

acht Ziffern

### <a name="pattern"></a>Muster

acht aufeinander folgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- der reguläre Ausdruck Regex_sweden_passport_number Inhalte findet, die dem Muster entsprechen.
- ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_sweden_passport` gefunden wird.
- Der reguläre Ausdruck `Regex_sweden_eu_passport_date` findet ein Datum im Format DD MMM/MMM JJ (01 JAN/JAN 12), oder es wird ein Schlüsselwort `Keywords_eu_passport_date` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- der reguläre Ausdruck Regex_sweden_passport_number Inhalte findet, die dem Muster entsprechen.
- ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keyword_sweden_passport` gefunden wird.


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- Karten für die Registrierung
- g3-Verarbeitungsgebühren
- Mehrfacheintrag
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- visa
- visas
- Einzelner Eintrag
- sverige pass
- visa requirements
- Visaverarbeitung
- Visatyp

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- Problemdatum
- Ablaufdatum


## <a name="sweden-tax-identification-number"></a>Steueridentifikationsnummer (Schweden)
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern und ein Symbol im angegebenen Muster

### <a name="pattern"></a>Muster

10 Ziffern und ein Symbol:

- sechs Ziffern, die dem Geburtsdatum (JJMMTD) entsprechen
- Pluszeichen oder Minuszeichen
- drei Ziffern, die die Identifikationsnummer eindeutig machen, wobei:
  - bei Nummern, die vor 1990 ausgegeben wurden, identifizieren die siebente und achte Ziffer den Geburtsdatumskreis oder fremde Menschen.
  - Die Ziffer an der neunten Position gibt an, dass das Geschlecht entweder bei einem Mädchen oder sogar bei einer Frau ungerade ist.
- eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_sweden_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_sweden_eu_tax_file_number` gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_sweden_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.

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
- Personnummer
- skatt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- Steuerdatei
- tax id
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #


## <a name="swift-code"></a>SWIFT-Codes

### <a name="format"></a>Format

vier Buchstaben gefolgt von 5 bis 31 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

vier Buchstaben gefolgt von 5 bis 31 Buchstaben oder Ziffern:
- Aus vier Buchstaben bestehender Bankcode (Groß-/Kleinschreibung wird nicht beachtet)
- Ein optionaler Bereich
- 4 bis 28 Buchstaben oder Ziffern (BBAN, Basic Bank Account Number)
- Ein optionaler Bereich
- ein bis drei Buchstaben oder Ziffern (Rest des BBAN)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- schnell #
- swiftcode
- Swiftnumber
- Swiftroutingnummer
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- Bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>Bic
- code identificateur de banque
- SWIFTドード
- SWIFT番号
- BIC番号
- BICドード
- SWIFT ドード
- SWIFT 番号
- BIC 番号
- BIC ドード
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Schweiz SSN AHV-Nummer
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

13-stellige Zahl

### <a name="pattern"></a>Muster

13-stellige Zahl:

- drei Ziffern – 756
- Ein optionaler Punkt
- vier Ziffern
- Ein optionaler Punkt
- vier Ziffern
- Ein optionaler Punkt
- Zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_swiss_social_security_number_ahv nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keywords_swiss_social_security_number_ahv gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_swiss_social_security_number_ahv nach Inhalten sucht, die dem Muster entsprechen.

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

- Ahv
- Ssn
- pid
- Versicherungsnummer
- Personalidno #
- social security number
- Persönliche ID-Nummer
- Persönliche Identifikationsnr.
- insuranceno #
- uniqueidno #
- eindeutige Identifikationsnr.
- AVS-Nummer
- Persönliche Identität keine Versicherungsnummer
- identifikationsnummer
- Einzigartige Identität nicht
- sozialversicherungsnummer
- id personnelle id
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>Nationale Kennnummer Taiwans

### <a name="format"></a>Format

ein Buchstabe (in Englisch), gefolgt von neun Ziffern

### <a name="pattern"></a>Muster

ein Buchstabe (in Englisch), gefolgt von neun Ziffern:
- ein Buchstabe (in Englisch ohne Beachtung der Groß-/Kleinschreibung)
- die Ziffer "1" oder "2"
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

## <a name="taiwan-passport-number"></a>Taiwan-Reisepassnummer

### <a name="format"></a>Format

- biometrische Reisepassnummer: neun Ziffern
- Nicht biometrische Reisepassnummer: neun Ziffern

### <a name="pattern"></a>Muster
Biometrische Reisepassnummer:
- das Zeichen "3"
- acht Ziffern

Nicht biometrische Reisepassnummer:
- neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_taiwan_passport sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_taiwan_passport gefunden.

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

## <a name="taiwan-resident-certificate-arctarc-number"></a>Nummer des in Taiwan ansässigen Zertifikats (ARC/TARC)

### <a name="format"></a>Format

10 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

10 Buchstaben und Ziffern:
- zwei Buchstaben (groß- und kleingeschrieben)
- acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_taiwan_resident_certificate nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_taiwan_resident_certificate gefunden.

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

## <a name="thai-population-identification-code"></a>Kenncode für thailändische Populationen

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffern:
- Die erste Ziffer ist nicht Null oder neun.
- 12 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Thai_Citizen_Id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Thai_Citizen_Id gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Thai_Citizen_Id nach Inhalten sucht, die dem Muster entsprechen.

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

## <a name="turkish-national-identification-number"></a>Nationale Kennnummer für Türkisch

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Turkish_National_Id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Turkish_National_Id gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_Turkish_National_Id nach Inhalten sucht, die dem Muster entsprechen.

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
- TC Kimlik nubüchersı
- Vatandaşlık nuatursı
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Großbritannien. Führerscheinnummer

### <a name="format"></a>Format

Kombination aus 18 Buchstaben und Ziffern im angegebenen Format

### <a name="pattern"></a>Muster

18 Buchstaben und Ziffern:
- Fünf Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer "9" anstelle eines Buchstabens.
- Eine Ziffer.
- Fünf Ziffern im Datumsformat MMDDY für das Geburtsdatum. Das siebte Zeichen wird um 50 erhöht, wenn der Treiber männlich ist; für Prüfung, 51 bis 62 anstelle von 01 bis 12.
- Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer "9" anstelle eines Buchstabens.
- Fünf Ziffern.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_uk_drivers_license` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde `Keywords_eu_driver's_license_number` gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion `Func_uk_drivers_license` sucht Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- Treiber
- Driverlicense
- Driverlicenses
- Treiberlizenz
- Treiberlizenzen
- Driver lic
- Treiberlizenzen
- driver license
- driver licenses
- Führerschein
- Treiberlizenzen
- driverslic
- Driverslics
- Driverslicence
- Treiberlizenzen
- driverslicense
- driverslicenses
- Drivers lic
- Treiberlizenzen
- drivers license
- drivers licenses
- drivers licence
- Lizenzen für Treiber
- driver'lic
- Driver'lics
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver' lic
- Treiberlizenzen
- Führerschein
- Treiberlizenzen
- Führerschein
- Führerschein
- Driver'slic
- Treiberlizenzen
- Driver'slicense
- Segmente des Treibers
- Driver'slicence
- Segmente des Treibers
- Treiberlic
- Treiberlizenzen
- driver's license
- driver's licenses
- driver's licence
- Führerschein
- Dl #
- Dls #
- driverlic #
- Treiber #
- Driverlicense #
- Driverlicenses #
- Treiberlizenz #
- Treiberlizenzen #
- Driver lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenzen #
- driverslic #
- Driverslics #
- driverslicense #
- driverslicenses #
- Driverslicence #
- Treiberlizenzen #
- Drivers lic #
- Treiberlizenzen #
- Treiberlizenz #
- Treiberlizenzen #
- Treiberlizenz #
- Lizenzen für Treiber #
- driver'lic #
- Driver'lics #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver' lic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Driver'slic #
- Treiberlizenzen #
- Driver'slicense #
- Segmente des Treibers #
- Driver'slicence #
- Segmente des Treibers #
- Treiberlic #
- Treiberlizenzen #
- Führerschein #
- Treiberlizenzen #
- Führerschein #
- Führerschein #
- Führerschein 
- driving license
- dlno #
- driv lic
- driv licen
- Driv-Lizenz
- Drivlizenzen
- Driv-Lizenz
- Driv-Lizenzen
- Treiberlizenzen
- Drivers licen
- Driver's licen
- Driving lic
- Fahren mit Licen
- Führerscheine
- driving licence
- driving licences
- Führerschein
- dl no
- dlno
- DL-Nummer


## <a name="uk-electoral-roll-number"></a>Großbritannien. Rollnummer

### <a name="format"></a>Format

zwei Buchstaben gefolgt von 1 bis 4 Ziffern

### <a name="pattern"></a>Muster

zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) gefolgt von 1 bis 4 Zahlen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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


## <a name="uk-national-health-service-number"></a>Großbritannien. Nummer des nationalen Gesundheitsdiensts

### <a name="format"></a>Format

10-17 Ziffern, durch Leerzeichen getrennt

### <a name="pattern"></a>Muster

10 bis 17 Stellen:
- 3 oder 10 Ziffern
- ein Leerzeichen
- drei Ziffern
- ein Leerzeichen
- vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Nhs
- health services authority
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- Gp
- Dob
- O.B.
- Date of Birth
- Birth Date

## <a name="uk-national-insurance-number-nino"></a>Großbritannien. Nationale Versicherungsnummer (NINO)
Diese Entität für vertrauliche Informationstypen ist im vertraulichen Informationstyp "NATIONALE IDENTIFIKATIONSNUMMER" der EU enthalten. Es ist auch als eigenständige Entität für vertrauliche Informationstypen verfügbar.

### <a name="format"></a>Format

Sieben oder neun Zeichen getrennt durch Leerzeichen oder Gedankenstriche

### <a name="pattern"></a>Muster

Zwei mögliche Muster:

- zwei Buchstaben (gültige NINOs verwenden nur bestimmte Zeichen in diesem Präfix, die von diesem Muster überprüft werden, ohne Groß-/Kleinschreibung zu beachten)
- sechs Ziffern
- entweder 'A', 'B', 'C' oder 'D' (wie das Präfix sind nur bestimmte Zeichen im Suffix zulässig; Groß-/Kleinschreibung nicht beachtet)

ODER

- zwei Buchstaben
- Ein Leerzeichen oder Strich
- Zwei Ziffern
- Ein Leerzeichen oder Strich
- Zwei Ziffern
- Ein Leerzeichen oder Strich
- Zwei Ziffern
- Ein Leerzeichen oder Strich
- entweder "A", "B", "C" oder "D"

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_uk_nino wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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
- Versicherung
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI-Nummer
- NI-Nein.
- Ni #
- Ni #
- Versicherung #
- Versicherungsnummer
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>Großbritannien. Eindeutige Referenznummer für Denkverweise
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen


### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion  `Func_uk_eu_tax_file_number` sucht Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort wurde  `Keywords_uk_eu_tax_file_number` gefunden.

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
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuerregistrierungsnummer
- umzingen #
- vererzteno #
- anzahl #
- taxno #
- Steuernummer #
- Steuernummer
- tin id
- tin no
- Zinn #

## <a name="us-bank-account-number"></a>US-Bankkontonummer

### <a name="format"></a>Format

6-17 Ziffern

### <a name="pattern"></a>Muster

6 bis 17 aufeinander folgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

## <a name="us-drivers-license-number"></a>U.S. Driver's License Number

### <a name="format"></a>Format

Abhängig vom Bundesstaat

### <a name="pattern"></a>Muster

hängt vom Zustand ab , z. B. New York:
- Neun Ziffern, die wie ddd ddd ddd formatiert sind, stimmen überein.
- Neun Ziffern wie "ddddddddd" stimmen nicht überein.

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.
- Es wird ein Schlüsselwort aus Keyword_us_drivers_license gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- Dl
- Dls
- Cdl
- CDLS
- ID
- Ids
- Dl #
- Dls #
- Cdl #
- CDLS #
- Id #
- Ids #
- ID number
- ID numbers
- Lic
- Lic #

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
- Führerschein
- Treiberlizenzen
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
- Führerschein #
- Treiberlizenzen #
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

- Statusabkürzung (z. B. "NY")
- Statusname (z. B. "New York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>U.S. Individual Tax Identification Number (ITIN)

### <a name="format"></a>Format

neun Ziffern, die mit einer "9" beginnen und eine "7" oder "8" als vierte Ziffer enthalten, optional formatiert mit Leerzeichen oder Gedankenstrichen

### <a name="pattern"></a>Muster

Formatiert:
- die Ziffer "9"
- Zwei Ziffern
- Ein Leerzeichen oder Strich
- ein "7" oder "8"
- eine Ziffer
- ein Leerzeichen oder ein Gedankenstrich
- vier Ziffern

Unformatierte:
- die Ziffer "9"
- Zwei Ziffern
- ein "7" oder "8"
- fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_formatted_itin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_itin wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_itin wurde gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_formatted_itin oder Func_unformatted_itin Inhalte findet, die dem Muster entsprechen.

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

- Steuerzahler
- tax id
- tax identification
- Itin
- i.t.i.n.
- Ssn
- Zinn
- social security
- tax payer
- itins
- umzingen
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>US-Sozialversicherungsnummer (SSN)

### <a name="format"></a>Format

neun Ziffern, die ein formatiertes oder unformatiertes Muster aufweisen können

> [!NOTE]
> Wenn ein SSN vor Mitte 2011 ausgestellt wurde, weist er eine starke Formatierung auf, bei der bestimmte Teile der Zahl in bestimmte Bereiche fallen müssen, um gültig zu sein (es gibt jedoch keine Prüfsumme).

### <a name="pattern"></a>Muster

Vier Funktionen suchen nach SSNs in vier verschiedenen Mustern:
- Func_ssn findet SSNs mit starker Formatierung vor 2011, die mit Strichen oder Leerzeichen formatiert sind (ddd-dd-dddd OR ddd dddd)
- Func_unformatted_ssn findet SSNs mit starker Formatierung vor 2011, die als neun aufeinander folgende Ziffern unformatiert sind (ddddddddd).
- Func_randomized_formatted_ssn sucht nach 2011 SSNs, die mit Bindestrichen oder Leerzeichen formatiert sind (ddd-dd-dddd OR ddd dddd)
- Func_randomized_unformatted_ssn sucht nach 2011 SSNs, die als neun aufeinander folgende Ziffern unformatiert sind (dddddddddd)

### <a name="checksum"></a>Prüfsumme

Nein


### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_unformatted_ssn nach Inhalten sucht, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_randomized_formatted_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie hat nur geringes Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
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

- SSA-Nummer
- social security number
- Soziale Sicherheit #
- Soziale Sicherheit #
- Sozialversicherung nein
- Social Security#
- Soc Sec
- Ssn
- SSNS
- Ssn #
- Ss #
- Ssid

## <a name="us--uk-passport-number"></a>USA/VEREINIGTES KÖNIGREICH passport number

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist sehr sicher, dass diese Art von vertraulichen Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_usa_uk_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keywords_uk_eu_passport_number` wird gefunden.
- Ein Schlüsselwort wurde `Keywords_eu_passport_date` gefunden

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Die Funktion Func_usa_uk_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort von `Keywords_eu_passport_number` oder `Keywords_uk_eu_passport_number` wird gefunden.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- Pass #
- Pass #
- passportid
- Pässe
- Passportno
- Passport No
- Passportnummer
- passport number
- Passportnumbers
- Reisepassnummern

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- britischer Passport
- Uk Passport


## <a name="ukraine-passport-domestic"></a>Inlandspass für die Ukraine
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

neun Ziffern

### <a name="pattern"></a>Muster

neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_Ukraine_Passport_Domestic sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Ukraine_Passport_Domestic gefunden.

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
- Passport No
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Internationales Passport für die Ukraine
Dieser Typ vertraulicher Informationen ist nur für folgende Zwecke verfügbar:
- Richtlinien zur Verhinderung von Datenverlust
- Richtlinien für die Kommunikationscompliance
- Informationsgovernance
- Datensatzverwaltung
- Microsoft Cloud App Security

### <a name="format"></a>Format

Alphanumerisches Muster mit acht Zeichen

### <a name="pattern"></a>Muster

Alphanumerisches Muster mit acht Zeichen:
- zwei Buchstaben oder Ziffern
- sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_Ukraine_Passport_International sucht Inhalte, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_Ukraine_Passport_International gefunden.

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
- Passport No
- паспорт України
- номер паспорта
