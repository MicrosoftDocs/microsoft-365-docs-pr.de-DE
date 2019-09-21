---
title: Unterstützte Dateitypen in Data Investigations (Preview)
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
ms.openlocfilehash: 60e4baf2df94793b532fb4035a34ca3c7a5cd332
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081904"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Unterstützte Dateitypen in Data Investigations (Preview)

Data Investigations (Preview) unterstützt viele Dateitypen auf verschiedene Arten, die in der folgenden Tabelle beschrieben werden. Diese Liste ist nicht abgeschlossen, und wir werden neue Dateitypen hinzufügen, während wir unsere Validierungstests fortsetzen. Die Tabelle gibt auch an, ob ein Dateityp in den verfügbaren Viewern angezeigt werden kann, wenn Sie Beweise überprüfen.

| MIME-Typ | File-Klasse | Nativer Viewer | Text Anzeige | Annotations-Viewer | Container Extraktion | Erweiterungen |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Dokument | Ja | Ja | Ja | Nein | . doc;. dat |
| application/pdf | Dokument | Ja | Ja | Ja | Nein | .pdf |
| Application/RTF | Dokument | Ja | Ja | Ja | Nein | . RTF;. doc |
| application/vnd. MS-Excel | Dokument | Ja | Ja | Ja | Nein | xls; DAT |
| application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Produktivität/Open Document Format | Ja | Ja | Nein | Nein | . xlsb |
| application/vnd. MS-Excel. Sheet. macroenabled. 12 | Dokument | Ja | Ja | Ja | Nein | . xlsm |
| application/vnd. MS-Excel. Template. macroenabled. 12 | Produktivität/Open Document Format | Nein | Ja | Nein | Nein | . xltm |
| application/vnd. MS-Outlook | Produktivität | Nein | Nein | Nein | Nein | . msg |
| application/vnd. MS-Outlook-PST | Produktivität/Zusammenarbeit | Nein | Nein | Nein | Ja | PST-Datei |
| application/vnd. MS-PowerPoint | Dokument | Ja | Ja | Ja | Nein | ppt;. PPS;. Pot |
| application/vnd. MS-Word. Document. macroenabled. 12 | Dokument | Ja | Ja | Ja | Nein | DOCM |
| application/vnd. MS-Word. Template. macroenabled. 12 | Dokument | Ja | Ja | Ja | Nein | . dotm |
| application/vnd. Oasis. OpenDocument. Text | Dokument | Ja | Ja | Ja | Nein | ODT  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Dokument | Ja | Ja | Ja | Nein | PPTX |
| application/vnd. openxmlformats-officeDocument. PresentationML. Slideshow | Produktivität/Open Document Format | Ja | Ja | Ja | Nein | . ppsx |
| application/vnd. openxmlformats-officeDocument. PresentationML. Template | Dokument | Ja | Ja | Ja | Nein | . POTX |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Dokument | Ja | Ja | Ja | Nein | xlsx |
| application/vnd. openxmlformats-officeDocument. SpreadsheetML. Template | Dokument | Ja | Ja | Ja | Nein | . xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Dokument | Ja | Ja | Ja | Nein | DOCX |
| application/vnd. openxmlformats-officeDocument. WordprocessingML. Template | Dokument | Ja | Ja | Ja | Nein | . dotx |
| application/vnd. Visio | Dokument | Ja | Ja | Ja | Nein | VSD |
| Application/x-7z-komprimiert | Archiv/Container | Nein | Nein | Nein | Ja | .7z |
| Application/XHTML + XML | Dokument | Ja | Ja | Ja | Nein | . XHTML |
| Application/XML | Dokument | Ja | Ja | Ja | Nein | . XML |
| Application/x-Msaccess | Dokument | Ja | Ja | Ja | Nein | MDB |
| Application/x-mspublisher | Dokument | Ja | Ja | Ja | Nein | . pub |
| Application/x-rar-komprimiert | Archiv/Container | Nein | Nein | Nein | Ja | . rar |
| Anwendung/zip | Archiv/Container | Nein | Nein | Nein | Ja | . zip |
| Bild/BMP | Image | Ja | Ja | Ja | Nein | BMP |
| Bild/EMF | Image | Ja | Ja | Ja | Nein | . EMF |
| image/gif | Dokument | Ja | Ja | Ja | Nein | .gif |
| image/jpeg | Image | Ja | Ja | Ja | Nein | JPG; JPEG;. dat;. jpgt |
| image/png | Image | Ja | Ja | Ja | Nein | .png |
| Bild/TIFF | Image | Ja | Ja | Ja | Nein | TIF |
| Image/vnd. DWG | Dokument | Ja | Ja | Ja | Nein | . dwg;. DXF |
| Image/WMF | Dokument | Ja | Ja | Ja | Nein | . WMF |
| Nachricht/RFC822 | Produktivität/Zusammenarbeit | Nein | Nein | Nein | Nein | EML |
| Text/CSV | Dokument | Ja | Ja | Ja | Nein | . CSV |
| Text/HTML | Dokument | Ja | Ja | Ja | Nein | . html;. shtml;. htm |
| text/plain | Dokument | Ja | Ja | Ja | Nein | txt; CSS;. con;. pl;. CSV;. dat |
| Text/vCard-Kontakt | Dokument | Ja | Ja | Ja | Nein | . vcf |
||||||||
