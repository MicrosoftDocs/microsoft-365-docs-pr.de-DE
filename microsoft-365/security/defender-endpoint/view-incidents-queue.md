---
title: Anzeigen und Organisieren der Vorfallswarteschlange
ms.reviewer: ''
description: Sehen Sie sich die Liste der Vorfälle an, und erfahren Sie, wie Sie Filter anwenden, um die Liste einzuschränken und eine stärker fokussierte Ansicht zu erhalten.
keywords: anzeigen, organisieren, Vorfälle, aggregieren, Untersuchungen, Warteschlange, ttp
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
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844220"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Anzeigen und Organisieren der Warteschlange für Microsoft Defender für Endpunktvorfälle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die von Geräten in Ihrem Netzwerk gekennzeichnet wurden. Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.

Standardmäßig zeigt die Warteschlange Vorfälle an, die in den letzten 30 Tagen aufgetreten sind, wobei der letzte Vorfall oben in der Liste angezeigt wird, damit Sie die neuesten Vorfälle zuerst sehen können.

Es gibt mehrere Optionen, aus denen Sie auswählen können, um die Vorfallwarteschlangenansicht anzupassen. 

In der oberen Navigationsleiste haben Sie folgende Möglichkeiten:
- Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten 
- Ändern der Anzahl der Elemente, die pro Seite angezeigt werden sollen
- Auswählen der Elemente, die pro Seite angezeigt werden sollen
- Batchauswahl der zuzuweisenden Vorfälle 
- Navigieren zwischen Seiten
- Anwenden von Filtern

![Abbildung einer Vorfallswarteschlange](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>Sortieren und Filtern der Vorfallwarteschlange
Sie können die folgenden Filter anwenden, um die Liste der Vorfälle einzuschränken und eine stärker fokussierte Ansicht zu erhalten.

### <a name="severity"></a>Severity

Schweregrad des Vorfalls | Beschreibung
:---|:---
Hoch </br>(Rot) | Bedrohungen, die häufig mit erweiterten dauerhaften Bedrohungen (Advanced Persistent Threats, APT) verbunden sind. Diese Vorfälle weisen aufgrund des Schweregrads des Schadens, den sie auf Geräten verursachen können, auf ein hohes Risiko hin.
Mittel </br>(Orange) | Bedrohungen, die in der Organisation selten beobachtet werden, z. B. anomale Registrierungsänderungen, Ausführung verdächtiger Dateien und beobachtete Verhaltensweisen, die typisch für Angriffsphasen sind.
Niedrig </br>(Gelb) | Bedrohungen im Zusammenhang mit weit verbreiteter Schadsoftware und Hack-Tools, die nicht notwendigerweise auf eine erweiterte Bedrohung für die Organisation hinweisen.
Zur Information </br>(Grau) | Informationsvorfälle werden möglicherweise nicht als schädlich für das Netzwerk betrachtet, können aber gut nachverfolgt werden.

## <a name="assigned-to"></a>Zugewiesen an
Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.

### <a name="category"></a>Kategorie
Vorfälle werden basierend auf der Beschreibung der Phase kategorisiert, in der sich die Cybersicherheits-Kill Chain befindet. Diese Ansicht hilft dem Bedrohungsanalysten, Priorität, Dringlichkeit und entsprechende Reaktionsstrategie zu bestimmen, die basierend auf dem Kontext bereitgestellt werden soll.

### <a name="status"></a>Status
Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.

### <a name="data-sensitivity"></a>Vertraulichkeit der Daten
Verwenden Sie diesen Filter, um Vorfälle anzuzeigen, die Vertraulichkeitsbezeichnungen enthalten.

## <a name="incident-naming"></a>Benennung von Vorfällen

Um den Umfang des Vorfalls auf einen Blick zu verstehen, werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl der betroffenen Endpunkte, betroffenen Benutzern, Erkennungsquellen oder Kategorien generiert.

Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*

> [!NOTE]
> Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen aufgetreten sind, behalten ihren Namen.


## <a name="see-also"></a>Siehe auch
- [Vorfallswarteschlange](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)

