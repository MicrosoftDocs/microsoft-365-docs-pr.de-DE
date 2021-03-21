---
title: Herunterladen von Exportaufträgen für einen Advanced eDiscovery-Fall
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Installieren und verwenden Sie den Azure Storage Explorer, um Dokumente herunterzuladen, die aus einem Überprüfungssatz in Advanced eDiscovery exportiert wurden.
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926621"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>Herunterladen von Exportaufträgen in einem Advanced eDiscovery-Fall

Wenn Sie Dokumente aus einem Überprüfungssatz in einem Advanced eDiscovery-Fall exportieren, werden die Dokumente an einen von Microsoft bereitgestellten Azure Storage-Speicherort oder an einen azure-Speicherspeicherort hochgeladen, der von Ihrer Organisation verwaltet wird. Der typ des verwendeten Azure Storage-Speicherorts hängt davon ab, welche Option beim Exportieren der Dokumente ausgewählt wurde.

Dieser Artikel enthält Anweisungen zum Verwenden des Microsoft Azure Storage Explorers, um eine Verbindung mit einem Azure Storage-Speicherort herzustellen, um die exportierten Dokumente zu durchsuchen und herunterzuladen. Weitere Informationen zum Azure Storage Explorer finden Sie unter [Schnellstart: Verwenden von Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="step-1-install-the-azure-storage-explorer"></a>Schritt 1: Installieren des Azure Storage Explorer

Der erste Schritt besteht im Herunterladen und Installieren des Azure Storage Explorers. Anweisungen finden Sie unter [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842). Mit diesem Tool können Sie in Schritt 3 eine Verbindung mit den exportierten Dokumenten herstellen und diese herunterladen.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Schritt 2: Abrufen der SAS-URL aus dem Exportauftrag

Im nächsten Schritt rufen Sie die SAS-URL (Shared Access Signature) ab, die beim Erstellen des Exportauftrags zum Exportieren von Dokumenten aus einem [Überprüfungssatz generiert wird.](export-documents-from-review-set.md) Sie können die SAS-URL für Dokumente kopieren, die an einen von Microsoft bereitgestellten Azure Storage-Speicherort oder einen von Ihrer Organisation verwalteten Azure Storage-Speicherort hochgeladen werden. In beiden Fällen verwenden Sie die SAS-URL, um eine Verbindung mit dem Azure Storage-Speicherort in Schritt 3 herzustellen.

1. Wechseln Sie auf der Seite **Advanced eDiscovery** zum Fall, und klicken Sie dann **auf** die Registerkarte Exporte.

2. Klicken Sie auf der Registerkarte **Exporte** auf den Exportvorgang, den Sie herunterladen möchten.

3. Kopieren Sie auf der Flyoutseite unter **Speicherorte** die angezeigte SAS-URL. Bei Bedarf können Sie sie in einer Datei speichern, damit Sie in Schritt 3 darauf zugreifen können.
 
   ![Kopieren der UNTER Speicherorte angezeigten SAS-URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>Schritt 3: Herstellen einer Verbindung mit dem Azure Storage-Speicherort

Der letzte Schritt besteht in der Verwendung des Azure Storage Explorers und der SAS-URL, um eine Verbindung mit dem Azure Storage-Speicherort herzustellen und die Dokumente herunterzuladen, die Sie auf einen lokalen Computer exportiert haben.

1. Öffnen Sie den Azure Storage Explorer, den Sie in Schritt 1 installiert haben.

2. Klicken Sie auf **das Symbol Konto** hinzufügen. Alternativ können Sie mit der rechten Maustaste auf **Speicherkonten klicken.**

   ![Klicken Sie auf das Symbol Konto hinzufügen](../media/AzureStorageConnect.png)

3. Klicken Sie **auf der Seite** Verbindung mit Azure Storage herstellen auf **SAS-URI (Shared Access Signature)** verwenden, und klicken Sie dann auf **Weiter**.

    ![Klicken Sie auf Sas-URI (Shared Access Signature) verwenden, und klicken Sie dann auf Weiter.](../media/AzureStorageConnect2.png)

4. Klicken Sie auf der Seite Mit **SAS-URI** anfügen in das URI-Feld, und fügen Sie dann die SAS-URL ein, die Sie in Schritt 2 erhalten haben. 

    ![Einfügen der SAS-URL in das URI-Feld](../media/AzureStorageConnect3.png)

    Beachten Sie, dass ein Teil der SAS-URL im Feld **Anzeigename angezeigt** wird. Dies wird als Anzeigename des Containers verwendet, der unter den **Speicherkonten** erstellt wird, nachdem Sie eine Verbindung mit dem Speicherort hergestellt haben. Dieser Name besteht aus der ID des Advanced eDiscovery-Falls und aus einem eindeutigen Bezeichner. Sie können den standardmäßigen Anzeigenamen beibehalten oder ändern. Wenn Sie ihn ändern, muss der Anzeigename eindeutig sein.

5. Klicken Sie auf **Weiter**.

    Die **Seite Verbindungszusammenfassung** wird angezeigt.

    ![Klicken Sie auf der Seite Verbindungszusammenfassung auf Verbinden, um eine Verbindung mit dem Azure Storage-Speicherort herzustellen.](../media/AzureStorageConnect4.png)

6. Überprüfen Sie **auf der Seite Verbindungszusammenfassung** die Verbindungsinformationen, und klicken Sie dann auf **Verbinden**.

    Der **Knoten Blobcontainer** (unter **Speicherkonten**  >  **(angefügte Container)** \> wird geöffnet.

    ![Exportieren von Aufträgen im Knoten Blobs-Container](../media/AzureStorageConnect5.png)

    Es enthält einen Container mit dem Anzeigenamen aus Schritt 4. Dieser Container enthält einen Ordner für jeden von Ihnen erstellten Exportauftrag. Diese Ordner werden mit einer ID benannt, die der ID des Exportauftrags entspricht. Sie finden diese Export-IDs (und den Namen des Exports) unter **Supportinformationen** auf der Flyoutseite für jeden **Exportauftrag** vorbereiten, der auf der Registerkarte Aufträge aufgeführt **ist.**

7. Doppelklicken Sie auf den Exportauftragsordner, um ihn zu öffnen.

   Eine Liste der Ordner und Exportberichte wird angezeigt.
   
    ![Der Exportordner enthält exportierte Dateien und Exportberichte.](../media/AzureStorageConnect6.png)

   Der Exportauftragsordner enthält die folgenden Elemente. Die tatsächlichen Elemente im Exportordner werden durch die Exportoptionen bestimmt, die beim Erstellen des Exportauftrags konfiguriert wurden. Weitere Informationen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungssatz](export-documents-from-review-set.md).

    - Export_load_file.csv: Diese CSV-Datei ist ein Detailexportbericht, der Informationen zu jedem exportierten Dokument enthält. Die Datei besteht aus einer Spalte für jede Metadateneigenschaft für ein Dokument. Eine Liste und Beschreibung der Metadaten, die in diesem  Bericht enthalten sind, finden Sie in der Tabelle in Dokumentmetadatenfelder [in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md)in der Spalte Exportierter Feldname.
    
    - Summary.txt: Eine Textdatei, die eine Zusammenfassung des Exports einschließlich Exportstatistiken enthält.
    
    - Extracted_text_files: Dieser Ordner enthält eine Textdateiversion jedes exportierten Dokuments.
     
    - NativeFiles: Dieser Ordner enthält eine systemeigene Dateiversion jedes exportierten Dokuments.
    
    - Error_files: Dieser Ordner enthält die folgenden Elemente, wenn der Exportauftrag Fehlerdateien enthält: 
        
      - ExtractionError.csv: Diese CSV-Datei enthält die verfügbaren Metadaten für Dateien, die nicht ordnungsgemäß aus ihrem übergeordneten Element extrahiert wurden.
        
      - ProcessingError: Dieser Ordner enthält Dokumente mit Verarbeitungsfehlern. Dieser Inhalt befindet sich auf Elementebene, d. h., wenn in einer Anlage ein Verarbeitungsfehler aufgetreten ist, wird auch das Dokument, das die Anlage enthält, in diesem Ordner enthalten sein.
 
8. Wenn Sie alle Inhalte im Export exportieren möchten, wählen Sie den Exportordner aus, und klicken Sie dann auf **Herunterladen**.

9. Geben Sie den Speicherort an, an den Sie die exportierten Dateien herunterladen möchten, und klicken Sie dann auf Ordner auswählen.

    Der Azure Storage Explorer startet den Exportvorgang. Der Status des Downloads der exportierten Elemente wird im Bereich **Aktivitäten** angezeigt. Nach Abschluss des Downloads wird eine Meldung angezeigt.

    ![Nach Abschluss des Downloads wird eine Meldung angezeigt.](../media/AzureStorageConnect8.png)

> [!NOTE]
> Statt den gesamten Exportauftrag herunterzuladen, können Sie bestimmte Elemente zum Herunterladen auswählen. Anstatt Elemente herunterzuladen, können Sie auch auf ein Element doppelklicken, um es anzuzeigen.