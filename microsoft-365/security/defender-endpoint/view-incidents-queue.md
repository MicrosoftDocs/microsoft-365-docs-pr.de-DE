---
title: Anzeigen und Organisieren der Vorfallswarteschlange
ms.reviewer: ''
description: Sehen Sie sich die Liste der Vorfälle an, und erfahren Sie, wie Sie Filter anwenden, um die Liste zu beschränken und eine fokussierte Ansicht zu erhalten.
keywords: view, organize, incidents, aggregate, investigations, queue, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499934"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Anzeigen und Organisieren der Microsoft Defender for Endpoint Incidents-Warteschlange

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Die **Incidents-Warteschlange** zeigt eine Sammlung von Vorfällen an, die von Geräten in Ihrem Netzwerk gekennzeichnet wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.

Standardmäßig werden in der Warteschlange Vorfälle angezeigt, die in den letzten 30 Tagen angezeigt wurden, und der letzte Vorfall wird oben in der Liste angezeigt, damit Sie die neuesten Vorfälle zuerst sehen können.

Es stehen mehrere Optionen zur Verfügung, um die Warteschlangenansicht "Vorfälle" anzupassen. 

Im oberen Navigationsbereich können Sie:
- Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten 
- Ändern der Anzahl der Elemente, die pro Seite angezeigt werden
- Auswählen der Elemente, die pro Seite angezeigt werden soll
- Batchauswahl der zuzuordnenden Vorfälle 
- Navigieren zwischen Seiten
- Anwenden von Filtern

![Abbildung einer Vorfallswarteschlange](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>Sortieren und Filtern der Warteschlange für Vorfälle
Sie können die folgenden Filter anwenden, um die Liste der Vorfälle zu begrenzen und eine fokussierte Ansicht zu erhalten.

### <a name="severity"></a>Severity

Schweregrad des Vorfalls | Beschreibung
:---|:---
Hoch </br>(Rot) | Bedrohungen, die häufig mit erweiterten beständigen Bedrohungen (Advanced Persistent Threats, APT) verbunden sind. Diese Vorfälle deuten auf ein hohes Risiko aufgrund des Schweregrads des Schadens hin, den sie auf Geräten anrichten können.
Mittel </br>(Orange) | Bedrohungen, die in der Organisation selten beobachtet werden, z. B. anomale Registrierungsänderung, Ausführung verdächtiger Dateien und beobachtete Verhaltensweisen, die für Angriffsphasen typisch sind.
Niedrig </br>(Gelb) | Bedrohungen im Zusammenhang mit weit verbreiteter Schadsoftware und Hacktools, die nicht unbedingt auf eine erweiterte Bedrohung für die Organisation hindeuten.
Informational </br>(Grau) | Informationsvorfälle werden möglicherweise nicht als schädlich für das Netzwerk betrachtet, aber es ist möglicherweise gut, den Überblick zu behalten.

## <a name="assigned-to"></a>Zugewiesen an
Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.

### <a name="category"></a>Kategorie
Vorfälle werden basierend auf der Beschreibung der Phase kategorisiert, in der sich die Cybersicherheitstötekette befindet. Diese Ansicht hilft dem Bedrohungsanalysten bei der Bestimmung der Priorität, Dringlichkeit und der entsprechenden Reaktionsstrategie, die basierend auf dem Kontext bereitgestellt werden soll.

### <a name="status"></a>Status
Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.

### <a name="data-sensitivity"></a>Vertraulichkeit der Daten
Verwenden Sie diesen Filter, um Vorfälle mit Vertraulichkeitsbezeichnungen zu zeigen.

## <a name="incident-naming"></a>Vorfallbenennung

Um den Umfang des Vorfalls auf einen Blick zu verstehen, werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien generiert.

Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*

> [!NOTE]
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihren Namen.


## <a name="see-also"></a>Siehe auch
- [Vorfallswarteschlange](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)

