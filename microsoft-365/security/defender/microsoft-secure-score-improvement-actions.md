---
title: Bewerten Ihres Sicherheitsstatus mithilfe der Microsoft-Sicherheitsbewertung
description: Beschreibt, wie Sie Maßnahmen ergreifen, um Ihre Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center zu verbessern.
keywords: Microsoft-Sicherheitsbewertung, Sicherheitsbewertung, Office 365-Sicherheitsbewertung, Microsoft-Sicherheitsbewertung, Microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: c4d4958c03bee7301465c16fef2cd4ff8adb1722
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288455"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Bewerten Ihres Sicherheitsstatus mit der Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Um Ihnen zu helfen, die benötigten Informationen schneller zu finden, sind Die Verbesserungsmaßnahmen von Microsoft in Gruppen unterteilt:

- Identität (Azure Active Directory Konten & Rollen)
- Gerät (Microsoft Defender für Endpunkt, bekannt als [Microsoft-Sicherheitsbewertung für Geräte)](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
- Apps (E-Mail- und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)

>[!NOTE]
>In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht, das zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt hatte. [Details anzeigen](microsoft-secure-score-whats-new.md)

In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available. Sie können auch eine Übersicht über die Gesamtbewertung, den historischen Trend Ihrer Sicherheitsbewertung mit Benchmarkvergleichen und priorisierte Verbesserungsmaßnahmen erhalten, die zur Verbesserung Ihrer Bewertung ergriffen werden können.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a>Überprüfen Des aktuellen Bewertungsergebnisses

Um Ihre aktuelle Bewertung zu überprüfen, wechseln Sie zur Übersicht über die Microsoft-Sicherheitsbewertung, und suchen Sie nach der Kachel mit der Meldung **"Ihre Sicherheitsbewertung".** Ihre Bewertung wird als Prozentsatz zusammen mit der Anzahl der Punkte angezeigt, die Sie von den möglichen Gesamtpunkten erreicht haben.

Wenn Sie zusätzlich zur Bewertung die Schaltfläche **"Einschließen"** auswählen, können Sie unterschiedliche Ansichten Ihrer Bewertung auswählen. Diese unterschiedlichen Bewertungsansichten werden im Diagramm auf der Bewertungskachel und im Punktestrukturplandiagramm angezeigt.

Im Folgenden finden Sie Ergebnisse, die Sie Ihrer Ansicht Ihres Gesamtergebnisses hinzufügen können, um ein umfassenderes Bild ihrer Gesamtbewertung zu erhalten:

- **Geplante Bewertung:** Zeigen Sie die projizierte Bewertung an, wenn geplante Aktionen abgeschlossen sind
- **Aktuelle Lizenzbewertung:** Anzeigen der Bewertung, die mit Ihrer aktuellen Microsoft-Lizenz erzielt werden kann
- **Erreichbare Bewertung:** Anzeigen der Bewertung, die mit Ihren Microsoft-Lizenzen und der aktuellen Risikoakzeptanz erzielt werden kann

Diese Ansicht sieht wie folgt aus, wenn Sie alle möglichen Bewertungsansichten eingeschlossen haben:

![Ihre Sicherheitsbewertung, einschließlich der geplanten Bewertung, der aktuellen Lizenzbewertung und der erreichbaren Bewertung](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf der Registerkarte **"Verbesserungsmaßnahmen"** sind die Sicherheitsempfehlungen aufgeführt, die mögliche Angriffsflächen behandeln. Es enthält auch ihren Status (zum Adressieren, Planen, Akzeptieren des Risikos, Gelöst durch Dritte, gelöst durch alternative Risikominderung und Abgeschlossen). Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Rangfolge basiert auf der Anzahl der zu erreichenden Punkte, den Implementierungseinbußen, den Auswirkungen auf die Benutzer und der Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Anzeigen von Details zu Verbesserungsmaßnahmen

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein vollständiges Seiten-Flyout angezeigt.  

![Beispiel für Verbesserungsmaßnahmen-Flyout](../../media/secure-score/secure-score-improvement-action-details.png)

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

- Wählen Sie **Verwalten** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion wert ist, die im Flyout sichtbar sind. Die Aktualisierung von Punkten dauert in der Regel ca. 24 Stunden.

- Wählen Sie **"Freigeben"** aus, um den direkten Link zu der Verbesserungsmaßnahme zu kopieren. Sie können auch die Plattform auswählen, um den Link freizugeben, z. B. E-Mail, Microsoft Teams oder Microsoft Planner.

Fügen Sie **Notizen** hinzu, um den Fortschritt oder andere Punkte nachzuverfolgen, die Sie kommentieren möchten. Wenn Sie der Verbesserungsmaßnahme eigene **Tags** hinzufügen, können Sie nach diesen Tags filtern.

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungsmaßnahmenstatus

Wählen Sie beliebige Status aus, und zeichnen Sie Notizen auf, die für die Verbesserungsmaßnahme spezifisch sind.

- **To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future. Dieser Zustand gilt auch für Aktionen, die als teilweise, aber nicht vollständig abgeschlossen erkannt werden.
- **Geplant** – Es gibt konkrete Pläne, um die Verbesserungsmaßnahme abzuschließen.
- **Risiko akzeptiert** – Sicherheit sollte immer mit Benutzerfreundlichkeit ausgeglichen werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung. Wenn dies der Fall ist, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen und die Verbesserungsmaßnahme nicht zu ergreifen. Sie erhalten keine Punkte, aber die Aktion wird nicht mehr in der Liste der Verbesserungsmaßnahmen angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
- **Behoben über Drittanbieter** und **behoben durch alternative Gegenmaßnahmen** – Die Verbesserungsmaßnahme wurde bereits von einer Drittanbieteranwendung oder -software oder einem internen Tool behoben. Sie erhalten die Punkte, die die Aktion wert ist, sodass Ihre Bewertung Ihren allgemeinen Sicherheitsstatus besser widerspiegelt. Wenn ein Drittanbieter- oder internes Toll diese Maßnahme nicht mehr abdeckt, können Sie einen anderen Status auswählen. Beachten Sie, dass Microsoft keine Einblicke in die Vollständigkeit der Implementierung hat, wenn die Verbesserungsmaßnahme als einer dieser Status gekennzeichnet ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbesserungsmaßnahmen für Bedrohungen & Sicherheitsrisikomanagement

Für Verbesserungsmaßnahmen in der Kategorie "Gerät" können Sie keine Status auswählen. Stattdessen werden Sie zu der zugehörigen [Bedrohungs- und Sicherheitsrisikomanagement Sicherheitsempfehlung](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) im [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) weitergeleitet, um Maßnahmen zu ergreifen. Die von Ihnen getroffene Ausnahme und begründung, die Sie schreiben, ist für dieses Portal spezifisch. Es wird nicht im Microsoft Secure Score-Portal vorhanden sein.

#### <a name="completed-improvement-actions"></a>Erledigte Verbesserungsmaßnahmen

Verbesserungsmaßnahmen haben den Status „Erledigt“, sobald alle möglichen Punkte der Verbesserungsmaßnahme erzielt wurden. Abgeschlossene Verbesserungsmaßnahmen werden durch Microsoft-Daten bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf Benutzer

Der Abschnitt mit dem Namen **"Auf einen Blick"** informiert Sie über die Kategorie, die Angriffe, vor denen sie geschützt werden kann, und das Produkt.

**Die Auswirkungen auf** die Benutzer werden den Benutzern angezeigt, wenn die Verbesserungsmaßnahmen ergriffen werden, und die **betroffenen Benutzer** sind die Betroffenen.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungsmaßnahmen

Der Abschnitt **"Implementierung"** enthält alle Voraussetzungen, schrittweise die nächsten Schritte zum Abschließen der Verbesserungsmaßnahme, den aktuellen Implementierungsstatus der Verbesserungsmaßnahme und weitere Links.

Zu den Voraussetzungen gehören alle Lizenzen, die erforderlich sind, oder Aktionen, die abgeschlossen werden müssen, bevor die Verbesserungsmaßnahme behoben wird. Vergewissern Sie sich, dass Ihre Lizenz genügend Plätze abdeckt, um die Verbesserungsmaßnahme vornehmen zu können, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie sie in der [Community für Sicherheit, Datenschutz & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Übersicht über die Microsoft-Sicherheitsbewertung](microsoft-secure-score.md)
- [Nachverfolgen des Microsoft-Verlaufs der Sicherheitsbewertung und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
