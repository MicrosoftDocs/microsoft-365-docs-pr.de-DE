---
title: Reagieren auf gefährdete Benutzerkonten mit automatischer Untersuchung und Reaktion
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, fortgeschritten, Bedrohung, Schutz, kompromittiert
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
ms.date: 02/25/2020
description: Erfahren Sie, wie Sie den Prozess der Erkennung und Behandlung von gefährdeten Benutzerkonten mit automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2 beschleunigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176063"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Reagieren auf gefährdete Benutzerkonten mit automatischer Untersuchung und Reaktion

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) umfasst leistungsstarke funktionen für [automatisierte Untersuchung](office-365-air.md) und Reaktion (AIR). Solche Funktionen können Ihrem Sicherheitsteam viel Zeit und Mühe beim Umgang mit Bedrohungen sparen. Microsoft verbessert weiterhin die Sicherheitsfunktionen. Kürzlich wurden die Funktionen von AIR um ein gefährdetes Benutzersicherheits-Playbook erweitert (derzeit in der Vorschau). Lesen Sie diesen Artikel, um mehr über das Playbook für die Sicherheit gefährdeter Benutzer zu erfahren. Weitere Details finden Sie im Blogbeitrag "Beschleunigen der Zeit zum Erkennen und Reagieren auf Benutzerverstöße und Zum Einschränken des Umfangs von Sicherheitsverletzungen mit [Microsoft Defender für Office 365".](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)

![Automatische Untersuchung eines gefährdeten Benutzers](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das Sicherheits-Playbook für gefährdete Benutzer ermöglicht dem Sicherheitsteam Ihrer Organisation:

- Beschleunigen der Erkennung von gefährdeten Benutzerkonten;

- Einschränken des Umfangs einer Verletzung, wenn ein Konto gefährdet ist; und

- Reagieren Sie effektiver und effizienter auf gefährdete Benutzer.

## <a name="compromised-user-alerts"></a>Warnungen von gefährdeten Benutzern

Wenn ein Benutzerkonto gefährdet ist, treten atypische oder anomale Verhaltensweisen auf. Beispielsweise können Phishing- und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Defender für Office 365 kann solche Anomalien in E-Mail-Mustern und Aktivitäten zur Zusammenarbeit in Office 365 erkennen. Wenn dies geschieht, werden Warnungen ausgelöst, und der Prozess zur Risikominderung beginnt.

Hier ist beispielsweise eine Warnung, die aufgrund verdächtigen Sendens von E-Mails ausgelöst wurde:

![Warnung aufgrund verdächtigen Sendens von E-Mails ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, wenn ein Sendegrenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Erreichen des Sendegrenzwerts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und Reagieren auf einen gefährdeten Benutzer

Wenn ein Benutzerkonto gefährdet ist, werden Warnungen ausgelöst. Und in einigen Fällen wird dieses Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Maßnahmen führen kann, die Ihr Sicherheitsteam ergreifen sollte.

- [Anzeigen und Untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen zum Ausführen der folgenden Aufgaben verfügen. Siehe ["Erforderliche Berechtigungen zum Verwenden von AIR-Funktionen".](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und Untersuchen eingeschränkter Benutzer

Sie haben einige Optionen, um zu einer Liste eingeschränkter Benutzer zu navigieren. Beispielsweise können Sie im Security & Compliance Center zu  "Bedrohungsverwaltung Überprüfen \>  \> **eingeschränkter Benutzer" wechseln.** Im folgenden Verfahren wird die Navigation mithilfe **des** Benachrichtigungsdashboards beschrieben. Dies ist eine gute Möglichkeit, verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Gehen Sie auf <https://protection.office.com>, und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **"Warnungsdashboard"** \> **aus.**

3. Wählen Sie **im Widget "Andere Warnungen"** die Option **"Eingeschränkte Benutzer" aus.**

   ![Widget für andere Warnungen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Maßnahmen zu ergreifen, z. B. [freigeben des eingeschränkten Benutzers.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Anzeigen von Details zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung begonnen hat, können Sie ihre Details und Ergebnisse im Security & Compliance Center anzeigen. Wechseln Sie zu **"Threat Management** Investigations", und wählen Sie dann \> eine Untersuchung aus, um deren Details anzuzeigen.

Weitere Informationen finden Sie unter [Anzeigen von Details zu einer Untersuchung.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- **Bleiben Sie über Ihre Warnungen auf dem Besten.** Wie Sie wissen, gilt: Je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Ihre Kunden und Partner. Eine frühzeitige Erkennung und zeitnahe Reaktion sind entscheidend, um Bedrohungen zu mindern, insbesondere, wenn das Konto eines Benutzers gefährdet ist.

- **Die Automatisierung unterstützt Ihr Sicherheitsteam, ersetzt aber nicht.** Automatisierte Untersuchungs- und Reaktionsfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheitsteam muss sich wahrscheinlich einarbeiten und einige Untersuchungen und Korrekturen unternehmen. Benötigen Sie Hilfe dazu? Siehe Überprüfen [und Genehmigen von Aktionen.](air-review-approve-pending-completed-actions.md)

- **Verlassen Sie sich nicht auf eine verdächtige Anmeldewarnung als einzigen Indikator.** Wenn ein Benutzerkonto gefährdet ist, wird möglicherweise eine verdächtige Anmeldebenachrichtigung ausgelöst. Manchmal ist es die Reihe von Aktivitäten, die auftreten, nachdem ein Konto gefährdet wurde, das eine Warnung auslöst. Möchten Sie mehr über Warnungen erfahren? Siehe [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen der erforderlichen Berechtigungen für die Verwendung von AIR-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Suchen und Untersuchen bösartiger E-Mails in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Informationen zu AIR in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was in Kürze verfügbar ist, und die Roll-out-Website.](https://www.microsoft.com/microsoft-365/roadmap?filters=)
