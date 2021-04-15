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
ms.openlocfilehash: 95c87330eec3cb557e5fea96148d626b7e0ee4b3
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768914"
---
# <a name="protect-your-network"></a><span data-ttu-id="e3321-104">Schützen Sie Ihr Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e3321-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3321-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e3321-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3321-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e3321-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3321-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3321-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e3321-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e3321-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3321-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e3321-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e3321-110">Der Netzwerkschutz reduziert die Angriffsfläche Ihrer Geräte durch internetbasierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="e3321-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="e3321-111">Es verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können.</span><span class="sxs-lookup"><span data-stu-id="e3321-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="e3321-112">Der Netzwerkschutz erweitert den Umfang von [Microsoft Defender SmartScreen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) um den gesamten ausgehenden HTTP-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Reputation herzustellen (basierend auf der Domäne oder dem Hostnamen).</span><span class="sxs-lookup"><span data-stu-id="e3321-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="e3321-113">Der Netzwerkschutz wird unter Windows unterstützt, beginnend mit Windows 10, Version 1709.</span><span class="sxs-lookup"><span data-stu-id="e3321-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="e3321-114">Der Netzwerkschutz wird auf anderen Betriebssystemen noch nicht unterstützt, der Webschutz wird jedoch mit dem neuen Microsoft Edge unterstützt, das auf Chromium basiert.</span><span class="sxs-lookup"><span data-stu-id="e3321-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="e3321-115">Weitere Informationen finden Sie unter [Web protection](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3321-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="e3321-116">Der Netzwerkschutz erweitert den Schutz im [Webschutz](web-protection-overview.md) auf die Betriebssystemebene.</span><span class="sxs-lookup"><span data-stu-id="e3321-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="e3321-117">Es bietet Webschutzfunktionen in Edge für andere unterstützte Browser und Nicht-Browser-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e3321-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="e3321-118">Darüber hinaus bietet der Netzwerkschutz Sichtbarkeit und Blockierung von Indikatoren für Kompromisse (IoCs) bei Verwendung mit [Endpunkterkennung und -antwort](overview-endpoint-detection-response.md).</span><span class="sxs-lookup"><span data-stu-id="e3321-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="e3321-119">Der Netzwerkschutz funktioniert z. B. mit Ihren [benutzerdefinierten Indikatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="e3321-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="e3321-120">Weitere Informationen zum Aktivieren des Netzwerkschutzes finden Sie unter [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e3321-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="e3321-121">Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e3321-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="e3321-122">Sehen Sie sich die Microsoft Defender ATP-Testground-Website [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu sehen, wie netzwerkschutz funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e3321-122">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="e3321-123">Der Netzwerkschutz funktioniert am besten [mit Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), mit dem Sie detaillierte Berichte zu Exploitschutzereignissen und -blöcken im Rahmen von Warnungsuntersuchungsszenarien erstellen [können.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e3321-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="e3321-124">Wenn netzwerkschutz eine Verbindung blockiert, wird eine Benachrichtigung aus dem Aktionscenter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3321-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="e3321-125">Ihr Sicherheitsteam kann [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) den Details und Kontaktinformationen Ihrer Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="e3321-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="e3321-126">Darüber hinaus können individuelle Regeln zur Reduzierung der Angriffsfläche aktiviert und an bestimmte Überwachungstechniken angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="e3321-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="e3321-127">Sie können auch den [Überwachungsmodus verwenden,](audit-windows-defender.md) um zu bewerten, wie sich der Netzwerkschutz auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="e3321-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3321-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3321-128">Requirements</span></span>

