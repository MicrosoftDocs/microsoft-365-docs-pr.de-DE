---
title: Bereitstellen von Bedrohungsschutzfunktionen in Microsoft 365
description: Verschaffen Sie sich einen Überblick über Die Bedrohungsschutzdienste und Sicherheitsfunktionen in Microsoft 365 E5. Schützen Sie Ihre Benutzerkonten, Geräte, E-Mail-Inhalte und mehr mit Microsoft 365 E5.
keywords: advanced threat protection, security, microsoft 365 E5, solution, protect devices, defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 0edc3847d6b832f254c6f289355570a3a044b1f4
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061037"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Bereitstellen von Bedrohungsschutzfunktionen in Microsoft 365 E5

Diese Lösung beschreibt leistungsstarke Funktionen zum Schutz vor Bedrohungen in Microsoft 365 E5 und warum diese Funktionen wichtig sind. Lesen Sie diese Lösung, um einen Überblick darüber zu erhalten, was in Microsoft 365 E5 enthalten ist, wie Funktionen zum Schutz vor Bedrohungen funktionieren und wie Sie den Bedrohungsschutz in Ihrer Organisation einrichten und konfigurieren.

## <a name="why-threat-protection-is-important"></a>Warum Bedrohungsschutz wichtig ist 

[Schadsoftware](/windows/security/threat-protection/intelligence/understanding-malware)und komplexe Cyberangriffe, z. B. [dateilose](/windows/security/threat-protection/intelligence/fileless-threats)Bedrohungen, sind häufig vorkommen. Unternehmen müssen sich und ihre Kunden mit effektiven IT-Sicherheitsfunktionen schützen. Cyberangriffe können große Probleme für Ihre Organisation verursachen, von Vertrauensverlusten bis hin zu finanziellen Problemen, geschäftsbedrohlichen Ausfallzeiten und vielem mehr. Der Schutz vor Bedrohungen ist wichtig, es kann jedoch schwierig sein, zu bestimmen, wo die Zeit, der Aufwand und die Ressourcen Ihrer Organisation konzentriert werden sollen. Microsoft 365 E5 kann ihnen helfen. 

Microsoft-Sicherheitslösungen sind in unsere Produkte und Dienste integrierte. Automatisierungs- und Maschinelles Lernen verringern die Last für Ihre Sicherheitsteams, um sicherzustellen, dass die richtigen Elemente adressiert werden. Und die Stärke von Microsoft-Sicherheitslösungen baut auf Billionen von Signalen auf, die wir täglich in unserem [Intelligenten Sicherheitsdiagramm verarbeiten.](/graph/security-concept-overview) Microsoft 365-Sicherheitslösungen umfassen [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), eine Lösung, die Signale über Ihre E-Mails, Daten, Geräte und Identitäten hinweg zusammen bringt, um ein Bild von erweiterten Bedrohungen für Ihre Organisation zu zeichnen.

Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a>Bedrohungsschutz in Microsoft 365 E5

[Mit Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) können Sie Ihre Organisation mit adaptiver, integrierter Intelligenz schützen. Mit den Bedrohungsschutzfeatures in Microsoft 365 E5 können Sie erweiterte Bedrohungen, gefährdete Identitäten und schädliche Aktionen in Ihrer lokalen und Cloudumgebung erkennen und untersuchen.

In Microsoft 365 E5 sind Bedrohungsschutzfunktionen standardmäßig integriert. Signale jeder Funktion erhöhen die Allgemeine Fähigkeit, Bedrohungen zu erkennen und darauf zu reagieren. Die kombinierten Funktionen bieten den besten Schutz für Organisationen, insbesondere für multinationale Organisationen, im Vergleich zum Ausführen von Nicht-Microsoft-Produkten. Die folgende Abbildung zeigt die In diesem Artikel beschriebenen Dienste und Funktionen zum Schutz vor Bedrohungen in Microsoft 365 E5.

