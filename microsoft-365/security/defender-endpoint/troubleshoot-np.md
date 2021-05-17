---
title: Problembehandlung bei Netzwerkschutz
description: Ressourcen und Beispielcode zur Problembehandlung bei Netzwerkschutz in Microsoft Defender for Endpoint.
keywords: Problembehandlung, Fehler, Behebung, Windows Defender z. B. Asr, Regeln, Hips, Problembehandlung, Überwachung, Ausschluss, falsch positiv, gebrochen, Blockieren, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f77ce94fda63a9e7e8a9484a67a22eeec136d619
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935881"
---
# <a name="troubleshoot-network-protection"></a>Problembehandlung beim Netzwerkschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wenn Sie [Netzwerkschutz verwenden,](network-protection.md) können Probleme auftreten, z. B.:

- Netzwerkschutz blockiert eine sichere Website (falsch positiv)
- Netzwerkschutz blockiert eine verdächtige oder bekannte schädliche Website nicht (falsch negativ)

Es gibt vier Schritte zur Problembehandlung:

1. Bestätigen von Voraussetzungen
2. Verwenden des Überwachungsmodus zum Testen der Regel
3. Hinzufügen von Ausschlüssen für die angegebene Regel (für falsch positive Ergebnisse)
4. Übermitteln von Supportprotokollen

## <a name="confirm-prerequisites"></a>Bestätigen von Voraussetzungen

Der Netzwerkschutz funktioniert nur auf Geräten mit den folgenden Bedingungen:

>[!div class="checklist"]
> - Endpunkte werden Windows 10 Pro oder Enterprise Version 1709 oder höher ausgeführt.
> - Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Erfahren Sie, was geschieht, wenn Sie eine Nicht-Microsoft-Antivirenlösung verwenden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [Echtzeitschutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.
> - [Der in der Cloud zugestellte Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) ist aktiviert.
> - Der Überwachungsmodus ist nicht aktiviert. Verwenden [Sie Gruppenrichtlinie,](enable-network-protection.md#group-policy) um die Regel auf **Deaktiviert** (Wert: 0 ) **zu setzen.**

## <a name="use-audit-mode"></a>Verwenden des Überwachungsmodus

Sie können den Netzwerkschutz im Überwachungsmodus aktivieren und dann eine Website besuchen, die wir zum Demo des Features erstellt haben. Alle Websiteverbindungen werden vom Netzwerkschutz zugelassen, aber ein Ereignis wird protokolliert, um eine Verbindung anzugeben, die blockiert worden wäre, wenn der Netzwerkschutz aktiviert wäre.

1. Legen Sie den Netzwerkschutz auf **Den Überwachungsmodus .**

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Führen Sie die Verbindungsaktivität aus, die ein Problem verursacht (z. B. versuchen Sie, den Standort zu besuchen oder eine Verbindung mit der IP-Adresse herzustellen, die Sie tun oder nicht blockieren möchten).

3. [Überprüfen Sie die Netzwerkschutzereignisprotokolle,](network-protection.md#review-network-protection-events-in-windows-event-viewer) um zu sehen, ob das Feature die Verbindung blockiert hätte, wenn sie auf **Aktiviert festgelegt worden wäre.**
   
   Wenn der Netzwerkschutz eine Verbindung nicht blockiert, von der Sie erwarten, dass sie blockiert wird, aktivieren Sie das Feature.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Melden eines falsch positiven oder falsch negativen Werts

Wenn Sie das Feature mit der Demowebsite und dem Überwachungsmodus getestet haben und der Netzwerkschutz an vorkonfigurierten Szenarien arbeitet, aber für eine bestimmte Verbindung nicht wie erwartet funktioniert, verwenden Sie das [webbasierte Übermittlungsformular für Windows Defender Security Intelligence,](https://www.microsoft.com/wdsi/filesubmission) um ein falsch negatives oder falsch positives Ergebnis für den Netzwerkschutz zu melden. Mit einem E5-Abonnement können Sie auch einen Link zu allen [zugeordneten Warnungen bereitstellen.](alerts-queue.md)

Weitere [Informationen finden Sie unter Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).

## <a name="exclude-website-from-network-protection-scope"></a>Ausschließen von Websites aus dem Netzwerkschutzbereich

Fügen Sie die URL zur Liste der vertrauenswürdigen Websites hinzu, um die blockierte Website zu erlauben (falsch [positiv).](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/) Webressourcen aus dieser Liste umgehen die Überprüfung des Netzwerkschutzes.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Sammeln von Diagnosedaten für Dateiübermittlungen

Wenn Sie ein Problem mit dem Netzwerkschutz melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und Engineeringteams zur Problembehandlung verwendet werden können.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und ändern Sie Windows Defender Verzeichnis:

   ```console
   cd c:\program files\windows defender
   ```

2. Führen Sie diesen Befehl aus, um die Diagnoseprotokolle zu generieren:

   ```console
   mpcmdrun -getfiles
   ```

3. Fügen Sie die Datei an das Übermittlungsformular an. Diagnoseprotokolle werden standardmäßig unter `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` gespeichert. 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Beheben von Konnektivitätsproblemen beim Netzwerkschutz (für E5-Kunden)

Aufgrund der Umgebung, in der der Netzwerkschutz ausgeführt wird, kann Microsoft die Proxyeinstellungen des Betriebssystems nicht sehen. In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen. Um Konnektivitätsprobleme mit dem Netzwerkschutz zu beheben, konfigurieren Sie einen der folgenden Registrierungsschlüssel, damit der Netzwerkschutz die Proxykonfiguration kennt:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

Sie können den Registrierungsschlüssel mithilfe von PowerShell, Microsoft Endpoint Manager oder Gruppenrichtlinie konfigurieren. Hier sind einige Ressourcen, die Ihnen helfen:
- [Arbeiten mit Registrierungsschlüsseln](/powershell/scripting/samples/working-with-registry-keys)
- [Konfigurieren von benutzerdefinierten Clienteinstellungen für Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Verwenden von Gruppenrichtlinieneinstellungen zum Verwalten von Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Siehe auch

- [Netzwerkschutz](network-protection.md)
- [Auswerten des Netzwerkschutzes](evaluate-network-protection.md)
- [Aktivieren des Netzwerkschutzes](enable-network-protection.md)
- [Adress false positives/negatives in Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
