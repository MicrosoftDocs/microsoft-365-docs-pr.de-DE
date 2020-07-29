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
description: Die Verhinderung von Datenverlust im Security &amp; Compliance Center umfasst 80 Typen für vertrauliche Informationen, die Sie in ihren DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.
ms.openlocfilehash: 9e1b1261bbb58b1ca65818a5ad304ee186561ae6
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430518"
---
# <a name="sensitive-information-type-entity-definitions"></a>Entitätsdefinitionen für Typen vertraulicher Informationstypen

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) im Compliance Center umfasst viele vertrauliche Informationstypen, die Sie in ihren DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt. Ein vertraulicher Informationstyp wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann. Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden. Beim Auswertungsprozess können auch die Zuverlässigkeitsstufe und die Näherung herangezogen werden.
  
## <a name="aba-routing-number"></a>ABA-Routingnummer

### <a name="format"></a>Format

9 Ziffern in formatiertem oder unformatiertem Muster

### <a name="pattern"></a>Muster

Formatiert
- Vier Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8
- Ein Bindestrich 
- Vier Ziffern
- Ein Bindestrich 
- Eine Ziffer

Unformatiert: 9 aufeinanderfolgende Ziffern, beginnend mit 0, 1, 2, 3, 6, 7 oder 8 

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_aba_routing findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ABA_Routing wurde gefunden.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_aba_routing"></a>Keyword_ABA_Routing

- ABA
- aba #
- aba routing #
- aba routing number
- ABA #
- abarouting #
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bank routing number
- bankrouting #
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>Argentinische nationale Identitätsnummer (DNI)

### <a name="format"></a>Format

Acht Ziffern, durch Punkte getrennt

### <a name="pattern"></a>Muster

Acht Ziffern:
- Zwei Ziffern
- Ein Punkt 
- Drei Ziffern 
- Ein Punkt 
- Drei Ziffern 

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_argentina_national_id wurde gefunden.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- Identity 
- Identification National Identity Card 
- DNI 
- Nic-nationales Personenregister 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>Australische Bankkontennummer

### <a name="format"></a>Format

6-10 Stellen mit oder ohne Bankfilialnummer

### <a name="pattern"></a>Muster

Kontonummer hat 6-10 Stellen.
Australische Bankleitzahl:
- Drei Ziffern 
- Ein Bindestrich 
- Drei Stellen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_australia_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_australia_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_australia_bank_account_number_bsb findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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
- IAEO

   
## <a name="australia-drivers-license-number"></a>Australische Führerscheinnummer

### <a name="format"></a>Format

Neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

Neun Buchstaben und Ziffern: 

- Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) 
- Zwei Ziffern 
- Fünf Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)

ODER

- 1-2 optionale Buchstaben (Groß-/Kleinschreibung irrelevant)  
- 4 bis 9 Ziffern

ODER

- Neun Ziffern oder Buchstaben (Groß-/Kleinschreibung irrelevant)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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
- Driver ' License
- Driver ' Licenses
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
- Driver ' License #
- Driver ' Licenses #
- Driver' License#
- Driver' Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Australische Kranken Kontonummer

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

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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

   
## <a name="australia-passport-number"></a>Australische Passport-Nummer

### <a name="format"></a>Format

Ein Buchstabe gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Ein Buchstabe (Groß-/Kleinschreibung irrelevant) gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Pass #
- Passport-Nr
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- Pass
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- Visa
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Australische Steuerdatei Nummer

### <a name="format"></a>Format

8-9 Ziffern

### <a name="pattern"></a>Muster

8 bis 9 Ziffern, die in der Regel wie folgt mit Leerzeichen dargestellt werden:
- Drei Ziffern 
- Ein optionales Leerzeichen 
- Drei Ziffern 
- Ein optionales Leerzeichen 
- 2 bis 3 Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_australian_tax_file_number findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_Australia_Tax_File_Number oder Keyword_number_exclusions gefunden.
- Die Prüfsumme stimmt.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- TFN

#### <a name="keyword_number_exclusions"></a>Keyword_number_exclusions

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

## <a name="austria-drivers-license-number"></a>Österreichische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_austria_eu_driver's_license_number` wurde gefunden. 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_austria_eu_driver ' s_license_number**
- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- driver's licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- fuhrerschein
- Fuhrerschein Republik Osterreich

## <a name="austria-national-identification-number"></a>Österreichische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Eine Kombination aus Buchstaben, Ziffern und Sonderzeichen mit einer 24 Zeichen Länge
  
### <a name="pattern"></a>Muster

24 Zeichen:
  
-  22 Buchstaben (Unterscheidung nach Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche oder Pluszeichen 
    
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet), Ziffern, Backslashes, Schrägstriche, Pluszeichen oder gleich Zeichen
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_austria_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_austria_eu_national_id_card` wurde gefunden. 
   
```xml
<!-- EU austria_eu_national_id -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- Identitätsnummer
- 
national id
- Personalausweis Republik Österreich

## <a name="austria-passport-number"></a>Österreichische Passnummer
Diese Typen Entität für vertrauliche Informationen ist nur im sensitiveinformation-Typ der EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Ein Buchstabe, gefolgt von einem optionalen Leerzeichen und sieben Ziffern
  
### <a name="pattern"></a>Muster

Eine Kombination aus einem Buchstaben, sieben Ziffern und einem Leerzeichen:
  
- Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)
    
- Ein Leerzeichen (optional)
    
- Sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_austria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_austria_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_austria_eu_passport_number**
- passport number
- Österreichische Passnummer
- Passport-Nummer
- Reisepass
- österreichisch Reisepass

## <a name="austria-social-security-number-or-equivalent-identification"></a>Österreichische Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

10 Ziffern im angegebenen Format
  
### <a name="pattern"></a>Muster

10 Ziffern:
  
-  Drei Ziffern, die einer Seriennummer entsprechen 
- Eine Prüfziffer
- Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_austria_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_austria_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_austria_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- Sozialversicherungsnummer
- social security number
- social security code
- Versicherungsnummer
- Österreichische SSN
- SSN #
- SSN
- versicherungscode
- versicherungscode #
- socialsecurityno #
- sozialversicherungsnummer
- soziale Sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>Österreichische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur für den Typ der vertraulichen Informationen der EU-Steuernummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern mit optionalem Bindestrich und Schrägstrich
  
### <a name="pattern"></a>Muster

Neun Ziffern mit optionalem Bindestrich und Schrägstrich:
  
- Zwei Ziffern
- Ein Bindestrich (optional)
- Drei Ziffern
- Ein Schrägstrich (optional)
- Vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_austria_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_austria_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_austria_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- Österreich
- St.Nr.
- Steuernummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- Steuernummer

## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB-Authentifizierungsschlüssel

### <a name="format"></a>Format

