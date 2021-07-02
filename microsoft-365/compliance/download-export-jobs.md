---
title: Exportieren von Dokumenten in das Azure Storage Konto Ihrer Organisation
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
description: Exportieren Sie Dokumente in einem Prüfdateisatz auf ein Azure Storage Konto, und verwenden Sie dann Azure Storage-Explorer, um sie auf einen lokalen Computer herunterzuladen.
ms.openlocfilehash: b7638e33a40a2ac46f4bb69b869e4c2cf6d48f65
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256507"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>Exportieren von Dokumenten in einem Prüfdateisatz auf ein Azure Storage Konto

Wenn Sie Dokumente aus einem Prüfdateisatz in einem Advanced eDiscovery Fall exportieren, haben Sie die Möglichkeit, sie in ein Azure Storage Konto zu exportieren, das von Ihrer Organisation verwaltet wird. Wenn Sie diese Option verwenden, werden die Dokumente an Ihren Azure Storage Speicherort hochgeladen. Nachdem sie exportiert wurden, können Sie mithilfe der Azure Storage-Explorer auf die Dokumente zugreifen (und sie auf einen lokalen Computer oder einen anderen Speicherort herunterladen). Dieser Artikel enthält Anweisungen zum Exportieren von Dokumenten in Ihr Azure Storage Konto und zum Verwenden des Azure Storage-Explorer zum Herstellen einer Verbindung mit einem Azure Storage Speicherort zum Herunterladen der exportierten Dokumente. Weitere Informationen zu Azure Storage-Explorer finden Sie unter [Verwenden von Azure Storage-Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="before-you-export-documents-from-a-review-set"></a>Vor dem Exportieren von Dokumenten aus einem Prüfdateisatz

- Sie müssen ein SAS-Token (Shared Access Signature) für Ihr Azure Storage konto und die URL für einen bestimmten Container im Speicherkonto bereitstellen, um Dokumente aus einem Prüfdateisatz zu exportieren. Achten Sie darauf, dass diese beim Ausführen von Schritt 2 zur Hand sind (z. B. in eine Textdatei kopiert).

  - **SAS-Token:** Stellen Sie sicher, dass sie das SAS-Token für Ihr Azure Storage Konto (und nicht für den Container) abrufen. Sie können ein SAS-Token für Ihr Konto in Azure Storage generieren. Wechseln Sie dazu zum Azure Storage Konto, und wählen Sie **die Zugriffssignatur** freigeben unter den **einstellungen Einstellungen** im Blatt "Speicherkonto" aus. Verwenden Sie die Standardeinstellungen, und lassen Sie alle Ressourcentypen zu, wenn Sie das SAS-Token generieren.

  - **Container-URL:** Sie müssen einen Container erstellen, um die Prüfdateisatzdokumente hochzuladen, und dann eine Kopie der URL für den Container abrufen. Beispiel: `https://ediscoverydata.blob.core.windows.net/exportdata` . Um die URL abzurufen, wechseln Sie zu dem Container in Azure Storage, und wählen Sie **Eigenschaften** unter dem Abschnitt **Einstellungen** im Containerblatt aus.

- Laden Sie die Azure Storage-Explorer herunter, und installieren Sie sie. Anweisungen finden Sie unter [Azure Storage-Explorer Tool.](https://go.microsoft.com/fwlink/p/?LinkId=544842) Mit diesem Tool stellen Sie eine Verbindung mit dem Container in Ihrem Azure Storage konto her und laden die Dokumente herunter, die Sie in Schritt 1 exportiert haben.

## <a name="step-1-export-the-documents-from-a-review-set"></a>Schritt 1: Exportieren der Dokumente aus einem Prüfdateisatz

Der erste Schritt besteht darin, einen Exportauftrag zum Exportieren von Dokumenten aus einem Prüfdateisatz zu erstellen. Ausführlichere Anweisungen zu allen Exportoptionen finden Sie unter [Exportieren von Dokumenten aus einem Prüfdateisatz.](export-documents-from-review-set.md) Im folgenden Verfahren werden die Einstellungen zum Exportieren von Dokumenten in das Azure Storage Konto Ihrer Organisation hervorgehoben.

1. Öffnen Sie im Microsoft 365 Compliance Center die Advanced eDiscovery Fall, wählen Sie die Registerkarte **"Prüfdateisätze"** aus, und wählen Sie dann den Prüfdateisatz aus, den Sie exportieren möchten.

2. Klicken Sie im Prüfdateisatz auf **"Aktion exportieren".**  >  

3. Geben Sie auf der Flyoutseite **"Exportoptionen"** einen Namen (erforderlich) und eine Beschreibung (optional) für den Export ein.

4. Konfigurieren Sie die Einstellungen in den Abschnitten "Dokumente", "Metadaten", "Inhalte" und "Optionen". Weitere Informationen zu diesen Einstellungen finden Sie unter [Exportieren von Dokumenten aus einem Prüfdateisatz.](export-documents-from-review-set.md)

5. Wählen Sie im Abschnitt **"Ausgabeoptionen"** die Struktur des **komprimierten Verzeichnisses** aus, die in Ihre Azure Storage Kontooption exportiert wurde.

6. Fügen Sie die Container-URL und das SAS-Token für Ihr Speicherkonto in die entsprechenden Felder ein.

   ![Einfügen der Verbindungs-URL und des SAS-Tokens in die entsprechenden Felder](../media/AzureStorageOutputOptions.png)

7. Klicken Sie auf **"Exportieren",** um den Exportauftrag zu erstellen.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Schritt 2: Abrufen der SAS-URL aus dem Exportauftrag

Der nächste Schritt besteht darin, die SAS-URL abzurufen, die generiert wird, nachdem Sie den Exportauftrag in Schritt 1 erstellt haben. Verwenden Sie die SAS-URL, um eine Verbindung mit dem Container in Ihrem Azure Storage Konto herzustellen, in das Sie die Dokumente des Prüfdateisatzes exportiert haben.

1. Wechseln **Sie auf** der Advanced eDiscovery Seite zu der Groß-/Kleinschreibung, und klicken Sie dann auf die Registerkarte **"Exporte".**

2. Klicken Sie auf der Registerkarte **Exporte** auf den Exportvorgang, den Sie herunterladen möchten. Dies ist der Exportauftrag, den Sie in Schritt 1 erstellt haben.

3. Kopieren Sie auf der Flyoutseite unter **"Speicherorte"** die angezeigte SAS-URL. Falls erforderlich, können Sie sie in einer Textdatei speichern, damit Sie in Schritt 3 darauf zugreifen können.

   ![Kopieren der SAS-URL, die unter "Speicherorte" angezeigt wird](../media/eDiscoExportJob.png)

   > [!TIP]
   > Die SAS-URL, die im Exportauftrag angezeigt wird, ist eine Verkettung der Container-URL und des SAS-Tokens für Ihr Azure Storage Konto. Sie können ihn aus dem Exportauftrag kopieren oder selbst erstellen, indem Sie die URL und das SAS-Token kombinieren.

## <a name="step-3-connect-to-the-azure-storage-container"></a>Schritt 3: Verbinden zum Azure Storage-Container

Der letzte Schritt besteht darin, die Azure Storage-Explorer und die SAS-URL zu verwenden, um eine Verbindung mit dem Container in Ihrem Azure Storage konto herzustellen und die exportierten Dokumente auf einen lokalen Computer herunterzuladen.

1. Starten Sie die Azure Storage-Explorer, die Sie heruntergeladen und installiert haben.

2. Klicken Sie auf das Dialogfeld **Öffnen Verbinden .**

   ![Klicken Sie auf das Symbol "Konto hinzufügen".](../media/AzureStorageConnect.png)

3. Klicken Sie auf der **Verbinden auf Azure Storage** Seite auf **Blobcontainer.**

4. Wählen Sie auf der Seite **"Authentifizierungsmethode auswählen"** die Option **"Shared Access Signature (SAS)"** aus, und klicken Sie dann auf **"Weiter".**

5. Fügen Sie auf der Seite **"Verbindungsinformationen eingeben"** die SAS-URL (die Sie im Exportauftrag in Schritt 2 erhalten haben) in das **FELD "SAS-URL** des Blobcontainers" ein.

    ![Einfügen der SAS-URL in das URI-Feld](../media/AzureStorageConnect3.png)

    Beachten Sie, dass der Containername im **Anzeigenamenfeld** angezeigt wird. Sie können diesen Namen bearbeiten.

6. Klicken Sie auf **"Weiter",** um die **Zusammenfassungsseite** anzuzeigen, und klicken Sie dann auf **Verbinden**.

    Der **Blobcontainerknoten** (unter **Storage Konten**  >  **(angefügte Container)** wird \> geöffnet.

    ![Exportieren von Aufträgen im Knoten "Blobs-Container"](../media/AzureStorageConnect5.png)

    Es enthält einen Container mit dem Anzeigenamen aus Schritt 5. Dieser Container enthält einen Ordner für jeden Exportauftrag, den Sie in den Container in Ihrem Azure Storage-Konto heruntergeladen haben. Diese Ordner werden mit einer ID benannt, die der ID des Exportauftrags entspricht. Sie finden diese Export-IDs (und den Namen des Exports) unter **"Supportinformationen"** auf der Flyoutseite für die einzelnen **Vorbereitungsdaten für den Exportauftrag,** die auf der Registerkarte **"Aufträge"** im Advanced eDiscovery Fall aufgeführt sind.

7. Doppelklicken Sie auf den Exportauftragsordner, um ihn zu öffnen.

   Eine Liste der Ordner und Exportberichte wird angezeigt.

    ![Der Exportordner enthält exportierte Dateien und Exportberichte.](../media/AzureStorageConnect6.png)

8. Um alle Inhalte aus dem Exportauftrag zu exportieren, klicken Sie auf den Pfeil nach **oben,** um zum Exportauftragsordner zurückzukehren, und klicken Sie dann auf **"Herunterladen".**

9. Geben Sie den Speicherort an, an den Sie die exportierten Dateien herunterladen möchten, und klicken Sie dann auf Ordner auswählen.

    Die Azure Storage-Explorer startet den Downloadvorgang. Der Status des Herunterladens der exportierten Elemente wird im **Bereich "Aktivitäten"** angezeigt. Wenn der Download abgeschlossen ist, wird eine Meldung angezeigt.

> [!NOTE]
> Anstatt den gesamten Exportauftrag in Azure Storage-Explorer herunterzuladen, können Sie bestimmte Elemente auswählen, die heruntergeladen und angezeigt werden sollen.

## <a name="more-information"></a>Weitere Informationen

- Der Exportauftragsordner enthält die folgenden Elemente. Die tatsächlichen Elemente im Exportordner werden durch die Exportoptionen bestimmt, die beim Erstellen des Exportauftrags konfiguriert wurden. Weitere Informationen zu diesen Optionen finden Sie unter [Exportieren von Dokumenten aus einem Prüfdateisatz.](export-documents-from-review-set.md)

  - Export_load_file.csv: Diese CSV-Datei ist ein Detailexportbericht, der Informationen zu jedem exportierten Dokument enthält. Die Datei besteht aus einer Spalte für jede Metadateneigenschaft für ein Dokument. Eine Liste und Beschreibung der Metadaten, die in diesem Bericht enthalten sind, finden Sie in der Spalte **"Exportierter Feldname"** in der Tabelle in den [Dokumentmetadatenfeldern in Advanced eDiscovery.](document-metadata-fields-in-advanced-ediscovery.md)

  - Summary.txt: Eine Textdatei, die eine Zusammenfassung des Exports einschließlich Exportstatistiken enthält.

  - Extracted_text_files: Dieser Ordner enthält eine Textdateiversion jedes exportierten Dokuments.

  - NativeFiles: Dieser Ordner enthält eine systemeigene Dateiversion jedes exportierten Dokuments.

  - Error_files: Dieser Ordner enthält die folgenden Elemente, wenn der Exportauftrag Fehlerdateien enthält:

    - ExtractionError.csv: Diese CSV-Datei enthält die verfügbaren Metadaten für Dateien, die nicht ordnungsgemäß aus dem übergeordneten Element extrahiert wurden.

    - ProcessingError: Dieser Ordner enthält Dokumente mit Verarbeitungsfehlern. Dieser Inhalt befindet sich auf Elementebene, d. h., wenn eine Anlage einen Verarbeitungsfehler aufweist, wird das Dokument, das die Anlage enthält, ebenfalls in diesem Ordner enthalten sein.
