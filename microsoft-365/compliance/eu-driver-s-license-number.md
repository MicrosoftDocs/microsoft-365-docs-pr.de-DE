---
title: EU-Führerscheinnummer
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805958"
---
# <a name="eu-drivers-license-number"></a>EU-Führerscheinnummer

In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
  
## <a name="austria"></a>Österreich

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_austria_eu_driver's_license_number` aus wurde gefunden. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_austria_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/>  Führerscheinnummer  <br/> dlno #  <br/> fuhrerschein  <br/> Fuhrerschein Republik Osterreich  <br/> |
   
## <a name="belgium"></a>Belgien

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_belgium_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords__belgium_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> Führerschein-Nr  <br/> Fuehrerschein-Nr  <br/> Fuehrerschein-Nr  <br/> |
   
## <a name="bulgaria"></a>Bulgarien

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_bulgaria_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_bulgaria_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>Kroatien

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_croatia_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_croatia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>Zypern

### <a name="format"></a>Format

12 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

12 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_cyprus_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_cyprus_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>Tschechien

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
    
- Ein Schlüsselwort `Keywords_czech_republic_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_czech_republic_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Dänemark

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern
  
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_denmark_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_denmark_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estland

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
    
- Ein Schlüsselwort `Keywords_estonia_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_estonia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>Finnland

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
    
- Ein Schlüsselwort `Keywords_finland_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_finland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>Frankreich

Ausführliche Informationen finden Sie im Abschnitt "französische Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Deutschland

Ausführliche Informationen finden Sie im Abschnitt "Deutsche Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Griechenland

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Neun Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_greece_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_greece_eu_driver ' s_license_number**|
|:-----|
|dlL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Ungarn

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sechs Ziffern
  
### <a name="pattern"></a>Muster

Zwei Buchstaben und sechs Ziffern:
  
-  Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
    
- Sechs Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_hungary_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_hungary_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irland

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
    
- Ein Schlüsselwort `Keywords_ireland_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_ireland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Italien

Ausführliche Informationen finden Sie im Abschnitt "Italien-Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Lettland

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
    
- Ein Schlüsselwort `Keywords_latvia_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_latvia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Litauen

### <a name="format"></a>Format

Acht Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Acht Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_lithuania_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_lithuania_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> Vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Format

Sechs Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

 Sechs Ziffern 
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_luxemburg_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_luxemburg_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

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
    
- Ein Schlüsselwort `Keywords_malta_eu_driver's_license_number` aus wurde gefunden. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_malta_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> Liċenzja TAS-Sewqan  <br/> |
   
## <a name="netherlands"></a>Niederlande

### <a name="format"></a>Format

10 Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

10 Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_netherlands_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_netherlands_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polen

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
    
- Ein Schlüsselwort `Keywords_poland_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_poland_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> Prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portugal

### <a name="format"></a>Format

Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster
  
### <a name="pattern"></a>Muster

Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:
  
-  Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet) 
    
- Ein Bindestrich 
    
- Sechs Ziffern
    
- Ein Leerzeichen
    
- Eine Ziffer
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_portugal_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_portugal_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> Carteira de motorista  <br/> |
   
## <a name="romania"></a>Rumänien

### <a name="format"></a>Format

Ein Zeichen gefolgt von acht Ziffern
  
### <a name="pattern"></a>Muster

Ein Zeichen gefolgt von acht Ziffern:
  
-  Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern 
    
- Acht Ziffern
    
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_romania_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_romania_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>Slowakei

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
    
- Ein Schlüsselwort `Keywords_slovakia_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_slovakia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Slowenien

### <a name="format"></a>Format

Neun Ziffern ohne Leerzeichen und Trennzeichen
  
### <a name="pattern"></a>Muster

Neun Ziffern
  
### <a name="checksum"></a>Prüfsumme

Nein
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_slovenia_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_slovenia_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>Spanien

### <a name="format"></a>Format

Acht Ziffern, gefolgt von einem Zeichen
  
### <a name="pattern"></a>Muster

Acht Ziffern, gefolgt von einem Zeichen:
  
-  Acht Ziffern 
    
- Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)
    
### <a name="checksum"></a>Prüfsumme

Ja
  
### <a name="definition"></a>Definition

Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:
  
- Die- `Func_spain_eu_driver's_license_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen. 
    
- Ein Schlüsselwort `Keywords_spain_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_spain_eu_driver ' s_license_number**|
|:-----|
|dlno #  <br/> DL #  <br/> Treiber lic.  <br/> Treiber Lizenz  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> Führerschein  <br/> driving license  <br/> Führerscheinnummer  <br/> Treiber Lizenznummer  <br/> Führerscheinnummer  <br/> Lizenznummer für Treiber  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerschein  <br/> Führerscheinnummer  <br/> Permiso de conducción  <br/> permiso conducción  <br/> número licencia Conducir  <br/> número de carnet de Conducir  <br/> número Carnet Conducir  <br/> licencia Conducir  <br/> número de Permiso de Conducir  <br/> número de Permiso Conducir  <br/> número Permiso Conducir  <br/> Permiso Conducir  <br/> licencia de Manejo  <br/> El Carnet de Conducir  <br/> Carnet Conducir  <br/> |
   
## <a name="sweden"></a>Schweden

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
    
- Ein Schlüsselwort `Keywords_sweden_eu_driver's_license_number` aus wurde gefunden. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Schlüsselwörter

| |
|**Keywords_sweden_eu_driver ' s_license_number**|
|:-----|
|DL #  <br/> driver license  <br/> Treiber Lizenznummer  <br/> Treiber Lizenz  <br/> Treiber lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> Führerscheinnummer  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>UK

Ausführliche Informationen finden Sie im Abschnitt "U.K. Nummer des Führerscheins "in [dem, wonach die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Siehe auch

[Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)

