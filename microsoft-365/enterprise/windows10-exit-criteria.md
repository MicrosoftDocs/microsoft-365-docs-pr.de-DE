---
title: 'Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur'
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 06/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für Windows 10 Enterprise erfüllt.
ms.openlocfilehash: 7ac79fec93e4b4aae0b075891917e2f88432b80f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867948"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Wenn Ihre Windows 10 Enterprise-Infrastruktur die folgenden Kriterien erfüllt, können Sie mit Phase 4 fortfahren.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Erforderlich: Ihrer Microsoft 365-Domänen wurden hinzugefügt und überprüft

Der Azure AD-Mandant für Ihre Office 365- und Intune-Abonnements wurde mit Ihren Internetdomänennamen (z. B. „contoso.com“) konfiguriert, statt nur mit einem Domänennamen, der „onmicrosoft.com“ enthält. 

Wenn dies nicht der Fall ist, werden die Authentifizierungsmethoden eingeschränkt, die Sie konfigurieren können. Pass-Through und Verbundauthentifizierung können zum Beispiel den Domänennamen „onmicrosoft.com“ nicht verwenden.

Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md), diese Anforderung zu erfüllen.

## <a name="optional-your-users-are-added-and-licensed"></a>Optional: Benutzer sind hinzugefügt und lizenziert

Die entsprechenden Konten für Ihre Benutzer wurden hinzugefügt, entweder direkt zu Ihrem Azure AD-Mandanten für Ihre Office 365- und Intune-Abonnements oder über die Verzeichnissynchronisierung von Ihrem lokalen Windows Server AD.

Nachdem Sie die Benutzer hinzugefügt haben, können Sie diesen Microsoft 365 Enterprise-Lizenzen zuweisen, entweder direkt als globaler Administrator oder Benutzeradministrator oder automatisch über die Gruppenmitgliedschaft.

Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.

## <a name="optional-diagnostics-are-enabled"></a>Optional: Diagnosen sind aktiviert

Sie haben Diagnosedateneinstellungen mithilfe einer Gruppenrichtlinie, Microsoft Intune, des Registrierungs-Editors oder der Eingabeaufforderung aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Für direktes Upgrade erforderlich: Eine Tasksequenz des Konfigurations-Managers wurde für eine Bereitstellung des Betriebssystems erstellt

Zum Starten einer Tasksequenz des Konfigurations-Managers für ein direktes Upgrade auf einem Gerät unter Windows 7 oder Windows 8.1 müssen Sie die folgenden Schritte durchführen:

- Festlegen der entsprechenden Windows-Diagnosedatenebene
- Überprüfen der Bereitschaft für ein Upgrade von Windows
- Erstellen einer Tasksequenz des Konfigurations-Managers, die eine Gerätesammlung und eine Bereitstellung des Betriebssystems mit einem Windows 10-Betriebssystemimage enthält

Nach Abschluss dieser Schritte können Sie direkte Upgrades auf Geräten durchführen, die für das Upgrade von Windows bereit sind. Um den maximalen Nutzen aus Microsoft 365 Enterprise zu ziehen, führen Sie das Upgrade für so viele Geräte unter Windows 7 und Windows 8.1 wie möglich durch. 

Jedes Gerät unter Windows 10 Enterprise kann von den Vorteilen der integrierten Lösung von Microsoft 365 Enterprise profitieren. Die verbleibenden Geräte unter Windows 7 oder Windows 8.1 können die Cloudtechnologien und erweiterten Sicherheitsfunktionen von Windows 10 Enterprise nicht verwenden.

Gegebenenfalls hilft Ihnen [Schritt 2](windows10-deploy-inplaceupgrade.md), diese Anforderung zu erfüllen.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Erforderlich für neue Geräte: Windows Autopilot wurde konfiguriert

Um Windows Autopilot zum Bereitstellen und Anpassen von Windows 10 Enterprise auf einem neuen Gerät zu verwenden, müssen Sie die folgenden Schritte durchführen:

- Festlegen der entsprechenden Windows-Diagnosedatenebene
- Abschließen der für Windows Autopilot erforderlichen Schritte, die Folgendes umfassen:
- Geräteregistrierung und Anpassung der Windows-Willkommensseite
- Unternehmensbranding für Windows-Willkommensseite
- Automatische Registrierung bei MDM in Microsoft Intune
- Netzwerkkonnektivität mit von Windows Autopilot verwendeten Clouddiensten
- Installation von Windows 10, Version 1703 oder höher auf den Geräten
- Auswählen des Windows Autopilot Deployment-Programms für Ihre Organisation

Nach Abschluss der Konfiguration von Windows Autopilot können Sie diese zum Konfigurieren und Anpassen von Windows 10 Enterprise für die Windows-Willkommensseite für Folgendes verwenden:

- Neue Geräte
- Geräte, die in Ihrer Organisation bereits eingerichtet wurden 

Windows Autopilot konfiguriert das Gerät und verbindet es mit Azure AD.

Ohne Windows Autopilot müssen neue Geräte manuell konfiguriert werden und mit Azure AD verbunden werden.

Gegebenenfalls hilft Ihnen [Schritt 3](windows10-deploy-autopilot.md), diese Anforderung zu erfüllen.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Optional: Bei Verwendung von Windows Analytics Device Health für Geräte für die Überwachung von Windows 10 Enterprise-basierten Geräten

Sie haben die Informationen unter „Integrität von Geräten mit Device Health überwachen“ zum Erkennen und Beheben von Problemen mit Auswirkungen auf die Endbenutzer verwendet. Eine schnelle Behebung dieser Art von Problemen kann Ihre Supportkosten reduzieren und Benutzern das IT-Engagement für Windows 10 Enterprise demonstrieren, was eine schnelle Benutzerakzeptanz in Ihrer Organisation fördern kann. 

Gegebenenfalls hilft Ihnen [Schritt 4](windows10-enable-windows-analytics.md) bei dieser Option.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Erforderlich: Bei Verwendung von Windows Defender Antivirus oder einer eigenen Antischadsoftwarelösung

Sie haben Windows Defender Antivirus oder eine eigene Antischadsoftwarelösung bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Schadsoftware zu schützen. Wenn Sie Windows Defender Antivirus bereitgestellt haben, haben Sie eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Antivirusereignisse und -aktivitäten zu überwachen.

Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-av), diese Anforderung zu erfüllen.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Erforderlich: Verwendung von Windows Defender Exploit Guard

Sie haben Windows Defender Exploit Guard bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Angriffen zu schützen, und haben eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Angriffsschutzereignisse und -aktivitäten zu überwachen.

Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-eg), diese Anforderung zu erfüllen.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a>Erforderlich: Verwendung von Windows Defender Advanced Threat Protection (nur Microsoft 365 Enterprise E5)

Sie haben Windows Defender Advanced Threat Protection (ATP) bereitgestellt, um erweiterte Bedrohungen für Ihr Netzwerk und die Geräte unter Windows 10 Enterprise zu ermitteln, zu analysieren und auf diese zu reagieren. 

Optional haben Sie Windows Defender ATP in anderen Tools integriert, um seine Funktionen zu erweitern.

Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-atp), diese Anforderung zu erfüllen.


## <a name="next-phase"></a>Nächste Phase

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Die nächste Phase im End-to-End-Bereitstellungsprozess für Microsoft 365 Enterprise ist [Office 365 ProPlus](office365proplus-infrastructure.md). |
