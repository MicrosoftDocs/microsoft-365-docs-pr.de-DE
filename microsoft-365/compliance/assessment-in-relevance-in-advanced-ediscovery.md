---
title: Verstehen der Relevanzbewertung in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Verschaffen Sie sich einen Überblick über die Bewertungsphase und deren Rolle bei der Bestimmung der Vielfalt von Problemen während der Relevanzschulung in Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769276"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Bewertung im Relevanzmodul in Advanced eDiscovery
  
Advanced eDiscovery ermöglicht eine frühzeitige Bewertung, z. B. für die definierten Probleme und die für einen Fall importierten Daten. Advanced eDiscovery kann der Experte Entscheidungen zu einem angenommenen Ansatz treffen und diese Entscheidungen auf das Dokumentüberprüfungsprojekt anwenden.
  
## <a name="understanding-assessment"></a>Grundlegendes zur Bewertung

In Assessment überprüft der Experte einen zufälligen Satz von mindestens 500 Dateien, die verwendet werden, um den Reichhaltigen der Probleme zu ermitteln und Statistiken zu erstellen, die die Schulungsergebnisse widerspiegeln. Die Bewertung ist erfolgreich, wenn genügend relevante Dateien gefunden werden, um eine statistische Ebene zu erreichen, die Advanced eDiscovery Relevanz für die Bereitstellung präziser Statistiken und die effektive Bestimmung des Stabilisierungspunkts im Schulungsprozess hilft. 
  
Je höher die Anzahl relevanter Dateien im Bewertungssatz, desto genauer sind die Statistiken und die Effektivität des Stabilitätsalgorithmus. Die Anzahl relevanter Dateien in den Bewertungsdateien hängt vom Reichhaltigen des Problems ab. Richness ist der geschätzte Prozentsatz der relevanten Dateien in der Gruppe, die für ein Problem relevant sind. Probleme mit einem höheren Reichhaltigen erreichen schneller eine höhere Anzahl relevanter Dateien als Probleme mit geringerem Reichhaltigem. Probleme mit extrem geringem Reichhaltigem (z. B. 2 % oder weniger) erfordern einen sehr großen Bewertungssatz, um eine beträchtliche Anzahl relevanter Dateien zu erreichen.
  
Die Statistiken, die während der Schulung und nach der Batchberechnung auf den Registerkarten Nachverfolgen und Entscheiden angezeigt werden, enthalten Schätzungen des Rückrufs für verschiedene Überprüfungssätze. In der Statistik enthalten Schätzungen, die auf einem Beispielsatz basieren (in diesem Fall die Bewertungsdateien), die Fehlermarge und das Konfidenzniveau dieser Fehlerspanne. Beispielsweise kann der geschätzte Rückruf von 80 % eine Fehlermarge von plus oder minus 5 % mit einem Konfidenzniveau von 95 % haben. Dies bedeutet, dass der geschätzte Rückruf tatsächlich 75 %-85 % beträgt und diese Schätzung 95 % Vertrauen hat. Je größer der Bewertungssatz, desto kleiner wird der Fehlerrand, und die Statistiken sind genauer. 
  
Nachdem der Experte einen ersten Bewertungssatz von 500 Dateien überprüft hat, kann die Relevanz den aktuellen Fehlerrand der Rückrufwerte bestimmen. Die Relevanz empfiehlt außerdem eine Standardfehlermarge, um den Bewertungssatz zu optimieren. Hier sind einige Beispiele:
  
- Wenn der Bewertungssatz bereits eine Fehlermarge von plus oder minus 10 % ergeben hat, empfiehlt relevanz den Wechsel zu Schulungen (es ist keine zusätzliche Bewertungsprüfung erforderlich). 

- Wenn der Bewertungssatz eine Fehlermarge von plus oder minus 13 % ergeben hat, empfiehlt die Relevanz möglicherweise die Überprüfung einer anderen Gruppe von Bewertungsdateien, um einen kleineren Rand zu erreichen. 

- Wenn der Reichhaltige extrem niedrig ist, empfiehlt die Relevanz möglicherweise, die Bewertung zu beenden, obwohl die Fehlermarge groß ist (was Statistiken unpraktisch macht), da der Bewertungssatz, der zum Erreichen einer nützlichen Fehlermarge erforderlich ist, zu groß ist.

Jedes Problem verfügt über einen eigenen Rich-In-Wert, einen aktuellen Fehlerrand und als Ergebnis eine geschätzte Anzahl zusätzlicher Bewertungsdateien. Der nächste Bewertungssatz wird entsprechend der maximalen Anzahl von Dateien (bis zu 1.000 in einem einzigen Satz) erstellt.
  
Sie können die Relevanzempfehlungen akzeptieren oder den aktuellen Fehlerrand entsprechend Ihren Anforderungen anpassen. Der aktuelle Standardfehlerrand wird für den Rückruf auf mindestens 75 % festgelegt.
  
> [!NOTE]
> Die Bewertungsphase kann auf der **\>** Registerkarte Relevanzspur in der erweiterten Ansicht für ein Problem umgangen werden, indem das Kontrollkästchen **Bewertung** pro Problem und dann für "alle Probleme" behoben wird. Daher gibt es keine Statistiken für dieses Problem. Das **Kontrollkästchen Bewertung** kann nur vor der Bewertung benennen. Wenn in einem Fall mehrere Probleme vorhanden sind, wird die Bewertung nur umgangen, wenn das Kontrollkästchen für jedes Problem behoben ist.
