---
title: Verwalten von Microsoft Defender für Endpunkt mit PowerShell, WMI und MPCmdRun.exe
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt mit PowerShell, WMI und MPCmdRun.exe
keywords: nach der Migration, verwalten, Vorgänge, Wartung, Nutzung, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender für Endpunkt, edr
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
ms.openlocfilehash: d2238703e3b1205287d4ab6239af20095b51df13
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841912"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Verwalten von Microsoft Defender für Endpunkt mit PowerShell, WMI und MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Es wird empfohlen, [Microsoft Endpoint Manager](/mem) zu verwenden, um die Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) zu verwalten. Endpoint Manager enthält [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Microsoft Endpoint Configuration Manager.](/mem/configmgr/core/understand/introduction) 
> - [Weitere Informationen zu Endpoint Manager](/mem/endpoint-manager-overview)
> - [Gemeinsames Verwalten von Microsoft Defender für Endpunkt auf Windows 10 Geräten mit Configuration Manager und Intune](manage-atp-post-migration-intune.md)
> - [Verwalten von Microsoft Defender für Endpunkt mit Intune](manage-atp-post-migration-intune.md) 

Sie können einige Microsoft Defender Antivirus-Einstellungen auf Geräten mit [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [Windows-Verwaltungsinstrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) und dem [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe) verwalten. Beispielsweise können Sie einige Microsoft Defender Antivirus Einstellungen verwalten. Und in einigen Fällen können Sie die Regeln zur Verringerung der Angriffsfläche und exploit-Schutzeinstellungen anpassen. 

> [!IMPORTANT]
> Bedrohungsschutzfeatures, die Sie mithilfe von PowerShell, WMI oder MCPmdRun.exe konfigurieren, können durch Konfigurationseinstellungen überschrieben werden, die mit Intune oder Configuration Manager bereitgestellt werden.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Konfigurieren von Microsoft Defender für Endpunkt mit PowerShell

Sie können PowerShell verwenden, um Microsoft Defender Antivirus, Exploit-Schutz und Die Verringerung der Angriffsfläche zu verwalten.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Microsoft Defender Antivirus** <br/><br/>*Zeigen Sie den Status des Antischadsoftwareschutzes an, konfigurieren Sie Einstellungen für Antivirenscans & Updates, und nehmen Sie weitere Änderungen an Ihrem Antivirenschutz vor.*    |[Verwenden von PowerShell-Cmdlets zum Konfigurieren und Verwalten von Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Verwenden von PowerShell-Cmdlets zum Aktivieren des über die Cloud bereitgestellten Schutzes](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Konfigurieren des Exploit-Schutzes** zum Mindern von Bedrohungen auf den Geräten Ihrer Organisation<br/><br/> *Es wird empfohlen, exploit-Schutz zunächst im [Überwachungsmodus](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) zu verwenden. Auf diese Weise können Sie sehen, wie sich Exploit-Schutz auf Apps auswirkt, die Ihre Organisation verwendet.*     | [Anpassen des Exploit-Schutzes](/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell-Cmdlets für Exploit-Schutz](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Konfigurieren von Regeln zur Verringerung der Angriffsfläche** mit PowerShell <br/><br/>*Sie können PowerShell verwenden, um Dateien und Ordner von Regeln zur Verringerung der Angriffsfläche auszuschließen.* |[Anpassen von Regeln zur Verringerung der Angriffsfläche: Verwenden von PowerShell zum Ausschließen von Dateien & Ordnern](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Lesen Sie auch [das grafische Benutzeroberflächentool von António Vasconcelo zum Festlegen von Regeln zur Verringerung der Angriffsfläche mit PowerShell.](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI) |
|**Aktivieren des Netzwerkschutzes** mit PowerShell <br/><br/>*Sie können PowerShell verwenden, um Den Netzwerkschutz zu aktivieren.* |[Aktivieren des Netzwerkschutzes mit PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomware-Schutz bezeichnet.* |[Aktivieren des kontrollierten Ordnerzugriffs mit PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Konfigurieren sie Microsoft Defender Firewall,** um nicht autorisierten Netzwerkdatenverkehr zu blockieren, der in die Geräte Ihrer Organisation oder aus ihr heraus fließt. |[Microsoft Defender Firewall mit advanced Security Administration unter Verwendung von Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Konfigurieren von Verschlüsselung und BitLocker** zum Schutz von Informationen auf den Geräten Ihrer Organisation, auf denen Windows |[BitLocker PowerShell-Referenzhandbuch](/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Konfigurieren von Microsoft Defender für Endpunkt mit Windows-Verwaltungsinstrumentation (WMI)

WMI ist eine Skriptschnittstelle, mit der Sie Einstellungen abrufen, ändern und aktualisieren können. Weitere Informationen finden Sie unter [Verwenden von WMI](/windows/win32/wmisdk/using-wmi). 

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|Aktivieren des über die **Cloud bereitgestellten Schutzes** auf einem Gerät    |[Verwenden Windows Management Instruction (WMI) zum Aktivieren des über die Cloud bereitgestellten Schutzes](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Abrufen, Ändern und Aktualisieren** von Einstellungen für Microsoft Defender Antivirus     | [Verwenden von WMI zum Konfigurieren und Verwalten von Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Überprüfen der Liste der verfügbaren WMI-Klassen und Beispielskripts](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Siehe auch die archivierten [Windows Defender WMIv2-Anbieterreferenzinformationen.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Konfigurieren von Microsoft Defender für Endpunkt mit microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

Auf einem einzelnen Gerät können Sie eine Überprüfung ausführen, die Diagnoseablaufverfolgung starten, nach Sicherheitsupdates suchen und vieles mehr mithilfe des Befehlszeilentools mpcmdrun.exe. Sie finden das Hilfsprogramm unter `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Führen Sie ihn über eine Eingabeaufforderung aus.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten von Microsoft Defender Antivirus**  |[Konfigurieren und Verwalten von Microsoft Defender Antivirus mit mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihrer Microsoft Defender Security Center

Wenn sie dies noch nicht getan haben, konfigurieren Sie **Ihre Microsoft Defender Security Center** ( ) so, dass [https://securitycenter.windows.com](https://securitycenter.windows.com) Warnungen angezeigt werden, Bedrohungsschutzfeatures konfiguriert werden und detaillierte Informationen zum allgemeinen Sicherheitsstatus Ihrer Organisation angezeigt werden. 

Sie können auch konfigurieren, ob und welche Features Endbenutzer im Microsoft Defender Security Center sehen können.

- [Übersicht über die Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Nächste Schritte

- [Übersicht über Bedrohungs- und Sicherheitsrisikomanagement](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Dashboard für Microsoft Defender Security Center Sicherheitsvorgänge.](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Verwalten von Microsoft Defender für Endpunkt mit Intune](manage-atp-post-migration-intune.md)
