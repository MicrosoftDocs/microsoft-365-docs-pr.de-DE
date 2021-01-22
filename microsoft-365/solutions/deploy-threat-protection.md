---
title: Bereitstellen des Schutzes vor Bedrohungen durch Netzwerksicherheit in Microsoft 365
description: Erfahren Sie, wie Sie Bedrohungsschutzdienste und Funktionen für die Sicherheit des IT-Netzwerks in Microsoft 365 E5 bereitstellen.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926750"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Bereitstellen von Bedrohungsschutzfunktionen in Microsoft 365

[Schadsoftware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)und komplexe Cyberangriffe, z. B. dateilose [Bedrohungen,](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)sind häufig vorkommen. Unternehmen müssen sich und ihre Kunden mit effektiven Funktionen für die Sicherheit des IT-Netzwerks schützen. Solche Angriffe können große Probleme für Ihre Organisation verursachen, von Einem Verlust des Vertrauens bis hin zu finanziellen Problemen, ausfallbedrohenden Ausfallzeiten und vielem mehr. Der Schutz vor Bedrohungen ist wichtig, aber es kann schwierig sein, zu bestimmen, wo die Zeit, der Aufwand und die Ressourcen Ihrer Organisation konzentriert werden sollten. 

Sicherheitslösungen von Microsoft sind in unsere Produkte und Dienste integrierte. Automatisierungs- und Machine Learning-Funktionen verringern die Belastung Ihrer Sicherheitsteams, um sicherzustellen, dass die richtigen Elemente behandelt werden. Und die Stärke von Microsoft-Netzwerksicherheitslösungen baut auf Billionen von Signalen auf, die wir täglich in unserem [Intelligent Security Graph verarbeiten.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-Sicherheitslösungen umfassen [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)eine Lösung, die Signale über Ihre E-Mails, Daten, Geräte und Identitäten hinweg zusammen bringt, um ein Bild von erweiterten Bedrohungen für Ihre Organisation zu zeichnen.


Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Verwenden Sie diesen Artikel als Leitfaden für die Implementierung Ihrer Bedrohungsschutzlösung.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedrohungsschutz in Microsoft 365 E5

[Mit Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) können Sie Ihre Organisation mit adaptiver, integrierter Intelligenz schützen. Mit den Bedrohungsschutzfunktionen in Microsoft 365 E5 können Sie erweiterte Bedrohungen, gefährdete Identitäten und böswillige Aktionen in Ihrer lokalen und Cloudumgebung erkennen und untersuchen.

In Microsoft 365 E5 sind Funktionen zum Schutz vor Bedrohungen standardmäßig integriert. Signale von jeder Funktion erhöhen die Gesamtfähigkeit, Bedrohungen zu erkennen und darauf zu reagieren. Die kombinierten Funktionen bieten im Vergleich zur Ausführung von Nicht-Microsoft-Produkten den besten Schutz für Organisationen, insbesondere multinationale Organisationen. Die folgende Abbildung zeigt die Dienste und Funktionen zum Schutz vor Bedrohungen in Microsoft 365 E5, die in diesem Artikel beschrieben werden.

![Übersicht über Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Sobald Sie eine der Funktionen von Defender für Office 365 bereitstellen, können Sie Microsoft 365 Defender aktivieren, wodurch die Signale und Daten an einem Ort zusammenkommen. 

![Konzeptionelle Abbildung des Microsoft 365 Defender-Dashboards](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

Die folgende Abbildung zeigt einen empfohlenen Pfad für die Bereitstellung dieser einzelnen Funktionen. 

![M365-Bedrohungsschutzsignale](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Lösung/Funktionen  |Beschreibung  |
|---------|---------|
|Mehrstufige Authentifizierung und bedingter Zugriff     |Schutz vor gefährdeten Identitäten und Geräten. Beginnen Sie mit diesem Schutz, da er grundsensell ist. Die in diesem Leitfaden empfohlene Konfiguration umfasst Azure AD Identity Protection als Voraussetzung.     |
|Microsoft Defender for Identity     |  Eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory-Signale nutzt, um erweiterte Bedrohungen, gefährdete Identitäten und böswillige Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die an Ihre Organisation gerichtet sind. Konzentrieren Sie sich als Nächstes auf Microsoft Defender for Identity, da es Ihre vor Ort und Ihre Cloudinfrastruktur schützt, keine Abhängigkeiten oder Voraussetzungen aufweist und sofortige Vorteile bieten kann.       | 
|Microsoft Defender für Office 365     | Schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Schutz vor Schadsoftware, Phishing, Spoofing und anderen Angriffstypen. Als Nächstes wird die Konfiguration von Microsoft Defender für Office 365 empfohlen, da die Änderungssteuerung, das Migrieren von Einstellungen aus dem systemintegrierenden System und andere Überlegungen länger dauern können. <br><br>Hinweis: Konfigurieren Sie unbedingt die Bedrohungsschutzfunktionen, die in allen Office 365-Abonnements (Exchange Online Protection) enthalten sind.       |
|Microsoft Defender für Endpunkt    | Eine Endpunktschutzplattform, die hilft, fortgeschrittene Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren.  Die Bereitstellung von Defender for Endpoint kann einige Zeit dauern, die Konfiguration kann jedoch parallel zu anderen Funktionen durchgeführt werden.   |
|Microsoft Cloud App-Sicherheit     |   Ein Cloudzugriffssicherheitsbroker für Ermittlung, Untersuchung und Governance. Sie können Microsoft Cloud App Security frühzeitig aktivieren, um mit dem Sammeln von Daten und Einblicken zu beginnen. Die Implementierung von Informationen und anderer gezielter Schutz in Ihren SaaS-Apps umfasst die Planung und kann mehr Zeit in Sich nehmen.       | 

> [!TIP]
> Organisationen mit mehreren Sicherheitsteams können diese Funktionen parallel implementieren.

## <a name="deploy-your-threat-protection-solution"></a>Bereitstellen ihrer Lösung zum Schutz vor Bedrohungen

Um sicherzustellen, dass Ihre Organisation über den bestmöglichen Schutz verfügt, richten Sie Ihre Sicherheitslösung ein, und stellen Sie sie so ein, dass sie die folgenden Schritte umfasst:

1. [Einrichten von Mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurieren von Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Aktivieren von Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Konfigurieren von Defender für Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Konfigurieren von Microsoft Defender für Endpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Konfigurieren von Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Überwachen des Status und Ergreifen von Aktionen](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Benutzer trainieren](deploy-threat-protection-configure.md#step-8-train-users)

Ihre Bedrohungsschutzfeatures können parallel konfiguriert werden. Wenn Sie also mehrere Netzwerksicherheitsteams haben, die für verschiedene Dienste verantwortlich sind, können sie die Schutzfunktionen Ihrer Organisation gleichzeitig konfigurieren. Das folgende Diagramm veranschaulicht den prozess auf hoher Ebene für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen. 

![Prozess für die Bereitstellung von Funktionen zum Schutz vor Bedrohungen](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
