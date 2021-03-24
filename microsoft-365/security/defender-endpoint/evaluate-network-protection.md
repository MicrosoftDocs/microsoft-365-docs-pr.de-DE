---
title: Bewerten des Netzwerkschutzes
description: Erfahren Sie, wie der Netzwerkschutz funktioniert, indem Sie gängige Szenarien testen, vor denen er schützt.
keywords: Netzwerkschutz, Exploits, schädliche Website, IP, Domäne, Domänen, Evaluieren, Testen, Demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41d1c9400720e20185922a97463e776c3ce0d80a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064192"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="f8238-104">Bewerten des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="f8238-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8238-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f8238-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8238-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f8238-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="f8238-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8238-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f8238-108">[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können.</span><span class="sxs-lookup"><span data-stu-id="f8238-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="f8238-109">Dieser Artikel hilft Ihnen bei der Bewertung des Netzwerkschutzes, indem Sie das Feature aktivieren und Sie zu einer Testwebsite führen.</span><span class="sxs-lookup"><span data-stu-id="f8238-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="f8238-110">Die Websites in diesem Evaluierungsartikel sind nicht bösartig.</span><span class="sxs-lookup"><span data-stu-id="f8238-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="f8238-111">Es sind speziell erstellte Websites, die vorgeben, bösartig zu sein.</span><span class="sxs-lookup"><span data-stu-id="f8238-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="f8238-112">Die Website repliziert das Verhalten, das auftreten würde, wenn ein Benutzer eine schädliche Website oder Domäne besuchte.</span><span class="sxs-lookup"><span data-stu-id="f8238-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="f8238-113">Sie können auch die Microsoft Defender Testground-Website unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu sehen, wie andere Schutzfunktionen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f8238-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="f8238-114">Aktivieren des Netzwerkschutzes im Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="f8238-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="f8238-115">Aktivieren Sie den Netzwerkschutz im Überwachungsmodus, um zu sehen, welche IP-Adressen und Domänen blockiert worden wären.</span><span class="sxs-lookup"><span data-stu-id="f8238-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="f8238-116">Sie können sicherstellen, dass sich dies nicht auf Business-Apps aus wirkt, oder Sie können sich eine Vorstellung davon machen, wie oft Blöcke auftreten.</span><span class="sxs-lookup"><span data-stu-id="f8238-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="f8238-117">Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **maustaste Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="f8238-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="f8238-118">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="f8238-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="f8238-119">Besuchen einer (gefälschten) bösartigen Domäne</span><span class="sxs-lookup"><span data-stu-id="f8238-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="f8238-120">Öffnen Sie Internet Explorer, Google Chrome oder einen anderen Browser Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="f8238-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="f8238-121">Wechseln Sie zu [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="f8238-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="f8238-122">Die Netzwerkverbindung ist zulässig, und es wird eine Testnachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8238-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Beispielbenachrichtigung mit der Meldung "Verbindung blockiert": Ihr IT-Administrator hat windows Security dazu verangert, diese Netzwerkverbindung zu blockieren.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="f8238-125">Überprüfen von Netzwerkschutzereignissen in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="f8238-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="f8238-126">Um Apps zu überprüfen, die blockiert wurden, öffnen Sie die Ereignisanzeige, und filtern Sie im Microsoft-Windows-Windows-Defender/Operational-Protokoll nach Ereignis-ID 1125.</span><span class="sxs-lookup"><span data-stu-id="f8238-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="f8238-127">In der folgenden Tabelle sind alle Netzwerkschutzereignisse aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8238-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="f8238-128">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f8238-128">Event ID</span></span> | <span data-ttu-id="f8238-129">Bereitstellen/Quelle</span><span class="sxs-lookup"><span data-stu-id="f8238-129">Provide/Source</span></span> | <span data-ttu-id="f8238-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8238-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="f8238-131">5007</span><span class="sxs-lookup"><span data-stu-id="f8238-131">5007</span></span> | <span data-ttu-id="f8238-132">Windows Defender (Betriebsbereit)</span><span class="sxs-lookup"><span data-stu-id="f8238-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="f8238-133">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="f8238-133">Event when settings are changed</span></span> |
|<span data-ttu-id="f8238-134">1125</span><span class="sxs-lookup"><span data-stu-id="f8238-134">1125</span></span> | <span data-ttu-id="f8238-135">Windows Defender (Betriebsbereit)</span><span class="sxs-lookup"><span data-stu-id="f8238-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="f8238-136">Ereignis, wenn eine Netzwerkverbindung überwacht wird</span><span class="sxs-lookup"><span data-stu-id="f8238-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="f8238-137">1126</span><span class="sxs-lookup"><span data-stu-id="f8238-137">1126</span></span> | <span data-ttu-id="f8238-138">Windows Defender (Betriebsbereit)</span><span class="sxs-lookup"><span data-stu-id="f8238-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="f8238-139">Ereignis, wenn eine Netzwerkverbindung blockiert wird</span><span class="sxs-lookup"><span data-stu-id="f8238-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="f8238-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8238-140">See also</span></span>

* [<span data-ttu-id="f8238-141">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="f8238-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="f8238-142">Aktivieren des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="f8238-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="f8238-143">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="f8238-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
