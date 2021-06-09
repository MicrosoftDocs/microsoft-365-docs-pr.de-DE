---
title: Verwenden von Netzwerkschutz, um Verbindungen mit fehlerhaften Standorten zu verhindern
description: Schützen Sie Ihr Netzwerk, indem Sie verhindern, dass Benutzer auf bekannte böswillige und verdächtige Netzwerkadressen zugreifen
keywords: Netzwerkschutz, Exploits, schädliche Websites, IP, Domäne, Domänen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844262"
---
# <a name="protect-your-network"></a>Schützen Sie Ihr Netzwerk

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Der Netzwerkschutz trägt dazu bei, die Angriffsfläche Ihrer Geräte durch internetbasierte Ereignisse zu reduzieren. Es verhindert, dass Mitarbeiter eine beliebige Anwendung verwenden, um auf gefährliche Domänen zuzugreifen, die Phishing-Angriffe, Exploits und andere schädliche Inhalte im Internet hosten könnten. Der Netzwerkschutz erweitert den Bereich der [Microsoft Defender SmartScreen,](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) um den gesamten ausgehenden HTTP-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Zuverlässigkeit (basierend auf der Domäne oder dem Hostnamen) herzustellen.

Der Netzwerkschutz wird auf Windows unterstützt, beginnend mit Windows 10, Version 1709. Der Netzwerkschutz wird unter anderen Betriebssystemen noch nicht unterstützt, der Webschutz wird jedoch mithilfe der neuen Microsoft Edge basierend auf Chromium unterstützt. Weitere Informationen finden Sie unter [Webschutz.](web-protection-overview.md)

Der Netzwerkschutz erweitert den Schutz im [Webschutz](web-protection-overview.md) auf Betriebssystemebene. Es bietet Webschutzfunktionen in Edge für andere unterstützte Browser und Nicht-Browser-Anwendungen. Darüber hinaus bietet der Netzwerkschutz Sichtbarkeit und Blockierung von Gefährdungsindikatoren (Indicators of Compromise, IOCs), wenn sie mit [Endpunkterkennung und -reaktion](overview-endpoint-detection-response.md)verwendet werden. Der Netzwerkschutz funktioniert beispielsweise mit Ihren [benutzerdefinierten Indikatoren.](manage-indicators.md)

Weitere Informationen zum Aktivieren des Netzwerkschutzes finden Sie unter Aktivieren des [Netzwerkschutzes.](enable-network-protection.md) Verwenden Sie Gruppenrichtlinien, PowerShell oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.

