---
title: Bereitstellen von Sicherheitsmerkmalen von Windows 10 Enterprise
description: Enthält eine allgemeine Anleitung zu den Schritten, die Sie für die Bereitstellung von Windows 10 Enterprise-Sicherheitsfeatures auf PCs als Teil von Microsoft 365 Enterprise benötigen.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, Security
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d7e71eda9cf0750ce44a978dca742b43f2101d63
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801260"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Schritt 5: Bereitstellen von Windows 10 Enterprise-Sicherheitsfeatures

![Phase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 bietet Sicherheitsfeatures zum Schutz von Unternehmensbenutzern, zum Beenden von Bedrohungen und zum Verhindern von Datenverlust. 

Weitere Informationen zu diesen Technologien finden Sie unter:

* [Identity Protection](https://docs.microsoft.com/windows/security/identity-protection/) – Informationen zu Windows Hello for Business, zum Schutz von Anmeldeinformationen und zur Zugriffssteuerung.
* [Threat Protection](https://docs.microsoft.com/windows/threat-protection/) – erfahren Sie mehr über Microsoft Defender Advanced Threat Protection, eine einheitliche Plattform für vorbeugenden Schutz, Erkennung nach einem Verstoß, automatische Untersuchung und Antwort.
* [Informationsschutz](https://docs.microsoft.com/windows/security/information-protection/) – erfahren Sie mehr über BitLocker, Windows Information Protection und andere Möglichkeiten, wie Windows 10 zum Schutz von Unternehmensdaten beiträgt. 

In diesem Schritt erfahren Sie, wie Sie mithilfe dieser Sicherheitsfeatures bereitstellen, verwalten, konfigurieren und die Problembehandlung durchführen können:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Microsoft Defender Advanced Threat Protection](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) ist eine Antischadsoftware-Lösung, die in Windows 10 integriert ist. Es bietet Sicherheit und Antischadsoftware-Verwaltung für Desktops, tragbare Computer und Server. Weitere Informationen zu Windows Defender AV, zu den Mindestanforderungen und dazu, wie Sie dieses Feature verwalten können, finden Sie unter [Windows Defender Antivirus in Windows 10 und Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Wenn Sie Windows Defender AV nicht als primären Antivirus-Client verwenden oder wenn Sie auch Microsoft Defender ATP verwenden, müssen Sie einige Überlegungen berücksichtigen. Weitere Informationen finden Sie unter [Windows Defender AV Compatibility](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Bereitstellung und Verwaltung
Um Windows Defender AV bereitzustellen und zu verwalten, befolgen Sie die Anweisungen hier:

* [Bereitstellen, verwalten und melden von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Referenzthemen für Verwaltungs-und Konfigurationstools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Konfiguration
Benutzer können eine Reihe von Features konfigurieren. Weitere Informationen finden Sie in den folgenden Ressourcen:

* [Konfigurieren von Windows Defender AV-Features](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Referenzthemen für Verwaltungs-und Konfigurationstools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Informationen zur besseren Übersicht über Konfigurationsoptionen finden Sie in dieser Liste aller Einstellungen (wie in der Gruppenrichtlinienkonfiguration definiert): [verwenden Sie Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus) .

Sie können das [Windows Defender AV Protection Evaluation Guide](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) verwenden, um die Schutzebene und die Auswirkungen von Windows Defender AV in Ihrem Netzwerk zu bewerten. Dies kann auch beim Erstellen einer Erstkonfiguration oder als "Schnellstarthandbuch" hilfreich sein und regelmäßig aktualisiert werden, um die nützlichsten Empfehlungen zum Konfigurieren und Aktivieren von Features zur Gewährleistung eines maximalen Schutzes zu bieten.

### <a name="reporting"></a>Reporting
Sie können die Berichterstellung mithilfe eines Konfigurationstools wie Microsoft Endpoint Configuration Manager oder Microsoft InTune erhalten. Sie können auch die Berichterstellung über die Update Compliance (OMS) oder durch den Verzehr von Windows-Ereignisprotokollen in Ihrem Siem-Objekt erhalten. Wenn Sie eine Lizenz für Microsoft Defender ATP haben, können Sie auch Berichte in Windows Defender AV-Erkennungen abrufen und grundlegende Korrekturen durchführen. Weitere Informationen finden Sie in den folgenden Ressourcen:
* [Bereitstellen, verwalten und melden von Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Bericht über den AV-Schutz von Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Übersicht über das Microsoft Defender ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Informationen zur grundlegenden Problembehandlung von Fehler-und Ereigniscodes finden Sie unter [Überprüfen von Ereignisprotokollen und Fehlercodes zur Behandlung von Problemen mit Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Sie können auch Probleme (beispielsweise falsch positive Ergebnisse) mithilfe des Security Intelligence-Übermittlungssystems von Windows Defender übermitteln. Weitere Informationen finden Sie unter [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender Exploit Guard ist ein neuer Host Intrusion Prevention-Funktionsumfang für Windows 10. Weitere Informationen zu Windows Defender Exploit Guard, zu den Mindestanforderungen und zur Verwaltung dieses Features finden Sie unter [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Um Windows Defender Exploit Guard bereitzustellen, zu verwalten und zu konfigurieren, befolgen Sie die Anweisungen hier:
* [Schutz vor Ausnutzung](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Angriffs Oberflächenschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Netzwerkschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Zugriff auf kontrollierte Ordner](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Sie können eine Reihe von Evaluierungs Themen verwenden, um die Schutzebene und die Auswirkungen von Windows Defender Exploit Guard in Ihrem Netzwerk zu bewerten. Dies kann auch beim Erstellen einer Erstkonfiguration oder als "Schnellstarthandbuch" hilfreich sein, und die Themen und Anleitungen werden regelmäßig aktualisiert, um die nützlichsten Empfehlungen zum Konfigurieren und Aktivieren von Features zur Gewährleistung eines maximalen Schutzes zu bieten. Weitere Informationen erhalten Sie, indem Sie [Windows Defender Exploit Guard auswerten](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
Sie können die Berichterstellung mithilfe eines Konfigurationstools wie Configuration Manager oder InTune erhalten. Sie können auch Berichte erhalten, indem Sie Windows-Ereignisprotokolle in Ihrem Siem-Objekt verwenden. Wenn Sie eine Lizenz für Microsoft Defender ATP haben, können Sie auch Berichte in Windows Defender AV-Erkennungen abrufen und grundlegende Korrekturen durchführen. Weitere Informationen finden Sie in den folgenden Ressourcen:
* [Anzeigen von Windows Defender Exploit Guard-Ereignissen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Übersicht über das Microsoft Defender ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Sie können eine grundlegende Problembehandlung durchführen oder Microsoft CAB-Dateien optional zur Verfügung stellen und Probleme (beispielsweise falsch positive Ergebnisse) mithilfe des Security Intelligence-Übermittlungssystems von Windows Defender übermitteln. Weitere Informationen finden Sie unter [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection
Microsoft Defender ATP, das nur im Microsoft 365 E5-Plan verfügbar ist, ist ein Sicherheitsdienst, mit dem Unternehmenskunden erweiterte Bedrohungen in ihren Netzwerken erkennen, untersuchen und darauf reagieren können. Weitere Informationen zu Microsoft Defender ATP, zu den Mindestanforderungen und zur Verwaltung dieses Features finden Sie unter:

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Mindestanforderungen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Um Microsoft Defender ATP bereitzustellen, müssen Sie sicherstellen, dass Sie über die richtige Windows-Lizenz verfügen. Nachdem Sie überprüft haben, dass Sie über die richtige Lizenz verfügen, müssen Sie den Geolokations Punkt für die Speicherung Ihrer Daten bestimmen. Anschließend können Sie die Onboarding-Endpunkte für den Dienst starten.

Weitere Informationen zu diesen Schritten finden Sie in den folgenden Hauptthemen: 

* [Validieren der Lizenzierung und Abschließen der Einrichtung](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Datenspeicherung und Datenschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Onboard-Endpunkte und Setup Zugriff](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Erkennen, untersuchen, Antworten
Nach erfolgreichem Onboarding von Endpunkten für den Dienst können Sie mit der Untersuchung von Warnungen aus den verschiedenen Dashboards beginnen. Nachdem Sie Warnungen untersucht haben, können Sie Reaktions Aktionen für Warnungen durchführen. 

Weitere Informationen zur Vorgehensweise finden Sie unter:
* [Übersicht über das Microsoft Defender ATP-Portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [Verwenden des Microsoft Defender ATP-Portals](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Reaktions Aktionen ausführen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integration in andere Produkte und Tools
Microsoft Defender ATP integriert und unterstützt verschiedene andere Produkte und Tools, um die Sicherheitsfunktionen zu erweitern. 

Weitere Informationen zu den Tools und anderen Produkten finden Sie unter:
* [Siem-Tools](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Erstellen von benutzerdefinierten Warnungen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Verwenden von APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Erstellen von Power BI-Berichten](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Problembehandlung
Beim Onboarding oder beim Verwenden des Produkts können Probleme auftreten. Weitere Informationen zur Problembehandlung finden Sie unter:
* [Problembehandlung bei Onboarding-Problemen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Problembehandlung bei Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Nächster Schritt

[Windows 10-Beendigungskriterien für die Enterprise-Infrastruktur](windows10-exit-criteria.md)
