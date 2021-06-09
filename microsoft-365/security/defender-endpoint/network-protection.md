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
# <a name="protect-your-network"></a><span data-ttu-id="3ebec-104">Schützen Sie Ihr Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3ebec-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ebec-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3ebec-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ebec-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3ebec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ebec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ebec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ebec-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="3ebec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ebec-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3ebec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3ebec-110">Der Netzwerkschutz trägt dazu bei, die Angriffsfläche Ihrer Geräte durch internetbasierte Ereignisse zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="3ebec-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="3ebec-111">Es verhindert, dass Mitarbeiter eine beliebige Anwendung verwenden, um auf gefährliche Domänen zuzugreifen, die Phishing-Angriffe, Exploits und andere schädliche Inhalte im Internet hosten könnten.</span><span class="sxs-lookup"><span data-stu-id="3ebec-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="3ebec-112">Der Netzwerkschutz erweitert den Bereich der [Microsoft Defender SmartScreen,](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) um den gesamten ausgehenden HTTP-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Zuverlässigkeit (basierend auf der Domäne oder dem Hostnamen) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="3ebec-113">Der Netzwerkschutz wird auf Windows unterstützt, beginnend mit Windows 10, Version 1709.</span><span class="sxs-lookup"><span data-stu-id="3ebec-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="3ebec-114">Der Netzwerkschutz wird unter anderen Betriebssystemen noch nicht unterstützt, der Webschutz wird jedoch mithilfe der neuen Microsoft Edge basierend auf Chromium unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ebec-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="3ebec-115">Weitere Informationen finden Sie unter [Webschutz.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="3ebec-116">Der Netzwerkschutz erweitert den Schutz im [Webschutz](web-protection-overview.md) auf Betriebssystemebene.</span><span class="sxs-lookup"><span data-stu-id="3ebec-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="3ebec-117">Es bietet Webschutzfunktionen in Edge für andere unterstützte Browser und Nicht-Browser-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="3ebec-118">Darüber hinaus bietet der Netzwerkschutz Sichtbarkeit und Blockierung von Gefährdungsindikatoren (Indicators of Compromise, IOCs), wenn sie mit [Endpunkterkennung und -reaktion](overview-endpoint-detection-response.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ebec-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="3ebec-119">Der Netzwerkschutz funktioniert beispielsweise mit Ihren [benutzerdefinierten Indikatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="3ebec-120">Weitere Informationen zum Aktivieren des Netzwerkschutzes finden Sie unter Aktivieren des [Netzwerkschutzes.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="3ebec-121">Verwenden Sie Gruppenrichtlinien, PowerShell oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="3ebec-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="3ebec-122">Informationen zur Funktionsweise des Netzwerkschutzes finden Sie auf der Microsoft Defender für Endpunkt-Testwebsite unter [demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="3ebec-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="3ebec-123">Der Netzwerkschutz funktioniert am besten mit [Microsoft Defender für Endpunkt.](microsoft-defender-endpoint.md)Dadurch erhalten Sie detaillierte Berichte zu Exploit-Schutz-Ereignissen und -Blockierungen im Rahmen von [Warnungsuntersuchungsszenarien.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="3ebec-124">Wenn der Netzwerkschutz eine Verbindung blockiert, wird im Info-Center eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ebec-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="3ebec-125">Ihr Sicherheitsteam kann [die Benachrichtigung](customize-attack-surface-reduction.md#customize-the-notification) mit den Details und Kontaktinformationen Ihrer Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="3ebec-126">Darüber hinaus können einzelne Regeln zur Verringerung der Angriffsfläche aktiviert und an bestimmte Überwachungstechniken angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3ebec-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="3ebec-127">Sie können auch den [Überwachungsmodus](audit-windows-defender.md) verwenden, um zu bewerten, wie sich der Netzwerkschutz auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="3ebec-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ebec-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ebec-128">Requirements</span></span>

