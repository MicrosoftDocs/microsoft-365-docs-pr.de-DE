---
title: Exportieren von Dokumenten in das Azure Storage-Konto Ihrer Organisation
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
ms.custom: seo-marvel-mar2020
description: Exportieren Sie Dokumente in einem Überprüfungssatz in ein Azure Storage-Konto, und laden Sie sie dann mithilfe von Azure Storage Explorer auf einen lokalen Computer herunter.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574709"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>Exportieren von Dokumenten in einem Überprüfungssatz in ein Azure Storage-Konto

Wenn Sie Dokumente aus einem Überprüfungssatz in einem Advanced eDiscovery-Fall exportieren, haben Sie die Möglichkeit, sie in ein Azure Storage-Konto zu exportieren, das von Ihrer Organisation verwaltet wird. Wenn Sie diese Option verwendet haben, werden die Dokumente an Ihren Azure Storage-Speicherort hochgeladen. Nachdem sie exportiert wurden, können Sie mithilfe des Azure Storage Explorer auf die Dokumente zugreifen (und sie auf einen lokalen Computer oder einen anderen Speicherort herunterladen). Dieser Artikel enthält Anweisungen zum Exportieren von Dokumenten in Ihr Azure Storage-Konto und zum Verwenden des Azure Storage Explorers, um eine Verbindung mit einem Azure Storage-Speicherort herzustellen, um die exportierten Dokumente herunterzuladen. Weitere Informationen zum Azure Storage Explorer finden Sie unter [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="before-you-export-documents-from-a-review-set"></a>Vor dem Exportieren von Dokumenten aus einem Überprüfungssatz

- Sie müssen ein SAS-Token (Shared Access Signature) für Ihr Azure Storage-Konto und die URL für einen bestimmten Container im Speicherkonto bereitstellen, um Dokumente aus einem Überprüfungssatz zu exportieren. Stellen Sie sicher, dass sie zur Hand sind (z. B. in eine Textdatei kopiert), wenn Sie Schritt 2 ausführen.

  - **SAS-Token**: Stellen Sie sicher, dass das SAS-Token für Ihr Azure Storage-Konto (und nicht für den Container) verwendet wird. Sie können ein SAS-Token für Ihr Konto in Azure Storage generieren. Wechseln Sie dazu zum Azure Storage-Konto, und wählen Sie unter Einstellungen **im** Blatt Speicherkonto die Option Zugriffssignatur freigeben aus.  Verwenden Sie die Standardeinstellungen, und lassen Sie alle Ressourcentypen zu, wenn Sie das SAS-Token generieren.

  - **Container-URL:** Sie müssen einen Container erstellen, in den die Überprüfungssatzdokumente hochgeladen werden, und dann eine Kopie der URL für den Container erhalten. Beispiel: `https://ediscoverydata.blob.core.windows.net/exportdata` . Um die URL zu erhalten, wechseln Sie zum Container  in Azure Storage, und wählen Sie **im** Abschnitt Einstellungen im Containerblatt Eigenschaften aus.

- Laden Sie den Azure Storage Explorer herunter, und installieren Sie sie. Anweisungen finden Sie unter [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842). Sie verwenden dieses Tool, um eine Verbindung mit dem Container in Ihrem Azure Storage-Konto herzustellen und die Dokumente herunterzuladen, die Sie in Schritt 1 exportiert haben.

## <a name="step-1-export-the-documents-from-a-review-set"></a>Schritt 1: Exportieren der Dokumente aus einem Überprüfungssatz

Der erste Schritt besteht im Erstellen eines Exportauftrags zum Exportieren von Dokumenten aus einem Überprüfungssatz. Ausführlichere Anweisungen zu allen Exportoptionen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungssatz](export-documents-from-review-set.md). Im folgenden Verfahren werden die Einstellungen zum Exportieren von Dokumenten in das Azure Storage-Konto Ihrer Organisation hervorgehoben.

