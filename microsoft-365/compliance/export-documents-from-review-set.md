---
title: Exportieren von Dokumenten aus einem Prüfdateisatz
f1.keywords:
- NOCSH
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
description: Hier erfahren Sie, wie Sie Inhalte aus einem Überprüfungspaket für Präsentationen oder externe Überprüfungen auswählen und exportieren oder herunterladen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034093"
---
# <a name="export-documents-from-a-review-set"></a>Exportieren von Dokumenten aus einem Prüfdateisatz

Sie können Inhalte für die Präsentation oder externe Überprüfung aus einem Überprüfungs Sätze mit einer der folgenden Methoden exportieren:

- [Dokumente herunterladen](#download-documents-from-a-review-set)
 
- [Exportieren von Dokumenten](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>Herunterladen von Dokumenten aus einem Überprüfungspaket

Download bietet eine einfache Möglichkeit zum Herunterladen von Inhalten aus einer Überprüfungsgruppe im systemeigenen Format. Es nutzt die Datentransfer Funktionen des Browsers, sodass nach dem Download eine Browser Ansage angezeigt wird. Mit dieser Methode heruntergeladene Dateien werden in eine Containerdatei gezippt und werden Dateien auf Elementebene sein. Wenn Sie also eine Anlage auswählen, erhalten Sie automatisch die e-Mail-Adresse, die mit der Anlage eingeschlossen ist. Wenn Sie eine Excel-Kalkulationstabelle auswählen, die in ein Word-Dokument eingebettet wurde, erhalten Sie das Word-Dokument mit eingebettetem Excel-Arbeitsblatt. Durch heruntergeladene Elemente wird das Datum der letzten Änderung beibehalten, das als Dateieigenschaft angezeigt werden kann.

Um Inhalte aus einem Überprüfungs herunterzuladen, wählen Sie zunächst die Dateien aus, die Sie herunterladen möchten, und klicken Sie dann im Menü Aktionen auf "herunterladen".

![Screenshot einer automatisch generierten Computerbeschreibung](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>Exportieren von Dokumenten aus einem Prüfdateisatz

Mit dem Export können Benutzer die Inhalte anpassen, die im Downloadpaket enthalten sind. Es stellt eine Konfigurationsseite mit den folgenden Einstellungen bereit:

### <a name="metadata-file"></a>Metadaten-Datei

Dies kann als ihre "Laden Datei" betrachtet werden, die Metadaten enthält, die den exportierten Dateien zugeordnet sind. Eine Liste der exportierten Felder, die in der Metadatendatei zur Verfügung stehen, finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Diese Datei kann normalerweise von Tools von Drittanbietern aufgenommen werden.

### <a name="tag-data"></a>Tag-Daten

Dieser Inhalt würde als Felder in der Metadatendatei hinzugefügt werden. Sie enthält alle in Überprüfungs Sätzen angewendeten Tag-Informationen.

### <a name="text-files"></a>Textdateien

Text Dateien können für jede Datei generiert werden, die aus einem Überprüfungs Satz exportiert wurde. Häufig sind diese Dateien für Service Partner erforderlich, wenn Sie Daten in Drittanbietertools aufnehmen.

### <a name="redacted-files"></a>Behandelte Dateien

Wenn während der Überprüfung redigierte PDF-Dateien generiert werden, stehen diese Dateien während des Exports zur Verfügung. Sie können entscheiden, ob Sie nur systemeigene Dateien exportieren oder die systemeigenen Dateien ersetzen möchten, die für die PDF-Dateien erforderlich sind, die die tatsächlichen Aktionen enthalten.

### <a name="export-location"></a>Export Speicherort

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