<span data-ttu-id="e3321-129">Netzwerkschutz erfordert Windows 10 Pro oder Enterprise und Microsoft Defender Antivirus Echtzeitschutz.</span><span class="sxs-lookup"><span data-stu-id="e3321-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="e3321-130">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="e3321-130">Windows version</span></span> | <span data-ttu-id="e3321-131">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e3321-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="e3321-132">Windows 10, Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="e3321-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="e3321-133">Windows Server 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="e3321-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="e3321-134">[Microsoft Defender Antivirus-Echtzeitschutz und](configure-real-time-protection-microsoft-defender-antivirus.md) [Cloud-zugestellter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) müssen aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="e3321-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="e3321-135">Nachdem Sie die Dienste aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall so konfigurieren, dass die Verbindungen zwischen den Diensten und Ihren Geräten (auch als Endpunkte bezeichnet) zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="e3321-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="e3321-136">Überprüfen von Netzwerkschutzereignissen im Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="e3321-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="e3321-137">Microsoft Defender for Endpoint bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e3321-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="e3321-138">Sie können Microsoft Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e3321-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="e3321-139">Wenn Sie den Überwachungsmodus [verwenden,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu sehen, wie sich Netzwerkschutzeinstellungen auf Ihre Umgebung auswirken würden, wenn sie aktiviert wären.</span><span class="sxs-lookup"><span data-stu-id="e3321-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="e3321-140">Hier ist eine Beispielabfrage</span><span class="sxs-lookup"><span data-stu-id="e3321-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="e3321-141">Überprüfen von Netzwerkschutzereignissen in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="e3321-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="e3321-142">Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die erstellt werden, wenn der Netzwerkschutz den Zugriff auf eine schädliche IP oder Domäne blockiert (oder überwacht):</span><span class="sxs-lookup"><span data-stu-id="e3321-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="e3321-143">[Kopieren Sie die XML direkt](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="e3321-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="e3321-144">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e3321-144">Select **OK**.</span></span>

<span data-ttu-id="e3321-145">Mit diesem Verfahren wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die folgenden Ereignisse im Zusammenhang mit dem Netzwerkschutz zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="e3321-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="e3321-146">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e3321-146">Event ID</span></span> | <span data-ttu-id="e3321-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3321-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="e3321-148">5007</span><span class="sxs-lookup"><span data-stu-id="e3321-148">5007</span></span> | <span data-ttu-id="e3321-149">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="e3321-149">Event when settings are changed</span></span> |
| <span data-ttu-id="e3321-150">1125</span><span class="sxs-lookup"><span data-stu-id="e3321-150">1125</span></span> | <span data-ttu-id="e3321-151">Ereignis, wenn der Netzwerkschutz im Überwachungsmodus abgeschaltet wird</span><span class="sxs-lookup"><span data-stu-id="e3321-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="e3321-152">1126</span><span class="sxs-lookup"><span data-stu-id="e3321-152">1126</span></span> | <span data-ttu-id="e3321-153">Ereignis, wenn der Netzwerkschutz im Blockmodus abgeschaltet wird</span><span class="sxs-lookup"><span data-stu-id="e3321-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="e3321-154">Überlegungen zum virtuellen Windows-Desktop mit Windows 10 Enterprise Multi-Session</span><span class="sxs-lookup"><span data-stu-id="e3321-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="e3321-155">Beachten Sie aufgrund des Mehrbenutzercharakters von Windows 10 Enterprise die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="e3321-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="e3321-156">Netzwerkschutz ist ein geräteweites Feature und kann nicht auf bestimmte Benutzersitzungen ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e3321-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="e3321-157">Web content filtering policies are also device wide.</span><span class="sxs-lookup"><span data-stu-id="e3321-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="e3321-158">Wenn Sie zwischen Benutzergruppen unterscheiden müssen, sollten Sie separate Windows Virtual Desktop-Hostpools und -Zuweisungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3321-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="e3321-159">Testen Sie den Netzwerkschutz im Überwachungsmodus, um sein Verhalten vor dem Roll out zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="e3321-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="e3321-160">Erwägen Sie, die Größe Ihrer Bereitstellung zu ändern, wenn Sie über eine große Anzahl von Benutzern oder eine große Anzahl von Sitzungen mit mehreren Benutzern verfügen.</span><span class="sxs-lookup"><span data-stu-id="e3321-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="e3321-161">Alternative Option für netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="e3321-161">Alternative option for network protection</span></span>

<span data-ttu-id="e3321-162">Für Windows 10 Enterprise Multi-Session 1909 und mehr, die in Windows Virtual Desktop in Azure verwendet werden, kann der Netzwerkschutz für Microsoft Edge mithilfe der folgenden Methode aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="e3321-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="e3321-163">Verwenden [Sie Netzwerkschutz aktivieren,](enable-network-protection.md) und befolgen Sie die Anweisungen, um Ihre Richtlinie anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e3321-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="e3321-164">Führen Sie den folgenden PowerShell-Befehl aus: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="e3321-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="e3321-165">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="e3321-165">Network protection troubleshooting</span></span>

<span data-ttu-id="e3321-166">Aufgrund der Umgebung, in der Network Protection ausgeführt wird, kann Microsoft möglicherweise keine Betriebssystemproxyeinstellungen erkennen.</span><span class="sxs-lookup"><span data-stu-id="e3321-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="e3321-167">In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen.</span><span class="sxs-lookup"><span data-stu-id="e3321-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="e3321-168">Um das Konnektivitätsproblem zu beheben, sollten Kunden mit E5-Lizenzen einen der folgenden Defender-Registrierungsschlüssel konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e3321-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="e3321-169">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e3321-169">Related articles</span></span>

- <span data-ttu-id="e3321-170">[Bewerten von Netzwerkschutz|](evaluate-network-protection.md) Gehen Sie ein schnelles Szenario durch, das veranschaulicht, wie das Feature funktioniert und welche Ereignisse in der Regel erstellt würden.</span><span class="sxs-lookup"><span data-stu-id="e3321-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="e3321-171">[Aktivieren von Netzwerkschutz](enable-network-protection.md) | Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e3321-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