![Übersicht über Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender vereint die Signale und Daten in einem einheitlichen [Microsoft 365 Security Center.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Konzeptionelle Abbildung des Microsoft 365 Defender-Dashboards](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

Die folgende Abbildung zeigt einen empfohlenen Pfad für die Bereitstellung dieser einzelnen Funktionen. 

> [!div class="mx-imgBorder"]
> ![M365-Bedrohungsschutzsignale](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Lösung/Funktionen  |Beschreibung  |
|---------|---------|
|Mehrstufige Authentifizierung und bedingter Zugriff     |Schutz vor gefährdeten Identitäten und Geräten. Beginnen Sie mit diesem Schutz, da er grundsindlich ist. Die in diesem Leitfaden empfohlene Konfiguration umfasst Azure AD Identity Protection als Voraussetzung.     |
|Microsoft Defender for Identity     |  Eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory Domain Services (AD DS)-Signale nutzt, um erweiterte Bedrohungen, gefährdete Identitäten und schädliche Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die an Ihre Organisation gerichtet sind. Konzentrieren Sie sich als Nächstes auf Microsoft Defender for Identity, da es Ihre lokale und Cloudinfrastruktur schützt, keine Abhängigkeiten oder Voraussetzungen hat und sofortige Sicherheitsvorteile bieten kann. | 
|Microsoft Defender für Office 365     | Schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Schutz vor Schadsoftware, Phishing, Spoofing und anderen Angriffstypen. Als Nächstes wird die Konfiguration von Microsoft Defender für Office 365 empfohlen, da die Änderungssteuerung, das Migrieren von Einstellungen vom etablierten System und andere Überlegungen länger dauern können. <p>**HINWEIS**: Stellen Sie sicher, dass Sie die Bedrohungsschutzfunktionen konfigurieren, die in allen Office 365-Abonnements (Exchange Online Protection) enthalten sind.       |
|Microsoft Defender für Endpunkt    | Eine Endpunktschutzplattform, die hilft, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und auf sie zu reagieren.  Die Bereitstellung von Defender for Endpoint kann einige Zeit in Dauern dauern, die Konfiguration kann jedoch parallel zu anderen Funktionen ausgeführt werden.   |
|Microsoft Cloud App Security     |   Ein Cloudzugriffssicherheitsbroker für Ermittlung, Untersuchung und Governance. Sie können Microsoft Cloud App Security frühzeitig aktivieren, um mit dem Sammeln von Daten und Erkenntnissen zu beginnen. Die Implementierung von Informationen und anderen gezielten Schutz in Ihren SaaS-Apps umfasst die Planung und kann mehr Zeit in Sich nehmen.       | 

> [!TIP]
> Organisationen mit mehreren Sicherheitsteams können diese Funktionen parallel implementieren. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planen der Bereitstellung Ihrer Bedrohungsschutzlösung

Das folgende Diagramm veranschaulicht den prozess auf hoher Ebene für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen. 

![Prozess für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Um sicherzustellen, dass Ihre Organisation über den bestmöglichen Schutz verfügt, richten Sie Ihre Sicherheitslösung mithilfe eines Prozesses ein, der die folgenden Schritte umfasst:

1. [Einrichten von mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies).
2. [Konfigurieren von Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Aktivieren Sie Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Konfigurieren von Defender für Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Konfigurieren von Microsoft Defender für Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Konfigurieren von Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Überwachen Sie den Status, und ergreifen Sie Aktionen.](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Schulen von Benutzern](deploy-threat-protection-configure.md#step-8-train-users).

Ihre Bedrohungsschutzfeatures können parallel konfiguriert werden. Wenn Sie also mehrere Netzwerksicherheitsteams für verschiedene Dienste verantwortlich sind, können sie die Schutzfeatures Ihrer Organisation gleichzeitig konfigurieren.

## <a name="next-step"></a>Nächster Schritt

Fahren Sie [mit Configure threat protection capabilities across Microsoft 365 fort.](deploy-threat-protection-configure.md)


