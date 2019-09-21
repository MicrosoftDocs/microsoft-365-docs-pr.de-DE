---
title: EU-nationale Identifikationsnummer
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-nationale Identifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: cbcacb3f85877f5a84238468fb52d612d90f5f0b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081475"
---
# <a name="eu-national-identification-number"></a>EU-nationale Identifikationsnummer

In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-nationale Identifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
  
## <a name="austria"></a>Österreich

### <a name="format"></a>Format

Eine Kombination aus Buchstaben, Ziffern und Sonderzeichen mit einer 24 Zeichen Länge
  
### <a name="pattern"></a>Muster

24 Zeichen:
  
-  22 Buchstaben (Unterscheidung nach Groß-/Kleinschreibung), Ziffern, umgekehrte Schrägstriche oder Pluszeichen 
    
- Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet), Ziffern, Backslashes, Schrägstriche, Pluszeichen oder gleich Zeichen
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_austria_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_austria_eu_national_id_card` aus wurde gefunden. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

Österreichische Identitätsnummer
  
nationale Identitätsnummer
  
Identitätsnummer
  
national id
  
Personalausweis Republik Österreich
  
## <a name="belgium"></a>Belgien

Ausführliche Informationen finden Sie im Abschnitt "belgische nationale Nummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgarien

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
    
- Zwei Ziffern, die der Geburts Reihenfolge entsprechen
    
- Eine Ziffer, die dem Geschlecht entspricht: eine gerade Ziffer für "männlich" und eine ungerade Ziffer für "weiblich".
    
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_bulgaria_national_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_bulgaria_national_number` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_bulgaria_national_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

EGN
  
EGN #
  
Bulgarische Nationale Nummer
  
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
  
единен граждански номер
  
edinen grazhdanski Nomen
  
егн
  
егн #
  
## <a name="croatia"></a>Kroatien

Ausführliche Informationen finden Sie im Abschnitt "kroatische Identitätsnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Zypern

### <a name="format"></a>Format

Zehn Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Zehn Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_cyprus_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_cyprus_eu_national_id_card` aus wurde gefunden. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

ID-Kartennummer
  
national identification number
  
persönliche ID-Nummer
  
Personalausweisnummer
  
ταυτοτητασ
  
## <a name="czech-republic"></a>Tschechien

Ausführliche Informationen finden Sie im Abschnitt "Tschechische Nationale Identitätsnummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Dänemark

Ausführliche Informationen finden Sie im Abschnitt "dänische persönliche Identifikationsnummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estland

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
  
- Die- `Func_estonia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_estonia_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_estonia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

persönlicher Identifikationscode
  
persönliche Identifikationsnummer
  
national identification number
  
nationale Nummer
  
persönliche ID-Nummer
  
personalidnumber #
  
IK
  
isikukood
  
ID-Kaart
  
## <a name="finland"></a>Finnland

Ausführliche Informationen finden Sie im Abschnitt "finnische nationale ID" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Frankreich

