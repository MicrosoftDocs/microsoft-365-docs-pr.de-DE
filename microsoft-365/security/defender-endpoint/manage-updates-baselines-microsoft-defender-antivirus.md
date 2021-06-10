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
ms.date: 06/09/2021
ms.openlocfilehash: 05b2b2af87e423058d18651571d52a97ac387506
ms.sourcegitcommit: 3584c1fe59d12512d67faf3efc955e1d67e2baa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862147"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="aa709-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="aa709-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="aa709-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="aa709-105">**Applies to:**</span></span>

- [<span data-ttu-id="aa709-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="aa709-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="aa709-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="aa709-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="aa709-108">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="aa709-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="aa709-109">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="aa709-109">Security intelligence updates</span></span>
- <span data-ttu-id="aa709-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="aa709-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa709-111">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="aa709-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="aa709-112">Aktualisieren Sie den Virenschutz auch dann, wenn Microsoft Defender Antivirus im [passiven Modus](./microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aa709-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="aa709-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aa709-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="aa709-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="aa709-114">Security intelligence updates</span></span>

<span data-ttu-id="aa709-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aa709-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="aa709-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="aa709-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="aa709-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="aa709-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="aa709-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="aa709-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="aa709-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="aa709-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="aa709-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="aa709-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="aa709-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="aa709-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="aa709-122">Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="aa709-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="aa709-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aa709-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="aa709-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="aa709-124">Product updates</span></span>

<span data-ttu-id="aa709-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="aa709-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="aa709-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="aa709-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="aa709-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="aa709-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="aa709-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aa709-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="aa709-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="aa709-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="aa709-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="aa709-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="aa709-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aa709-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="aa709-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="aa709-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="aa709-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="aa709-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="aa709-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="aa709-134">All our updates contain</span></span> 
- <span data-ttu-id="aa709-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="aa709-135">performance improvements;</span></span>
- <span data-ttu-id="aa709-136">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="aa709-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="aa709-137">Integrationsverbesserungen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="aa709-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="aa709-138">Mai-2021 (Plattform: 4.18.2105.4 | Modul: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="aa709-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="aa709-139">&ensp;Security Intelligence Update-Version: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="aa709-140">&ensp;Veröffentlicht: **3. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="aa709-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="aa709-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="aa709-142">&ensp;Modul: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="aa709-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="aa709-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-144">What's new</span></span>
- <span data-ttu-id="aa709-145">Verbesserungen bei der [Verhaltensüberwachung](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="aa709-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="aa709-146">Benachrichtigungsfilterungsfeature für den Fixed [Network-Schutz](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="aa709-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-147">Known Issues</span></span>
<span data-ttu-id="aa709-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-149">April-2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="aa709-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="aa709-150">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="aa709-151">&ensp;Veröffentlicht: **26. April 2021**  (Modul: 1.1.18100.6 veröffentlicht am 5. Mai 2021) &ensp; Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="aa709-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="aa709-152">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="aa709-153">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="aa709-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-154">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-154">What's new</span></span>
- <span data-ttu-id="aa709-155">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="aa709-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="aa709-156">Verbesserte Kernelmodus-Keyloggererkennung</span><span class="sxs-lookup"><span data-stu-id="aa709-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-157">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-157">Known Issues</span></span>
<span data-ttu-id="aa709-158">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-159">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="aa709-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="aa709-160">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="aa709-161">&ensp;Veröffentlicht: **2. April 2021**</span><span class="sxs-lookup"><span data-stu-id="aa709-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="aa709-162">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="aa709-163">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="aa709-164">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="aa709-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-165">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-165">What's new</span></span>

- <span data-ttu-id="aa709-166">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="aa709-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="aa709-167">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="aa709-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="aa709-168">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="aa709-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-169">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-169">Known Issues</span></span>
<span data-ttu-id="aa709-170">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="aa709-171">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="aa709-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="aa709-172">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="aa709-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="aa709-173">Ältere Versionen sind in diesem Abschnitt aufgeführt und werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aa709-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="aa709-174">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="aa709-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="aa709-175">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="aa709-176">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="aa709-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="aa709-177">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="aa709-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="aa709-178">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="aa709-179">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-180">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-180">What's new</span></span>

- <span data-ttu-id="aa709-181">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="aa709-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="aa709-182">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="aa709-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-183">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-183">Known Issues</span></span>
<span data-ttu-id="aa709-184">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-185">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="aa709-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="aa709-186">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="aa709-187">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="aa709-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="aa709-188">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="aa709-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="aa709-189">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa709-190">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-191">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-191">What's new</span></span>

- <span data-ttu-id="aa709-192">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="aa709-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="aa709-193">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="aa709-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="aa709-194">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="aa709-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="aa709-195">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="aa709-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="aa709-196">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="aa709-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-197">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-197">Known Issues</span></span>
<span data-ttu-id="aa709-198">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-199">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="aa709-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="aa709-200">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="aa709-201">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="aa709-202">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="aa709-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="aa709-203">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="aa709-204">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-205">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-205">What's new</span></span>

- <span data-ttu-id="aa709-206">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="aa709-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-207">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-207">Known Issues</span></span>
<span data-ttu-id="aa709-208">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-209">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="aa709-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="aa709-210">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="aa709-211">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="aa709-212">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="aa709-213">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa709-214">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-215">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-215">What's new</span></span>

- <span data-ttu-id="aa709-216">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="aa709-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="aa709-217">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="aa709-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="aa709-218">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="aa709-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="aa709-219">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="aa709-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-220">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-220">Known Issues</span></span>

<span data-ttu-id="aa709-221">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa709-222">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="aa709-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="aa709-223">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="aa709-224">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="aa709-225">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="aa709-226">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="aa709-227">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-228">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-228">What's new</span></span>

- <span data-ttu-id="aa709-229">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aa709-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="aa709-230">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="aa709-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="aa709-231">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="aa709-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="aa709-232">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="aa709-232">New management interfaces for:</span></span>
   - <span data-ttu-id="aa709-233">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="aa709-233">UDP Inspection</span></span>
   - <span data-ttu-id="aa709-234">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="aa709-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="aa709-235">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="aa709-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="aa709-236">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="aa709-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="aa709-237">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="aa709-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-238">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-238">Known Issues</span></span>

<span data-ttu-id="aa709-239">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="aa709-240">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="aa709-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="aa709-241">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="aa709-242">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="aa709-243">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="aa709-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="aa709-244">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="aa709-245">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="aa709-246">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-246">What's new</span></span>

- <span data-ttu-id="aa709-247">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="aa709-247">Add more telemetry events</span></span>
- <span data-ttu-id="aa709-248">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="aa709-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="aa709-249">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="aa709-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="aa709-250">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="aa709-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="aa709-251">`AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="aa709-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="aa709-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="aa709-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="aa709-253">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="aa709-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="aa709-254">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-254">Known Issues</span></span>
<span data-ttu-id="aa709-255">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-256">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="aa709-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="aa709-257">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="aa709-258">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="aa709-259">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="aa709-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="aa709-260">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="aa709-261">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-262">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-262">What's new</span></span>

- <span data-ttu-id="aa709-263">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="aa709-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="aa709-264">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="aa709-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-265">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-265">Known Issues</span></span>
<span data-ttu-id="aa709-266">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-267">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="aa709-268">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="aa709-269">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="aa709-270">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="aa709-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="aa709-271">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="aa709-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="aa709-272">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-273">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-273">What's new</span></span>

- <span data-ttu-id="aa709-274">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="aa709-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="aa709-275">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="aa709-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="aa709-276">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="aa709-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="aa709-277">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="aa709-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="aa709-278">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="aa709-278">Fixed registry query</span></span> 
- <span data-ttu-id="aa709-279">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-280">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-280">Known Issues</span></span>
<span data-ttu-id="aa709-281">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-282">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="aa709-283">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="aa709-284">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="aa709-285">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="aa709-286">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="aa709-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="aa709-287">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-288">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-288">What's new</span></span>

- <span data-ttu-id="aa709-289">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="aa709-289">Improved logging for scan events</span></span>
- <span data-ttu-id="aa709-290">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="aa709-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="aa709-291">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="aa709-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="aa709-292">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="aa709-293">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="aa709-294">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="aa709-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-295">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-295">Known Issues</span></span>
<span data-ttu-id="aa709-296">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-297">April -2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="aa709-298">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="aa709-299">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="aa709-300">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="aa709-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="aa709-301">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="aa709-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="aa709-302">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-303">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-303">What's new</span></span>
- <span data-ttu-id="aa709-304">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="aa709-304">WDfilter improvements</span></span>
- <span data-ttu-id="aa709-305">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="aa709-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="aa709-306">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="aa709-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="aa709-307">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="aa709-308">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="aa709-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="aa709-309">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="aa709-309">UEFI scan capability</span></span>
- <span data-ttu-id="aa709-310">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="aa709-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa709-311">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-311">Known Issues</span></span>
<span data-ttu-id="aa709-312">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-313">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="aa709-314">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="aa709-315">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="aa709-316">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="aa709-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="aa709-317">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="aa709-318">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa709-319">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-319">What's new</span></span>

- <span data-ttu-id="aa709-320">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="aa709-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="aa709-321">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="aa709-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="aa709-322">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="aa709-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="aa709-323">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="aa709-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="aa709-324">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="aa709-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa709-325">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-325">Known Issues</span></span>
<span data-ttu-id="aa709-326">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="aa709-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="aa709-327">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="aa709-328">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="aa709-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="aa709-329">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="aa709-330">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="aa709-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="aa709-331">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="aa709-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="aa709-332">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="aa709-333">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="aa709-334">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-334">Known Issues</span></span>
<span data-ttu-id="aa709-335">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-336">Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="aa709-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="aa709-337">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="aa709-338">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="aa709-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="aa709-339">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="aa709-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="aa709-340">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="aa709-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="aa709-341">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="aa709-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="aa709-342">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-342">What's new</span></span>

- <span data-ttu-id="aa709-343">BSOD in WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="aa709-344">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="aa709-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="aa709-345">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="aa709-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="aa709-346">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="aa709-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="aa709-347">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="aa709-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa709-348">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-348">Known Issues</span></span>

<span data-ttu-id="aa709-349">[**Fixed**] Devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span><span class="sxs-lookup"><span data-stu-id="aa709-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="aa709-350">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="aa709-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="aa709-351">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="aa709-351">This update is:</span></span>
> - <span data-ttu-id="aa709-352">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="aa709-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="aa709-353">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="aa709-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="aa709-354">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="aa709-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="aa709-355">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="aa709-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="aa709-356">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="aa709-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa709-357">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="aa709-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="aa709-358">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="aa709-359">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="aa709-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="aa709-360">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="aa709-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="aa709-361">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="aa709-362">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="aa709-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="aa709-363">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="aa709-363">What's new</span></span>

- <span data-ttu-id="aa709-364">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="aa709-365">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="aa709-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="aa709-366">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="aa709-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="aa709-367">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="aa709-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa709-368">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="aa709-368">Known Issues</span></span>
<span data-ttu-id="aa709-369">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.18.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="aa709-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="aa709-370">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="aa709-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="aa709-371">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aa709-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="aa709-372">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="aa709-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="aa709-373">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="aa709-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="aa709-374">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aa709-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="aa709-375">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="aa709-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="aa709-376">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="aa709-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="aa709-377">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion in Windows 10-Versionen)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aa709-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="aa709-378">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die verwalteten Supportangebote von Microsoft (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aa709-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="aa709-379">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="aa709-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="aa709-380">Plattformversion, die in Windows 10 Versionen enthalten ist</span><span class="sxs-lookup"><span data-stu-id="aa709-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="aa709-381">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10-Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="aa709-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="aa709-382">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="aa709-382">Windows 10 release</span></span>  |<span data-ttu-id="aa709-383">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="aa709-383">Platform version</span></span>  |<span data-ttu-id="aa709-384">Modulversion</span><span class="sxs-lookup"><span data-stu-id="aa709-384">Engine version</span></span> |<span data-ttu-id="aa709-385">Supportphase</span><span class="sxs-lookup"><span data-stu-id="aa709-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="aa709-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="aa709-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="aa709-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="aa709-387">4.18.1909.6</span></span> |<span data-ttu-id="aa709-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="aa709-388">1.1.17000.2</span></span> | <span data-ttu-id="aa709-389">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="aa709-390">1909  (19H2)</span></span> |<span data-ttu-id="aa709-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="aa709-391">4.18.1902.5</span></span> |<span data-ttu-id="aa709-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="aa709-392">1.1.16700.3</span></span> | <span data-ttu-id="aa709-393">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="aa709-394">1903  (19H1)</span></span> |<span data-ttu-id="aa709-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="aa709-395">4.18.1902.5</span></span> |<span data-ttu-id="aa709-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="aa709-396">1.1.15600.4</span></span> | <span data-ttu-id="aa709-397">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="aa709-398">1809  (RS5)</span></span> |<span data-ttu-id="aa709-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="aa709-399">4.18.1807.18075</span></span> |<span data-ttu-id="aa709-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="aa709-400">1.1.15000.2</span></span> | <span data-ttu-id="aa709-401">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="aa709-402">1803  (RS4)</span></span> |<span data-ttu-id="aa709-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="aa709-403">4.13.17134.1</span></span> |<span data-ttu-id="aa709-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="aa709-404">1.1.14600.4</span></span> | <span data-ttu-id="aa709-405">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="aa709-406">1709  (RS3)</span></span> |<span data-ttu-id="aa709-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="aa709-407">4.12.16299.15</span></span> |<span data-ttu-id="aa709-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="aa709-408">1.1.14104.0</span></span> | <span data-ttu-id="aa709-409">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="aa709-410">1703  (RS2)</span></span> |<span data-ttu-id="aa709-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="aa709-411">4.11.15603.2</span></span> |<span data-ttu-id="aa709-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="aa709-412">1.1.13504.0</span></span> | <span data-ttu-id="aa709-413">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa709-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="aa709-414">1607 (RS1)</span></span> |<span data-ttu-id="aa709-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="aa709-415">4.10.14393.3683</span></span> |<span data-ttu-id="aa709-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="aa709-416">1.1.12805.0</span></span> | <span data-ttu-id="aa709-417">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="aa709-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="aa709-418">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="aa709-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="aa709-419">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="aa709-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="aa709-420">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antiviren- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="aa709-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="aa709-421">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="aa709-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="aa709-422">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Betriebssysteminstallationsimages.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="aa709-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="aa709-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="aa709-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="aa709-424">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="aa709-425">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="aa709-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="aa709-426">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="aa709-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="aa709-427">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-428">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-428">Fixes</span></span>
- <span data-ttu-id="aa709-429">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-430">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-430">Additional information</span></span>
- <span data-ttu-id="aa709-431">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="aa709-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="aa709-433">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="aa709-434">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="aa709-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="aa709-435">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="aa709-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="aa709-436">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-437">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-437">Fixes</span></span>
- <span data-ttu-id="aa709-438">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-439">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-439">Additional information</span></span>
- <span data-ttu-id="aa709-440">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="aa709-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="aa709-442">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="aa709-443">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="aa709-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="aa709-444">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="aa709-445">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-446">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-446">Fixes</span></span>
- <span data-ttu-id="aa709-447">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-448">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-448">Additional information</span></span>
- <span data-ttu-id="aa709-449">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="aa709-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="aa709-451">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="aa709-452">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="aa709-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="aa709-453">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa709-454">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-455">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-455">Fixes</span></span>
- <span data-ttu-id="aa709-456">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-457">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-457">Additional information</span></span>
- <span data-ttu-id="aa709-458">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="aa709-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="aa709-460">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="aa709-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="aa709-461">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="aa709-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="aa709-462">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa709-463">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-464">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-464">Fixes</span></span>
- <span data-ttu-id="aa709-465">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-466">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-466">Additional information</span></span>
- <span data-ttu-id="aa709-467">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="aa709-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="aa709-469">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="aa709-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="aa709-470">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="aa709-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="aa709-471">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="aa709-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="aa709-472">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-473">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-473">Fixes</span></span>
- <span data-ttu-id="aa709-474">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-475">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-475">Additional information</span></span>
- <span data-ttu-id="aa709-476">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="aa709-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="aa709-478">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="aa709-479">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="aa709-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="aa709-480">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa709-481">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-482">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-482">Fixes</span></span>
- <span data-ttu-id="aa709-483">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-484">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-484">Additional information</span></span>
- <span data-ttu-id="aa709-485">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="aa709-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="aa709-487">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="aa709-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="aa709-488">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="aa709-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="aa709-489">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa709-490">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-491">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-491">Fixes</span></span>
- <span data-ttu-id="aa709-492">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-493">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-493">Additional information</span></span>
- <span data-ttu-id="aa709-494">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="aa709-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="aa709-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="aa709-496">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="aa709-497">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="aa709-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="aa709-498">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa709-499">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-500">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-500">Fixes</span></span>
- <span data-ttu-id="aa709-501">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-502">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-502">Additional information</span></span>
- <span data-ttu-id="aa709-503">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa709-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="aa709-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="aa709-505">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="aa709-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="aa709-506">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="aa709-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="aa709-507">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="aa709-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="aa709-508">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="aa709-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa709-509">Behebungen</span><span class="sxs-lookup"><span data-stu-id="aa709-509">Fixes</span></span>
- <span data-ttu-id="aa709-510">Keine</span><span class="sxs-lookup"><span data-stu-id="aa709-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa709-511">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa709-511">Additional information</span></span>
- <span data-ttu-id="aa709-512">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aa709-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="aa709-513">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="aa709-513">Additional resources</span></span>

| <span data-ttu-id="aa709-514">Artikel</span><span class="sxs-lookup"><span data-stu-id="aa709-514">Article</span></span> | <span data-ttu-id="aa709-515">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa709-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="aa709-516">Microsoft Defender-Update für Windows Installationsimages des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="aa709-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="aa709-517">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="aa709-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="aa709-518">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="aa709-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="aa709-519">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="aa709-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="aa709-520">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa709-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="aa709-521">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="aa709-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="aa709-522">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa709-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="aa709-523">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="aa709-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="aa709-524">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="aa709-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="aa709-525">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="aa709-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="aa709-526">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="aa709-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="aa709-527">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="aa709-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="aa709-528">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="aa709-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
