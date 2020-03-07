---
title: Verwenden der Express Analyse in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Hier erfahren Sie, wie Sie den Express-Analysemodus Office 365 Advanced eDiscovery ausführen können.
ms.openlocfilehash: d4b8e1fa5e8251f5ede2d9a3003c756decac3b45
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557643"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a>Verwenden der Express Analyse in Advanced eDiscovery (klassisch) 

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Sie können die **Express Analyse** verwenden, um einen Fall schnell zu analysieren und die Ergebnisse zu exportieren. 
  
Sie können die Expressanalyse verwenden, um nahe Duplikate und e-Mail-Threads zu berechnen und Designs zu berechnen. Sie können auch bestimmte Parameter für Designs, die Ähnlichkeit von Dokumenten und die Exportdateien in den [erweiterten Einstellungen für die Express Analyse](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)festlegen.
  
## <a name="run-express-analysis"></a>Ausführen der Express Analyse

1. Wählen Sie auf der Registerkarte **Express Analyse** (1) einen Container aus, um die Schaltflächen * * Express-Analyse * * (2) und **Erweiterte Einstellungen** zu aktivieren. 
    
    ![Screenshot der Seite "Express-Analyse"](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. Unter **Parameter analysieren**:
    
  - Überprüfen Sie **berechnen nahe Duplikate und e-Mail-Threads** , wenn Sie die Analyse ausführen möchten. Diese Option ist standardmäßig aktiviert. 
    
  - Überprüfen Sie **Designs berechnen** , um alle Dateien zu verarbeiten und Ihnen Designs zuzuweisen. Diese Option ist standardmäßig aktiviert. 
    
3. Unter **Export Ziel**:
    
  - Überprüfen Sie **Download auf lokalen** Computer herunterladen auf Ihren lokalen Computer. 
    
  - Wenn Sie **den Export in ein benutzerdefiniertes Azure-BLOB** überprüfen, können Sie auch eine Container-URL und ein SAS-Token angeben. 
    
    > [!NOTE]
    > Nachdem ein Exportpaket im benutzerdefinierten Azure-BLOB gespeichert wurde, werden die Daten nicht mehr von Advanced eDiscovery verwaltet. Sie wird vom Azure-BLOB verwaltet. Dies bedeutet, dass die exportierten Dateien weiterhin auf dem Azure-BLOB verbleiben, wenn Sie den Fall löschen. 
  
  - **SAS-Token für zukünftige Export Sitzung speichern**: Wenn diese Option aktiviert ist, wird das SAS-Token in der internen Datenbank der erweiterten eDiscovery zur zukünftigen Verwendung verschlüsselt.
    
    > [!NOTE]
    > Das SAS-Token läuft derzeit nach einem Monat ab. Wenn Sie versuchen, nach mehr als einem Monat herunterzuladen, müssen Sie die letzte Sitzung rückgängig machen und dann erneut exportieren. 
  
4. Um die Express-Analyse mit Standardeinstellungen zu starten, wählen Sie **Express-Analyse**und auf der Seite **Aufgabenstatus** wird angezeigt 
    
    Auf der Seite **Aufgabenstatus** können Sie die Registerkarten **verarbeiten**, **analysieren** und **exportieren** erweitern, um Details zur Express Ausführung anzuzeigen. 
    
    ![Screenshot der Seite Advanced eDiscovery Express Analysis Task Status](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Wählen Sie die **Zusammenfassungsseite für Express Analysen** aus, um detaillierte Informationen zur Ausführung aufzulisten. 
    
    Wählen Sie unten auf der Seite **Zusammenfassung der Express Analyse** die Option **letzte Sitzung herunterladen** aus, um die Analysedateien TP auf Ihrem lokalen Computer herunterzuladen. Zunächst müssen Sie das eDiscovery-Export Tool herunterladen und den Exportschlüssel in das eDiscovery-Export Tool einfügen. 
    
## <a name="advanced-settings-for-express-analysis"></a>Erweiterte Einstellungen für die Express Analyse
<a name="BK_AdvancedSettings"> </a>

Sie können optional **Erweiterte Einstellungen** festlegen, um die Standardparameter für die Express-Analyse zu ändern. 
  
1. Im Abschnitt **analyze** : 
    
  - Geben Sie in den **Themen nahe Duplikate und e-Mail-Threads**den **Dokument Ähnlichkeits** Wert ein, oder übernehmen Sie die Standardeinstellung von 65%. 
    
  - Geben Sie in die **Maximale Anzahl von Designs** ein, oder wählen Sie einen Wert für die Anzahl der Designs aus, die erstellt werden sollen. Der Standardwert ist 200. 
    
    > [!NOTE]
    > Die Erhöhung der Anzahl von Designs wirkt sich sowohl auf die Leistung als auch auf die Möglichkeit eines Designs für die Verallgemeinerung aus. Je höher die Anzahl der Designs ist, desto präziser sind Sie. Wenn beispielsweise eine Gruppe von 50 Designs ein Design wie "Basketball, Sporen, Clippers, Lakers" enthält; 300 Designs können separate Designs enthalten: "spores", "Clippers", "Lakers". Wenn Sie kein Bewusstsein für das Thema "Basketball" und verwenden Sie diese Funktion für ECA, sehen das Thema "Basketball" könnte nützlich sein. Wenn die Verarbeitung jedoch zu viele Designs hatte, werden Sie möglicherweise nie das Wort "Basketball" sehen und wissen möglicherweise nicht, dass Spurs und Clippers gute Basketball Themen sind, anstatt Elemente, die auf Stiefeln laufen und für Haare verwendet werden. 
  
  - Wählen Sie in den **vorgeschlagenen Designs** die Option **ändern** aus, um die Themen Wörter zur Steuerung der Design Verarbeitung zu empfehlen. Advanced eDiscovery konzentriert sich auf diese vorgeschlagenen Wörter und versucht, ein oder mehrere relevante Designs basierend auf den Einstellungen für "maximale Anzahl von Designs" zu erstellen. 
    
    Wenn beispielsweise das vorgeschlagene Wort "Computer" lautet und Sie "2" als "maximale Anzahl von Designs" angegeben haben, versucht Advanced eDiscovery, zwei Designs zu generieren, die sich auf das Wort "Computer" beziehen. Die beiden Themen können beispielsweise "Computer Software" und "Computer Hardware" lauten.
    
    ![Hinzufügen eines vorgeschlagenen Designs](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modus "** Wählen Sie in der Dropdownliste die Option **Designs** aus: 
    
  - **Modell erstellen und anwenden**: berechnet Designs anhand von Modellen aus einem Segment der Dateien und verteilt dann Dateien unter diesen.
    
  - **Modell erstellen**: berechnet ein Design Modell aus einem Segment der Dateien. Das Anwenden von Dateien wird separat zu einem anderen Zeitpunkt ausgeführt.
    
  - **Modell anwenden**: diese Option wird nur angezeigt, wenn ein Modell zuvor erstellt wurde und noch nicht angewendet wurde. Dadurch werden die Dateien basierend auf den Designs aufgeteilt.
    
2. Im Abschnitt **Export** : 
    
1. Im **Select Export Batch**:
    
  - Wählen Sie in der Liste **Export Batch** den batchnamen aus, oder exportieren Sie Ergebnisse in Batch 01 exportieren (Standard Batch). 
    
  - Um Ergebnisse für neue Dateien zu exportieren, die Sie einem vorhandenen Fall hinzugefügt haben, fahren Sie mit dem aktuellen Batch fort. Wenn Sie eine Sitzung im Batch erstellen möchten, wählen Sie die gleiche Batchnummer aus, und klicken Sie auf **Create Export Session** . Sie können diese Option verwenden, um die gleichen Parameter wie der vorherige Batch in einer inkrementellen Weise zu exportieren. 
    
  - Klicken Sie zum Exportieren in einen neuen Batch auf Add-](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) Symbol **Hinzufügen** ![, und geben Sie einen neuen Namen in **Batch Name** ein (oder übernehmen Sie den Standardwert) und eine Beschreibung in der **Batch Beschreibung**. Klicken Sie auf **OK**.
    
  - Um einen Stapelverarbeitungs Namen oder eine Beschreibung zu bearbeiten, wählen Sie den Namen in **Export Batch**aus](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![, und ändern Sie dann die Felder.
    
    > [!NOTE]
    > Nachdem Sie Sitzungen für einen Export Batch ausgeführt haben, können diese nicht gelöscht werden. Darüber hinaus können nur einige Parameter bearbeitet werden, nachdem die erste Sitzung ausgeführt wurde. 
  
  - Um einen doppelten Export Batch zu erstellen, wählen Sie **Duplicate** ![Export Batch Create a Duplicate Export](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) Batch Icon aus, und geben Sie einen Namen und eine Beschreibung für den doppelten Batch im Bereich ein. 
    
  - Zum Löschen eines Export Batches wählen Sie **Delete** ![Export Batch Icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)aus.
    
  - Um den Verlauf eines Batches anzuzeigen, wählen Sie Verlaufs Symbol](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)für **Stapel Verlauf** ![anzeigen aus.
    
2. Wählen Sie unter define p **Bevölkerung:** **nur Dateien oberhalb des Relevanz-Trenn Ergebnisses einschließen** und/oder **Export Batch verfeinern** aus, wenn Sie die Einstellungen für den Export Batch optimieren möchten. Wenn Sie **nur Dateien oberhalb des Relevanz-Trenn Ergebnisses einschließen**auswählen, wird das **Problem** aktiviert, und wenn das Relevanz-Ergebnis der Datei höher ist als das trennergebnis für das ausgewählte Problem, wird die Datei exportiert. Die Datei wird exportiert, es sei denn, Sie wird durch den Filter " **for Review** " ausgeschlossen. Wenn Sie **Export Batch verfeinern**auswählen, werden die Optionsfelder **deduplizieren** und **Filtern nach für die Überprüfung** aktiviert. Wenn Sie die Option " **deduplizieren**" auswählen, werden Duplikate von Dateien entsprechend der definierten Richtlinie gefiltert: [Case Level (Default): aus jeder Gruppe von doppelten Dateien im gesamten Fall werden alle außer einer Datei dedupliziert. Depotebene: aus jeder Gruppe von doppelten Dateien desselben depoters werden alle Dateien mit Ausnahme einer Datei detäuscht. In der Exportausgabe steht ein Datensatz aller doppelten Dateien zur Verfügung. Wenn Sie nach dem Feld **"zur Überprüfung Filtern** " auswählen, wählen Sie **unter Metadaten ändern** aus, um die Feld Einstellungen **für die Überprüfung**einzugeben. Wählen Sie **Eingabedateien einschließen**aus, um Quelldateien in den Paketinhalt einzubeziehen. Sie können diese Option deaktivieren, um den Exportvorgang zu beschleunigen. Beachten Sie, dass die systemeigenen Dateien in jedem Fall exportiert werden.
    
3. Wählen Sie unter **Metadaten definieren**die Option aus den folgenden Optionen in der Liste **Export Vorlage** aus (einmal pro Sitzung). 
    
  - **Standard**: grundlegende Gruppe von Datenelementen, Metadaten und Eigenschaften. Verwenden Sie diese Option, wenn Importdaten bereits in Advanced eDiscovery verarbeitet wurden und Exportdaten in ein System hochgeladen werden, das bereits die Dateien enthält. Standardmäßig werden Spalten der Exportvorlage erstellt und gefüllt.
    
  - **All**: vollständige Reihe von Standardmetadaten, einschließlich aller Verarbeitungsdaten, sowie Analyse-und Relevanz-Ergebnisse. Diese Vorlage ist erforderlich, wenn Advanced eDiscovery die Verarbeitung ausführt und Dateidaten erstmalig in ein externes System hochgeladen werden.
    
  - **Probleme**: Wählen Sie **alle Probleme** aus, oder wählen Sie ein bestimmtes Problem aus, das Sie erstellt haben. 
    
Wählen Sie **OK**aus, um die erweiterten Einstellungen zu speichern, Standardwerte für **Wiederherstellung** zu verwenden oder **Abbrechen** , um das Festlegen der erweiterten Einstellungen abzubrechen. 
  
## <a name="see-also"></a>Siehe auch
<a name="BK_AdvancedSettings"> </a>

[Advanced eDiscovery (klassisch)](office-365-advanced-ediscovery.md)

