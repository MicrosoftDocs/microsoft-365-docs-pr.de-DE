---
title: Bereitstellen von Sicherheitsmerkmalen von Windows 10 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365 Microsoft 365 Enterprise Microsoft 365 Windows 10 Enterprise-Dokumentation-Sicherheit
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868199"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Schritt 5: Stellen Sie die Sicherheitsmerkmale von Windows 10 Enterprise bereit

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows-10 bietet Features zum Schutz gegen Bedrohungen, Hilfe Sie schützen Ihrer Geräte und Hilfe zur Steuerung des Zugriffs. 

Weitere Informationen zu diesen Technologien finden Sie unter:
* [Zugriffsschutz](https://docs.microsoft.com/windows/access-protection/) - erfahren Sie mehr über Access S/MIME-Steuerelement digitale Zertifikate, Anmeldeinformationen Guard, User Account Control, virtuelle Smart Karten, Windows Hello Business, Windows-Firewall mit erweiterter Sicherheit und vieles mehr.
* [Gerätesicherheit](https://docs.microsoft.com/windows/device-security/) - enthält AppLocker, BitLocker, Gerät Guard und Trusted Platform Module
* [Virenschutz](https://docs.microsoft.com/windows/threat-protection/) - umfasst Windows Defender-Sicherheitscenter, Windows Defender erweiterte Schutz, Windows Defender Antivirus, Windows Defender Anwendung Guard, Windows Defender Smart Bildschirm und Windows Information Protection

Dieser Schritt zeigt, wie Sie können bereitstellen, verwalten, konfigurieren und Problembehandlung bei der Verwendung von Sicherheitsfeatures:

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender Antivirus (AV) ist eine Modul-Lösung, die in Windows 10 integriert ist. Sicherheit und Verwaltung von Modul bereitgestellt für Desktopcomputern, tragbaren Computern und Servern. Weitere Informationen zu Windows Defender AV, die Mindestanforderungen und wie Sie dieses Feature verwalten können finden Sie unter [Windows Defender Antivirus in 10 für Windows und Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Wenn Windows Defender AV nicht als primären Client antivirus verwenden, oder wenn Sie Windows Defender ATP auch verwenden, einige Aspekte sind müssen Sie berücksichtigen. Finden Sie weitere Informationen finden Sie unter [Windows Defender a/v-Kompatibilität](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Bereitstellung und Verwaltung
Bereitstellen und Verwalten von Windows Defender AV, befolgen die Anweisungen hier:

* [Bereitstellen, verwalten und Berichten über Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Referenzthemen für die Verwaltung und Konfiguration von tools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Konfiguration
Benutzer können eine Reihe von Features konfigurieren. Weitere Informationen finden Sie unter folgenden Ressourcen:

* [Konfigurieren von Windows Defender a/v-Funktionen](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Referenzthemen für die Verwaltung und Konfiguration von tools](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Zum Verständnis der Konfigurationsoptionen finden Sie in dieser Liste aller Einstellungen (gemäß Definition durch die Konfiguration von Gruppenrichtlinien): [Einstellungen zum Konfigurieren und Verwalten von Windows Defender AV mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Sie können [Windows Defender Virenschutz Evaluation Guide](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) , mit denen die Mail-Schutzstufe und Auswirkung von Windows Defender AV in Ihrem Netzwerk verwenden. Dies kann auch bei der Erstellung einer Erstkonfiguration oder als 'quick Start Guide' nützlich sein und wird regelmäßig aktualisiert, um die nützlichsten Empfehlungen zum Konfigurieren und Aktivieren von Features, um sicherzustellen, dass maximalen Schutz bereitzustellen.

### <a name="reporting"></a>Berichte
Sie können die berichterstellung mithilfe von ein Konfigurationstool, wie System Center Configuration Manager oder Microsoft Intune abrufen. Sie können auch von Update Compliance (OMS) oder unter Verwendung der Windows-Ereignisprotokolle in Ihrer SIEM reporting abrufen. Wenn Sie eine Lizenz für Windows Defender ATP verfügen, können auch in Windows Defender AV erkannte reporting zu erhalten und grundlegende Remediation ausführen. Weitere Informationen finden Sie unter folgenden Ressourcen:
* [Bereitstellen, verwalten und Berichten über Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Berichten Sie über Windows Defender AV-Schutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Übersicht über Windows Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Info zur Problembehandlung für grundlegende Fehler- und Ereignis Codes finden Sie unter [Review-Ereignisprotokolle als auch zum Behandeln von Problemen mit Windows Defender a/v-Fehlercodes](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Sie können auch Probleme (beispielsweise falsch positive Ergebnisse) mithilfe von Windows Defender Security Intelligence Übermittlung System senden. Informationen hierzu finden Sie unter [Probleme an Microsoft senden](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender ausnutzen Guard wird ein neuer Satz von Host Intrusion Prevention-Funktionen für Windows 10. Weitere Informationen zu Windows Defender ausnutzen Guard, die Mindestanforderungen und wie Sie dieses Feature verwalten können finden Sie unter [Windows Defender ausnutzen Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Zum Bereitstellen, verwalten und Konfigurieren von Windows Defender ausnutzen Guard, befolgen Sie die Anweisungen hier:
* [Schutz vor Exploits](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Schutz vor Angriffen Fläche](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Netzwerk-Schutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Zugriff auf Ordner gesteuert](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Sie können eine Reihe von Themen Evaluierung, mit denen die Mail-Schutzstufe und Auswirkung von Windows Defender ausnutzen Guard in Ihrem Netzwerk verwenden. Dies kann auch bei der Erstellung einer Erstkonfiguration oder als 'quick Start Guide' hilfreich sein, und die Themen und Anleitung werden regelmäßig aktualisiert, um die nützlichsten Empfehlungen zum Konfigurieren und Aktivieren von Features, um sicherzustellen, dass maximalen Schutz bereitzustellen. Weitere Informationen zum [Windows Defender ausnutzen Guard ausgewertet werden soll](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Berichte
Sie können die berichterstellung mithilfe von ein Konfigurationstool, wie System Center Configuration Manager oder Intune abrufen. Sie können auch unter Verwendung der Windows-Ereignisprotokolle in Ihrer SIEM reporting abrufen. Wenn Sie eine Lizenz für Windows Defender ATP verfügen, können auch in Windows Defender AV erkannte reporting zu erhalten und grundlegende Remediation ausführen. Weitere Informationen finden Sie unter folgenden Ressourcen:
* [Windows Defender ausnutzen Guard-Ereignisse anzeigen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Übersicht über Windows Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Problembehandlung
Sie können grundlegenden Problembehandlung oder optional Microsoft mit CAB-Dateien bereitstellen und Übermitteln von Problemen (beispielsweise falsch positive Ergebnisse) mithilfe von Windows Defender Security Intelligence Übermittlung System. Informationen hierzu finden Sie unter [Probleme an Microsoft senden](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender ATP, sind nur mit Microsoft 365 Enterprise E5 planen, ist ein Service, mit der Unternehmenskunden erkennen, untersuchen und erweiterte Bedrohungen auf ihren Netzwerken beantworten kann. Weitere Informationen zu Windows Defender ATP, die Mindestanforderungen und wie Sie dieses Feature verwalten können finden Sie unter:

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Mindestanforderungen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Bereitstellung, Verwaltung und Konfiguration
Zum Bereitstellen von Windows Defender ATP müssen Sie sicherstellen, dass Sie die Windows-Lizenz berechtigt. Nachdem Sie sichergestellt haben, dass Sie die richtige Lizenz verfügen, müssen Sie entscheiden, den geografischen Standort für die Speicherorte der Daten. Anschließend können Sie Onboarding-Endpunkte für den Dienst starten.

Weitere Informationen zu diesen Schritten finden Sie unter diesen wichtigsten Themen: 

* [Überprüfen Sie der Lizenzierung Bereitstellung, und schließen Sie Set up](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Speicherung von Daten und Datenschutz](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Integrierte Endpunkte und Setup Zugriff](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Erkennen, untersuchen, reagieren
Nach dem erfolgreichen Onboarding Endpunkte mit dem Dienst können Sie starten, untersuchen von Benachrichtigungen aus den verschiedenen Dashboards. Nachdem Sie Warnungen untersucht haben, können Sie Warnungen Antwortaktionen durchführen. 

Weitere Informationen über diese Vorgehensweise finden Sie unter:
* [Übersicht über Windows Defender ATP-portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [Verwenden Sie das Windows Defender ATP-portal](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Antwort Aktionen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrieren Sie in andere Produkte und tools
Windows Defender ATP integriert und unterstützt verschiedene andere Produkte und Tools zum seine Sicherheitsfunktionen zu erweitern. 

Weitere Informationen zu den Tools und anderen Produkten finden Sie unter:
* [SIEM-tools](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Benutzerdefinierte Benachrichtigungen erstellen](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Verwenden Sie APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Erstellen von Power BI-Berichten](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Problembehandlung
Probleme beim Onboarding oder während der Verwendung des Produkts auftreten können. Weitere Informationen zum Beheben von Problemen finden Sie unter:
* [Problembehandlung bei der onboarding](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Problembehandlung bei Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Infrastruktur von Windows 10 Enterprise](windows10-exit-criteria.md)
