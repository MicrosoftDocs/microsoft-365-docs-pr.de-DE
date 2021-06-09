---
title: Behandeln von Problemen mit dem Netzwerkschutz
description: Ressourcen und Beispielcode zur Behandlung von Problemen mit dem Netzwerkschutz in Microsoft Defender für Endpunkt.
keywords: Troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
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
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844056"
---
# <a name="troubleshoot-network-protection"></a>Problembehandlung beim Netzwerkschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Bei Verwendung des [Netzwerkschutzes](network-protection.md) können Probleme auftreten, z. B.:

- Netzwerkschutz blockiert eine sichere Website (falsch positiv)
- Der Netzwerkschutz kann eine verdächtige oder bekannte schädliche Website nicht blockieren (falsch negativ)

Es gibt vier Schritte zur Problembehandlung:

1. Bestätigen der Voraussetzungen
2. Verwenden des Überwachungsmodus zum Testen der Regel
3. Hinzufügen von Ausschlüssen für die angegebene Regel (bei falsch positiven Ergebnissen)
4. Übermitteln von Supportprotokollen

## <a name="confirm-prerequisites"></a>Bestätigen der Voraussetzungen

Der Netzwerkschutz funktioniert nur auf Geräten mit den folgenden Bedingungen:

>[!div class="checklist"]
> - Endpunkte werden Windows 10 Pro oder Enterprise Edition, Version 1709 oder höher, ausgeführt.
> - Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App. [Sehen Sie, was geschieht, wenn Sie eine Antivirenlösung verwenden,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)die nicht von Microsoft verwendet wird.
> - [Der Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.
> - [Der über die Cloud bereitgestellte Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) ist aktiviert.
> - Der Überwachungsmodus ist nicht aktiviert. Verwenden Sie [die Gruppenrichtlinie,](enable-network-protection.md#group-policy) um die Regel auf **"Deaktiviert"** (Wert: **0)** festzulegen.

## <a name="use-audit-mode"></a>Verwenden des Überwachungsmodus

Sie können den Netzwerkschutz im Überwachungsmodus aktivieren und dann eine Website besuchen, die wir erstellt haben, um das Feature zu demonstören. Alle Websiteverbindungen werden vom Netzwerkschutz zugelassen, aber ein Ereignis wird protokolliert, um eine Verbindung anzugeben, die blockiert worden wäre, wenn der Netzwerkschutz aktiviert wäre.

1. Legen Sie den Netzwerkschutz auf den **Überwachungsmodus** fest.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Führen Sie die Verbindungsaktivität aus, die ein Problem verursacht (z. B. versuchen Sie, die Website zu besuchen oder eine Verbindung mit der IP-Adresse herzustellen, die Sie blockieren möchten).

3. [Überprüfen Sie die Netzwerkschutz-Ereignisprotokolle,](network-protection.md#review-network-protection-events-in-windows-event-viewer) um festzustellen, ob das Feature die Verbindung blockiert hätte, wenn es auf **"Aktiviert"** festgelegt worden wäre.
   
   Wenn der Netzwerkschutz keine Verbindung blockiert, von der Sie erwarten, dass sie blockiert werden soll, aktivieren Sie das Feature.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Melden eines falsch positiven oder falsch negativen Ergebnisses

Wenn Sie das Feature mit der Demowebsite und dem Überwachungsmodus getestet haben und der Netzwerkschutz in vorkonfigurierten Szenarien funktioniert, aber für eine bestimmte Verbindung nicht wie erwartet funktioniert, verwenden Sie das [webbasierte Übermittlungsformular Windows Defender Security Intelligence,](https://www.microsoft.com/wdsi/filesubmission) um einen falsch negativen oder falsch positiven Wert für den Netzwerkschutz zu melden. Mit einem E5-Abonnement können Sie auch [einen Link zu jeder zugeordneten Warnung bereitstellen.](alerts-queue.md)

Siehe ["Adresse falsch positive/negative Ergebnisse" in Microsoft Defender für Endpunkt.](defender-endpoint-false-positives-negatives.md)

## <a name="exclude-website-from-network-protection-scope"></a>Ausschließen einer Website aus dem Netzwerkschutzbereich

Um zuzulassen, dass die Website blockiert wird (falsch positiv), fügen Sie ihre URL zur [Liste der vertrauenswürdigen Websites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)hinzu. Webressourcen aus dieser Liste umgehen die Netzwerkschutzüberprüfung.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Sammeln von Diagnosedaten für Dateiübermittlungen

Wenn Sie ein Problem mit dem Netzwerkschutz melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und -Entwicklungsteams zur Problembehandlung verwendet werden können.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und wechseln Sie zum Verzeichnis Windows Defender:

   ```console
   cd c:\program files\windows defender
   ```

2. Führen Sie diesen Befehl aus, um die Diagnoseprotokolle zu generieren:

   ```console
   mpcmdrun -getfiles
   ```

3. Fügen Sie die Datei an das Übermittlungsformular an. Diagnoseprotokolle werden standardmäßig unter `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` gespeichert. 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Beheben von Konnektivitätsproblemen beim Netzwerkschutz (für E5-Kunden)

Aufgrund der Umgebung, in der der Netzwerkschutz ausgeführt wird, können Ihre Proxyeinstellungen für das Betriebssystem von Microsoft nicht angezeigt werden. In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen. Um Konnektivitätsprobleme mit dem Netzwerkschutz zu beheben, konfigurieren Sie einen der folgenden Registrierungsschlüssel, damit der Netzwerkschutz die Proxykonfiguration erkennt:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

Sie können den Registrierungsschlüssel mithilfe von PowerShell, Microsoft Endpoint Manager oder Gruppenrichtlinien konfigurieren. Hier sind einige Ressourcen, die Ihnen helfen können:
- [Arbeiten mit Registrierungsschlüsseln](/powershell/scripting/samples/working-with-registry-keys)
- [Konfigurieren von benutzerdefinierten Clienteinstellungen für Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Verwenden von Gruppenrichtlinieneinstellungen zum Verwalten Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Siehe auch

- [Netzwerkschutz](network-protection.md)
- [Auswerten des Netzwerkschutzes](evaluate-network-protection.md)
- [Netzwerkschutz aktivieren](enable-network-protection.md)
- [Adressierung falsch positiver/negativer Ergebnisse in Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
