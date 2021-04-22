---
title: Analysieren von Warnungen in Microsoft 365 Defender
description: Analysieren Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reaktion, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939542"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a>Analysieren von Warnungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Warnungen sind die Grundlage aller Vorfälle und geben das Auftreten von böswilligen oder verdächtigen Ereignissen in Ihrer Umgebung an. Warnungen sind in der Regel Teil eines umfassenderen Angriffs und geben Hinweise zu einem Vorfall.

In Microsoft 365 Defender werden verwandte Warnungen zu Vorfällen [zusammengefasst.](incidents-overview.md) Vorfälle bieten immer den umfassenderen Kontext eines Angriffs. Die Analyse von Warnungen kann jedoch hilfreich sein, wenn eine tiefergehende Analyse erforderlich ist. 

Die **Warnungswarteschlange** zeigt den aktuellen Satz von Warnungen an. Sie erhalten die Benachrichtigungswarteschlange von **Incidents & alerts > Alerts** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Beispiel für die Benachrichtigungswarteschlange":::

Hier werden Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender for Endpoint, Microsoft Defender für Office 365 und Microsoft 365 Defender angezeigt.

Standardmäßig werden in der Benachrichtigungswarteschlange im Microsoft 365 Security Center die neuen und in Bearbeitung benachrichtigungen aus den letzten 30 Tagen angezeigt. Die letzte Warnung befindet sich am Anfang der Liste, damit Sie sie zuerst sehen können. 

In der Standardbenachrichtigungswarteschlange können  Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie eine Teilmenge der Warnungen angeben können. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Beispiel für den Filterbereich für die Benachrichtigungswarteschlange":::

Sie können Warnungen nach folgenden Kriterien filtern:

- Severity
- Status
- Kategorie
- Erkennungsquelle
- Tags
- Richtlinie
- Auswirkungen auf Ressourcen

## <a name="analyze-an-alert"></a>Analysieren einer Warnung

Um die Hauptbenachrichtigungsseite zu sehen, wählen Sie den Namen der Warnung aus. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Security Center":::

Sie können auch die Aktion **Hauptbenachrichtigungsseite öffnen** im Bereich **Warnung verwalten** auswählen.

Eine Warnungsseite besteht aus den folgenden Abschnitten: 

- Warnungsgeschichte
- Ergriffene Aktionen (einschließlich betroffener Objekte)
- Verwandte Ereignisse
- Zusammenfassungsdetails

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Security Center":::

Auf einer Warnungsseite können Sie neben jeder Entität die Ellipsen (**...**) auswählen, um verfügbare Aktionen zu sehen, z. B. das Öffnen der bestimmten Objektseite oder das Ausführen bestimmter Korrekturschritte.

### <a name="analyze-affected-assets"></a>Analysieren betroffener Objekte

Der **Abschnitt "Aktionen"** enthält eine Liste der betroffenen Objekte, z. B. Postfächer, Geräte und Benutzer, die von dieser Warnung betroffen sind. 

Sie können auch Ansicht **im Aktionscenter auswählen,** um die Registerkarte **Verlauf** des **Aktionscenters** im Microsoft 365 Security Center zu sehen. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Verfolgen der Rolle einer Warnung im Warnungsstory

Der Warnungsstory zeigt alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht an. Die Warnung im Titel ist die Warnung, die beim ersten Landen auf der Seite der ausgewählten Warnung im Fokus steht. Objekte im Warnungsstory können erweitert und angeklickt werden. Sie stellen zusätzliche Informationen zur Verfügung und beschleunigen Ihre Antwort, indem Sie direkt im Kontext der Warnungsseite Maßnahmen ergreifen können. 

> [!NOTE]
> Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, und zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur werden vor oder nach der ausgewählten Warnung angezeigt.

### <a name="view-more-alert-information-on-the-details-page"></a>Weitere Benachrichtigungsinformationen auf der Detailseite anzeigen

Die Detailseite zeigt die Details der ausgewählten Warnung mit Details und Aktionen im Zusammenhang mit dieser Warnung. Wenn Sie eine der betroffenen Objekte oder Entitäten im Warnungsstory auswählen, wird die Detailseite geändert, um kontextbezogene Informationen und Aktionen für das ausgewählte Objekt zur Verfügung zu stellen.

Nachdem Sie eine entität von Interesse ausgewählt haben, ändert sich die Detailseite so, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn sie verfügbar ist, und Optionen zum Ergreifen von Aktionen für diese Entität direkt auf der Warnungsseite angezeigt werden.

## <a name="manage-alerts"></a>Verwalten von Warnungen

Um eine Warnung zu verwalten, wählen Sie die Warnung in der Benachrichtigungswarteschlange in der Zeile aus, um einen **Warnungsbereich verwalten anzuzeigen.** Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Beispiel für den Zusammenfassungsbereich für eine Warnung":::

Im **Bereich Warnung verwalten** können Sie:

- Der Warnungsstatus (Neu, Aufgelöst, In Bearbeitung).
- Die Klassifizierung der Warnung (Nicht festgelegt, True Alert, False Alert).
- Für die Klassifizierung als echte Warnung ist der Typ der Bedrohung für die Warnung im **Feld Bestimmung.**
- Ein Kommentar zur Warnung.

> [!NOTE]
> Eine Möglichkeit zum Verwalten von Warnungen mithilfe von Tags. Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell ausgeführt und befindet sich derzeit in der Vorschau. <br>
> Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die nach *dem Update* erstellt wurden. Warnungen, die vor der Änderung generiert wurden, geben nicht den aktualisierten Tagnamen wieder. 

In diesem Bereich können Sie auch die folgenden zusätzlichen Aktionen ausführen: 

- Öffnen der Hauptbenachrichtigungsseite
- Konsultieren eines Microsoft-Bedrohungsexperten
- Anzeigen der Übermittlung
- Link zu einem anderen Vorfall
- Anzeigen der Warnung in einer Zeitachse
- Erstellen einer Unterdrückungsregel

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Beispiel für die Aktionen für eine Warnung im Microsoft 365 Security Center":::

Die Liste der zusätzlichen Aktionen hängt vom Typ der Warnung ab.

## <a name="resolve-an-alert"></a>Auflösen einer Warnung

Sobald Sie die Analyse einer Warnung durchgeführt haben und  diese aufgelöst werden kann, wechseln Sie zum Bereich Warnung verwalten  für die Warnung, markieren Sie den Status als **Aufgelöst,** und klassifizieren Sie sie entweder als False-Warnung oder **als True-Warnung.** Geben Sie bei echten Warnungen den Bedrohungstyp der Warnung im Feld **Bestimmung** an.

Das Klassifizieren von Warnungen und das Angeben ihrer Bestimmung trägt dazu bei, Microsoft 365 Defender so zu optimieren, dass mehr echte Warnungen und weniger falsch Warnungen angezeigt werden.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Analysieren von Vorfällen](investigate-incidents.md)
