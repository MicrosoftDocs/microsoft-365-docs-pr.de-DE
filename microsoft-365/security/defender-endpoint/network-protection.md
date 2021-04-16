---
title: Verwenden von Netzwerkschutz zum Verhindern von Verbindungen mit ungültigen Standorten
description: Schützen Sie Ihr Netzwerk, indem Sie verhindern, dass Benutzer auf bekannte bösartige und verdächtige Netzwerkadressen zugreifen
keywords: Netzwerkschutz, Exploits, schädliche Website, IP, Domäne, Domänen
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
ms.openlocfilehash: a22cab9185b2ece2e8e30c00ea747cca823f4920
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861155"
---
# <a name="protect-your-network"></a>Schützen Sie Ihr Netzwerk

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Der Netzwerkschutz reduziert die Angriffsfläche Ihrer Geräte durch internetbasierte Ereignisse. Es verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können. Der Netzwerkschutz erweitert den Umfang von [Microsoft Defender SmartScreen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) um den gesamten ausgehenden HTTP-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Reputation herzustellen (basierend auf der Domäne oder dem Hostnamen).

Der Netzwerkschutz wird unter Windows unterstützt, beginnend mit Windows 10, Version 1709. Der Netzwerkschutz wird auf anderen Betriebssystemen noch nicht unterstützt, der Webschutz wird jedoch mit dem neuen Microsoft Edge unterstützt, das auf Chromium basiert. Weitere Informationen finden Sie unter [Web protection](web-protection-overview.md).

Der Netzwerkschutz erweitert den Schutz im [Webschutz](web-protection-overview.md) auf die Betriebssystemebene. Es bietet Webschutzfunktionen in Edge für andere unterstützte Browser und Nicht-Browser-Anwendungen. Darüber hinaus bietet der Netzwerkschutz Sichtbarkeit und Blockierung von Indikatoren für Kompromisse (IoCs) bei Verwendung mit [Endpunkterkennung und -antwort](overview-endpoint-detection-response.md). Der Netzwerkschutz funktioniert z. B. mit Ihren [benutzerdefinierten Indikatoren.](manage-indicators.md)

Weitere Informationen zum Aktivieren des Netzwerkschutzes finden Sie unter [Enable network protection](enable-network-protection.md). Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.

> [!TIP]
> Informationen zur Funktionsweise des Netzwerkschutzes finden Sie auf der [Demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Microsoft Defender for Endpoint-Testground-Website.

Der Netzwerkschutz funktioniert am besten [mit Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), mit dem Sie detaillierte Berichte zu Exploitschutzereignissen und -blöcken im Rahmen von Warnungsuntersuchungsszenarien erstellen [können.](investigate-alerts.md)

Wenn netzwerkschutz eine Verbindung blockiert, wird eine Benachrichtigung aus dem Aktionscenter angezeigt. Ihr Sicherheitsteam kann [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) den Details und Kontaktinformationen Ihrer Organisation anpassen. Darüber hinaus können individuelle Regeln zur Reduzierung der Angriffsfläche aktiviert und an bestimmte Überwachungstechniken angepasst werden.

Sie können auch den [Überwachungsmodus verwenden,](audit-windows-defender.md) um zu bewerten, wie sich der Netzwerkschutz auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.

## <a name="requirements"></a>Anforderungen

Netzwerkschutz erfordert Windows 10 Pro oder Enterprise und Microsoft Defender Antivirus Echtzeitschutz.

| Windows-Version | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10, Version 1709 oder höher <p>Windows Server 1803 oder höher | [Microsoft Defender Antivirus-Echtzeitschutz und](configure-real-time-protection-microsoft-defender-antivirus.md) [Cloud-zugestellter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) müssen aktiviert sein |

Nachdem Sie die Dienste aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall so konfigurieren, dass die Verbindungen zwischen den Diensten und Ihren Geräten (auch als Endpunkte bezeichnet) zulässig sind.  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Überprüfen von Netzwerkschutzereignissen im Microsoft Defender for Endpoint Security Center

Microsoft Defender for Endpoint bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)

Sie können Microsoft Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](advanced-hunting-overview.md) Wenn Sie den Überwachungsmodus [verwenden,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu sehen, wie sich Netzwerkschutzeinstellungen auf Ihre Umgebung auswirken würden, wenn sie aktiviert wären.

Hier ist eine Beispielabfrage

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Überprüfen von Netzwerkschutzereignissen in der Windows-Ereignisanzeige

Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die erstellt werden, wenn der Netzwerkschutz den Zugriff auf eine schädliche IP oder Domäne blockiert (oder überwacht):

1. [Kopieren Sie die XML direkt](event-views.md).

2. Wählen Sie **OK** aus.

Mit diesem Verfahren wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die folgenden Ereignisse im Zusammenhang mit dem Netzwerkschutz zu zeigen:

| Ereignis-ID | Beschreibung |
|:---|:---|
| 5007 | Ereignis, wenn Einstellungen geändert werden |
| 1125 | Ereignis, wenn der Netzwerkschutz im Überwachungsmodus abgeschaltet wird |
| 1126 | Ereignis, wenn der Netzwerkschutz im Blockmodus abgeschaltet wird |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Überlegungen zum virtuellen Windows-Desktop mit Windows 10 Enterprise Multi-Session

Beachten Sie aufgrund des Mehrbenutzercharakters von Windows 10 Enterprise die folgenden Punkte:

1. Netzwerkschutz ist ein geräteweites Feature und kann nicht auf bestimmte Benutzersitzungen ausgerichtet werden.

2. Web content filtering policies are also device wide.

3. Wenn Sie zwischen Benutzergruppen unterscheiden müssen, sollten Sie separate Windows Virtual Desktop-Hostpools und -Zuweisungen erstellen.

4. Testen Sie den Netzwerkschutz im Überwachungsmodus, um sein Verhalten vor dem Roll out zu bewerten. 

5. Erwägen Sie, die Größe Ihrer Bereitstellung zu ändern, wenn Sie über eine große Anzahl von Benutzern oder eine große Anzahl von Sitzungen mit mehreren Benutzern verfügen.

### <a name="alternative-option-for-network-protection"></a>Alternative Option für netzwerkschutz

Für Windows 10 Enterprise Multi-Session 1909 und mehr, die in Windows Virtual Desktop in Azure verwendet werden, kann der Netzwerkschutz für Microsoft Edge mithilfe der folgenden Methode aktiviert werden:

1. Verwenden [Sie Netzwerkschutz aktivieren,](enable-network-protection.md) und befolgen Sie die Anweisungen, um Ihre Richtlinie anzuwenden.

2. Führen Sie den folgenden PowerShell-Befehl aus: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Problembehandlung beim Netzwerkschutz

Aufgrund der Umgebung, in der Network Protection ausgeführt wird, kann Microsoft möglicherweise keine Betriebssystemproxyeinstellungen erkennen. In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen. Um das Konnektivitätsproblem zu beheben, sollten Kunden mit E5-Lizenzen einen der folgenden Defender-Registrierungsschlüssel konfigurieren:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Verwandte Artikel

- [Bewerten von Netzwerkschutz|](evaluate-network-protection.md) Gehen Sie ein schnelles Szenario durch, das veranschaulicht, wie das Feature funktioniert und welche Ereignisse in der Regel erstellt würden.

- [Aktivieren von Netzwerkschutz](enable-network-protection.md) | Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.
