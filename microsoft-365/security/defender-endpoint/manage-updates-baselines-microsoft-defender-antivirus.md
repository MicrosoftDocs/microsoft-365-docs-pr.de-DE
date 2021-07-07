---
title: Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen
description: Verwalten, wie Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
keywords: Updates, Sicherheitsgrundwerte, Schutz, Updates planen, Updates erzwingen, mobile Updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314464"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="c1564-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="c1564-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="c1564-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c1564-105">**Applies to:**</span></span>

- [<span data-ttu-id="c1564-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c1564-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="c1564-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c1564-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="c1564-108">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c1564-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="c1564-109">Aktualisieren Sie den Virenschutz, auch wenn Microsoft Defender Antivirus im [passiven Modus](microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c1564-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="c1564-110">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="c1564-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="c1564-111">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="c1564-111">Security intelligence updates</span></span>
- <span data-ttu-id="c1564-112">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="c1564-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="c1564-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates) von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1564-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="c1564-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="c1564-114">Security intelligence updates</span></span>

<span data-ttu-id="c1564-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c1564-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="c1564-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="c1564-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="c1564-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="c1564-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="c1564-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="c1564-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="c1564-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c1564-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="c1564-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="c1564-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="c1564-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="c1564-122">Eine Liste der neuesten Security Intelligence-Updates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c1564-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="c1564-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c1564-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="c1564-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="c1564-124">Product updates</span></span>

<span data-ttu-id="c1564-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623),](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) die als *Plattformupdates* bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c1564-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="c1564-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="c1564-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="c1564-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="c1564-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="c1564-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c1564-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="c1564-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="c1564-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="c1564-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="c1564-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="c1564-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1564-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="c1564-132">In diesem Artikel werden Änderungen aufgelistet, die im Kanal für die allgemeine Version enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c1564-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="c1564-133">[Sehen Sie sich hier die neueste allgemeine Kanalversion an.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)</span><span class="sxs-lookup"><span data-stu-id="c1564-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="c1564-134">Weitere Informationen zum graduellen Rolloutprozess und weitere Informationen zur nächsten Version finden Sie unter [Verwalten des schrittweisen Rollouts für Microsoft Defender-Updates.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="c1564-135">Weitere Informationen zu Security Intelligence-Updates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c1564-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="c1564-136">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="c1564-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="c1564-137">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="c1564-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="c1564-138">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="c1564-138">All our updates contain</span></span> 
- <span data-ttu-id="c1564-139">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="c1564-139">performance improvements;</span></span>
- <span data-ttu-id="c1564-140">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="c1564-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="c1564-141">Integrationsverbesserungen (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="c1564-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="c1564-142">Juni -2021 (Plattform: 4.18.2106.5 | Modul: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="c1564-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="c1564-143">&ensp;Version des Security Intelligence-Updates: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="c1564-144">&ensp;Veröffentlicht: **28. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="c1564-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="c1564-145">&ensp;Plattform: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="c1564-146">&ensp;Modul: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="c1564-147">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="c1564-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-148">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-148">What's new</span></span>
- <span data-ttu-id="c1564-149">Neue Steuerelemente für die Verwaltung des schrittweisen Rollouts von Microsoft Defender-Updates.</span><span class="sxs-lookup"><span data-stu-id="c1564-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="c1564-150">Weitere Informationen finden Sie unter [Verwalten des schrittweisen Rollouts für Microsoft Defender-Updates.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="c1564-151">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="c1564-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="c1564-152">Verbesserungen beim Rollout von Antischadsoftwaredefinitionen</span><span class="sxs-lookup"><span data-stu-id="c1564-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="c1564-153">Erweiterte Edge-Netzwerk-Ereignisüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="c1564-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-154">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-154">Known Issues</span></span>
<span data-ttu-id="c1564-155">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-156">Mai-2021 (Plattform: 4.18.2105.4 | Modul: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="c1564-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="c1564-157">&ensp;Security Intelligence Update-Version: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="c1564-158">&ensp;Veröffentlicht: **3. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="c1564-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="c1564-159">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="c1564-160">&ensp;Modul: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="c1564-161">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="c1564-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-162">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-162">What's new</span></span>
- <span data-ttu-id="c1564-163">Verbesserungen bei der [Verhaltensüberwachung](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="c1564-164">Benachrichtigungsfilterungsfeature für den Fixed [Network-Schutz](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-165">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-165">Known Issues</span></span>
<span data-ttu-id="c1564-166">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-167">April 2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="c1564-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="c1564-168">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="c1564-169">&ensp;Veröffentlicht: **26. April 2021**  (Modul: 1.1.18100.6 veröffentlicht am 5. Mai 2021) &ensp; Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="c1564-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="c1564-170">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="c1564-171">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="c1564-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-172">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-172">What's new</span></span>
- <span data-ttu-id="c1564-173">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="c1564-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="c1564-174">Verbesserte Kernelmodus-Schlüsselprotokollierungserkennung</span><span class="sxs-lookup"><span data-stu-id="c1564-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="c1564-175">Neue Steuerelemente zum Verwalten des schrittweisen Rollouts für [Microsoft Defender-Updates hinzugefügt](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="c1564-176">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-176">Known Issues</span></span>
<span data-ttu-id="c1564-177">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="c1564-178">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="c1564-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="c1564-179">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="c1564-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="c1564-180">Ältere Versionen als die in diesem Abschnitt aufgeführten versionen werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1564-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="c1564-181">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="c1564-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="c1564-182">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="c1564-183">&ensp;Veröffentlicht: **2. April 2021**</span><span class="sxs-lookup"><span data-stu-id="c1564-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="c1564-184">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="c1564-185">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="c1564-186">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-187">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-187">What's new</span></span>

- <span data-ttu-id="c1564-188">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="c1564-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="c1564-189">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="c1564-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="c1564-190">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c1564-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-191">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-191">Known Issues</span></span>
<span data-ttu-id="c1564-192">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-193">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="c1564-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="c1564-194">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="c1564-195">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="c1564-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="c1564-196">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="c1564-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="c1564-197">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="c1564-198">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-199">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-199">What's new</span></span>

- <span data-ttu-id="c1564-200">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="c1564-201">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="c1564-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-202">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-202">Known Issues</span></span>
<span data-ttu-id="c1564-203">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-204">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="c1564-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="c1564-205">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c1564-206">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="c1564-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="c1564-207">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="c1564-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="c1564-208">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1564-209">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-210">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-210">What's new</span></span>

- <span data-ttu-id="c1564-211">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="c1564-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="c1564-212">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="c1564-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="c1564-213">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="c1564-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="c1564-214">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="c1564-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="c1564-215">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="c1564-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-216">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-216">Known Issues</span></span>
<span data-ttu-id="c1564-217">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-218">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="c1564-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="c1564-219">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c1564-220">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="c1564-221">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="c1564-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="c1564-222">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="c1564-223">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-224">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-224">What's new</span></span>

- <span data-ttu-id="c1564-225">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="c1564-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-226">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-226">Known Issues</span></span>
<span data-ttu-id="c1564-227">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-228">Oktober -2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="c1564-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="c1564-229">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="c1564-230">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="c1564-231">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="c1564-232">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1564-233">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-234">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-234">What's new</span></span>

- <span data-ttu-id="c1564-235">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="c1564-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="c1564-236">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c1564-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="c1564-237">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c1564-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="c1564-238">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="c1564-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-239">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-239">Known Issues</span></span>

<span data-ttu-id="c1564-240">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1564-241">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="c1564-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="c1564-242">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="c1564-243">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="c1564-244">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="c1564-245">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="c1564-246">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-247">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-247">What's new</span></span>

- <span data-ttu-id="c1564-248">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1564-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="c1564-249">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="c1564-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="c1564-250">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="c1564-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="c1564-251">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="c1564-251">New management interfaces for:</span></span>
   - <span data-ttu-id="c1564-252">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="c1564-252">UDP Inspection</span></span>
   - <span data-ttu-id="c1564-253">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="c1564-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="c1564-254">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="c1564-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="c1564-255">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="c1564-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="c1564-256">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="c1564-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-257">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-257">Known Issues</span></span>

<span data-ttu-id="c1564-258">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="c1564-259">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="c1564-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="c1564-260">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="c1564-261">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="c1564-262">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="c1564-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="c1564-263">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="c1564-264">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="c1564-265">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-265">What's new</span></span>

- <span data-ttu-id="c1564-266">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="c1564-266">Add more telemetry events</span></span>
- <span data-ttu-id="c1564-267">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="c1564-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="c1564-268">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="c1564-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="c1564-269">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="c1564-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="c1564-270">`AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c1564-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="c1564-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c1564-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="c1564-272">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c1564-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="c1564-273">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-273">Known Issues</span></span>
<span data-ttu-id="c1564-274">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-275">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="c1564-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="c1564-276">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="c1564-277">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="c1564-278">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="c1564-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="c1564-279">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="c1564-280">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-281">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-281">What's new</span></span>

- <span data-ttu-id="c1564-282">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="c1564-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="c1564-283">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="c1564-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-284">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-284">Known Issues</span></span>
<span data-ttu-id="c1564-285">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-286">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="c1564-287">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="c1564-288">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="c1564-289">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="c1564-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="c1564-290">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="c1564-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="c1564-291">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-292">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-292">What's new</span></span>

- <span data-ttu-id="c1564-293">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="c1564-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="c1564-294">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="c1564-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="c1564-295">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="c1564-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="c1564-296">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="c1564-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="c1564-297">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="c1564-297">Fixed registry query</span></span> 
- <span data-ttu-id="c1564-298">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-299">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-299">Known Issues</span></span>
<span data-ttu-id="c1564-300">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-301">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="c1564-302">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="c1564-303">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="c1564-304">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="c1564-305">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="c1564-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="c1564-306">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-307">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-307">What's new</span></span>

- <span data-ttu-id="c1564-308">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="c1564-308">Improved logging for scan events</span></span>
- <span data-ttu-id="c1564-309">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="c1564-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="c1564-310">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c1564-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="c1564-311">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="c1564-312">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="c1564-313">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="c1564-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-314">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-314">Known Issues</span></span>
<span data-ttu-id="c1564-315">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-316">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="c1564-317">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="c1564-318">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="c1564-319">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="c1564-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="c1564-320">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="c1564-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="c1564-321">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-322">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-322">What's new</span></span>
- <span data-ttu-id="c1564-323">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="c1564-323">WDfilter improvements</span></span>
- <span data-ttu-id="c1564-324">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="c1564-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="c1564-325">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="c1564-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="c1564-326">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="c1564-327">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c1564-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="c1564-328">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="c1564-328">UEFI scan capability</span></span>
- <span data-ttu-id="c1564-329">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="c1564-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1564-330">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-330">Known Issues</span></span>
<span data-ttu-id="c1564-331">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-332">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="c1564-333">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="c1564-334">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="c1564-335">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="c1564-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="c1564-336">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="c1564-337">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1564-338">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-338">What's new</span></span>

- <span data-ttu-id="c1564-339">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c1564-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="c1564-340">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="c1564-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="c1564-341">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="c1564-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="c1564-342">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="c1564-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="c1564-343">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="c1564-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1564-344">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-344">Known Issues</span></span>
<span data-ttu-id="c1564-345">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="c1564-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="c1564-346">Februar-2020 (Plattform: – | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="c1564-347">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="c1564-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="c1564-348">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="c1564-349">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="c1564-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="c1564-350">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="c1564-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="c1564-351">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c1564-352">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="c1564-353">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-353">Known Issues</span></span>
<span data-ttu-id="c1564-354">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-355">Januar-2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="c1564-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="c1564-356">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="c1564-357">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="c1564-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="c1564-358">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="c1564-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="c1564-359">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="c1564-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="c1564-360">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="c1564-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c1564-361">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-361">What's new</span></span>

- <span data-ttu-id="c1564-362">BSOD in WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="c1564-363">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="c1564-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="c1564-364">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c1564-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="c1564-365">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c1564-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="c1564-366">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="c1564-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1564-367">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-367">Known Issues</span></span>

<span data-ttu-id="c1564-368">[**Fixed**] Devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span><span class="sxs-lookup"><span data-stu-id="c1564-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="c1564-369">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="c1564-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="c1564-370">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="c1564-370">This update is:</span></span>
> - <span data-ttu-id="c1564-371">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="c1564-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="c1564-372">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="c1564-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="c1564-373">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="c1564-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="c1564-374">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="c1564-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="c1564-375">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="c1564-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1564-376">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="c1564-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="c1564-377">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="c1564-378">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="c1564-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="c1564-379">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="c1564-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="c1564-380">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="c1564-381">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="c1564-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="c1564-382">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="c1564-382">What's new</span></span>

- <span data-ttu-id="c1564-383">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="c1564-384">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="c1564-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="c1564-385">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="c1564-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="c1564-386">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="c1564-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1564-387">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="c1564-387">Known Issues</span></span>
<span data-ttu-id="c1564-388">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.18.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="c1564-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="c1564-389">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="c1564-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="c1564-390">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1564-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="c1564-391">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="c1564-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="c1564-392">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="c1564-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="c1564-393">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c1564-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="c1564-394">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="c1564-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="c1564-395">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="c1564-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="c1564-396">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion, die in Windows 10-Versionen enthalten ist)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1564-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="c1564-397">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c1564-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="c1564-398">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c1564-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="c1564-399">In Windows 10-Versionen enthaltene Plattformversion</span><span class="sxs-lookup"><span data-stu-id="c1564-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="c1564-400">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10-Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="c1564-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="c1564-401">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="c1564-401">Windows 10 release</span></span>  |<span data-ttu-id="c1564-402">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="c1564-402">Platform version</span></span>  |<span data-ttu-id="c1564-403">Modulversion</span><span class="sxs-lookup"><span data-stu-id="c1564-403">Engine version</span></span> |<span data-ttu-id="c1564-404">Supportphase</span><span class="sxs-lookup"><span data-stu-id="c1564-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="c1564-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="c1564-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="c1564-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="c1564-406">4.18.1909.6</span></span> |<span data-ttu-id="c1564-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="c1564-407">1.1.17000.2</span></span> | <span data-ttu-id="c1564-408">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="c1564-409">1909  (19H2)</span></span> |<span data-ttu-id="c1564-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c1564-410">4.18.1902.5</span></span> |<span data-ttu-id="c1564-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="c1564-411">1.1.16700.3</span></span> | <span data-ttu-id="c1564-412">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="c1564-413">1903  (19H1)</span></span> |<span data-ttu-id="c1564-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c1564-414">4.18.1902.5</span></span> |<span data-ttu-id="c1564-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="c1564-415">1.1.15600.4</span></span> | <span data-ttu-id="c1564-416">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="c1564-417">1809  (RS5)</span></span> |<span data-ttu-id="c1564-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="c1564-418">4.18.1807.18075</span></span> |<span data-ttu-id="c1564-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="c1564-419">1.1.15000.2</span></span> | <span data-ttu-id="c1564-420">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="c1564-421">1803  (RS4)</span></span> |<span data-ttu-id="c1564-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="c1564-422">4.13.17134.1</span></span> |<span data-ttu-id="c1564-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="c1564-423">1.1.14600.4</span></span> | <span data-ttu-id="c1564-424">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="c1564-425">1709  (RS3)</span></span> |<span data-ttu-id="c1564-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="c1564-426">4.12.16299.15</span></span> |<span data-ttu-id="c1564-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="c1564-427">1.1.14104.0</span></span> | <span data-ttu-id="c1564-428">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="c1564-429">1703  (RS2)</span></span> |<span data-ttu-id="c1564-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="c1564-430">4.11.15603.2</span></span> |<span data-ttu-id="c1564-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="c1564-431">1.1.13504.0</span></span> | <span data-ttu-id="c1564-432">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1564-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="c1564-433">1607 (RS1)</span></span> |<span data-ttu-id="c1564-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="c1564-434">4.10.14393.3683</span></span> |<span data-ttu-id="c1564-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="c1564-435">1.1.12805.0</span></span> | <span data-ttu-id="c1564-436">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="c1564-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="c1564-437">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="c1564-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="c1564-438">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="c1564-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="c1564-439">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antivirus- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c1564-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="c1564-440">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="c1564-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="c1564-441">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Betriebssysteminstallationsimages.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="c1564-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="c1564-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="c1564-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="c1564-443">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="c1564-444">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="c1564-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="c1564-445">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c1564-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c1564-446">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-447">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-447">Fixes</span></span>
- <span data-ttu-id="c1564-448">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-449">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-449">Additional information</span></span>
- <span data-ttu-id="c1564-450">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="c1564-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="c1564-452">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="c1564-453">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="c1564-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="c1564-454">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c1564-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c1564-455">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-456">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-456">Fixes</span></span>
- <span data-ttu-id="c1564-457">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-458">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-458">Additional information</span></span>
- <span data-ttu-id="c1564-459">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="c1564-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="c1564-461">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="c1564-462">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="c1564-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="c1564-463">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="c1564-464">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-465">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-465">Fixes</span></span>
- <span data-ttu-id="c1564-466">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-467">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-467">Additional information</span></span>
- <span data-ttu-id="c1564-468">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="c1564-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="c1564-470">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="c1564-471">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="c1564-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="c1564-472">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1564-473">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-474">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-474">Fixes</span></span>
- <span data-ttu-id="c1564-475">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-476">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-476">Additional information</span></span>
- <span data-ttu-id="c1564-477">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="c1564-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="c1564-479">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="c1564-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="c1564-480">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c1564-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c1564-481">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1564-482">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-483">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-483">Fixes</span></span>
- <span data-ttu-id="c1564-484">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-485">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-485">Additional information</span></span>
- <span data-ttu-id="c1564-486">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="c1564-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="c1564-488">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="c1564-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="c1564-489">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c1564-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c1564-490">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c1564-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="c1564-491">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-492">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-492">Fixes</span></span>
- <span data-ttu-id="c1564-493">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-494">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-494">Additional information</span></span>
- <span data-ttu-id="c1564-495">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="c1564-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="c1564-497">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="c1564-498">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c1564-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c1564-499">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1564-500">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-501">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-501">Fixes</span></span>
- <span data-ttu-id="c1564-502">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-503">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-503">Additional information</span></span>
- <span data-ttu-id="c1564-504">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="c1564-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="c1564-506">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="c1564-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="c1564-507">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c1564-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c1564-508">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1564-509">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-510">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-510">Fixes</span></span>
- <span data-ttu-id="c1564-511">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-512">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-512">Additional information</span></span>
- <span data-ttu-id="c1564-513">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="c1564-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="c1564-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="c1564-515">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c1564-516">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c1564-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="c1564-517">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1564-518">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-519">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-519">Fixes</span></span>
- <span data-ttu-id="c1564-520">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-521">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-521">Additional information</span></span>
- <span data-ttu-id="c1564-522">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1564-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="c1564-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="c1564-524">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c1564-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c1564-525">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="c1564-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="c1564-526">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c1564-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="c1564-527">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="c1564-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1564-528">Behebungen</span><span class="sxs-lookup"><span data-stu-id="c1564-528">Fixes</span></span>
- <span data-ttu-id="c1564-529">Keine</span><span class="sxs-lookup"><span data-stu-id="c1564-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1564-530">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1564-530">Additional information</span></span>
- <span data-ttu-id="c1564-531">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c1564-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="c1564-532">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c1564-532">Additional resources</span></span>

| <span data-ttu-id="c1564-533">Artikel</span><span class="sxs-lookup"><span data-stu-id="c1564-533">Article</span></span> | <span data-ttu-id="c1564-534">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1564-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="c1564-535">Microsoft Defender Update für Windows Installationsimages des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="c1564-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="c1564-536">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="c1564-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="c1564-537">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="c1564-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="c1564-538">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="c1564-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c1564-539">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c1564-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="c1564-540">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="c1564-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="c1564-541">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c1564-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="c1564-542">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="c1564-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="c1564-543">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c1564-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="c1564-544">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="c1564-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c1564-545">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="c1564-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="c1564-546">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="c1564-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="c1564-547">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="c1564-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
