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
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="205e5-104">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="205e5-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="205e5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="205e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="205e5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="205e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="205e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="205e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="205e5-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="205e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="205e5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="205e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="205e5-110">Bei Verwendung des [Netzwerkschutzes](network-protection.md) können Probleme auftreten, z. B.:</span><span class="sxs-lookup"><span data-stu-id="205e5-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="205e5-111">Netzwerkschutz blockiert eine sichere Website (falsch positiv)</span><span class="sxs-lookup"><span data-stu-id="205e5-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="205e5-112">Der Netzwerkschutz kann eine verdächtige oder bekannte schädliche Website nicht blockieren (falsch negativ)</span><span class="sxs-lookup"><span data-stu-id="205e5-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="205e5-113">Es gibt vier Schritte zur Problembehandlung:</span><span class="sxs-lookup"><span data-stu-id="205e5-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="205e5-114">Bestätigen der Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="205e5-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="205e5-115">Verwenden des Überwachungsmodus zum Testen der Regel</span><span class="sxs-lookup"><span data-stu-id="205e5-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="205e5-116">Hinzufügen von Ausschlüssen für die angegebene Regel (bei falsch positiven Ergebnissen)</span><span class="sxs-lookup"><span data-stu-id="205e5-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="205e5-117">Übermitteln von Supportprotokollen</span><span class="sxs-lookup"><span data-stu-id="205e5-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="205e5-118">Bestätigen der Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="205e5-118">Confirm prerequisites</span></span>