Die Zeichenfolge "DocumentDb" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "DocumentDb"
- Eine beliebige Kombination von zwischen 3-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Ein größer als-Symbol (>), ein Gleichheitszeichen (=), ein Anführungszeichen (") oder ein Apostroph (')
- Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureDocumentDBAuthKey findet Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IaaS-Datenbankverbindungszeichenfolge und Azure SQL-Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Server", "Server" oder "Datenquelle", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolge "cloudapp. Azure" aufgeführt sind.<!--no-hyperlink-->com "oder" cloudapp. Azure.<!--no-hyperlink-->NET "oder" Database. Windows.<!--no-hyperlink-->NET "und die Zeichenfolge" Password "oder" Password "oder" pwd ".

### <a name="pattern"></a>Muster

- Die Zeichenfolge "Server", "Server" oder "Datenquelle"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "cloudapp. Azure.<!--no-hyperlink-->com "," cloudapp. Azure.<!--no-hyperlink-->NET "oder" Database. Windows.<!--no-hyperlink-->NET
- Eine beliebige Kombination von zwischen 1-300 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "Password", "Password" oder "pwd"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Ein oder mehrere Zeichen, bei denen es sich nicht um ein Semikolon handelt (;), Anführungszeichen (") oder Apostroph (')
- Ein Semikolon (;), Anführungszeichen (") oder Apostroph (')

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureConnectionString findet Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-iot-connection-string"></a>Azurey-Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Hostname" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten beschrieben sind, einschließlich der Zeichenfolgen "Azure-Devices".<!--no-hyperlink-->NET "und" SharedAccessKey ".

### <a name="pattern"></a>Muster

- Die Zeichenfolge "Hostname"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "Azure-Devices.<!--no-hyperlink-->NET
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "SharedAccessKey"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von 43 unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureIoTConnectionString findet Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-publish-setting-password"></a>Kennwort für Azure-Veröffentlichungseinstellung

### <a name="format"></a>Format

Die Zeichenfolge "benutzerkwt =" gefolgt von einer alphanumerischen Zeichenfolge.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "benutzerkwt ="
- Eine beliebige Kombination von 60 Kleinbuchstaben oder Ziffern
- Ein Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzurePublishSettingPasswords findet Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.


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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-redis-cache-connection-string"></a>Azure-Zeichenfolgen-Cache-Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "" Codestring. Cache. Windows.<!--no-hyperlink-->NET ", gefolgt von den Zeichen und Zeichenfolgen, die im folgenden Muster dargestellt werden, einschließlich der Zeichenfolge" Password "oder" pwd ".

### <a name="pattern"></a>Muster

- Die Zeichenfolge "" Codestring. Cache. Windows.<!--no-hyperlink-->NET
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "Password" oder "pwd"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureRedisCacheConnectionString findet Inhalte, die mit dem Muster übereinstimmen..
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-sas"></a>Azure-SAS

### <a name="format"></a>Format

Die Zeichenfolge "SIG" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt werden.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "SIG"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von zwischen 43-53 Zeichen, die klein-oder Großbuchstaben, Ziffern oder das Prozentzeichen (%)
- Die Zeichenfolge "% 3D"
- Ein beliebiges Zeichen, das kein niedriger oder groß geschriebener Buchstabe, eine Ziffer oder ein Prozentzeichen ist (%)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureSAS findet Inhalte, die mit dem Muster übereinstimmen.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure Service Bus-Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Endpoint" gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten, einschließlich der Zeichenfolgen "ServiceBus. Windows.<!--no-hyperlink-->NET "und" SharedAccesKey ".

### <a name="pattern"></a>Muster

- Die Zeichenfolge "Endpoint"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "ServiceBus. Windows.<!--no-hyperlink-->NET
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "SharedAccessKey"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von 43 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Ein Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureServiceBusConnectionString findet Inhalte, die mit dem Muster übereinstimmen..
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-storage-account-key"></a>Azure Storage-Kontoschlüssel

### <a name="format"></a>Format

Die Zeichenfolge "DefaultEndpointsProtocol", gefolgt von den Zeichen und Zeichenfolgen, die in dem Muster unten, einschließlich der Zeichenfolge "AccountKey", dargestellt werden.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "DefaultEndpointsProtocol"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "AccountKey"
- 0-2 Leerzeichen
- Ein Gleichheitszeichen (=)
- 0-2 Leerzeichen
- Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, Schrägstrich (/) oder Pluszeichen (+)
- Zwei Gleichheitszeichen (=)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKey findet Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_AzureEmulatorStorageAccountFilter findet **keine** Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_AzureEmulatorStorageAccountFilter

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="azure-storage-account-key-generic"></a>Azure Storage-Kontoschlüssel (generisch)

### <a name="format"></a>Format

Eine beliebige Kombination von 86 unter-oder Großbuchstaben, Ziffern, den Schrägstrich (/) oder Pluszeichen (+), vorangestellt oder gefolgt von den im Muster unten beschriebenen Zeichen.

### <a name="pattern"></a>Muster

- 0-1 des größer als-Symbols (>), Apostroph ('), Gleichheitszeichen (=), Anführungszeichen (") oder Nummernzeichen (#)
- Eine beliebige Kombination von 86 Zeichen mit unter-oder Großbuchstaben, Ziffern, dem Schrägstrich (/) oder Pluszeichen (+)
- Zwei Gleichheitszeichen (=)


### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_AzureStorageAccountKeyGeneric findet Inhalte, die mit dem Muster übereinstimmen.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Belgische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_belgium_eu_driver's_license_number` wurde gefunden.
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords__belgium_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- Führerschein-Nr
- Fuehrerschein-Nr
- Fuehrerschein-Nr

## <a name="belgium-national-number"></a>Belgische Landesnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

11 Ziffern plus Trennzeichen

### <a name="pattern"></a>Muster

11 Ziffern plus Trennzeichen:
- Sechs Ziffern und zwei Punkte im Format JJ.MM.TT für das Geburtsdatum  
- Ein Bindestrich  
- Drei aufeinander folgende Ziffern (ungerade für Männer, gerade für Frauen)  
- Ein Punkt  
- Zwei Ziffern als Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_belgium_national_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_belgium_national_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasten von Mal
- BNN #
- BNN
- Carte d ' identité
- identifizierbare nationale
- identifiantnational #
- identificatie
- Identifizierung
- Identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- Identität
- Inschrift
- nationale Nummer
- National Register
- nationalnumber #
- nationalnumber
- NIF #
- NIF
- Numéro d'assuré
- Numéro de Registre National
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- Numéro National
- numéronational #
- persönliche ID-Nummer
- Personalausweis
- personalidnumber #
- Registratie
- Registrierung
- registrationsnumme
- Registrierung
- social security number

- SSN #
- SSN
- Steuernummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="belgium-passport-number"></a>Belgische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben und gefolgt von sechs Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_belgium_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_belgium_eu_passport_number` wurde gefunden.

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_belgium_eu_passport_number**
- passport number
- belgische Passnummer
- Passport-Nummer
- paspoort
- paspoortnummer
- Reisepass kein
- Reisepass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>Belgische Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_belgium_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_belgium_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_belgium_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- belgische nationale Nummer
- nationale Nummer
- social security number
- nationalnumber #
- SSN #
- SSN
- nationalnumber
- BNN #
- BNN
- persönliche ID-Nummer
- personalidnumber #
- Numéro National
- numéro de sécurité
- Numéro d'assuré
- identifizierbare nationale
- identifiantnational #
- numéronational #

## <a name="belgium-tax-identification-number"></a>Belgische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur für den Identificaiton-Informationstyp "EU-Steuernummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- Zwei Ziffern
- A "0" oder "1"
- Eine Ziffer
- A "0" oder "1" oder "2" oder "3" 
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_belgium_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_belgium_eu_tax_file_number` wurde gefunden. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

- belasten von Mal
- BNN #
- BNN
- Carte d ' identité
- identifizierbare nationale
- identifiantnational #
- identificatie
- Identifizierung
- Identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- Identität
- Inschrift
- nationale Nummer
- National Register
- nationalnumber #
- nationalnumber
- NIF #
- NIF
- Numéro d'assuré
- Numéro de Registre National
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- Numéro National
- numéronational #
- persönliche ID-Nummer
- Personalausweis
- personalidnumber #
- Registratie
- Registrierung
- registrationsnumme
- Registrierung
- social security number

- SSN #
- SSN
- Steuernummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #


## <a name="brazil-cpf-number"></a>Brasilien CPF Number

### <a name="format"></a>Format

11 Ziffern, die eine Prüfziffer umfassen und die formatiert oder unformatiert sein können

### <a name="pattern"></a>Muster

Formatiert
- Drei Ziffern
- Ein Punkt 
- Drei Ziffern
- Ein Punkt 
- Drei Ziffern
- Ein Bindestrich 
- Zwei Ziffern, die Prüfziffern sind

Unformatiert
- 11 Ziffern, wobei die letzten beiden Ziffern Prüfziffern sind

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_brazil_cpf wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_cpf sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identifizierung
- Registrierung
- Umsatz
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 
   
## <a name="brazil-legal-entity-number-cnpj"></a>Brazil legal Entity Number (CNPJ)

### <a name="format"></a>Format

14 Ziffern, die eine Registrierungsnummer, eine Zweignummer und Prüfnziffern sowie Trennzeichen umfassen

### <a name="pattern"></a>Muster
14 Ziffern plus Trennzeichen:
- Zwei Ziffern 
- Ein Punkt  
- Drei Ziffern 
- Ein Punkt  
- Drei Ziffern (diese ersten acht Ziffern sind die Registrierungsnummer)  
- Ein Schrägstrich  
- Vierstellige Zweignummer  
- Ein Bindestrich 
- Zwei Ziffern, die Prüfziffern sind

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_brazil_cnpj wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_cnpj sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="brazil-national-identification-card-rg"></a>Brasilien National Identification Card (RG)

### <a name="format"></a>Format

Registro Geral (altes Format): neun Ziffern

Registro de Identidade (RIC) (neues Format): 11 Ziffern

### <a name="pattern"></a>Muster

Registro Geral (altes Format):
- Zwei Ziffern 
- Ein Punkt  
- Drei Ziffern 
- Ein Punkt  
- Drei Ziffern 
- Ein Bindestrich  
- Eine Ziffer als Prüfziffer

Registro de Identidade (RIC) (neues Format):
- 10 Ziffern 
- Ein Bindestrich  
- Eine Ziffer als Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_brazil_rg wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_brazil_rg sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden) 
- RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden) 


## <a name="bulgaria-drivers-license-number"></a>Bulgarische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_bulgaria_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_bulgaria_eu_driver ' s_license_number**
- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка

## <a name="bulgaria-national-identification-number"></a>Bulgarische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
- Zwei Ziffern, die der Geburts Reihenfolge entsprechen
- Eine Ziffer, die dem Geschlecht entspricht: eine gerade Ziffer für "männlich" und eine ungerade Ziffer für "weiblich".
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_bulgaria_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_bulgaria_national_number` wurde gefunden. 

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_bulgaria_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

- BNN #
- BNN
- BUCN #
- BUCN
- edinen grazhdanski Nomen
- EGN #
- EGN
- identification number

- 
national id
- nationale Nummer
- nationalnumber #
- nationalnumber
- persönliche ID
- persönliches Nein
- persönliche Nummer
- personalidnumber #
- social security number

- SSN #
- SSN
- Uniform Civil ID
- Uniform Civil Nein
- einheitliche Zivil Telefonnummer
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- eindeutige Staats Bürgerschafts Nummer
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ-ID
- униформ-граждански-ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #

## <a name="bulgaria-passport-number"></a>Bulgarische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_bulgaria_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_bulgaria_eu_passport_number` wurde gefunden. 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter

**Keywords_bulgaria_eu_passport_number**
- passport number
- Bulgarische Passnummer
- Passport-Nummer
- номер на паспорта

## <a name="bulgaria-tax-identification-number"></a>Steueridentifikationsnummer (Bulgarien)
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_bulgaria_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_bulgaria_eu_tax_file_number` wurde gefunden. 

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_bulgaria_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 

```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number
- BNN #
- BNN
- BUCN #
- BUCN
- edinen grazhdanski Nomen
- EGN #
- EGN
- identification number

- 
national id
- nationale Nummer
- nationalnumber #
- nationalnumber
- persönliche ID
- persönliches Nein
- persönliche Nummer
- personalidnumber #
- social security number

- SSN #
- SSN
- Uniform Civil ID
- Uniform Civil Nein
- einheitliche Zivil Telefonnummer
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- eindeutige Staats Bürgerschafts Nummer
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ-ID
- униформ-граждански-ID
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="canada-bank-account-number"></a>Kanada Bank Kontonummer

### <a name="format"></a>Format

Sieben oder zwölf Ziffern

### <a name="pattern"></a>Muster

Eine kanadische Kontonummer umfasst sieben oder zwölf Ziffern.

Eine kanadische Bankkontonummer setzt sich wie folgt zusammen:
- Fünf Ziffern 
- Ein Bindestrich 
- Drei Ziffern oder
- Eine 0 (null)  
- Acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_canada_bank_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_canada_bank_account_number wurde gefunden.
- Der reguläre Ausdruck Regex_canada_bank_account_transit_number findet Inhalte, die dem Muster entsprechen.

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

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
- Driver ' License
- Driver ' Licenses
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
- Personalausweis
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- Identifizierung 
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
- Driver ' License # 
- Driver ' Licenses # 
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
- ID # 
- IDs # 
- idcard card# 
- idcard cards# 
- Personalausweis # 
- identification card# 
- identification cards# 
- Identifizierung # 
   
## <a name="canada-health-service-number"></a>Canada Health Service-Nummer

### <a name="format"></a>Format

10 Ziffern

### <a name="pattern"></a>Muster

10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- Psychiater
- workers compensation
- Disability
      
## <a name="canada-passport-number"></a>Kanadische Passnummer

### <a name="format"></a>Format

Zwei Großbuchstaben, gefolgt von sechs Ziffern

### <a name="pattern"></a>Muster

Zwei Großbuchstaben, gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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
- Passport-Nr
- Passportno
- passportnumber
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
   
## <a name="canada-personal-health-identification-number-phin"></a>Kanadische Personal Health Identification Number (Phin)

### <a name="format"></a>Format

Neun Ziffern

### <a name="pattern"></a>Muster

Neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_canada_phin findet Inhalte, die mit dem Muster übereinstimmen.
Mindestens zwei Schlüsselwörter aus Keyword_canada_phin oder Keyword_canada_provinces werden gefunden..

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="canada-social-insurance-number"></a>Kanadische Sozialversicherungsnummer

### <a name="format"></a>Format

Neun Ziffern mit optionalen Bindestrichen oder Leerzeichen

### <a name="pattern"></a>Muster

Formatiert
- Drei Ziffern 
- Ein Bindestrich oder Leerzeichen 
- Drei Ziffern 
- Ein Bindestrich oder Leerzeichen 
- Drei Ziffern

Unformatiert: neun Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_canadian_sin findet Inhalte, die dem Muster entsprechen.
- Mindestens zwei dieser eine beliebige Kombination der folgenden Aktionen aus:
    - Ein Schlüsselwort aus Keyword_sin wurde gefunden.
    - Ein Schlüsselwort aus Keyword_sin_collaborative wurde gefunden.
    - Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- Todsünden 
- SSN 
- Sozialversicherungsnummern 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- Sin # 
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
   
## <a name="chile-identity-card-number"></a>Chile Personalausweisnummer

### <a name="format"></a>Format

7-8 Ziffern Plus Trennzeichen für eine Prüfziffer oder einen Buchstaben

### <a name="pattern"></a>Muster

7-8 Ziffern plus Trennzeichen:
- 1-2 Ziffern  
- Ein Punkt  
- Drei Ziffern 
- Ein Punkt  
- Drei Ziffern 
- Ein Bindestrich 
- Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung nicht unterschieden), die bzw. der eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_chile_id_card wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_chile_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- National Identification Number 
- Identity card 
- ID 
- Identifizierung 
- Rol Único Nacional 
- Ausführen 
- Rol Único Tributario 
- Rut 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 
   
## <a name="china-resident-identity-card-prc-number"></a>China Resident Identity Card (PRC)-Nummer

### <a name="format"></a>Format

18 Ziffern

### <a name="pattern"></a>Muster

18 Ziffern:
- Sechs Ziffern, die einen Adresscode angeben  
- Acht Ziffern im Fomat JJJJMMTT, wobei es sich um das Geburtsdatum handelt  
- Drei Ziffern, die ein Reihenfolgencode sind  
- Eine Ziffer als Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_china_resident_id wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_china_resident_id sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

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

14 bis 16 Ziffern, die formatiert oder unformatiert (dddddddddddddddd) sein können und die den Luhn-Test bestehen müssen.

### <a name="pattern"></a>Muster

Sehr komplexe und robuste Muster, die Karten aller wichtigen Marken weltweit, einschließlich Visa, MasterCard, Discover-Karte, JCB, American Express, Geschenkgutscheine und Restaurantkarten erkennen.

### <a name="checksum"></a>Prüfsumme

Ja, die Luhn-Prüfsumme

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_credit_card findet Inhalte, die dem Muster entsprechen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_cc_verification wurde gefunden.
    - Ein Schlüsselwort aus Keyword_cc_name wurde gefunden.
    - Die Funktion Func_expiration_date findet ein Datum im richtigen Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- CVN
- cid
- CVC2
- CVV2
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
- COD. Sicurezza
- cod sicurezza
- n autorizzazione
- Código
- codigo
- COD. SEG
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. Segurança
- COD. Seguranca COD. Segurança
- cód. seguranca
- cód segurança
- COD Seguranca COD Segurança
- cód seguranca
- número de verificação
- numero de verificacao
- Ablauf
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
- VTO
- data de expiração
- data de expiracao
- data em que expira
- validade
- Valor
- vencimento
- Venc 

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- AmericanExpress
- Visa
- MasterCard
- master card
- Verwaltungskonsole 
- MasterCards gesichert
- master cards
- diner's Club
- diners club
- DinersClub
- discover card
- discovercard
- discover cards
- JCB
- japanese card bureau
- carte blanche
- CarteBlanche
- credit card
- CC #
- cc #:
- expiration date
- exp date
- expiry date
- Datum d'expiration
- date d'exp
- date expiration
- bank card
- Bankcard
- card number
- card num
- cardNumber
- cardnumbers
- card numbers
- CreditCard
- credit cards
- creditCards
- Angaben
- card holder
- Inhaber
- card holders
- Inhaber
- check card
- checkcard
- check cards
- checkcards
- debit card
- Debitkarte
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
- Kreditkarten-Nummer
- carta di credito
- carta credito
- Carta
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
- nº. do cartão
- no do cartão
- no do cartao
- Nein. do cartão
- Nein. do cartao 

## <a name="croatia-drivers-license-number"></a>Kroatische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_croatia_eu_driver's_license_number` wurde gefunden. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_croatia_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- vozačka dozvola

## <a name="croatia-identity-card-number"></a>Kroatische Personalausweisnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.


### <a name="format"></a>Format

Neun Ziffern

### <a name="pattern"></a>Muster

Neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_croatia_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_croatia_id_card wurde gefunden.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski Broj građana
- Bürgermeister Nummer
- Nacionalni identifikacijski Broj
- nationale Identifikationsnummer
- OIB #
- OIB
- osobna iskaznica
- Osobni-ID
- Osobni identifikacijski Broj
- persönliche Identifikationsnummer
- porezni Broj
- porezni identifikacijski Broj
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="croatia-passport-number"></a>Kroatische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_croatia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_croatia_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter

**Keywords_croatia_eu_passport_number**

- passport number
- Kroatische Passnummer
- Passport-Nummer
- Broj putovnice

   
## <a name="croatia-personal-identification-oib-number"></a>Kroatische persönliche Identifikationsnummer (OIB)

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- 10 Ziffern 
- Letzte Ziffer ist eine Prüfziffer für den Zweck des internationalen Datenaustauschs, die Buchstaben HR werden vor den elf Ziffern hinzugefügt.

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_croatia_oib_number wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_croatia_oib_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- Personal Identification Number
- Osobni identifikacijski broj 
- OIB 

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Kroatische Sozialversicherungsnummer oder gleichwertige Kennzeichnung
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 11 Ziffern:
  
- Zehn Ziffern
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_croatia_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_croatia_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_croatia_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- persönliche Identifikationsnummer
- Bürgermeister Nummer
- national identification number
- social security number
- nationalnumber #
- SSN #
- SSN
- nationalnumber
- BNN #
- BNN
- persönliche ID-Nummer
- personalidnumber #
- OIB
- Osobni identifikacijski Broj
   
## <a name="croatia-tax-identification-number"></a>Kroatische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im Steuer Identificaiton Nummer vertraulichen Informationstyp der EU verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- Zehn Ziffern, nach dem Zufallsprinzip ausgewählt
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_croatia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_croatia_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_croatia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

- majstorski Broj građana
- Bürgermeister Nummer
- Nacionalni identifikacijski Broj
- nationale Identifikationsnummer
- OIB #
- OIB
- osobna iskaznica
- Osobni-ID
- Osobni identifikacijski Broj
- persönliche Identifikationsnummer
- porezni Broj
- porezni identifikacijski Broj
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="cyprus-drivers-license-number"></a>Zypern-Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

12 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

12 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_cyprus_eu_driver's_license_number` wurde gefunden.

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_cyprus_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- άδεια οδήγησης

## <a name="cyprus-national-identification-number"></a>Zyprische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Zehn Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_cyprus_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_cyprus_eu_national_id_card` wurde gefunden. 
    
```xml 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- ID-Kartennummer
- Personalausweisnummer
- KİMLİK karti
- nationale Identifikationsnummer
- persönliche ID-Nummer
- ταυτοτητασ

## <a name="cyprus-passport-number"></a>Zypern-Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Ein Buchstabe, gefolgt von 6-8 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe, gefolgt von sechs bis acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_cyprus_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus `Keywords_cyprus_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_cyprus_eu_passport_number**

- passport number
- Zypern-Passnummer
- Passport-Nummer
- αριθμό διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>Zyprische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern und ein Buchstabe im angegebenen Muster
  
### <a name="pattern"></a>Muster

Acht Ziffern und ein Buchstabe:
  
-  A "0" 
- Sieben Ziffern 
- Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_cyprus_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_cyprus_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_cyprus_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- Steuer Identifikationscode
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- TIC #
- TIC
- Tin-ID
- Tin Nein
- Zinn #
- Vergi KİMLİK Kodu
- Vergi KİMLİK numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού
- Steuernummer

## <a name="czech-drivers-license-number"></a>Tschechische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Acht Buchstaben und Ziffern:
  
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)
- Ein Leerzeichen (optional) 
- Sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_czech_republic_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_czech_republic_eu_driver's_license_number` wurde gefunden. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_czech_republic_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- řidičský prúkaz

