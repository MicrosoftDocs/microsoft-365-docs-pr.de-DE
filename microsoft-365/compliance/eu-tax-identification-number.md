---
title: EU-Steueridentifikationsnummer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-Steueridentifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591016"
---
# <a name="eu-tax-identification-number"></a>EU-Steueridentifikationsnummer

In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der vertraulichen Informationen für die EU-Steueridentifikationsnummer (TIN) erkennt. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
  
## <a name="austria"></a>Österreich

### <a name="format"></a>Format

Neun Ziffern mit optionalem Bindestrich und Schrägstrich
  
### <a name="pattern"></a>Muster

Neun Ziffern mit optionalem Bindestrich und Schrägstrich:
  
-  Zwei Ziffern 
    
- Ein Bindestrich (optional)
    
- Drei Ziffern
    
- Ein Schrägstrich (optional)
    
- Vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_austria_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

Steuernummer
  
number
  
Steuerregistrierungsnummer
  
tax id
  
St.Nr.
  
Steuernummer
  
## <a name="belgium"></a>Belgien

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

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_belgium_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_belgium_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

Steuernummer
  
nationale Registrierungsnummer
  
Steuerregistrierungsnummer
  
tax id
  
NIF
  
NIF #
  
Numéro de Registre National
  
Numéro d'identification Fiscale
  
## <a name="bulgaria"></a>Bulgarien

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_bulgaria_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number

BUCN
  
einheitliche Zivil Telefonnummer
  
BUCN #
  
uniformcivilnumber #
  
Uniform Civil ID
  
Uniform Civil Nein
  
EGN
  
Bulgarische Uniform Civil Number
  
uniformcivilno #
  
EGN #
  
униформ граждански номер
  
униформ-ID
  
униформ-граждански-ID
  
униформ граждански не
  
## <a name="croatia"></a>Kroatien

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
  
- Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_croatia_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

Steuernummer
  
Steuer
  
tax id
  
oid
  
OID #
  
porezni Broj
  
## <a name="cyprus"></a>Zypern

### <a name="format"></a>Format

Acht Ziffern und ein Buchstabe im angegebenen Muster
  
### <a name="pattern"></a>Muster

Acht Ziffern und ein Buchstabe:
  
-  A "0" 
    
- Sieben Ziffern 
    
- Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_cyprus_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

Steuernummer
  
Steuer
  
tax id
  
Steuer Identifikationscode
  
TIC
  
TIC #
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>Tschechien

### <a name="format"></a>Format

Neun oder zehn Ziffern mit einem optionalen Backslash
  
### <a name="pattern"></a>Muster

Neun oder zehn Ziffern mit einem optionalen backslashl:
  
- Sechs Ziffern 
    
- Ein Backslash (optional)
    
- Drei oder vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_czech_republic_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_czech_republic_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

Steuernummer
  
Steuer
  
tax id
  
persönliche Nummer
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>Dänemark

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
  
- Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_denmark_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

Steuernummer
  
Steuer
  
tax id
  
CPR-Nummer
  
CPR #
  
Skate Nummer
  
Skat-ID
  
## <a name="estonia"></a>Estland

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
  
- Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_estonia_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

Steuernummer
  
Steuer
  
tax id
  
persönlicher Code
  
maksunumber
  
maksu-ID
  
isikukood
  
## <a name="finland"></a>Finnland

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
  
- Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_finland_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

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
  
## <a name="france"></a>Frankreich

### <a name="format"></a>Format

13 Ziffern für einzelne Personen und neun Ziffern für Entitäten
  
### <a name="pattern"></a>Muster

13 Ziffern für einzelne Personen:
  
- Eine Ziffer, die 0, 1, 2 oder 3 sein muss
    
- 12 Ziffern
    
Neun Ziffern für Entitäten
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_france_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

Steueridentifikationsnummer
  
Steuernummer
  
tax id
  
Numéro d'identification Fiscale
  
## <a name="germany"></a>Deutschland

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
  
- Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_germany_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
Steuernummer
  
Ingo-ID
  
steueridentifikationsnummer
  
## <a name="greece"></a>Griechenland

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_greece_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_greece_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

AFM
  
Zinn
  
USt-IdNr.
  
Steuernummer Nr.
  
Steueridentifikationsnummer
  
Steuerregistrierungsnummer
  
Steuerregistrierungsnummer
  
AFM #
  
Zinn #
  
taxidno #
  
taxregistryno #
  
αριθμός φορολογικού μητρώου
  
aφμ
  
aφμ αριθμός
  
φορολογικού μητρώου νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>Ungarn

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
  
- Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_hungary_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

ungarische Steueridentifikationsnummer
  
Ungarisch Zinn
  
USt-ID-Nummer
  
USt-IdNr.
  
Steuerbehörde Nein
  
USt-ID-Steueridentifikationsnummer
  
taxidnumber #
  
Zinn #
  
hungatiantin #
  
Steueridentifikationsnummer
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irland

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Buchstaben ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Buchstaben:
  
-  Sieben Ziffern  
    
- Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_ireland_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

öffentlicher Dienst Nein
  
persönlicher öffentlicher Dienst Nein
  
PPS Nein
  
persönlicher Dienst Nein
  
PPS-Dienst Nein
  
ppsno #
  
irische PPS Nein
  
publicserviceno #
  
persönliche öffentliche Dienstnummer
  
uimhir phearsanta seirbhíse poiblí
  
PPS-uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Italien

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
  
- Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_italy_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Geschäftscode
  
Geschäftsjahr
  
## <a name="latvia"></a>Lettland

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern im angegebenen Muster
  
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ) 
    
