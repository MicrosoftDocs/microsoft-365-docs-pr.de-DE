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
description: Erfahren Sie, wie Sie Inhalte aus einem Bewertungssatz für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423646"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportieren von Dokumenten aus einem Überprüfungssatz in Advanced eDiscovery

Der Export ermöglicht Benutzern das Anpassen der Inhalte, die im Downloadpaket enthalten sind. Das Exporttool bietet eine Konfigurationsseite mit den folgenden Einstellungen:

![Optionen zum Exportieren von Elementen aus einem Überprüfungssatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Exportoptionen

- Exportname: Name des Exportauftrags.

- Beschreibung: Freitextfeld zum Hinzufügen einer Beschreibung.

- Exportieren Sie diese Dokumente:

  - Nur ausgewählte Dokumente – Exportiert nur die aktuell ausgewählten Dokumente.
  
  - Alle Dokumente im Überprüfungssatz – Exportiert alle Dokumente im Überprüfungssatz

- Metadaten
  
  - Datei laden : Diese Datei enthält Metadaten für jede Datei. Weitere Informationen zu den enthaltenen Feldern finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Diese Datei kann in der Regel von eDiscovery-Tools von Drittanbietern aufgenommen werden.
  
  - Tags : Wenn diese Option ausgewählt ist, werden Tagginginformationen in die Ladedatei aufgenommen.

- Inhalt
  
  - Systemeigene Dateien : Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien zu enthalten.
  
  - Unterhaltungsoptionen
    
    - Unterhaltungsdateien – Exportiert rekonstruierte Chatnachrichten. Dieses Format zeigt Unterhaltungen in einem Format an, das dem entspricht, was Benutzern in der systemeigenen Anwendung angezeigt wird.
    
    - Einzelne Chatnachrichten – Exportieren Sie die ursprünglichen Unterhaltungsdateien, wie sie in Microsoft 365 gespeichert sind.

- Optionen

  - Textdateien : Schließen Sie extrahierte Textversionen systemeigener Dateien ein.
  
  - Ersetzen Sie redacted natives durch konvertierte PDFs: Wenn während der Überprüfung redaktierte PDF-Dateien generiert werden, sind diese Dateien für den Export verfügbar. Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden, die redacted wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Redactions enthalten.

- Ausgabeoptionen (Exportierte Inhalte stehen entweder direkt über einen Webbrowser zum Herunterladen bereit oder können an ein Azure Storage-Konto gesendet werden. Die ersten beiden Optionen ermöglichen den direkten Download.)
  
  - Lose Dateien und PSTs (E-Mails werden psTs nach Möglichkeit hinzugefügt) – Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die Benutzer in ihren systemeigenen Anwendungen sehen.  Weitere Informationen finden Sie im Abschnitt [Lose-Dateien und PST-Exportstruktur.](#loose-files-and-pst-export-structure)
  
  - Verdichtete Verzeichnisstruktur – Dateien werden exportiert und im Download enthalten.
  
  - Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage-Konto exportiert wurde – Dateien werden in das Azure Storage-Konto Ihrer Organisation exportiert.

## <a name="loose-files-and-pst-export-structure"></a>Lose Dateien und PST-Exportstruktur

Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:

- Stammordner – Dieser Ordner in ExportName.zip
  
  - Export_load_file.csv - Metadatendatei.
  
  - Summary.csv – Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.
  
  - Exchange – Dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat. Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.
  
  - SharePoint = Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat. Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.

## <a name="condensed-directory-structure"></a>Verdichtete Verzeichnisstruktur

- Stammordner : Dieser Ordner heißt ExportName.zip
  
  - Export_load_file.csv - Metadatendatei.
  
  - Summary.txt – Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.
  
  - Input_or_native_files – Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden. Wenn Sie redacted PDF-Dateien exportieren, werden sie nicht in PST-Dateien gespeichert. Stattdessen werden sie einem getrennten Ordner hinzugefügt.
  
  - Error_files – Dieser Ordner enthält die folgenden Fehlerdateien, wenn sie im Export enthalten sind:
    
    - ExtractionError. Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.
    
    - ProcessingError – Diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern. Dieser Inhalt ist Elementebene, d. h., wenn eine Anlage zu einem Verarbeitungsfehler geführt hat, wird die E-Mail-Nachricht, die die Anlage enthält, in diesem Ordner enthalten.
  
  - Extracted_text_files – Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.

> [!NOTE]
> Exportaufträge werden für die Lebensdauer des Falls beibehalten. Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.