1. Öffnen Sie im Microsoft 365 Compliance Center den Fall  Advanced eDiscovery, wählen Sie die Registerkarte Sätze überprüfen aus, und wählen Sie dann den Überprüfungssatz aus, den Sie exportieren möchten.

2. Klicken Sie im Überprüfungssatz auf **Aktion**  >  **Exportieren**.

3. Geben Sie auf der Flyoutseite **Exportoptionen** einen Namen (erforderlich) und eine Beschreibung (optional) für den Export ein.

4. Konfigurieren Sie die Einstellungen in den Abschnitten Dokumente, Metadaten, Inhalte und Optionen. Weitere Informationen zu diesen Einstellungen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungssatz](export-documents-from-review-set.md).

5. Wählen Sie **im Abschnitt Ausgabeoptionen** die Option **Verdichtete Verzeichnisstruktur** aus, die in Ihr Azure Storage-Konto exportiert wurde.

6. Fügen Sie die Container-URL und das SAS-Token für Ihr Speicherkonto in die entsprechenden Felder ein.

   ![Einfügen der Verbindungs-URL und des SAS-Tokens in die entsprechenden Felder](../media/AzureStorageOutputOptions.png)

7. Klicken Sie **auf Exportieren,** um den Exportauftrag zu erstellen.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Schritt 2: Abrufen der SAS-URL aus dem Exportauftrag

Im nächsten Schritt rufen Sie die SAS-URL ab, die generiert wird, nachdem Sie den Exportauftrag in Schritt 1 erstellt haben. Sie verwenden die SAS-URL, um eine Verbindung mit dem Container in Ihrem Azure Storage-Konto herzustellen, in das Sie die Überprüfungssatzdokumente exportiert haben.

1. Wechseln Sie auf der Seite **Advanced eDiscovery** zum Fall, und klicken Sie dann **auf** die Registerkarte Exporte.

2. Klicken Sie auf der Registerkarte **Exporte** auf den Exportvorgang, den Sie herunterladen möchten. Dies ist der Exportauftrag, den Sie in Schritt 1 erstellt haben.

3. Kopieren Sie auf der Flyoutseite unter **Speicherorte** die angezeigte SAS-URL. Bei Bedarf können Sie sie in einer Textdatei speichern, damit Sie in Schritt 3 darauf zugreifen können.

   ![Kopieren der UNTER Speicherorte angezeigten SAS-URL](../media/eDiscoExportJob.png)

   > [!TIP]
   > Die im Exportauftrag angezeigte SAS-URL ist eine Verkettung der Container-URL und des SAS-Tokens für Ihr Azure Storage-Konto. Sie können ihn aus dem Exportauftrag kopieren oder selbst erstellen, indem Sie die URL und das SAS-Token kombinieren.

## <a name="step-3-connect-to-the-azure-storage-container"></a>Schritt 3: Herstellen einer Verbindung mit dem Azure Storage-Container

Der letzte Schritt besteht in der Verwendung des Azure Storage Explorers und der SAS-URL, um eine Verbindung mit dem Container in Ihrem Azure Storage-Konto herzustellen und die exportierten Dokumente auf einen lokalen Computer herunterzuladen.

1. Starten Sie den Azure Storage Explorer, den Sie heruntergeladen und installiert haben.

2. Klicken Sie **auf das Symbol Verbinden öffnen.**

   ![Klicken Sie auf das Symbol Konto hinzufügen](../media/AzureStorageConnect.png)

3. Klicken Sie **auf der Seite** Mit Azure Storage verbinden auf **Blob-Container**.

4. Wählen Sie auf der Seite **Authentifizierungsmethode** auswählen die Option SAS **(Shared Access Signature)** aus, und klicken Sie dann auf **Weiter**.

5. Fügen Sie **auf der Seite Verbindungsinformationen** eingeben die SAS-URL (die Sie im Exportauftrag in Schritt 2 erhalten haben) in das Feld **Blob Container SAS URL** ein.

    ![Einfügen der SAS-URL in das URI-Feld](../media/AzureStorageConnect3.png)

    Beachten Sie, dass der Containername im Feld **Anzeigename angezeigt** wird. Sie können diesen Namen bearbeiten.

