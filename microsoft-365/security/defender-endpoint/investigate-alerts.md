---
title: Untersuchen von Microsoft Defender für Endpunkt-Warnungen
description: Verwenden Sie die Untersuchungsoptionen, um Details zu Warnungen zu erhalten, die Sich auf Ihr Netzwerk auswirken, was sie bedeuten und wie Sie diese beheben können.
keywords: untersuchen, Untersuchung, Geräte, Gerät, Warnungswarteschlange, Dashboard, IP-Adresse, Datei, übermitteln, Übermittlungen, umfassende Analyse, Zeitachse, Suche, Domäne, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841090"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Untersuchen von Warnungen in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

Untersuchen Sie Warnungen, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten und wie Sie diese beheben können.

Wählen Sie eine Warnung aus der Warnungswarteschlange aus, um zur Warnungsseite zu wechseln. Diese Ansicht enthält den Warnungstitel, die betroffenen Ressourcen, den Detailseitenbereich und den Warnungsartikel.

Beginnen Sie ihre Untersuchung auf der Warnungsseite, indem Sie die betroffenen Ressourcen oder entitäten unter der Warnungs-Story-Strukturansicht auswählen. Der Detailbereich wird automatisch mit weiteren Informationen zu den ausgewählten Elementen aufgefüllt. Um zu sehen, welche Art von Informationen Sie hier anzeigen können, lesen Sie ["Warnungen überprüfen" in Microsoft Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/review-alerts)

## <a name="investigate-using-the-alert-story"></a>Untersuchen der Verwendung des Warnungsartikels

Der Warnungsartikel beschreibt, warum die Warnung ausgelöst wurde, verwandte Ereignisse, die vor und nach der Warnung aufgetreten sind, sowie andere verwandte Entitäten.

Entitäten sind klickbar, und jede Entität, die keine Warnung ist, kann mithilfe des Erweiterungssymbols auf der rechten Seite der Karte dieser Entität erweitert werden. Die entität im Fokus wird durch einen blauen Streifen auf der linken Seite der Karte der Entität angezeigt, wobei die Warnung im Titel zuerst im Fokus steht.

Erweitern Sie Entitäten, um Details auf einen Blick anzuzeigen. Wenn Sie eine Entität auswählen, wird der Kontext des Detailbereichs auf diese Entität umgestellt, und Sie können weitere Informationen überprüfen und diese Entität verwalten. Wenn Sie *...* rechts neben der Entitätskarte auswählen, werden alle für diese Entität verfügbaren Aktionen angezeigt. Diese Aktionen werden im Detailbereich angezeigt, wenn diese Entität im Fokus steht.

> [!NOTE]
> Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, wobei zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur vor oder nach der ausgewählten Warnung angezeigt werden.

![Ein Beispiel für eine Warnung mit einer Warnung im Fokus und einigen erweiterten Karten](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>Ergreifen von Maßnahmen aus dem Detailbereich

Nachdem Sie eine interessante Entität ausgewählt haben, wird der Detailbereich so geändert, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn diese verfügbar sind, und Steuerelemente zum Ergreifen von **Maßnahmen** für diese Entität direkt über die Warnungsseite angezeigt werden.

Sobald Sie die Untersuchung abgeschlossen haben, kehren Sie zu der Warnung zurück, mit der Sie begonnen haben, markieren Sie den Status der Warnung als **aufgelöst,** und klassifizieren Sie sie als **"False"** oder **"True".** Das Klassifizieren von Warnungen hilft bei der Optimierung dieser Funktion, um mehr echte und weniger falsche Warnungen bereitzustellen.

Wenn Sie sie als echte Warnung klassifizieren, können Sie auch eine Bestimmung auswählen, wie in der abbildung unten dargestellt.

![Ein Codeausschnitt des Detailbereichs mit einer aufgelösten Warnung und erweiterter Dropdownliste zur Ermittlung](images/alert-details-resolved-true.png)

Wenn bei einer Branchenanwendung eine falsche Warnung auftritt, erstellen Sie eine Unterdrückungsregel, um diese Art von Warnung in Zukunft zu vermeiden.

![Aktionen und Klassifizierung im Detailbereich mit hervorgehobener Unterdrückungsregel](images/alert-false-suppression-rule.png)

> [!TIP]
> Wenn Sie Probleme haben, die oben nicht beschrieben sind, verwenden Sie die 🙂 Schaltfläche, um Feedback zu geben oder ein Supportticket zu öffnen.


## <a name="related-topics"></a>Verwandte Themen
- [Anzeigen und Organisieren der Microsoft Defender für Endpunkt-Warnungswarteschlange](alerts-queue.md)
- [Verwalten von Microsoft Defender für Endpunkt-Warnungen](manage-alerts.md)
- [Untersuchen einer Datei, die einer Defender für Endpunkt-Warnung zugeordnet ist](investigate-files.md)
- [Untersuchen von Geräten in der Liste "Defender für Endpunktgeräte"](investigate-machines.md)
- [Untersuchen einer IP-Adresse, die einer Defender für Endpunkt-Warnung zugeordnet ist](investigate-ip.md)
- [Untersuchen einer Domäne, die einer Defender für Endpunkt-Warnung zugeordnet ist](investigate-domain.md)
- [Untersuchen eines Benutzerkontos in Defender für Endpunkt](investigate-user.md)


