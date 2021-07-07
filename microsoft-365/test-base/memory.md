---
title: Analyse der Speicherregression
description: Ableiten der Speicherregression
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322788"
---
# <a name="memory-regression-analysis"></a>Analyse der Speicherregression

Die Testbasis hilft Ihnen dabei, deutlich zu erkennen, dass die Auslastung des Arbeitsspeichers bei den virtuellen Testcomputern, auf denen Ihre Apps ausgeführt werden, deutlich zunimmt. Leistungsmetriken, z. B. die Speichernutzung, können ein Indikator für die allgemeine Anwendungsintegrität sein, und wir glauben, dass diese Ergänzung die optimale Leistung Ihrer Apps erheblich verbessern wird.

Lesen Sie weiter, um weitere Details zu erhalten, oder sehen Sie sich dieses Video an, um einen kurzen Überblick über die neuesten Verbesserungen zu erhalten. 

Weitere Informationen zur Fähigkeit der Testbasis für M365 zur Unterstützung der Regressionsanalyse finden Sie unter Regressionsergebnisse basierend auf der Prozesszulässigkeit.

<b>Genauerer Blick auf Speicherregressionen</b>

Das Dashboard "TestBasis für M365" zeigt den von Ihrer Anwendung verbrauchten Speicher auf einer neuen vorab veröffentlichten Windows-Aktualisierung an und vergleicht ihn mit dem Speicher, der vom letzten freigegebenen Windows-Update verwendet wurde. 

Mit den Verbesserungen dieses Monats wird die Speicherregressionsanalyse nun in Ihren bevorzugten Prozessen vorgestellt. Anwendungen können mehrere Prozesse enthalten, und Sie können Ihre bevorzugten Prozesse manuell über die Registerkarte "Zuverlässigkeit" auswählen. Unser Dienst identifiziert dann Speicherregressionen in diesen bevorzugten Prozessen, während Testläufe in verschiedenen Windows Updateversionen verglichen werden. Wenn eine Regression erkannt wird, sind Details zur Regression leicht verfügbar.

Sehen wir uns dieses Feature nun genauer an und erläutern, wie Sie Mithilfe von Windows Performance Analyzer Speicherregressionen beheben können.

Das durch eine Speicherregression verursachte Fehlersignal wird im Dashboard "TestBasis für M365" auf der Seite "Testergebnisse" unter "Speicherauslastung" angezeigt:

![Speicherauslastungsergebnisse](Media/01_memory-utilization-results.png)


Fehler für die Anwendung aufgrund einer höheren Speicherauslastung, wird auch wie ```Fail``` auf der Seite "Testzusammenfassung" angezeigt:

![Testzusammenfassungsergebnisse](Media/02_test-summary.png)

Indem wir diese Fehlersignale vorab bereitstellen, ist es unser Ziel, potenzielle Probleme deutlich zu kennzeichnen, die die Endbenutzererfahrung für Ihre Anwendung stören und beeinträchtigen können. 

Anschließend können Sie die Protokolldateien herunterladen und die Windows Performance Analyzer oder Ihr bevorzugtes Toolkit verwenden, um weitere Untersuchungen auszuführen. Sie können auch gemeinsam mit dem Test Base für M365-Team an der Behebung des Problems arbeiten und probleme vermeiden, die sich auf Endbenutzer auswirken.

Speichersignale werden auf der Registerkarte "Speicherauslastung" im Test base für M365-Dienst für alle Testläufe erfasst. Das folgende Beispiel zeigt eine kürzlich ausgeführte Testausführung mit der integrierten Anwendung "Memory Stress beim Qualmtest" gegen das Sicherheitsupdate vom August 2020 in der Vorabversion. (Diese Anwendung wurde von unserem Team geschrieben, um Speicherregressionen zu veranschaulichen.)

![Speicherregressionsergebnisse](Media/03_memory-regression%20comparison.png)

In diesem Beispiel hat der Bevorzugte Prozess "USLTestMemoryStress.exe" im Vergleich zum veröffentlichten Juli-Update durchschnittlich ca. 100 MB für das August-Update vor der Veröffentlichung genutzt, daher hat die Testbasis für M365 eine Regression identifiziert. 

Die anderen Prozesse – hier als "USLTestMemoryStress_Aux1.exe" und "USLTestMemoryStress_Aux2.exe" dargestellt – gehören ebenfalls zur gleichen Anwendung, verbrauchten jedoch ungefähr die gleiche Menge an Arbeitsspeicher für die beiden Versionen, sodass sie "übergeben" wurden und als fehlerfrei betrachtet wurden.

Die Regression im Hauptprozess wurde als "statistische Bedeutung" ermittelt, sodass der Dienst diesen Unterschied für den Benutzer kommuniziert und hervorgehoben hat. Wenn der Vergleich nicht von statistischer Bedeutung wäre, würde er nicht hervorgehoben. Die Speicherauslastung kann laut sein, daher verwenden wir statistische Modelle, um zwischen Builds und Versionen sinnvolle Unterschiede von unwichtigen Unterschieden zu unterscheiden. 

Ein Vergleich kann selten gekennzeichnet werden, wenn kein wahrer Unterschied (ein falsch positives Ergebnis) vorliegt. Dies ist jedoch ein notwendiger Kompromiss, um die Wahrscheinlichkeit einer korrekten Identifizierung von Regressionen (oder wahr positiven Ergebnissen) zu verbessern.

Der nächste Schritt besteht darin, zu verstehen, was die Speicherregression verursacht hat. Sie können die ZIP-Dateien für beide Ausführungen wie unten dargestellt über die Option "Protokolldateien herunterladen" herunterladen. 

Diese ZIP-Dateien enthalten die Ergebnisse Ihrer Testausführung, einschließlich Skriptergebnisse sowie Speicher- und CPU-Leistungsdaten, die in der ETL-Datei enthalten sind.

![Testdateien für Speicherregression](Media/04_memory-regression-test-files.png)

Sie können die Protokolle für die beiden Testläufe herunterladen und entzippen, dann die ETL-Datei in jedem Ordner suchen und sie in "target.etl" (für den Testlauf im Vorabversionsupdate) und "baseline.etl" (für den Testlauf auf dem letzten veröffentlichten Update) umbenennen, um die Untersuchung und Navigation zu vereinfachen.
 
## <a name="next-steps"></a>Nächste Schritte

Beginnen Sie mit dem nächsten Artikel, um mit dem Verständnis der intelligenten CPU-Regressionsanalyse zu beginnen.
> [!div class="nextstepaction"]
> [Nächster Schritt](cpu.md)

<!---
Add button for next page
-->
