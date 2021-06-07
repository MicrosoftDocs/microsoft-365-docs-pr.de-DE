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
ms.date: 06/04/2021
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795982"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="1ddbc-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="1ddbc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-105">**Applies to:**</span></span>

- [<span data-ttu-id="1ddbc-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="1ddbc-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1ddbc-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="1ddbc-108">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="1ddbc-109">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-109">Security intelligence updates</span></span>
- <span data-ttu-id="1ddbc-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ddbc-111">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="1ddbc-112">Aktualisieren Sie den Virenschutz auch dann, wenn Microsoft Defender Antivirus im [passiven Modus](./microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="1ddbc-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="1ddbc-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-114">Security intelligence updates</span></span>

<span data-ttu-id="1ddbc-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="1ddbc-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="1ddbc-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="1ddbc-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="1ddbc-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="1ddbc-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="1ddbc-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="1ddbc-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="1ddbc-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="1ddbc-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="1ddbc-122">Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="1ddbc-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="1ddbc-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-124">Product updates</span></span>

<span data-ttu-id="1ddbc-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="1ddbc-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="1ddbc-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="1ddbc-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1ddbc-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="1ddbc-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="1ddbc-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="1ddbc-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="1ddbc-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="1ddbc-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="1ddbc-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="1ddbc-134">All our updates contain</span></span> 
- <span data-ttu-id="1ddbc-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="1ddbc-135">performance improvements;</span></span>
- <span data-ttu-id="1ddbc-136">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="1ddbc-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="1ddbc-137">Integrationsverbesserungen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="1ddbc-138">Mai-2021 (Plattform: 4.18.2105.4 | Modul: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="1ddbc-139">&ensp;Security Intelligence Update-Version: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="1ddbc-140">&ensp;Veröffentlicht: **4. Juni 2021**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="1ddbc-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="1ddbc-142">&ensp;Modul: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="1ddbc-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-144">What's new</span></span>
- <span data-ttu-id="1ddbc-145">Verbesserungen bei der [Verhaltensüberwachung](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="1ddbc-146">Benachrichtigungsfilterungsfeature für den Fixed [Network-Schutz](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-147">Known Issues</span></span>
<span data-ttu-id="1ddbc-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-149">April -2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="1ddbc-150">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="1ddbc-151">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="1ddbc-152">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="1ddbc-153">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="1ddbc-154">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-155">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-155">What's new</span></span>
- <span data-ttu-id="1ddbc-156">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="1ddbc-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="1ddbc-157">Verbesserte Kernelmodus-Keyloggererkennung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-158">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-158">Known Issues</span></span>
<span data-ttu-id="1ddbc-159">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-160">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="1ddbc-161">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="1ddbc-162">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="1ddbc-163">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="1ddbc-164">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="1ddbc-165">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-166">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-166">What's new</span></span>

- <span data-ttu-id="1ddbc-167">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="1ddbc-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="1ddbc-168">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="1ddbc-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="1ddbc-169">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="1ddbc-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-170">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-170">Known Issues</span></span>
<span data-ttu-id="1ddbc-171">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="1ddbc-172">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="1ddbc-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="1ddbc-173">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="1ddbc-174">Ältere Versionen sind in diesem Abschnitt aufgeführt und werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="1ddbc-175">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="1ddbc-176">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="1ddbc-177">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="1ddbc-178">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="1ddbc-179">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="1ddbc-180">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-181">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-181">What's new</span></span>

- <span data-ttu-id="1ddbc-182">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="1ddbc-183">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="1ddbc-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-184">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-184">Known Issues</span></span>
<span data-ttu-id="1ddbc-185">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-186">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="1ddbc-187">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="1ddbc-188">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="1ddbc-189">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="1ddbc-190">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="1ddbc-191">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-192">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-192">What's new</span></span>

- <span data-ttu-id="1ddbc-193">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="1ddbc-194">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="1ddbc-195">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="1ddbc-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="1ddbc-196">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="1ddbc-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="1ddbc-197">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="1ddbc-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-198">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-198">Known Issues</span></span>
<span data-ttu-id="1ddbc-199">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-200">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="1ddbc-201">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="1ddbc-202">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="1ddbc-203">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="1ddbc-204">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="1ddbc-205">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-206">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-206">What's new</span></span>

- <span data-ttu-id="1ddbc-207">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-208">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-208">Known Issues</span></span>
<span data-ttu-id="1ddbc-209">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-210">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="1ddbc-211">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="1ddbc-212">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="1ddbc-213">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="1ddbc-214">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="1ddbc-215">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-216">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-216">What's new</span></span>

- <span data-ttu-id="1ddbc-217">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="1ddbc-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="1ddbc-218">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="1ddbc-219">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="1ddbc-220">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="1ddbc-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-221">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-221">Known Issues</span></span>

<span data-ttu-id="1ddbc-222">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1ddbc-223">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="1ddbc-224">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="1ddbc-225">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="1ddbc-226">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="1ddbc-227">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="1ddbc-228">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-229">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-229">What's new</span></span>

- <span data-ttu-id="1ddbc-230">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="1ddbc-231">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="1ddbc-232">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="1ddbc-233">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-233">New management interfaces for:</span></span>
   - <span data-ttu-id="1ddbc-234">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-234">UDP Inspection</span></span>
   - <span data-ttu-id="1ddbc-235">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="1ddbc-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="1ddbc-236">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="1ddbc-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="1ddbc-237">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="1ddbc-238">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-239">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-239">Known Issues</span></span>

<span data-ttu-id="1ddbc-240">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="1ddbc-241">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="1ddbc-242">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="1ddbc-243">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="1ddbc-244">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="1ddbc-245">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="1ddbc-246">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="1ddbc-247">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-247">What's new</span></span>

- <span data-ttu-id="1ddbc-248">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="1ddbc-248">Add more telemetry events</span></span>
- <span data-ttu-id="1ddbc-249">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="1ddbc-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="1ddbc-250">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="1ddbc-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="1ddbc-251">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="1ddbc-252">`AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="1ddbc-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="1ddbc-254">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="1ddbc-255">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-255">Known Issues</span></span>
<span data-ttu-id="1ddbc-256">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-257">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="1ddbc-258">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="1ddbc-259">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="1ddbc-260">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="1ddbc-261">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="1ddbc-262">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-263">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-263">What's new</span></span>

- <span data-ttu-id="1ddbc-264">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="1ddbc-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="1ddbc-265">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-266">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-266">Known Issues</span></span>
<span data-ttu-id="1ddbc-267">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-268">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="1ddbc-269">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="1ddbc-270">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="1ddbc-271">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="1ddbc-272">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="1ddbc-273">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-274">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-274">What's new</span></span>

- <span data-ttu-id="1ddbc-275">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="1ddbc-276">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="1ddbc-277">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="1ddbc-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="1ddbc-278">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="1ddbc-279">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="1ddbc-279">Fixed registry query</span></span> 
- <span data-ttu-id="1ddbc-280">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-281">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-281">Known Issues</span></span>
<span data-ttu-id="1ddbc-282">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-283">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="1ddbc-284">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="1ddbc-285">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="1ddbc-286">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="1ddbc-287">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="1ddbc-288">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-289">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-289">What's new</span></span>

- <span data-ttu-id="1ddbc-290">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="1ddbc-290">Improved logging for scan events</span></span>
- <span data-ttu-id="1ddbc-291">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="1ddbc-292">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="1ddbc-293">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="1ddbc-294">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="1ddbc-295">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-296">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-296">Known Issues</span></span>
<span data-ttu-id="1ddbc-297">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-298">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="1ddbc-299">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="1ddbc-300">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="1ddbc-301">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="1ddbc-302">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="1ddbc-303">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-304">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-304">What's new</span></span>
- <span data-ttu-id="1ddbc-305">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-305">WDfilter improvements</span></span>
- <span data-ttu-id="1ddbc-306">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="1ddbc-307">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="1ddbc-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="1ddbc-308">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="1ddbc-309">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ddbc-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="1ddbc-310">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="1ddbc-310">UEFI scan capability</span></span>
- <span data-ttu-id="1ddbc-311">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="1ddbc-312">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-312">Known Issues</span></span>
<span data-ttu-id="1ddbc-313">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-314">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="1ddbc-315">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="1ddbc-316">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="1ddbc-317">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="1ddbc-318">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="1ddbc-319">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1ddbc-320">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-320">What's new</span></span>

- <span data-ttu-id="1ddbc-321">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="1ddbc-322">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="1ddbc-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="1ddbc-323">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="1ddbc-324">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="1ddbc-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="1ddbc-325">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1ddbc-326">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-326">Known Issues</span></span>
<span data-ttu-id="1ddbc-327">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="1ddbc-328">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="1ddbc-329">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="1ddbc-330">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="1ddbc-331">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="1ddbc-332">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="1ddbc-333">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="1ddbc-334">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="1ddbc-335">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-335">Known Issues</span></span>
<span data-ttu-id="1ddbc-336">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-337">Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="1ddbc-338">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="1ddbc-339">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="1ddbc-340">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="1ddbc-341">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="1ddbc-342">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="1ddbc-343">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-343">What's new</span></span>

- <span data-ttu-id="1ddbc-344">BSOD in WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="1ddbc-345">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="1ddbc-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="1ddbc-346">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1ddbc-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="1ddbc-347">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="1ddbc-348">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="1ddbc-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1ddbc-349">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-349">Known Issues</span></span>

<span data-ttu-id="1ddbc-350">[**Behoben**] Geräte, die den [modernen Standbymodus verwenden,](/windows-hardware/design/device-experiences/modern-standby) können mit dem Windows Defender Filtertreiber hängen bleiben, was zu einer Schutzlücke führt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="1ddbc-351">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="1ddbc-352">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-352">This update is:</span></span>
> - <span data-ttu-id="1ddbc-353">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="1ddbc-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="1ddbc-354">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="1ddbc-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="1ddbc-355">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="1ddbc-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="1ddbc-356">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="1ddbc-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="1ddbc-357">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="1ddbc-358">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="1ddbc-359">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="1ddbc-360">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="1ddbc-361">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="1ddbc-362">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="1ddbc-363">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="1ddbc-364">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-364">What's new</span></span>

- <span data-ttu-id="1ddbc-365">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="1ddbc-366">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="1ddbc-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="1ddbc-367">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="1ddbc-368">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="1ddbc-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1ddbc-369">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="1ddbc-369">Known Issues</span></span>
<span data-ttu-id="1ddbc-370">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="1ddbc-371">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="1ddbc-372">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="1ddbc-373">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="1ddbc-374">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="1ddbc-375">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="1ddbc-376">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="1ddbc-377">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="1ddbc-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="1ddbc-378">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion in Windows 10-Versionen)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="1ddbc-379">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die verwalteten Supportangebote von Microsoft (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="1ddbc-380">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="1ddbc-381">In Windows 10-Versionen enthaltene Plattformversion</span><span class="sxs-lookup"><span data-stu-id="1ddbc-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="1ddbc-382">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10 Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="1ddbc-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="1ddbc-383">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="1ddbc-383">Windows 10 release</span></span>  |<span data-ttu-id="1ddbc-384">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="1ddbc-384">Platform version</span></span>  |<span data-ttu-id="1ddbc-385">Modulversion</span><span class="sxs-lookup"><span data-stu-id="1ddbc-385">Engine version</span></span> |<span data-ttu-id="1ddbc-386">Supportphase</span><span class="sxs-lookup"><span data-stu-id="1ddbc-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="1ddbc-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="1ddbc-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="1ddbc-388">4.18.1909.6</span></span> |<span data-ttu-id="1ddbc-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="1ddbc-389">1.1.17000.2</span></span> | <span data-ttu-id="1ddbc-390">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-391">1909  (19H2)</span></span> |<span data-ttu-id="1ddbc-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="1ddbc-392">4.18.1902.5</span></span> |<span data-ttu-id="1ddbc-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="1ddbc-393">1.1.16700.3</span></span> | <span data-ttu-id="1ddbc-394">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-395">1903  (19H1)</span></span> |<span data-ttu-id="1ddbc-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="1ddbc-396">4.18.1902.5</span></span> |<span data-ttu-id="1ddbc-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="1ddbc-397">1.1.15600.4</span></span> | <span data-ttu-id="1ddbc-398">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-399">1809  (RS5)</span></span> |<span data-ttu-id="1ddbc-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="1ddbc-400">4.18.1807.18075</span></span> |<span data-ttu-id="1ddbc-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="1ddbc-401">1.1.15000.2</span></span> | <span data-ttu-id="1ddbc-402">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-403">1803  (RS4)</span></span> |<span data-ttu-id="1ddbc-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="1ddbc-404">4.13.17134.1</span></span> |<span data-ttu-id="1ddbc-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="1ddbc-405">1.1.14600.4</span></span> | <span data-ttu-id="1ddbc-406">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-407">1709  (RS3)</span></span> |<span data-ttu-id="1ddbc-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="1ddbc-408">4.12.16299.15</span></span> |<span data-ttu-id="1ddbc-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="1ddbc-409">1.1.14104.0</span></span> | <span data-ttu-id="1ddbc-410">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-411">1703  (RS2)</span></span> |<span data-ttu-id="1ddbc-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="1ddbc-412">4.11.15603.2</span></span> |<span data-ttu-id="1ddbc-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="1ddbc-413">1.1.13504.0</span></span> | <span data-ttu-id="1ddbc-414">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1ddbc-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-415">1607 (RS1)</span></span> |<span data-ttu-id="1ddbc-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="1ddbc-416">4.10.14393.3683</span></span> |<span data-ttu-id="1ddbc-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="1ddbc-417">1.1.12805.0</span></span> | <span data-ttu-id="1ddbc-418">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="1ddbc-419">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="1ddbc-420">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="1ddbc-421">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antivirus- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="1ddbc-422">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="1ddbc-423">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Installationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="1ddbc-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="1ddbc-425">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="1ddbc-426">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="1ddbc-427">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="1ddbc-428">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-429">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-429">Fixes</span></span>
- <span data-ttu-id="1ddbc-430">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-431">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-431">Additional information</span></span>
- <span data-ttu-id="1ddbc-432">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="1ddbc-434">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="1ddbc-435">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="1ddbc-436">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="1ddbc-437">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-438">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-438">Fixes</span></span>
- <span data-ttu-id="1ddbc-439">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-440">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-440">Additional information</span></span>
- <span data-ttu-id="1ddbc-441">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="1ddbc-443">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="1ddbc-444">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="1ddbc-445">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="1ddbc-446">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-447">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-447">Fixes</span></span>
- <span data-ttu-id="1ddbc-448">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-449">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-449">Additional information</span></span>
- <span data-ttu-id="1ddbc-450">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="1ddbc-452">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="1ddbc-453">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="1ddbc-454">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="1ddbc-455">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-456">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-456">Fixes</span></span>
- <span data-ttu-id="1ddbc-457">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-458">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-458">Additional information</span></span>
- <span data-ttu-id="1ddbc-459">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="1ddbc-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="1ddbc-461">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="1ddbc-462">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="1ddbc-463">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="1ddbc-464">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-465">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-465">Fixes</span></span>
- <span data-ttu-id="1ddbc-466">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-467">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-467">Additional information</span></span>
- <span data-ttu-id="1ddbc-468">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="1ddbc-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="1ddbc-470">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="1ddbc-471">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="1ddbc-472">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="1ddbc-473">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-474">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-474">Fixes</span></span>
- <span data-ttu-id="1ddbc-475">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-476">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-476">Additional information</span></span>
- <span data-ttu-id="1ddbc-477">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="1ddbc-479">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="1ddbc-480">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="1ddbc-481">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1ddbc-482">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-483">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-483">Fixes</span></span>
- <span data-ttu-id="1ddbc-484">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-485">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-485">Additional information</span></span>
- <span data-ttu-id="1ddbc-486">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="1ddbc-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="1ddbc-488">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="1ddbc-489">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="1ddbc-490">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1ddbc-491">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-492">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-492">Fixes</span></span>
- <span data-ttu-id="1ddbc-493">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-494">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-494">Additional information</span></span>
- <span data-ttu-id="1ddbc-495">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="1ddbc-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="1ddbc-497">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="1ddbc-498">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="1ddbc-499">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1ddbc-500">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-501">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-501">Fixes</span></span>
- <span data-ttu-id="1ddbc-502">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-503">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-503">Additional information</span></span>
- <span data-ttu-id="1ddbc-504">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1ddbc-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="1ddbc-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="1ddbc-506">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="1ddbc-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="1ddbc-507">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="1ddbc-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="1ddbc-508">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="1ddbc-509">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="1ddbc-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1ddbc-510">Behebungen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-510">Fixes</span></span>
- <span data-ttu-id="1ddbc-511">Keine</span><span class="sxs-lookup"><span data-stu-id="1ddbc-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1ddbc-512">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-512">Additional information</span></span>
- <span data-ttu-id="1ddbc-513">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="1ddbc-514">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-514">Additional resources</span></span>

| <span data-ttu-id="1ddbc-515">Artikel</span><span class="sxs-lookup"><span data-stu-id="1ddbc-515">Article</span></span> | <span data-ttu-id="1ddbc-516">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ddbc-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="1ddbc-517">Microsoft Defender-Update für Windows Betriebssysteminstallationsimages</span><span class="sxs-lookup"><span data-stu-id="1ddbc-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="1ddbc-518">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="1ddbc-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="1ddbc-519">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="1ddbc-520">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="1ddbc-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="1ddbc-521">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="1ddbc-522">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="1ddbc-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="1ddbc-523">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="1ddbc-524">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="1ddbc-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="1ddbc-525">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="1ddbc-526">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="1ddbc-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="1ddbc-527">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="1ddbc-528">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="1ddbc-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="1ddbc-529">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
