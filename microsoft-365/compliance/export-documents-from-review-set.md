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
description: Erfahren Sie, wie Sie Inhalte aus einem Advanced eDiscovery-Überprüfungssatz für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581018"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportieren von Dokumenten aus einem Überprüfungssatz in Advanced eDiscovery

Der Export ermöglicht Benutzern das Anpassen der Inhalte, die im Downloadpaket enthalten sind, wenn Sie ein Dokument aus einem Überprüfungssatz in Advanced eDiscovery exportieren.

So exportieren Sie Dokumente aus einem Überprüfungssatz:

1. Öffnen Sie im Microsoft 365 Compliance Center den Fall  Advanced eDiscovery, wählen Sie die Registerkarte Sätze überprüfen aus, und wählen Sie dann den Überprüfungssatz aus, den Sie exportieren möchten.

2. Klicken Sie im Überprüfungssatz auf **Aktion**  >  **Exportieren**.

   Das Exporttool zeigt die Flyoutseite mit den Einstellungen zum Konfigurieren des Exports an. Einige Optionen sind standardmäßig ausgewählt, sie können jedoch geändert werden. Beschreibungen der Exportoptionen, die Sie konfigurieren können, finden Sie im folgenden Abschnitt.

   ![Konfigurationsoptionen zum Exportieren von Elementen aus einem Überprüfungssatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Nachdem Sie den Export konfiguriert haben, klicken Sie **auf Exportieren,** um den Exportvorgang zu starten. Abhängig von der Option,  die Sie im Abschnitt Ausgabeoptionen ausgewählt haben, können Sie auf die Exportdateien durch direkten Download oder im Azure Storage-Konto Ihrer Organisation zugreifen.

> [!NOTE]
> Exportaufträge werden für die Lebensdauer des Falls beibehalten. Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.

## <a name="export-options"></a>Exportoptionen

Verwenden Sie die folgenden Optionen, um den Export zu konfigurieren.

- **Exportname**: Name des Exportauftrags.

- **Beschreibung**: Freitextfeld zum Hinzufügen einer Beschreibung.

- **Exportieren dieser Dokumente**

  - **Nur ausgewählte Dokumente:** Mit dieser Option werden nur die aktuell ausgewählten Dokumente exportiert.
  
  - **Alle Dokumente im Überprüfungssatz:** Mit dieser Option werden alle Dokumente im Überprüfungssatz exportiert.

- **Metadaten**
  
  - **Ladedatei**: Diese Datei enthält Metadaten für jede Datei. Diese Datei kann in der Regel von eDiscovery-Tools von Drittanbietern aufgenommen werden. Weitere Informationen zu den enthaltenen Feldern finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).
  
  - **Tags**: Wenn diese Option ausgewählt ist, sind Tagginginformationen in der Ladedatei enthalten.

- **Inhalt**
  
  - **Systemeigene Dateien:** Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien der Dokumente in den Prüfsatz zu setzen. Wenn Sie systemeigene Dateien exportieren möchten, haben Sie die folgenden Optionen für den Export von Chatunterhaltungen.
  
  - **Unterhaltungsoptionen**

    - **Unterhaltungsdateien:** Mit dieser Option werden rekonstruierte Chatunterhaltungen exportiert. Dieses Format zeigt Unterhaltungen in einem Format an, das dem entspricht, was Benutzern in der systemeigenen Anwendung angezeigt wird.

    - **Einzelne Chatnachrichten:** Mit dieser Option werden die ursprünglichen Unterhaltungsdateien exportiert, wie sie in Microsoft 365 gespeichert sind.

- **Optionen**

  - **Textdateien**: – Diese Option enthält die extrahierten Textversionen systemeigener Dateien im Export.
  
  - **Ersetzen Sie redacted natives durch konvertierte PDFs:** Wenn während der Überprüfung redaktierte PDF-Dateien generiert werden, sind diese Dateien für den Export verfügbar. Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden, die redacted wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Redactions enthalten.

- **Ausgabeoptionen:** Exportierte Inhalte können entweder direkt über einen Webbrowser heruntergeladen oder an ein Azure Storage-Konto gesendet werden. Die ersten beiden Optionen ermöglichen den direkten Download.
  
  - **Lose Dateien und PSTs**(E-Mails werden psTs nach Möglichkeit hinzugefügt): Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die benutzer in ihren systemeigenen Anwendungen sehen.  Weitere Informationen finden Sie im Abschnitt [Lose-Dateien und PST-Exportstruktur.](#loose-files-and-pst-export-structure)
  
  - **Verdichtete Verzeichnisstruktur:** Dateien werden exportiert und im Download enthalten.
  
  - **Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage-Konto** exportiert wurde: Dateien werden in das Azure Storage-Konto Ihrer Organisation exportiert. Für diese Option müssen Sie die URL für den Container in Ihrem Azure Storage-Konto angeben, in den die Dateien exportiert werden. Sie müssen auch das SAS-Token (Shared Access Signature) für Ihr Azure Storage-Konto bereitstellen. Weitere Informationen finden Sie [unter Exportieren von Dokumenten in einem Überprüfungssatz auf ein Azure Storage-Konto](download-export-jobs.md).

In den folgenden Abschnitten wird die Ordnerstruktur für lose Dateien und verkürzte Verzeichnisstrukturoptionen beschrieben.

### <a name="loose-files-and-pst-export-structure"></a>Lose Dateien und PST-Exportstruktur

Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:

- Stammordner: Dieser Ordner in ExportName.zip
  
  - Export_load_file.csv: Die Metadatendatei.
  
  - Summary.csv: Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.
  
  - Exchange: Dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat. Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.
  
  - SharePoint: Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat. Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.

### <a name="condensed-directory-structure"></a>Verdichtete Verzeichnisstruktur

- Stammordner: Dieser Ordner heißt ExportName.zip
  
  - Export_load_file.csv: Die Metadatendatei.
  
  - Summary.txt: Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.
  
  - NativeFiles: Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden. Wenn Sie redacted PDF-Dateien exportieren, werden sie nicht in PST-Dateien gespeichert. Stattdessen werden sie einem getrennten Ordner hinzugefügt.
  
  - Error_files: Dieser Ordner enthält die folgenden Fehlerdateien, wenn sie im Export enthalten sind:

    - ExtractionError: Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.

    - ProcessingError: Diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern. Dieser Inhalt ist Elementebene, d. h., wenn eine Anlage zu einem Verarbeitungsfehler geführt hat, wird die E-Mail-Nachricht, die die Anlage enthält, in diesem Ordner enthalten.
  
  - Extracted_text_files: Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.
