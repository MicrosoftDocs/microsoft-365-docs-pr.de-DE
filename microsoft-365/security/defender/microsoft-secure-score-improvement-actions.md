---
title: Bewerten Ihrer Sicherheitslage mithilfe von Microsoft Secure Score
description: Beschreibt, wie Sie Maßnahmen ergreifen, um Ihre Microsoft Secure Score im Microsoft 365 zu verbessern.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246397"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Bewerten Ihrer Sicherheitslage mit Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Um Ihnen zu helfen, die benötigten Informationen schneller zu finden, sind Die Verbesserungsmaßnahmen von Microsoft in Gruppen unterteilt:

* Identität (Azure Active Directory Konten & Rollen)
* Device (Microsoft Defender for Endpoint, bekannt als [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
* Apps (E-Mail- und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)

>[!NOTE]
>In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht, das zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt hatte. [Details anzeigen](microsoft-secure-score-whats-new.md)

Zeigen Sie auf der Übersichtsseite von Microsoft Secure Score an, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Sie können auch eine Gesamtansicht der Gesamtpunktzahl, den verlaufshistorischen Trend Ihrer sicheren Bewertung mit Benchmarkvergleichen und priorisierte Verbesserungsmaßnahmen erhalten, die zur Verbesserung Ihrer Bewertung ergriffen werden können.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a>Überprüfen Ihrer aktuellen Bewertung

Um Ihre aktuelle Bewertung zu überprüfen, wechseln Sie zur Übersichtsseite microsoft Secure Score, und suchen Sie nach der Kachel, die **Ihre sichere Bewertung enthält.** Ihre Bewertung wird als Prozentsatz angezeigt, zusammen mit der Anzahl der Punkte, die Sie aus den insgesamt möglichen Punkten erzielt haben.

Wenn Sie außerdem die **Schaltfläche** Include neben Ihrer Bewertung auswählen, können Sie unterschiedliche Ansichten Ihrer Bewertung auswählen. Diese verschiedenen Bewertungsansichten werden im Diagramm auf der Ergebniskachel und im Punktstrukturdiagramm angezeigt.

Im Folgenden finden Sie Ergebnisse, die Sie Ihrer Ansicht ihrer Gesamtpunktzahl hinzufügen können, um Ihnen ein vollständigeres Bild der Gesamtpunktzahl zu geben:

- **Geplante Punktzahl**: Projizierte Punktzahl anzeigen, wenn geplante Aktionen abgeschlossen sind
- **Aktuelle Lizenznote:** Anzeigen der Bewertung, die mit Ihrer aktuellen Microsoft-Lizenz erzielt werden kann
- **Erreichbare Bewertung:** Anzeigen der Bewertung, die mit Ihren Microsoft-Lizenzen und der aktuellen Risikoakzeptanz erzielt werden kann

Diese Ansicht sieht aus, wenn Sie alle möglichen Bewertungsansichten einbezogen haben:

![Ihre sichere Punktzahl, einschließlich geplanter Punktzahl, aktueller Lizenzpunktzahl und erreichbarer Punktzahl](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf **der Registerkarte Verbesserungsaktionen** sind die Sicherheitsempfehlungen aufgeführt, die mögliche Angriffsflächen adressieren. Sie enthält auch ihren Status (zum Adressieren, Geplanten, Akzeptierten Risiko, Auflösen durch Dritte, Auflösen durch alternative Gegenmaßnahmen und Abgeschlossen). Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Rangfolge basiert auf der Anzahl der noch zu erreichende Punkte, Implementierungsschwierigkeiten, Benutzerwirkungen und Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Anzeigen von Details zu Verbesserungsmaßnahmen

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein vollständiges Seiten-Flyout angezeigt.  

![Beispiel für ein Flyout zur Verbesserungsaktion](../../media/secure-score/secure-score-improvement-action-details.png)

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

- Wählen Sie **Verwalten** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion wert ist, die im Fly-Out sichtbar sind. Die Aktualisierung von Punkten dauert in der Regel etwa 24 Stunden.

- Wählen **Sie Freigeben** aus, um den direkten Link zur Verbesserungsaktion zu kopieren. Sie können auch die Plattform auswählen, um den Link zu teilen, z. B. E-Mail, Microsoft Teams oder Microsoft Planner.

Fügen **Sie Notizen** hinzu, um den Fortschritt oder andere Kommentare zu verfolgen. Wenn Sie der **Verbesserungsaktion** eigene Tags hinzufügen, können Sie nach diesen Tags filtern.

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungsmaßnahmenstatus

Wählen Sie beliebige Status aus, und zeichnen Sie Notizen auf, die für die Verbesserungsmaßnahme spezifisch sind.

- **To address** – Sie erkennen, dass die Verbesserungsaktion erforderlich ist, und planen, sie zu einem bestimmten Zeitpunkt in der Zukunft zu adressen. Dieser Status gilt auch für Aktionen, die als teilweise, aber nicht vollständig abgeschlossen erkannt werden.
- **Geplant** – Es gibt konkrete Pläne zum Abschließen der Verbesserungsaktion.
- **Risiko akzeptiert** – Sicherheit sollte immer mit Benutzerfreundlichkeit abgewogen werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung. Wenn dies der Fall ist, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen und die Verbesserungsmaßnahme nicht zu ergreifen. Sie erhalten keine Punkte, aber die Aktion wird nicht mehr in der Liste der Verbesserungsaktionen angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
- **Durch Drittanbieter** aufgelöst und **durch** alternative Gegenmaßnahmen aufgelöst – Die Verbesserungsaktion wurde bereits von einer Drittanbieteranwendung oder -software oder einem internen Tool behoben. Sie erhalten die Punkte, die die Aktion wert ist, damit Ihre Bewertung Ihre allgemeine Sicherheitshaltung besser widerspiegelt. Wenn ein Drittanbieter- oder internes Toll diese Maßnahme nicht mehr abdeckt, können Sie einen anderen Status auswählen. Beachten Sie, dass Microsoft keinen Einblick in die Vollständigkeit der Implementierung hat, wenn die Verbesserungsaktion als einer dieser Status gekennzeichnet ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbesserungsmaßnahmen & Sicherheitsrisikomanagement Bedrohungen

Für Verbesserungsmaßnahmen in der Kategorie "Gerät" können Sie keine Status auswählen. Stattdessen werden Sie an die zugeordnete Sicherheitsempfehlung Bedrohungs- und Sicherheitsrisikomanagement [in](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) der [Microsoft Defender Security Center,](/windows/security/threat-protection/microsoft-defender-atp/use) um Maßnahmen zu ergreifen. Die von Ihnen zu schreibende Ausnahme und Begründung ist für dieses Portal spezifisch. Sie ist nicht im Microsoft Secure Score-Portal vorhanden.

#### <a name="completed-improvement-actions"></a>Erledigte Verbesserungsmaßnahmen

Verbesserungsmaßnahmen haben den Status „Erledigt“, sobald alle möglichen Punkte der Verbesserungsmaßnahme erzielt wurden. Abgeschlossene Verbesserungsmaßnahmen werden durch Microsoft-Daten bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf Benutzer

Im Abschnitt **Mit dem Namen Auf einen Blick** erhalten Sie informationen zur Kategorie, den Angriffen, vor der sie schützen kann, und dem Produkt.

**Die Auswirkungen auf** den Benutzer werden für die Benutzer  angezeigt, wenn die Verbesserungsaktion umgesetzt wird, und betroffene Benutzer sind die Personen, die betroffen sind.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungsmaßnahmen

Der **Abschnitt Implementierung** enthält alle Erforderlichen, schritt-für-Schritt-schritte zum Abschließen der Verbesserungsaktion, den aktuellen Implementierungsstatus der Verbesserungsaktion und weitere Links.

Zu den Voraussetzungen gehören alle erforderlichen Lizenzen oder Aktionen, die abgeschlossen werden müssen, bevor die Verbesserungsaktion behoben wird. Vergewissern Sie sich, dass Ihre Lizenz genügend Plätze abdeckt, um die Verbesserungsmaßnahme vornehmen zu können, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der [Community für Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Übersicht über die Microsoft Secure Score](microsoft-secure-score.md)
- [Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)