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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198653"
---
# <a name="protect-your-network"></a><span data-ttu-id="9f6d9-104">Schützen Ihres Netzwerks</span><span class="sxs-lookup"><span data-stu-id="9f6d9-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f6d9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9f6d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="9f6d9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9f6d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9f6d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f6d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9f6d9-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9f6d9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f6d9-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9f6d9-110">Der Netzwerkschutz reduziert die Angriffsfläche Ihrer Geräte durch internetbasierte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="9f6d9-111">Es verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="9f6d9-112">Der Netzwerkschutz erweitert den Umfang von [Microsoft Defender SmartScreen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) um den gesamten ausgehenden HTTP-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Reputation herzustellen (basierend auf der Domäne oder dem Hostnamen).</span><span class="sxs-lookup"><span data-stu-id="9f6d9-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="9f6d9-113">Der Netzwerkschutz wird unter Windows unterstützt, beginnend mit Windows 10, Version 1709.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="9f6d9-114">Weitere Informationen zum Aktivieren des Netzwerkschutzes finden Sie unter [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9f6d9-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="9f6d9-115">Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="9f6d9-116">Sehen Sie sich die Microsoft Defender ATP-Testground-Website [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu sehen, wie netzwerkschutz funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="9f6d9-117">Der Netzwerkschutz funktioniert am besten [mit Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), mit dem Sie detaillierte Berichte zu Exploitschutzereignissen und -blöcken im Rahmen von Warnungsuntersuchungsszenarien erstellen [können.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="9f6d9-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="9f6d9-118">Wenn netzwerkschutz eine Verbindung blockiert, wird eine Benachrichtigung aus dem Aktionscenter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="9f6d9-119">Ihr Sicherheitsteam kann [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) den Details und Kontaktinformationen Ihrer Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="9f6d9-120">Darüber hinaus können individuelle Regeln zur Reduzierung der Angriffsfläche aktiviert und an bestimmte Überwachungstechniken angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="9f6d9-121">Sie können auch den [Überwachungsmodus verwenden,](audit-windows-defender.md) um zu bewerten, wie sich der Netzwerkschutz auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f6d9-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f6d9-122">Requirements</span></span>

<span data-ttu-id="9f6d9-123">Netzwerkschutz erfordert Windows 10 Pro oder Enterprise und Microsoft Defender Antivirus Echtzeitschutz.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="9f6d9-124">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="9f6d9-124">Windows version</span></span> | <span data-ttu-id="9f6d9-125">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9f6d9-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="9f6d9-126">Windows 10, Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="9f6d9-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="9f6d9-127">Windows Server 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="9f6d9-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="9f6d9-128">[Microsoft Defender Antivirus-Echtzeitschutz und](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) [Cloud-zugestellter Schutz](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) müssen aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="9f6d9-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="9f6d9-129">Nachdem Sie die Dienste aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall so konfigurieren, dass die Verbindungen zwischen den Diensten und Ihren Geräten (auch als Endpunkte bezeichnet) zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="9f6d9-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9f6d9-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="9f6d9-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9f6d9-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="9f6d9-132">Überprüfen von Netzwerkschutzereignissen im Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="9f6d9-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="9f6d9-133">Microsoft Defender for Endpoint bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="9f6d9-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="9f6d9-134">Sie können Microsoft Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="9f6d9-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="9f6d9-135">Wenn Sie den Überwachungsmodus [verwenden,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu sehen, wie sich Netzwerkschutzeinstellungen auf Ihre Umgebung auswirken würden, wenn sie aktiviert wären.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="9f6d9-136">Hier ist eine Beispielabfrage</span><span class="sxs-lookup"><span data-stu-id="9f6d9-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="9f6d9-137">Überprüfen von Netzwerkschutzereignissen in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="9f6d9-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="9f6d9-138">Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die erstellt werden, wenn der Netzwerkschutz den Zugriff auf eine schädliche IP oder Domäne blockiert (oder überwacht):</span><span class="sxs-lookup"><span data-stu-id="9f6d9-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="9f6d9-139">[Kopieren Sie die XML direkt](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="9f6d9-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="9f6d9-140">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-140">Select **OK**.</span></span>

<span data-ttu-id="9f6d9-141">Mit diesem Verfahren wird eine benutzerdefinierte Ansicht erstellt, die filtert, um nur die folgenden Ereignisse im Zusammenhang mit dem Netzwerkschutz zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="9f6d9-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="9f6d9-142">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9f6d9-142">Event ID</span></span> | <span data-ttu-id="9f6d9-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f6d9-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="9f6d9-144">5007</span><span class="sxs-lookup"><span data-stu-id="9f6d9-144">5007</span></span> | <span data-ttu-id="9f6d9-145">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="9f6d9-145">Event when settings are changed</span></span> |
| <span data-ttu-id="9f6d9-146">1125</span><span class="sxs-lookup"><span data-stu-id="9f6d9-146">1125</span></span> | <span data-ttu-id="9f6d9-147">Ereignis, wenn der Netzwerkschutz im Überwachungsmodus abgeschaltet wird</span><span class="sxs-lookup"><span data-stu-id="9f6d9-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="9f6d9-148">1126</span><span class="sxs-lookup"><span data-stu-id="9f6d9-148">1126</span></span> | <span data-ttu-id="9f6d9-149">Ereignis, wenn der Netzwerkschutz im Blockmodus abgeschaltet wird</span><span class="sxs-lookup"><span data-stu-id="9f6d9-149">Event when network protection fires in block mode</span></span> |

## <a name="related-articles"></a><span data-ttu-id="9f6d9-150">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9f6d9-150">Related articles</span></span>

- <span data-ttu-id="9f6d9-151">[Bewerten von Netzwerkschutz|](evaluate-network-protection.md) Gehen Sie ein schnelles Szenario durch, das veranschaulicht, wie das Feature funktioniert und welche Ereignisse in der Regel erstellt würden.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-151">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="9f6d9-152">[Aktivieren von Netzwerkschutz](enable-network-protection.md) | Verwenden Sie Gruppenrichtlinien, PowerShell- oder MDM-CSPs, um den Netzwerkschutz in Ihrem Netzwerk zu aktivieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f6d9-152">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
