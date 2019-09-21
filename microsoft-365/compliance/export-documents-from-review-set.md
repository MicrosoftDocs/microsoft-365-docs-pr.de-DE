---
title: Exportieren von Dokumenten aus einem Prüfdateisatz
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
ms.openlocfilehash: cf8b11fa82398ab8cfa3981064741d0dbf349f71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081437"
---
# <a name="export-documents-from-a-review-set"></a>Exportieren von Dokumenten aus einem Prüfdateisatz

Sie können Inhalte für die Präsentation oder externe Überprüfung aus einem Überprüfungs Sätze mit einer der folgenden Methoden exportieren:

- [Dokumente herunterladen](#download-documents-from-a-review-set)
 
- [Exportieren von Dokumenten](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>Herunterladen von Dokumenten aus einem Überprüfungspaket

Download bietet eine einfache Möglichkeit zum Herunterladen von Inhalten aus einer Überprüfungsgruppe im systemeigenen Format. Es nutzt die Datentransfer Funktionen des Browsers, sodass nach dem Download eine Browser Ansage angezeigt wird. Mit dieser Methode heruntergeladene Dateien werden in eine Containerdatei gezippt und werden Dateien auf Elementebene sein. Wenn Sie also eine Anlage auswählen, erhalten Sie automatisch die e-Mail-Adresse, die mit der Anlage eingeschlossen ist. Wenn Sie eine Excel-Kalkulationstabelle auswählen, die in ein Word-Dokument eingebettet wurde, erhalten Sie das Word-Dokument mit eingebettetem Excel-Arbeitsblatt. Durch heruntergeladene Elemente wird das Datum der letzten Änderung beibehalten, das als Dateieigenschaft angezeigt werden kann.

Um Inhalte aus einem Überprüfungs herunterzuladen, wählen Sie zunächst die Dateien aus, die Sie herunterladen möchten, und klicken Sie dann im Menü Aktionen auf "herunterladen".

![Screenshot einer automatisch generierten Computerbeschreibung](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>Exportieren von Dokumenten aus einem Prüfdateisatz

Mit dem Export können Benutzer die Inhalte anpassen, die im Downloadpaket enthalten sind. Es stellt eine Konfigurationsseite mit den folgenden Einstellungen bereit:

### <a name="metadata-file"></a>Metadaten-Datei

Dies kann als ihre "Laden Datei" betrachtet werden, die Metadaten enthält, die den exportierten Dateien zugeordnet sind. Eine Liste der in der Metadatendatei verfügbaren Felder \[finden\]Sie unter Link. Diese Datei kann normalerweise von drei<sup>Remote</sup> Tools von Drittanbietern aufgenommen werden.

### <a name="tag-data"></a>Tag-Daten

Dieser Inhalt würde als Felder in der Metadatendatei hinzugefügt werden. Sie enthält alle in Überprüfungs Sätzen angewendeten Tag-Informationen.

### <a name="text-files"></a>Textdateien

Text Dateien können für jede Datei generiert werden, die aus einem Überprüfungs Satz exportiert wurde. Häufig sind diese Dateien für Service Partner erforderlich, wenn Sie Daten<sup>in Drittanbieter</sup> -Tools nach Downstream aufnehmen.

### <a name="redacted-files"></a>Behandelte Dateien

Wenn während der Überprüfung redigierte PDFs generiert werden, stehen diese Dateien während des Exports zur Verfügung. Benutzer können entscheiden, ob Sie systemeigene Dateien exportieren oder natives ersetzen möchten, bei denen die in PDFs gebrannt wurden.

### <a name="export-location"></a>Exportspeicherort

Exportierte Inhalte werden entweder an ein von Microsoft bereitgestelltes Azure-BLOB zugestellt, oder das BLOB eines Kunden kann verwendet werden, wenn die Details beim Export angegeben werden.

### <a name="export-structure"></a>Export Struktur

Wenn Inhalte aus einem Überprüfungs Satzes exportiert werden, ist der Inhalt in der folgenden Struktur organisiert.

  - Stammordner – Download-ID
    
      - Exportieren\_der\_Datei "file. CSV = Metadata"
    
      - Summary. txt = eine Zusammenfassungsdatei mit Export Statistiken
    
      - Input\_oder Native\_files = enthält alle systemeigenen Dateien
    
      - Error\_files = enthält alle Fehler Dateien, die im Export enthalten sind.
        
          - ExtractionError – eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden
        
          - ProcessingError – Inhalte mit Verarbeitungsfehlern. Dieser Inhalt ist eine Elementebene, was bedeutet, dass bei einer Anlage ein Verarbeitungsfehler auftritt, wird die e-Mail-Nachricht, die die Anlage enthält, in diesen Ordner aufgenommen.
    
      - Extrahierte\_Text\_Dateien = enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.