## <a name="czech-passport-number"></a>Tschechische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_czech_republic_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_czech_republic_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_czech_republic_eu_passport_number**

- passport number
- Tschechische Passnummer
- Passport-Nummer
- Cestovní Pas
- Pas

## <a name="czech-personal-identity-number"></a>Tschechische Personalausweisnummer
Diese vertrauliche Informationen Typ Entität ist in der EU-National Identification Number Bundle enthalten und steht als eigenständige vertrauliche Informationen Typ Entität zur Verfügung.

### <a name="format"></a>Format

Neun Ziffern mit optionalem Schrägstrich (altes Format), 10 Ziffern mit optionalem Schrägstrich (neues Format)

### <a name="pattern"></a>Muster

Neun Ziffern (altes Format):
- Neun Ziffern

ODER

- Sechs Ziffern, die das Geburtsdatum darstellen.
- Ein Schrägstrich 
- Drei Ziffern

10 Ziffern (neues Format):
- 10 Ziffern

ODER

- Sechs Ziffern, die das Geburtsdatum darstellen.
- Ein Schrägstrich  
- Vier Ziffern, wobei die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_czech_id_card findet Inhalte, die mit dem Muster übereinstimmen.
Ein Schlüsselwort aus Keyword_czech_id_card wurde gefunden.
Die Prüfsumme stimmt.

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter

- Tschechische Personalausweisnummer
- Rodné číslo



## <a name="czech-social-security-number-or-equivalent-identification"></a>Tschechische Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

Zehn Ziffern und ein Backslash im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zehn Ziffern und ein Backslash:
  
- Sechs Ziffern, die dem Geburtsdatum (JJMMTT) entsprechen: 
    
- Einen umgekehrten Schrägstrich
    
- Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am selben Datum geboren wurden
    
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_czech_republic_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_czech_republic_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_czech_republic_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- Geburtsnummer
- national identification number
- persönliche Identifikationsnummer
- social security number
- nationalnumber #
- SSN #
- SSN
- nationale Nummer
- persönliche ID-Nummer
- personalidnumber #
- rč
- rodné číslo
- rodne cislo

## <a name="czech-tax-identification-number"></a>Tschechische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Neun oder zehn Ziffern mit einem optionalen Backslash
  
### <a name="pattern"></a>Muster

Neun oder zehn Ziffern mit einem optionalen backslashl:
  
- Sechs Ziffern 
- Ein Backslash (optional)
- Drei oder vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_czech_republic_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_czech_republic_eu_tax_file_number` wurde gefunden. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

- Tschechische Republik ID
- czechidno #
- daňové číslo
- identifikační číslo
- Identität Nein
- Identitätsnummer
- identityno #
- identityno
- Versicherungsnummer
- nationale Identifikationsnummer
- nationale Nummer
- osobní číslo
- persönliche ID-Nummer
- persönliche Nummer
- PID #
- pid
- pojištění číslo
- rodné číslo
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- eindeutige Identifikationsnummer
- Steuernummer

## <a name="denmark-drivers-license-number"></a>Dänische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_denmark_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_denmark_eu_driver ' s_license_number**

- | DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Dänische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_denmark_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_denmark_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_denmark_eu_passport_number**

- passport number
- dänische Passnummer
- Passport-Nummer
- Pas
- pasnummer

## <a name="denmark-personal-identification-number"></a>Dänische persönliche Identifikationsnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

10 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

10 Ziffern:
- Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben  
- Ein Bindestrich  
- Vier Ziffern, bei denen die letzte Ziffer eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: der reguläre Ausdruck Regex_denmark_id findet Inhalte, die mit dem Muster übereinstimmen.
Ein Schlüsselwort aus Keyword_denmark_id wurde gefunden.
Die Prüfsumme stimmt.

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- Centrale personregister
- civilt registreringssystem
- CPR
- CPR #
- Gesundheitskarte Nummer
- gesundheitsversicherungkarte Nummer
- Integritäts Karte
- Krankenversicherungskarten Nummer
- Krankenversicherungsnummer
- identification number

- identifikationsnummer
- identifikationsnummer #
- Identitätsnummer
- krankenkassennummer
- National-Nr. #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- Skat-ID
- Skate Kode
- Skate Nummer
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- Steuercode
- Krankenversicherungskarte für Reisen
- uniqueidentityno #
- Steuernummer
- Steuerregistrierungsnummer
- tax id

- Steueridentifikationsnummer
- per Taxi #
- taxnumber #
- Steuernummer
- taxno #
- taxnumber
- Steueridentifikationsnummer
- Zinn #
- taxidno #
- taxidnumber #
- Steuernummer #
- Tin-ID
- Tin Nein

## <a name="denmark-social-security-number-or-equivalent-identification"></a>Dänemark Sozialversicherungsnummer oder gleichwertige Kennzeichnung
Diese vertrauliche Informationstyp Entität steht nur für die Sozialversicherungsnummer der EU oder für einen entsprechenden ID-vertraulichen Informationstyp zur Verfügung.

### <a name="format"></a>Format

Zehn Ziffern und ein Bindestrich im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zehn Ziffern und ein Bindestrich:
  
- Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ) 
- Ein Bindestrich 
- Vier Ziffern, die einer Sequenznummer entsprechen
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_denmark_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_denmark_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_denmark_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- persönliche Identifikationsnummer
- national identification number
- social security number
- nationalnumber #
- SSN #
- SSN
- nationale Nummer
- persönliche ID-Nummer
- personalidnumber #
- CPR-Nummer
- personnummer

## <a name="denmark-tax-identification-number"></a>Dänische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Zehn Ziffern mit einem Bindestrich
  
### <a name="pattern"></a>Muster

Zehn Ziffern mit einem Bindestrich:
  
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)
- Ein Bindestrich 
- Vier Ziffern, die einer Sequenznummer entsprechen, wobei die erste Ziffer dem Jahrhundert der Geburt entspricht und die letzte Ziffer dem Geschlecht der Person entspricht (ungerade für männliche und sogar für weiblich)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_denmark_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_denmark_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_denmark_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

- Centrale personregister
- civilt registreringssystem
- CPR
- CPR #
- Gesundheitskarte Nummer
- gesundheitsversicherungkarte Nummer
- Integritäts Karte
- Krankenversicherungskarten Nummer
- Krankenversicherungsnummer
- identification number

- identifikationsnummer
- identifikationsnummer #
- Identitätsnummer
- krankenkassennummer
- National-Nr. #
- personalidentityno #
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- Skat-ID
- Skate Kode
- Skate Nummer
- skattenummer
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- Steuercode
- Krankenversicherungskarte für Reisen
- uniqueidentityno #
- Steuernummer
- Steuerregistrierungsnummer
- tax id

- Steueridentifikationsnummer
- per Taxi #
- taxnumber #
- Steuernummer
- taxno #
- taxnumber
- Steueridentifikationsnummer
- Zinn #
- taxidno #
- taxidnumber #
- Steuernummer #
- Tin-ID
- Tin Nein


## <a name="drug-enforcement-agency-dea-number"></a>Drug Enforcement Agency (DEA)-Nummer

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Einen Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) aus der folgenden Gruppe möglicher Buchstaben: abcdefghjklmnprstux, was einem Registrantencode entspricht 
- Ein Buchstabe (bei dem die Groß-und Kleinschreibung nicht beachtet wird), der dem ersten Buchstaben des Nachnamens des Registrants entspricht 
- Sieben Ziffern, von denen die letzte die Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_dea_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Keine

## <a name="estonia-drivers-license-number"></a>Estnische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Zwei Buchstaben und sechs Ziffern:
  
-  Die Buchstaben "et" (unterscheidet nicht zwischen Groß-/Kleinschreibung) 
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_estonia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_estonia_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_estonia_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- permis de conduire

## <a name="estonia-national-identification-number"></a>Estnische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
- Eine Ziffer, die Geschlecht und Jahrhundert der Geburt entspricht (ungerade Zahl männlich, gerade Zahl weiblich; 1-2:19. Jahrhundert; 3-4:20th Century; 5-6:21st Century)
    
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)
- Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_estonia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_estonia_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_estonia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- ID-Kaart
- IK
- isikukood #
- isikukood
- maksu-ID
- maksukohustuslase identifitseerimisnumber
- maksunumber
- nationale Identifikationsnummer
- nationale Nummer
- persönlicher Code
- persönliche ID-Nummer
- persönlicher Identifikationscode
- persönliche Identifikationsnummer
- personalidnumber #
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="estonia-passport-number"></a>Estland-Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe, gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_estonia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_estonia_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_estonia_eu_passport_number**

- passport number
- Estnische Passnummer
- Passport-Nummer
- Eesti kodaniku Pass

## <a name="estonia-tax-identification-number"></a>Estland Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
-  Eine Ziffer, die dem Geschlecht und dem Jahrhundert der Geburt entspricht, wobei eine ungerade Zahl männlich ist und die gerade Zahl weiblich wie folgt angibt: 1, 2 für das 19. Jahrhundert; 3,4 für das 20. Jahrhundert; und 5, 6 für das 21. Jahrhundert 
    
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)
- Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_estonia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_estonia_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_estonia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

- ID-Kaart
- IK
- isikukood #
- isikukood
- maksu-ID
- maksukohustuslase identifitseerimisnumber
- maksunumber
- nationale Identifikationsnummer
- nationale Nummer
- persönlicher Code
- persönliche ID-Nummer
- persönlicher Identifikationscode
- persönliche Identifikationsnummer
- personalidnumber #
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="eu-debit-card-number"></a>EU-Debitkartennummern

### <a name="format"></a>Format

16 Ziffern

### <a name="pattern"></a>Muster

Sehr komplexes und robustes Muster

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- CC # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- AmericanExpress 
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
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- Inhaber 
- Inhaber 
- cardNumber 
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
- CarteBlanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- Angaben 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- Cirrus 
- Cirrus-EDC-Maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- CreditCard 
- creditCards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- Debitkarte 
- debitcards 
- debito automatico 
- diners club 
- DinersClub 
- ermitteln 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- EDC 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- JCB 
- Kaart 
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
- Kreditkarten-Nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- Maestro 
- master card 
- master cards 
- MasterCard 
- MasterCards gesichert 
- Verwaltungskonsole 
- mister cash 
- n carta 
- Carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Nein. de tarjeta 
- Nein. do cartao 
- Nein. do cartão 
- nr carta 
- Nr. Carta 
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
- Schalter 
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
- Scheda 
- v pay 
- v-Pay 
- Visa 
- visa plus 
- visa electron 
- Visto 
- Visum 
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
- COD. SEG 
- COD. seguranca 
- COD. Segurança 
- COD. Sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- Kryptogramm 
- cryptogramme 
- CV2 
- CVC 
- CVC2 
- CVN 
- CVV 
- CVV2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. Segurança 
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
- Nein. Dell ' edizione 
- Nein. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- Scheda 
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
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- Ablauf 
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
- ablaufen 
- abläuft 
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
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- VTO 
- válido hasta 

## <a name="eu-drivers-license-number"></a>EU-Führerscheinnummer
Hierbei handelt es sich um die Entitäten im vertraulichen Informationstyp des EU-Führerscheins Nummer.

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
- [Britannien](#uk-drivers-license-number)

## <a name="eu-national-identification-number"></a>EU-nationale Identifikationsnummer
Hierbei handelt es sich um die Entitäten im vertraulichen Informationstyp "EU-nationale Identifikationsnummer".

- [Österreich](#austria-national-identification-number)
- [Belgien](#belgium-national-number)
- [Bulgarien](#bulgaria-national-identification-number)
- [Kroatien](#croatia-identity-card-number)
- [Zypern](#cyprus-national-identification-number)
- [Tschechisch](#czech-personal-identity-number)
- [Dänemark](#denmark-personal-identification-number)
- [Estland](#estonia-national-identification-number)
- [Finnland](#finland-national-identification-number)
- [Frankreich](#france-national-identification-card-cni)
- [Deutschland](#germany-identity-card-number)
- [Griechenland](#greece-national-id-card)
- [Ungarn](#hungary-national-identification-number)
- [Irland](#ireland-national-identification-number)
- [Italien](#italy-national-identification-number)
- [Lettland](#latvia-national-identification-number)
- [Litauen](#lithuania-national-identification-number)
- [Luxemburg](#luxemburg-national-identification-number)
- [Malta](#malta-national-identification-number)
- [Niederlande](#netherlands-national-identification-number)
- [Polen](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Rumänien](#romania-national-identification-number)
- [Slowakei](#slovakia-national-identification-number)
- [Slowenien](#slovenia-national-identification-number)
- [Spanien](#spain-national-identification-number)
- [Britannien](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU-Passport-Nummer 
Dies sind die Entitäten in der EU-Passport-Nummer vertrauliche Informationen typeThese sind die Entitäten im EU-Passport-Nummern Paket.

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
- [Britannien](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU-Sozialversicherungsnummer oder gleichwertige Identifikation
Dabei handelt es sich um die Entitäten, die sich in der EU-Sozialversicherungsnummer oder einem äquivalenten Identifikations sensiblen Informationstyp befinden.

- [Österreich](#austria-social-security-number-or-equivalent-identification)
- [Belgien](#belgium-social-security-number-or-equivalent-identification)
- [Kroatien](#croatia-social-security-number-or-equivalent-identification)
- [Tschechisch](#czech-social-security-number-or-equivalent-identification)
- [Dänemark](#denmark-social-security-number-or-equivalent-identification)
- [Finnland](#finland-social-security-number-or-equivalent-identification)
- [Frankreich](#france-social-security-number-insee-or-equivalent-identification)
- [Deutschland](#germany-identity-card-number)
- [Griechenland](#greece-national-id-card)
- [Ungarn](#hungary-social-security-number-or-equivalent-identification)
- [Portugal](#portugal-citizen-card-number)
- [Spanien](#spain-social-security-number-ssn)
- [Schweden](#sweden-social-security-number-or-equivalent-identification)

## <a name="eu-tax-identification-number"></a>EU-Steueridentifikationsnummer

iese-Entitäten befinden sich im vertraulichen Informationstyp "EU-Steueridentifikationsnummer".

- [Österreich](#austria-tax-identification-number)
- [Belgien](#belgium-tax-identification-number)
- [Bulgarien](#bulgaria-tax-identification-number)
- [Kroatien](#croatia-tax-identification-number)
- [Zypern](#cyprus-tax-identification-number)
- [Tschechisch](#czech-tax-identification-number)
- [Dänemark](#denmark-tax-identification-number)
- [Estland](#estonia-tax-identification-number)
- [Finnland](#finland-tax-identification-number)
- [Frankreich](#france-tax-identification-number)
- [Deutschland](#germany-tax-identification-number)
- [Griechenland](#greece-tax-identification-number)
- [Ungarn](#hungary-tax-identification-number)
- [Irland](#ireland-tax-identification-number)
- [Italien](#italy-tax-identification-number)
- [Lettland](#latvia-tax-identification-number)
- [Litauen](#lithuania-tax-identification-number)
- [Luxemburg](#luxemburg-tax-identification-number)
- [Malta](#malta-tax-identification-number)
- [Niederlande](#netherlands-tax-identification-number)
- [Polen](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Rumänien](#romania-tax-identification-number)
- [Slowakei](#slovakia-tax-identification-number)
- [Slowenien](#slovenia-tax-identification-number)
- [Spanien](#spain-tax-identification-number)
- [Schweden](#sweden-tax-identification-number)
- [Britannien](#uk-tax-identification-number)


## <a name="finland-drivers-license-number"></a>Finnland-Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

10 Ziffern, die einen Bindestrich enthalten
  
### <a name="pattern"></a>Muster

10 Ziffern mit einem Bindestrich:
  
-  Sechs Ziffern 
- Ein Bindestrich
-  Vier Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_finland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_finland_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_finland_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- ajokortti

## <a name="finland-national-identification-number"></a>Finnische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

Sechs Ziffern plus ein Zeichen, das ein Jahrhundert angibt, plus drei Ziffern plus einer Prüfziffer

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Sechs Ziffern im Format TTMMJJ, die ein Geburtsdatum darstellen 
- Jahrhundertkennzeichnung (entweder „-“, „+“ oder „a“) 
- Dreistellige persönliche Identifikationsnummer 
- Eine Ziffer oder ein Buchstabe (Groß-/Kleinschreibung irrelevant), die bzw. der eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_finnish_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_finnish_national_id wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- Hetu
- ID Nein
- ID-Nummer
- identification number

- identiteetti numero
- Identitätsnummer
- idnumber
- der Kok henkilötunnus
- kansallisen henkilökortin
- nationale ID-Karte
- nationale ID-Nr.
- persönliche ID
- persönlicher Identitätscode
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus

## <a name="finland-passport-number"></a>Finnland-Passport-Nummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer verfügbar und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format
Kombination aus neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster
Kombination von neun Buchstaben und Ziffern: zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) sieben Ziffern

### <a name="checksum"></a>Prüfsumme
Nein

### <a name="definition"></a>Definition
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_finland_passport_number findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_finland_passport_number wurde gefunden.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter
- Keyword_finland_passport_number
- Pass
- Passi

## <a name="finland-social-security-number-or-equivalent-identification"></a>Finnland Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

Eine Kombination aus 11 Zeichen im angegebenen Format
  
### <a name="pattern"></a>Muster

Eine Kombination aus 11 Zeichen im angegebenen Format:
  
-  Sechs Ziffern 
- Eine Instanz einer der folgenden:
  - Plus-Symbol
  - Minus Zeichen
  - Der Buchstabe "A" (Groß-/Kleinschreibung wird nicht berücksichtigt)
- Drei Ziffern
- Ein Buchstabe oder eine Ziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_finland_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_finland_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_finland_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- persönliche ID
- Identitätsnummer
- Finnische Nationale ID-Nummer
- personalidnumber #
- national identification number
- ID-Nummer
- nationale ID-Nr.
- nationale ID-Nummer
- ID Nein
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- Suomen der Kok henkilötunnus
- henkilötunnusnumero #
- kansallisen tunnistenumero
- tunnusnumero
- der Kok tunnus numero
- Hetu

## <a name="finland-tax-identification-number"></a>Finnland Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen
  
### <a name="pattern"></a>Muster

Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen:
  
- Sechs Ziffern
- Eine der folgenden Optionen: ein Pluszeichen, ein Minuszeichen oder der Buchstabe "a" (Groß-/Kleinschreibung nicht beachtet), wobei das Pluszeichen zwischen 1800-1899 geboren wird, das Minuszeichen zwischen 1900-1999 und "a" geboren ist 2000 und nach
- Drei Ziffern
- Ein Buchstabe oder eine Zahl
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_finland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_finland_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_finland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- Hetu
- ID Nein
- ID-Nummer
- identification number

- identiteetti numero
- Identitätsnummer
- idnumber
- der Kok henkilötunnus
- kansallisen henkilökortin
- nationale ID-Karte
- nationale ID-Nr.
- persönliche ID
- persönlicher Identitätscode
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- Suomen der Kok henkilötunnus
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="france-drivers-license-number"></a>Frankreich Führerscheinnummer
Diese vertrauliche Informationstyp Entität ist im Sicherheits Informationstyp des EU-Führerscheins Nummer verfügbar und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern mit Validierung, um ähnliche Muster ( z. B. französische Telefonnummern) auszuschließen

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_french_drivers_license findet Inhalte, die dem Muster entsprechen.
- Mindestens eine der folgenden Bedingungen trifft zu:
- Ein Schlüsselwort aus Keyword_french_drivers_license wurde gefunden.
- Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- Führerschein
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers

## <a name="france-national-identification-card-cni"></a>Nationale Identitätskarte von Frankreich (CNI)
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_france_cni findet Inhalte, die dem Muster entsprechen.

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

- card number

- Carte nationale d ' identité
- Carte nationale d'idenite No
- CNI #
- CNI
- Compte Bancaire
- nationale Identifikationsnummer
- nationale Identität
- nationalidno #
- Numéro assurance maladie
- Numéro de carte Vitale

   
## <a name="france-passport-number"></a>Frankreich-Passnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer verfügbar und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

Neun Ziffern und Buchstaben

### <a name="pattern"></a>Muster

Neun Ziffern und Buchstaben:
- Zwei Ziffern 
- Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) 
- Fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport#
- Pass #
- Passport-Nr
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport#
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Frankreich Sozialversicherungsnummer (INSEE) oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist in der Sozialversicherungsnummer und dem äquivalenten ID-Typ für vertrauliche Informationen enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

15 Ziffern

### <a name="pattern"></a>Muster

Muss einem von zwei Mustern entsprechen:
- 13 Ziffern, gefolgt von einem Leerzeichen, gefolgt von zwei Ziffern<br/>
oder
- 15 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_fr_insee wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_french_insee oder Func_fr_insee findet Inhalte, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- INSEE
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- Nein. d ' identité
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

## <a name="france-tax-identification-number"></a>Frankreich Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

13 Ziffern für einzelne Personen und neun Ziffern für Entitäten
  
### <a name="pattern"></a>Muster

13 Ziffern für einzelne Personen:
  
- Eine Ziffer, die 0, 1, 2 oder 3 sein muss
- 12 Ziffern
    
Neun Ziffern für Entitäten
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_france_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_france_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_france_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- Numéro d'identification Fiscale
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="germany-drivers-license-number"></a>Deutschland Führerscheinnummer
Diese vertrauliche Informationen Typ Entität ist in der EU-Führerscheinnummer vertraulichen Informationstyp enthalten und ist als eigenständige vertrauliche Informationen Typ Entität zur Verfügung.

### <a name="format"></a>Format

Kombination von 11 Ziffern und Buchstaben

### <a name="pattern"></a>Muster

11 Zahlen und Buchstaben (ohne Beachtung der Groß-/Kleinschreibung):
- Eine Ziffer oder ein Buchstabe 
- Zwei Ziffern 
- Sechs Ziffern oder Buchstaben 
- Eine Ziffer 
- Eine Ziffer oder ein Buchstabe

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_german_drivers_license findet Inhalte, die dem Muster entsprechen.
- Mindestens eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_german_drivers_license_number wurde gefunden.
    - Ein Schlüsselwort aus Keyword_german_drivers_license_collaborative wurde gefunden.
    - Ein Schlüsselwort aus Keyword_german_drivers_license wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Germany Driver's License Number -->
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

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

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

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

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- Ausstellende Behöde
- Ausstellende Behorde
- ausstellende behoerde

## <a name="germany-identity-card-number"></a>Deutsche Personalausweisnummer
- Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.
- Diese vertrauliche Informationstyp Entität ist in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-Typ für vertrauliche Informationen enthalten.

### <a name="format"></a>Format

Seit dem 1. November 2010: neun Buchstaben und Ziffern

Vom 1. April 1987 bis 31. Oktober 2010:10 Ziffern

### <a name="pattern"></a>Muster

Seit 1. November 2010:
- Ein Buchstaben (Groß-/Kleinschreibung irrelevant)  
- Acht Ziffern

Vom 1. April 1987 bis 31. Oktober 2010:
- 10 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_germany_id_card findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_germany_id_card wurde gefunden.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- Ausweis
- GPID
- Identifizierung
- Identifikation
- identifizierungsnummer
- Personalausweis
- Identitätsnummer
- ID-Nummer
- persönliche ID
- Personalausweis
- persönliche-ID-Nummer
- persönliche identifikationsnummer
- persönliche-ID-Nummer


## <a name="germany-passport-number"></a>Deutschland Passport-Nummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

10 Ziffern oder Buchstaben

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:
- Das erste Zeichen ist eine Ziffer oder ein Buchstabe aus dieser Gruppe (C, F, G, H, J, K) 
- Drei Ziffern 
- Fünf Ziffern oder Buchstaben aus dieser Gruppe (C -H, J-N, P, R, T, V-Z) 
- Eine Ziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_german_passport findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_german_passport_data findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus einer der fünf Schlüsselwortlisten wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Germany Passport Number -->
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- Reisepass
- reisepasse
- reisepassnummer
- Pass
- Pässe

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

No-Reisepass Nr-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-Nr

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit. t

## <a name="germany-tax-identification-number"></a>Deutschland Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
-  Zehn Ziffern 
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_germany_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_germany_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_germany_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- Ingo-ID
- steueridentifikationsnummer
- Steuernummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- Zinn #
- Zinn
- zinnnummer

## <a name="greece-drivers-license-number"></a>Griechenland Führerscheinnummer
Diese vertrauliche Informationen Typ Entität ist in der EU-Führerscheinnummer vertraulichen Informationstyp enthalten und ist als eigenständige vertrauliche Informationen Typ Entität zur Verfügung.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_greece_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_greece_eu_driver ' s_license_number**

- dlL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>Nationale griechische ID-Karte
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

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

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_greece_id_card findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_greece_id_card wurde gefunden.

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- griechische ID
- griechische nationale ID
- griechische Personalausweis Karte
- griechische Polizei-ID
- Personalausweis
- tautotita
- ταυτότητα
- ταυτότητας

## <a name="greece-passport-number"></a>Griechenland Passport-Nummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_greece_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_greece_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_greece_eu_passport_number**

- passport number
- griechische Passnummer
- Passport-Nummer
- διαβατηριο

## <a name="greece-tax-identification-number"></a>Griechenland Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_greece_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_greece_eu_tax_file_number` wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- AFM #
- AFM
- aφμ | aφμ αριθμός
- aφμ
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- Steuerregistrierungsnummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- Tin-ID
- Tin Nein
- Zinn #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Hong Kong Personalausweisnummer (HKID)

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

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_hong_kong_id_card wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_hong_kong_id_card sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- Hong Kong Identity Card
- HKIDC
- id card
- identity card
- HK-Personalausweis
- Hong Kong-ID
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
   
