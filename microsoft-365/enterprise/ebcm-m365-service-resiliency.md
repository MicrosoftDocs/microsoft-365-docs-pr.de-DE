---
title: Microsoft 365-Dienstausfallsicherheit
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Beschreibung des Resilienzthemas
ms.openlocfilehash: f2fd50a662076904daf3133e0edf45808ef2c39d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031050"
---
# <a name="built-in-resiliency"></a>Integrierte Resilienz

Als Ihr Cloud-Zusammenarbeitsanbieter erkennt Microsoft die Notwendigkeit, sich kontinuierlich Ihr Vertrauen zu verdienen, indem es Lösungen anbietet, die konsistent funktionieren und die Ihre Benutzer lieben. Wenn ein bestimmter Dienst nicht verfügbar ist, wird dies als Ausfallzeit bezeichnet. Die Definition von Ausfallzeit variiert für jeden Microsoft 365-Dienst, aber sie konzentriert sich in der Regel auf jeden Zeitraum, in dem Benutzer die wesentlichen Funktionen des Dienstes nicht nutzen können. Hier ist beispielsweise die Definition von Ausfallzeit für SharePoint Online, die vom Microsoft 365-SLA (Vereinbarung zum Servicelevel) abgenommen wird:

**"Ausfallzeit von SharePoint Online**: Jeder Zeitraum, in dem Benutzer keine Teile einer SharePoint Online-Websitesammlung lesen oder schreiben können, für die Sie über die entsprechenden Berechtigungen verfügen."

