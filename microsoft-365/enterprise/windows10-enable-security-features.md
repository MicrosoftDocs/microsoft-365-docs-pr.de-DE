---
title: Bereitstellen von Sicherheitsmerkmalen von Windows 10 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, Security
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: 60145444a7fb2b4ddf2ea6a3606e04aa04a578af
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291622"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Schritt 5: Bereitstellen von Windows 10 Enterprise-Sicherheitsfeatures

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 bietet Sicherheitsfunktionen zum Schutz von Unternehmensbenutzern, zum Beenden von Bedrohungen und zum Verhindern von Datenverlust. 

Weitere Informationen zu diesen Technologien finden Sie unter:
* [Identitätsschutz](https://docs.microsoft.com/windows/security/identity-protection/) – erfahren Sie mehr über Windows Hello for Business, den Schutz von Anmeldeinformationen und die Zugriffssteuerung.
* [Threat Protection](https://docs.microsoft.com/windows/threat-protection/) – erfahren Sie mehr über Windows Defender Advanced Threat Protection, eine einheitliche Plattform für vorbeugenden Schutz, Erkennung nach Verstößen, automatisierte Untersuchungen und Antwort.
* [Informationsschutz](https://docs.microsoft.com/windows/security/information-protection/) – erfahren Sie mehr über BitLocker, Windows Information Protection und andere Möglichkeiten, wie Windows 10 Enterprise-Daten schützt. 

In diesem Schritt wird gezeigt, wie Sie mithilfe dieser Sicherheitsfeatures bereitstellen, verwalten, konfigurieren und behandeln können:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) ist eine Antischadsoftware-Lösung, die in Windows 10 integriert ist. Es bietet Sicherheit und Antischadsoftware-Verwaltung für Desktops, tragbare Computer und Server. Weitere Informationen zu Windows Defender AV, zu den Mindestanforderungen und zur Verwaltung dieser Funktion finden Sie unter [Windows Defender Antivirus in Windows 10 und Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Wenn Sie nicht Windows Defender AV als primären Antivirus-Client verwenden oder wenn Sie auch Windows Defender ATP verwenden, müssen Sie einige Überlegungen berücksichtigen. Weitere Informationen finden Sie unter [Windows Defender AV Compatibility](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Bereitstellung und Verwaltung
Führen Sie die folgenden Schritte aus, um Windows Defender AV bereitzustellen und zu verwalten:

* [Bereitstellen, verwalten und melden von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Referenzthemen für Verwaltungs-und Konfigurationstools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Konfiguration
Benutzer können eine Reihe von Features konfigurieren. Weitere Informationen finden Sie in den folgenden Ressourcen:

* [Konfigurieren von Windows Defender AV-Features](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Referenzthemen für Verwaltungs-und Konfigurationstools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Informationen zu den Konfigurationsoptionen finden Sie in dieser Liste aller Einstellungen (gemäß der Gruppenrichtlinienkonfiguration): [Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Sie können mithilfe des [Windows Defender AV Protection-Evaluierungs](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) Handbuchs die Schutzebene und die Auswirkungen von Windows Defender AV in Ihrem Netzwerk bewerten. Dies kann auch beim Erstellen einer anfänglichen Konfiguration oder als Schnellstartanleitung hilfreich sein und wird regelmäßig aktualisiert, um die nützlichsten Empfehlungen für das Konfigurieren und Aktivieren von Features bereitzustellen, um maximalen Schutz zu gewährleisten.

### <a name="reporting"></a>Reporting
Sie können die Berichterstellung über ein Konfigurationstool wie System Center Configuration Manager oder Microsoft InTune abrufen. Sie können auch Berichte über Update Compliance (OMS) oder über Windows-Ereignisprotokolle in SIEM abrufen. Wenn Sie über eine Lizenz für Windows Defender ATP verfügen, können Sie auch Berichte zu Windows Defender AV-Entdeckungen erhalten und grundlegende Korrekturen durchführen. Weitere Informationen finden Sie in den folgenden Ressourcen:
* [Bereitstellen, verwalten und melden von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Bericht zu Windows Defender AV Protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Übersicht über das Windows Defender-ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Informationen zur grundlegenden Problembehandlung von Fehler-und Ereigniscodes finden Sie unter [Überprüfen von Ereignisprotokollen und Fehlercodes zur Behandlung von Problemen mit Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Sie können auch Probleme (wie falsch positive Ergebnisse) mithilfe des Windows Defender Security Intelligence-Übermittlungssystems übermitteln. Weitere Informationen finden Sie unter [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender Exploit Guard ist eine neue Gruppe von Host Intrusion Prevention-Funktionen für Windows 10. Weitere Informationen zu Windows Defender Exploit Guard, zu den Mindestanforderungen und zur Verwaltung dieser Funktion finden Sie unter [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Führen Sie die folgenden Schritte aus, um Windows Defender Exploit Guard bereitzustellen, zu verwalten und zu konfigurieren:
* [Schutz ausNutzen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [AnGriffs Oberflächenschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Netzwerkschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Zugriff auf kontrollierte Ordner](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Sie können eine Reihe von Evaluierungs Themen verwenden, um die Schutzebene und die Auswirkungen von Windows Defender Exploit Guard in Ihrem Netzwerk zu bewerten. Dies kann auch bei der Erstellung einer anfänglichen Konfiguration oder als Schnellstartanleitung hilfreich sein, und die Themen und Anleitungen werden regelmäßig aktualisiert, um die nützlichsten Empfehlungen für das Konfigurieren und Aktivieren von Features für maximalen Schutz zu bieten. Weitere Informationen finden Sie unter [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
Sie können die Berichterstellung mithilfe eines Konfigurationstools wie System Center Configuration Manager oder InTune abrufen. Sie können auch Berichte abrufen, indem Sie Windows-Ereignisprotokolle in SIEM verwenden. Wenn Sie über eine Lizenz für Windows Defender ATP verfügen, können Sie auch Berichte zu Windows Defender AV-Entdeckungen erhalten und grundlegende Korrekturen durchführen. Weitere Informationen finden Sie in den folgenden Ressourcen:
* [Anzeigen von Windows Defender Exploit Guard-Ereignissen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Übersicht über das Windows Defender-ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Sie können eine einfache Problembehandlung durchführen oder optional Microsoft CAB-Dateien bereitstellen und Probleme (wie falsch positive Ergebnisse) mithilfe des Windows Defender Security Intelligence-Übermittlungssystems übermitteln. Weitere Informationen finden Sie unter [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender ATP, nur verfügbar mit Microsoft 365 Enterprise E5-Plan, ist ein Sicherheitsdienst, der es Unternehmenskunden ermöglicht, erweiterte Bedrohungen in ihren Netzwerken zu ermitteln, zu untersuchen und darauf zu reagieren. Weitere Informationen zu Windows Defender ATP, zu den Mindestanforderungen und zur Verwaltung dieser Funktion finden Sie unter:

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Mindestanforderungen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Für die Bereitstellung von Windows Defender ATP müssen Sie sicherstellen, dass Sie über die richtige Windows-Lizenz verfügen. Nachdem Sie sichergestellt haben, dass Sie über die richtige Lizenz verfügen, müssen Sie sich entscheiden, wo Ihre Daten gespeichert werden sollen. Danach können Sie Onboarding-Endpunkte für den Dienst starten.

Weitere Informationen zu diesen Schritten finden Sie in den folgenden Themen: 

* [ÜberPrüfen der Lizenzierung und Abschließen der Einrichtung](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Speicherung und Datenschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Onboard-Endpunkte und Setup Zugriff](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Ermitteln, untersuchen, Antworten
Nach dem erfolgreichen Onboarding von Endpunkten zum Dienst können Sie mit der Untersuchung von Warnungen in den verschiedenen Dashboards beginnen. Nachdem Sie Warnungen untersucht haben, können Sie auf Warnungen reagieren. 

Weitere Informationen dazu finden Sie unter:
* [Übersicht über das Windows Defender-ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [Verwenden des Windows Defender-ATP-Portals](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Ergreifen von Antwort Aktionen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integration in andere Produkte und Tools
Windows Defender ATP integriert und unterstützt verschiedene andere Produkte und Tools, um die Sicherheitsfunktionen zu erweitern. 

Weitere Informationen zu den Tools und anderen Produkten finden Sie unter:
* [SIEM-Tools](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Erstellen benutzerdefinierter Warnungen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Verwenden von APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Erstellen von Power BI-Berichten](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Problembehandlung
Während des onboardings oder beim Verwenden des Produkts können Probleme auftreten. Weitere Informationen zur Behebung von Problemen finden Sie unter:
* [Problembehandlung bei Onboarding-Problemen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Problembehandlung bei Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Nächster Schritt

[Windows 10 Enterprise-Infrastruktur-Exit-Kriterien](windows10-exit-criteria.md)
