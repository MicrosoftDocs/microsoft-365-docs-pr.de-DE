---
title: Exportieren von Ergebnissen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'Hier erfahren Sie, wie Sie Optionen für den Export von Ergebnissen aus Advanced eDiscovery definieren, einschließlich der Vorgehensweise zum Angeben von Parametern für einen Export Batch. '
ms.openlocfilehash: 2929b183c7c0f3f132cc40738c18e2b4859a49a6
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662910"
---
# <a name="export-results-in-advanced-ediscovery-classic"></a>Exportieren von Ergebnissen in "Advanced eDiscovery" (klassisch)

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In diesem Thema werden die erweiterten eDiscovery-Export-Setup Optionen beschrieben.
  
 **Inhalt dieses Themas:**
  
- [Definieren von Export Batches und-Sitzungen](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [Inkrementelle und zusätzliche Exporte](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [Einrichten von Batch Exportparametern](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [Exportieren von Berichtsausgabe Dateien](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>Definieren von Export Batches und-Sitzungen
<a name="BK_Define"> </a>

Ein Export Batch ermöglicht die Export Verarbeitung mit einem Satz definierter Parameter. Mit Advanced eDiscovery können Sie Batches definieren, um die einzelnen Exporte anzupassen.
  
Parameter werden pro Export Batch definiert. Ein Batch mit dem Namen "Export Batch 01" wird standardmäßig für den ersten Batch einer Anfrage erstellt. Sie können auch den Namen und die Beschreibung des Batches bearbeiten.
  
Bei einer Export Sitzung handelt es sich um eine Ausführung des erweiterten eDiscovery-Exports innerhalb eines Export Batches.
  
## <a name="incremental-and-additional-exports"></a>Inkrementelle und zusätzliche Exporte
<a name="BK_IncrementalReports"> </a>

Sie können mehrere Export Sitzungen innerhalb eines Export Batches ausführen, um konsistente Ergebnisse basierend auf der gleichen Exportvorlage und den gleichen Parametern sicherzustellen. Für jede Sitzung innerhalb eines Batches können Sie Analysen für neu verarbeitete Falldaten exportieren und jeweils "inkrementell" verarbeiten.
  
Um mit einem anderen Satz von Parametern zu exportieren, müssen Sie zunächst einen neuen Batch erstellen. Die erste Sitzung im neuen Batch generiert Ergebnisse für Dateien, die in dem vorliegenden Fall verarbeitet wurden, unabhängig davon, ob diese Dateien über einen oder mehrere Importe importiert und verarbeitet wurden. Jeder Batch berechnet Pivots, Ähnlichkeit, inklusivwerte usw. neu. Sitzungen verwenden die für den Batch definierten Parameter und berechnen Pivots, Ähnlichkeit, inklusivwerte usw. für jede Sitzungs Ausführung nicht neu.
  
Nehmen wir beispielsweise an, dass ein Fall importiert und seine Daten analysiert wurden. Klicken Sie auf **Create Export Session** in dem gleichen Batch, der zuvor zum Exportieren von Daten verwendet wurde, um Near-Duplicates und e-Mail-Threading Ergebnisse für die inkrementellen Daten abzurufen. 
  
## <a name="set-up-batch-export-parameters"></a>Einrichten von Batch Exportparametern
<a name="BK_SetUpExport"> </a>

Das eDiscovery-Export Tool wird verwendet, um Suchergebnisse aus Advanced eDiscovery auf Ihren lokalen Computer zu exportieren.
  
1. Wählen Sie in Advanced eDiscovery einen Fall aus,  und klicken Sie auf \> **Setup** exportieren.
    
    - Wählen Sie in der Liste **Export Batch** den batchnamen aus, oder exportieren Sie Ergebnisse in Batch 01 exportieren (Standard Batch). 
    
    - Um Ergebnisse für neue Dateien zu exportieren, die Sie einem vorhandenen Fall hinzugefügt haben, fahren Sie mit dem aktuellen Batch fort. Wenn Sie eine Sitzung im Batch erstellen möchten, wählen Sie die gleiche Batchnummer aus, und klicken Sie auf **Create Export Session** . Sie können diese Option verwenden, um die gleichen Parameter wie der vorherige Batch in einer inkrementellen Weise zu exportieren. 
    
    - Klicken Sie zum Exportieren in einen neuen Batch auf Add-Symbol **Hinzufügen** , ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) und geben Sie einen neuen Namen in **Batch Name** ein (oder übernehmen Sie den Standardwert) und eine Beschreibung in der **Batch Beschreibung**. Klicken Sie auf **OK**.
    
    - Um einen Stapelverarbeitungs Namen oder eine Beschreibung zu bearbeiten, wählen Sie den Namen in **Export Batch** aus, klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) , und ändern Sie dann die Felder.
    
      > [!NOTE]
      > Nachdem Sie Sitzungen für einen Export Batch ausgeführt haben, können diese nicht gelöscht werden. Darüber hinaus können nur einige Parameter bearbeitet werden, nachdem die erste Sitzung ausgeführt wurde. 
  
    - Um einen doppelten Export Batch zu erstellen, wählen Sie **Duplicate** Export Batch ![ Create a Duplicate Export Batch Icon aus, ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) und geben Sie einen Namen und eine Beschreibung für den doppelten Batch im Bereich ein. 
    
    - Zum Löschen eines Export Batches wählen Sie **Delete** ![ Export Batch Icon aus ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) .
    
    - Um den Verlauf eines Batches anzuzeigen, wählen Sie Verlaufs Symbol für **Stapel Verlauf** ![ anzeigen aus ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) .
    
2. Wählen Sie unter **Auffüllung** die Option **nur Dateien oberhalb des Relevanz-Trenn Ergebnisses einschließen** und/oder **Export Batch verfeinern** aus, wenn Sie die Einstellungen für den Export Batch optimieren möchten. 
    
3. Wenn Sie **nur Dateien oberhalb des Relevanz-Trenn Ergebnisses einschließen** auswählen, wird das **Problem** aktiviert. Wenn das Relevanz-Ergebnis der Datei höher ist als das Ergebnis für das ausgewählte Problem, wird die Datei exportiert, es sei denn, Sie wird vom Filter "for Review" ausgeschlossen. 
  
    Wenn Sie **Export Batch verfeinern** auswählen, werden die Optionsfelder **deduplizieren** und Filtern nach für die Überprüfung aktiviert. Wenn Sie die Option " **deduplizieren**" auswählen, werden doppelte Dateien entsprechend der definierten Richtlinie herausgefiltert [Case Level (Default): aus jeder Gruppe von doppelten Dateien im gesamten Fall werden alle außer einer Datei dedupliziert. Depotebene: in allen doppelten Dateien derselben Depotbank wird jede Datei mit Ausnahme einer Datei dedupliziert.] Die Exportausgabe enthält einen Datensatz aller doppelten Dateien. Wenn Sie nach dem Feld **"zur Überprüfung Filtern** " auswählen, wählen Sie **unter Metadaten ändern** aus, um die Feld Einstellungen **für die Überprüfung** einzugeben. Wählen Sie **Eingabedateien einschließen** aus, um Quelldateien in den Paketinhalt einzubeziehen. Sie können diese Einstellung deaktivieren, um den Exportvorgang zu beschleunigen. Beachten Sie, dass die systemeigenen Dateien in jedem Fall exportiert werden. 
    
4. Wählen Sie unter **Metadaten** eine der folgenden Optionen in der Liste **Export Vorlage** aus (einmal pro Sitzung). 
    
    - **Standard**: grundlegende Gruppe von Datenelementen, Metadaten und Eigenschaften. Verwenden Sie diese Option, wenn Importdaten bereits in Advanced eDiscovery verarbeitet wurden und Exportdaten in ein System hochgeladen werden, das bereits die Dateien enthält. Standardmäßig werden Spalten der Exportvorlage erstellt und gefüllt.
    
    - **All**: vollständige Reihe von Standardmetadaten, einschließlich aller Verarbeitungsdaten, sowie Analyse-und Relevanz-Ergebnisse. Diese Vorlage ist erforderlich, wenn Advanced eDiscovery die Verarbeitung ausführt und Dateidaten erstmalig in ein externes System hochgeladen werden.
    
    - **Probleme**: Wählen Sie **alle Probleme** aus, oder wählen Sie ein bestimmtes Problem aus, das Sie erstellt haben. 
    
5. Unter **Destination**:
    
    - **Herunterladen auf den lokalen Computer**
    
    - **In benutzerdefiniertes Azure-BLOB exportieren**: Wenn diese Option aktiviert ist, können Sie eine Container-URL und ein SAS-Token angeben.
    
      > [!NOTE]
      > Nachdem ein Exportpaket im benutzerdefinierten Azure-BLOB gespeichert wurde, werden die Daten nicht mehr von Advanced eDiscovery verwaltet; Sie wird vom Azure-BLOB verwaltet. Dies bedeutet, dass die exportierten Dateien weiterhin auf dem Azure-BLOB verbleiben, wenn Sie den Fall löschen. 
  
    - **SAS-Token für zukünftige Export Sitzung speichern**: Wenn diese Option aktiviert ist, wird das SAS-Token in der internen Datenbank der erweiterten eDiscovery zur zukünftigen Verwendung verschlüsselt.
    
      > [!NOTE]
      > Das SAS-Token läuft derzeit nach einem Monat ab. Wenn Sie versuchen, nach mehr als einem Monat herunterzuladen, müssen Sie die letzte Sitzung rückgängig machen und dann erneut exportieren. 
  
6. Klicken Sie auf **ändern** , um die Feld Einstellungen für die Überprüfung festzulegen. 
    
    ![Einrichten von Feld Einstellungen für die Überprüfung eines Export Batches](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - Wählen Sie unter **für Überarbeitungs Feld Einstellungen** in Dropdownliste **Szenario auswählen** das Szenario und den Umfang der Überprüfung aus. Die Einstellungen werden basierend auf Ihrer Auswahl angezeigt.
    
      - **Alle überprüfen** (Standard): alle e-Mails, Anlagen und Dokumente sind standardmäßig ausgewählt. 
    
      - **Überprüfen Sie alle eindeutigen Inhalte in einer Gruppe**: inklusive und eindeutige inklusive Kopien, eindeutige Anlagen in e-Mail-Satzebene, repräsentativ für jeden Satz exakter Duplikate.
    
      - **Überprüfen Sie alle eindeutigen Inhalte in einer Gruppe-keine-inklusiv-Kopien**: inklusive, eindeutige Anlagen in e-Mail-Satzebene, repräsentativ für jeden Satz exakter Duplikate.
    
      - **Überprüfen Sie alle eindeutigen Inhalte und verwandten Familiendateien**: inklusive, eindeutige Anlagen in e-Mail-Satzebene, repräsentativ für jeden Satz exakter Duplikate, und erweitern Sie, um Familiendateien einzuschließen.
    
      - **Benutzerdefiniert** (ermöglicht es Ihnen, die Optionen im Dialogfeld zu definieren): Standardmäßig werden aktuelle Auswahlen beibehalten und alle Dialog Optionen aktiviert, um die Auswahl zu ermöglichen. Wenn Sie diese Option auswählen, können Sie die Einstellungen für e-Mails, Dokumente, Anlagen und Verschiedenes anpassen.
    
    - Wählen Sie unter **e-Mails** die e-Mails aus, die Sie exportieren möchten.
    
      - **Alle e-Mails**: (Standardeinstellung) alle e-Mails werden ausgewählt.
    
      - **Inclusive**: eine inklusive e-Mail ist eine letzte e-Mail eines Threads und enthält alle anderen e-Mails aus dem Thread.
    
      - **Inklusiv-und eindeutige inklusive Kopien**: inklusive Kopien und Inklusivleistungen mit gleichem Betreff, Textkörper und Anlagen; eindeutige inklusive Kopien sind eindeutige Kopien dieser e-Mails.
    
    - Wählen Sie unter **Dokumente** die Dokumente aus, die Sie exportieren möchten. 
    
      - **Alle Dokumente**: (Standard) alle Dokumente sind ausgewählt.
    
      - **Pivots**: eine Datei, die als Vertreter der Gruppe "nahe Duplikate" ausgewählt wurde, die in der Regel beim Überprüfen der Gruppe als Grundlinie verwendet wird.
    
      - **Vertreter aus jeder Reihe von exakten Duplikaten**: eindeutige Dateien in doppelter Nähe (einschließlich Pivot).
    
    - Wählen Sie unter **Anlagen** die Anlagen aus, die Sie exportieren möchten. 
    
      - **Alle Anlagen**: (Standard) alle Anlagen sind ausgewählt.
    
      - **Eindeutige Anlage in Fallebene**: eindeutige Anlagendateien im angegebenen Fall.
    
      - **Eindeutige Anlage in e-Mail-Satzebene**: eindeutige Anlagendateien im angegebenen e-Mail-Fall.
    
   - Unter **Micellaneous** können Sie festlegen, dass **Anlagen als Dokumente behandelt**, **e-Mails als Dokumente behandelt** oder **erweitert werden sollen, um Familiendateien einzubeziehen**. Wenn Sie **Expand to include Family files** auswählen, werden für jede Datei, die zur Überarbeitung vorgemerkt ist, auch alle Dateien der gleichen Familie gekennzeichnet.
    
7. Klicken Sie auf **Speichern** , um die Einstellungen zu speichern. 
    
8. Nachdem Sie Exportparameter angegeben haben, klicken Sie auf **Create Export Session**, um den Export Batch zu starten.
    
    Während des Exports wird der Status im **Vorgangsstatus** angezeigt. Die Ergebnisse werden in der **Export Zusammenfassung** angezeigt.
    
9. Klicken Sie im Fenster **Download Dateien** auf in die **Zwischenablage kopieren** , um den Export Schlüssel zu kopieren. 
    
    ![Herunterladen von Dateien](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. Klicken Sie auf **Schließen**. 
    
    Das eDiscovery-Export Tool wird gestartet.
    
    ![eDiscovery-Export Tool](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. Im **eDiscovery-Export Tool**:
    
    -  Fügen Sie in **die freigegebene zugriffssignatur einfügen, die zum Herstellen einer Verbindung mit der Quelle verwendet wird**, den Export Schlüssel ein, den Sie in Schritt 7 in die Zwischenablage kopiert haben.
    
    - Klicken Sie auf **Durchsuchen** , um den Zielspeicherort zum Speichern der heruntergeladenen Exportdateien auf dem lokalen Computer auszuwählen. 
    
    - Klicken Sie auf **Start**. Die Exportdateien werden auf den lokalen Computer heruntergeladen. Wenn Sie in Schritt 4 in **benutzerdefiniertes Azure-BLOB exportieren** ausgewählt haben, wird die Sitzung in ein BLOB-Speicher-URL-Ziel Ihrer Wahl exportiert.
    
Eine vollständige Beschreibung der Felder im Exportbericht finden Sie unter [Export Report Fields](export-report-fields-in-advanced-ediscovery.md).
  
## <a name="export-report-output-files"></a>Exportieren von Berichtsausgabe Dateien
<a name="BK_ExportOutputFIles"> </a>

In der folgenden Tabelle sind die Ausgabedateien aufgeführt, die beim Ausführen eines Export Batches generiert werden.
  
|**Dateiname**|**Dateityp**|**Beschreibung**|
|:-----|:-----|:-----|
|Export Zusammenfassung  <br/> |CSV  <br/> |Eine vom eDiscovery-Export Tool generierte Protokolldatei.  <br/> |
|Ablaufverfolgung  <br/> |txt  <br/> |Eine vom eDiscovery-Export Tool generierte Protokolldatei.  <br/> |
|Extrahierte Textdateien  <br/> |Datei Ordner  <br/> |Ordner, der die extrahierten Textdateien der exportierten Dateien enthält.  <br/> |
|Eingabe-oder systemeigene Dateien  <br/> |Datei Ordner  <br/> |Ordner, der die systemeigenen und Eingabedateien der exportierten Dateien enthält.  <br/> |
|Liste exportieren  <br/> |xlsx  <br/> |Metadaten für exportierte Dateien im XLSX-Format. Felder in Dateien entsprechen dem vom Benutzer ausgewählten Vorlagentyp für den Export. Bei Bedarf werden mehrere Dateien erstellt, die jeweils 100-150K Zeilen enthalten. Wenn ein bestimmter Wert mehr Zeichen enthält als eine Excel-Zelle enthalten kann (derzeit beträgt der Grenzwert 32.767 Zeichen), wird der Wert auf die zulässige maximale Länge gekürzt. Wenn ein Wert gekürzt wird, ist die Hintergrundfarbe der Zelle rot, um dies dem Benutzer anzuzeigen. " E-Mail-Teilnehmer "ist ein Beispiel für ein Feld, das den Längen Grenzwert überschreiten kann, wenn die e-Mail an eine große Verteilung gesendet wurde. Details zu den Ausgabefeldern finden Sie unter [Export Report Fields](export-report-fields-in-advanced-ediscovery.md) .  <br/> |
|Datei laden  <br/> |CSV  <br/> |Exportierte Dateien Metadaten im CSV-Format zum Laden in eine andere Anwendung. Felder in Dateien entsprechen dem vom Benutzer ausgewählten Vorlagentyp für den Export.  <br/> |
|Erfolgsindikator  <br/> |txt  <br/> |Wird nur beim Exportieren in ein Drittanbieter-Azure-Blob erstellt. Wenn der Export vollständig ausgeführt wird, wird die Datei erstellt. Im Falle eines Fehlers oder eines Teil Erfolgs wird die Datei nicht erstellt. Die Datei wird im Stammordner erstellt und ermöglicht eine automatisierte Nachverfolgung in unterschiedlichen Export Batches/-Sitzungsstatus. Dies ist eine leere Datei. Der Name lautet: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md)
  
[Anzeigen des Batch Verlaufs und exportieren vergangener Ergebnisse](view-batch-history-and-export-past-results.md)
  
[Schnelles Einrichten von Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md)

[Exportieren von Berichtsfeldern](export-report-fields-in-advanced-ediscovery.md)
