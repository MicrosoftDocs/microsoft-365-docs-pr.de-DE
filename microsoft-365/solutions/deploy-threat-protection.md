---
title: Bereitstellen von Bedrohungsschutzfunktionen Microsoft 365
description: Verschaffen Sie sich einen Überblick über Bedrohungsschutzdienste und Sicherheitsfunktionen in Microsoft 365 E5. Schützen Sie Ihre Benutzerkonten, Geräte, E-Mail-Inhalte und mehr mit Microsoft 365 E5.
keywords: microsoft threat protection, defender, setup, advanced threat protection, security, microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583220"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Bereitstellen von Bedrohungsschutzfunktionen Microsoft 365 E5

Diese Lösung beschreibt leistungsstarke Bedrohungsschutzfunktionen in Microsoft 365 E5 und warum Bedrohungsschutz wichtig ist. Verschaffen Sie sich einen Überblick über den Bedrohungsschutz in Microsoft 365 E5, und erfahren Sie, wie Sie setup and configuration für Ihre Organisation vorgehen.

## <a name="why-threat-protection-is-important"></a>Warum Bedrohungsschutz wichtig ist 

[Schadsoftware](/windows/security/threat-protection/intelligence/understanding-malware)und komplexe Cyberangriffe, z. B. [dateilose](/windows/security/threat-protection/intelligence/fileless-threats)Bedrohungen, sind häufig vorkommen. Unternehmen müssen sich und ihre Kunden mit effektiven IT-Sicherheitsfunktionen schützen. Cyberangriffe können große Probleme für Ihre Organisation verursachen, von Vertrauensverlusten bis hin zu finanziellen Problemen, geschäftsbedrohlichen Ausfallzeiten und vielem mehr. Der Schutz vor Bedrohungen ist wichtig, es kann jedoch schwierig sein, zu bestimmen, wo die Zeit, der Aufwand und die Ressourcen Ihrer Organisation konzentriert werden sollen. Microsoft 365 E5 kann helfen. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedrohungsschutz in Microsoft 365 E5

Microsoft-Sicherheitslösungen sind in unsere Produkte und Dienste integrierte. Automatisierungs- und Maschinelles Lernen verringern die Last für Ihre Sicherheitsteams, um sicherzustellen, dass die richtigen Elemente adressiert werden. Die Stärke von Microsoft-Sicherheitslösungen baut auf Billionen von Signalen auf, die wir täglich in unserem Intelligenten Sicherheitsdienst [Graph.](/graph/security-concept-overview) Microsoft 365 Sicherheitslösungen umfassen [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), eine Lösung, die Signale über Ihre E-Mails, Daten, Geräte und Identitäten hinweg zusammen bringt, um ein Bild von erweiterten Bedrohungen für Ihre Organisation zu zeichnen.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) ermöglicht Es Ihnen, Ihre Organisation mit adaptiver, integrierter Intelligenz zu schützen. Mit den Sicherheitsfunktionen in Microsoft 365 E5 können Sie erweiterte Bedrohungen, gefährdete Identitäten und schädliche Aktionen in Ihrer Umgebung (lokal und in der Cloud) erkennen und untersuchen.

## <a name="better-protection-with-integration"></a>Besserer Schutz bei Integration

In Microsoft 365 E5 sind Bedrohungsschutzfunktionen standardmäßig integriert. Signale jeder Funktion erhöhen die Allgemeine Fähigkeit, Bedrohungen zu erkennen und darauf zu reagieren. Die kombinierten Funktionen bieten den besten Schutz für Organisationen, insbesondere für multinationale Organisationen, im Vergleich zum Ausführen von Nicht-Microsoft-Produkten. Die folgende Abbildung zeigt die In diesem Artikel beschriebenen Dienste und Funktionen zum Schutz vor Bedrohungen.

