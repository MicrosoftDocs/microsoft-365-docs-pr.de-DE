---
title: Bewerten Ihrer Sicherheitsposition über Microsoft Secure Score
description: In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft Secure Score-Aktion im Microsoft 365 Security Center verbessern können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
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
ms.openlocfilehash: 469056bbae4627e0b013bfc0f2e965586fd15175
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200062"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Bewerten Ihrer Sicherheitsposition mit Microsoft Secure Score

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Damit Sie die benötigten Informationen schneller finden können, sind die Microsoft Verbesserungsmaßnahmen in Gruppen aufgeteilt:

* Identität (Azure AD-Konten & -Rollen)
* Daten (Microsoft Information Protection)
* Gerät (Microsoft Defender ATP, bekannt als [Konfigurationsergebnis](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))
* App (E-Mail-und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)
* Infrastruktur (bisher keine Verbesserungsmaßnahmen)

>[!NOTE]
>In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht, das zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt hatte. [Details anzeigen](microsoft-secure-score-whats-new.md)

Auf der Übersicht der Microsoft-Sicherheitsbewertung können Sie sehen, wie die Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Auf der Übersichtsseite können Sie auch einen Überblick über die Gesamtpunktzahl, den historischen Trend Ihres Sicherheitsbewertung mit Benchmark-Vergleichen sowie priorisierte Verbesserungsmaßnahmen zur Verbesserung ihrer Punktzahl erhalten.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Überprüfen der aktuellen Bewertung

Um Ihre aktuelle Bewertung zu überprüfen, wechseln Sie zur Microsoft Secure Score-Übersichtsseite, und suchen Sie nach der Kachel, die **Ihre sichere Punktzahl**angibt. Ihre Punktzahl wird als Prozentsatz angezeigt, zusammen mit der Anzahl der Punkte, die Sie aus insgesamt möglichen Punkten erzielt haben.

Wenn Sie darüber hinaus die Schaltfläche **einschließen** neben dem Ergebnis auswählen, können Sie unterschiedliche Ansichten der Partitur auswählen. Diese unterschiedlichen Bewertungs Ansichten werden im Diagramm auf der Ergebnis Kachel und im Punkt Aufgliederungs Diagramm angezeigt.

Im folgenden werden Partituren angezeigt, die Sie Ihrer Gesamtpunktzahl hinzufügen können, um ein vollständigeres Bild Ihres Gesamtergebnisses zu erhalten:

- **Geplante Punktzahl**: projiziertes Ergebnis anzeigen, wenn geplante Aktionen abgeschlossen sind
- **Aktuelle Lizenz Bewertung**: Ergebnis anzeigen, das mit Ihrer aktuellen Microsoft-Lizenz erreicht werden kann
- **Erzielbare Punktzahl**: Ergebnis anzeigen, das mit Ihren Microsoft-Lizenzen und der aktuellen Risikoakzeptanz erreicht werden kann

So sieht es aus, wenn Sie alle möglichen Bewertungs Ansichten berücksichtigt haben:

![Ihr sicheres Ergebnis, einschließlich geplanter Punktzahl, aktueller Lizenz Bewertung und erreichbarer Punktzahl](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf der Registerkarte **Verbesserungsmaßnahmen** werden die Sicherheitsempfehlungen, die mögliche Angriffsflächen behandeln, zusammen mit deren Status („Zu behandeln“, „Geplant“, „Risiko akzeptiert“, „Von Drittanbieter behoben“, „Durch alternative Korrektur behoben“ und „Erledigt“) aufgelistet. Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Bewertung basiert auf der Anzahl der noch zu erreichenden Punkte, der Implementierungsschwierigkeit, der Auswirkungen auf die Benutzer und der Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Anzeigen von Details zu Verbesserungsmaßnahmen

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein vollständiges Seiten-Flyout angezeigt.  

![Beispiel für Verbesserungsmaßnahmen-Flyout](../../media/secure-score/secure-score-improvement-action-details.png)
*Abbildung 2: Beispiel für Verbesserungsmaßnahmen-Flyout*

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

* Wählen Sie **Verwalten** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Dann erhalten Sie die Punkte, die die Maßnahme wert ist und wie sie im Flyout angezeigt werden. Es dauert in der Regel bis zu 24 Stunden, bis Punkte aktualisiert werden.

* Wählen Sie **Teilen** aus, um den direkten Link zu der Verbesserungsmaßnahme zu kopieren, oder wählen Sie die Plattform für das Teilen des Links aus, z. B. E-Mail, Microsoft Teams, Microsoft Planner oder ServiceNow. Wenn Sie ServiceNow auswählen, können Sie ein Änderungsticket erstellen, das in ServiceNow und auf der Startseite des Microsoft 365 Security Center angezeigt wird. Weitere Informationen finden Sie unter [Microsoft 365 Security Center und ServiceNow-Integration](tickets-security-center.md).

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungsmaßnahmenstatus

Wählen Sie beliebige Status aus, und zeichnen Sie Notizen auf, die für die Verbesserungsmaßnahme spezifisch sind. Sie können die folgenden Status auswählen:

* **Zu behandeln**: Sie erkennen an, dass die Verbesserungsmaßnahme notwendig ist, und planen deren Durchführung zu einem späteren Zeitpunkt. Dieser Zustand gilt auch für Maßnahmen, die als teilweise, aber noch nicht vollständig erledigt erkannt wurden.
* **Geplant**: Es gibt konkrete Pläne, die Verbesserungsmaßnahme auszuführen.
* **Risiko akzeptiert**: Sicherheit sollte immer mit Benutzerfreundlichkeit in Einklang stehen, und nicht jede Empfehlung wird für Ihre Umgebung funktionieren. Wenn dies der Fall ist, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen und die Verbesserungsmaßnahme nicht zu ergreifen. Sie erhalten keine Punkte, aber die Maßnahme wird in der Liste der Verbesserungsmaßnahmen nicht mehr angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
* **Von Drittanbieter behoben** und **Durch alternative Korrektur behoben**:Die Verbesserungsmaßnahme wurde bereits von einer Drittanbieteranwendung oder -software oder einem internen Tool vorgenommen. Sie erhalten die Punkte, die die Maßnahme wert ist, damit Ihre Bewertung Ihren Sicherheitsstatus im Ganzen besser widerspiegelt. Wenn ein Drittanbieter- oder internes Toll diese Maßnahme nicht mehr abdeckt, können Sie einen anderen Status auswählen. Bitte beachten Sie, dass Microsoft keinen Einblick in die Vollständigkeit der Implementierung besitzt, wenn die Verbesserungsmaßnahme mit einem dieser Status gekennzeichnet ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbesserungsmaßnahmen für Bedrohungs- und Sicherheitsrisikoverwaltung

Für Verbesserungsmaßnahmen in der Kategorie „Gerät“ können Sie keinen Status auswählen. Stattdessen werden Sie zu der zugeordneten [Sicherheitsempfehlung des Bedrohungs- und Sicherheitsrisikomanagements (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) im [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) geleitet, um Maßnahmen zu ergreifen. Die Ausnahme, die Sie auswählen, und die Begründung, die Sie schreiben, sind spezifisch für dieses Portal und finden sich nicht im Microsoft-Sicherheitsbewertungsportal.

#### <a name="completed-improvement-actions"></a>Erledigte Verbesserungsmaßnahmen

Verbesserungsmaßnahmen haben den Status „Erledigt“, sobald alle möglichen Punkte der Verbesserungsmaßnahme erzielt wurden. Erledigte Verbesserungsmaßnahmen werden durch Microsoft-Daten bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf Benutzer

Im Abschnitt **Auf einen Blick** erfahren Sie die Kategorie, Angriffe, vor denen Sie geschützt werden können, sowie das Produkt.

Die **Benutzerauswirkungen** zeigen, was bei den Benutzern geschieht, wenn die Verbesserungsmaßnahme vorgenommen wird, und unter **Betroffene Benutzer** wird angezeigt, wer diese Erfahrungen machen wird.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungsmaßnahmen

Im Abschnitt **Implementierung** werden alle Voraussetzungen, schrittweise die nächsten Schritte zum Durchführen der Verbesserungsmaßnahme, der aktuelle Implementierungsstatus der Verbesserungsmaßnahme sowie alle „Weitere Informationen“-Links angezeigt.

Voraussetzungen sind alle Lizenzen, die Sie besitzen müssen, oder Aktionen, die ausgeführt werden müssen, bevor die Verbesserungsmaßnahme vorgenommen wird. Vergewissern Sie sich, dass Ihre Lizenz genügend Plätze abdeckt, um die Verbesserungsmaßnahme vornehmen zu können, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Microsoft Secure Score (Übersicht)](microsoft-secure-score.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuigkeiten](microsoft-secure-score-whats-new.md)