Ausführliche Informationen finden Sie im Abschnitt "France National ID Card (CNI)" in [What the sensitive Information Types Look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Deutschland

Ausführliche Informationen finden Sie im Abschnitt "Deutsche Identitätskartennummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Griechenland

Ausführliche Informationen finden Sie im Abschnitt "Griechenland-National Ausweis" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungarn

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
  
- Die- `Func_hungary_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_hungary_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_hungary_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

persönliche Identifikationsnummer
  
identification number
  
persönliche ID-Nummer
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irland

### <a name="format"></a>Format

Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster
  
### <a name="pattern"></a>Muster

Eine neunstellige Kombination aus Buchstaben, Ziffern und einem Leerzeichen im angegebenen Muster
  
Vom 01 Januar 2013 bis jetzt:
  
-  Sieben Ziffern  
    
- Eine Prüfziffer
    
- Ein Leerzeichen oder der Großbuchstabe "W" (Groß-/Kleinschreibung)
    
Vor dem 01. Januar 2013:
  
-  Sieben Ziffern  
    
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
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

persönliche öffentliche Dienstnummer
  
PPS Nein
  
Umsatz-und Sozialversicherungsnummer
  
RSI-Nr.
  
persönliche Identifikationsnummer
  
identification number
  
persönliche ID-Nummer
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Italien

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
  
- Die- `Func_italy_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_italy_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_italy_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

persönlicher Code
  
persönliche Codenummer
  
persönliche Zertifikat Nummer
  
Geschäftscode
  
personalcodeno #
  
persönliche ID-Nummer
  
persönlicher ID-Code
  
Dice personale
  
Numero Bescheinigung personale
  
Numero personale
  
Numero-ID personale
  
Dice ID personale
  
Geschäftsjahr
  
## <a name="latvia"></a>Lettland

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
  
- Die- `Func_latvia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_latvia_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_latvia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

persönlicher Code
  
persönliche Codenummer
  
persönliche Zertifikat Nummer
  
personalcodeno #
  
persönliche ID-Nummer
  
persönlicher ID-Code
  
Personas KODS
  
## <a name="lithuania"></a>Litauen

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern ohne Leerzeichen und Trennzeichen:
  
- Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht
    
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
    
- Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
    
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_lithuania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_lithuania_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_lithuania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

persönlicher numerischer Code
  
eindeutige Identifikationsnummer
  
Bürgerdienst Nummer
  
eindeutige Identitätsnummer
  
uniqueidentityno #
  
persönlicher Code.
  
asmeninis skaitmeninis KODAS
  
unikalus identifikavimo Numeris
  
piliečio paslaugos Numeris
  
unikalus identifikavimo KODAS
  
Mens KODAS.
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Format

11 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

11 Ziffern
  
- Eine Ziffer, die dem Geschlecht der Person und dem Jahrhundert der Geburt entspricht
    
-  Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT) 
    
- Drei Ziffern, die der Seriennummer des Geburtsdatums entsprechen
    
- Eine Prüfziffer
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_luxemburg_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_luxemburg_eu_national_id_card` aus wurde gefunden. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

persönliche ID
  
persönliche ID-Nummer
  
personalidno #
  
eindeutige ID-Nummer
  
personalidnumber #
  
eindeutiger ID-Schlüssel
  
persönlicher ID-Code
  
uniqueidkey #
  
einzelner Code
  
individuelle ID
  
eindeutige-ID-Nummer
  
eindeutige-ID
  
ID personnelle
  
Numéro-d'identification-Mitarbeiter
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Buchstaben
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Buchstaben:
  
-  Sieben Ziffern  
    
- Ein Großbuchstabe (Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_malta_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_malta_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

persönlicher numerischer Code
  
eindeutige Identifikationsnummer
  
Bürgerdienst Nummer
  
eindeutige Identitätsnummer
  
uniqueidentityno #
  
Kodiċi Numeri personali
  
numru ta ' identifikazzjoni uniku
  
numru TAS-servizz taċ-ċittadin
  
numru ta ' identità uniku
  
## <a name="netherlands"></a>Niederlande

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen oder Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_netherlands_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort aus wurde gefunden.
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_netherlands_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

persönlicher numerischer Code
  
eindeutige Identifikationsnummer
  
Bürgerdienst Nummer
  
eindeutige Identitätsnummer
  
uniqueidentityno #
  
BSN
  
BSN #
  
Persoonlijke-numerieke-Code
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>Polen

Ausführliche Informationen finden Sie im Abschnitt "Poland National ID (PESEL)" in [What the sensitive Information Types Look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

Ausführliche Informationen finden Sie im Abschnitt "Portugal-Bürgerkarten Nummer" unter [was die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Rumänien

### <a name="format"></a>Format

13 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

13 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_romania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_romania_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_romania_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

persönlicher numerischer Code
  
eindeutige Identifikationsnummer
  
CNP
  
CNP #
  
PIN
  
PIN #
  
Versicherungsnummer
  
insurancenumber #
  
eindeutige Identitätsnummer
  
uniqueidentityno #
  
COD numerisch persönlich
  
COD identificare Personal
  
COD Unic identificare
  
număr Personal Unic
  
număr identitate
  
număr identificare Personal
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Slowakei

### <a name="format"></a>Format

Zehn Ziffern mit einem Backslash
  
### <a name="pattern"></a>Muster

Zehn Ziffern mit einem Backslash:
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_slovakia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_slovakia_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_slovakia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

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
  
## <a name="slovenia"></a>Slowenien

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
  
- Die- `Func_slovenia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_slovenia_eu_national_id_card` aus wurde gefunden. 
    
Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_slovenia_eu_national_id_card` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
```
 
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

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

persönlicher numerischer Code
  
eindeutige Identifikationsnummer
  
eindeutige Registrierungsnummer
  
eindeutige Identitätsnummer
  
uniqueidentityno #
  
eindeutige Master Bürgerzahl
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
EMŠO
  
## <a name="spain"></a>Spanien

### <a name="format"></a>Format

Sieben Ziffern, gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

Sieben Ziffern, gefolgt von einem Zeichen
  
- Sieben Ziffern 
    
- Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Nicht zutreffend
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_spain_eu_national_id_card` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_spain_eu_national_id_card"` aus wurde gefunden. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

DNI
  
national identification number
  
nationale Identitätsnummer
  
Versicherungsnummer
  
persönliche Identifikationsnummer
  
nationale Identität
  
persönliche Identität Nein
  
eindeutige Identitätsnummer
  
nationalidno #
  
UniqueId #
  
DNI #
  
National-Nr. #
  
nie #
  
nie
  
nienúmero #
  
nie número
  
Documento Nacional de Identidad
  
Identidad Único
  
número Nacional Identidad
  
DNI número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Schweden

Ausführliche Informationen finden Sie im Abschnitt "Sweden National ID" unter [What the sensitive Information Types Look](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Siehe auch

[Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)

