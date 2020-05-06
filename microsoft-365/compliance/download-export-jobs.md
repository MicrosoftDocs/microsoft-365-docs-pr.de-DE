---
title: Herunterladen von Exportaufträgen für einen Fall
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
ms.custom: seo-marvel-mar2020
description: Installieren und verwenden Sie den Azure Storage Explorer zum Herunterladen von Dokumenten, die aus einer Überprüfungsgruppe in Advanced eDiscovery exportiert wurden.
ms.openlocfilehash: 617ef0b27d5cab4098c505eaefb935ba8ae4ae2a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035677"
---
# <a name="download-export-jobs"></a>Herunterladen von Exportaufträgen

Wenn Sie Dokumente aus einer Überprüfungsgruppe in einem erweiterten eDiscovery-Fall exportieren, werden die Dokumente in einen von Microsoft bereitgestellten Azure-Speicherort oder an einen Azure-Speicherort hochgeladen, der von Ihrer Organisation verwaltet wird. Der Typ des verwendeten Azure-Speicherorts hängt davon ab, welche Option beim Exportieren der Dokumente ausgewählt wurde. 

In diesem Artikel wird beschrieben, wie Sie mithilfe des Microsoft Azure Speicher-Explorers eine Verbindung mit einem Azure-Speicherort herstellen, um die exportierten Dokumente zu durchsuchen und herunterzuladen. Weitere Informationen zum Azure Storage-Explorer finden Sie unter [Quick Start: Verwenden des Azure Storage Explorers](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="step-1-install-the-azure-storage-explorer"></a>Schritt 1: Installieren des Azure Storage-Explorers

Der erste Schritt besteht darin, den Azure Storage Explorer herunterzuladen und zu installieren. Anweisungen finden Sie unter [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842). Mit diesem Tool können Sie in Schritt 3 eine Verbindung mit den exportierten Dokumenten herstellen und diese herunterladen.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Schritt 2: Abrufen der SAS-URL aus dem Exportauftrag

Der nächste Schritt besteht darin, die SAS-URL (Shared Access Signature) zu erhalten, die generiert wurde, als Sie den Exportauftrag zum [Exportieren von Dokumenten aus einem Überprüfungs Satz](export-documents-from-review-set.md)erstellt haben. Sie können die SAS-URL für Dokumente kopieren, die in einen von Microsoft bereitgestellten Azure-Speicherort oder einen von Ihrer Organisation verwalteten Azure-Speicherplatz hochgeladen werden. In beiden Fällen verwenden Sie die SAS-URL, um eine Verbindung mit dem Azure-Speicherort in Schritt 3 herzustellen.

1. Wechseln Sie auf der Seite **Erweiterte eDiscovery** zu dem Fall, und klicken Sie dann auf die Registerkarte **Exporte** .

2. Klicken Sie auf der Registerkarte **Exports** auf den Exportauftrag, den Sie herunterladen möchten.

3. Kopieren Sie auf der Flyout-Seite unter **Standorte**die angezeigte SAS-URL. Falls erforderlich, können Sie Sie in einer Datei speichern, damit Sie in Schritt 3 darauf zugreifen können.
 
   ![Kopieren der unter Standorte angezeigten SAS-URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>Schritt 3: Herstellen einer Verbindung mit dem Azure-Speicherort

Im letzten Schritt wird der Azure-Speicher-Explorer und die SAS-URL verwendet, um eine Verbindung mit dem Azure-Speicherort herzustellen und die Dokumente herunterzuladen, die Sie auf einen lokalen Computer exportiert haben.

1.  Öffnen Sie den Azure Storage Explorer, den Sie in Schritt 1 installiert haben.

2. Klicken Sie auf das Symbol **Konto hinzufügen** . Alternativ können Sie mit der rechten Maustaste auf **Speicherkonten**klicken.

   ![Klicken Sie auf das Symbol Konto hinzufügen.](../media/AzureStorageConnect.png)

3.  Klicken Sie auf der Seite **Verbindung mit Azure-Speicher herstellen** auf **einen SAS-URI (Shared Access Signature) verwenden** , und klicken Sie dann auf **weiter**.

    ![Klicken Sie auf SAS-URI (Shared Access Signature) verwenden, und klicken Sie dann auf Weiter.](../media/AzureStorageConnect2.png)

4.  Klicken Sie auf der Seite **mit SAS-URI anfügen** in das Feld URI, und fügen Sie dann die SAS-URL ein, die Sie in Schritt 2 abgerufen haben. 

    ![Fügen Sie die SAS-URL in das Feld URI ein.](../media/AzureStorageConnect3.png)

    Beachten Sie, dass ein Teil der SAS-URL im Feld **Anzeigename** angezeigt wird. Dieser wird als Anzeigename des Containers verwendet, der unter den **Speicherkonten** erstellt wurde, nachdem Sie eine Verbindung mit dem Speicherort hergestellt haben. Dieser Name besteht aus der ID des erweiterten eDiscovery-Falls und einem eindeutigen Bezeichner. Sie können den standardmäßigen Anzeigenamen beibehalten oder ändern. Wenn Sie den Namen ändern, muss der Anzeigename eindeutig sein.

5.  Klicken Sie auf **Weiter**.

    Die Seite **Verbindungszusammenfassung** wird angezeigt.
   
    ![Klicken Sie auf der Seite Verbindungszusammenfassung auf verbinden, um eine Verbindung mit dem Azure-Speicherort herzustellen.](../media/AzureStorageConnect4.png)

6. Überprüfen Sie auf der Seite zusammen **Fassung der Verbindung** die Verbindungsinformationen, und klicken Sie dann auf **verbinden**. 

    Der **Knoten BLOB-Container** (unter **Speicherkonten** > **(angefügte Container)** \> wird geöffnet. 

    ![Exportieren von Aufträgen im Knoten BLOBs-Container](../media/AzureStorageConnect5.png)

    Sie enthält einen Container namens mit dem Anzeigenamen aus Schritt 4. Dieser Container enthält einen Ordner für jeden exportierten Auftrag, den Sie erstellt haben. Diese Ordner werden mit einer ID benannt, die der ID des Exportauftrags entspricht. Diese Export-IDs (und der Name des Exports) finden Sie unter **Support Informationen** auf der Flyout-Seite für jeden auf der Registerkarte **Aufträge** aufgeführten **Vorbereitungs Daten für den Export** Auftrag.

7. Doppelklicken Sie auf den Exportauftrags Ordner, um ihn zu öffnen.

   Eine Liste von Ordnern und Export Berichten wird angezeigt.
   
    ![Der Exportordner enthält exportierte Dateien und exportiert Berichte](../media/AzureStorageConnect6.png)

   Der Exportauftrags Ordner enthält die folgenden Elemente. Die tatsächlichen Elemente im Exportordner werden durch die Exportoptionen bestimmt, die beim Erstellen des Exportauftrags konfiguriert wurden. Weitere Informationen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungs Satzes](export-documents-from-review-set.md).

    - Export_load_file. CSV: Diese CSV-Datei ist ein Detail Exportbericht mit Informationen zu den einzelnen exportierten Dokumenten. Die Datei besteht aus einer Spalte für jede Metadata-Eigenschaft für ein Dokument. Eine Liste und eine Beschreibung der Metadaten, die in diesem Bericht enthalten sind, finden Sie in der Spalte **exportierter Feldname** in der Tabelle in [Document Metadata fields in Advanced eDiscovery](document-metadata-fields.md).
    
    - Summary. txt: eine Textdatei, die eine Zusammenfassung des Exports einschließlich Export Statistiken enthält.
    
    - Extracted_text_files: dieser Ordner enthält eine Text Dateiversion jedes exportierten Dokuments.
     
    - NativeFiles: dieser Ordner enthält eine systemeigene Dateiversion jedes exportierten Dokuments.
    
    - Error_files: dieser Ordner enthält die folgenden Elemente, wenn der Exportauftrag Fehler Dateien enthält: 
        
      - ExtractionError. CSV: Diese CSV-Datei enthält die verfügbaren Metadaten für Dateien, die nicht ordnungsgemäß aus dem übergeordneten Element extrahiert wurden.
        
      - ProcessingError: dieser Ordner enthält Dokumente mit Verarbeitungsfehlern. Dieser Inhalt befindet sich auf einer Elementebene, was bedeutet, dass bei einer Anlage ein Verarbeitungsfehler vorliegt, das Dokument, das die Anlage enthält, ebenfalls in diesem Ordner enthalten sein wird.
 
8. Wenn Sie alle Inhalte im Export exportieren möchten, wählen Sie den Ordner exportieren aus, und klicken Sie dann auf **herunterladen**.

9. Geben Sie den Speicherort an, an dem Sie die exportierten Dateien herunterladen möchten, und klicken Sie dann auf Ordner auswählen.

    Der Azure Storage Explorer startet den Exportvorgang. Der Status des Herunterladens der exportierten Elemente wird im Bereich " **Aktivitäten** " angezeigt. Nach Abschluss des Downloads wird eine Meldung angezeigt.

    ![Eine Meldung wird angezeigt, wenn der Download abgeschlossen ist.](../media/AzureStorageConnect8.png)

> [!NOTE]
> Anstatt den gesamten Exportauftrag herunterzuladen, können Sie bestimmte Elemente zum Herunterladen auswählen. Anstatt Elemente herunterzuladen, können Sie auf ein Element doppelklicken, um es anzuzeigen.
