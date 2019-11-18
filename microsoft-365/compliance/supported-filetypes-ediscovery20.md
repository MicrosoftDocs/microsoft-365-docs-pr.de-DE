---
title: Unterstützte Dateitypen in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 5f574fa4fa53e83e2af4ea563c63106e8206c3d5
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "38686019"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Unterstützte Dateitypen in Advanced eDiscovery

Advanced eDiscovery unterstützt viele Dateitypen in vielen verschiedenen Ebenen, die in der folgenden Tabelle beschrieben werden. Diese Liste ist nicht abgeschlossen, und wir werden neue Dateitypen hinzufügen, während wir unsere Validierungstests fortsetzen. In den Tabellen wird angegeben, ob ein Dateityp für die Textextraktion (OCR für Bilder) unterstützt wird, der im Native Viewer angezeigt wird und auch im Annotations-Viewer in Advanced eDiscovery unterstützt wird.


## <a name="archive--container"></a>Archiv/Container

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Container Extraktion | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |
| Application/x-7z-komprimiert | Ja | Ja | Ja | .7z |
| Application/x-rar-komprimiert | Ja | Ja | Ja | . rar |
| Anwendung/x-tar | Ja | Ja | Ja | . tar |
| Anwendung/zip | Ja | Ja | Ja | .ZIP |
||||||||

## <a name="audio--video"></a>Audio/Video

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Anwendung/MP4 | Ja | Ja | Nein | Ja | Nein | . F4V;. m4a;. m4v;. MP4;. MP4V;. MPEG;. MPEG4 |
| Audio/MPEG | Ja | Ja | Nein | Ja | Nein | . MPEG |
| Video/3GPP | Ja | Ja | Nein | Ja | Nein | .3GP |
| Video-3GPP2 | Ja | Ja | Nein | Ja | Nein | .3G2;. 3gp2 |
| Video/QuickTime | Ja | Ja | Nein | Ja | Nein | . mov;. mov;. Qt |
| Video/x-m4v | Ja | Ja | Nein | Ja | Nein | . m4v |
||||||||

## <a name="database"></a>Datenbank

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/x-Msaccess | Ja | Ja | Ja | Nein | Nein | MDB |
||||||||

## <a name="email"></a>E-Mail

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Outlook | Ja | Ja | Ja | Ja | Ja | . msg |
| Nachricht/RFC822 | Ja | Ja | Ja | Ja | Ja | .EML |
| Text/vCard-Kontakt | Ja | Ja | Ja | Ja | Ja | . vcf |
||||||||

## <a name="email-container"></a>E-Mail-Container

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Container Extraktion | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |
| Anwendung/mbox | Ja | Ja | Ja | . mbox |
| application/vnd. MS-Outlook-PST | Ja | Ja | Ja | PST-Datei |
||||||||

## <a name="html"></a>HTML

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/XHTML + XML | Ja | Ja | Ja | Ja | Ja | . XHTML |
| Application/XML | Ja | Ja | Ja | Ja | Ja | . XML |
| Text/HTML | Ja | Ja | Ja | Ja | Ja | . htm;. html;. shtml |
||||||||

