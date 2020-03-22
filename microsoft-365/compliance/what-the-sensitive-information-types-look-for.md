---
title: Wonach die Typen von vertraulichen Informationen suchen
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
description: Die Verhinderung von Datenverlust (Data Loss &amp; Prevention, DLP) im Office 365 Security Compliance Center umfasst 80 Typen für vertrauliche Informationen, die Sie in ihren DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt.
ms.openlocfilehash: bd74551b7e8b2d659724a1222e115a479db76ec8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894301"
---
# <a name="what-the-sensitive-information-types-look-for"></a>Wonach die Typen von vertraulichen Informationen suchen

Die Verhinderung von Datenverlust (Data Loss &amp; Prevention, DLP) im Office 365 Security Compliance Center umfasst viele Arten von vertraulichen Informationen, die Sie in ihren DLP-Richtlinien verwenden können. Dieses Thema enthält eine Liste aller dieser vertraulichen Informationstypen und zeigt, was eine DLP-Richtlinie sucht, wenn sie den jeweiligen Typen erkennt. Ein vertraulicher Informationstyp wird durch ein Muster definiert, das durch einen regulären Ausdruck oder eine Funktion identifiziert werden kann. Darüber hinaus können auch belegende Hinweise wie Schlüsselwörter oder Prüfsummen zum Identifizieren eines Typs vertraulicher Informationen verwendet werden. Beim Auswertungsprozess können auch die Zuverlässigkeitsstufe und die Näherung herangezogen werden.
  
## <a name="aba-routing-number"></a>ABA Routing Number (US-Bankleitzahl)

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


### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="argentina-national-identity-dni-number"></a>Argentina National Identity (DNI) Number

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- Identität 
- Identification National Identity Card 
- DNI 
- Nic-nationales Personenregister 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>Australische Bankkontonummer

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
   
## <a name="australia-medical-account-number"></a>Australische Medical Account-Nummer

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

Eine DLP-Richtlinie ist zu 95 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_Australia_Medical_Account_Number wurde gefunden.
- Die Prüfsumme stimmt.

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_australian_medical_account_number findet Inhalte, die dem Muster entsprechen.
- Die Prüfsumme stimmt.