## <a name="hungary-drivers-license-number"></a>Ungarische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Zwei Buchstaben und sechs Ziffern:
  
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_hungary_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_hungary_eu_driver ' s_license_number**
- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- vezetoi engedely

## <a name="hungary-national-identification-number"></a>Ungarische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern
  
### <a name="pattern"></a>Muster

11 Ziffern:
  
-  Eine Ziffer, die dem Geschlecht entspricht (1-männlich, 2-weiblich, andere Zahlen sind auch für Bürger möglich, die vor 1900 oder Bürgern mit doppelter Staatsbürgerschaft geboren wurden) 
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)
- Drei Ziffern, die einer Seriennummer entsprechen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_hungary_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- ID-Nummer
- identification number

- SZ IG
- SZ.IG.
- SZ. ig.
- személyazonosító igazolvány
- személyi igazolvány

## <a name="hungary-passport-number"></a>Ungarn Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben, gefolgt von sechs oder sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_hungary_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_hungary_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Schlüsselwörter

**Keywords_hungary_eu_passport_number**

- passport number
- ungarische Passnummer
- Passport-Nummer
- útlevél száma

## <a name="hungary-social-security-number-or-equivalent-identification"></a>Ungarn Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_hungary_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- ungarische Sozialversicherungsnummer
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- Taj
- Taj #
- SSN
- SSN #
- Sozialversicherungsnummer
- ÁFA
- közösségi adószám
- Általános forgalmi adó szám
- hozzáadottérték adó
- ÁFA szám
- Magyar ÁFA szám


## <a name="hungary-tax-identification-number"></a>Ungarn Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zehn Ziffern:
  
-  Eine Ziffer, die "8" sein muss 
- Fünf Ziffern, die der Anzahl von Tagen zwischen dem Datum 01/01/1867 und dem Geburtsdatum der einzelnen Personen entsprechen.
- Drei Ziffern, die der durch Zufall generierten Zahl entsprechen, um Personen zu unterscheiden, die am selben Tag geboren wurden
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_hungary_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_hungary_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- Ungarisch Zinn
- hungatiantin #
- Steuerbehörde Nein
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- USt-IdNr.

## <a name="india-permanent-account-number-pan"></a>Indische permanente Kontonummer (Pan)

### <a name="format"></a>Format

10 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

10 Buchstaben oder Ziffern:
- Fünf Buchstaben (Groß-/Kleinschreibung irrelevant)  
- Vier Ziffern 
- Ein Buchstabe, der eine alphabetische Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_india_permanent_account_number findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_india_permanent_account_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- Schwenken 
   
## <a name="india-unique-identification-aadhaar-number"></a>Indische eindeutige Identifikationsnummer (Aadhaar)

### <a name="format"></a>Format

12 Ziffern mit optionalen Leerzeichen oder Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- Vier Ziffern  
- Eine optionales Leerzeichen oder ein Bindestrich  
- Vier Ziffern  
- Eine optionales Leerzeichen oder ein Bindestrich  
- Die letzte Ziffer, die eine Prüfziffer ist

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist 85% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.
Ein Schlüsselwort aus Keyword_india_aadhar wurde gefunden.
Die Prüfsumme stimmt.
Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_india_aadhaar findet Inhalte, die mit dem Muster übereinstimmen.
Die Prüfsumme stimmt.
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
### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Indonesien Personalausweisnummer (KTP)

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

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_indonesia_id_card wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_indonesia_id_card findet Inhalte, die mit dem Muster übereinstimmen.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>International Banking Account Number (IBAN)

### <a name="format"></a>Format

Landesvorwahl (zwei Buchstaben) plus Prüfziffern (zwei Ziffern) plus BBAN-Nummer (bis zu 30 Zeichen)

### <a name="pattern"></a>Muster

Das Muster muss Folgendes enthalten:

- Landesvorwahl mit zwei Buchstaben
- Zwei Prüfziffern (gefolgt von einem optionalen Leerzeichen) 
- 1-7 Gruppen von vier Buchstaben oder Ziffern (können durch Leerzeichengetrennt werden)
- 1 bis 3 Buchstaben oder Ziffern

Das Format für jedes Land unterscheidet sich geringfügig. Der Typ der IBAN-vertraulichen Informationen deckt diese 60 Länder ab:

AD, AE, Al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, Do, EE, es, fi, FO, Fr, GB, ge, GI, GL, GR, HR, HU, IE, IL, is, IT, kW, KZ, LB, Li, lt, LU, LV, MC, MD, me, MK, Mr, MT, mu, NL, No, PL, PT, RO, RS, Sa, SE, Si, SK, SM, TN, TR, VG

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_iban findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Keine

   

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Internationale Klassifikation von Krankheiten (ICD-10-cm)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Ein Schlüsselwort aus Dictionary_icd_10_updated wurde gefunden.
- Ein Schlüsselwort aus Dictionary_icd_10_codes wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

Schlüsselwörter

Ein beliebiger Ausdruck aus dem Dictionary_icd_10_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.

Ein beliebiger Ausdruck aus dem Dictionary_icd_10_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, zehnte Revision, klinische Änderung (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Internationale Klassifikation von Krankheiten (ICD-9-cm)

### <a name="format"></a>Format

Wörterbuch

### <a name="pattern"></a>Muster

Schlüsselwort

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.
- Ein Schlüsselwort aus Dictionary_icd_9_codes wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Ein Schlüsselwort aus Dictionary_icd_9_updated wurde gefunden.

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

### <a name="keywords"></a>Schlüsselwörter

Ein beliebiger Ausdruck aus dem Dictionary_icd_9_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.

Ein beliebiger Ausdruck aus dem Dictionary_icd_9_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.

## <a name="ip-address"></a>IP-Adresse

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4
Komplexes Muster, das formatierte (Punkte) und unformatierte (keine Punkte) Versionen der IPv4-Adressen angibt

#### <a name="ipv6"></a>IPv6
 Komplexes Muster, das formatierte IPv6-Nummern angibt (schließt Doppelpunkte ein)

### <a name="pattern"></a>Muster

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Für IPv6 ist eine DLP-Richtlinie zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden)
- ip address 
- IP-Adressen
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>Irland Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Sechs Ziffern, gefolgt von vier Buchstaben
  
### <a name="pattern"></a>Muster

Sechs Ziffern und vier Buchstaben:
  
- Sechs Ziffern
- Vier Buchstaben (Groß-/Kleinschreibung nicht beachtet)
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_ireland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_ireland_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_ireland_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- ceadúnas tiomána

## <a name="ireland-national-identification-number"></a>Irische nationale Identifikationsnummer
Diese vertrauliche Informationstypen Entität ist nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten.

### <a name="format"></a>Format

Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster
  
### <a name="pattern"></a>Muster

Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster
  
Vom 01 Januar 2013 bis jetzt:
  
-  Sieben Ziffern  
- Eine Prüfziffer
- Ein Leerzeichen oder der Großbuchstabe "W" (Groß-/Kleinschreibung)
    
Vor dem 01. Januar 2013:
  
- Sieben Ziffern  
- Eine Prüfziffer
- Ein Leerzeichen oder ein Großbuchstabe (Groß-/Kleinschreibung beachten)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die-Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus wurde gefunden.
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die-Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.
    
```xml
 <!--Ireland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- Client Identitätsdienst
- identification number

- persönliche ID-Nummer
- persönliche öffentliche Dienstnummer
- persönlicher Dienst Nein
- phearsanta seirbhíse poiblí
- PPS Nein
- PPS-Nummer
- PPS-Dienst Nein
- PPS-uimh
- ppsn
- ppsno #
- ppsno
- öffentlicher Dienst Nein
- publicserviceno #
- publicserviceno
- Umsatz-und Sozialversicherungsnummer
- RSI-Nr.
- RSI-Nummer
- rsin
- seirbhís-aitheantais-Client
- uimh.PSP
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí

## <a name="ireland-passport-number"></a>Irland Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:
  
- Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)
- Sieben Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_ireland_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_ireland_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_ireland_eu_passport_number**

- passport number
- irische Passnummer
- Passport-Nummer
- Pas
- Pass
- Passeport
- Passeport numero

## <a name="ireland-personal-public-service-pps-number"></a>Irland Personal Public Service (PPS)-Nummer

### <a name="format"></a>Format

Altes Format (bis 31. Dez. 2012):
- Sieben Ziffern, gefolgt von 1-2 Buchstaben  

Neues Format (1 Jan 2013 und danach):
- Sieben Ziffern, gefolgt von zwei Buchstaben

### <a name="pattern"></a>Muster

Altes Format (bis 31. Dez. 2012):
- Sieben Ziffern  
- 1-2 Buchstaben (Groß-/Kleinschreibung irrelevant)  

Neues Format (1 Jan 2013 und danach):
- Sieben Ziffern  
- Ein Buchstabe (Groß-/Kleinschreibung irrelevant), wobei es sich um eine alphabetische Prüfziffer handelt  
- Die Buchstaben "A" oder "H" (Groß-/Kleinschreibung irrelevant)

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_ireland_pps wurde gefunden.
    - Die Funktion Func_eu_date findet ein Datum in das richtige Datumsformat.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_ireland_pps sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Die Prüfsumme stimmt.

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ireland_pps"></a>Keyword_ireland_pps

- Personal Public Service Number 
- PPS Number 
- PPS Num 
- PPS No. 
- PPS # 
- PPS # 
- PPSN 
- Public Services Card 
- Uimhir Phearsanta Seirbhíse Poiblí 
- Uimh. PSP 
- PSP 


## <a name="ireland-tax-identification-number"></a>Irische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Buchstaben:
  
- Sieben Ziffern  
- Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_ireland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_ireland_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_ireland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

- Client Identitätsdienst
- identification number

- persönliche ID-Nummer
- persönliche öffentliche Dienstnummer
- persönlicher Dienst Nein
- phearsanta seirbhíse poiblí
- PPS Nein
- PPS-Nummer
- PPS-Dienst Nein
- PPS-uimh
- ppsn
- ppsno #
- ppsno
- öffentlicher Dienst Nein
- publicserviceno #
- publicserviceno
- Umsatz-und Sozialversicherungsnummer
- RSI-Nr.
- RSI-Nummer
- rsin
- seirbhís-aitheantais-Client
- uimh.PSP
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí


## <a name="israel-bank-account-number"></a>Israel Bank Kontonummer

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

Formatiert
- Zwei Ziffern 
- Ein Bindestrich 
- Drei Ziffern 
- Ein Bindestrich 
- Acht Ziffern

Unformatiert
- 	13 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Israelische nationale Identifikationsnummer

### <a name="format"></a>Format

Neun Ziffern

### <a name="pattern"></a>Muster

Neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Italienische Führerscheinnummer
Diese vertrauliche Informationen Typ Entität ist in der EU-Führerscheinnummer vertraulichen Informationstyp enthalten und ist als eigenständige vertrauliche Informationen Typ Entität zur Verfügung.

### <a name="format"></a>Format

Eine Kombination von 10 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

- Eine Kombination aus 10 Buchstaben und Ziffern:
- Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung) 
- Der Buchstabe „A“ oder „W“ (ohne Beachtung der Groß-/Kleinschreibung) 
- Sieben Buchstaben (ohne Beachtung der Groß-/Kleinschreibung), Ziffern oder der Unterstrich 
- Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-national-identification-number"></a>Italienische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Eine Kombination aus Buchstaben und Ziffern aus 16 Zeichen im angegebenen Muster
  
### <a name="pattern"></a>Muster

Eine Kombination aus Buchstaben und Ziffern aus 16 Zeichen:
  
- Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen
- Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen
- Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen
- Ein Buchstabe, der dem Brief für den Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).
- Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen – um zwischen den Geschlechtern zu unterscheiden, wird 40 am Tag der Geburt für Frauen hinzugefügt.
- Vier Ziffern, die der Ortskennzahl für die Gemeinde entsprechen, in der die Person geboren wurde (landesweite Codes werden für fremde Länder verwendet)
- Eine Paritäts Ziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_italy_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_italy_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_italy_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
<!-- Italy national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- mitdices-Steuer
- Geschäftsjahr
- Dice ID personale
- Dice personale
- Geschäftscode
- Numero Bescheinigung personale
- numero di identificazione Fiscale
- Numero-ID personale
- Numero personale
- persönliche Zertifikat Nummer
- persönlicher Code
- persönlicher ID-Code
- persönliche ID-Nummer
- personalcodeno #
- Steuercode
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="italy-passport-number"></a>Italien Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:
  
- Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)
- Sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_italy_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_italy_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_italy_eu_passport_number**

- italienische Passnummer
- Repubblica Italiana Passa Porto
- Passa Porto
- Passa Porto Italiana
- passport number
- Italiana Passa Porto numero
- Passa Porto numero
- Numéro Passeport Italien
- Numéro Passeport

## <a name="italy-tax-identification-number"></a>Italienische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

16 Buchstaben und Ziffern im angegebenen Muster
  
### <a name="pattern"></a>Muster

16 Buchstaben und Ziffern:
  
-  Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen 
- Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen
- Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen
- Eine Ziffer, die dem Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).
- Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen, in dem 40 dem Tag der Geburt hinzugefügt wird, damit weibliche Personen von Männern unterscheiden können
- Vier Ziffern, die einer Ortskennzahl entsprechen, die für die Gemeinde spezifisch ist, in der die Person geboren wurde – landesweite Codes werden für fremde Länder verwendet
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_italy_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_italy_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_italy_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

- mitdices-Steuer
- Geschäftsjahr
- Dice ID personale
- Dice personale
- Geschäftscode
- Numero Bescheinigung personale
- numero di identificazione Fiscale
- Numero-ID personale
- Numero personale
- persönliche Zertifikat Nummer
- persönlicher Code
- persönlicher ID-Code
- persönliche ID-Nummer
- personalcodeno #
- Steuercode
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #


## <a name="japan-bank-account-number"></a>Japan Bank Kontonummer

### <a name="format"></a>Format

Sieben oder acht Ziffern

### <a name="pattern"></a>Muster

Bankkontonummer:
- Sieben oder acht Ziffern
- Niederlassungscode der Bank:
- Vier Ziffern 
- Ein Leerzeichen oder ein Bindestrich (optional) 
- Drei Ziffern

Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_jp_bank_account findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_account wurde gefunden.
- Eine der folgenden Bedingungen trifft zu:
- Die Funktion Func_jp_bank_account_branch_code findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_bank_branch_code wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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
- 口座番号を当座預金口座の確認 
- #アカウントの確認, 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>Japanische Führerscheinnummer

### <a name="format"></a>Format

12 Ziffern

### <a name="pattern"></a>Muster

12 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- DL # 
- DL 
- DLS # 
- DLS 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- lic # 
- LIC 
- LiCS # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>Japan Passnummer

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von sieben Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>Japanische Residenz Kartennummer

### <a name="format"></a>Format

12 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

12 Buchstaben und Ziffern:
- Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) 
- Acht Ziffern 
- Zwei Buchstaben (Groß-/Kleinschreibung irrelevant) 

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_jp_residence_card_number findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_jp_residence_card_number wurde gefunden.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Wohnsitz Kartennummer
- Residenzkarte Nein
- Aufenthaltskarte #
- 在留カード番号

## <a name="japan-resident-registration-number"></a>Japan Resident Registrationsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>Japan Sozialversicherungsnummer (Sin)

### <a name="format"></a>Format

7-12 Ziffern

### <a name="pattern"></a>Muster

7 bis 12 Ziffern:
- Vier Ziffern 
- Ein Bindestrich (optional) 
- Sechs Ziffern oder
- 7-12 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_jp_sin findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_jp_sin wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>Lettland Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Drei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Drei Buchstaben und sechs Ziffern:
  
-  Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_latvia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_latvia_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_latvia_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- autovadītāja apliecība

## <a name="latvia-national-identification-number"></a>Lettische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern und ein Bindestrich im angegebenen Format
  
### <a name="pattern"></a>Muster

11 Ziffern und Bindestrich:
  
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ) 
- Ein Bindestrich 
- Eine Ziffer, die dem Jahrhundert der Geburt entspricht ("0" für das 19. Jahrhundert, "1" für das 20. Jahrhundert und "2" für das 21. Jahrhundert)
- Vier Ziffern, nach dem Zufallsprinzip generiert
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_latvia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_latvia_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_latvia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
<!-- Latvia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- administrative Nummer
- Alva nē
- Geburtsnummer
- Bürgerzahl
- Zivil Nummer
- Elektronische zählungs Nummer
- Elektronische Nummer
- Geschäftscode
- Benutzernummer für das Gesundheitswesen
- ID #
- ID-Code
- identification number

- identifikācijas numurs
- ID-Nummer
- einzelne Nummer
- a. Alva
- Nacionālais-ID
- 
national id
- nationale Identifikationsnummer
- nationale Identitätsnummer
- national insurance number

- nationalregisternummer
- nodokļa numurs
- nodokļu-ID
- nodokļu identifikācija numurs
- persönliche Zertifikat Nummer
- persönlicher Code
- persönlicher ID-Code
- persönliche ID-Nummer
- persönlicher Identifikationscode
- persönlicher Bezeichner
- persönliche Identitätsnummer
- persönliche Nummer
- persönlicher numerischer Code
- personalcodeno #
- Personas KODS
- Code für die Bevölkerungs Identifikation
- öffentliche Dienstnummer
- 
registration number
- Umsatz Nummer
- Sozialversicherungsnummer
- social security number

- Landessteuer Code
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- Nummer des Wählers

## <a name="latvia-passport-number"></a>Lettland Passport-Nummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben oder Ziffern, gefolgt von sieben Ziffern:
  
- Zwei Ziffern oder Buchstaben (ohne Beachtung der Groß-/Kleinschreibung)
- Sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_latvia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_latvia_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_latvia_eu_passport_number**

- passport number
- Lettische Passnummer
- Passport-Nummer
- Pase numurs    

## <a name="latvia-tax-identification-number"></a>Lettische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern im angegebenen Muster
  
- Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ) 
- Eine Ziffer, die dem Jahrhundert der Geburt entspricht, wobei "0" dem 19. Jahrhundert entspricht, "1" entspricht dem 20. Jahrhundert, und "2" entspricht dem 21. Jahrhundert
- Vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_latvia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_latvia_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_latvia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

- administrative Nummer
- Alva nē
- Geburtsnummer
- Bürgerzahl
- Zivil Nummer
- Elektronische zählungs Nummer
- Elektronische Nummer
- Geschäftscode
- Benutzernummer für das Gesundheitswesen
- ID #
- ID-Code
- identification number

- identifikācijas numurs
- ID-Nummer
- einzelne Nummer
- a. Alva
- Nacionālais-ID
- 
national id
- nationale Identifikationsnummer
- nationale Identitätsnummer
- national insurance number

- nationalregisternummer
- nodokļa numurs
- nodokļu-ID
- nodokļu identifikācija numurs
- persönliche Zertifikat Nummer
- persönlicher Code
- persönlicher ID-Code
- persönliche ID-Nummer
- persönlicher Identifikationscode
- persönlicher Bezeichner
- persönliche Identitätsnummer
- persönliche Nummer
- persönlicher numerischer Code
- personalcodeno #
- Personas KODS
- Code für die Bevölkerungs Identifikation
- öffentliche Dienstnummer
- 
registration number
- Umsatz Nummer
- Sozialversicherungsnummer
- social security number

- Landessteuer Code
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- Nummer des Wählers

## <a name="lithuania-drivers-license-number"></a>Litauische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Acht Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_lithuania_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_lithuania_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- Vairuotojo pažymėjimas

## <a name="lithuania-national-identification-number"></a>Litauische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern ohne Leerzeichen und Trennzeichen:
  
- Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
- Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_lithuania_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_lithuania_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_lithuania_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
<!-- Lithuania national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis KODAS
- Mens KODAS
- Bürgerdienst Nummer
- mokesčių-ID
- mokesčių identifikavimas Numeris
- mokesčių identifikavimo Numeris
- mokesčių Numeris
- nationale Identifikationsnummer
- persönlicher Code
- persönlicher numerischer Code
- piliečio paslaugos Numeris
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- unikalus identifikavimo KODAS
- unikalus identifikavimo Numeris
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Litauen-Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_lithuania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_lithuania_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_lithuania_eu_passport_number**

Passnummer lithunian Passport Number Passport No Paso Numeris

## <a name="lithuania-tax-identification-number"></a>Litauische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_lithuania_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_lithuania_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_lithuania_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

- asmeninis skaitmeninis KODAS
- Mens KODAS
- Bürgerdienst Nummer
- mokesčių-ID
- mokesčių identifikavimas Numeris
- mokesčių identifikavimo Numeris
- mokesčių Numeris
- nationale Identifikationsnummer
- persönlicher Code
- piliečio paslaugos Numeris
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- unikalus identifikavimo KODAS
- unikalus identifikavimo Numeris
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="luxemburg-drivers-license-number"></a>Luxemburgische Führerscheinnummer
seine vertraulichen Informationen Typ Entität ist nur in der EU-Führerscheinnummer vertrauliche Informationen Typ verfügbar.

### <a name="format"></a>Format

Sechs Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Sechs Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_luxemburg_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_luxemburg_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- fahrerlaubnis

## <a name="luxemburg-national-identification-number"></a>Luxemburgische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
- Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
- Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_luxemburg_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_luxemburg_eu_national_id_card` wurde gefunden. 
    