6. Klicken **Sie auf Weiter,** um die **Zusammenfassungsseite** zu zeigen, und klicken Sie dann auf **Verbinden**.

    Der **Knoten Blobcontainer** (unter **Speicherkonten**  >  **(angefügte Container)** \> wird geöffnet.

    ![Exportieren von Aufträgen im Knoten Blobs-Container](../media/AzureStorageConnect5.png)

    Es enthält einen Container mit dem Anzeigenamen aus Schritt 5. Dieser Container enthält einen Ordner für jeden Exportauftrag, den Sie in den Container in Ihrem Azure Storage-Konto heruntergeladen haben. Diese Ordner werden mit einer ID benannt, die der ID des Exportauftrags entspricht. Sie finden diese Export-IDs (und den Namen des Exports) unter  **Supportinformationen** auf der Flyoutseite für jeden Exportauftrag vorbereiten, der auf der Registerkarte Aufträge im Fall Advanced eDiscovery aufgeführt ist. 

7. Doppelklicken Sie auf den Exportauftragsordner, um ihn zu öffnen.

   Eine Liste der Ordner und Exportberichte wird angezeigt.

    ![Der Exportordner enthält exportierte Dateien und Exportberichte.](../media/AzureStorageConnect6.png)

8. Klicken Sie zum Exportieren aller Inhalte aus dem Exportauftrag auf den Pfeil **nach** oben, um zum Exportauftragsordner zurück zu wechseln, und klicken Sie dann auf **Herunterladen**.

9. Geben Sie den Speicherort an, an den Sie die exportierten Dateien herunterladen möchten, und klicken Sie dann auf Ordner auswählen.

    Der Azure Storage Explorer startet den Downloadvorgang. Der Status des Downloads der exportierten Elemente wird im Bereich **Aktivitäten** angezeigt. Wenn der Download abgeschlossen ist, wird eine Meldung angezeigt.

> [!NOTE]
> Anstatt den gesamten Exportauftrag im Azure Storage Explorer herunterzuladen, können Sie bestimmte Elemente zum Herunterladen und Anzeigen auswählen.

## <a name="more-information"></a>Weitere Informationen

- Der Exportauftragsordner enthält die folgenden Elemente. Die tatsächlichen Elemente im Exportordner werden durch die Exportoptionen bestimmt, die beim Erstellen des Exportauftrags konfiguriert wurden. Weitere Informationen zu diesen Optionen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungssatz](export-documents-from-review-set.md).

  - Export_load_file.csv: Diese CSV-Datei ist ein Detailexportbericht, der Informationen zu jedem exportierten Dokument enthält. Die Datei besteht aus einer Spalte für jede Metadateneigenschaft für ein Dokument. Eine Liste und Beschreibung der Metadaten, die in diesem  Bericht enthalten sind, finden Sie in der Tabelle in Dokumentmetadatenfelder [in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md)in der Spalte Exportierter Feldname.

  - Summary.txt: Eine Textdatei, die eine Zusammenfassung des Exports einschließlich Exportstatistiken enthält.

  - Extracted_text_files: Dieser Ordner enthält eine Textdateiversion jedes exportierten Dokuments.

  - NativeFiles: Dieser Ordner enthält eine systemeigene Dateiversion jedes exportierten Dokuments.

  - Error_files: Dieser Ordner enthält die folgenden Elemente, wenn der Exportauftrag Fehlerdateien enthält:

    - ExtractionError.csv: Diese CSV-Datei enthält die verfügbaren Metadaten für Dateien, die nicht ordnungsgemäß aus ihrem übergeordneten Element extrahiert wurden.

    - ProcessingError: Dieser Ordner enthält Dokumente mit Verarbeitungsfehlern. Dieser Inhalt befindet sich auf Elementebene, d. h., wenn in einer Anlage ein Verarbeitungsfehler aufgetreten ist, wird auch das Dokument, das die Anlage enthält, in diesem Ordner enthalten sein.
