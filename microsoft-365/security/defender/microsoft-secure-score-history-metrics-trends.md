---
title: Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen
description: Erhalten Sie Einblicke in Aktivitäten, die Sich auf Ihre Microsoft Secure Score ausdingen. Entdecken Sie Trends und legen Sie Ziele fest.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.technology: m365d
ms.openlocfilehash: 70b20755de836d3fce2469da00bd41520e70ca57
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064632"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score](microsoft-secure-score.md) ist ein Maß für die Sicherheitslage einer Organisation, mit einer höheren Anzahl, die mehr Verbesserungsmaßnahmen anzeigt. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Erhalten Von Einblicken in Aktivitäten, die Sich auf Ihre Bewertung ausdingen

Zeigen Sie auf der Registerkarte Verlauf ein Diagramm der Bewertung Ihrer Organisation im Laufe der **Zeit** an.

Unterhalb des Diagramms finden Sie eine Liste aller Aktionen im ausgewählten Zeitraum und deren Attribute, z. B. resultierende Punkte und Kategorie. Sie können einen Datumsbereich anpassen und nach Kategorie filtern.

![Aktivitätsverlauf](../../media/secure-score/secure-score-history-activity.png)

Wenn Sie die Verbesserungsaktion auswählen, die einer Aktivität zugeordnet ist, wird das Flyout der vollständigen Verbesserungsaktion angezeigt.

Um den verlauf für diese spezifische Verbesserungsaktion anzeigen zu können, wählen Sie im Flyout den Verlaufslink aus.

![Verlauf der Verbesserungsaktion](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Entdecken von Trends und Festlegen von Zielen

Auf der Registerkarte **Metriken und Trends** finden Sie mehrere Graphen und Diagramme, die Ihnen einen besseren Einblick in Trends und festgelegte Ziele ermöglichen. Sie können den Datumsbereich für die gesamte Seite der Visualisierungen festlegen. Die Visualisierungen umfassen:

* **Ihre Secure Score Zone** – Angepasst basierend auf den Zielen und Definitionen ihrer Organisation für gute, okaye und schlechte Bewertungsbereiche.
* **Regressionstrend** – Eine Zeitachse mit Punkten, die aufgrund von Konfigurations-, Benutzer- oder Geräteänderungen zurückgeschritten sind.  
* **Vergleichstrend** – Vergleich zwischen dem Secure Score ihrer Organisation und dem der anderen Personen im Laufe der Zeit. Diese Ansicht kann Linien enthalten, die den Bewertungsdurchschnitt von Organisationen mit ähnlicher Anzahl von Plätzen darstellt, sowie eine benutzerdefinierte Vergleichsansicht, die Sie festlegen können.
* **Trend zur Risikoakzeptanz** – Zeitachse der Verbesserungsmaßnahmen, die als "Risiko akzeptiert" gekennzeichnet sind.
* **Bewertungsänderungen** – Die Anzahl der erzielten Punkte, die anzahl der zurückgeschrittenen Punkte und die Änderungen an Ihrer Punktzahl im angegebenen Datumsbereich.

### <a name="compare-your-score-to-organizations-like-yours"></a>Vergleichen Ihrer Bewertung mit Organisationen wie Ihrer

Es gibt zwei Orte, an denen Sie sehen können, wie Ihre Bewertung mit Organisationen vergleichbar ist. In beiden Diagrammen können Sie **Vergleiche** verwalten auswählen, um die Informationen Ihrer Organisation anzuzeigen und zu bearbeiten. Sie können auch einen benutzerdefinierten Vergleich basierend auf Branche, Organisationsgröße, Lizenzen und Regionen erstellen.

#### <a name="comparison-bar-chart"></a>Vergleichsbalkendiagramm

Das Vergleichsbalkendiagramm ist die **Registerkarte** Übersicht. Zeigen Sie auf das Diagramm, um die Bewertungs- und Bewertungschance zu sehen. Die Vergleichsdaten werden anonymisiert, sodass wir nicht genau wissen, welche anderen Mandanten sich in der Mischung befinden.

![Balkendiagramm der Ergebnisse ähnlicher Organisationen](../../media/secure-score/secure-score-comparison-bar.png)

- **Organisationen wie Ihre**: eine durchschnittliche Bewertung anderer Mandanten (sofern mindestens fünf Mandanten zu vergleichen sind), die mit den folgenden Kriterien qualifiziert sind:
    1. Gleiche Branche
    2. Gleiche Organisationsgröße
    3. Alle Regionen
    4. Verwendete Microsoft-Produkte sind zu 80 % ähnlich
    5. Chance (maximale Punktzahl, die von der aktuellen Lizenz erreicht werden kann) innerhalb eines Bereichs von 20 % von Ihrem Mandanten

- **Benutzerdefinierter Vergleich**: muss eingerichtet werden, indem Sie **Vergleich** basierend auf den folgenden Kriterien verwalten auswählen:
    1. Ausgewählte Branchen
    2. Ausgewählte Organisationsgröße(n)
    3. Ausgewählte Regionen
    4. Ausgewählte Lizenzen
    5. Verwendete Microsoft-Produkte sind zu 80 % ähnlich
    6. Chance (maximale Punktzahl, die von der aktuellen Lizenz erreicht werden kann) innerhalb eines Bereichs von 20 % von Ihrem Mandanten

Wenn Sie eine benutzerdefinierte Auswahl getroffen haben, die Ergebnisse jedoch weniger als fünf andere Mandanten haben, mit der wir vergleichen können, wird "Aufgrund begrenzter Daten nicht verfügbar" angezeigt.

#### <a name="comparison-trend"></a>Vergleichstrend

Zeigen Sie **auf der Registerkarte** Metriken & Trends an, wie die Sichere Bewertung Ihrer Organisation mit der der anderen im Laufe der Zeit verglichen wird.

![Liniendiagramm der Ergebnisse ähnlicher Organisationen im Laufe der Zeit](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der [Community für Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Übersicht über die Microsoft Secure Score](microsoft-secure-score.md)
- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
