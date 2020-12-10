---
title: Adressieren von kompromittierten Benutzerkonten mit automatisierter Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz, kompromittiert
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Erfahren Sie, wie Sie das erkennen und adressieren von kompromittierten Benutzerkonten mit automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Defender für Office 365 Plan 2 beschleunigen können.
ms.openlocfilehash: 19c9bad33263178f92c6fe523b44497cf38ebd53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616737"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adressieren von kompromittierten Benutzerkonten mit automatisierter Untersuchung und Antwort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) enthält leistungsstarke Funktionen für die [Automatische Untersuchung und Reaktion](office-365-air.md) (Air). Solche Funktionen können Ihr Sicherheits Betriebsteam viel Zeit und Mühe beim Umgang mit Bedrohungen speichern. Microsoft verbessert weiterhin die Sicherheitsfunktionen. In letzter Zeit wurden die Air-Funktionen erweitert, um ein kompromittiertes Benutzer Sicherheits-Textbuch (derzeit in der Vorschau) einzuschließen. Lesen Sie diesen Artikel, um mehr über das kompromittierte User Security-Manuskript zu erfahren. Und lesen Sie den Blogbeitrag [beschleunigen Zeit zum erkennen und reagieren auf Benutzer Kompromisse und Grenzwerte für Verstöße mit Microsoft Defender für Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) zusätzliche Details.

![Automatische Untersuchung für einen kompromittierten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das kompromittierte User Security-Manuskript ermöglicht dem Sicherheitsteam Ihrer Organisation Folgendes:

- Schnellere Erkennung kompromittierter Benutzerkonten;

- Einschränken des Gültigkeitsbereichs einer Verletzung, wenn ein Konto kompromittiert wird; und

- Effektivere und effizientere Reaktion auf kompromittierte Benutzer.

## <a name="compromised-user-alerts"></a>Kompromittierte Benutzer Warnungen

Wenn ein Benutzerkonto kompromittiert wird, treten atypische oder anomale Verhaltensweisen auf. Beispielsweise können Phishing-und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Defender for Office 365 kann solche Anomalien in e-Mail-Mustern und Zusammenarbeitsaktivitäten innerhalb Office 365 erkennen. In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung wird gestartet.

Hier ist beispielsweise eine Warnung, die aufgrund eines verdächtigen e-Mail-Sendens ausgelöst wurde:

![Warnung aufgrund eines verdächtigen e-Mail-Sendens ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Und hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, als ein Sende Grenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Sende Grenzwert erreicht](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und reagieren auf einen kompromittierten Benutzer

Wenn ein Benutzerkonto kompromittiert wird, werden Warnungen ausgelöst. In einigen Fällen wird das Benutzerkonto blockiert und verhindert, dass weitere e-Mail-Nachrichten gesendet werden, bis das Problem vom Security Operations-Team Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die das Sicherheitsteam durchführen sollte.

- [Anzeigen und untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen zum Ausführen der folgenden Aufgaben verfügen. Siehe [erforderliche Berechtigungen für die Verwendung von Air-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und untersuchen eingeschränkter Benutzer

Sie haben einige Optionen, um zu einer Liste eingeschränkter Benutzer zu navigieren. Im Security & Compliance Center können Sie beispielsweise zu **Threat Management** \> **Review** \> **restricted users** wechseln. Im folgenden Verfahren wird die Navigation mithilfe des **Alerts** -Dashboards beschrieben, eine gute Möglichkeit, um verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Gehen Sie auf <https://protection.office.com>, und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **Warnungs** \> **Dashboard** aus.

3. Wählen Sie im Widget **andere Benachrichtigungen** die Option **eingeschränkte Benutzer** aus.

   ![Widget "andere Warnungen"](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Aktionen durchführen zu können, beispielsweise [das Freigeben des eingeschränkten Benutzers](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="view-details-about-automated-investigations"></a>Anzeigen von Details zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung begonnen hat, können Sie Details und Ergebnisse im Security & Compliance Center anzeigen. Wechseln Sie zu **Threat Management** \> **Investigations**, und wählen Sie dann eine Untersuchung aus, um die Details anzuzeigen.

Weitere Informationen finden Sie unter [View Details of a Investigation](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- **Behalten Sie Ihre Benachrichtigungen im Vorder** Grund. Wie Sie wissen, gilt: je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Kunden und Partner. Frühzeitige Erkennung und zeitnahe Reaktion sind wichtig, um Bedrohungen zu minimieren, insbesondere dann, wenn das Konto eines Benutzers kompromittiert wird.

- **Automatisierung unterstützt, ersetzt aber Ihr Sicherheits Betriebsteam**. Automatisierte Ermittlungs-und Antwortfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheits Betriebsteam muss wahrscheinlich einige Untersuchungen und Korrekturen durchführen. Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [überprüfen und Genehmigen von Aktionen](air-review-approve-pending-completed-actions.md).

- **Verlassen Sie sich nicht auf eine verdächtige Anmelde Warnung als einzigen Indikator**. Wenn ein Benutzerkonto kompromittiert wird, wird möglicherweise eine verdächtige Anmelde Warnung ausgelöst. Manchmal handelt es sich um die Reihe von Aktivitäten, die auftreten, nachdem ein Konto kompromittiert wurde, das eine Warnung auslöst. Möchten Sie mehr über Benachrichtigungen erfahren? Siehe [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen der erforderlichen Berechtigungen für die Verwendung von Air-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Suchen und untersuchen von böswilligen e-Mails in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Informationen zu Air in Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was bald kommt und wie Sie Rollen](https://www.microsoft.com/microsoft-365/roadmap?filters=)
