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
ms.openlocfilehash: 719a0474d45825114cf4ea3fbd19082bb8df7622
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599830"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Unterstützte Dateitypen in Advanced eDiscovery

Advanced eDiscovery unterstützt viele Dateitypen auf vielen verschiedenen Ebenen. Die Typen von Supportdateien werden in den folgenden Tabellen in diesem Artikel beschrieben. Diese Liste ist nicht endgültig, und wir fügen neue Dateitypen hinzu, während wir unsere Überprüfungstests fortsetzen. Diese Tabellen geben an, ob ein Dateityp für die Textextraktion (und optische Zeichenerkennung oder OCR-Textextraktion für Bilddateien) unterstützt wird, der im systemeigenen Viewer angezeigt werden kann und auch im Annotate Viewer in Advanced eDiscovery unterstützt wird.

## <a name="archive--container"></a>Archiv/Container

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Containerextraktion | Mögliche Erweiterungen |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Ja | Ja | Ja | .7z |
|application/x-rar-compressed | Ja | Ja | Ja | .rar |
|application/x-tar | Ja | Ja | Ja | .tar |
|application/zip | Ja | Ja | Ja | .ZIP |
||||||||

## <a name="audio--video"></a>Audio/Video

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Ja | Ja | Nein | Ja | Nein | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | Ja | Ja | Nein | Ja | Nein | .mpeg |
|video/3gpp | Ja | Ja | Nein | Ja | Nein | .3gp |
|video/3gpp2 | Ja | Ja | Nein | Ja | Nein | .3g2; .3gp2 |
|Video/Quicktime | Ja | Ja | Nein | Ja | Nein | .moov; .mov; .qt |
|video/x-m4v | Ja | Ja | Nein | Ja | Nein | .m4v |
||||||||

## <a name="database"></a>Database

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Ja | Ja | Ja | Nein | Nein | .mdb |
||||||||

## <a name="email"></a>E-Mail senden

|Mime-Typ |Dateiidentifikation |Metadatenextraktion |Textextraktion |Systemeigener Viewer |Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Ja | Ja | Ja | Ja | Ja | .msg |
|message/rfc822 | Ja | Ja | Ja | Ja | Ja | .EML |
|text/vcard-contact | Ja | Ja | Ja | Ja | Ja | .vcf |
||||||||

## <a name="email-container"></a>E-Mail-Container

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Containerextraktion | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------|
|application/mbox | Ja | Ja | Ja | .mbox |
|application/vnd.ms-outlook-pst | Ja | Ja | Ja | PST |
||||||||

## <a name="html"></a>HTML

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Ja | Ja | Ja | Ja | Ja | .xhtml |
|application/xml | Ja | Ja | Ja | Ja | Ja | .xml |
|text/html | Ja | Ja | Ja | Ja | Ja | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Bild

|Mime-Typ |Dateiidentifikation |Metadatenextraktion |OCR-Textextraktion |Systemeigener Viewer |Annotate Viewer |Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | Ja | Ja | Ja | Ja | Ja | BMP |
|image/emf | Ja | Ja | Ja | Ja | Ja | .emf |
|image/gif | Ja | Ja | Ja | Ja | Ja | .gif |
|image/jpeg | Ja | Ja | Ja | Ja | Ja | .jpeg; .jpg |
|image/png | Ja | Ja | Ja | Ja | Ja | .png |
|image/svg+xml | Ja | Ja | Ja | Ja | Nein | .svg |
|image/tiff | Ja | Ja | Ja | Ja | Ja | .tif |
|image/vnd.dwg | Ja | Ja | Ja | Ja | Ja | .dxf; .dxf |
|image/wmf | Ja | Ja | Ja | Ja | Ja | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Ja | Ja | Ja | Ja | Ja | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Ja | Ja | Ja | Ja | Nein | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Ja | Ja | Ja | Nein | Nein | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Ja | Ja | Ja | Ja | Ja | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Ja | Ja | Ja | Ja | Ja | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | Ja | Ja | Ja | Nein | Nein | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Ja | Ja | Ja | Ja | Ja | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Ja | Ja | Ja | Ja | Ja | PPTX |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Ja | Ja | Ja | Ja | Ja | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | Ja | Ja | Ja | Ja | Ja | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Ja | Ja | Ja | Nein | Ja | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Ja | Ja | Ja | Ja | Ja | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Ja | Ja | Ja | Ja | Nein |  |
|application/vnd.visio | Ja | Ja | Ja | Ja | Ja | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | Ja | Ja | Ja | Ja | Ja | .dat; .doc |
| application/rtf | Ja | Ja | Ja | Ja | Ja | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | DOCM |
|application/vnd.ms-word.template.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | .dotm |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Ja | Ja | Ja | Ja | Ja | DOCX |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Ja | Ja | Ja | Ja | Ja | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Ja | Ja | Nein | Nein | Nein | .wps |
|application/vnd.ms-works-wp | Ja | Ja | Nein | Nein | Nein | .wps |
||||||||

## <a name="open-document-format"></a>Öffnen des Dokumentformats

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | Ja | Ja | Ja | Ja | Ja | .odt |
||||||||

## <a name="other"></a>Andere

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Ja | Ja | Ja | Ja | Ja | n/v |
|application/vnd.ms-graph | Ja | Ja | Nein | Nein | Nein |  |
|application/winhlp | Ja | Ja | Nein | Nein | Nein | .hlp |
|application/x-tnef | Ja | Ja | Nein | Nein | Nein |  |
||||||||

## <a name="plain-text"></a>Nur-Text

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Ja | Ja | Ja | Ja | Ja | .csv |
|text/plain | Ja | Ja | Ja | Ja | Ja | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | Ja | Ja | Ja | Ja | Ja | .PDF |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Ja | Ja | Ja | Nein | Nein | .wpd |
|application/vnd.wordperfect; version=5.1 | Ja | Ja | Ja | Nein | Nein | .wpd |
|application/vnd.wordperfect; version=6.x | Ja | Ja | Ja | Nein | Nein | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime-Typ | Dateiidentifikation | Metadatenextraktion | Textextraktion | Systemeigener Viewer | Annotate Viewer | Mögliche Erweiterungen |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Ja | Ja | Nein | Nein | Nein | .lwp |
||||||||