```xml
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige-ID
- eindeutige-ID-Nummer
- eindeutigeid #
- ID personnelle
- idpersonnelle #
- idpersonnelle
- einzelner Code
- individuelle ID
- individuelle Identifikation
- individuelle Identität
- Numéro-d'identification-Mitarbeiter
- persönliche ID
- persönliche Identifikation
- persönliche Identität
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- eindeutige ID
- eindeutige Identität
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Luxemburg-Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern oder Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern oder Buchstaben (Groß-/Kleinschreibung nicht beachtet)
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_nation_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_nation_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_nation_eu_passport_number**

Passnummer lettische Passnummer Passport No Passnummer

## <a name="luxemburg-tax-identification-number"></a>Luxemburgische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern:
  
- 11 Ziffern 
- Zwei Prüfziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_luxemburg_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_luxemburg_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_luxemburg_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- Carte de sécurité sociale
- Étain nicht
- Étain #
- identifizierbare d'impôt
- luxemburgische Steuer identifikatiounsnummer
- Numéro d'étain
- Numéro d'identification Fiscal Luxembourgeois
- Numéro d'identification Fiscale
- soziale Sicherheit
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- Steier-ID
- Steier identifikatiounsnummer
- Steier Nummer
- Ingo-ID
- steueridentifikationsnummer
- Steuernummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- Zinn #
- Zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Malaysia-Identifikationskarten Nummer

### <a name="format"></a>Format

12 Ziffern mit optionalen Bindestrichen

### <a name="pattern"></a>Muster

12 Ziffern:
- Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben  
- Ein Bindestrich (optional)  
- Zwei Buchstaben als Code für den Geburtsort  
- Ein Bindestrich (optional)  
- Drei beliebige Ziffern  
- Einstelliger Code für das Geschlecht

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_malaysia_id_card_number findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_malaysia_id_card_number wurde gefunden.

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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- digitale Anwendungs Karte
- i/c
- i/c Nein
- IK
- IC Nein
- id card
- Ausweis
- identity card
- k/p
- k/p Nein
- Kad akuan Diri
- Kad aplikasi Digital
- Kad Einführung in Malaysia
- KP
- KP Nein
- MyKAD
- mykas
- mykid
- mypr
- mytentera
- Malaysia-Personalausweis
- malaysischer Personalausweis
- NRIC
- Personalausweis

## <a name="malta-drivers-license-number"></a>Malta-Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster
  
### <a name="pattern"></a>Muster

Kombination aus zwei Zeichen und sechs Ziffern:
  
- Zwei Zeichen (Ziffern oder Buchstaben, bei denen die Groß-/Kleinschreibung nicht beachtet wird)
- Ein Leerzeichen (optional) 
- Drei Ziffern
- Ein Leerzeichen (optional) 
- Drei Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_malta_eu_driver's_license_number` wurde gefunden. 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_malta_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- Liċenzja TAS-Sewqan

## <a name="malta-national-identification-number"></a>Maltesische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Buchstaben
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Buchstaben:
  
-  Sieben Ziffern  
- Ein Großbuchstabe (Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_malta_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!--Malta national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- Bürgerdienst Nummer
- ID tat-Taxxa
- Identifika numru Tal-biljett
- Kodiċi Numeri personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-Taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru TAS-servizz taċ-ċittadin
- numru tat-Taxxa
- persönlicher numerischer Code
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #


## <a name="malta-passport-number"></a>Malta Passport-Nummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

 Sieben Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_malta_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_malta_eu_passport_number**

- passport number
- Maltesische Passnummer
- Passport-Nummer
- numru Tal-Passaport

## <a name="malta-tax-identification-number"></a>Malta-Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Für maltesische Staatsangehörige: 7 Ziffern und ein Buchstabe im angegebenen Muster
  
Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern
  
### <a name="pattern"></a>Muster

Maltesische Staatsangehörige: 7 Ziffern und ein Buchstaben
  
-  Sieben Ziffern  
- Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern
  
-  Neun Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_malta_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_malta_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_malta_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- Bürgerdienst Nummer
- ID tat-Taxxa
- Identifika numru Tal-biljett
- Kodiċi Numeri personali
- numru ta ' identifikazzjoni personali
- numru ta ' identifikazzjoni tat-Taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' identità uniku
- numru TAS-servizz taċ-ċittadin
- numru tat-Taxxa
- persönlicher numerischer Code
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Niederländische Bürgerdienst Nummer (BSN)

### <a name="format"></a>Format

8-9 Ziffern mit optionalen Leerzeichen

### <a name="pattern"></a>Muster

8-9 Ziffern:
- Drei Ziffern 
- Ein Leerzeichen (optional)  
- Drei Ziffern 
- Ein Leerzeichen (optional)  
- 2-3 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_netherlands_bsn sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_netherlands_bsn wurde gefunden.
- Die Funktion Func_eu_date2 findet ein Datum im richtigen Datumsformat.
- Die Prüfsumme stimmt.

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn
  
- BSN #
- BSN
- burgerservicenummer
- Bürgerdienst Nummer
- Personennummer
- persönliche Nummer
- persönlicher numerischer Code
- personenbezogene Nummer
- persoonlijk Nummer
- Persoonlijke-numerieke-Code
- persoonsgebonden
- persoonsnummer
- Sociaal-fiscaal Nummer
- sozial-Steuernummer
- Sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Niederländische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_netherlands_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_netherlands_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- permis de conduire
- rijbewijs
- rijbewijsnummer

## <a name="netherlands-national-identification-number"></a>Niederländische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_netherlands_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus wurde gefunden.
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_netherlands_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!--Netherland national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- BSN #
- BSN
- burgerservicenummer
- Bürgerdienst Nummer
- Personennummer
- persönliche Nummer
- persönlicher numerischer Code
- personenbezogene Nummer
- persoonlijk Nummer
- Persoonlijke-numerieke-Code
- persoonsgebonden
- persoonsnummer
- Sociaal-fiscaal Nummer
- sozial-Steuernummer
- Sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #

## <a name="netherlands-passport-number"></a>Niederländische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Neun Buchstaben oder Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Buchstaben oder Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_netherlands_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_netherlands_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_netherlands_eu_passport_number**

- niederländische Passnummer
- passport number
- niederländische Passnummer
- Nederlanden paspoort Nummer
- paspoort
- Nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>Niederländische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_netherlands_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_netherlands_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_netherlands_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- BTW Nummer
- hollânske-Steueridentifikation
- hulandes-Impuesto-ID-Nummer
- hulandes Impuesto Identification
- identificatienummer-Belastungen
- identificatienummer van belasten
- Impuesto-Identifikationsnummer
- Impuesto-Nummer
- Nederlands Belasting ID Nummer
- Nederlands belasten identificatie
- Nederlands belasten identificatienummer
- Nederlands belastingnummer
- Nederlandse belasten von identificatie
- niederländische Steueridentifikation
- niederländische Steueridentifikation
- Niederlande Tin
- niederländische Zinn
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steueridentifikation Tal
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- Steuer Tal
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="new-zealand-ministry-of-health-number"></a>Neuseeländisches Gesundheitsministerium Nummer

### <a name="format"></a>Format

Drei Buchstaben, ein Leerzeichen (optional) und vier Ziffern

### <a name="pattern"></a>Muster

Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet) ein Leerzeichen (optional) vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_new_zealand_ministry_of_health_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_nz_terms wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

Schlüsselwörter

Keyword_nz_terms

- Nhi 
- New Zealand 
- Gesundheitswesen 
- Behandlung 
   
## <a name="norway-identification-number"></a>Norwegen-Identifikationsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern:
- Sechs Ziffern im Format TTMMJJ, die das Geburtsdatum angeben  
- Dreistellige individuelle Zahl  
- Zwei Prüfziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_norway_id_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_norway_id_number wurde gefunden.
- Die Prüfsumme stimmt.
- Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_norway_id_numbe sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Identifizierung
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Philippinische Unified Multi-Purpose Identification Number

### <a name="format"></a>Format

12 Ziffern, durch Bindestriche getrennt

### <a name="pattern"></a>Muster

12 Ziffern:
- Vier Ziffern 
- Ein Bindestrich  
- Sieben Ziffern  
- Ein Bindestrich  
- Eine Ziffer

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_philippines_unified_id findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_philippines_id wurde gefunden.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- Umid 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Polen-Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

14 Ziffern mit 2 Schrägstrichen
  
### <a name="pattern"></a>Muster

14 Ziffern und 2 Schrägstriche:
  
-  Fünf Ziffern 
- Ein Schrägstrich 
- Zwei Ziffern
- Ein Schrägstrich 
- Sieben Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_poland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_poland_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_poland_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- Prawo jazdy

## <a name="poland-identity-card"></a>Polen-Personalausweis

### <a name="format"></a>Format

Drei Buchstaben und sechs Ziffern

### <a name="pattern"></a>Muster

Drei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sechs Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist 75% sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn in einer Nähe von 300 Zeichen: die Funktion Func_polish_national_id findet Inhalte, die mit dem Muster übereinstimmen.
Ein Schlüsselwort aus Keyword_polish_national_id_passport_number wurde gefunden.
Die Prüfsumme stimmt.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i Numer dowodu osobistego
- Nazwa i Nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. OS.

   
## <a name="poland-national-id-pesel"></a>Polnische ID-Karte (PESEL)
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_pesel_identification_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_pesel_identification_number wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny-Numer
- niepowtarzalnynumer
- Nr.-PESEL
- Nr-PESEL
- Numer identyfikacyjny
- PESEL
- tożsamości Narodowej

   
## <a name="poland-passport-number"></a>Polen-Passnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

Zwei Buchstaben und sieben Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von sieben Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-tax-identification-number"></a>Polnische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Elf Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Elf Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_poland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_poland_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_poland_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

NIP #
- NIP
- Numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- USt-ID #
- USt-ID
- USt-IdNr.
- USt-IdNr.
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Portugiesische Bürgerkarten Nummer
- Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.
- Diese vertrauliche Informationstyp Entität ist in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-Typ für vertrauliche Informationen enthalten.


### <a name="format"></a>Format

Acht Ziffern

### <a name="pattern"></a>Muster

Acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_portugal_citizen_card findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_portugal_citizen_card wurde gefunden.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- Cartão de Cidadão
- Bürgerkarte
- Dokumentnummer
- Documento de identificação
- ID-Nummer
- Identifikationsnummer
- identification number

- Personalausweis Nr.
- Personalausweisnummer
- nationale ID-Karte
- Nic
- número BI de Portugal
- número de identificação Civil
- número de identificação Fiscal
- número do Documento
- Portugal BI-Nummer


## <a name="portugal-drivers-license-number"></a>Portugiesische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:
  
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
- Ein Bindestrich 
- Sechs Ziffern
- Ein Leerzeichen
- Eine Ziffer
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_portugal_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_portugal_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- Carteira de motorista

## <a name="portugal-passport-number"></a>Portugiesische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Ein Buchstabe, gefolgt von sechs Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Ein Buchstabe, gefolgt von sechs Ziffern:
  
- Ein Buchstabe (ohne Beachtung der Groß-/Kleinschreibung)
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_portugal_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_portugal_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_portugal_eu_passport_number**

Passnummer portugiesische Passnummer Passport No número do passaporte

## <a name="portugal-tax-identification-number"></a>Portugiesische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_portugal_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_portugal_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_portugal_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- CPF #
- CPF
- NIF #
- NIF
- número de identificação fisca
- numerisch-Geschäftsjahr
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #


## <a name="romania-drivers-license-number"></a>Rumänische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Ein Zeichen gefolgt von acht Ziffern
  
### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von acht Ziffern:
  
- Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern 
- Acht Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_romania_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_romania_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- permis de conducere

