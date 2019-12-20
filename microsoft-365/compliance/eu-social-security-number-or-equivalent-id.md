---
title: EU-Sozialversicherungsnummer oder gleichwertige ID
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie die Sozialversicherungsnummer der EU oder einen entsprechenden ID-vertraulichen Informationstyp ermittelt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 0666818dc892070f5c2f0c34abd8ca33d1253e33
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805928"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>EU-Sozialversicherungsnummer oder gleichwertige ID

In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der EU-Sozialversicherungsnummer (SSN) oder einen äquivalenten ID-vertraulichen Informationstyp erkennt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
  
## <a name="austria"></a>Österreich

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
  
- Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_austria_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_austria_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

Sozialversicherungsnummer
  
social security number
  
social security code
  
Versicherungsnummer
  
Österreichische SSN
  
SSN #
  
SSN
  
versicherungscode
  
versicherungscode #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale Sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>Belgien

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_belgium_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_belgium_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

belgische nationale Nummer
  
nationale Nummer
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
nationalnumber
  
BNN #
  
BNN
  
persönliche ID-Nummer
  
personalidnumber #
  
Numéro National
  
numéro de sécurité
  
Numéro d'assuré
  
identifizierbare nationale
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>Kroatien

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
  
- Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_croatia_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_croatia_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

persönliche Identifikationsnummer
  
Bürgermeister Nummer
  
national identification number
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
nationalnumber
  
BNN #
  
BNN
  
persönliche ID-Nummer
  
personalidnumber #
  
OIB
  
Osobni identifikacijski Broj
  
## <a name="czech-republic"></a>Tschechien

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
  
- Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_czech_republic_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_czech_republic_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

Geburtsnummer
  
national identification number
  
persönliche Identifikationsnummer
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
nationale Nummer
  
persönliche ID-Nummer
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="denmark"></a>Dänemark

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
  
- Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_denmark_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_denmark_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

persönliche Identifikationsnummer
  
national identification number
  
social security number
  
nationalnumber #
  
SSN #
  
SSN
  
nationale Nummer
  
persönliche ID-Nummer
  
personalidnumber #
  
CPR-Nummer
  
personnummer
  
## <a name="finland"></a>Finnland

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
  
- Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_finland_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_finland_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number
  
persönliche ID
  
Identitätsnummer
  
Finnische Nationale ID-Nummer
  
personalidnumber #
  
national identification number
  
ID-Nummer
  
nationale ID-Nr.
  
nationale ID-Nummer
  
ID Nein
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
Suomen der Kok henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
der Kok tunnus numero
  
Hetu
  
## <a name="france"></a>Frankreich

Ausführliche Informationen finden Sie im Abschnitt "französische Sozialversicherungsnummer (INSEE)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Deutschland

Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Griechenland

Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungarn

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_hungary_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_hungary_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

ungarische Sozialversicherungsnummer
  
social security number
  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
Taj
  
Taj #
  
SSN
  
SSN #
  
Sozialversicherungsnummer
  
ÁFA
  
közösségi adószám
  
Általános forgalmi adó szám
  
hozzáadottérték adó
  
ÁFA szám
  
Magyar ÁFA szám
  
## <a name="portugal"></a>Portugal

Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>Spanien

Ausführliche Informationen finden Sie im Abschnitt "Spanien Sozialversicherungsnummer (SSN)" in [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Schweden

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
  
- Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_sweden_eu_ssn_or_equivalent` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_sweden_eu_ssn_or_equivalent` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

persönliche ID-Nummer
  
identification number
  
persönliche ID Nein
  
Identität Nein
  
Identifikationsnummer
  
persönliche Identifikationsnummer
  
PERSONNUMMER-ID
  
personligt-ID-Nummer
  
unikt-ID-Nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>Siehe auch

[Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)