<span data-ttu-id="3ebec-129">Der Netzwerkschutz erfordert Windows 10 Pro oder Enterprise und Microsoft Defender Antivirus Echtzeitschutz.</span><span class="sxs-lookup"><span data-stu-id="3ebec-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="3ebec-130">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="3ebec-130">Windows version</span></span> | <span data-ttu-id="3ebec-131">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3ebec-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="3ebec-132">Windows 10 Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="3ebec-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="3ebec-133">Windows Server 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="3ebec-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="3ebec-134">[Microsoft Defender Antivirus Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md) und über die [Cloud bereitgestellter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="3ebec-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="3ebec-135">Nachdem Sie die Dienste aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall konfigurieren, um die Verbindungen zwischen den Diensten und Ihren Geräten zuzulassen (auch als Endpunkte bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="3ebec-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="3ebec-136">Überprüfen von Netzwerkschutzereignissen im Microsoft Defender für Endpunkt Security Center</span><span class="sxs-lookup"><span data-stu-id="3ebec-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="3ebec-137">Microsoft Defender für Endpunkt bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="3ebec-138">Sie können Microsoft Defender für Endpunktdaten mithilfe der [erweiterten Suche](advanced-hunting-overview.md)abfragen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="3ebec-139">Wenn Sie den [Überwachungsmodus](audit-windows-defender.md)verwenden, können Sie die erweiterte Suche verwenden, um zu sehen, wie sich Netzwerkschutzeinstellungen auf Ihre Umgebung auswirken, wenn sie aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3ebec-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="3ebec-140">Hier ist eine Beispielabfrage</span><span class="sxs-lookup"><span data-stu-id="3ebec-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="3ebec-141">Überprüfen von Netzwerkschutzereignissen in Windows Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="3ebec-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="3ebec-142">Sie können das Windows Ereignisprotokoll überprüfen, um Ereignisse anzuzeigen, die erstellt werden, wenn der Netzwerkschutz den Zugriff auf eine schädliche IP oder Domäne blockiert (oder überwacht):</span><span class="sxs-lookup"><span data-stu-id="3ebec-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="3ebec-143">[Kopieren Sie den XML-Code direkt.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="3ebec-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="3ebec-144">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3ebec-144">Select **OK**.</span></span>

<span data-ttu-id="3ebec-145">Dieses Verfahren erstellt eine benutzerdefinierte Ansicht, die filtert, um nur die folgenden Ereignisse im Zusammenhang mit dem Netzwerkschutz anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3ebec-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="3ebec-146">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3ebec-146">Event ID</span></span> | <span data-ttu-id="3ebec-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ebec-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="3ebec-148">5007</span><span class="sxs-lookup"><span data-stu-id="3ebec-148">5007</span></span> | <span data-ttu-id="3ebec-149">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="3ebec-149">Event when settings are changed</span></span> |
| <span data-ttu-id="3ebec-150">1125</span><span class="sxs-lookup"><span data-stu-id="3ebec-150">1125</span></span> | <span data-ttu-id="3ebec-151">Ereignis, wenn der Netzwerkschutz im Überwachungsmodus ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="3ebec-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="3ebec-152">1126</span><span class="sxs-lookup"><span data-stu-id="3ebec-152">1126</span></span> | <span data-ttu-id="3ebec-153">Ereignis, wenn der Netzwerkschutz im Blockierungsmodus ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="3ebec-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="3ebec-154">Überlegungen zum Windows virtuellen Desktops, auf dem Windows 10 Enterprise mehrere Sitzungen ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="3ebec-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="3ebec-155">Beachten Sie aufgrund der Multibenutzerart von Windows 10 Enterprise die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="3ebec-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="3ebec-156">Der Netzwerkschutz ist ein geräteweites Feature und kann nicht auf bestimmte Benutzersitzungen ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="3ebec-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="3ebec-157">Richtlinien für die Webinhaltsfilterung sind auch geräteweit.</span><span class="sxs-lookup"><span data-stu-id="3ebec-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="3ebec-158">Wenn Sie zwischen Benutzergruppen unterscheiden müssen, sollten Sie separate Windows Virtual Desktop-Hostpools und -Zuweisungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="3ebec-159">Testen Sie den Netzwerkschutz im Überwachungsmodus, um sein Verhalten vor dem Rollout zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="3ebec-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="3ebec-160">Ziehen Sie in Betracht, die Größe Ihrer Bereitstellung zu ändern, wenn Sie über eine große Anzahl von Benutzern oder eine große Anzahl von Sitzungen mit mehreren Benutzern verfügen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="3ebec-161">Alternative Option für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="3ebec-161">Alternative option for network protection</span></span>

<span data-ttu-id="3ebec-162">Für Windows 10 Enterprise Multi-Session 1909 und höher, die in Windows Virtual Desktop on Azure verwendet wird, kann der Netzwerkschutz für Microsoft Edge mithilfe der folgenden Methode aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="3ebec-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="3ebec-163">Verwenden Sie ["Netzwerkschutz aktivieren",](enable-network-protection.md) und befolgen Sie die Anweisungen, um Ihre Richtlinie anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="3ebec-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="3ebec-164">Führen Sie den folgenden PowerShell-Befehl aus: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="3ebec-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="3ebec-165">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="3ebec-165">Network protection troubleshooting</span></span>

<span data-ttu-id="3ebec-166">Aufgrund der Umgebung, in der Netzwerkschutz ausgeführt wird, kann Microsoft möglicherweise keine Proxyeinstellungen des Betriebssystems erkennen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="3ebec-167">In einigen Fällen können Netzwerkschutzclients den Clouddienst nicht erreichen.</span><span class="sxs-lookup"><span data-stu-id="3ebec-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="3ebec-168">Um das Konnektivitätsproblem zu beheben, sollten Kunden mit E5-Lizenzen einen der folgenden Defender-Registrierungsschlüssel konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3ebec-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="3ebec-169">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3ebec-169">Related articles</span></span>

- <span data-ttu-id="3ebec-170">[Auswerten des Netzwerkschutzes](evaluate-network-protection.md) | Führen Sie ein schnelles Szenario durch, das zeigt, wie das Feature funktioniert und welche Ereignisse in der Regel erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ebec-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="3ebec-171">[Netzwerkschutz | aktivieren](enable-network-protection.md) Verwenden Sie Gruppenrichtlinien, PowerShell oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="3ebec-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
