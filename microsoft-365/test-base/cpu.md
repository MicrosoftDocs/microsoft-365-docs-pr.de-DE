---
title: CPU-Regressionsanalyse
description: Grundlegendes zu Regressionsergebnissen und Metriken für die CPU-Auslastung
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
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322720"
---
# <a name="intelligent-cpu-regression-analysis"></a>Intelligente CPU-Regressionsanalyse

Die CPU-Auslastung kann angeben, ob eine Anwendung von einem Betriebssystemupdate betroffen ist. 

Die Testbasis für Microsoft 365 bietet Softwareentwicklern einen Einblick in CPU-Leistungsregressionen, die auftreten, wenn ihre Anwendung unter verschiedenen Versionen eines bevorstehenden Betriebssystemupdates (Windows Betriebssystem) ausgeführt wird. 

Diese CPU-Regressionen ermöglichen Es Entwicklern, Anwendungsprobleme (und potenzielle Fehler) zu erkennen und zu beheben, bevor das Betriebssystemupdate allgemein bereitgestellt wird, wodurch eine schlechte Benutzererfahrung verhindert wird.


### <a name="how-cpu-regression-analysis-works"></a>Funktionsweise der CPU-Regressionsanalyse ###

Als Testbasisbenutzer können Sie die Binärdateien Ihrer Anwendung (in einer einzelnen .zip-Datei) zusammen mit den zugehörigen Testskripts hochladen und die Windows Betriebssystemversion auswählen, mit der Sie Ihre Anwendung im Testbasisportal in Azure testen möchten. 

Der Testbasisdienst führt dann die Testskripts aus und führt die **CPU-Regressionsanalyse** aus. 

Der Dienst überprüft, ob die CPU-Auslastung für die Anwendung in der Vorabversion des Updates für das Zielbetriebssystem mit der CPU-Auslastung für die veröffentlichte Version des Betriebssystems in Einklang steht. 

Die CPU-Auslastung ist kein 100%iger vergleichsähnlicher Vergleich, da die Prozesse, die auf den beiden Versionen des Betriebssystems ausgeführt werden, aufgrund unterschiedlicher Betriebssystemversionen möglicherweise eine genaue Übereinstimmung darstellen. Die von Test Base durchgeführte Analyse kann jedoch zeigen, ob die CPU-Auslastung für Ihre Anwendung von einem bevorstehenden Betriebssystemupdate betroffen ist und welche Prozesse aus vorherigen Testläufen zurückgeleitet wurden.

In der folgenden Momentaufnahme gibt es zwei Betriebssystemversionen, mit denen die CPU-Auslastung für dieselbe Anwendung verglichen wird. 
-   Auf der Registerkarte "CPU-Auslastung" werden die oberen und unteren Begrenzungen der Auslastung für beide Versionen jeweils am 90. und 10. Quantil angezeigt. 
-   Die Diagramme zeigen die Zeitreihe der CPU-Auslastung zusammen mit der durchschnittlichen Auslastung. 

Kunden können nun anhand der Funktionalität ermitteln, ob die CPU-Auslastung ihrer Anwendung durch Betriebssystemupdates beeinträchtigt wird und welche Prozesse von der vorherigen Ausführung zurückgeleitet wurden.


![CPU-Regressionsanalyse](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>Relevante Prozessidentifikation ###

Hier wird erläutert, wie sie zurückgeleitete Prozesse in der Anwendung identifizieren können. 

Die Analyse der Leistungsregression erfordert das Nachverfolgen verschiedener Arten von Leistungsindikatoren für jeden Prozess, der während des Testlaufs auf einem virtuellen Computer ausgeführt wird. 

Bei einer solchen Analyse werden viele Variablen für viele Prozesse für eine bestimmte Anwendung erfasst. Nicht alle Prozesse sind einer Ausführung oder Anwendung zugeordnet. Um diese Herausforderung zu umgehen, wird mithilfe der Wahrscheinlichkeits- und Informationsthematik ein Algorithmus zur gegenseitigen Informationsbewertung angewendet, um herauszufinden, welche Prozesse für eine bestimmte Anwendung am relevantesten sind. 

Eine Anwendung kann als ein Typ diskreter Zufallsvariablen betrachtet werden, während ein Prozess als eine andere Art diskreter Zufallsvariablen betrachtet wird. Die Zuordnung der beiden Zufallsvariablen wird mit bedingten Wahrscheinlichkeiten für die Relevanz gemessen. 

Prozesse werden dann in der Reihenfolge ihrer Relevanz für jede Anwendung angezeigt. Sie können auch eine Teilmenge von Prozessen als Favorit verwenden, die standardmäßig zusammen mit relevanten Prozessen für die CPU-Regressionsanalyse überwacht werden können. Sobald eine Regression erkannt wurde, können Sie das Windows Performance Analyzer-Toolkit herunterladen und die Gründe für CPU-Leistungsregressionen analysieren. 

Die Windows Performance Analyzer verwendet Ereignisablaufverfolgungsprotokoll (Event Trace Log, ETL) als Eingaben, und diese ETL-Dateien sind in den Protokolldateien verfügbar, die für Testläufe im Portal herunterladbar sind. Weitere Informationen zum Debuggen der CPU-Leistung finden Sie in der Dokumentation Windows Performance Analyzer.

