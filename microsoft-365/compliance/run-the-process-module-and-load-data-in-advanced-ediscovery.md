---
title: Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Erfahren Sie, wie Sie mit dem &amp; Office 365 Security Compliance Center auf Office 365 Advanced eDiscovery zugreifen und das Prozessmodul für einen Fall ausführen.  '
ms.openlocfilehash: 89a4be9bf56f35d9d9cbd88494bcae5a5a10fe7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081973"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In diesem Abschnitt wird die Funktionalität des Advanced eDiscovery Process-Moduls beschrieben. 
  
Zusätzlich zu Dateidaten können Metadaten wie Dateityp, Erweiterung, Ort oder Pfad, Erstellungsdatum und-Uhrzeit, Autor, Depotbank und Betreff in Advanced eDiscovery geladen und für jeden Fall gespeichert werden. Einige Metadaten werden von Advanced eDiscovery berechnet, beispielsweise, wenn systemeigene Dateien geladen werden. 
  
Advanced eDiscovery stellt Systemmetadaten-Werte bereit, beispielsweise nahe doppelte Gruppierungen oder Relevanz-Bewertungen. Andere Metadaten, wie beispielsweise Datei Anmerkungen, können vom Administrator hinzugefügt werden. 
  
## <a name="running-process"></a>Ausgeführter Prozess

> [!NOTE]
> Batch Nummern werden während des Prozesses einer Datei zugewiesen, um die Nachverfolgung von Dateien zu ermöglichen. Die Batchnummer ermöglicht auch das Identifizieren von Prozess Batches für die Wiederaufbereitung von Optionen. Für die Filterung nach Batchnummer und Sitzungen stehen zusätzliche Filter zur Verfügung. 
  
Führen Sie die folgenden Schritte aus, um den Prozess auszuführen.
  
1. [Öffnen Sie das Office 365 &amp; Security Compliance Center](go-to-the-securitycompliance-center.md) . 
    
2. Wechseln Sie **zu &amp; Search Investigation** \> **eDiscovery** , und klicken Sie dann auf **Gehe zu Advanced eDiscovery**.
    
3. Wählen Sie in Advanced eDiscovery den entsprechenden Fall auf der Seite angezeigte **Anfragen** aus, und klicken Sie auf **Gehe zu Groß-/Kleinschreibung**.
    
4. Wählen Sie in **Prepare** \> **Process** \> **Setup**einen Container aus der Liste der verfügbaren Container aus.
    
    ![Klicken Sie auf Prozess, um dem Fall die Suchergebnisse hinzuzufügen.](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Klicken Sie auf **Erweiterte Einstellungen...** , wenn Sie den Container als Seed-Dateien oder als Dateien mit vordefinierten Tags hinzufügen möchten. 
    
    Verwenden Sie Seed-Dateien, um das Training für Probleme mit niedrigem Umfang zu beschleunigen (normalerweise 2% oder weniger). Für Seed-Dateien wird empfohlen, dass Sie eine Vielzahl von eindeutig relevanten Dateien auswählen und über 20-50-Seeds pro Problem verarbeiten (zu viele seeddateien können die Relevanz der Ergebnisse verzerren). Seed-Dateien sollten von derselben Person überprüft werden, die das Problem trainiert.
    
    Verwenden Sie Pre-Tagged-Dateien, um die Relevanz-Schulung zu automatisieren. Sie sollten mindestens 1.500-Dateien markieren und den Anteil relevanter für unrelevante Dateien auf die gleiche Weise wie in der zur Relevanz hinzugefügten Sammlung beibehalten. Diese Dateien sollten manuell markiert werden, und Sie sollten in der Qualität von Tagging sicher sein.
    
    ![Screenshot der Seite "Erweiterte Einstellungen" für die Verarbeitung von Batchdateien](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - Im Abschnitt **Seed** : 
    
    Wählen Sie **als Seed-Dateien markieren** aus, um den Container als seeddateien zu kennzeichnen. Sie müssen auch auswählen, um Sie pro Problem aus der Dropdownliste **für Probleme** zuzuweisen. Wählen Sie aus der Dropdownliste **Tag** entweder **relevant** oder **nicht relevant** aus. 
    
    > [!NOTE]
    > Nachdem Sie Dateien als **Seed**festgelegt haben, können Sie Sie nicht als **vormarkiert**markieren. 
  
  - Im Abschnitt " **Pre-Tagged files** ": 
    
    Wählen Sie **als vordefinierte Dateien markieren** aus, um den Container als vormarkierte Dateien zu kennzeichnen. Sie müssen Sie auch pro Problem aus der Dropdownliste " **für Problem** " zuweisen. Wählen Sie aus der Dropdownliste **Tag** entweder **relevant** oder **nicht relevant** aus. 
    
    > [!NOTE]
    > Nachdem Sie Dateien als **vordefinierte Tags**festgelegt haben, können Sie Sie nicht als **Seed**markieren. 
  
  - Im Abschnitt **e-Mail-Tagging** . Legen Sie fest, welcher Teil einer verarbeiteten e-Mail als Seed oder Pre-Tagged markiert werden soll. 
    
6. Klicken Sie zunächst auf **verarbeiten**. Nach Abschluss werden die Prozessergebnisse angezeigt.
    
7. Optional Wenn Sie einer bestimmten Depotbank Datenquellen zuweisen müssen, können Sie Verwalter Namen in **Verwalter** \> **Verwalten** und \> Zuweisungen **in Verwalter zuweisen hinzu** fügen und **Bearbeiten.** 
    
Wenn Sie den Fall hinzufügen, können Sie den Vorgang erneut ausführen.
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Anzeigen der Ergebnisse des Prozess Moduls](view-process-module-results-in-advanced-ediscovery.md)