## <a name="romania-national-identification-number"></a>Rumänische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_romania_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_romania_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_romania_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!--Romania national identification number  -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- CNP #
- CNP
- COD identificare Personal
- COD numerisch persönlich
- COD Unic identificare
- codnumericpersonal #
- Codul Fiscal Nr.
- identificarea fiscală Nr #
- ID-UL taxei
- Versicherungsnummer
- insurancenumber #
- nationale ID #
- 
national id
- nationale Identifikationsnummer
- număr identificare Personal
- număr identitate
- număr Personal Unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- persönlicher numerischer Code
- PIN #
- PIN
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Rumänische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Acht oder neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht oder neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_romania_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_romania_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_romania_eu_passport_number**

- passport number
- rumänische Passnummer
- Passport-Nummer
- numărul pașaportului

## <a name="romania-tax-identification-number"></a>Rumänische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_romania_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_romania_eu_tax_file_number` wurde gefunden. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

- CNP #
- CNP
- COD identificare Personal
- COD numerisch persönlich
- COD Unic identificare
- codnumericpersonal #
- Codul Fiscal Nr.
- identificarea fiscală Nr #
- ID-UL taxei
- Versicherungsnummer
- insurancenumber #
- nationale ID #
- 
national id
- nationale Identifikationsnummer
- număr identificare Personal
- număr identitate
- număr Personal Unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- persönlicher numerischer Code
- PIN #
- PIN
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #
- eindeutige Identifikationsnummer
- eindeutige Identitätsnummer
- uniqueidentityno #
- uniqueidentityno



## <a name="saudi-arabia-national-id"></a>Saudi-Arabische Ausweisnummer

### <a name="format"></a>Format

10 Ziffern

### <a name="pattern"></a>Muster

10 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Singapur nationale Registrierungs-Personalausweisnummer (NRIC)

### <a name="format"></a>Format

Neun Buchstaben und Ziffern

### <a name="pattern"></a>Muster

- Neun Buchstaben und Ziffern:
- Die Buchstaben "F", "G", "S" oder "T" (Groß-/Kleinschreibung irrelevant)  
- Sieben Ziffern  
- Eine alphabetische Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_singapore_nric wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_singapore_nric findet Inhalte, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- IK 
- Foreign Identification Number 
- FIN 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Slowakische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Ein Zeichen gefolgt von sieben Ziffern
  
### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von sieben Ziffern
  
- Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern
-  Sieben Ziffern 
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovakia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovakia_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_slovakia_eu_driver ' s_license_number**

DL # Driver License Driver License Number Treiber Lizenz Treiber lic.
Führerschein Treiber Lizenznummer Führerschein Führerscheinnummer Treiber Lizenznummer dlno # vodičský preukaz

## <a name="slovakia-national-identification-number"></a>Slowakische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Zehn Ziffern mit einem Backslash
  
### <a name="pattern"></a>Muster

Zehn Ziffern mit einem Backslash:
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovakia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovakia_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovakia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- Slovakia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- Geburtsnummer
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- ID-Nummer
- Identifikationsnummer
- identification number

- identifikačná Karta č
- identifikačné číslo
- Personalausweis Nr.
- Personalausweisnummer
- Národná identifikačná značka č
- nationale Nummer
- nationalnumber #
- Nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="slovakia-passport-number"></a>Slowakische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Eine Ziffer oder ein Buchstabe, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Eine Ziffer oder ein Buchstabe (ohne Groß-/Kleinschreibung), gefolgt von sieben Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovakia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovakia_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_slovakia_eu_passport_number**

- passport number
- Slowakische Passport-Nummer
- Passport-Nummer
- číslo Pasu

## <a name="slovakia-tax-identification-number"></a>Slowakische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovakia_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovakia_eu_tax_file_number` wurde gefunden. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

- azonosító szám
- Geburtsnummer
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- ID-Nummer
- Identifikationsnummer
- identification number

- identifikačná Karta č
- identifikačné číslo
- Personalausweis Nr.
- Personalausweisnummer
- Národná identifikačná značka č
- nationale Nummer
- nationalnumber #
- Nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- SSN #
- SSN
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #


## <a name="slovenia-drivers-license-number"></a>Slowenische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovenia_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_slovenia_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license 
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- vozniško dovoljenje

## <a name="slovenia-national-identification-number"></a>Slowenische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern im angegebenen Muster:
  
-  Sieben Ziffern, die dem Geburtsdatum (DDMMLLL) entsprechen, wobei "LLL" den letzten drei Ziffern des Geburtsjahres entspricht. 
- Zwei Ziffern, die dem Geburts Bereich entsprechen
- Drei Ziffern, die einer Kombination aus Geschlecht und Seriennummer für Personen entsprechen, die am selben Tag geboren wurden (000-499 für männliche und 500-999 für weiblich)
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovenia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovenia_eu_national_id_card` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovenia_eu_national_id_card` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- Slovenia national identification number -->
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- EMŠO
- Enotna maticna številka obcana
- ID-Karte
- identification number

- identifikacijska številka
- Personalausweis
- Nacionalna-ID
- Nacionalni-potni-Liste
- 
national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- persönlicher Code
- persönliche Nummer
- persönlicher numerischer Code
- številka državljana
- eindeutige Bürgerzahl
- eindeutige ID-Nummer
- eindeutige Identitätsnummer
- eindeutige Master Bürgerzahl
- eindeutige Registrierungsnummer
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Slowenische Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sieben Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Zwei Buchstaben, gefolgt von sieben Ziffern:
  
- Der Buchstabe "P"
- Ein Großbuchstabe
- Sieben Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovenia_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovenia_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_slovenia_eu_passport_number**

Passnummer slowenische Passnummer Passport No številka potnega lista

## <a name="slovenia-tax-identification-number"></a>Slowenische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovenia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_slovenia_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_slovenia_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka beim Davka
- številka davčne datoteke
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #



## <a name="south-africa-identification-number"></a>Südafrikanische Identifikationsnummer

### <a name="format"></a>Format

13 Ziffern, die Leerzeichen enthalten können

### <a name="pattern"></a>Muster

13 Ziffern:
- Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben  
- Vier Ziffern 
- Ein einstelliger Citizenship-Indikator  
- Die Ziffer "8" oder "9"  
- Eine Ziffer als Prüfsummenziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_south_africa_identification_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_south_africa_identification_number wurde gefunden.
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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Identifizierung 
   
## <a name="south-korea-resident-registration-number"></a>Südkorea ansässige Registrierungsnummer

### <a name="format"></a>Format

13 Ziffern, die einen Bindestrich enthalten

### <a name="pattern"></a>Muster

13 Ziffern:
- Sechs Ziffern im Format JJMMTT, die das Geburtsdatum angeben  
- Ein Bindestrich  
- Eine Ziffer, die durch das Jahrhundert und das Geschlecht bestimmt wird  
- Vierstelliger Code für die Geburtsregion  
- Eine Ziffer, um Personen zu unterscheiden, für die die vorhergehenden Zahlen identisch sind  
- Eine Prüfziffer

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_south_korea_resident_number wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_south_korea_resident_number sucht nach Inhalten, die mit dem Muster übereinstimmen.
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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Spanische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Acht Ziffern, gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern, gefolgt von einem Zeichen:
  
- Acht Ziffern 
- Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_spain_eu_driver's_license_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_spain_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_spain_eu_driver ' s_license_number**

- dlno #
- DL #
- Treiber lic.
- Treiber Lizenz
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- Führerschein
- driving license
- Führerscheinnummer
- Treiber Lizenznummer
- Führerscheinnummer
- Lizenznummer für Treiber
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- Führerschein
- Führerscheinnummer
- Permiso de conducción
- permiso conducción
- número licencia Conducir
- número de carnet de Conducir
- número Carnet Conducir
- licencia Conducir
- número de Permiso de Conducir
- número de Permiso Conducir
- número Permiso Conducir
- Permiso Conducir
- licencia de Manejo
- El Carnet de Conducir
- Carnet Conducir

## <a name="spain-national-identification-number"></a>Spanische nationale Identifikationsnummer
Diese vertrauliche Informationstyp Entität steht nur im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" zur Verfügung.

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Zeichen
  
- Sieben Ziffern 
- Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_spain_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_spain_eu_national_id_card"` wurde gefunden. 
    
```xml
<!-- Spain national identification number -->
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- Carné de Identidad
- DNI #
- DNI
- dninúmero #
- Documento Nacional de Identidad
- Identidad Único
- identidadúnico #
- Versicherungsnummer
- nationale Identifikationsnummer
- nationale Identität
- National-Nr. #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de Identificación
- número Nacional Identidad
- persönliche Identifikationsnummer
- persönliche Identität Nein
- eindeutige Identitätsnummer
- UniqueId #

## <a name="spain-passport-number"></a>Spanien Passnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Passport-Nummer verfügbar.

### <a name="format"></a>Format

Eine Kombination aus Buchstaben und Zahlen mit acht oder neun Zeichen ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Eine Kombination aus Buchstaben und Zahlen aus acht oder neun Zeichen:
  
-  Zwei Ziffern oder Buchstaben 
- Eine Ziffer oder ein Buchstabe (optional)
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht anwendbar
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_spain_eu_passport_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_spain_eu_passport_number` wurde gefunden. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_spain_eu_passport_number**

- Pass
- Spanien-Passport
- Passport-Buch
- passport number
- Passport-Nummer
- Libreta Pasaporte
- número Pasaporte
- ESPAÑA PASAPORTE
- pasaporte


## <a name="spain-social-security-number-ssn"></a>Spanien Sozialversicherungsnummer (SSN)
Diese vertrauliche Informationstyp Entität ist in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

11-12 Ziffern

### <a name="pattern"></a>Muster

11-12 Ziffern:
- Zwei Ziffern 
- Ein Schrägstrich (optional) 
- 7 bis 8 Ziffern 
- Ein Schrägstrich (optional) 
- Zwei Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

Keine

## <a name="spain-tax-identification-number"></a>Spanien Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster
  
### <a name="pattern"></a>Muster

Spanisch natürliche Personen mit einem nationalen spanischen Identitätsausweis:
  
-  Acht Ziffern 
- Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung) 
    
Nicht-residente Spanier ohne einen nationalen Identitätsausweis in Spanien
  
- Ein Großbuchstabe "L" (Unterscheidung nach Groß-/Kleinschreibung)
- Sieben Ziffern 
- Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung) 
    
Ansässige Spanier unter 14 Jahren ohne einen nationalen spanischen Identitätsausweis:
  
- Ein Großbuchstabe "K" (Unterscheidung nach Groß-/Kleinschreibung)
-  Sieben Ziffern  
- Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)
    
Ausländer mit Identifikationsnummer eines Ausländers
  
- Ein Großbuchstabe mit "X", "Y" oder "Z" (Groß-/Kleinschreibung wird beachtet) 
- Sieben Ziffern 
- Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung) 
    
Ausländer ohne Identifikationsnummer eines Ausländers
  
- Ein Großbuchstabe, der "M" ist (Groß-/Kleinschreibung beachten) 
- Sieben Ziffern 
- Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung) 
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_spain_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_spain_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_spain_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- CIF
- cifid #
- cifnúmero #
- número de contribuyente
- número de Identificación Fiscal
- número de Impuesto Corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- Steuerdatei Nein
- Steuerdatei Nummer
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #


## <a name="sql-server-connection-string"></a>SQL Server Verbindungszeichenfolge

### <a name="format"></a>Format

Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID", gefolgt von den Zeichen und Zeichenfolgen, die im Muster unten dargestellt sind.

### <a name="pattern"></a>Muster