```xml
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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="australia-tax-file-number"></a>Australische Steuernummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_australia_tax_file_number"></a>Keyword_Australia_Tax_File_Number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

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

## <a name="belgium-national-number"></a>Belgien – Nationale Nummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- Identität
- Registrierung
- Identifizierung 
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
- Inschrift 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>Brazil CPF Number

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="brazil-legal-entity-number-cnpj"></a>Brasilien – Juristische Personennummer (CNPJ)

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
   
## <a name="brazil-national-id-card-rg"></a>	Brasilien – Personalausweis (RG)

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

Cédula de identidade Personalausweis National ID número de rregistro Registro de Iidentidade Registro Geral RG (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet) RIC (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung beachtet) 
   
## <a name="canada-bank-account-number"></a>Kanadische Bankkontonummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="canada-health-service-number"></a>Kanadische Health Service-Nummer

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
- Disability
      
## <a name="canada-passport-number"></a>Kanadische Reisepassnummer

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
   
## <a name="canada-personal-health-identification-number-phin"></a>Kanadische Personal Health Identification-Nummer (PHIN)

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="chile-identity-card-number"></a>	Chile Identity Card Number

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="china-resident-identity-card-prc-number"></a>	China (PRC) – Personalausweisnummer

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
   
## <a name="credit-card-number"></a>Kreditkartennummer

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

### <a name="keywords"></a>Schlüsselwörter

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
- date d’expiration
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
   
## <a name="croatia-identity-card-number"></a>	Kroatien – Personalausweisnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- Croatian identity card
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>	Croatia Personal Identification (OIB) Number

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- Personal Identification Number
- Osobni identifikacijski broj 
- OIB 

   
## <a name="czech-personal-identity-number"></a>Tschechische Personalausweisnummer

### <a name="format"></a>Format

Neun Ziffern mit optionalem Schrägstrich (altes Format) 10 Ziffern mit optionalem Schrägstrich (neues Format)

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
### <a name="keywords"></a>Schlüsselwörter

- Tschechische Personalausweisnummer
- Rodné číslo
   
## <a name="denmark-personal-identification-number"></a>	Dänemark – Persönliche Identifikationsnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- Personal Identification Number
- CPR
- Det Centrale Personregister
- Personnummer
   
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

### <a name="keywords"></a>Schlüsselwörter

Keine

   
## <a name="eu-debit-card-number"></a>EU Debit Card-Nummer

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

### <a name="keywords"></a>Schlüsselwörter

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

Weitere Informationen finden Sie unter [EU-Führerscheinnummer vertraulicher Informationstyp](eu-driver-s-license-number.md).
  
## <a name="eu-national-identification-number"></a>EU-nationale Identifikationsnummer

Weitere Informationen finden Sie unter [sensible Informationstypen für die nationale Identifikationsnummer der EU](eu-national-identification-number.md).
  
## <a name="eu-passport-number"></a>EU-Passport-Nummer

Weitere Informationen finden Sie unter [sensible Informationstypen für EU-Passport-Nummern](eu-passport-number.md).
  
## <a name="eu-social-security-number-or-equivalent-id"></a>EU-Sozialversicherungsnummer oder gleichwertige ID

Weitere Informationen finden Sie unter [EU-Sozialversicherungsnummer oder gleichwertiger ID-Typ für vertrauliche Informationen](eu-social-security-number-or-equivalent-id.md).
  
## <a name="eu-tax-identification-number"></a>EU-Steueridentifikationsnummer

Weitere Informationen finden Sie unter [vertraulicher Informationstyp der EU-Steueridentifikationsnummer](eu-tax-identification-number.md).
  
## <a name="finland-national-id"></a>Finland National ID (Finnischer Personalausweis)

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

### <a name="keywords"></a>Schlüsselwörter

- Keyword_finnish_national_id
- Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>Finnland – Ausweisnummer

Format Kombination von neun Buchstaben und Ziffern Muster Kombination aus neun Buchstaben und Ziffern: zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) siebenstellige Prüfsumme keine Definition eine DLP-Richtlinie ist 75% zuversichtlich, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb eines Proximity of 300 Characters: der reguläre Ausdruck Regex_finland_passport_number findet Inhalte, die mit dem Muster übereinstimmen.
Ein Schlüsselwort aus Keyword_finland_passport_number wurde gefunden.
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity>
Schlüsselwörter Keyword_finland_passport_number Passport Passi
   
## <a name="france-drivers-license-number"></a>Französische Führerscheinnummer

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

### <a name="keywords"></a>Schlüsselwörter

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

## <a name="france-national-id-card-cni"></a>Französische Carte nationale d'identité (CNI)

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

### <a name="keywords"></a>Schlüsselwörter

Keine
   
## <a name="france-passport-number"></a>Französische Reisepassnummer

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

### <a name="keywords"></a>Schlüsselwörter

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

      
## <a name="france-social-security-number-insee"></a>Französische Sozialversicherungsnummer (INSEE)

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="german-drivers-license-number"></a>Deutsche Führerscheinnummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="german-passport-number"></a>Deutsche Reisepassnummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="germany-identity-card-number"></a>Deutsche Personalausweisnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- Identity Card
- ID
- Identifizierung
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>Griechenland – Personalausweis

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

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- Greek identity Card
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## <a name="hong-kong-identity-card-hkid-number"></a>Hongkong (HKID) - Personalausweisnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

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
   
## <a name="india-permanent-account-number-pan"></a>Indien – Permanente Kontonummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- Schwenken 
   
## <a name="india-unique-identification-aadhaar-number"></a>Indien - Eindeutige Identifikationsnummer (Aadhaar)

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
### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Indonesien – Perosonalausweisnummer (KTP)

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

### <a name="keywords"></a>Schlüsselwörter
   
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

AD, AE, Al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, Do, EE, es, fi, FO, Fr, GB, ge, GI, GL, GR, HR, HU, IE, IL, is, IT, kW, KZ, LB, Li, lt, LU, LV, MC, MD, me, MK, Mr, MT, mu , NL, No, PL, PT, RO, RS, Sa, SE, Si, SK, SM, TN, TR, VG

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

### <a name="keywords"></a>Schlüsselwörter

Keine

   
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (bei diesem Schlüsselwort wird die Groß-/Kleinschreibung unterschieden)
- ip address 
- IP-Adressen
- internet protocol
- IP-כתובת ה 
   
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

Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

Ein beliebiger Ausdruck aus dem Dictionary_icd_9_updated Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Dieser Typ sucht nur nach dem Begriff, nicht nach den Versicherungs Codes.

Ein beliebiger Ausdruck aus dem Dictionary_icd_9_codes Keyword-Wörterbuch, das auf der [internationalen Klassifikation von Krankheiten basiert, neunte Revision, klinische Änderung (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Dieser Typ sucht nur nach Versicherungs Codes, nicht nach der Beschreibung.

## <a name="ireland-personal-public-service-pps-number"></a>Irland – Personal Public Service-Nummer (PPS)

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="israel-bank-account-number"></a>Israelische Bankkontonummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-id"></a>Israelische Ausweis-ID

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Italienische Führerscheinnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 
   
## <a name="japan-bank-account-number"></a>Japanische Bankkontonummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="japan-passport-number"></a>Japanische Reisepassnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
   
## <a name="japan-resident-registration-number"></a>Japanische Einwohnerregistrierungsnummer

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

### <a name="keywords"></a>Schlüsselwörter

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

   
## <a name="japan-social-insurance-number-sin"></a>Japanische Sozialversicherungsnummer (SIN)

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="japanese-residence-card-number"></a>Japanische Residenz Kartennummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Wohnsitz Kartennummer
- Residenzkarte Nein
- Aufenthaltskarte #
- 在留カード番号
   
## <a name="malaysia-id-card-number"></a>Malaysia -ID-Kartennummer

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

### <a name="keywords"></a>Schlüsselwörter
   
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
   
## <a name="netherlands-citizens-service-bsn-number"></a>Niederlande – Bürgerdienstnummer (BSN)

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_netherlands_bsn"></a>Keyword_netherlands_bsn

- Citizen service number 
- BSN 
- Burgerservicenummer 
- Sofinummer 
- Persoonsgebonden nummer 
- Persoonsnummer    

   
## <a name="new-zealand-ministry-of-health-number"></a>Neuseeländische Gesundheitsministeriumsnummer

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

Schlüsselwörter

Keyword_nz_terms

- Nhi 
- New Zealand 
- Gesundheitswesen 
- Behandlung 
   
## <a name="norway-identification-number"></a>Norwegen – Identifikationsnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Identifizierung
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>Philippinen – Vereinheitlichte Mehrzweck-ID-Nummer

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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- Umid 
- Identity Card 
- Pinag-isang Multi-Layunin ID
   
## <a name="poland-identity-card"></a>Polen Personalausweis

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i Numer dowodu osobistego
- Nazwa i Nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. OS.

   
## <a name="poland-national-id-pesel"></a>Polnische ID-Karte (PESEL)

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- Nr PESEL
- PESEL   

   
## <a name="poland-passport"></a>Polen Reisepass

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_polish_national_id_passport_number"></a>Keyword_polish_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

   
## <a name="portugal-citizen-card-number"></a>Portugal – Bürgerkartennummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- Citizen Card
- National ID Card
- CC
- Cartão de Cidadão
- Bilhete de Identidade
   
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Singapur – National Registration Identity Card-Nummer (NRIC)

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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- IK 
- Foreign Identification Number 
- FIN 
- 身份证 
- 身份證 
   
## <a name="south-africa-identification-number"></a>Südafrika – Identifikationsnummer

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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Identifizierung 
   
## <a name="south-korea-resident-registration-number"></a>Südkorea – Einwohnerregistrierungsnummer

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

### <a name="keywords"></a>Schlüsselwörter
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호
   
## <a name="spain-social-security-number-ssn"></a>Spanische Sozialversicherungsnummer (SSN)

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

### <a name="keywords"></a>Schlüsselwörter

Keine

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

### <a name="keywords"></a>Schlüsselwörter

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

## <a name="sweden-national-id"></a>Schwedische Ausweisnummer

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

### <a name="keywords"></a>Schlüsselwörter

Nein
   
## <a name="sweden-passport-number"></a>Schwedische Reisepassnummer

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
   
## <a name="swift-code"></a>SWIFT-Code

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

### <a name="keywords"></a>Schlüsselwörter
   
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
   
## <a name="taiwan-national-id"></a>Taiwanesicher Personalausweis

### <a name="format"></a>Format

Ein Buchstabe (auf Englisch) gefolgt von neun Ziffern

### <a name="pattern"></a>Muster

Ein Buchstabe (Englisch), gefolgt von neun Ziffern:
- Ein Buchstabe (Englisch, Groß-/Kleinschreibung wird nicht beachtet) 
- Die Ziffer 1 oder 2 
- Acht Ziffern

### <a name="checksum"></a>Prüfsumme

Ja

### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
- Die Funktion Func_taiwanese_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_taiwanese_national_id wurde gefunden.
- Die Prüfsumme stimmt.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="taiwan-passport-number"></a>	Taiwan – Reisepassnummer

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
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Taiwan – Einwohnerzertifikatsnummer (ARC/TARC)

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

## <a name="thai-population-identification-code"></a>Thai-Populations Kennzeichnungs Code

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

### <a name="keywords"></a>Schlüsselwörter

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_turkish_national_id"></a>Keyword_Turkish_National_Id

- TC KİMLİK Nein
- TC KİMLİK numarası
- Vatandaşlık numarası
- Vatandaşlık Nein

## <a name="uk-drivers-license-number"></a>Britische Führerscheinnummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="uk-electoral-roll-number"></a>Britische Wählerverzeichnisnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Britische National Health Service-Nummer

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

### <a name="keywords"></a>Schlüsselwörter
   
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
   
## <a name="uk-national-insurance-number-nino"></a>Britische nationale Versicherungsnummer (NINO)

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

### <a name="keywords"></a>Schlüsselwörter

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
- social security 
- great britain 
- Versicherungs    
   
## <a name="us--uk-passport-number"></a>US-amerikanische/britische Reisepassnummer

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="us-bank-account-number"></a>US-Bankkontonummer

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
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>US-Steueridentifikationsnummer (ITIN)

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

### <a name="keywords"></a>Schlüsselwörter

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
   
## <a name="us-social-security-number-ssn"></a>US-Sozialversicherungsnummer

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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_ssn"></a>Keyword_ssn

- Social Security 
- Social Security# 
- Soc Sec 
- SSN 
- Sozialversicherungsnummern 
- SSN # 
- SS # 
- SSID 
   
