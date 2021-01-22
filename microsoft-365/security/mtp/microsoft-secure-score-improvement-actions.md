---
title: Bewerten Ihres Sicherheitsstands mithilfe der Microsoft Secure Score
description: Beschreibt, wie Sie Maßnahmen ergreifen, um Ihre Microsoft Secure Score im Microsoft 365 Security Center zu verbessern.
keywords: Microsoft-Sicherheitsergebnis, Sicherheitsergebnis, Office 365-Sicherheitsergebnis, Microsoft-Sicherheitsergebnis, Microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930642"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Bewerten Ihres Sicherheitsstands mit der Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Damit Sie die benötigten Informationen schneller finden können, sind die Microsoft Verbesserungsmaßnahmen in Gruppen aufgeteilt:

* Identität (Azure Active Directory-Konten & Rollen)
* Gerät (Microsoft Defender für Endpunkt, auch bekannt als [Microsoft Secure Score für Geräte)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* App (E-Mail-und Cloud-Apps, einschließlich Office 365 und Microsoft Cloud App Security)

>[!NOTE]
>In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht, das zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt hatte. [Details anzeigen](microsoft-secure-score-whats-new.md)

Zeigen Sie auf der Übersichtsseite der Microsoft Secure Score an, wie Punkte zwischen diesen Gruppen aufgeteilt werden und welche Punkte verfügbar sind. Sie können auch eine Gesamtansicht der Gesamtpunktzahl, den historischen Trend Ihrer Sicherheitsergebnis mit Benchmarkvergleichen und priorisierte Verbesserungsmaßnahmen erhalten, die zur Verbesserung Ihrer Bewertung ergriffen werden können.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Überprüfen Der aktuellen Bewertung

To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**. Ihre Bewertung wird als Prozentsatz zusammen mit der Anzahl der Punkte angezeigt, die Sie aus den möglichen Gesamtpunkten erzielt haben.

Wenn Sie zusätzlich die **Schaltfläche** "Ein-/Aus" neben Ihrer Bewertung auswählen, können Sie verschiedene Ansichten Ihrer Bewertung auswählen. Diese unterschiedlichen Bewertungsansichten werden im Diagramm auf der Ergebniskachel und im Punktstrukturdiagramm angezeigt.

Im Folgenden finden Sie Bewertungen, die Sie Ihrer Ansicht der Gesamtpunktzahl hinzufügen können, um einen vollständigeren Überblick über Ihre Gesamtpunktzahl zu erhalten:

- **Geplantes Ergebnis:** Projizierte Bewertung anzeigen, wenn geplante Aktionen abgeschlossen sind
- **Aktuelle Lizenzergebnis:** Anzeigen der Bewertung, die mit Ihrer aktuellen Microsoft-Lizenz erreicht werden kann
- **Erreichbare Bewertung:** Zeigen Sie die Bewertung an, die mit Ihren Microsoft-Lizenzen und der aktuellen Risikoakzeptanz erreicht werden kann.

Diese Ansicht sieht so aus, wenn Sie alle möglichen Bewertungsansichten eingeschlossen haben:

![Ihr Sicherheitsergebnis, einschließlich geplanter Punktzahl, aktueller Lizenzpunktzahl und erreichbarer Punktzahl](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Ergreifen Sie Maßnahmen, um Ihre Punktzahl zu verbessern

Auf **der Registerkarte "Verbesserungsmaßnahmen"** sind die Sicherheitsempfehlungen aufgeführt, die mögliche Angriffsflächen adressieren. Sie enthält auch ihren Status (zur Behebung, Planung, Risiko akzeptiert, durch Dritte aufgelöst, durch alternative Gegenmaßnahmen aufgelöst und abgeschlossen). Sie können alle Verbesserungsmaßnahmen durchsuchen, filtern und gruppieren.  

### <a name="ranking"></a>Rangfolge

Die Rangfolge basiert auf der Anzahl der Punkte, die noch erreicht werden müssen, implementierungsbezogene Schwierigkeiten, Auswirkungen auf die Benutzer und Komplexität. Die am höchsten bewerteten Verbesserungen bieten viele Punkte mit geringem Schwierigkeitsgrad, Auswirkungen auf Benutzer, sowie Komplexität.

### <a name="view-improvement-action-details"></a>Anzeigen von Details zu Verbesserungsmaßnahmen

Wenn Sie eine bestimmte Verbesserungsmaßnahme auswählen, wird ein vollständiges Seiten-Flyout angezeigt.  

![Beispiel für ein Flyout zur Verbesserungsaktion](../../media/secure-score/secure-score-improvement-action-details.png)

Zum Ausführen der Maßnahme stehen Ihnen verschiedene Optionen zur Verfügung:

- Wählen Sie **Verwalten** aus, um in den Konfigurationsbildschirm zu wechseln und die Änderung vorzunehmen. Sie erhalten dann die Punkte, die die Aktion wert ist, die im Flyout sichtbar sind. Die Aktualisierung von Punkten dauert in der Regel etwa 24 Stunden.

- Wählen **Sie "Freigeben"** aus, um den direkten Link zur Verbesserungsaktion zu kopieren. Sie können auch die Plattform auswählen, auf der der Link geteilt werden soll, z. B. E-Mail, Microsoft Teams, Microsoft Planner oder ServiceNow. Wenn Sie ServiceNow auswählen, können Sie ein Änderungsticket erstellen, das in ServiceNow und der Microsoft 365 Security Center Home angezeigt wird. Weitere Informationen finden Sie unter [Microsoft 365 Security Center- und ServiceNow-Integration.](tickets-security-center.md)

Fügen **Sie Notizen** hinzu, um den Fortschritt oder andere Informationen, die Sie kommentieren möchten, nachverfolgt zu werden. Wenn Sie der **Verbesserungsaktion** eigene Tags hinzufügen, können Sie nach diesen Tags filtern.

### <a name="choose-an-improvement-action-status"></a>Auswählen eines Verbesserungsmaßnahmenstatus

Wählen Sie beliebige Status aus, und zeichnen Sie Notizen auf, die für die Verbesserungsmaßnahme spezifisch sind.

- **To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future. Dieser Status gilt auch für Aktionen, die als teilweise, aber nicht vollständig abgeschlossen erkannt werden.
- **Geplant** – Es gibt konkrete Pläne zum Abschließen der Verbesserungsmaßnahmen.
- **Risiko akzeptiert** – Sicherheit sollte immer mit Benutzerfreundlichkeit ausgeglichen werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung. Wenn dies der Fall ist, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen und die Verbesserungsmaßnahme nicht zu ergreifen. Sie erhalten keine Punkte, aber die Aktion wird nicht mehr in der Liste der Verbesserungsmaßnahmen angezeigt. Sie können diese Aktion jederzeit im Verlauf anzeigen oder rückgängig machen.
- **Lösung durch** Drittanbieter und **Lösung** durch alternative Gegenmaßnahmen – Die Verbesserungsaktion wurde bereits von einer Drittanbieteranwendung oder -software oder einem internen Tool behoben. Sie erhalten die Punkte, die die Aktion wert ist, damit Ihre Bewertung Ihren allgemeinen Sicherheitsstand besser widerspiegelt. Wenn ein Drittanbieter- oder internes Toll diese Maßnahme nicht mehr abdeckt, können Sie einen anderen Status auswählen. Beachten Sie, dass Microsoft keinen Einblick in die Vollständigkeit der Implementierung hat, wenn die Verbesserungsaktion als einer dieser Status gekennzeichnet ist.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbesserungsmaßnahmen & Bedrohungsmanagements

Für Verbesserungsmaßnahmen in der Kategorie "Gerät" können Sie keine Status auswählen. Stattdessen werden Sie an die entsprechende Sicherheitsempfehlung zur Bedrohungs- und Sicherheitsrisikoverwaltung [im](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) Microsoft Defender [Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) geleitet, um Maßnahmen zu ergreifen. Die Ausnahme, die Sie auswählen, und die Begründung, die Sie schreiben, sind für dieses Portal spezifisch. Sie ist nicht im Microsoft Secure Score Portal vorhanden.

#### <a name="completed-improvement-actions"></a>Erledigte Verbesserungsmaßnahmen

Verbesserungsmaßnahmen haben den Status „Erledigt“, sobald alle möglichen Punkte der Verbesserungsmaßnahme erzielt wurden. Abgeschlossene Verbesserungsmaßnahmen werden durch die Daten von Microsoft bestätigt, und Sie können den Status nicht ändern.

### <a name="assess-information-and-review-user-impact"></a>Bewerten von Informationen und Überprüfen der Auswirkungen auf Benutzer

Im Abschnitt mit **dem Namen "Auf einen Blick"** werden die Kategorie, angriffe, vor der sie geschützt werden können, und das Produkt angezeigt.

**Die Auswirkungen** auf die Benutzer sind die Auswirkungen,  die die Benutzer haben, wenn die Verbesserungsaktion umgesetzt wird, und die betroffenen Benutzer sind die Betroffenen.

### <a name="implement-the-improvement-action"></a>Implementieren der Verbesserungsmaßnahmen

Der **Abschnitt "Implementierung"** enthält alle Voraussetzungen, schrittweise nächste Schritte zum Abschließen der Verbesserungsaktion, den aktuellen Implementierungsstatus der Verbesserungsaktion und weitere Links.

Zu den Voraussetzungen gehören alle Lizenzen, die erforderlich sind, oder Aktionen, die abgeschlossen werden müssen, bevor die Verbesserungsaktion behandelt wird. Vergewissern Sie sich, dass Ihre Lizenz genügend Plätze abdeckt, um die Verbesserungsmaßnahme vornehmen zu können, und dass diese Lizenzen auf die erforderlichen Benutzer angewendet werden.  

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie sie in der [Community "Sicherheit& Datenschutzrichtlinien"](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Übersicht über die Microsoft Secure Score](microsoft-secure-score.md)
- [Verfolgen Des Verlaufs der Microsoft Secure Score und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