Sie finden die Definitionen für Ausfallzeiten in den [Vereinbarungen zum Servicelevel](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

Um die Ausfallzeiten – geplant oder unerwartet – zu minimieren, sind Microsoft 365-Dienste so konzipiert und ausgeführt, dass Sie hochgradig verfügbar und Ausfall resistent sind, indem Sie sich auf vier Bereiche konzentrieren:

## <a name="activeactive-design"></a>Aktiv/Aktiv-Ausführung

In Microsoft 365 streben wir danach, dass alle Dienste in einer aktiven/aktiven Ausführung entwickelt und betrieben werden, was die Resilienz erhöht. Dies bedeutet, dass immer mehrere Instanzen eines Diensts ausgeführt werden, die auf Benutzeranforderungen reagieren und in geografisch verteilten Rechenzentren gehostet werden. Der gesamte Benutzerdatenverkehr wird über den Microsoft Front Door-Dienst durchgeführt. Er wird automatisch an die optimal lokalisierte Instanz des Diensts und zu allen Dienstfehlern geleitet, um die Auswirkungen auf die Kunden zu verhindern oder zu verringern.

## <a name="reduce-incident-scope"></a>Reduzieren des Vorfallumfangs

Der Umfang eines Dienstvorfalls wird anhand des Schweregrads, der Dauer und der Anzahl der Kunden ermittelt. Wir sind bestrebt, den Umfang aller Vorfälle zu begrenzen durch:

- mehrere Instanzen jedes Dienstes voneinander getrennt zu haben
- die kontrollierte, abgestufte Bereitstellung von Updates mit Hilfe von Validierungsringen, so dass alle Probleme, die sich aus dem Update ergeben könnten, frühzeitig im Bereitstellungsprozess erkannt und behoben werden können. Auf diese Weise wird die Regression des Updates gegebenenfalls in einer kleinen Gruppe innerhalb von Microsoft (innerer Ring) durchgeführt, bevor es in größeren Gruppen bereitgestellt wird, z. B. in allen 140 000 Microsoft-Mitarbeitern (Ring 2), dann in Early Adopter Ringen (Ring 3) und schließlich an alle Kunden weltweit (Ring 4).
- Verbesserungen bei der Überwachung durch Automatisierung. Microsoft 365 ist sehr umfangreich, und die Verfügbarkeit des SLA-Ziels ist hoch. Am Anfang eines Dienstvorfalls, wenn Menschen an der Erkennung und Reaktion beteiligt sein mussten, konnten wir nicht schnell genug reagieren, um SLAs zu erfüllen. Die Automatisierung ist der Schlüssel für die schnelle und effektive Erkennung und Reaktion von Dienstvorfällen. Je früher wir etwas wissen, desto schneller lässt es sich beheben.

Zusammen mit den in der Microsoft 365-Dienstearchitektur integrierten Aktiv/Aktiv-Funktionen mindern diese Maßnahmen den Schweregrad, die Dauer und die Anzahl der betroffenen Kunden während eines Dienstvorfalls.  

## <a name="fault-isolation"></a>Fehlerisolation

So wie die Dienste aktiv/aktiv konzipiert und betrieben werden und voneinander getrennt sind, um zu verhindern, dass ein Fehler in einem Dienst einen anderen beeinflusst, wird die Codebasis des Dienstes nach ähnlichen Partitionsprinzipien entwickelt, der sogenannten Fehlerisolation. Maßnahmen zur Fehlerisolation sind inkrementelle Schutzmaßnahmen, die innerhalb der Codebasis selbst durchgeführt werden. Diese Maßnahmen tragen dazu bei, dass ein Problem in einem Bereich nicht in andere Betriebsbereiche übergeht.
Maßnahmen zur Fehlerisolation werden in mehreren Phasen der Entwicklung und Bereitstellung eines Dienstes angewendet, einschließlich Codeentwicklung, Dienstbereitstellung, Lastausgleich und Datenbankreplikation.

Der Microsoft Security Development Lifecycle (SDL) fördert die Resilienz weiter und besteht aus einer Reihe von Praktiken, die Sicherheits-und Compliance-Anforderungen unterstützen. SDL leitet unsere Entwickler in den Aufbau widerstandsfähiger, sicherer und kompatibler Dienste. Zu den Schlüsselelementen von SDL gehören Codeüberprüfungen, Bedrohungsmodellierung, Penetrationstests und standardisierte Prozesse zur Ereignisreaktion in der Microsoft-Cloud.

M365-Dienste sind hochgradig miteinander verbunden, aber die Systeme und Technologien dahinter sind so konzipiert, dass sie die Auswirkungen eines Dienstereignisses auf andere Dienste begrenzen. So hat beispielsweise ein Problem mit Exchange Online keinen Einfluss auf die Kernfunktionalität in Teams, oder ein Problem mit der Suchfunktionalität in SharePoint Online hat keinen Einfluss auf die Fähigkeit der Benutzer, Dateien hoch- oder herunterzuladen.

## <a name="continuous-service-improvement"></a>Kontinuierliche Serviceverbesserung

Wenn wir einen Vorfall erleben, nehmen wir ihn ernst. Denn unsere redundante Cloud-Architektur und strenge interne Prozesse zielen darauf ab, unsere Dienste barrierefrei zu halten. Während eines Vorfalls erkennt unsere Überwachung schnell die betroffenen Dienste und, wenn Ihr Mandant betroffen ist, werden Sie sofort über eine Vielzahl von Kanälen benachrichtigt. Gleichzeitig folgen Entwickler genau definierten Prozessen, um das Problem zu analysieren, und führen die erforderlichen Schritte aus, um den normalen Betrieb so schnell wie möglich wiederherzustellen. Sobald der Dienst ordnungsgemäß funktioniert, führen wir im Rahmen des Zyklus der kontinuierlichen Serviceverbesserung Post Incident Reviews durch. Während der Post Incident Review identifizieren wir die eigentlichen Ursachen des Vorfalls und was zur Behebung der Probleme erforderlich war. Anschließend nehmen wir das, was aus der Situation gelernt wurde, und wenden es auf die Entwicklung und den Betrieb aller unserer Angebotspakete an. Auf diese Weise können wir verhindern, dass die gleiche Ursache andere Dienste und zusätzliche Kunden beeinträchtigt.
