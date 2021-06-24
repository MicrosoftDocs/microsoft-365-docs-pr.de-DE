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
ms.date: 06/23/2021
ms.openlocfilehash: 88be32a2c1e9204629682ec678f80ab6daf701f4
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105332"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="f7f82-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="f7f82-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="f7f82-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7f82-105">**Applies to:**</span></span>

- [<span data-ttu-id="f7f82-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7f82-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="f7f82-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f7f82-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f7f82-108">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f7f82-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="f7f82-109">Aktualisieren Sie den Virenschutz, auch wenn Microsoft Defender Antivirus im [passiven Modus](microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7f82-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="f7f82-110">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="f7f82-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="f7f82-111">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="f7f82-111">Security intelligence updates</span></span>
- <span data-ttu-id="f7f82-112">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="f7f82-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="f7f82-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates) von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7f82-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="f7f82-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="f7f82-114">Security intelligence updates</span></span>

<span data-ttu-id="f7f82-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f7f82-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f82-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f7f82-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="f7f82-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="f7f82-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="f7f82-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="f7f82-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="f7f82-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f7f82-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="f7f82-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="f7f82-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="f7f82-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f7f82-122">Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware von Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f7f82-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="f7f82-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f7f82-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="f7f82-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="f7f82-124">Product updates</span></span>

