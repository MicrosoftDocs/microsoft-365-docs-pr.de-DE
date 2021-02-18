---
title: Informationen zur Testversion von Microsoft Defender für Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: Administratoren können sich über den Testmodus von Microsoft Defender für Office 365 informieren.
ms.openlocfilehash: 0f45379bec52b54059c743823e2c8eb366f9bd59
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289389"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Informationen zur Testversion von Microsoft Defender für Office 365

Microsoft Defender für Office 365 schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Microsoft Defender für Office 365 umfasst:

- **Threat protection-Richtlinien**: Definieren von Richtlinien für den Bedrohungsschutz, um den geeigneten Schutzgrad für Ihre Organisation festzulegen.
- **Berichte:** Anzeigen von Echtzeitberichten zum Überwachen der Leistung von Defender für Office 365 in Ihrer Organisation.
- **Bedrohungsuntersuchung- und Antwortfunktionen** Verwenden Sie brandneue Tools, um Bedrohungen zu untersuchen, zu verstehen, zu simulieren und zu verhindern.
- **Automatisierte Untersuchungs- und Antwortfunktionen** Sparen Sie Zeit und Mühe beim Untersuchen und Beheben von Bedrohungen.

Eine Testversion von Microsoft Defender für Office 365 ist die einfachste Möglichkeit, die Funktionen von Defender für Office 365 auszuprobieren, und die Einrichtung dauert nur ein paar Klicks. Nach Abschluss der Testeinrichtung sind alle Funktionen von Defender für Office 365 Plan 1 und Plan 2 bis zu 90 Tage lang in der Organisation verfügbar.

> [!NOTE]
> Die in diesem Artikel beschriebene automatisierte Konfiguration befindet sich derzeit in der öffentlichen Vorschau und ist möglicherweise nicht an Ihrem Standort verfügbar.

## <a name="terms-and-conditions"></a>Geschäftsbedingungen

Die Testversion von Defender für Office 365 ist 90 Tage lang verfügbar und kann für alle Benutzer initiiert werden. Weitere Informationen finden Sie unter [Microsoft Defender for Office 365 Trial Terms & Conditions](defender-for-office-365-trial-terms-and-conditions.md).

## <a name="set-up-a-defender-for-office-365-trial"></a>Einrichten einer Testversion von Defender für Office 365

Mit einer Testversion können Organisationen die Funktionen von Defender für Office 365 problemlos einrichten und konfigurieren. Während des Setups werden Richtlinien, die ausschließlich für Defender für [](atp-safe-links.md)Office 365 gelten (insbesondere sichere [Anlagen,](atp-safe-attachments.md)sichere Links und Identitätswechselschutz [in Antispamrichtlinien)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)mithilfe der Standardvorlage für voreingestellte Sicherheitsrichtlinien [angewendet.](preset-security-policies.md)

Standardmäßig sind diese Richtlinien auf alle Benutzer in der Organisation begrenzt, Administratoren können die Richtlinien jedoch während oder nach dem Setup anpassen, sodass sie nur für bestimmte Benutzer gelten.

Während des Setups wird die Reaktionsfunktionalität von MDO (in MDO P2 oder äquivalent) auch für die gesamte Organisation eingerichtet. Es ist keine Richtliniende scoping erforderlich.

## <a name="licensing"></a>Lizenzierung

Im Rahmen der Testeinrichtung werden die Defender für Office 365-Lizenzen automatisch auf die Organisation angewendet. Die Lizenzen sind für die ersten 90 Tage kostenlos.

## <a name="permissions"></a>Berechtigungen

Zum Starten oder Beenden der Testversion müssen Sie Mitglied der Rollen **"Globaler Administrator"** oder **"Sicherheitsadministrator"** in Azure Active Directory sein. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen".](../../admin/add-users/about-admin-roles.md)

## <a name="additional-information"></a>Weitere Informationen

Nachdem Sie sich für die Testversion registriert haben, kann es bis zu zwei Stunden dauern, bis die Änderungen und Updates verfügbar sind. Administratoren müssen sich abmelden und sich erneut anmelden, um die Änderungen zu sehen.

Administratoren können die Testversion jederzeit deaktivieren, indem sie zur <> gehen.

## <a name="availability"></a>Verfügbarkeit

Die Testversion von Defender für Office 365 wird schrittweise für bestehende Kunden eingeführt, die bestimmte Kriterien (einschließlich Geografie) erfüllen und nicht über vorhandene Defender für Office 365 Plan 1- oder Plan 2-Lizenzen verfügen (im Abonnement oder als Add-On enthalten).

## <a name="learn-more-about-defender-for-office-365"></a>Weitere Informationen zu Defender für Office 365

Defender für Office 365 hilft Organisationen bei der Sicherung ihres Unternehmens, indem sie einen umfassenden Überblick über die Funktionen bieten.

Weitere Informationen zu Defender für Office 365 finden Sie in diesem [interaktiven Leitfaden.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Konzeptionelles Diagramm von Microsoft Defender für Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prävention

Ein robuster Filterstapel verhindert eine Vielzahl von volumebasierten und gezielten Angriffen, einschließlich Unternehmens-E-Mail-Angriffen, Phishing mit Anmeldeinformationen, Ransomware und erweiterter Schadsoftware.

- [Antiphishingrichtlinien: Exklusive Einstellungen in Defender für Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Sichere Anlagen](atp-safe-attachments.md)
- [Sichere Links](atp-safe-links.md)

### <a name="detection"></a>Erkennung

Branchenführende KI erkennt schädliche und verdächtige Inhalte und korreliert Angriffsmuster, um Kampagnen zu identifizieren, die dem Schutz ausweichen.

- [Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Untersuchung und Suche

Leistungsstarke Erfahrungen helfen bei der Identifizierung, Priorisierung und Untersuchung von Bedrohungen mit erweiterten Funktionen zum Nachverfolgen von Angriffen in Office 365.

- [Bedrohungs-Explorer und Echtzeiterkennungen](threat-explorer.md)
- [Echtzeitberichte in Defender für Office 365](view-reports-for-atp.md)
- [Aufzeichnungen von Bedrohungen – neu und wichtig](threat-trackers.md)
- Integration in [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

### <a name="response-and-remediation"></a>Antwort und Problembehebung

Umfangreiche Funktionen zur Reaktion auf Vorfälle und Automatisierung steigern die Effektivität und Effizienz Ihres Sicherheitsteams.

- [Automatisierte Untersuchung und Reaktion (AIR) in Microsoft Defender für Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Sensibilisierung und Schulung

Umfangreiche Simulations- und Schulungsfunktionen zusammen mit integrierten Erfahrungen in Clientanwendungen fördern das Benutzerbewusstsein.

- [Erste Schritte mit dem Angriffssimulationstraining](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Sicherer Posture

Empfohlene Vorlagen und Konfigurationseinblicke helfen Kunden, sich zu schützen und zu schützen.

- [Voreingestellte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365](preset-security-policies.md)
- [Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365](configuration-analyzer-for-security-policies.md).

## <a name="give-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung besser vor erweiterten Angriffen zu schützen. Teilen Sie Ihre Erfahrungen und Einblicke in Produktfunktionen und Testergebnisse.
