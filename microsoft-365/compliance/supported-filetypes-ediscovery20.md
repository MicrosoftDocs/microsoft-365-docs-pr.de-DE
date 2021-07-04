---
title: Unterstützte Dateitypen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Eine Liste der unterstützten Dateitypen in Microsoft 365 Advanced eDiscovery, einschließlich Bilddateitypen, die von der OCR-Funktionalität in Advanced eDiscovery unterstützt werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a637dc0505b74a2b7f7d726ed9a731db8e68c12
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288107"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Unterstützte Dateitypen in Advanced eDiscovery

Advanced eDiscovery unterstützt viele Dateitypen auf vielen verschiedenen Ebenen. Die Typen von Supportdateien werden in den folgenden Tabellen in diesem Artikel beschrieben. Diese Liste ist noch nicht abgeschlossen, und wir fügen neue Dateitypen hinzu, wenn wir unsere Überprüfungstests fortsetzen. Diese Tabellen geben an, ob ein Dateityp für die Textextraktion (und optische Zeichenerkennung oder OCR-Textextraktion für Bilddateien) unterstützt wird, der im nativen Viewer angezeigt werden kann und auch im Kommentaranzeige in Advanced eDiscovery unterstützt wird.

## <a name="archive--container"></a>Archiv/Container

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Containerextraktion|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|
|application/x-7z-compressed|Ja|Ja|Ja|.7z|
|application/x-rar-compressed|Ja|Ja|Ja|.rar|
|application/x-tar|Ja|Ja|Ja|TAR|
|application/zip|Ja|Ja|Ja|.ZIP|
|

## <a name="audio--video"></a>Audio/Video

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/mp4|Ja|Ja|Nein|Ja|Nein|.f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; MPEG4|
|audio/mpeg|Ja|Ja|Nein|Ja|Nein|.mpeg|
|Video/3 gpp|Ja|Ja|Nein|Ja|Nein|.3gp|
|Video/3gpp2|Ja|Ja|Nein|Ja|Nein|.3g2; .3gp2|
|Video/Schnellzeit|Ja|Ja|Nein|Ja|Nein|.moov; .mov; .qt|
|Video/x-m4v|Ja|Ja|Nein|Ja|Nein|M4V|
|

## <a name="database"></a>Datenbank

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-msaccess|Ja|Ja|Ja|Nein|Nein|MDB|
|

## <a name="email"></a>E-Mails

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-outlook|Ja|Ja|Ja|Ja|Ja|MSG|
|message/rfc822|Ja|Ja|Ja|Ja|Ja|.EML|
|text/vcard-contact|Ja|Ja|Ja|Ja|Ja|.vcf|
|

## <a name="email-container"></a>E-Mail-Container

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Containerextraktion|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|
|application/mbox|Ja|Ja|Ja|MBOX|
|application/vnd.ms-outlook-pst|Ja|Ja|Ja|PST|
|

## <a name="html"></a>HTML

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/xhtml+xml|Ja|Ja|Ja|Ja|Ja|XHTML|
|application/xml|Ja|Ja|Ja|Ja|Ja|.xml|
|text/html|Ja|Ja|Ja|Ja|Ja|.htm; .html; .shtml|
|

## <a name="image"></a>Bild

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|OCR-Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|image/bmp|Ja|Ja|Ja|Ja|Ja|BMP|
|image/emf|Ja|Ja|Ja|Ja|Ja|EMF|
|image/gif|Ja|Ja|Ja|Ja|Ja|.gif|
|image/jpeg|Ja|Ja|Ja|Ja|Ja|JPEG; .jpg|
|image/png|Ja|Ja|Ja|Ja|Ja|.png|
|image/svg+xml|Ja|Ja|Ja|Ja|Nein|.svg|
|image/tiff|Ja|Ja|Ja|Ja|Ja|TIF|
|image/vnd.dwg|Ja|Ja|Ja|Ja|Ja|.dwg; .dxf|
|image/wmf|Ja|Ja|Ja|Ja|Ja|WMF|
|