- Die Zeichenfolge "Benutzer-ID", "Benutzer-ID", "UID" oder "UserID"
- Eine beliebige Kombination von zwischen 1-200 unter-oder Großbuchstaben, Ziffern, Symbolen, Sonderzeichen oder Leerzeichen
- Die Zeichenfolge "Password" oder "pwd", wobei "pwd" kein Kleinbuchstabe vorangestellt ist
- Ein Gleichheitszeichen (=)
- Ein beliebiges Zeichen, das kein Dollarzeichen ($), Prozentzeichen (%), größer als das Symbol (>), Symbol (@), Anführungszeichen ("), Semikolon (;), linke geschweifte Klammer ([) oder linke Klammer ({) ist.
- Eine beliebige Kombination von 7-128 Zeichen, die kein Semikolon sind (;), Schrägstrich (/) oder Anführungszeichen (")
- Ein Semikolon (;) oder Anführungszeichen (")

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck CEP_Regex_SQLServerConnectionString findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus CEP_GlobalFilter wurde **nicht** gefunden.
- Der reguläre Ausdruck CEP_PasswordPlaceHolder findet **keine** Inhalte, die mit dem Muster übereinstimmen.
- Der reguläre Ausdruck CEP_CommonExampleKeywords findet **keine** Inhalte, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- Einige-Kennwort
- somepassword
- secretPassword
- Beispiel

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- Password oder PWD gefolgt von 0-2 Leerzeichen, ein Gleichheitszeichen (=), 0-2 Leerzeichen und ein Sternchen (*)--oder--
- Password oder PWD gefolgt von:
    - Gleichheitszeichen (=)
    - Kleiner als-Symbol (<)
    - Eine beliebige Kombination von 1-200 Zeichen mit groß-oder Kleinbuchstaben, Ziffern, einem Sternchen (*), einem Bindestrich (-), einem Unterstrich (_) oder einem Leerzeichen
    - Größer als-Symbol (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Beachten Sie, dass dieser vertrauliche Informationstyp technisch diese Schlüsselwörter mit einem regulären Ausdruck und nicht mit einer Stichwortliste identifiziert.)

- contoso
- Fabrikam
- Northwind
- Sandkasten
- OneBox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->NET

## <a name="sweden-drivers-license-number"></a>Schwedische Führerscheinnummer
Diese Typen Entität für vertrauliche Informationen ist nur im vertraulichen Informationstyp für den EU-Führerscheinnummer verfügbar.

### <a name="format"></a>Format

Zehn Ziffern mit einem Bindestrich
  
### <a name="pattern"></a>Muster

Zehn Ziffern mit einem Bindestrich:
  
-  Sechs Ziffern 
- Ein Bindestrich
- Vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_sweden_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_sweden_eu_driver's_license_number` wurde gefunden. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Schlüsselwörter

**Keywords_sweden_eu_driver ' s_license_number**

- DL #
- driver license
- Treiber Lizenznummer
- Treiber Lizenz
- Treiber lic.
- drivers license
- drivers licence
- driver's license
- Führerscheinnummer
- Führerscheinnummer
- Führerscheinnummer
- dlno #
- körkort

## <a name="sweden-national-id"></a>Nationale schwedische ID-Nummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp "EU-nationale Identifikationsnummer" enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

10 oder 12 Ziffern und ein optionales Trennzeichen

### <a name="pattern"></a>Muster

10 oder 12 Ziffern und ein optionals Trennzeichen:
- 2 bis 4 Ziffern (optional) 
- Sechs Ziffern im Datumsformat JJMMTT 
- Trennzeichen „-“ oder „+“ (optional) und
- Vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_swedish_national_identifier findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

Nein
   
## <a name="sweden-passport-number"></a>Schwedische Passnummer
Diese vertrauliche Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer enthalten und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

Acht Ziffern

### <a name="pattern"></a>Muster

Acht aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_sweden_passport_number findet Inhalte, die dem Muster entsprechen.
- Eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_passport wurde gefunden.
    - Ein Schlüsselwort aus Keyword_sweden_passport wurde gefunden.

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

### <a name="keywords"></a>Schlüsselwörter
   
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
- Pass # 
- Passport-Nr 
- Passportno 
- passportnumber 
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

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Schwedische Sozialversicherungsnummer oder gleichwertige Identifikation
Diese vertrauliche Informationstyp Entität ist nur in der Sozialversicherungsnummer der EU oder einem entsprechenden ID-vertraulichen Informationstyp verfügbar.

### <a name="format"></a>Format

12 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

12 Ziffern:
  
-  Acht Ziffern, die dem Geburtsdatum entsprechen (JJJJMMTT) 
- Drei Ziffern, die einer Seriennummer entsprechen: 
  - Die letzte Ziffer in der Seriennummer gibt das Geschlecht durch die Zuweisung einer ungeraden Zahl für männliche und eine gerade Zahl für weiblich an.
  - Bis zu 1990 entsprach die Zuordnung der Seriennummer dem Kreis, in dem der Inhaber der Nummer geboren wurde oder (sofern er vor 1947 geboren wurde), in dem er nach Steuerunterlagen am 1. Januar 1947 mit einem Sondercode (in der Regel 9 als siebte Ziffer) für Einwanderer gelebt hatte. 
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_sweden_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_sweden_eu_ssn_or_equivalent` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_sweden_eu_ssn_or_equivalent` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- persönliche ID-Nummer
- identification number
- persönliche ID Nein
- Identität Nein
- Identifikationsnummer
- persönliche Identifikationsnummer
- PERSONNUMMER-ID
- personligt-ID-Nummer
- unikt-ID-Nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>Schwedische Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.

### <a name="format"></a>Format

Zehn Ziffern und ein Symbol im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zehn Ziffern und ein Symbol:
  
- Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
- Pluszeichen, Minuszeichen oder Backslash
- Drei Ziffern, die die Identifikationsnummer eindeutig machen: 
  - Für Zahlen, die vor 1990 ausgegeben wurden, identifizieren die siebte und die achte Ziffer den Geburts Kreis oder den in der fremde geborenen Personen.
  - Die Ziffer in der neunten Position gibt das Geschlecht entweder ungerade für männliche oder sogar für weiblich an.
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_sweden_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
- Ein Schlüsselwort aus `Keywords_sweden_eu_tax_file_number` wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_sweden_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```xml
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- persönliche ID-Nummer
- personnummer
- Skate ID Nummer
- skatt Identifikation
- skattebetalarens identifikationsnummer
- Sverige Tin
- Steuerdatei
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #



## <a name="swift-code"></a>SWIFT-Codes

### <a name="format"></a>Format

Vier Buchstaben, gefolgt von 5-31 Buchstaben oder Ziffern

### <a name="pattern"></a>Muster

Vier Buchstaben, gefolgt von 5 bis 31 Buchstaben oder Ziffern:
- Vier Buchstaben für den Bankcode (ohne Beachtung der Groß-/Kleinschreibung) 
- Ein optionales Leerzeichen 
- 4 bis 28 Buchstaben oder Ziffern (BBAN, Basic Bank Account Number) 
- Ein optionales Leerzeichen 
- 1 bis 3 Buchstaben oder Ziffern (Rest des BBAN)

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- SWIFT\# 
- Swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- BIC\# 
- BIC\# 
- bank identifier code 
- 標準化 9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rapide\# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \#BIC 
- code identificateur de banque 
   
## <a name="taiwan-national-identification-number"></a>Taiwan nationale Identifikationsnummer

### <a name="format"></a>Format

Ein Buchstabe (auf Englisch) gefolgt von neun Ziffern

### <a name="pattern"></a>Muster

Ein Buchstabe (Englisch), gefolgt von neun Ziffern:
- Ein Buchstaben (auf Englisch, Groß-/Kleinschreibung irrelevant) 
- Die Ziffer "1" oder "2" 
- Acht Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_taiwanese_national_id"></a>Keyword_taiwanese_national_id

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
   
## <a name="taiwan-passport-number"></a>Taiwan Passport-Nummer

### <a name="format"></a>Format

- Biometrische Passport-Nummer: neun Ziffern
- Nicht biometrische Passport-Nummer: neun Ziffern

### <a name="pattern"></a>Muster
Biometrische Passnummer:
- Die Ziffer "3"  
- Acht Ziffern

Nicht biometrische Passnummer:
- Neun Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_taiwan_passport findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_taiwan_passport wurde gefunden.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan Resident Certificate (Arc/tarc)-Nummer

### <a name="format"></a>Format

10 Buchstaben und Ziffern

### <a name="pattern"></a>Muster

10 Buchstaben und Ziffern:
- Zwei Buchstaben (Groß-/Kleinschreibung irrelevant)  
- Acht Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Der reguläre Ausdruck Regex_taiwan_resident_certificate findet Inhalte, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_taiwan_resident_certificate wurde gefunden.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

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

## <a name="thai-population-identification-code"></a>Thai-Populations Kennzeichnungscode

### <a name="format"></a>Format

13 Ziffern

### <a name="pattern"></a>Muster

13 Ziffern:
- Die erste Ziffer ist nicht 0 oder 9. 
- 12 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_Thai_Citizen_Id wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_Thai_Citizen_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_thai_citizen_id"></a>Keyword_Thai_Citizen_Id

- ID Number
- Identifikationsnummer
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Türkische nationale Identifikationsnummer

### <a name="format"></a>Format

11 Ziffern

### <a name="pattern"></a>Muster

11 Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_Turkish_National_Id wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_Turkish_National_Id sucht nach Inhalten, die mit dem Muster übereinstimmen.

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC KİMLİK Nein
- TC KİMLİK numarası
- Vatandaşlık numarası
- Vatandaşlık Nein

## <a name="uk-drivers-license-number"></a>Britannien Führerscheinnummer
Diese vertrauliche Informationen Typ Entität ist in der EU-Führerscheinnummer vertraulichen Informationstyp enthalten und ist als eigenständige vertrauliche Informationen Typ Entität zur Verfügung.

### <a name="format"></a>Format

Kombination aus 18 Buchstaben und Ziffern im angegebenen Format

### <a name="pattern"></a>Muster

18 Buchstaben und Ziffern:
- Fünf Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens 
- Eine Ziffer 
- Fünf Ziffern im Datumsformat MMDDY für das Geburtsdatum (das siebte Zeichen wird um 50 erhöht, wenn der Fahrer weiblich ist, d. h. 51 bis 62 statt 01 bis 12).
- Zwei Buchstaben (ohne Beachtung der Groß-/Kleinschreibung) oder die Ziffer 9 anstelle eines Buchstabens 
- Fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- Quads entwickelt 
- motor cars 
- 125cc 
- Beiwagen 
- Dreiräder 
- Motorrad 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>Britannien Nummer der Wahl Rolle

### <a name="format"></a>Format

Zwei Buchstaben gefolgt von 1-4 Ziffern

### <a name="pattern"></a>Muster

Zwei Buchstaben (Groß-/Kleinschreibung irrelevant), gefolgt von 1-4 Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Britannien National Health Service-Nummer

### <a name="format"></a>Format

10-17 Ziffern, durch Leerzeichen getrennt

### <a name="pattern"></a>Muster

10 bis 17 Stellen:
- 3 oder 10 Ziffern 
- Ein Leerzeichen 
- Drei Ziffern 
- Ein Leerzeichen 
- Vier Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- NHS 
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
- D. O. B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>Britannien Nationale Versicherungsnummer (Nino)
Diese vertrauliche Informationen Typ Entität ist in der EU-nationalen Identificaiton Nummer vertraulichen Informationstyp enthalten und ist als eigenständige vertrauliche Informationen Typ Entität verfügbar.

### <a name="format"></a>Format

7 Zeichen oder 9 Zeichen, getrennt durch Leerzeichen oder Bindestriche

### <a name="pattern"></a>Muster

Zwei mögliche Muster:

- Zwei Buchstaben (gültige Ninos verwenden nur bestimmte Zeichen in diesem Präfix, die von diesem Muster überprüft werden; Groß-/Kleinschreibung wird nicht berücksichtigt)
- Sechs Ziffern
- Entweder "A", "B", "C" oder "'d" (wie das Präfix sind nur bestimmte Zeichen im Suffix zulässig; Groß-/Kleinschreibung wird nicht berücksichtigt)

ODER

- Zwei Buchstaben
- Ein Leerzeichen oder ein Bindestrich
- Zwei Ziffern
- Ein Leerzeichen oder ein Bindestrich
- Zwei Ziffern
- Ein Leerzeichen oder ein Bindestrich
- Zwei Ziffern
- Ein Leerzeichen oder ein Bindestrich
- Entweder "A", "B", "C" oder "'d"

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_uk_nino wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_uk_nino findet Inhalte, die dem Muster entsprechen.
- Es wurde kein Schlüsselwort aus Keyword_uk_nino gefunden.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- Versicherungs
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- soziale Sicherheit
- great britain
- Versicherungs
    
## <a name="uk-tax-identification-number"></a>Britannien Steueridentifikationsnummer
Diese vertrauliche Informationstyp Entität ist nur im vertraulichen Informationstyp EU-Steueridentifikationsnummer verfügbar.


### <a name="format"></a>Format

Unique Steuerzahler Referenz (UTR): 10 Ziffern ohne Leerzeichen und Trennzeichen
 
  
### <a name="pattern"></a>Muster

Unique Steuerzahler Referenz (UTR): 10 Ziffern

  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die `Func_uk_eu_tax_file_number` -Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus `Keywords_uk_eu_tax_file_number` wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- Steuernummer
- Steuerdatei
- tax id

- Steueridentifikationsnummer
- Steueridentifikationsnummer
- Steuernummer #
- Steuernummer
- Steuerregistrierungsnummer
- per Taxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- Tin-ID
- Tin Nein
- Zinn #

## <a name="us-bank-account-number"></a>US-Bank Kontonummer

### <a name="format"></a>Format

8-17 Ziffern

### <a name="pattern"></a>Muster

8-17 aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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

Abhängig vom Bundesstaat – am Beispiel für New York:
- Neun Ziffern, die wie DDD DDD DDD formatiert sind, stimmen überein.
- Neun Ziffern wie ddddddddd werden nicht übereinstimmen.

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_new_york_drivers_license_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_[state_name]_drivers_license_name wurde gefunden.
- Ein Schlüsselwort aus Keyword_us_drivers_license wurde gefunden.

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

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
- Driver ' License 
- Driver ' Licenses 
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
- Driver ' License # 
- Driver ' Licenses # 
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


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- Abkürzung für Bundesstaat (z. B. „NY“) 
- Name des Bundesstaats (z. B. „New York“)

## <a name="us-individual-taxpayer-identification-number-itin"></a>US-individuelle Steuerzahler-Identifikationsnummer (ITIN)

### <a name="format"></a>Format

Neun Ziffern, die mit "9" beginnen und "7" oder "8" als vierte Ziffer enthalten, optional mit Leerzeichen oder Bindestrichen formatiert

### <a name="pattern"></a>Muster

Formatiert
- Die Ziffer 9 
- Zwei Ziffern 
- Ein Leerzeichen oder ein Bindestrich 
- Eine 7 oder 8 
- Eine Ziffer 
- Ein Leerzeichen oder ein Bindestrich 
- Vier Ziffern

Unformatiert
- Die Ziffer 9 
- Zwei Ziffern 
- Eine 7 oder 8 
- Fünf Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_formatted_itin findet Inhalte, die dem Muster entsprechen.
- Mindestens eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_itin wurde gefunden.
    - Die Funktion Func_us_address findet eine Adresse im richtigen Format.
    - Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.
    - Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_unformatted_itin findet Inhalte, die dem Muster entsprechen.
- Mindestens eine der folgenden Bedingungen trifft zu:
    - Ein Schlüsselwort aus Keyword_itin_collaborative wurde gefunden.
    - Die Funktion Func_us_address findet eine Adresse im richtigen Format.
    - Die Funktion Func_us_date findet ein Datum im richtigen Datumsformat.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_itin"></a>Keyword_itin

- Steuer 
- tax id 
- tax identification 
- Itin 
- SSN 
- Zinn 
- social security 
- tax payer 
- itins 
- per Taxi 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- Lizenz 
- DL 
- DOB 
- Geburtsdatum 
- Geburtstag 
- Date of Birth 

## <a name="us-social-security-number-ssn"></a>US-Sozialversicherungsnummer (SSN)

### <a name="format"></a>Format

9 Ziffern in formatiertem oder unformatiertem Muster

> [!NOTE]
> Wenn ein SSN vor Mitte 2011 ausgegeben wird, weist es eine starke Formatierung auf, bei der bestimmte Teile der Zahl in bestimmte Bereiche fallen müssen, um gültig zu sein (aber keine Prüfsumme).

### <a name="pattern"></a>Muster

Vier Funktionen suchen nach Sozialversicherungsnummern in vier verschiedenen Mustern:
- Func_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)
- Func_unformatted_ssn findet Sozialversicherungsnummern mit starker Formatierung vor 2011, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.
- Func_randomized_formatted_ssn findet Post-2011-Sozialversicherungsnummern, die mit Bindestrichen oder Leerzeichen formatiert sind (DDD-DD-dddd oder DDD DD dddd)
- Func_randomized_unformatted_ssn findet Post-2011 Sozialversicherungsnummern, die als neun aufeinanderfolgende Ziffern (ddddddddd) unformatiert sind.

### <a name="checksum"></a>Prüfsumme

Nein


### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_ssn findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_unformatted_ssn sucht nach Inhalten, die mit dem Muster übereinstimmen.
- Ein Schlüsselwort aus Keyword_ssn wurde gefunden.

Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ssn"></a>Keyword_ssn

- Social Security 
- Social Security# 
- Soc Sec 
- SSN 
- Sozialversicherungsnummern 
- SSN # 
- SS # 
- SSID 
   
## <a name="us--uk-passport-number"></a>USA/U.K. passport number
Großbritannien Passport-Nummer vertraulicher Informationstyp Entität ist im vertraulichen Informationstyp EU-Passport-Nummer verfügbar und steht als eigenständige vertrauliche Informationstyp Entität zur Verfügung.

### <a name="format"></a>Format

Neun Ziffern

### <a name="pattern"></a>Muster

Neun aufeinanderfolgende Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport# 
- Pass # 
- Passport-Nr 
- Passportno 
- passportnumber 
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