![Übersicht über Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender vereint die Signale und Daten in einem [einheitlichen Microsoft 365 Security Center](/microsoft-365/security/defender/overview-security-center). 

> [!div class="mx-imgBorder"]
> ![Konzeptionelle Abbildung Microsoft 365 Defender-Dashboards](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die folgende Abbildung zeigt einen empfohlenen Pfad für die Bereitstellung dieser einzelnen Funktionen. 

> [!div class="mx-imgBorder"]
> ![M365-Bedrohungsschutzsignale](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

In der folgenden Tabelle werden die verschiedenen zu konfigurierende Lösungen/Funktionen und deren Aufgaben beschrieben.

|Schritt |Lösung/Funktionen  |Beschreibung  |
|--|---------|---------|
| 1 |[Mehrstufige Authentifizierung und bedingter Zugriff](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Schutz vor gefährdeten Identitäten und Geräten. Beginnen Sie mit diesem Schutz, da er grundsindlich ist. Die in diesem Leitfaden empfohlene Konfiguration umfasst Azure AD Identity Protection als Voraussetzung. Weitere Informationen finden Sie unter [Azure AD Identity Protection](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection).     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  Eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory Domain Services (AD DS)-Signale verwendet, um erweiterte Bedrohungen, gefährdete Identitäten und schädliche Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die an Ihre Organisation gerichtet sind. Konzentrieren Sie sich als Nächstes auf Microsoft Defender for Identity, da es Ihre lokale und Cloudinfrastruktur schützt, keine Abhängigkeiten oder Voraussetzungen hat und sofortige Sicherheitsvorteile bieten kann. Weitere Informationen finden Sie unter [Was ist Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection). | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Kombiniert Signale und orchestriert Funktionen in einer einzigen Lösung. Ermöglicht Es Sicherheitsexperten, Bedrohungssignale zusammen zu heften und den vollständigen Umfang und die Auswirkungen einer Bedrohung zu bestimmen. Microsoft 365 Defender ergreift automatische Aktionen, um den Angriff zu verhindern oder zu beenden und betroffene Postfächer, Endpunkte und Benutzeridentitäten selbst zu beenden. Weitere Informationen finden Sie unter [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). |
| 4  |[Microsoft Defender für Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Schützt vor Schadsoftware, Phishing, Spoofing und anderen Angriffstypen. Die Konfiguration von Microsoft Defender für Office 365 wird empfohlen, da die Änderungssteuerung, das Migrieren von Einstellungen vom etablierten System und andere Überlegungen länger dauern können. Weitere Informationen finden Sie unter [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365).       |
| 5  |[Microsoft Defender für Endpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Verhindert, erkennt, untersucht und reagiert auf erweiterte Bedrohungen auf allen Geräten (auch als Endpunkte bezeichnet). Defender for Endpoint ist ein robustes Bedrohungsschutzangebot. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | Ein Cloudzugriffssicherheitsbroker für Ermittlung, Untersuchung und Governance. Sie können die Microsoft Cloud App Security, um mit dem Sammeln von Daten und Erkenntnissen zu beginnen. Die Implementierung von Informationen und anderen gezielten Schutz in Ihren SaaS-Apps umfasst die Planung und kann mehr Zeit in Sich nehmen. Weitere Informationen finden Sie unter [What is Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Organisationen mit mehreren Sicherheitsteams können Funktionen parallel implementieren. Beispielsweise kann ein Team Defender für die Office 365 ein anderes Team Defender für Endpoint konfigurieren. Die Konfiguration muss unserer vorgeschlagenen Reihenfolge nicht genau folgen. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planen der Bereitstellung Ihrer Bedrohungsschutzlösung

Das folgende Diagramm veranschaulicht den prozess auf hoher Ebene für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen. 

![Prozess für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Um sicherzustellen, dass Ihre Organisation über den bestmöglichen Schutz [verfügt,](deploy-threat-protection-configure.md) richten Sie Ihre Sicherheitslösung mit einem Prozess ein, der die folgenden Schritte umfasst:

1. [Einrichten von mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies).
2. [Konfigurieren von Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Aktivieren sie Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Konfigurieren von Defender für Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Konfigurieren von Microsoft Defender für Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Konfigurieren Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Überwachen Sie den Status, und ergreifen Sie Aktionen.](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Schulen von Benutzern](deploy-threat-protection-configure.md#step-8-train-users).

Ihre Bedrohungsschutzfeatures können parallel konfiguriert werden. Wenn Sie also mehrere Netzwerksicherheitsteams für verschiedene Dienste verantwortlich sind, können sie die Schutzfeatures Ihrer Organisation gleichzeitig konfigurieren.

## <a name="next-step"></a>Nächster Schritt

Fahren Sie mit [Configure threat protection capabilities across Microsoft 365 fort.](deploy-threat-protection-configure.md)


