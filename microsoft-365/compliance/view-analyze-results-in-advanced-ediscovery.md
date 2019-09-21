---
title: Anzeigen von Analyseergebnissen in Office 365 Advanced eDiscovery
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Hier erfahren Sie, wo Sie die Ergebnisse des Analyseprozesses in Office 365 Advanced eDiscovery anzeigen können, einschließlich der Definitionen der angezeigten Aufgabenoptionen.  '
ms.openlocfilehash: 092daa506316b5eb1ef1f5c466055b29e350dc18
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082113"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Anzeigen von Analyseergebnissen in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery können Fortschritte und Ergebnisse für den Analyseprozess in einer Vielzahl von Displays angezeigt werden, wie unten beschrieben.
  
## <a name="view-analyze-task-status"></a>Anzeigen des Vorgangsstatus analysieren

In **Prepare \> Analyse \> results \> Task Status**wird der Status während und nach dem Analysieren der Prozessausführung angezeigt. 
  
![Analysieren des Aufgabenstatus](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
Die angezeigten Aufgaben können je nach den ausgewählten Optionen variieren. 
  
- **ND/et: Setup**: bereitet die Ausführung vor, beispielsweise legt Run-und Case-Parameter fest.
    
- **ND/et: ND-Berechnung**: verarbeitet die nahezu duplizierte Analyse von Dateien.
    
- **ND/et: et calculation**: führt eine e-Mail-Thread Analyse für die gesamte e-Mail-Gruppe aus.
    
- **ND/et: Pivots und Ähnlichkeiten**: führt die Verarbeitung von Pivot-und Datei Ähnlichkeit aus.
    
- **ND/et: Metadata Update**: schließt die neuen Daten ein, die für die Dateien in der Datenbank gesammelt wurden.
    
- **Designs: Design Berechnung**: führt die Design Analyse aus. (Wird nur angezeigt, wenn aktiviert.)
    
- **Vorgangsstatus**: diese Verbindung wird nach Abschluss des Vorgangs angezeigt. Während Vorgänge ausgeführt werden, wird die Ausführungsdauer angezeigt.
    
> [!NOTE]
> Die Analyseergebnisse von nahe Duplikaten und e-Mail-Threads (ND und ED) gelten für die Anzahl der zu verarbeitenden Dokumente. Es enthält keine exakten doppelten Dateien. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>Status von nahe Duplikaten und e-Mail-Threads anzeigen

Die Ergebnisse der **Ziel** Population zeigen die Anzahl von Dokumenten, e-Mails, Anlagen und Fehlern in der Zielpopulation an. 
  
In den **Dokumenten** Ergebnissen werden die Anzahl von Pivots, eindeutige nahe Duplikate und exakte doppelte Dateien angezeigt. 
  
In **den e-Mail-Ergebnissen werden** die Anzahl der inklusiv-, einschließlich-, eindeutigen einschließlich-Kopien und der restlichen e-Mail-Nachrichten angezeigt. Die verschiedenen Arten von e-Mail-Ergebnissen sind: 
  
- **Inclusive**: eine inklusive e-Mail ist der abschließende Knoten in einem e-Mail-Thread und enthält alle vorherigen Verlaufsdaten dieses Threads. Folglich kann der Prüfer sich sicher auf die inklusive e-Mail konzentrieren, ohne die vorherigen Nachrichten im Thread lesen zu müssen. 
    
- **Inclusive minus**: eine inklusive e-Mail wird als inclusive minus festgelegt, wenn es eine oder mehrere verschiedene Anlagen gibt, die mit den übergeordneten Elemente der Inclusive-Nachricht verknüpft sind. In diesem Kontext wird der Begriff Parent für Nachrichten verwendet, die sich im e-Mail-Thread oder Unterhaltungen in dieser spezifischen e-Mail-Nachricht nach oben befinden. Ein Prüfer kann die inklusiv-minus Angabe als Signal verwenden, dass es möglicherweise nicht erforderlich ist, den Inhalt der inklusiven e-Mail-übergeordneten Elemente zu überprüfen, es kann jedoch hilfreich sein, die Anlagen zu überprüfen, die mit Eltern im inklusiven Pfad verknüpft sind. 
    
- **Inclusive-Kopie**: eine inklusive e-Mail wird als inklusiv-Kopie festgelegt, wenn es sich um die Kopie einer anderen Nachricht handelt, die als inklusiv oder inklusive minus gekennzeichnet ist. Mit anderen Worten: Diese Nachricht hat denselben Betreff und denselben Text wie eine andere einschließliche Nachricht, die sich als solche in demselben Knoten befindet. Da inklusive Copy-Nachrichten denselben Inhalt enthalten, können Sie in der Regel beim Überprüfungsprozess übersprungen werden. 
    
- **Der Rest**: Dies deutet darauf hin, dass e-Mails keine eindeutigen Inhalte enthalten und daher nicht in die vorherigen drei Kategorien fallen. Diese e-Mail-Nachrichten müssen nicht überprüft werden. Wenn eine Nachricht eine Anlage enthält, die sich nicht in einer späteren inclusive-e-Mail befindet, muss die Anlage möglicherweise überprüft werden. Dies wird durch das vorhanden sein einer inklusiven minus-e-Mail im Thread angezeigt.
    
In den **Anlagen** Ergebnissen wird die Anzahl der Anlagen angezeigt, die dem Typ "eindeutig" und "Duplikate" entsprechen. 
  
![Nahe Duplikate und e-Mail-Threads](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Dokument Ähnlichkeit](understand-document-similarity-in-advanced-ediscovery.md)
  
[Festlegen von Analyseoptionen](set-analyze-options-in-advanced-ediscovery.md)
  
[Festlegen von Text ignorieren](set-ignore-text-in-advanced-ediscovery.md)
  
[Einstellungen für die erweiterte Analyse Einstellung](view-analyze-results-in-advanced-ediscovery.md)

