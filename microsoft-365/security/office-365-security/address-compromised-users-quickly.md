---
title: Umgang mit kompromittierten Benutzerkonten mit automatischer Untersuchung und Reaktion
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz, kompromittiert
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: Erfahren Sie, wie Sie den Prozess der Erkennung und Behandlung von kompromittierten Benutzerkonten mit automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2 beschleunigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd1ad6f52114340153f3958441bfb9500db67215
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108577"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Umgang mit kompromittierten Benutzerkonten mit automatischer Untersuchung und Reaktion

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) umfasst leistungsstarke Air-Funktionen [(Automated Investigation and Response).](office-365-air.md) Diese Funktionen können Ihrem Sicherheitsteam viel Zeit und Mühe beim Umgang mit Bedrohungen ersparen. Microsoft verbessert weiterhin die Sicherheitsfunktionen. Kürzlich wurden die AIR-Funktionen erweitert, um ein kompromittiertes Sicherheits-Playbook für Benutzer (derzeit in der Vorschau) einzuschließen. Lesen Sie diesen Artikel, um mehr über das Sicherheits-Playbook für kompromittierte Benutzer zu erfahren. Weitere Informationen finden Sie im Blogbeitrag "Beschleunigen der [Zeit zum Erkennen und Reagieren auf Benutzerkompromittierung und Einschränken des Umfangs von Sicherheitsverletzungen mit Microsoft Defender für Office 365".](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)

![Automatisierte Untersuchung für einen kompromittierten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das Sicherheits-Playbook für kompromittierte Benutzer ermöglicht dem Sicherheitsteam Ihrer Organisation Folgendes:

- Beschleunigen der Erkennung von kompromittierten Benutzerkonten;
- Beschränken des Umfangs einer Verletzung, wenn ein Konto kompromittiert wird; Und
- Reagieren Sie effektiver und effizienter auf kompromittierte Benutzer.

## <a name="compromised-user-alerts"></a>Warnungen kompromittierte Benutzer

Wenn ein Benutzerkonto kompromittiert wird, tritt ein atypisches oder anomales Verhalten auf. Beispielsweise können Phishing- und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Defender für Office 365 können solche Anomalien in E-Mail-Mustern und Zusammenarbeitsaktivitäten innerhalb Office 365 erkennen. In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung beginnt.

Hier ist beispielsweise eine Warnung, die aufgrund eines verdächtigen Sendens von E-Mails ausgelöst wurde:

![Warnung ausgelöst aufgrund des sendens verdächtiger E-Mails](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, als ein Sendegrenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Das Senden des Grenzwerts erreicht](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und Reagieren auf einen kompromittierten Benutzer

Wenn ein Benutzerkonto kompromittiert wird, werden Warnungen ausgelöst. In einigen Fällen wird dieses Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die Ihr Sicherheitsteam ergreifen sollte.

- [Anzeigen und Untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen verfügen, um die folgenden Aufgaben ausführen zu können. Siehe ["Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen".](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und Untersuchen eingeschränkter Benutzer

Sie haben einige Optionen für die Navigation zu einer Liste der eingeschränkten Benutzer. Im Microsoft 365 Defender Portal können Sie beispielsweise zu **"E-Mail & Zusammenarbeit** \>  \> **eingeschränkte Benutzer** überprüfen" wechseln. Im folgenden Verfahren wird  die Navigation mithilfe des Warnungsdashboards beschrieben. Dies ist eine gute Möglichkeit, verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) und wechseln Sie zu Vorfälle &  \> **Warnungen**. Oder verwenden Sie , um direkt zur Seite **"Warnungen"** zu <https://security.microsoft.com/alerts> wechseln.

2. Filtern Sie auf der Seite **"Warnungen"** die Ergebnisse nach Zeitraum, und die Richtlinie mit dem Namen **"Benutzer" hat das Senden von E-Mails eingeschränkt.**

   ![Die Seite "Warnungen" im Microsoft 365 Defender-Portal, gefiltert nach eingeschränkten Benutzern](../../media/m365-sc-alerts-page-with-restricted-user.png)

3. Wenn Sie den Eintrag auswählen, indem Sie auf den Namen klicken, wird ein Benutzer, der auf das **Senden von E-Mails beschränkt ist,** mit zusätzlichen Details geöffnet, die Sie überprüfen können. Neben der Schaltfläche **"Warnung verwalten"** können Sie auf das ![ Symbol ](../../media/m365-cc-sc-more-actions-icon.png) **"Weitere Optionen"** klicken und dann **"Eingeschränkte Benutzerdetails anzeigen"** auswählen, um zur Seite **"Eingeschränkte Benutzer"** zu wechseln, auf der Sie [den eingeschränkten Benutzer freigeben](removing-user-from-restricted-users-portal-after-spam.md)können.

   ![Der Benutzer hat das Senden von E-Mails aus dem Warnungscenter eingeschränkt](../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png)

### <a name="view-details-about-automated-investigations"></a>Anzeigen von Details zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung begonnen hat, können Sie die Details und Ergebnisse im Security & Compliance Center anzeigen. Wechseln Sie zu Untersuchungen zur **Bedrohungsverwaltung,** \> und wählen Sie dann eine Untersuchung aus, um die Details anzuzeigen.

Weitere Informationen finden Sie unter [Anzeigen von Details zu einer Untersuchung.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- **Bleiben Sie auf dem Laufenden über Ihre Warnungen.** Wie Sie wissen, je länger ein Kompromiss nicht erkannt wird, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Ihre Kunden und Partner. Die frühzeitige Erkennung und rechtzeitige Reaktion sind entscheidend, um Bedrohungen zu mindern, insbesondere wenn das Konto eines Benutzers kompromittiert wird.

- **Automatisierung unterstützt, ersetzt aber nicht Ihr Sicherheitsteam.** Automatisierte Untersuchungs- und Reaktionsfunktionen können einen kompromittierten Benutzer frühzeitig erkennen, aber Ihr Sicherheitsteam muss sich wahrscheinlich engagieren und einige Untersuchungen und Korrekturen durchführen. Benötigen Sie Hilfe dazu? Siehe ["Überprüfen und Genehmigen von Aktionen".](air-review-approve-pending-completed-actions.md)

- **Verlassen Sie sich nicht auf eine verdächtige Anmeldewarnung als einzigen Indikator.** Wenn ein Benutzerkonto kompromittiert wird, wird möglicherweise eine verdächtige Anmeldewarnung ausgelöst. Manchmal ist es die Reihe von Aktivitäten, die auftreten, nachdem ein Konto kompromittiert wurde, das eine Warnung auslöst. Möchten Sie mehr über Warnungen wissen? Siehe [Warnungsrichtlinien.](../../compliance/alert-policies.md)

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen der erforderlichen Berechtigungen für die Verwendung von AIR-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Suchen und Untersuchen bösartiger E-Mails in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Informationen zu AIR in Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besuchen Sie die Roadmap für Microsoft 365, um zu sehen, was in Kürze verfügbar ist und wie es in Kürze verfügbar ist.](https://www.microsoft.com/microsoft-365/roadmap?filters=)