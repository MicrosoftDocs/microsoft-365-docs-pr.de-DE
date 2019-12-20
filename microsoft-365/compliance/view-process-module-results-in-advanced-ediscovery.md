---
title: Anzeigen der Ergebnisse des Prozess Moduls in Office 365 Advanced eDiscovery
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'In diesem Artikel erfahren Sie, wie Sie die Ergebnisse eines in Office 365 Advanced eDiscovery ausgeführten Prozess Moduls finden, einschließlich Vorgangsstatus und Prozesszusammenfassung.  '
ms.openlocfilehash: decfd181354a51054f2ab33870b281d91783cf50
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802180"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>Anzeigen der Ergebnisse des Prozess Moduls in Office 365 Advanced eDiscovery

Nachdem der **Vorbereitungs** \> **Prozess** initiiert wurde, können Sie den Status und die Ergebnisse anzeigen. 
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Prozessaufgaben Status

In **Prepare** \> **Process** \> **results**zeigt die Seite den aktuellen Status (wenn der Prozess derzeit ausgeführt wird) oder den Status des letzten Prozessstatus Vorgangs an, wie im folgenden Beispiel gezeigt.
  
![Vorgangsstatus des Prozess Moduls](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
Die angezeigten Vorgänge können je nach den ausgewählten Prozessoptionen variieren. 
  
- **Inventory**: Advanced eDiscovery durchläuft alle für den Prozess ausgewählten Dateien und führt grundlegende Datensammlungen aus.
    
- **Calculate Signatures**: berechnet die digitalen MD5-Signaturen.
    
- **Compounds-Extraktion**: extrahiert interne oder enthaltene Dateien rekursiv aus Verbunddateien (beispielsweise PST, ZIP, msg). Extrahierte Dateien werden im Fallordner des Falls gespeichert.
    
- **Datenbank wird synchronisiert**: interner Datenbankprozess.
    
- **Dateikopie**: kopiert Prozessdateien. Diese Aufgabe wird immer angezeigt, auch wenn die Option Erweiterte Dateien kopieren ausgewählt ist.
    
- **Textextraktion**: bei systemeigenen Dateien extrahiert Advanced eDiscovery Text aus diesen Dateien mithilfe von DTSearch. Der extrahierte Text dieser Dateien wird als Textdateien im Fallordner gespeichert.
    
- **Aktualisieren von Metadaten**: verarbeitet die geladenen Metadaten. 
    
- **Finalisieren**: interne Verarbeitung, die die Daten der geladenen Fall Dateien abschließt (beispielsweise Fehler-und Erfolgs Dateien identifizieren). 
    
Vorgangsstatus: wird nach Abschluss des Vorgangs angezeigt. Während Vorgänge ausgeführt werden, wird die Ausführungsdauer angezeigt.
  
> [!NOTE]
> Abgeschlossene Aufgaben können auch Summen für Dateien enthalten, die die Verarbeitung abgeschlossen haben, oder Dateien mit Fehlern. 
  
> [!TIP]
> "Cancel" bietet eine Rollback-Option, um die Prozessausführung zu beenden und dann auf die vorherige Datenauffüllung oder gespeicherte verarbeitete Daten zurückzusetzen. Rollback löscht alle verarbeiteten Daten. Wenn Sie nicht möchten, dass die verarbeiteten Daten verloren gehen (beispielsweise möchten Sie diese Dateien erneut laden), wählen Sie die Option "Abbrechen" in diesem Fenster aus, um kein Rollback durchführen zu können. 
  
## <a name="process-summary"></a>Prozesszusammenfassung

In Prepare \> Process \> results \> Process Summary wird eine Aufschlüsselung der geladenen Datei Ergebnisse entsprechend der erfolgreichen Dateiverarbeitung und Fehlerergebnisse angezeigt.
  
In den Bereichen wird eine grafische Anzeige der importierten Dateistatistiken wie folgt dargestellt:
  
- **Prozesszusammenfassung**d: alle Dateien im Fall akkumulieren.
    
- **Prozesszusammenfassung zuletzt**: Dateien, die aus der letzten Sitzung oder Aktion geladen wurden. 
    
- **Familien zuletzt**: Familieninformationen im Fall (sofern vorhanden).
    
- Wenn **Seed** -Dateien hinzugefügt wurden, wird die Anzahl der Seed-Dateien pro Problem aufgeführt, die für die Dateien definiert wurde. 
    
    Wenn die Markierung von **Seed** -Dateien fehlgeschlagen ist, wird dies ebenfalls angegeben. 
    
- Wenn Dateien mit vordefinierten **Tags** hinzugefügt wurden, wird die Anzahl der vordefinierten Dateien pro Problem aufgeführt, das für die Dateien definiert wurde. 
    
    Wenn die Markierung von Dateien mit **vordefinierten Tags** fehlgeschlagen ist, wird dies ebenfalls angegeben. 
    
![Zusammenfassung des Prozess Moduls](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Kumuliertes und letztes Diagramm für Prozesszusammenfassung

Die linke Leiste enthält Quellen + extrahierte Dateien: alle gefundenen Dateien. 
  
Die rechte Leiste, die verarbeitet wird, umfasst Folgendes:
  
- Dateien mit Ladefehlern
    
- Erfolgreich geladene Dateien, was Folgendes beinhalten kann: 
    
  - **Vorhanden**: Dateien, die zuvor geladen wurden und nun erneut geladen wurden (einschließlich Duplikate).
    
  - **Text**: eindeutige Dateien mit Text.
    
  - **Nicht Text**: leere Textdateien, leere systemeigene Textdateien, systemeigene nicht-Textdateien. 
    
  - **Duplikate**s: doppelte Dateien mit Text.
    
## <a name="last-process-errors"></a>Letzte Prozessfehler

In Prepare \> Process \> results \> Last Process Errors werden Details der Fehler in der letzten Sitzung oder ausgeführten Aktion angezeigt.
  
![Prozessmodul Fehler](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Ausführung des Prozess Moduls und Laden von Daten](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

