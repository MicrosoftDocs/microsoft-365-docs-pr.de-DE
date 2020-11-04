---
title: Bereitstellen des Sicherheitsrisiko Schutzes für Netzwerke in Microsoft 365
description: Erfahren Sie, wie Sie Threat Protection-Dienste und Sicherheitsfunktionen für IT-Netzwerke in Microsoft 365 E5 bereitstellen.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 1bf06c605290dc94f64da6c2aabca3683c234c9a
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906751"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Bereitstellen von Threat Protection-Funktionen in Microsoft 365

Schadsoftware und ausgefeilte Cyberangriffe, wie etwa Datei [unschädliche](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware) [Bedrohungen](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), sind häufig vorkommen. Unternehmen müssen sich und ihre Kunden mit effektiven IT-Netzwerksicherheitsfunktionen schützen. Solche Angriffe können große Probleme für Ihre Organisation verursachen, angefangen beim Verlust von Vertrauen bis hin zu finanziellen Problemen, Unternehmens bedrohlichen Ausfallzeiten und vielem mehr. Der Schutz vor Bedrohungen ist wichtig, kann jedoch eine Herausforderung darstellen, um zu bestimmen, wo sich die Zeit, der Aufwand und die Ressourcen Ihrer Organisation konzentrieren müssen. 

Microsoft-Sicherheitslösungen sind in unsere Produkte und Dienste integriert. Automatisierung und maschinelle Lernfunktionen reduzieren die Auslastung Ihrer Sicherheitsteams, um sicherzustellen, dass die richtigen Elemente adressiert werden. Und die Stärke von Microsoft Network Security-Lösungen basiert auf Billionen von Signalen, die wir jeden Tag in unserem [intelligenten Sicherheits Diagramm](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)verarbeiten. Microsoft 365-Sicherheitslösungen umfassen [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), eine Lösung, mit der Signale über Ihre e-Mails, Daten, Geräte und Identitäten zusammengeführt werden, um ein Bild der fortgeschrittenen Bedrohungen Ihrer Organisation zu zeichnen.


Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Verwenden Sie diesen Artikel als Leitfaden für die Implementierung Ihrer Bedrohungsschutz Lösung.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bedrohungsschutz in Microsoft 365 E5

Mit [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) können Sie Ihre Organisation durch adaptive, integrierte Intelligenz schützen. Mit den Features zum Schutz vor Bedrohungen in Microsoft 365 E5 können Sie erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Aktionen in Ihrer lokalen und Cloud-Umgebung erkennen und untersuchen.

In Microsoft 365 E5 sind die Funktionen zum Schutz von Bedrohungen standardmäßig integriert. Signale aus jeder Funktion stärken die Gesamt Fähigkeit zur Erkennung und Reaktion auf Bedrohungen. Die kombinierte Gruppe von Funktionen bietet den besten Schutz für Unternehmen, insbesondere für multinationale Organisationen, im Vergleich zu nicht von Microsoft ausgeführten Produkten. In der folgenden Abbildung sind die Bedrohungen für den Schutz von Diensten und Funktionen in Microsoft 365 E5 dargestellt, die in diesem Artikel beschrieben werden.

![Übersicht über Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Sobald Sie einen der Verteidiger für Office 365 Funktionen bereitstellen, können Sie Microsoft 365 Defender aktivieren, wodurch die Signale und Daten an einer Stelle zusammengeführt werden. 

![Konzeptionelle Illustration des Microsoft 365 Defender-Dashboards](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In der folgenden Abbildung ist ein empfohlener Pfad für die bereitstellungdieser einzelnen Funktionen dargestellt. 

![M365-Bedrohungsschutz Signale](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Lösung/Funktionen  |Beschreibung  |
|---------|---------|
|Mehrstufige Authentifizierung und bedingter Zugriff     |Schutz vor kompromittierten Identitäten und Geräten. Beginnen Sie mit diesem Schutz, da er Grundlegendes ist. Die in diesem Leitfaden Empfohlene Konfiguration umfasst Azure AD Identitätsschutz als Voraussetzung.     |
|Microsoft Defender for Identity     |  Eine Cloud-basierte Sicherheitslösung, die ihre lokalen Active Directory Signale nutzt, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insider Aktionen, die an Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen. Konzentrieren Sie sich auf Microsoft Defender for Identity Next, da es Ihre on-Prem-und Ihre Cloud-Infrastruktur schützt, keine Abhängigkeiten oder Voraussetzungen hat und unmittelbare Vorteile bieten kann.       | 
|Microsoft Defender für Office 365     | Schützt Ihre Organisation vor böswilligen Bedrohungen durch e-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Schutzmaßnahmen für Malware, Phishing, Spoofing und andere Angriffstypen. Das Konfigurieren von Microsoft Defender für Office 365 wird als nächstes empfohlen, da das Bereitstellen von Änderungs Steuerelementen, das Migrieren von Einstellungen aus dem etablierten System und andere Überlegungen länger dauern kann. <br><br>Hinweis: Stellen Sie sicher, dass Sie die Funktionen für den Bedrohungsschutz konfigurieren, die in allen Office 365 Abonnements (Exchange Online Protection) enthalten sind.       |
|Microsoft Defender für Endpunkt    | Eine Endpunktschutz Plattform, die zum verhindern, erkennen, untersuchen und reagieren auf Erweiterte Bedrohungen beiträgt.  Defender for Endpoint kann einige Zeit dauern, bis die Bereitstellung erfolgt, die Konfiguration kann jedoch parallel zu anderen Funktionen erfolgen.   |
|Microsoft Cloud App Security     |   Ein Cloud Access-Sicherheits Broker für Ermittlung, Untersuchung und Steuerung. Sie können Microsoft Cloud App Security frühzeitig aktivieren, um mit dem Sammeln von Daten und Einblicken zu beginnen. Die Implementierung von Informationen und anderer gezielter Schutz in ihren Saas-apps umfasst die Planung und kann mehr Zeit in Anspruch nehmen.       | 

> [!TIP]
> Organisationen mit mehreren Sicherheitsteams können diese Funktionen parallel implementieren.

## <a name="deploy-your-threat-protection-solution"></a>Bereitstellen Ihrer Bedrohungsschutz Lösung

Um sicherzustellen, dass Ihre Organisation den bestmöglichen Schutz bietet, richten Sie die Sicherheitslösung ein, und stellen Sie Sie bereit, um die folgenden Schritte einzufügen:

1. [Einrichten von Richtlinien für mehrstufige Authentifizierung und bedingten Zugriff](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurieren von Microsoft Defender für Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Aktivieren von Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Konfigurieren von Defender für Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Konfigurieren von Microsoft Defender für den Endpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Konfigurieren der Microsoft Cloud-App-Sicherheit](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Überwachen des Status und ergreifen von Aktionen](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Benutzer trainieren](deploy-threat-protection-configure.md#step-8-train-users)

Ihre Threat Protection-Funktionen können parallel konfiguriert werden, wenn Sie also mehrere Netzwerk Sicherheitsteams für verschiedene Dienste zuständig sind, können Sie die Schutzfunktionen Ihrer Organisation gleichzeitig konfigurieren. Das folgende Diagramm veranschaulicht den allgemeinen Prozess für die Bereitstellung von Threat Protection-Funktionen. 

![Prozess für die Bereitstellung von Threat Protection-Funktionen](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