## <a name="microsoft-excel"></a>Microsoft Excel

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-excel|Ja|Ja|Ja|Ja|Ja|DAT; .xls|
|application/vnd.ms-excel.sheet.binary.macroenabled.12|Ja|Ja|Ja|Ja|Nein|XLSB|
|application/vnd.ms-excel.sheet.macroenabled.12|Ja|Ja|Ja|Ja|Ja|XLSM|
|application/vnd.ms-excel.template.macroenabled.12|Ja|Ja|Ja|Nein|Nein|XLTM|
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet|Ja|Ja|Ja|Ja|Ja|.xlsx|
|application/vnd.openxmlformats-officedocument.spreadsheetml.template|Ja|Ja|Ja|Ja|Ja|XLTX|
|

## <a name="microsoft-onenote"></a>Microsoft OneNote

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/onenote|Ja|Ja|Ja|Nein|Nein|.one|
|

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-powerpoint|Ja|Ja|Ja|Ja|Ja|.pot; .pps; .ppt|
|application/vnd.openxmlformats-officedocument.presentationml.presentation|Ja|Ja|Ja|Ja|Ja|PPTX|
|application/vnd.openxmlformats-officedocument.presentationml.slideshow|Ja|Ja|Ja|Ja|Ja|PPSX|
|application/vnd.openxmlformats-officedocument.presentationml.template|Ja|Ja|Ja|Ja|Ja|POTX|
|

## <a name="microsoft-project"></a>Microsoft Project

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-project|Ja|Ja|Ja|Nein|Ja|MPP|
|

## <a name="microsoft-publisher"></a>Microsoft Publisher

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-mspublisher|Ja|Ja|Ja|Ja|Ja|.pub|
|

## <a name="microsoft-visio"></a>Microsoft Visio

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-visio.drawing|Ja|Ja|Ja|Ja|Nein||
|application/vnd.visio|Ja|Ja|Ja|Ja|Ja|VSD|
|

## <a name="microsoft-word"></a>Microsoft Word

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/msword|Ja|Ja|Ja|Ja|Ja|DAT; .doc|
|application/rtf|Ja|Ja|Ja|Ja|Ja|.doc; RTF|
|application/vnd.ms-word.document.macroenabled.12|Ja|Ja|Ja|Ja|Ja|DOCM|
|application/vnd.ms-word.template.macroenabled.12|Ja|Ja|Ja|Ja|Ja|DOTM|
|application/vnd.openxmlformats-officedocument.wordprocessingml.document|Ja|Ja|Ja|Ja|Ja|DOCX|
|application/vnd.openxmlformats-officedocument.wordprocessingml.template|Ja|Ja|Ja|Ja|Ja|DOTX|
|

## <a name="microsoft-works"></a>Microsoft Works

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-works-ss|Ja|Ja|Nein|Nein|Nein|WPS|
|application/vnd.ms-works-wp|Ja|Ja|Nein|Nein|Nein|WPS|
|

## <a name="open-document-format"></a>Open Document Format

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.oasis.opendocument.text|Ja|Ja|Ja|Ja|Ja|ODT|
|

## <a name="other"></a>Andere

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/json|Ja|Ja|Ja|Ja|Ja|n/v|
|application/vnd.ms-graph|Ja|Ja|Nein|Nein|Nein||
|application/winhlp|Ja|Ja|Nein|Nein|Nein|HLP|
|application/x-tnef|Ja|Ja|Nein|Nein|Nein||
|

## <a name="plain-text"></a>Nur-Text

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|text/csv|Ja|Ja|Ja|Ja|Ja|.csv|
|text/plain|Ja|Ja|Ja|Ja|Ja|.con; .css; .csv; .dat; .pl; .txt|
|

## <a name="portable-document-format"></a>Portable Document Format

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/pdf|Ja|Ja|Ja|Ja|Ja|.PDF|
|

## <a name="word-perfect"></a>Word Perfect

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.wordperfect; version=5.0|Ja|Ja|Ja|Nein|Nein|WPD|
|application/vnd.wordperfect; version=5.1|Ja|Ja|Ja|Nein|Nein|WPD|
|application/vnd.wordperfect; version=6.x|Ja|Ja|Ja|Nein|Nein|WPD|
|

## <a name="word-pro"></a>Word Pro

<br>

****

|Mime-Typ|Dateiidentifikation|Metadatenextraktion|Textextraktion|Nativer Viewer|Kommentieren des Betrachters|Mögliche Erweiterungen|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.lotus-wordpro|Ja|Ja|Nein|Nein|Nein|LWP|
|