> [!TIP]
> Informationen zur Funktionsweise des Netzwerkschutzes finden Sie auf der Microsoft Defender für Endpunkt-Testwebsite unter [demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

Der Netzwerkschutz funktioniert am besten mit [Microsoft Defender für Endpunkt.](microsoft-defender-endpoint.md)Dadurch erhalten Sie detaillierte Berichte zu Exploit-Schutz-Ereignissen und -Blockierungen im Rahmen von [Warnungsuntersuchungsszenarien.](investigate-alerts.md)

Wenn der Netzwerkschutz eine Verbindung blockiert, wird im Info-Center eine Benachrichtigung angezeigt. Ihr Sicherheitsteam kann [die Benachrichtigung](customize-attack-surface-reduction.md#customize-the-notification) mit den Details und Kontaktinformationen Ihrer Organisation anpassen. Darüber hinaus können einzelne Regeln zur Verringerung der Angriffsfläche aktiviert und an bestimmte Überwachungstechniken angepasst werden.

Sie können auch den [Überwachungsmodus](audit-windows-defender.md) verwenden, um zu bewerten, wie sich der Netzwerkschutz auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.

## <a name="requirements"></a>Anforderungen

Der Netzwerkschutz erfordert Windows 10 Pro oder Enterprise und Microsoft Defender Antivirus Echtzeitschutz.

| Windows-Version | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 Version 1709 oder höher <p>Windows Server 1803 oder höher | [Microsoft Defender Antivirus Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md) und über die [Cloud bereitgestellter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) muss aktiviert sein. |

Nachdem Sie die Dienste aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall konfigurieren, um die Verbindungen zwischen den Diensten und Ihren Geräten zuzulassen (auch als Endpunkte bezeichnet).  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Überprüfen von Netzwerkschutzereignissen im Microsoft Defender für Endpunkt Security Center

Microsoft Defender für Endpunkt bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)

Sie können Microsoft Defender für Endpunktdaten mithilfe der [erweiterten Suche](advanced-hunting-overview.md)abfragen. Wenn Sie den [Überwachungsmodus](audit-windows-defender.md)verwenden, können Sie die erweiterte Suche verwenden, um zu sehen, wie sich Netzwerkschutzeinstellungen auf Ihre Umgebung auswirken, wenn sie aktiviert sind.

Hier ist eine Beispielabfrage

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Überprüfen von Netzwerkschutzereignissen in Windows Ereignisanzeige

Sie können das Windows Ereignisprotokoll überprüfen, um Ereignisse anzuzeigen, die erstellt werden, wenn der Netzwerkschutz den Zugriff auf eine schädliche IP oder Domäne blockiert (oder überwacht):

1. [Kopieren Sie den XML-Code direkt.](event-views.md)

2. Wählen Sie **OK** aus.

Dieses Verfahren erstellt eine benutzerdefinierte Ansicht, die filtert, um nur die folgenden Ereignisse im Zusammenhang mit dem Netzwerkschutz anzuzeigen:

| Ereignis-ID | Beschreibung |
|:---|:---|
| 5007 | Ereignis, wenn Einstellungen geändert werden |
| 1125 | Ereignis, wenn der Netzwerkschutz im Überwachungsmodus ausgelöst wird |
| 1126 | Ereignis, wenn der Netzwerkschutz im Blockierungsmodus ausgelöst wird |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Überlegungen zum Windows virtuellen Desktops, auf dem Windows 10 Enterprise mehrere Sitzungen ausgeführt werden

Beachten Sie aufgrund der Multibenutzerart von Windows 10 Enterprise die folgenden Punkte:

1. Der Netzwerkschutz ist ein geräteweites Feature und kann nicht auf bestimmte Benutzersitzungen ausgerichtet werden.

2. Richtlinien für die Webinhaltsfilterung sind auch geräteweit.

3. Wenn Sie zwischen Benutzergruppen unterscheiden müssen, sollten Sie separate Windows Virtual Desktop-Hostpools und -Zuweisungen erstellen.

4. Testen Sie den Netzwerkschutz im Überwachungsmodus, um sein Verhalten vor dem Rollout zu bewerten. 

5. Ziehen Sie in Betracht, die Größe Ihrer Bereitstellung zu ändern, wenn Sie über eine große Anzahl von Benutzern oder eine große Anzahl von Sitzungen mit mehreren Benutzern verfügen.

### <a name="alternative-option-for-network-protection"></a>Alternative Option für Netzwerkschutz

Für Windows 10 Enterprise Multi-Session 1909 und höher, die in Windows Virtual Desktop on Azure verwendet wird, kann der Netzwerkschutz für Microsoft Edge mithilfe der folgenden Methode aktiviert werden:

1. Verwenden Sie ["Netzwerkschutz aktivieren",](enable-network-protection.md) und befolgen Sie die Anweisungen, um Ihre Richtlinie anzuwenden.

2. Führen Sie den folgenden PowerShell-Befehl aus: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Problembehandlung beim Netzwerkschutz

Aufgrund der Umgebung, in der Netzwerkschutz ausgeführt wird, kann Microsoft möglicherweise keine Proxyeinstellungen des Betriebssystems erkennen. In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen. Um das Konnektivitätsproblem zu beheben, sollten Kunden mit E5-Lizenzen einen der folgenden Defender-Registrierungsschlüssel konfigurieren:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Verwandte Artikel

- [Auswerten des Netzwerkschutzes](evaluate-network-protection.md) | Führen Sie ein schnelles Szenario durch, das zeigt, wie das Feature funktioniert und welche Ereignisse in der Regel erstellt werden.

- [Netzwerkschutz | aktivieren](enable-network-protection.md) Verwenden Sie Gruppenrichtlinien, PowerShell oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.
