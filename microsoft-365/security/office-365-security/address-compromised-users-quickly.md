---
title: Adress von gefährdeten Benutzerkonten mit automatisierter Untersuchung und Reaktion
keywords: AIR, AutoIR, Microsoft Defender for Endpoint, automatisiert, Untersuchung, Antwort, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz, kompromittiert
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
description: Erfahren Sie, wie Sie den Prozess der Erkennung und Behandlung von gefährdeten Benutzerkonten mit automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender for Office 365 Plan 2 beschleunigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c500221a10c00cc3b8d9d99c102ce8ec54fa2a48
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934693"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adress von gefährdeten Benutzerkonten mit automatisierter Untersuchung und Reaktion

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) umfasst leistungsstarke [Funktionen](office-365-air.md) für die automatisierte Untersuchung und Reaktion (AIR). Diese Funktionen können Ihrem Sicherheitsteam viel Zeit und Aufwand beim Umgang mit Bedrohungen sparen. Microsoft verbessert weiterhin die Sicherheitsfunktionen. Kürzlich wurden die FUNKTIONEN von AIR erweitert, um ein gefährdetes Benutzersicherheitsspielbuch (derzeit in der Vorschau) zu enthalten. Lesen Sie diesen Artikel, um mehr über das Playbook für die Sicherheit gefährdeter Benutzer zu erfahren. Weitere Informationen finden Sie im Blogbeitrag Beschleunigen der Zeit zum Erkennen und Reagieren auf Benutzerverstöße und Zum Einschränken des Verletzungsbereichs mit [Microsoft Defender Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) Weitere Informationen.

![Automatisierte Untersuchung für einen gefährdeten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das Playbook mit gefährdeter Benutzersicherheit ermöglicht dem Sicherheitsteam Ihrer Organisation:

- Schnellere Erkennung von gefährdeten Benutzerkonten;

- Einschränken des Umfangs einer Verletzung, wenn ein Konto gefährdet ist; und

- Reagieren Sie effektiver und effizienter auf gefährdete Benutzer.

## <a name="compromised-user-alerts"></a>Gefährdete Benutzerwarnungen

Wenn ein Benutzerkonto gefährdet ist, treten atypische oder anomale Verhaltensweisen auf. Beispielsweise können Phishing- und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Defender for Office 365 kann solche Anomalien in E-Mail-Mustern und Aktivitäten zur Zusammenarbeit innerhalb von Office 365. In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung beginnt.

Hier ist beispielsweise eine Warnung, die aufgrund verdächtigen E-Mail-Sendens ausgelöst wurde:

![Warnung aufgrund verdächtigen Sendens von E-Mails ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Hier sehen Sie ein Beispiel für eine Warnung, die ausgelöst wurde, wenn ein Sendegrenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Erreichen des Sendegrenzwerts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und Reagieren auf einen gefährdeten Benutzer

Wenn ein Benutzerkonto gefährdet ist, werden Warnungen ausgelöst. Und in einigen Fällen wird dieses Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die Ihr Sicherheitsteam ergreifen sollte.

- [Anzeigen und Untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen verfügen, um die folgenden Aufgaben ausführen zu können. Weitere [Informationen finden Sie unter Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und Untersuchen eingeschränkter Benutzer

Sie haben einige Optionen für die Navigation zu einer Liste eingeschränkter Benutzer. Beispielsweise können Sie im Security & Compliance Center zu **Bedrohungsverwaltung** \> **Überprüfen** \> **eingeschränkter Benutzer wechseln.** Im folgenden Verfahren wird  die Navigation mithilfe des Benachrichtigungsdashboards beschrieben. Dies ist eine gute Möglichkeit, verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Gehen Sie auf <https://protection.office.com>, und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **Benachrichtigungsdashboard** \> **aus.**

3. Wählen Sie **im Widget Andere Warnungen** die Option **Eingeschränkte Benutzer aus.**

   ![Widget für andere Warnungen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Aktionen wie die Freigabe des [eingeschränkten Benutzers zu ergreifen.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Anzeigen von Details zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung begonnen hat, können Sie ihre Details und Ergebnisse im Security & Compliance Center anzeigen. Wechseln Sie zu **Bedrohungsverwaltungsuntersuchungen,** \> und wählen Sie dann eine Untersuchung aus, um die Details anzuzeigen.

Weitere Informationen finden Sie unter [Anzeigen von Details einer Untersuchung](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- **Bleiben Sie auf dem Besten ihrer Benachrichtigungen.** Je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Ihre Kunden und Partner. Frühzeitige Erkennung und zeitnahe Reaktion sind entscheidend, um Bedrohungen zu mindern, insbesondere wenn das Konto eines Benutzers gefährdet ist.

- **Die Automatisierung unterstützt Ihr Sicherheitsbetriebsteam,** ersetzt sie jedoch nicht. Automatisierte Untersuchungs- und Reaktionsfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheitsteam muss sich wahrscheinlich dafür engagieren und einige Untersuchungen und Korrekturen unternehmen. Benötigen Sie hier Hilfe? Weitere [Informationen finden Sie unter Überprüfen und Genehmigen von Aktionen.](air-review-approve-pending-completed-actions.md)

- **Verlassen Sie sich nicht auf eine verdächtige Anmeldebenachrichtigung als einziger Indikator.** Wenn ein Benutzerkonto gefährdet ist, löst es möglicherweise eine verdächtige Anmeldebenachrichtigung aus. Manchmal ist es die Reihe von Aktivitäten, die auftreten, nachdem ein Konto gefährdet wurde, das eine Warnung auslöst. Möchten Sie mehr über Warnungen erfahren? Weitere [Informationen finden Sie unter Warnungsrichtlinien](../../compliance/alert-policies.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen der erforderlichen Berechtigungen für die Verwendung von AIR-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Suchen und Untersuchen bösartiger E-Mails in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Informationen zu AIR in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besuchen Sie die Microsoft 365 Roadmap, um zu sehen, was in Kürze kommt, und das Roll-out](https://www.microsoft.com/microsoft-365/roadmap?filters=)