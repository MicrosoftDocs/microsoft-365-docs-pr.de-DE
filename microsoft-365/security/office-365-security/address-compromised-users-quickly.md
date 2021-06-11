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
ms.openlocfilehash: cd84617230e774b92902ef3d11a365c1965ac814
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904140"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Umgang mit kompromittierten Benutzerkonten mit automatischer Untersuchung und Reaktion

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) umfasst leistungsstarke Air-Funktionen [(Automated Investigation and Response).](office-365-air.md) Diese Funktionen können Ihrem Sicherheitsteam viel Zeit und Mühe beim Umgang mit Bedrohungen ersparen. Microsoft verbessert die Sicherheitsfunktionen weiter. Kürzlich wurden die AIR-Funktionen erweitert, um ein kompromittiertes Sicherheits-Playbook für Benutzer (derzeit in der Vorschau) einzuschließen. Lesen Sie diesen Artikel, um mehr über das Sicherheits-Playbook für kompromittierte Benutzer zu erfahren. Weitere Informationen finden Sie im Blogbeitrag "Beschleunigen der [Zeit zum Erkennen und Reagieren auf Benutzerkompromittierung und Einschränken des Umfangs von Sicherheitsverletzungen mit Microsoft Defender" für Office 365.](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)

![Automatisierte Untersuchung für einen kompromittierten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das Sicherheits-Playbook für kompromittierte Benutzer ermöglicht dem Sicherheitsteam Ihrer Organisation Folgendes:

- Beschleunigen der Erkennung von kompromittierten Benutzerkonten;

- Beschränken des Umfangs einer Verletzung, wenn ein Konto kompromittiert wird; Und

- Reagieren Sie effektiver und effizienter auf kompromittierte Benutzer.

## <a name="compromised-user-alerts"></a>Warnungen kompromittierte Benutzer

Wenn ein Benutzerkonto kompromittiert wird, tritt ein atypisches oder anomales Verhalten auf. Beispielsweise können Phishing- und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Defender für Office 365 kann solche Anomalien in E-Mail-Mustern und Zusammenarbeitsaktivitäten innerhalb Office 365 erkennen. In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung beginnt.

Hier ist beispielsweise eine Warnung, die aufgrund eines verdächtigen Sendens von E-Mails ausgelöst wurde:

![Warnung ausgelöst aufgrund des sendens verdächtiger E-Mails](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, wenn ein Sendegrenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Das Senden des Grenzwerts erreicht](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und Reagieren auf einen kompromittierten Benutzer

Wenn ein Benutzerkonto kompromittiert wird, werden Warnungen ausgelöst. In einigen Fällen wird dieses Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die Ihr Sicherheitsteam ergreifen sollte.

- [Anzeigen und Untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen verfügen, um die folgenden Aufgaben ausführen zu können. Siehe ["Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen".](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und Untersuchen eingeschränkter Benutzer

Sie haben einige Optionen für die Navigation zu einer Liste der eingeschränkten Benutzer. For example, in the Security & Compliance Center, you can go to **Threat Management** \> **Review** \> **Restricted Users**. Im folgenden Verfahren wird  die Navigation mithilfe des Warnungsdashboards beschrieben. Dies ist eine gute Möglichkeit, verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Gehen Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **warnungsdashboard** \> aus.

3. Wählen Sie im Widget **"Andere Warnungen"** die Option **"Eingeschränkte Benutzer"** aus.

   ![Andere Warnungs-Widget](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Maßnahmen zu ergreifen, z. [B. die Freigabe des eingeschränkten Benutzers.](removing-user-from-restricted-users-portal-after-spam.md)

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

- [Besuchen Sie die roadmap für Microsoft 365, um zu sehen, was in Kürze verfügbar ist und wie es in Kürze verfügbar ist.](https://www.microsoft.com/microsoft-365/roadmap?filters=)