## <a name="image"></a>Image

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | OCR-Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Bild/BMP | Ja | Ja | Ja | Ja | Ja | BMP |
| Bild/EMF | Ja | Ja | Ja | Ja | Ja | . EMF |
| image/gif | Ja | Ja | Ja | Ja | Ja | .gif |
| image/jpeg | Ja | Ja | Ja | Ja | Ja | JPEG, JPG |
| image/png | Ja | Ja | Ja | Ja | Ja | .png |
| Image/SVG + XML | Ja | Ja | Ja | Ja | Nein | . svg |
| Bild/TIFF | Ja | Ja | Ja | Ja | Ja | TIF |
| Image/vnd. DWG | Ja | Ja | Ja | Ja | Ja | . dwg;. DXF |
| Image/WMF | Ja | Ja | Ja | Ja | Ja | . WMF |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Excel | Ja | Ja | Ja | Ja | Ja | . dat;. xls |
| application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Ja | Ja | Ja | Ja | Nein | . xlsb |
| application/vnd. MS-Excel. Sheet. macroenabled. 12 | Ja | Ja | Ja | Ja | Ja | . xlsm |
| application/vnd. MS-Excel. Template. macroenabled. 12 | Ja | Ja | Ja | Nein | Nein | . xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Ja | Ja | Ja | Ja | Ja | xlsx |
| application/vnd. openxmlformats-officeDocument. SpreadsheetML. Template | Ja | Ja | Ja | Ja | Ja | . xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Anwendung/OneNote | Ja | Ja | Ja | Ja | Nein | . eine |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-PowerPoint | Ja | Ja | Ja | Ja | Ja | . Pot;. PPS;. ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Ja | Ja | Ja | Ja | Ja | PPTX |
| application/vnd. openxmlformats-officeDocument. PresentationML. Slideshow | Ja | Ja | Ja | Ja | Ja | . ppsx |
| application/vnd. openxmlformats-officeDocument. PresentationML. Template | Ja | Ja | Ja | Ja | Ja | . POTX |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Project | Ja | Ja | Ja | Nein | Ja | MPP |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/x-mspublisher | Ja | Ja | Ja | Ja | Ja | . pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Visio. Drawing | Ja | Ja | Ja | Ja | Nein |  |
| application/vnd. Visio | Ja | Ja | Ja | Ja | Ja | VSD |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | Ja | Ja | Ja | Ja | Ja | . dat;. doc |
| Application/RTF | Ja | Ja | Ja | Ja | Ja | . doc;. RTF |
| application/vnd. MS-Word. Document. macroenabled. 12 | Ja | Ja | Ja | Ja | Ja | DOCM |
| application/vnd. MS-Word. Template. macroenabled. 12 | Ja | Ja | Ja | Ja | Ja | . dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Ja | Ja | Ja | Ja | Ja | DOCX |
| application/vnd. openxmlformats-officeDocument. WordprocessingML. Template | Ja | Ja | Ja | Ja | Ja | . dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Works-SS | Ja | Ja | Nein | Nein | Nein | WPS |
| application/vnd. MS-Works-WP | Ja | Ja | Nein | Nein | Nein | WPS |
||||||||

## <a name="open-document-format"></a>Dokument Format öffnen

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. Oasis. OpenDocument. Text | Ja | Ja | Ja | Ja | Ja | ODT |
||||||||

## <a name="other"></a>Andere

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | Ja | Ja | Ja | Ja | Ja | n/v |
| application/vnd. MS-Graph | Ja | Ja | Nein | Nein | Nein |  |
| Application/winhlp | Ja | Ja | Nein | Nein | Nein | HLP |
| Application/x-TNEF | Ja | Ja | Nein | Nein | Nein |  |
||||||||

## <a name="plain-text"></a>Nur-Text

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Text/CSV | Ja | Ja | Ja | Ja | Ja | . CSV |
| text/plain | Ja | Ja | Ja | Ja | Ja | . con;. CSS;. CSV;. dat;. pl;. txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | Ja | Ja | Ja | Ja | Ja | .PDF |
||||||||

## <a name="word-perfect"></a>Word Perfect

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. WordPerfect; Version = 5.0 | Ja | Ja | Ja | Nein | Nein | . WPD |
| application/vnd. WordPerfect; Version = 5.1 | Ja | Ja | Ja | Nein | Nein | . WPD |
| application/vnd. WordPerfect; Version = 6. x | Ja | Ja | Ja | Nein | Nein | . WPD |
||||||||

## <a name="word-pro"></a>Word pro

| MIME-Typ | Datei Identifikation | Extraktion von Metadaten | Text Extraktion | Nativer Viewer | Annotations-Viewer | Mögliche Erweiterungen |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. Lotus-WordPro | Ja | Ja | Nein | Nein | Nein | . LWP |
||||||||
