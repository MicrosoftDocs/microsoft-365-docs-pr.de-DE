---
title: Verwalten von Microsoft Defender for Endpoint mithilfe von PowerShell, WMI und MPCmdRun.exe
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint mit PowerShell, WMI und MPCmdRun.exe
keywords: nach der Migration, verwalten, Betrieb, Wartung, Auslastung, PowerShell, WMI, MPCmdRun.exe, Windows Defender Advanced Threat Protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 5f0e94360cfaa0c66aedec400e81adc85f4f5450
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185873"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Verwalten von Microsoft Defender for Endpoint mit PowerShell, WMI und MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Wir empfehlen die [Verwendung von Microsoft Endpoint Manager](https://docs.microsoft.com/mem) zum Verwalten der Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet). Endpoint Manager umfasst [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und Microsoft Endpoint [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction). 
> - [Weitere Informationen zu Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Co-manage Microsoft Defender for Endpoint auf Windows 10-Geräten mit Configuration Manager und Intune](manage-atp-post-migration-intune.md)
> - [Verwalten von Microsoft Defender for Endpoint mit Intune](manage-atp-post-migration-intune.md) 

Sie können einige Microsoft Defender Antivirus-Einstellungen auf Geräten mit [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell)  [Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) und dem Microsoft Malware Protection Command Line [Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe) verwalten. Beispielsweise können Sie einige Microsoft Defender Antivirus-Einstellungen verwalten. Und in einigen Fällen können Sie Ihre Regeln für die Reduzierung der Angriffsfläche und Die Schutzeinstellungen für Exploits anpassen. 

> [!IMPORTANT]
> Bedrohungsschutzfeatures, die Sie mithilfe von PowerShell, WMI oder MCPmdRun.exe konfigurieren, können von Konfigurationseinstellungen überschrieben werden, die mit Intune oder Configuration Manager bereitgestellt werden.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Konfigurieren von Microsoft Defender for Endpoint mit PowerShell

Sie können PowerShell verwenden, um Microsoft Defender Antivirus, exploit protection und Ihre Regeln zur Reduzierung der Angriffsfläche zu verwalten.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Microsoft Defender Antivirus** <br/><br/>*Zeigen Sie den Status des Antischalwareschutzes an, konfigurieren Sie Einstellungen für Antivirenscans & Updates, und nehmen Sie weitere Änderungen am Antivirenschutz vor.*    |[Verwenden von PowerShell-Cmdlets zum Konfigurieren und Verwalten von Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Verwenden von PowerShell-Cmdlets zum Aktivieren des in der Cloud übermittelten Schutzes](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Konfigurieren des Exploitschutzes** zur Minderung von Bedrohungen auf den Geräten Ihrer Organisation<br/><br/> *Es wird empfohlen, den Exploitschutz zunächst [im Überwachungsmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) zu verwenden. Auf diese Weise können Sie sehen, wie sich der Exploitschutz auf Apps auswirkt, die Ihre Organisation verwendet.*     | [Anpassen des Exploitschutzes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell-Cmdlets für exploit-Schutz](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Konfigurieren von Regeln zur Reduzierung der Angriffsfläche** mit PowerShell <br/><br/>*Sie können PowerShell verwenden, um Dateien und Ordner von Regeln zur Reduzierung der Angriffsfläche auszuschließen.* |[Anpassen von Regeln zur Reduzierung der Angriffsfläche: Verwenden von PowerShell zum Ausschließen von & Ordnern](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Weitere Informationen finden [Sie im grafischen Benutzeroberflächentool von António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)zum Festlegen von Regeln zur Reduzierung der Angriffsfläche mit PowerShell . |
|**Aktivieren von Netzwerkschutz** mit PowerShell <br/><br/>*Sie können PowerShell verwenden, um Netzwerkschutz zu aktivieren.* |[Aktivieren von Netzwerkschutz mit PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomwareschutz bezeichnet.* |[Aktivieren des kontrollierten Ordnerzugriffs mit PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Konfigurieren der Microsoft Defender-Firewall** zum Blockieren des nicht autorisierten Netzwerkdatenverkehrs, der auf die Geräte Ihrer Organisation oder aus diesen fließt |[Microsoft Defender Firewall mit erweiterter Sicherheitsverwaltung mithilfe Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Konfigurieren von Verschlüsselung und BitLocker** zum Schutz von Informationen auf den Geräten Ihrer Organisation unter Windows |[BitLocker PowerShell-Referenzhandbuch](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Konfigurieren von Microsoft Defender for Endpoint mit Windows Management Instrumentation (WMI)

WMI ist eine Skriptschnittstelle, mit der Sie Einstellungen abrufen, ändern und aktualisieren können. Weitere Informationen finden Sie unter [Verwenden von WMI](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi). 

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Aktivieren des in der Cloud übermittelten Schutzes** auf einem Gerät    |[Verwenden von Windows Management Instruction (WMI) zum Aktivieren des in der Cloud übermittelten Schutzes](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Abrufen, Ändern und Aktualisieren von Einstellungen** für Microsoft Defender Antivirus     | [Konfigurieren und Verwalten von Microsoft Defender Antivirus mithilfe von WMI](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Überprüfen der Liste der verfügbaren WMI-Klassen und Beispielskripts](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Siehe auch die Referenzinformationen [Windows Defender WMIv2-Anbieters](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Konfigurieren von Microsoft Defender for Endpoint mit Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

Auf einem einzelnen Gerät können Sie eine Überprüfung ausführen, die Diagnoseablaufverfolgung starten, mithilfe des Befehlszeilentools nach Sicherheitsintelligenzupdates suchen und mpcmdrun.exe verwenden. Das Hilfsprogramm finden Sie unter `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Führen Sie es an einer Eingabeaufforderung aus.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Microsoft Defender Antivirus**  |[Konfigurieren und Verwalten von Microsoft Defender Antivirus mit mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihres Microsoft Defender Security Center

Wenn Sie dies noch nicht getan haben, konfigurieren Sie **Ihr Microsoft Defender Security Center** ( ) so, dass Warnungen angezeigt, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zur allgemeinen Sicherheitslage Ihrer Organisation angezeigt [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. 

Sie können auch konfigurieren, ob und welche Features Endbenutzer im Microsoft Defender Security Center sehen können.

- [Übersicht über das Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Nächste Schritte

- [Verschaffen Sie sich einen Überblick über die Verwaltung von Bedrohungen und Sicherheitslücken](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Microsoft Defender Security Center Security Center Security Operations Dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender for Endpoint mit Intune](manage-atp-post-migration-intune.md)
