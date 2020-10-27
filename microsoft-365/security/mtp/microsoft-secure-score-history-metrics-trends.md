---
title: Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele
description: Erhalten Sie Einblicke in Aktivitäten, die Ihre Microsoft Secure-Bewertung beeinträchtigt haben. Trends entdecken und Ziele festlegen.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Improvement Actions
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769244"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[Microsoft Secure Score](microsoft-secure-score.md) ist ein Maß für die Sicherheitslage einer Organisation mit einer höheren Zahl, die mehr Verbesserungs Aktionen anzeigt. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Erhalten Sie Einblicke in Aktivitäten, die Ihre Punktzahl beeinflusst haben.

Zeigen Sie auf der Registerkarte **Verlauf** ein Diagramm der Bewertung Ihrer Organisation über einen Zeitraum an.

Unter dem Diagramm finden Sie eine Liste aller Aktionen, die im ausgewählten Zeitbereich ausgeführt wurden, sowie deren Attribute, wie beispielsweise Ergebnis Punkte und Kategorie. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

![Aktivitätsverlauf](../../media/secure-score/secure-score-history-activity.png)

Wenn Sie die einer Aktivität zugeordnete Verbesserungs Aktion auswählen, wird das Flyout vollständige Verbesserungs Aktion angezeigt.

Um den gesamten Verlauf für diese bestimmte Verbesserungs Aktion anzuzeigen, wählen Sie den Link Verlauf im Flyout aus.

![Verlauf der Verbesserungs Aktion](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Trends entdecken und Ziele festlegen

Auf der Registerkarte **Metriken und Trends** finden Sie mehrere Graphen und Diagramme, die Ihnen einen besseren Einblick in Trends und festgelegte Ziele ermöglichen. Sie können den Datumsbereich für die gesamte Seite der Visualisierungen festlegen. Die Visualisierungen umfassen:

* **Ihre sichere Ergebnis Zone** – angepasst basierend auf den Zielen und Definitionen Ihrer Organisation für gute, ordnungsgemäße und ungültige Bewertungsbereiche.
* **Regressions Trend** – eine Zeitskala mit Punkten, die aufgrund von Konfigurations-, Benutzer-oder Geräteänderungen zurückgegangen sind.  
* **Vergleichs Trend** – wie die sichere Punktzahl Ihres Unternehmens mit anderen im Laufe der Zeit vergleicht. Diese Ansicht kann Linien enthalten, die den Bewertungsdurchschnitt von Organisationen mit ähnlicher Anzahl von Plätzen darstellt, sowie eine benutzerdefinierte Vergleichsansicht, die Sie festlegen können.
* **Trend zur Risikoakzeptanz** – Zeitskala der Verbesserungs Aktionen, die als "Risiko akzeptiert" gekennzeichnet sind.
* **Ergebnisänderungen** : Anzahl der erreichten Punkte, zurückgegebene Punkte, zusammen mit der nachfolgenden Ergebnis Änderung im angegebenen Datumsbereich.

### <a name="compare-your-score-to-organizations-like-yours"></a>Vergleichen Sie Ihre Punktzahl mit Organisationen wie Ihrem

Es gibt zwei Möglichkeiten, um zu sehen, wie sich Ihre Partitur mit Organisationen vergleicht, die Ihnen ähnlich sind. In beiden Diagrammen können Sie **Vergleiche verwalten** auswählen, um die Informationen Ihrer Organisation anzuzeigen und zu bearbeiten. Sie können auch einen benutzerdefinierten Vergleich basierend auf Industrie, Organisationsgröße, Lizenzen und Regionen erstellen.

#### <a name="comparison-bar-chart"></a>Vergleichs Balkendiagramm

Das Vergleichs Balkendiagramm ist die Registerkarte **Übersicht** . Zeigen Sie mit dem Mauszeiger auf das Diagramm, um die Möglichkeit zur Bewertung und Bewertung anzuzeigen. Die Vergleichsdaten werden anonymisiert, sodass wir nicht genau wissen, welche anderen Mandanten sich in der Mischung befinden.

![Balkendiagramm der Partituren einer ähnlichen Organisation](../../media/secure-score/secure-score-comparison-bar.png)

- **Organisationen wie Ihre** : Wir geben Ihnen eine durchschnittliche Punktzahl anderer Mandanten (vorausgesetzt, es müssen mindestens 5 Mandanten miteinander verglichen werden), die mit den folgenden Kriterien in Frage kommen:
    1. Gleiche Branche
    2. Gleiche Organisationsgröße
    3. Alle Regionen
    4. Verwendete Microsoft-Produkte sind 80% ähnlich
    5. Verkaufschance (maximale Punktzahl, die mit der aktuellen Lizenz erzielt werden kann) innerhalb eines Bereichs von 20% von Ihrem Mandanten

- **Benutzerdefinierter Vergleich** : muss zunächst durch Auswählen von **Vergleich verwalten** (nur wenn wir 5 oder mehr Mandanten finden) basierend auf den folgenden Kriterien eingerichtet werden:
    1. Ausgewählte Branche (n)
    2. Ausgewählte Organisationsgröße (n)
    3. Ausgewählte Region (en)
    4. Ausgewählte Lizenz (en)
    5. Verwendete Microsoft-Produkte sind 80% ähnlich
    6. Verkaufschance (maximale Punktzahl, die mit der aktuellen Lizenz erzielt werden kann) innerhalb eines Bereichs von 20% von Ihrem Mandanten

Wenn Sie für die benutzerdefinierte Auswahl des Auswahl Ergebnisses in immer weniger als 5 anderen Mandanten, mit denen wir vergleichen können, keine Auswahl getroffen haben, sehen Sie "aufgrund von begrenzten Daten nicht verfügbar".

#### <a name="comparison-trend"></a>Vergleichs Trend

Zeigen Sie auf der Registerkarte **Metriken & Trends** , wie sich die sichere Punktzahl Ihrer Organisation im Laufe der Zeit mit anderen vergleicht.

![Diagramm der Ergebnisse einer ähnlichen Organisation im Laufe der Zeit](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, lassen Sie es uns wissen, indem Sie in der [Sicherheits-, Datenschutz-& Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Microsoft Secure Score (Übersicht)](microsoft-secure-score.md)
- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuigkeiten](microsoft-secure-score-whats-new.md)