<span data-ttu-id="f7f82-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="f7f82-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="f7f82-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="f7f82-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="f7f82-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="f7f82-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="f7f82-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f7f82-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="f7f82-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="f7f82-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="f7f82-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="f7f82-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="f7f82-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f7f82-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="f7f82-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="f7f82-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="f7f82-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="f7f82-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="f7f82-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="f7f82-134">All our updates contain</span></span> 
- <span data-ttu-id="f7f82-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="f7f82-135">performance improvements;</span></span>
- <span data-ttu-id="f7f82-136">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="f7f82-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="f7f82-137">Integrationsverbesserungen (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="f7f82-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="f7f82-138">Mai-2021 (Plattform: 4.18.2105.4 | Modul: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="f7f82-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="f7f82-139">&ensp;Security Intelligence Update-Version: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="f7f82-140">&ensp;Veröffentlicht: **3. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="f7f82-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="f7f82-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="f7f82-142">&ensp;Modul: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="f7f82-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f7f82-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-144">What's new</span></span>
- <span data-ttu-id="f7f82-145">Verbesserungen bei der [Verhaltensüberwachung](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="f7f82-146">Benachrichtigungsfilterungsfeature für den Fixed [Network-Schutz](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-147">Known Issues</span></span>
<span data-ttu-id="f7f82-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-149">April -2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="f7f82-150">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="f7f82-151">&ensp;Veröffentlicht: **26. April 2021**  (Modul: 1.1.18100.6 veröffentlicht am 5. Mai 2021) &ensp; Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="f7f82-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="f7f82-152">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="f7f82-153">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f7f82-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-154">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-154">What's new</span></span>
- <span data-ttu-id="f7f82-155">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="f7f82-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="f7f82-156">Verbesserte Kernelmodus-Keyloggererkennung</span><span class="sxs-lookup"><span data-stu-id="f7f82-156">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="f7f82-157">Neue Steuerelemente zum Verwalten des schrittweisen Rollouts für [Microsoft Defender-Updates hinzugefügt](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-157">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="f7f82-158">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-158">Known Issues</span></span>
<span data-ttu-id="f7f82-159">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-160">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="f7f82-161">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="f7f82-162">&ensp;Veröffentlicht: **2. April 2021**</span><span class="sxs-lookup"><span data-stu-id="f7f82-162">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="f7f82-163">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="f7f82-164">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="f7f82-165">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="f7f82-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-166">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-166">What's new</span></span>

- <span data-ttu-id="f7f82-167">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="f7f82-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="f7f82-168">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="f7f82-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="f7f82-169">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="f7f82-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-170">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-170">Known Issues</span></span>
<span data-ttu-id="f7f82-171">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="f7f82-172">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="f7f82-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="f7f82-173">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="f7f82-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="f7f82-174">Ältere Versionen als die in diesem Abschnitt aufgeführten versionen werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7f82-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="f7f82-175">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="f7f82-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="f7f82-176">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="f7f82-177">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="f7f82-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="f7f82-178">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="f7f82-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="f7f82-179">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="f7f82-180">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-181">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-181">What's new</span></span>

- <span data-ttu-id="f7f82-182">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="f7f82-183">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="f7f82-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-184">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-184">Known Issues</span></span>
<span data-ttu-id="f7f82-185">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-186">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="f7f82-187">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f7f82-188">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="f7f82-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="f7f82-189">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="f7f82-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="f7f82-190">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="f7f82-191">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-192">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-192">What's new</span></span>

- <span data-ttu-id="f7f82-193">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="f7f82-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="f7f82-194">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="f7f82-195">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="f7f82-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="f7f82-196">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="f7f82-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="f7f82-197">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="f7f82-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-198">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-198">Known Issues</span></span>
<span data-ttu-id="f7f82-199">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-200">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="f7f82-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="f7f82-201">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f7f82-202">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="f7f82-203">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="f7f82-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="f7f82-204">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="f7f82-205">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-206">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-206">What's new</span></span>

- <span data-ttu-id="f7f82-207">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="f7f82-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-208">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-208">Known Issues</span></span>
<span data-ttu-id="f7f82-209">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-210">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="f7f82-211">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="f7f82-212">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="f7f82-213">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="f7f82-214">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="f7f82-215">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-216">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-216">What's new</span></span>

- <span data-ttu-id="f7f82-217">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="f7f82-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="f7f82-218">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="f7f82-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="f7f82-219">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f7f82-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="f7f82-220">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="f7f82-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-221">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-221">Known Issues</span></span>

<span data-ttu-id="f7f82-222">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f7f82-223">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="f7f82-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="f7f82-224">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="f7f82-225">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="f7f82-226">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="f7f82-227">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="f7f82-228">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-229">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-229">What's new</span></span>

- <span data-ttu-id="f7f82-230">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7f82-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="f7f82-231">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="f7f82-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="f7f82-232">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="f7f82-233">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="f7f82-233">New management interfaces for:</span></span>
   - <span data-ttu-id="f7f82-234">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="f7f82-234">UDP Inspection</span></span>
   - <span data-ttu-id="f7f82-235">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="f7f82-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="f7f82-236">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="f7f82-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="f7f82-237">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="f7f82-238">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f7f82-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-239">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-239">Known Issues</span></span>

<span data-ttu-id="f7f82-240">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="f7f82-241">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="f7f82-242">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="f7f82-243">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="f7f82-244">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="f7f82-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="f7f82-245">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="f7f82-246">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="f7f82-247">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-247">What's new</span></span>

- <span data-ttu-id="f7f82-248">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="f7f82-248">Add more telemetry events</span></span>
- <span data-ttu-id="f7f82-249">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="f7f82-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="f7f82-250">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="f7f82-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="f7f82-251">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="f7f82-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="f7f82-252">`AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f7f82-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="f7f82-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f7f82-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="f7f82-254">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f7f82-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="f7f82-255">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-255">Known Issues</span></span>
<span data-ttu-id="f7f82-256">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-257">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="f7f82-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="f7f82-258">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="f7f82-259">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="f7f82-260">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="f7f82-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="f7f82-261">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="f7f82-262">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-263">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-263">What's new</span></span>

- <span data-ttu-id="f7f82-264">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="f7f82-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="f7f82-265">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f7f82-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-266">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-266">Known Issues</span></span>
<span data-ttu-id="f7f82-267">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-268">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="f7f82-269">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="f7f82-270">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="f7f82-271">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="f7f82-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="f7f82-272">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="f7f82-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="f7f82-273">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-274">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-274">What's new</span></span>

- <span data-ttu-id="f7f82-275">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="f7f82-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="f7f82-276">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="f7f82-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="f7f82-277">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="f7f82-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="f7f82-278">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="f7f82-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="f7f82-279">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="f7f82-279">Fixed registry query</span></span> 
- <span data-ttu-id="f7f82-280">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-281">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-281">Known Issues</span></span>
<span data-ttu-id="f7f82-282">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-283">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="f7f82-284">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="f7f82-285">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="f7f82-286">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="f7f82-287">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="f7f82-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="f7f82-288">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-289">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-289">What's new</span></span>

- <span data-ttu-id="f7f82-290">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="f7f82-290">Improved logging for scan events</span></span>
- <span data-ttu-id="f7f82-291">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="f7f82-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="f7f82-292">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f7f82-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="f7f82-293">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="f7f82-294">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="f7f82-295">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="f7f82-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-296">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-296">Known Issues</span></span>
<span data-ttu-id="f7f82-297">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-298">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="f7f82-299">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="f7f82-300">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="f7f82-301">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="f7f82-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="f7f82-302">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="f7f82-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="f7f82-303">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-304">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-304">What's new</span></span>
- <span data-ttu-id="f7f82-305">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-305">WDfilter improvements</span></span>
- <span data-ttu-id="f7f82-306">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="f7f82-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="f7f82-307">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="f7f82-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="f7f82-308">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="f7f82-309">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f7f82-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="f7f82-310">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="f7f82-310">UEFI scan capability</span></span>
- <span data-ttu-id="f7f82-311">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="f7f82-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="f7f82-312">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-312">Known Issues</span></span>
<span data-ttu-id="f7f82-313">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-314">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="f7f82-315">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="f7f82-316">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="f7f82-317">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="f7f82-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="f7f82-318">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="f7f82-319">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f7f82-320">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-320">What's new</span></span>

- <span data-ttu-id="f7f82-321">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f7f82-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="f7f82-322">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="f7f82-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="f7f82-323">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="f7f82-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="f7f82-324">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="f7f82-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="f7f82-325">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="f7f82-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f7f82-326">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-326">Known Issues</span></span>
<span data-ttu-id="f7f82-327">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="f7f82-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="f7f82-328">Februar-2020 (Plattform: – | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="f7f82-329">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="f7f82-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="f7f82-330">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="f7f82-331">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="f7f82-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="f7f82-332">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="f7f82-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="f7f82-333">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f7f82-334">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="f7f82-335">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-335">Known Issues</span></span>
<span data-ttu-id="f7f82-336">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-337">Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="f7f82-338">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="f7f82-339">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="f7f82-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="f7f82-340">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="f7f82-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="f7f82-341">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="f7f82-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="f7f82-342">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="f7f82-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f7f82-343">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-343">What's new</span></span>

- <span data-ttu-id="f7f82-344">BSOD in WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="f7f82-345">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="f7f82-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="f7f82-346">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="f7f82-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="f7f82-347">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f7f82-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="f7f82-348">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="f7f82-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f7f82-349">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-349">Known Issues</span></span>

<span data-ttu-id="f7f82-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span><span class="sxs-lookup"><span data-stu-id="f7f82-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="f7f82-351">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="f7f82-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="f7f82-352">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="f7f82-352">This update is:</span></span>
> - <span data-ttu-id="f7f82-353">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="f7f82-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="f7f82-354">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="f7f82-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="f7f82-355">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="f7f82-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="f7f82-356">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="f7f82-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="f7f82-357">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="f7f82-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f7f82-358">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="f7f82-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="f7f82-359">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="f7f82-360">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="f7f82-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="f7f82-361">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="f7f82-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="f7f82-362">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="f7f82-363">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="f7f82-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="f7f82-364">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-364">What's new</span></span>

- <span data-ttu-id="f7f82-365">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="f7f82-366">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="f7f82-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="f7f82-367">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="f7f82-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="f7f82-368">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="f7f82-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f7f82-369">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="f7f82-369">Known Issues</span></span>
<span data-ttu-id="f7f82-370">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.18.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="f7f82-370">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="f7f82-371">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="f7f82-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="f7f82-372">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7f82-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="f7f82-373">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="f7f82-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="f7f82-374">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="f7f82-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="f7f82-375">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7f82-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="f7f82-376">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="f7f82-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="f7f82-377">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="f7f82-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="f7f82-378">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion in Windows 10-Versionen)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7f82-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="f7f82-379">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Support-Vorfälle über den Microsoft-Kundendienst & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f7f82-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="f7f82-380">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7f82-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="f7f82-381">Plattformversion, die in Windows 10 Versionen enthalten ist</span><span class="sxs-lookup"><span data-stu-id="f7f82-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="f7f82-382">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10 Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="f7f82-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="f7f82-383">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="f7f82-383">Windows 10 release</span></span>  |<span data-ttu-id="f7f82-384">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="f7f82-384">Platform version</span></span>  |<span data-ttu-id="f7f82-385">Modulversion</span><span class="sxs-lookup"><span data-stu-id="f7f82-385">Engine version</span></span> |<span data-ttu-id="f7f82-386">Supportphase</span><span class="sxs-lookup"><span data-stu-id="f7f82-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="f7f82-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="f7f82-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="f7f82-388">4.18.1909.6</span></span> |<span data-ttu-id="f7f82-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="f7f82-389">1.1.17000.2</span></span> | <span data-ttu-id="f7f82-390">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-391">1909  (19H2)</span></span> |<span data-ttu-id="f7f82-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f7f82-392">4.18.1902.5</span></span> |<span data-ttu-id="f7f82-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="f7f82-393">1.1.16700.3</span></span> | <span data-ttu-id="f7f82-394">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="f7f82-395">1903  (19H1)</span></span> |<span data-ttu-id="f7f82-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f7f82-396">4.18.1902.5</span></span> |<span data-ttu-id="f7f82-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="f7f82-397">1.1.15600.4</span></span> | <span data-ttu-id="f7f82-398">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="f7f82-399">1809  (RS5)</span></span> |<span data-ttu-id="f7f82-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="f7f82-400">4.18.1807.18075</span></span> |<span data-ttu-id="f7f82-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="f7f82-401">1.1.15000.2</span></span> | <span data-ttu-id="f7f82-402">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="f7f82-403">1803  (RS4)</span></span> |<span data-ttu-id="f7f82-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="f7f82-404">4.13.17134.1</span></span> |<span data-ttu-id="f7f82-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="f7f82-405">1.1.14600.4</span></span> | <span data-ttu-id="f7f82-406">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="f7f82-407">1709  (RS3)</span></span> |<span data-ttu-id="f7f82-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="f7f82-408">4.12.16299.15</span></span> |<span data-ttu-id="f7f82-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="f7f82-409">1.1.14104.0</span></span> | <span data-ttu-id="f7f82-410">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="f7f82-411">1703  (RS2)</span></span> |<span data-ttu-id="f7f82-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="f7f82-412">4.11.15603.2</span></span> |<span data-ttu-id="f7f82-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="f7f82-413">1.1.13504.0</span></span> | <span data-ttu-id="f7f82-414">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f7f82-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="f7f82-415">1607 (RS1)</span></span> |<span data-ttu-id="f7f82-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="f7f82-416">4.10.14393.3683</span></span> |<span data-ttu-id="f7f82-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="f7f82-417">1.1.12805.0</span></span> | <span data-ttu-id="f7f82-418">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="f7f82-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="f7f82-419">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="f7f82-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="f7f82-420">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="f7f82-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="f7f82-421">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antiviren- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7f82-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="f7f82-422">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="f7f82-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="f7f82-423">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Installationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="f7f82-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="f7f82-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="f7f82-425">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="f7f82-426">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="f7f82-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="f7f82-427">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f7f82-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f7f82-428">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-429">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-429">Fixes</span></span>
- <span data-ttu-id="f7f82-430">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-431">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-431">Additional information</span></span>
- <span data-ttu-id="f7f82-432">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="f7f82-434">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="f7f82-435">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="f7f82-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="f7f82-436">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="f7f82-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="f7f82-437">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-438">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-438">Fixes</span></span>
- <span data-ttu-id="f7f82-439">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-440">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-440">Additional information</span></span>
- <span data-ttu-id="f7f82-441">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="f7f82-443">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="f7f82-444">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="f7f82-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="f7f82-445">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="f7f82-446">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-447">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-447">Fixes</span></span>
- <span data-ttu-id="f7f82-448">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-449">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-449">Additional information</span></span>
- <span data-ttu-id="f7f82-450">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="f7f82-452">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="f7f82-453">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="f7f82-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="f7f82-454">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f7f82-455">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-456">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-456">Fixes</span></span>
- <span data-ttu-id="f7f82-457">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-458">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-458">Additional information</span></span>
- <span data-ttu-id="f7f82-459">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="f7f82-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="f7f82-461">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="f7f82-462">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f7f82-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f7f82-463">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f7f82-464">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-465">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-465">Fixes</span></span>
- <span data-ttu-id="f7f82-466">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-467">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-467">Additional information</span></span>
- <span data-ttu-id="f7f82-468">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="f7f82-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="f7f82-470">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="f7f82-471">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f7f82-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f7f82-472">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f7f82-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="f7f82-473">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-474">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-474">Fixes</span></span>
- <span data-ttu-id="f7f82-475">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-476">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-476">Additional information</span></span>
- <span data-ttu-id="f7f82-477">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="f7f82-479">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="f7f82-480">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f7f82-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f7f82-481">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f7f82-482">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-483">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-483">Fixes</span></span>
- <span data-ttu-id="f7f82-484">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-485">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-485">Additional information</span></span>
- <span data-ttu-id="f7f82-486">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="f7f82-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="f7f82-488">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="f7f82-489">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f7f82-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f7f82-490">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f7f82-491">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-492">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-492">Fixes</span></span>
- <span data-ttu-id="f7f82-493">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-494">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-494">Additional information</span></span>
- <span data-ttu-id="f7f82-495">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="f7f82-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="f7f82-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="f7f82-497">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f7f82-498">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f7f82-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="f7f82-499">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f7f82-500">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-501">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-501">Fixes</span></span>
- <span data-ttu-id="f7f82-502">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-503">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-503">Additional information</span></span>
- <span data-ttu-id="f7f82-504">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f7f82-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="f7f82-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="f7f82-506">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f7f82-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f7f82-507">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="f7f82-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="f7f82-508">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f7f82-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="f7f82-509">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="f7f82-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f7f82-510">Behebungen</span><span class="sxs-lookup"><span data-stu-id="f7f82-510">Fixes</span></span>
- <span data-ttu-id="f7f82-511">Keine</span><span class="sxs-lookup"><span data-stu-id="f7f82-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f7f82-512">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f82-512">Additional information</span></span>
- <span data-ttu-id="f7f82-513">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7f82-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="f7f82-514">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f7f82-514">Additional resources</span></span>

| <span data-ttu-id="f7f82-515">Artikel</span><span class="sxs-lookup"><span data-stu-id="f7f82-515">Article</span></span> | <span data-ttu-id="f7f82-516">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7f82-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="f7f82-517">Microsoft Defender-Update für Windows Betriebssysteminstallationsimages</span><span class="sxs-lookup"><span data-stu-id="f7f82-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="f7f82-518">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="f7f82-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="f7f82-519">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="f7f82-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="f7f82-520">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="f7f82-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f7f82-521">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f7f82-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="f7f82-522">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="f7f82-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="f7f82-523">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7f82-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="f7f82-524">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="f7f82-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="f7f82-525">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="f7f82-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="f7f82-526">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="f7f82-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f7f82-527">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f7f82-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="f7f82-528">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="f7f82-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="f7f82-529">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="f7f82-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
