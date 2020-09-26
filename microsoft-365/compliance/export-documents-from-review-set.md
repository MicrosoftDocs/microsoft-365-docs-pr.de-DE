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
description: Hier erfahren Sie, wie Sie Inhalte aus einer Überprüfungsgruppe für Präsentationen oder externe Überprüfungen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285361"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportieren von Dokumenten aus einer Überprüfungsgruppe in Advanced eDiscovery

Mit dem Export können Benutzer die Inhalte anpassen, die im Downloadpaket enthalten sind. Das Export-Tool stellt eine Konfigurationsseite mit den folgenden Einstellungen bereit:

![Optionen zum Exportieren von Elementen aus einer Überprüfungsgruppe](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Exportoptionen

- Export Name: Name des Exportauftrags.

- Beschreibung: frei Text Feld, in dem Sie eine Beschreibung hinzufügen können.

- Exportieren Sie diese Dokumente:

  - Nur ausgewählte Dokumente: exportiert nur die aktuell ausgewählten Dokumente.
  
  - Alle Dokumente in der Überprüfungsgruppe: exportiert alle Dokumente in der Überprüfungsgruppe.

- Metadaten
  
  - Datei laden – diese Datei enthält Metadaten für jede Datei. Weitere Informationen dazu, welche Felder enthalten sind, finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) . Diese Datei kann normalerweise von den eDiscovery-Tools von Drittanbietern aufgenommen werden.
  
  - Tags – Wenn diese Option ausgewählt ist, werden Markierungsinformationen in die Datei "Laden" eingeschlossen.

- Inhalt
  
  - Systemeigene Dateien: Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien einzubeziehen.
  
  - Unterhaltungsoptionen
    
    - Unterhaltungsdateien – exportieren Sie rekonstruierte Chatnachrichten. In diesem Format werden Unterhaltungen in einem Formular dargestellt, das den Benutzern in der systemeigenen Anwendung ähnelt.
    
    - Einzelne Chatnachrichten – exportieren Sie die ursprünglichen Unterhaltungsdateien so, wie Sie in Microsoft 365 gespeichert sind.

- Optionen

  - Textdateien – enthalten extrahierten Textversionen von systemeigenen Dateien.
  
  - Ersetzen Sie die bearbeiteten natives durch konvertierte PDFs-wenn im Rahmen der Überprüfung die erstellten PDF-Dateien generiert werden, stehen diese Dateien für den Export zur Verfügung. Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden sollen (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Aktionen enthalten.

- Ausgabeoptionen (exportierte Inhalte stehen entweder direkt über einen Webbrowser herunter oder können an ein Azure-Speicherkonto gesendet werden. Die ersten beiden Optionen ermöglichen das direkte herunterladen.)
  
  - Loose files and PST (e-Mail wird zu PST hinzugefügt, wenn möglich) – Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die Benutzern in ihren systemeigenen Anwendungen angezeigt wird.  Weitere Informationen finden Sie im Abschnitt [Loose files and PST Export Structure](#loose-files-and-pst-export-structure) .
  
  - Komprimierte Verzeichnisstruktur – Dateien werden exportiert und werden in den Download eingeschlossen.
  
  - Komprimierte Verzeichnisstruktur, die in Ihr Azure-Speicherkonto exportiert wurde-Dateien werden in das Azure-Speicher-abrechnen Ihrer Organisation exportiert.

## <a name="loose-files-and-pst-export-structure"></a>Lose Dateien und PST-Exportstruktur

Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:

- Stammordner – dieser Ordner mit dem Namen ExportName.zip
  
  - Export_load_file.csv-Metadata-Datei.
  
  - Summary.csv-eine Zusammenfassungsdatei, die auch Export Statistiken enthält.
  
  - Exchange – dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat. Natives-Dateien werden durch redigierte PDFs ersetzt, wenn Sie die Option " **natives mit konvertierten PDFs ersetzen** " ausgewählt haben.
  
  - SharePoint = dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat. Natives-Dateien werden durch redigierte PDFs ersetzt, wenn Sie die Option " **natives mit konvertierten PDFs ersetzen** " ausgewählt haben.

## <a name="condensed-directory-structure"></a>Komprimierte Verzeichnisstruktur

- Stammordner-dieser Ordner hat den Namen ExportName.zip
  
  - Export_load_file.csv-Metadata-Datei.
  
  - Summary.txt-eine Zusammenfassungsdatei, die auch Export Statistiken enthält.
  
  - Input_or_native_files-dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden. Wenn Sie redigierte PDF-Dateien exportieren, werden Sie nicht in PST-Dateien abgelegt. Stattdessen werden Sie einem getrennten Ordner hinzugefügt.
  
  - Error_files-dieser Ordner enthält die folgenden Fehler Dateien, wenn Sie im Export enthalten sind:
    
    - ExtractionError. Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.
    
    - ProcessingError – diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern. Dieser Inhalt ist auf Elementebene angegeben, was bedeutet, dass in diesem Ordner die e-Mail-Nachricht mit der Anlage enthalten ist, wenn eine Anlage zu einem Verarbeitungsfehler geführt hat.
  
  - Extracted_text_files-dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.

> [!NOTE]
> Export Aufträge werden für die Lebensdauer des Falls aufbewahrt und können heruntergeladen werden, solange der Fall nicht gelöscht wird.
