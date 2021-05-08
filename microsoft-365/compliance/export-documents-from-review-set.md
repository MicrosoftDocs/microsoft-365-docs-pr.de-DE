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
description: Erfahren Sie, wie Sie Inhalte aus einem Advanced eDiscovery für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244361"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportieren von Dokumenten aus einem Überprüfungssatz in Advanced eDiscovery

Der Export ermöglicht Benutzern das Anpassen des Inhalts, der im Downloadpaket enthalten ist, wenn Sie ein Dokument aus einem Überprüfungssatz in einem Advanced eDiscovery.

So exportieren Sie Dokumente aus einem Überprüfungssatz:

1. Öffnen Sie Microsoft 365 Compliance Center den Fall Advanced eDiscovery, wählen  Sie die Registerkarte Sätze überprüfen aus, und wählen Sie dann den Überprüfungssatz aus, den Sie exportieren möchten.

2. Klicken Sie im Überprüfungssatz auf **Aktion**  >  **Exportieren**.

   Das Exporttool zeigt die Flyoutseite mit den Einstellungen zum Konfigurieren des Exports an. Einige Optionen sind standardmäßig ausgewählt, sie können jedoch geändert werden. Beschreibungen der Exportoptionen, die Sie konfigurieren können, finden Sie im folgenden Abschnitt.

   ![Konfigurationsoptionen zum Exportieren von Elementen aus einem Überprüfungssatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Nachdem Sie den Export konfiguriert haben, klicken Sie **auf Exportieren,** um den Exportvorgang zu starten. Abhängig von der Option,  die Sie im Abschnitt Ausgabeoptionen ausgewählt haben, können Sie auf die Exportdateien durch direkten Download oder im Konto Ihrer Organisation Azure Storage zugreifen.

> [!NOTE]
> Exportaufträge werden für die Lebensdauer des Falls beibehalten. Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.

## <a name="export-options"></a>Exportoptionen

Verwenden Sie die folgenden Optionen, um den Export zu konfigurieren. Nicht alle Optionen sind für einige Ausgabeoptionen zulässig, insbesondere der Export von Textdateien und redacted PDFs ist beim Exportieren in das PST-Format nicht zulässig.

- **Exportname**: Name des Exportauftrags. Dies wird verwendet, um die heruntergeladenen ZIP-Dateien zu benennen.

- **Beschreibung**: Freitextfeld zum Hinzufügen einer Beschreibung.

- **Exportieren dieser Dokumente**

  - Nur ausgewählte Dokumente: Mit dieser Option werden nur die aktuell ausgewählten Dokumente exportiert. Diese Option ist nur verfügbar, wenn Elemente in einem Überprüfungssatz ausgewählt werden.
  - Alle gefilterten Dokumente: Mit dieser Option werden die Dokumente in einem aktiven Filter exportiert. Diese Option ist nur verfügbar, wenn ein Filter auf den Überprüfungssatz angewendet wird.
  - Alle Dokumente im Überprüfungssatz: Mit dieser Option werden alle Dokumente im Überprüfungssatz exportiert.

- **Ausgabeoptionen:** Exportierte Inhalte stehen entweder direkt über einen Webbrowser zum Download bereit oder können an ein Azure Storage gesendet werden. Die ersten beiden Optionen ermöglichen den direkten Download.
  
  - Nur Berichte: Es werden nur die Zusammenfassungs- und Ladedatei erstellt.
  - Lose Dateien und PSTs (E-Mails werden psTs nach Möglichkeit hinzugefügt): Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die Benutzer in ihren systemeigenen Anwendungen sehen.  Weitere Informationen finden Sie im Abschnitt [Lose-Dateien und PST-Exportstruktur.](#loose-files-and-pst-export-structure)
  - Verdichtete Verzeichnisstruktur: Dateien werden exportiert und im Download enthalten.
  - Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage exportiert wird: Dateien werden in das Konto Ihrer Organisation Azure Storage exportiert. Für diese Option müssen Sie die URL für den Container in Ihrem Azure Storage angeben, in den die Dateien exportiert werden. Sie müssen auch das SAS-Token (Shared Access Signature) für Ihr Azure Storage bereitstellen. Weitere Informationen finden Sie [unter Export documents in a review set to an Azure Storage account](download-export-jobs.md).

- **Include**
  - Tags: Wenn diese Option ausgewählt ist, sind Tagginginformationen in der Ladedatei enthalten.
  - Textdateien: Diese Option enthält die extrahierten Textversionen systemeigener Dateien im Export.
  - Ersetzen Sie redacted natives durch konvertierte PDFs: Wenn während der Überprüfung redaktierte PDF-Dateien generiert werden, sind diese Dateien für den Export verfügbar. Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden, die redacted wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Redactions enthalten.

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a>In den folgenden Abschnitten wird die Ordnerstruktur für lose Dateien und verkürzte Verzeichnisstrukturoptionen beschrieben.

Exporte werden in ZIP-Dateien mit einer maximalen Größe von nicht komprimiertem Inhalt von 75 GB partitioniert. Wenn die Exportgröße kleiner als 75 GB ist, besteht der Export aus einer Zusammenfassungsdatei und einer einzelnen ZIP-Datei. Bei Exporten von mehr als 75 GB unkomprimierter Daten werden mehrere ZIP-Dateien erstellt. Nach dem Herunterladen können die ZIP-Dateien an einem einzigen Speicherort unkomprimiert werden, um den vollständigen Export neu zu erstellen.

### <a name="loose-files-and-pst-export-structure"></a>Lose Dateien und PST-Exportstruktur

Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:

- Summary.csv: Enthält eine Zusammenfassung des Inhalts, der aus dem Überprüfungssatz exportiert wurde
- Stammordner: Dieser Ordner mit dem Namen [Exportname] x z.zip und wird für jede ZIP-Dateipartition wiederholt.
  - Export_load_file_x der z.csv: Die Metadatendatei.
  - Warnungen und Fehler x von z.csv: Diese Datei enthält Informationen zu Fehlern, die beim Exportieren aus dem Überprüfungssatz aufgetreten sind.
  - Exchange: Dieser Ordner enthält alle Inhalte aus Exchange in PST-Dateien gespeicherten Dateien. Redacted PDF files cannot be included with this option. Wenn eine Anlage im Überprüfungssatz ausgewählt ist, wird die übergeordnete E-Mail mit der angefügten Anlage exportiert.
  - SharePoint: Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat. Redacted PDF files cannot be included with this option.

### <a name="condensed-directory-structure"></a>Verdichtete Verzeichnisstruktur

- Summary.csv: Enthält eine Zusammenfassung des Inhalts, der aus dem Überprüfungssatz exportiert wurde
- Stammordner: Dieser Ordner mit dem Namen [Exportname] x z.zip und wird für jede ZIP-Dateipartition wiederholt.
  - Export_load_file_x von z.csv: Die Metadatendatei und enthält auch den Speicherort jeder Datei, die in der ZIP-Datei gespeichert ist.
  - Warnungen und Fehler x von z.csv: Diese Datei enthält Informationen zu Fehlern, die beim Exportieren aus dem Überprüfungssatz aufgetreten sind.
  - NativeFiles: Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden. Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option *Redacted Natives durch konvertierte PDFs ersetzen ausgewählt* haben.
  - Error_files: Dieser Ordner enthält Dateien mit extraktions- oder anderen Verarbeitungsfehlern. Die Dateien werden in separaten Ordnern abgelegt, entweder ExtractionError oder ProcessingError. Diese Dateien werden in der Ladedatei aufgeführt.
  - Extracted_text_files: Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage exportiert wurde

Diese Option verwendet dieselbe allgemeine Struktur wie die *Verdichtete* Verzeichnisstruktur, der Inhalt wird jedoch nicht gezippt und die Daten werden in Ihrem Azure Storage gespeichert. Diese Option wird im Allgemeinen bei der Arbeit mit einem eDiscovery-Drittanbieter verwendet. Weitere Informationen zur Verwendung dieser Option finden Sie unter Exportieren von Dokumenten in einem [Überprüfungssatz auf Azure Storage Konto](download-export-jobs.md).