<span data-ttu-id="205e5-119">Der Netzwerkschutz funktioniert nur auf Geräten mit den folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="205e5-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="205e5-120">Endpunkte werden Windows 10 Pro oder Enterprise Edition, Version 1709 oder höher, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="205e5-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="205e5-121">Endpunkte verwenden Microsoft Defender Antivirus als einzige Antivirenschutz-App.</span><span class="sxs-lookup"><span data-stu-id="205e5-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="205e5-122">[Sehen Sie, was geschieht, wenn Sie eine Antivirenlösung verwenden,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)die nicht von Microsoft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="205e5-122">[See what happens when you are using a non-Microsoft antivirus solution](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="205e5-123">[Der Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="205e5-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="205e5-124">[Der über die Cloud bereitgestellte Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="205e5-124">[Cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="205e5-125">Der Überwachungsmodus ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="205e5-125">Audit mode is not enabled.</span></span> <span data-ttu-id="205e5-126">Verwenden Sie [die Gruppenrichtlinie,](enable-network-protection.md#group-policy) um die Regel auf **"Deaktiviert"** (Wert: **0)** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="205e5-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="205e5-127">Verwenden des Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="205e5-127">Use audit mode</span></span>

<span data-ttu-id="205e5-128">Sie können den Netzwerkschutz im Überwachungsmodus aktivieren und dann eine Website besuchen, die wir erstellt haben, um das Feature zu demonstören.</span><span class="sxs-lookup"><span data-stu-id="205e5-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="205e5-129">Alle Websiteverbindungen werden vom Netzwerkschutz zugelassen, aber ein Ereignis wird protokolliert, um eine Verbindung anzugeben, die blockiert worden wäre, wenn der Netzwerkschutz aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="205e5-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="205e5-130">Legen Sie den Netzwerkschutz auf den **Überwachungsmodus** fest.</span><span class="sxs-lookup"><span data-stu-id="205e5-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="205e5-131">Führen Sie die Verbindungsaktivität aus, die ein Problem verursacht (z. B. versuchen Sie, die Website zu besuchen oder eine Verbindung mit der IP-Adresse herzustellen, die Sie blockieren möchten).</span><span class="sxs-lookup"><span data-stu-id="205e5-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="205e5-132">[Überprüfen Sie die Netzwerkschutz-Ereignisprotokolle,](network-protection.md#review-network-protection-events-in-windows-event-viewer) um festzustellen, ob das Feature die Verbindung blockiert hätte, wenn es auf **"Aktiviert"** festgelegt worden wäre.</span><span class="sxs-lookup"><span data-stu-id="205e5-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="205e5-133">Wenn der Netzwerkschutz keine Verbindung blockiert, von der Sie erwarten, dass sie blockiert werden soll, aktivieren Sie das Feature.</span><span class="sxs-lookup"><span data-stu-id="205e5-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="205e5-134">Melden eines falsch positiven oder falsch negativen Ergebnisses</span><span class="sxs-lookup"><span data-stu-id="205e5-134">Report a false positive or false negative</span></span>

<span data-ttu-id="205e5-135">Wenn Sie das Feature mit der Demowebsite und dem Überwachungsmodus getestet haben und der Netzwerkschutz in vorkonfigurierten Szenarien funktioniert, aber für eine bestimmte Verbindung nicht wie erwartet funktioniert, verwenden Sie das [webbasierte Übermittlungsformular Windows Defender Security Intelligence,](https://www.microsoft.com/wdsi/filesubmission) um einen falsch negativen oder falsch positiven Wert für den Netzwerkschutz zu melden.</span><span class="sxs-lookup"><span data-stu-id="205e5-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="205e5-136">Mit einem E5-Abonnement können Sie auch [einen Link zu jeder zugeordneten Warnung bereitstellen.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="205e5-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="205e5-137">Siehe ["Adresse falsch positive/negative Ergebnisse" in Microsoft Defender für Endpunkt.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="205e5-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="205e5-138">Ausschließen einer Website aus dem Netzwerkschutzbereich</span><span class="sxs-lookup"><span data-stu-id="205e5-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="205e5-139">Um zuzulassen, dass die Website blockiert wird (falsch positiv), fügen Sie ihre URL zur [Liste der vertrauenswürdigen Websites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)hinzu.</span><span class="sxs-lookup"><span data-stu-id="205e5-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="205e5-140">Webressourcen aus dieser Liste umgehen die Netzwerkschutzüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="205e5-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="205e5-141">Sammeln von Diagnosedaten für Dateiübermittlungen</span><span class="sxs-lookup"><span data-stu-id="205e5-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="205e5-142">Wenn Sie ein Problem mit dem Netzwerkschutz melden, werden Sie aufgefordert, Diagnosedaten zu sammeln und zu übermitteln, die von Microsoft-Support- und -Entwicklungsteams zur Problembehandlung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="205e5-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="205e5-143">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten, und wechseln Sie zum Verzeichnis Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="205e5-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="205e5-144">Führen Sie diesen Befehl aus, um die Diagnoseprotokolle zu generieren:</span><span class="sxs-lookup"><span data-stu-id="205e5-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="205e5-145">Fügen Sie die Datei an das Übermittlungsformular an.</span><span class="sxs-lookup"><span data-stu-id="205e5-145">Attach the file to the submission form.</span></span> <span data-ttu-id="205e5-146">Diagnoseprotokolle werden standardmäßig unter `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="205e5-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="205e5-147">Beheben von Konnektivitätsproblemen beim Netzwerkschutz (für E5-Kunden)</span><span class="sxs-lookup"><span data-stu-id="205e5-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="205e5-148">Aufgrund der Umgebung, in der der Netzwerkschutz ausgeführt wird, können Ihre Proxyeinstellungen für das Betriebssystem von Microsoft nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="205e5-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="205e5-149">In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen.</span><span class="sxs-lookup"><span data-stu-id="205e5-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="205e5-150">Um Konnektivitätsprobleme mit dem Netzwerkschutz zu beheben, konfigurieren Sie einen der folgenden Registrierungsschlüssel, damit der Netzwerkschutz die Proxykonfiguration erkennt:</span><span class="sxs-lookup"><span data-stu-id="205e5-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="205e5-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="205e5-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="205e5-152">Sie können den Registrierungsschlüssel mithilfe von PowerShell, Microsoft Endpoint Manager oder Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="205e5-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="205e5-153">Hier sind einige Ressourcen, die Ihnen helfen können:</span><span class="sxs-lookup"><span data-stu-id="205e5-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="205e5-154">Arbeiten mit Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="205e5-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="205e5-155">Konfigurieren von benutzerdefinierten Clienteinstellungen für Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="205e5-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="205e5-156">Verwenden von Gruppenrichtlinieneinstellungen zum Verwalten Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="205e5-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="205e5-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="205e5-157">See also</span></span>

- [<span data-ttu-id="205e5-158">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="205e5-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="205e5-159">Auswerten des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="205e5-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="205e5-160">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="205e5-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="205e5-161">Adressierung falsch positiver/negativer Ergebnisse in Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="205e5-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
