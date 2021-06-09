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
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822274"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="f048c-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="f048c-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="f048c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f048c-105">**Applies to:**</span></span>

- [<span data-ttu-id="f048c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f048c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="f048c-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f048c-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f048c-108">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="f048c-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="f048c-109">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="f048c-109">Security intelligence updates</span></span>
- <span data-ttu-id="f048c-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="f048c-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f048c-111">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f048c-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="f048c-112">Aktualisieren Sie den Virenschutz auch dann, wenn Microsoft Defender Antivirus im [passiven Modus](./microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f048c-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="f048c-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f048c-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="f048c-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="f048c-114">Security intelligence updates</span></span>

<span data-ttu-id="f048c-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f048c-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="f048c-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f048c-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="f048c-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="f048c-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="f048c-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="f048c-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="f048c-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f048c-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="f048c-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="f048c-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="f048c-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f048c-122">Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f048c-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="f048c-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f048c-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="f048c-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="f048c-124">Product updates</span></span>

<span data-ttu-id="f048c-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="f048c-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="f048c-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="f048c-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="f048c-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="f048c-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="f048c-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f048c-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="f048c-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="f048c-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="f048c-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="f048c-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="f048c-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f048c-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="f048c-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="f048c-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="f048c-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="f048c-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="f048c-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="f048c-134">All our updates contain</span></span> 
- <span data-ttu-id="f048c-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="f048c-135">performance improvements;</span></span>
- <span data-ttu-id="f048c-136">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="f048c-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="f048c-137">Integrationsverbesserungen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="f048c-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="f048c-138">Mai-2021 (Plattform: 4.18.2105.4 | Modul: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="f048c-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="f048c-139">&ensp;Security Intelligence Update-Version: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="f048c-140">&ensp;Veröffentlicht: **4. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="f048c-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="f048c-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="f048c-142">&ensp;Modul: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="f048c-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f048c-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-144">What's new</span></span>
- <span data-ttu-id="f048c-145">Verbesserungen bei der [Verhaltensüberwachung](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="f048c-146">Benachrichtigungsfilterungsfeature für den Fixed [Network-Schutz](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-147">Known Issues</span></span>
<span data-ttu-id="f048c-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-149">April -2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="f048c-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="f048c-150">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="f048c-151">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="f048c-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f048c-152">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="f048c-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="f048c-153">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="f048c-154">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f048c-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-155">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-155">What's new</span></span>
- <span data-ttu-id="f048c-156">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="f048c-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="f048c-157">Verbesserte Kernelmodus-Keyloggererkennung</span><span class="sxs-lookup"><span data-stu-id="f048c-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="f048c-158">Neue Steuerelemente zum Verwalten des schrittweisen Rollouts für [Microsoft Defender-Updates hinzugefügt](updates.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-159">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-159">Known Issues</span></span>
<span data-ttu-id="f048c-160">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-161">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="f048c-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="f048c-162">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="f048c-163">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="f048c-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f048c-164">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="f048c-165">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="f048c-166">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f048c-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-167">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-167">What's new</span></span>

- <span data-ttu-id="f048c-168">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="f048c-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="f048c-169">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="f048c-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="f048c-170">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="f048c-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-171">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-171">Known Issues</span></span>
<span data-ttu-id="f048c-172">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="f048c-173">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="f048c-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="f048c-174">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="f048c-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="f048c-175">Ältere Versionen sind in diesem Abschnitt aufgeführt und werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f048c-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="f048c-176">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="f048c-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="f048c-177">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="f048c-178">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="f048c-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="f048c-179">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="f048c-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="f048c-180">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="f048c-181">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-182">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-182">What's new</span></span>

- <span data-ttu-id="f048c-183">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="f048c-184">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="f048c-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-185">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-185">Known Issues</span></span>
<span data-ttu-id="f048c-186">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-187">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="f048c-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="f048c-188">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f048c-189">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="f048c-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="f048c-190">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="f048c-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="f048c-191">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="f048c-192">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-193">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-193">What's new</span></span>

- <span data-ttu-id="f048c-194">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="f048c-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="f048c-195">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f048c-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="f048c-196">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="f048c-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="f048c-197">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="f048c-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="f048c-198">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="f048c-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-199">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-199">Known Issues</span></span>
<span data-ttu-id="f048c-200">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-201">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="f048c-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="f048c-202">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f048c-203">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="f048c-204">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="f048c-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="f048c-205">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="f048c-206">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-207">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-207">What's new</span></span>

- <span data-ttu-id="f048c-208">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="f048c-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-209">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-209">Known Issues</span></span>
<span data-ttu-id="f048c-210">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-211">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="f048c-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="f048c-212">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="f048c-213">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="f048c-214">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="f048c-215">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="f048c-216">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-217">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-217">What's new</span></span>

- <span data-ttu-id="f048c-218">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="f048c-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="f048c-219">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="f048c-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="f048c-220">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f048c-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="f048c-221">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f048c-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-222">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-222">Known Issues</span></span>

<span data-ttu-id="f048c-223">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f048c-224">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="f048c-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="f048c-225">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="f048c-226">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="f048c-227">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="f048c-228">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="f048c-229">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-230">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-230">What's new</span></span>

- <span data-ttu-id="f048c-231">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f048c-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="f048c-232">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="f048c-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="f048c-233">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="f048c-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="f048c-234">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="f048c-234">New management interfaces for:</span></span>
   - <span data-ttu-id="f048c-235">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="f048c-235">UDP Inspection</span></span>
   - <span data-ttu-id="f048c-236">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="f048c-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="f048c-237">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="f048c-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="f048c-238">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="f048c-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="f048c-239">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f048c-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-240">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-240">Known Issues</span></span>

<span data-ttu-id="f048c-241">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="f048c-242">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="f048c-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="f048c-243">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="f048c-244">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="f048c-245">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="f048c-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="f048c-246">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="f048c-247">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="f048c-248">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-248">What's new</span></span>

- <span data-ttu-id="f048c-249">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="f048c-249">Add more telemetry events</span></span>
- <span data-ttu-id="f048c-250">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="f048c-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="f048c-251">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="f048c-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="f048c-252">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="f048c-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="f048c-253">`AMRunningMode`Hinzugefügt zu Get-MpComputerStatus PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f048c-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="f048c-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f048c-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="f048c-255">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f048c-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="f048c-256">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-256">Known Issues</span></span>
<span data-ttu-id="f048c-257">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-258">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="f048c-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="f048c-259">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="f048c-260">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="f048c-261">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="f048c-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="f048c-262">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="f048c-263">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-264">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-264">What's new</span></span>

- <span data-ttu-id="f048c-265">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="f048c-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="f048c-266">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f048c-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-267">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-267">Known Issues</span></span>
<span data-ttu-id="f048c-268">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-269">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="f048c-270">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="f048c-271">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="f048c-272">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="f048c-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="f048c-273">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="f048c-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="f048c-274">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-275">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-275">What's new</span></span>

- <span data-ttu-id="f048c-276">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="f048c-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="f048c-277">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="f048c-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="f048c-278">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="f048c-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="f048c-279">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="f048c-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="f048c-280">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="f048c-280">Fixed registry query</span></span> 
- <span data-ttu-id="f048c-281">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-282">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-282">Known Issues</span></span>
<span data-ttu-id="f048c-283">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-284">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="f048c-285">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="f048c-286">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="f048c-287">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="f048c-288">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="f048c-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="f048c-289">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-290">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-290">What's new</span></span>

- <span data-ttu-id="f048c-291">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="f048c-291">Improved logging for scan events</span></span>
- <span data-ttu-id="f048c-292">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="f048c-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="f048c-293">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f048c-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="f048c-294">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="f048c-295">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="f048c-296">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="f048c-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-297">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-297">Known Issues</span></span>
<span data-ttu-id="f048c-298">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-299">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="f048c-300">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="f048c-301">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="f048c-302">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="f048c-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="f048c-303">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="f048c-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="f048c-304">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-305">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-305">What's new</span></span>
- <span data-ttu-id="f048c-306">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="f048c-306">WDfilter improvements</span></span>
- <span data-ttu-id="f048c-307">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="f048c-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="f048c-308">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="f048c-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="f048c-309">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="f048c-310">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f048c-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="f048c-311">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="f048c-311">UEFI scan capability</span></span>
- <span data-ttu-id="f048c-312">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="f048c-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="f048c-313">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-313">Known Issues</span></span>
<span data-ttu-id="f048c-314">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-315">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="f048c-316">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="f048c-317">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="f048c-318">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="f048c-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="f048c-319">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="f048c-320">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f048c-321">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-321">What's new</span></span>

- <span data-ttu-id="f048c-322">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f048c-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="f048c-323">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="f048c-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="f048c-324">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="f048c-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="f048c-325">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="f048c-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="f048c-326">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="f048c-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f048c-327">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-327">Known Issues</span></span>
<span data-ttu-id="f048c-328">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="f048c-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="f048c-329">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="f048c-330">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="f048c-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="f048c-331">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="f048c-332">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="f048c-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="f048c-333">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="f048c-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="f048c-334">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f048c-335">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="f048c-336">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-336">Known Issues</span></span>
<span data-ttu-id="f048c-337">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-338">Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="f048c-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="f048c-339">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="f048c-340">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="f048c-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="f048c-341">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="f048c-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="f048c-342">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="f048c-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="f048c-343">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f048c-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f048c-344">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-344">What's new</span></span>

- <span data-ttu-id="f048c-345">BSOD auf WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="f048c-346">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="f048c-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="f048c-347">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f048c-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="f048c-348">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f048c-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="f048c-349">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="f048c-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f048c-350">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-350">Known Issues</span></span>

<span data-ttu-id="f048c-351">[**Fixed**] Devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span><span class="sxs-lookup"><span data-stu-id="f048c-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="f048c-352">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="f048c-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="f048c-353">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="f048c-353">This update is:</span></span>
> - <span data-ttu-id="f048c-354">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="f048c-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="f048c-355">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="f048c-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="f048c-356">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="f048c-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="f048c-357">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="f048c-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="f048c-358">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="f048c-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f048c-359">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="f048c-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="f048c-360">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="f048c-361">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="f048c-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="f048c-362">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="f048c-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="f048c-363">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="f048c-364">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="f048c-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="f048c-365">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f048c-365">What's new</span></span>

- <span data-ttu-id="f048c-366">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="f048c-367">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="f048c-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="f048c-368">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="f048c-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="f048c-369">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="f048c-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f048c-370">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f048c-370">Known Issues</span></span>
<span data-ttu-id="f048c-371">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.18.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="f048c-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="f048c-372">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="f048c-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="f048c-373">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f048c-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="f048c-374">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="f048c-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="f048c-375">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="f048c-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="f048c-376">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f048c-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="f048c-377">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="f048c-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="f048c-378">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="f048c-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="f048c-379">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion in Windows 10-Versionen)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f048c-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="f048c-380">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die verwalteten Supportangebote von Microsoft (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f048c-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="f048c-381">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f048c-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="f048c-382">Plattformversion, die in Windows 10 Versionen enthalten ist</span><span class="sxs-lookup"><span data-stu-id="f048c-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="f048c-383">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10-Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="f048c-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="f048c-384">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="f048c-384">Windows 10 release</span></span>  |<span data-ttu-id="f048c-385">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="f048c-385">Platform version</span></span>  |<span data-ttu-id="f048c-386">Modulversion</span><span class="sxs-lookup"><span data-stu-id="f048c-386">Engine version</span></span> |<span data-ttu-id="f048c-387">Supportphase</span><span class="sxs-lookup"><span data-stu-id="f048c-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="f048c-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="f048c-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="f048c-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="f048c-389">4.18.1909.6</span></span> |<span data-ttu-id="f048c-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="f048c-390">1.1.17000.2</span></span> | <span data-ttu-id="f048c-391">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="f048c-392">1909  (19H2)</span></span> |<span data-ttu-id="f048c-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f048c-393">4.18.1902.5</span></span> |<span data-ttu-id="f048c-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="f048c-394">1.1.16700.3</span></span> | <span data-ttu-id="f048c-395">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="f048c-396">1903  (19H1)</span></span> |<span data-ttu-id="f048c-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f048c-397">4.18.1902.5</span></span> |<span data-ttu-id="f048c-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="f048c-398">1.1.15600.4</span></span> | <span data-ttu-id="f048c-399">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="f048c-400">1809  (RS5)</span></span> |<span data-ttu-id="f048c-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="f048c-401">4.18.1807.18075</span></span> |<span data-ttu-id="f048c-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="f048c-402">1.1.15000.2</span></span> | <span data-ttu-id="f048c-403">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="f048c-404">1803  (RS4)</span></span> |<span data-ttu-id="f048c-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="f048c-405">4.13.17134.1</span></span> |<span data-ttu-id="f048c-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="f048c-406">1.1.14600.4</span></span> | <span data-ttu-id="f048c-407">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="f048c-408">1709  (RS3)</span></span> |<span data-ttu-id="f048c-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="f048c-409">4.12.16299.15</span></span> |<span data-ttu-id="f048c-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="f048c-410">1.1.14104.0</span></span> | <span data-ttu-id="f048c-411">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="f048c-412">1703  (RS2)</span></span> |<span data-ttu-id="f048c-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="f048c-413">4.11.15603.2</span></span> |<span data-ttu-id="f048c-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="f048c-414">1.1.13504.0</span></span> | <span data-ttu-id="f048c-415">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f048c-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="f048c-416">1607 (RS1)</span></span> |<span data-ttu-id="f048c-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="f048c-417">4.10.14393.3683</span></span> |<span data-ttu-id="f048c-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="f048c-418">1.1.12805.0</span></span> | <span data-ttu-id="f048c-419">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f048c-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="f048c-420">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="f048c-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="f048c-421">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="f048c-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="f048c-422">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antiviren- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f048c-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="f048c-423">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="f048c-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="f048c-424">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Installationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="f048c-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="f048c-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="f048c-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="f048c-426">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="f048c-427">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="f048c-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="f048c-428">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f048c-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f048c-429">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-430">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-430">Fixes</span></span>
- <span data-ttu-id="f048c-431">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-432">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-432">Additional information</span></span>
- <span data-ttu-id="f048c-433">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="f048c-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="f048c-435">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="f048c-436">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="f048c-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="f048c-437">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f048c-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f048c-438">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-439">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-439">Fixes</span></span>
- <span data-ttu-id="f048c-440">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-441">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-441">Additional information</span></span>
- <span data-ttu-id="f048c-442">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="f048c-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="f048c-444">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="f048c-445">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="f048c-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="f048c-446">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="f048c-447">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-448">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-448">Fixes</span></span>
- <span data-ttu-id="f048c-449">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-450">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-450">Additional information</span></span>
- <span data-ttu-id="f048c-451">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="f048c-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="f048c-453">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="f048c-454">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="f048c-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="f048c-455">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f048c-456">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-457">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-457">Fixes</span></span>
- <span data-ttu-id="f048c-458">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-459">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-459">Additional information</span></span>
- <span data-ttu-id="f048c-460">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="f048c-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="f048c-462">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="f048c-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="f048c-463">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f048c-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f048c-464">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f048c-465">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-466">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-466">Fixes</span></span>
- <span data-ttu-id="f048c-467">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-468">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-468">Additional information</span></span>
- <span data-ttu-id="f048c-469">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="f048c-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="f048c-471">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="f048c-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="f048c-472">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f048c-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f048c-473">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f048c-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="f048c-474">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-475">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-475">Fixes</span></span>
- <span data-ttu-id="f048c-476">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-477">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-477">Additional information</span></span>
- <span data-ttu-id="f048c-478">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="f048c-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="f048c-480">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="f048c-481">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f048c-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f048c-482">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f048c-483">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-484">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-484">Fixes</span></span>
- <span data-ttu-id="f048c-485">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-486">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-486">Additional information</span></span>
- <span data-ttu-id="f048c-487">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="f048c-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="f048c-489">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="f048c-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="f048c-490">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f048c-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f048c-491">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f048c-492">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-493">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-493">Fixes</span></span>
- <span data-ttu-id="f048c-494">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-495">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-495">Additional information</span></span>
- <span data-ttu-id="f048c-496">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="f048c-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="f048c-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="f048c-498">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f048c-499">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f048c-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="f048c-500">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f048c-501">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-502">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-502">Fixes</span></span>
- <span data-ttu-id="f048c-503">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-504">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-504">Additional information</span></span>
- <span data-ttu-id="f048c-505">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f048c-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="f048c-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="f048c-507">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f048c-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f048c-508">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="f048c-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="f048c-509">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f048c-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="f048c-510">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="f048c-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f048c-511">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f048c-511">Fixes</span></span>
- <span data-ttu-id="f048c-512">Keine</span><span class="sxs-lookup"><span data-stu-id="f048c-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f048c-513">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f048c-513">Additional information</span></span>
- <span data-ttu-id="f048c-514">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f048c-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="f048c-515">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f048c-515">Additional resources</span></span>

| <span data-ttu-id="f048c-516">Artikel</span><span class="sxs-lookup"><span data-stu-id="f048c-516">Article</span></span> | <span data-ttu-id="f048c-517">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f048c-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="f048c-518">Microsoft Defender-Update für Windows Installationsimages des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="f048c-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="f048c-519">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="f048c-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="f048c-520">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="f048c-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="f048c-521">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="f048c-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f048c-522">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f048c-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="f048c-523">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="f048c-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="f048c-524">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f048c-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="f048c-525">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="f048c-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="f048c-526">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="f048c-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="f048c-527">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="f048c-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f048c-528">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f048c-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="f048c-529">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="f048c-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="f048c-530">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="f048c-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
