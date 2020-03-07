---
title: Festlegen von Analyseoptionen in Office 365 Advanced eDiscovery
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Lesen Sie die Schritte zum Einrichten von Optionen für den Analyseprozess in Office 365 Advanced eDiscovery, einschließlich nahe Dubletten, e-Mail-Threads und Designs.  '
ms.openlocfilehash: 8897099d7531b48f7c6618c106eeb6f051dac546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557785"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>Festlegen von Analyseoptionen in Advanced eDiscovery (klassisch)

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Legen Sie in Advanced eDiscovery die Analyseoptionen vor der Ausführung von ANALYZE fest.
  
## <a name="set-analyze-options"></a>Festlegen von Analyseoptionen

Öffnen **Sie \> Prepare analyze** \> **Setup**. Das folgende Fenster wird angezeigt.
  
![Festlegen von Analyseoptionen](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **Nahe Duplikate und e-Mail-Threads** Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Analyse ausführen möchten. Diese Option ist standardmäßig aktiviert. 
  
 **Dokument Ähnlichkeit** Geben Sie den Schwellenwert für nahe Dubletten ein, oder übernehmen Sie den Standardwert von 65%. 
  
 **Designs** Aktivieren Sie dieses Kontrollkästchen, um alle Dateien zu verarbeiten und Ihnen Designs zuzuweisen. Dieses Kontrollkästchen ist standardmäßig nicht aktiviert. Geben Sie die folgenden Optionen ein, wenn Sie die Design Verarbeitung durchführen möchten.
  
- **Maximale Anzahl von Designs** Geben Sie einen Wert für die Anzahl der zu erstellende Designs ein, oder wählen Sie ihn aus. Der Standardwert ist 200. 
    
    > [!NOTE]
    > Die Erhöhung der Anzahl von Designs wirkt sich sowohl auf die Leistung als auch auf die Möglichkeit eines Designs für die Verallgemeinerung aus. Je höher die Anzahl der Designs ist, desto präziser sind Sie. Wenn beispielsweise eine Gruppe von 50 Designs ein Design wie "Basketball, Sporen, Clippers, Lakers" enthält; 300 Designs können separate Designs enthalten: "spores", "Clippers", "Lakers". Wenn Sie kein Bewusstsein für das Thema "Basketball" und verwenden Sie diese Funktion für ECA, sehen das Thema "Basketball" könnte nützlich sein. Wenn die Verarbeitung jedoch zu viele Designs hatte, werden Sie möglicherweise nie das Wort "Basketball" sehen und wissen möglicherweise nicht, dass Spurs und Clippers gute Basketball Themen sind, anstatt Elemente, die auf Stiefeln laufen und für Haare verwendet werden. 
  
- **Vorgeschlagene Designs** Sie können Design Wörter vorschlagen, um die Verarbeitung von Designs zu steuern. Advanced eDiscovery konzentriert sich auf diese vorgeschlagenen Wörter und versucht, ein oder mehrere relevante Designs basierend auf den Einstellungen für "maximale Anzahl von Designs" zu erstellen. 
    
    Wenn beispielsweise das vorgeschlagene Wort "Computer" lautet und Sie "2" als "maximale Anzahl von Designs" angegeben haben, versucht Advanced eDiscovery, zwei Designs zu generieren, die sich auf das Wort "Computer" beziehen. Die beiden Themen können beispielsweise "Computer Software" und "Computer Hardware" lauten. 
    
    ![Hinzufügen eines vorgeschlagenen Designs](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. Wenn Sie vorgeschlagene Designs anzeigen, hinzufügen oder bearbeiten möchten, klicken Sie auf **ändern**.
    
2. Klicken Sie im Bereich **vorgeschlagene Designs** **auf das** ![Symbol Add Icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) hinzufügen, um ein Design hinzuzufügen. Fügen Sie im Bereich **vorgeschlagenes Design hinzufügen** die Wörter hinzu, getrennt durch Kommas. 
    
3. Wählen Sie unter **Anzahl der Designs**einen Wert aus, um die Anzahl der Designs zu ermitteln, die Advanced eDiscovery für diese Wörter zu generieren versucht (Standard ist 1 Design).
    
4. Klicken Sie auf **Speichern** , und schließen Sie dann den Dialog. 
    
    > [!NOTE]
    > Die Gesamtzahl der Designs umfasst vorgeschlagene Designs. Die insgesamt vorgeschlagenen Designs dürfen die Gesamtdesigns nicht überschreiten. Wenn es viele vorgeschlagene Themen im Verhältnis zu den Gesamtdesigns gibt, werden nur einige "neuartige" Designs vom System erkannt, da die meisten Designs für vorgeschlagene Designs bestimmt sind. 
  
- **Modus "** Wählen Sie in der Dropdownliste die Option **Designs** aus: 
    
  - **Modell erstellen und anwenden**: berechnet Designs anhand von Modellen aus einem Segment der Dateien und verteilt dann Dateien unter diesen.
    
  - **Modell erstellen**: berechnet ein Design Modell aus einem Segment der Dateien. Das Anwenden von Dateien wird separat zu einem anderen Zeitpunkt ausgeführt.
    
  - **Modell anwenden**: diese Option wird nur angezeigt, wenn ein Modell zuvor erstellt wurde und noch nicht angewendet wurde. Dadurch werden die Dateien basierend auf den Designs aufgeteilt.
    
Sie können auch [Text ignorieren festlegen](set-ignore-text-in-advanced-ediscovery.md) und [Erweiterte Einstellungen](set-analyze-advanced-settings-in-advanced-ediscovery.md) für ANALYZE festlegen. 
  
Nachdem Sie diese Optionen festgelegt haben, klicken Sie auf **Analyse** ausführen. [Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md) werden angezeigt. 
  
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (klassisch)](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Dokument Ähnlichkeit](understand-document-similarity-in-advanced-ediscovery.md)
  
[Text ignorieren festlegen](set-ignore-text-in-advanced-ediscovery.md)
  
[Erweiterte Einstellungen für ANALYZE festlegen](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md)

