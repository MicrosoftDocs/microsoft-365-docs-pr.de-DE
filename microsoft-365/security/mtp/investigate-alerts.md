---
title: Untersuchen von Warnungen in Microsoft 365 Defender
description: Untersuchen Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c4a67a6b0df9308e9e61733a951a5016fa69c082
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50928698"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Untersuchen von Warnungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Warnungen sind die Grundlage aller Vorfälle und geben das Auftreten von böswilligen oder verdächtigen Ereignissen in Ihrer Umgebung an. Warnungen sind in der Regel Teil eines umfassenderen Angriffs und liefern Hinweise zu einem Vorfall.

In Microsoft 365 Defender werden verwandte Warnungen zu Vorfällen zusammengefasst. Vorfälle bieten immer den umfassenderen Kontext eines Angriffs. Es kann jedoch hilfreich sein, Warnungen zu untersuchen, wenn eine tiefergehende Analyse erforderlich ist. 



## <a name="using-alert-pages-in-investigations"></a>Verwenden von Warnungsseiten in Untersuchungen

Auf der Registerkarte Warnungen auf jeder Vorfallseite gelangen Sie durch Auswählen einer Warnung zu den einzelnen Warnungsseiten. Eine Warnungsseite besteht aus drei Abschnitten: betroffenen Ressourcen, Warnungsabschnitt und Detailbereich.

![Abbildung der Beispielbenachrichtigungsseite](../../media/new-alert-page2.png)

Auf einer Warnungsseite können Sie das Symbol mit drei Punkten (**...**) neben jeder Entität auswählen, damit Sie verfügbare Aktionen wie das Öffnen der bestimmten Objektseite oder bestimmte Korrekturschritte sehen können.

### <a name="analyze-affected-assets"></a>Analysieren betroffener Objekte
Im Abschnitt betroffene Objekte werden Postfächer, Geräte und Benutzer aufgeführt, die von dieser Warnung betroffen sind. Wenn Sie eine der Objektkarten auswählen, wird der Detailseitenbereich mit Informationen auffüllt, einschließlich anderer Warnungen, die im Zusammenhang mit den Ressourcen aufgetreten sind.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>Verfolgen der Rolle einer Warnung im Warnungsstory
Der Warnungsstory zeigt alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht an. Die Warnung im Titel ist die Warnung, die beim ersten Landen auf der Seite der ausgewählten Warnung im Fokus steht. Objekte im Warnungsstory können erweitert und angeklickt werden. Sie bieten zusätzliche Informationen und beschleunigen die Reaktion, indem Sie Aktionen direkt im Kontext der Warnungsseite ausführen können. 

> [!NOTE]
> Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, und zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur werden vor oder nach der ausgewählten Warnung angezeigt.

### <a name="view-more-alert-information-in-the-details-pane"></a>Weitere Benachrichtigungsinformationen im Detailbereich anzeigen

Im Detailbereich werden zunächst die Details der ausgewählten Warnung mit Details und Aktionen angezeigt. Wenn Sie eine der betroffenen Objekte oder Entitäten im Warnungsstory auswählen, wird der Detailbereich geändert, um kontextbezogene Informationen und Aktionen für das ausgewählte Objekt zur Verfügung zu stellen.

Nachdem Sie eine entität von Interesse ausgewählt haben, ändert sich der Detailbereich so, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, sobald diese verfügbar ist, und Optionen zum Ergreifen von Aktionen für diese Entität direkt auf der Warnungsseite angezeigt werden.

### <a name="manage-alerts"></a>Verwalten von Warnungen

Nachdem Sie die Untersuchung der Warnungen durchgeführt haben, können Sie zurück zu der Benachrichtigung, mit der Sie begonnen haben, den Status der Warnung als Aufgelöst markieren und als False- oder True-Warnung klassifizieren. Das Klassifizieren von Warnungen trägt dazu bei, Ihr Produkt so zu optimieren, dass mehr echte Warnungen und weniger falsche Warnungen angezeigt werden.

> [!NOTE]
> Eine Möglichkeit zum Verwalten von Warnungen mithilfe von Tags. Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell ausgeführt und befindet sich derzeit in der Vorschau. <br>
> Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die nach *dem Update* erstellt wurden. Warnungen, die vor der Änderung generiert wurden, spiegeln nicht den aktualisierten Tagnamen wider. 


## <a name="manage-the-unified-alert-queue"></a>Verwalten der einheitlichen Warnungswarteschlange

Durch Auswählen von Warnungen & Warnungen im Navigationsbereich des Microsoft 365 Security Center werden Sie zur einheitlichen Warnungswarteschlange angezeigt. Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender for Endpoint, Microsoft Defender für Office 365 und Microsoft 365 Defender werden in diesem Abschnitt angezeigt. 

![Abbildung der Beispielwarnungsseite](../../media/unified-alert-queue.png)

Die Warnungswarteschlange zeigt eine Liste der Warnungen an, die in Ihrem Netzwerk gekennzeichnet wurden. Standardmäßig werden in der Warteschlange Warnungen angezeigt, die in den letzten 30 Tagen angezeigt wurden. Die neuesten Warnungen werden am Anfang der Liste angezeigt, damit Sie zuerst die neuesten Warnungen sehen können.

> [!NOTE]
> Zum Zeitpunkt des Startes ist die Warteschlange für einheitliche Warnungen nur für 7 Tage mit Microsoft Defender für Office 365-Warnungen verfügbar. Die Warteschlange wird im Laufe der Zeit weiter aufbaut. Wenn Sie Warnungen vor dem Start der einheitlichen Benachrichtigungswarteschlange triagen müssen, verwenden Sie die Benachrichtigungswarteschlange im [Security and Compliance Center](https://protection.office.com/viewalerts).


Im oberen Navigationsbereich können Sie:

- Anwenden von Filtern
- Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten
- Exportieren von Daten

Sie können Warnungen auch nach unterschiedlichen Kriterien filtern:

- Severity
- Status
- Kategorie
- Erkennungsquelle
- Richtlinie
- Auswirkungen auf Ressourcen
- Erste Aktivität
- Letzte Aktivität


Lesen Sie Untersuchen von Vorfällen [in Microsoft 365 Defender,](investigate-incidents.md) um eine Untersuchung zu einem Vorfall zu starten.
## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