- Eine Ziffer, die dem Jahrhundert der Geburt entspricht, wobei "0" dem 19. Jahrhundert entspricht, "1" entspricht dem 20. Jahrhundert, und "2" entspricht dem 21. Jahrhundert
    
- Vier Ziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_latvia_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Litauen

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_lithuania_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
Steuernummer #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
mokesčių-ID
  
mokesčių Numeris
  
mokesčių identifikavimas Numeris
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern:
  
-  11 Ziffern 
    
- Zwei Prüfziffern
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_luxemburg_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
Steuernummer
  
Ingo-ID
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

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

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_malta_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
per Taxi #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
numru tat-Taxxa
  
ID tat-Taxxa
  
numru ta ' identifikazzjoni tat-Taxxa
  
## <a name="netherlands"></a>Niederlande

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_netherlands_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

niederländische Steueridentifikationsnummer
  
niederländische Steueridentifikation
  
niederländische Steueridentifikationsnummer
  
niederländische Steueridentifikation
  
Steueridentifikationsnummer
  
niederländische Steuernummer
  
niederländische Steueridentifikationsnummer
  
tax id
  
Steuer-ID #
  
Steuernummer
  
Steuernummer #
  
Steuer #
  
Zinn
  
Zinn #
  
Niederlande Tin
  
niederländische Zinn
  
Nederlands belasten identificatienummer
  
identificatienummer van belasten
  
identificatienummer-Belastungen
  
Nederlands belasten identificatie
  
Nederlands Belasting ID Nummer
  
Nederlands belastingnummer
  
BTW Nummer
  
Nederlandse belasten von identificatie
  
## <a name="poland"></a>Polen

### <a name="format"></a>Format

Elf Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Elf Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_poland_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIP
  
NIP #
  
tax id
  
Steuer-ID #
  
NIP-ID
  
NIP-ID #
  
Steueridentifikationsnummer
  
USt-ID-Nr.
  
USt-IdNr.
  
USt-IdNr.
  
vatno #
  
USt-ID
  
USt-ID #
  
Numer identyfikacji podatkowej
  
Polski Numer identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_portugal_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

Steuernummer
  
Steuer-Nr.
  
taxno #
  
taxnumber #
  
taxnumber
  
NIF
  
NIF #
  
numerisch-Geschäftsjahr
  
número de identificação Fiscal
  
## <a name="romania"></a>Rumänien

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_romania_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_romania_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

tax id
  
USt-ID-Nummer
  
Steuerdatei Nein
  
tax file number
  
Steuernummer
  
Steuernummer
  
per Taxi #
  
taxno #
  
ID-UL taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>Slowakei

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovakia_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_slovakia_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

tax id
  
USt-ID-Nummer
  
Tin-ID
  
Tin Nein
  
Slowakische Tin-ID
  
Zinn
  
Steuerdatei Nein
  
tax file number
  
Steuernummer
  
Steuernummer
  
per Taxi #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
Daňové číslo SÚBORU
  
## <a name="slovenia"></a>Slowenien

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_slovenia_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

tax id
  
USt-ID-Nummer
  
Tin-ID
  
Tin Nein
  
slowenische Tin-ID
  
Zinn
  
Steuerdatei Nein
  
tax file number
  
Steuernummer
  
Steuernummer
  
per Taxi #
  
taxno #
  
identifikacijska številka beim Davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>Spanien

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
  
- Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_spain_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

tax id
  
USt-ID-Nummer
  
CIF-ID
  
CIF Nein
  
spanische CIF-ID
  
CIF
  
Steuerdatei Nein
  
spanische CIF-Nummer
  
tax file number
  
Spanisch CIF Nein
  
Steuernummer
  
Steuernummer
  
per Taxi #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de Impuesto Corporativo
  
número de Identificación Fiscal
  
CIF-número
  
cifnúmero #
  
## <a name="sweden"></a>Schweden

### <a name="format"></a>Format

Zehn Ziffern und ein Symbol im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zehn Ziffern und ein Symbol:
  
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
    
- Pluszeichen, Minuszeichen oder Backslash
    
- Drei Ziffern, die die Identifikationsnummer eindeutig machen: 
    
  - Für Zahlen, die vor 1990 ausgegeben wurden, identifizieren die siebte und die achte Ziffer den Geburts Kreis oder den in der fremde geborenen Personen.
    
  - Die Ziffer in der neunten Position gibt das Geschlecht entweder ungerade für männliche oder sogar für weiblich an.
    
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_sweden_eu_tax_file_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

tax id
  
USt-IdNr.
  
USt-ID-Nummer
  
tax identification
  
Steueridentifikation #
  
Steuer-Nr.
  
Steuer #
  
per Taxi #
  
Steuerdatei
  
Steuerdatei-Nr.
  
persönliche ID-Nummer
  
Skate ID Nummer
  
skatt Identifikation
  
personnummer
  
## <a name="uk"></a>UK

### <a name="format"></a>Format

Unique Steuerzahler Referenz (UTR): 10 Ziffern ohne Leerzeichen und Trennzeichen
  
Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K. Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Muster

Unique Steuerzahler Referenz (UTR): 10 Ziffern
  
Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K. Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_uk_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_uk_eu_tax_file_number` aus wurde gefunden. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

tax id
  
USt-IdNr.
  
USt-ID-Nummer
  
tax identification
  
Steueridentifikation #
  
Steuer-Nr.
  
Steuer #
  
per Taxi #
  
Steuerdatei
  
Steuerdatei-Nr.
  
## <a name="see-also"></a>Siehe auch

[Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)

