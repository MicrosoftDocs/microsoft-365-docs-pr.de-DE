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
description: Erfahren Sie, wie Sie den Prozess der Erkennung und Adressierung kompromittierter Benutzerkonten mit automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection Plan 2 beschleunigen können.
ms.openlocfilehash: 5a1dd64a0b30bb230af0d96432ae9542ce0370d8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656909"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adressieren von kompromittierten Benutzerkonten mit automatisierter Untersuchung und Antwort

[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) enthält leistungsstarke Funktionen für die [Automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air). Solche Funktionen können Ihr Sicherheits Betriebsteam viel Zeit und Mühe beim Umgang mit Bedrohungen speichern. Microsoft verbessert weiterhin die Sicherheitsfunktionen. In letzter Zeit wurden die Air-Funktionen erweitert, um ein kompromittiertes Benutzer Sicherheits-Textbuch (derzeit in der Vorschau) einzuschließen. Lesen Sie diesen Artikel, um mehr über das kompromittierte User Security-Manuskript zu erfahren. Und lesen Sie den Blogbeitrag beschleunigen Sie die [Zeit zum erkennen und reagieren auf Benutzer Kompromisse und Grenzwerte für Verstöße mit Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) , um weitere Informationen zu erhalten.

![Automatische Untersuchung für einen kompromittierten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Das kompromittierte User Security-Manuskript ermöglicht dem Sicherheitsteam Ihrer Organisation Folgendes:

- Schnellere Erkennung kompromittierter Benutzerkonten;

- Einschränken des Gültigkeitsbereichs einer Verletzung, wenn ein Konto kompromittiert wird; und

- Effektivere und effizientere Reaktion auf kompromittierte Benutzer.

## <a name="compromised-user-alerts"></a>Kompromittierte Benutzer Warnungen

Wenn ein Benutzerkonto kompromittiert wird, treten atypische oder anomale Verhaltensweisen auf. Beispielsweise können Phishing-und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden. Office 365 Advanced Threat Protection kann solche Anomalien in e-Mail-Mustern und Zusammenarbeitsaktivitäten innerhalb Office 365 erkennen. In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung wird gestartet.

Hier ist beispielsweise eine Warnung, die aufgrund eines verdächtigen e-Mail-Sendens ausgelöst wurde:

![Warnung aufgrund eines verdächtigen e-Mail-Sendens ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Und hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, als ein Sende Grenzwert für einen Benutzer erreicht wurde:

![Warnung ausgelöst durch Sende Grenzwert erreicht](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Untersuchen und reagieren auf einen kompromittierten Benutzer

Wenn ein Benutzerkonto kompromittiert wird, werden Warnungen ausgelöst. In einigen Fällen wird das Benutzerkonto blockiert und verhindert, dass weitere e-Mail-Nachrichten gesendet werden, bis das Problem vom Security Operations-Team Ihrer Organisation behoben wurde. In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die das Sicherheitsteam durchführen sollte.

- [Anzeigen und untersuchen eingeschränkter Benutzer](#view-and-investigate-restricted-users)

- [Anzeigen von Details zu automatisierten Untersuchungen](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Sie müssen über die entsprechenden Berechtigungen zum Ausführen der folgenden Aufgaben verfügen. Siehe [erforderliche Berechtigungen für die Verwendung von Air-Funktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Anzeigen und untersuchen eingeschränkter Benutzer

Sie haben einige Optionen, um zu einer Liste eingeschränkter Benutzer zu navigieren. Im Security & Compliance Center können Sie beispielsweise zu **Threat Management**  >  **Review**  >  **restricted users**wechseln. Im folgenden Verfahren wird die Navigation mithilfe des **Alerts** -Dashboards beschrieben, eine gute Möglichkeit, um verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.

1. Gehen Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **Warnungs**  >  **Dashboard**aus.

3. Wählen Sie im Widget **andere Benachrichtigungen** die Option **eingeschränkte Benutzer**aus.

   ![Widget "andere Warnungen"](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.<br/>![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Aktionen durchführen zu können, beispielsweise [das Freigeben des eingeschränkten Benutzers](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

### <a name="view-details-about-automated-investigations"></a>Anzeigen von Details zu automatisierten Untersuchungen

Wenn eine automatisierte Untersuchung begonnen hat, können Sie Details und Ergebnisse im Security & Compliance Center anzeigen. Wechseln Sie zu **Threat Management**  >  **Investigations**, und wählen Sie dann eine Untersuchung aus, um die Details anzuzeigen.

Weitere Informationen finden Sie unter [View Details of a Investigation](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- **Behalten Sie Ihre Benachrichtigungen im Vorder**Grund. Wie Sie wissen, gilt: je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Kunden und Partner. Frühzeitige Erkennung und zeitnahe Reaktion sind wichtig, um Bedrohungen zu minimieren, insbesondere dann, wenn das Konto eines Benutzers kompromittiert wird.

- **Automatisierung unterstützt, ersetzt aber Ihr Sicherheits Betriebsteam**. Automatisierte Ermittlungs-und Antwortfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheits Betriebsteam muss wahrscheinlich einige Untersuchungen und Korrekturen durchführen. Benötigen Sie Hilfe? Weitere Informationen finden Sie unter [überprüfen und Genehmigen von Aktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Verlassen Sie sich nicht auf eine verdächtige Anmelde Warnung als einzigen Indikator**. Wenn ein Benutzerkonto kompromittiert wird, wird möglicherweise eine verdächtige Anmelde Warnung ausgelöst. Manchmal handelt es sich um die Reihe von Aktivitäten, die auftreten, nachdem ein Konto kompromittiert wurde, das eine Warnung auslöst. Möchten Sie mehr über Benachrichtigungen erfahren? Siehe [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen der erforderlichen Berechtigungen für die Verwendung von Air-Funktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Suchen und untersuchen von böswilligen e-Mails in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Informationen zu Air in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was bald kommt und wie Sie Rollen](https://www.microsoft.com/microsoft-365/roadmap?filters=)

