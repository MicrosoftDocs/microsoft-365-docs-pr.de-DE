---
title: Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten
description: Verwalten, wie Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
keywords: updates, security baselines, protection, schedule updates, force updates, mobile updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ae17aa6e2cb0cefd460ef0db0730570af8c84bb8
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995033"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="60582-104">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="60582-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="60582-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="60582-105">**Applies to:**</span></span>

- [<span data-ttu-id="60582-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="60582-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="60582-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="60582-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="60582-108">Es gibt zwei Arten von Updates im Zusammenhang mit der Aktualisierung von Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="60582-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="60582-109">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="60582-109">Security intelligence updates</span></span>
- <span data-ttu-id="60582-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="60582-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60582-111">Microsoft Defender Antivirus auf dem neuesten Stand zu halten, ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="60582-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="60582-112">Achten Sie darauf, Ihren Antivirenschutz zu aktualisieren, auch wenn Microsoft Defender Antivirus im [passiven Modus ausgeführt wird.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="60582-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="60582-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="60582-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="60582-114">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="60582-114">Security intelligence updates</span></span>

<span data-ttu-id="60582-115">Microsoft Defender Antivirus verwendet in der [Cloud](cloud-protection-microsoft-defender-antivirus.md) übermittelten Schutz (auch Microsoft Advanced Protection Service oder MAPS genannt) und lädt regelmäßig Sicherheitsintelligenzupdates herunter, um Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="60582-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="60582-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="60582-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="60582-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="60582-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="60582-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="60582-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="60582-119">Der von der Cloud übermittelte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, um zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="60582-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="60582-120">Sicherheitsintelligenzupdates erfolgen in einer geplanten Schrittfrequenz (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="60582-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="60582-121">Weitere Informationen finden Sie unter [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="60582-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="60582-122">Eine Liste der aktuellen Sicherheitsintelligenzupdates finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="60582-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="60582-123">Modulupdates sind in Sicherheitsintelligenzupdates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="60582-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="60582-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="60582-124">Product updates</span></span>

<span data-ttu-id="60582-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (auch als Plattformupdates bezeichnet) und erhält wichtige Featureupdates zusammen mit Windows 10-Versionen. </span><span class="sxs-lookup"><span data-stu-id="60582-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="60582-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="60582-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="60582-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="60582-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="60582-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="60582-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="60582-129">Die übliche Methode, mit der Sie Microsoft- und Windows-Updates auf Endpunkten in Ihrem Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="60582-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="60582-130">Weitere Informationen finden Sie unter [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="60582-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="60582-131">Monatliche Updates werden in Phasen veröffentlicht, was zu mehreren Paketen führt, die in Ihren [Window Server Update Services angezeigt werden.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="60582-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="60582-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="60582-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="60582-133">Weitere Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update for Windows Defender anmalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="60582-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="60582-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="60582-134">All our updates contain</span></span> 
- <span data-ttu-id="60582-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="60582-135">performance improvements;</span></span>
- <span data-ttu-id="60582-136">Verbesserungen bei der Dienstbarkeit; und</span><span class="sxs-lookup"><span data-stu-id="60582-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="60582-137">Integrationsverbesserungen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="60582-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="60582-138">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="60582-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="60582-139">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="60582-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="60582-140">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="60582-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="60582-141">&ensp;Plattform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="60582-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="60582-142">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="60582-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="60582-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="60582-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-144">What's new</span></span>

- <span data-ttu-id="60582-145">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="60582-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="60582-146">Risikominderungen für Brute-Force-Attack im erweiterten Netzwerk</span><span class="sxs-lookup"><span data-stu-id="60582-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="60582-147">Zusätzliche fehlgeschlagene Manipulationsversuchsereignisgenerierung, [wenn Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="60582-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-148">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-148">Known Issues</span></span>
<span data-ttu-id="60582-149">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="60582-150">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="60582-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="60582-151">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="60582-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="60582-152">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="60582-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="60582-153">&ensp;Plattform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="60582-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="60582-154">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="60582-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="60582-155">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="60582-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-156">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-156">What's new</span></span>

- <span data-ttu-id="60582-157">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="60582-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="60582-158">Erweitern des Schutzes von Manipulationen</span><span class="sxs-lookup"><span data-stu-id="60582-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-159">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-159">Known Issues</span></span>
<span data-ttu-id="60582-160">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="60582-161">Januar-2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="60582-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="60582-162">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="60582-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="60582-163">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="60582-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="60582-164">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="60582-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="60582-165">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="60582-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="60582-166">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="60582-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-167">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-167">What's new</span></span>

- <span data-ttu-id="60582-168">Verbesserungen bei der Erkennung von Shellcode-Exploits</span><span class="sxs-lookup"><span data-stu-id="60582-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="60582-169">Verbesserte Sichtbarkeit für Versuche zum Stehlen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="60582-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="60582-170">Verbesserungen bei antitampering-Features in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="60582-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="60582-171">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="60582-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="60582-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="60582-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-173">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-173">Known Issues</span></span>
<span data-ttu-id="60582-174">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="60582-175">Updates früherer Versionen: Nur support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="60582-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="60582-176">Nachdem eine neue Paketversion veröffentlicht wurde, wird die Unterstützung für die beiden vorherigen Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="60582-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="60582-177">Versionen, die älter sind als die in diesem Abschnitt aufgeführten, werden nur für technischen Upgradesupport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="60582-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="60582-178">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="60582-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="60582-179">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="60582-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="60582-180">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="60582-181">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="60582-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="60582-182">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="60582-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="60582-183">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-183">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-184">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-184">What's new</span></span>

- <span data-ttu-id="60582-185">Verbesserte [Unterstützung der SmartScreen-Statusprotokollierung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="60582-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-186">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-186">Known Issues</span></span>
<span data-ttu-id="60582-187">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="60582-188">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="60582-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="60582-189">&ensp;Version des Security Intelligence-Updates: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="60582-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="60582-190">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="60582-191">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="60582-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="60582-192">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="60582-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="60582-193">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-193">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-194">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-194">What's new</span></span>

- <span data-ttu-id="60582-195">Neue Beschreibungen für spezielle Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="60582-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="60582-196">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="60582-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="60582-197">Verbesserte Funktionen zum Zulassen/Blockieren von Hostadressen</span><span class="sxs-lookup"><span data-stu-id="60582-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="60582-198">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="60582-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-199">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-199">Known Issues</span></span>

<span data-ttu-id="60582-200">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="60582-201">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="60582-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="60582-202">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="60582-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="60582-203">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="60582-204">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="60582-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="60582-205">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="60582-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="60582-206">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-207">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-207">What's new</span></span>

- <span data-ttu-id="60582-208">Administratorberechtigungen sind erforderlich, um Dateien in Quarantäne wiederherzustellen</span><span class="sxs-lookup"><span data-stu-id="60582-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="60582-209">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="60582-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="60582-210">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="60582-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="60582-211">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="60582-211">New management interfaces for:</span></span>
   - <span data-ttu-id="60582-212">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="60582-212">UDP Inspection</span></span>
   - <span data-ttu-id="60582-213">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="60582-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="60582-214">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="60582-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="60582-215">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="60582-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="60582-216">Verbesserte Überprüfung des Office VBA-Moduls</span><span class="sxs-lookup"><span data-stu-id="60582-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-217">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-217">Known Issues</span></span>

<span data-ttu-id="60582-218">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="60582-219">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="60582-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="60582-220">&ensp;Updateversion der Sicherheitsintelligenz: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="60582-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="60582-221">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="60582-222">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="60582-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="60582-223">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="60582-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="60582-224">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="60582-225">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-225">What's new</span></span>

- <span data-ttu-id="60582-226">Hinzufügen von weiteren Telemetrieereignissen</span><span class="sxs-lookup"><span data-stu-id="60582-226">Add more telemetry events</span></span>
- <span data-ttu-id="60582-227">Verbesserte Telemetrie des Scanereigniss</span><span class="sxs-lookup"><span data-stu-id="60582-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="60582-228">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="60582-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="60582-229">Verbesserte Überprüfung von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="60582-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="60582-230">Hinzugefügt `AMRunningMode` zu Get-MpComputerStatus PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="60582-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="60582-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="60582-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="60582-232">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="60582-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="60582-233">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-233">Known Issues</span></span>
<span data-ttu-id="60582-234">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-235">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="60582-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="60582-236">&ensp;Version des Security Intelligence-Updates: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="60582-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="60582-237">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="60582-238">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="60582-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="60582-239">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="60582-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="60582-240">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-241">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-241">What's new</span></span>

- <span data-ttu-id="60582-242">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="60582-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="60582-243">Verbesserte Validierung von Authenticode-Codesignaturzertifikaten</span><span class="sxs-lookup"><span data-stu-id="60582-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-244">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-244">Known Issues</span></span>
<span data-ttu-id="60582-245">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-246">Juni-2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="60582-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="60582-247">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="60582-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="60582-248">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="60582-249">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="60582-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="60582-250">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="60582-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="60582-251">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-252">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-252">What's new</span></span>

- <span data-ttu-id="60582-253">Möglichkeit zum Angeben des [Speicherorts der Supportprotokolle](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="60582-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="60582-254">Überspringen der aggressiven Nachholscan im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="60582-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="60582-255">Zulassen, dass Defender bei gemessenen Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="60582-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="60582-256">Leistungsoptimierung behoben, wenn die Zwischenspeicherung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="60582-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="60582-257">Registrierungsabfrage wurde behoben</span><span class="sxs-lookup"><span data-stu-id="60582-257">Fixed registry query</span></span> 
- <span data-ttu-id="60582-258">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="60582-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-259">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-259">Known Issues</span></span>
<span data-ttu-id="60582-260">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-261">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="60582-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="60582-262">&ensp;Version des Security Intelligence-Updates: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="60582-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="60582-263">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="60582-264">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="60582-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="60582-265">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="60582-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="60582-266">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-267">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-267">What's new</span></span>

- <span data-ttu-id="60582-268">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="60582-268">Improved logging for scan events</span></span>
- <span data-ttu-id="60582-269">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="60582-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="60582-270">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="60582-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="60582-271">AmSI-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="60582-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="60582-272">Blockierung der AMSI-Cloud behoben</span><span class="sxs-lookup"><span data-stu-id="60582-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="60582-273">Installationsprotokoll für Sicherheitsupdates behoben</span><span class="sxs-lookup"><span data-stu-id="60582-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-274">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-274">Known Issues</span></span>
<span data-ttu-id="60582-275">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-276">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="60582-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="60582-277">&ensp;Version des Security Intelligence-Updates: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="60582-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="60582-278">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="60582-279">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="60582-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="60582-280">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="60582-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="60582-281">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-282">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-282">What's new</span></span>
- <span data-ttu-id="60582-283">Verbesserungen bei WDfilter</span><span class="sxs-lookup"><span data-stu-id="60582-283">WDfilter improvements</span></span>
- <span data-ttu-id="60582-284">Hinzufügen von ereignisfähigeren Ereignisdaten zum Angriff auf Erkennungsereignisse zur Oberflächenreduzierung</span><span class="sxs-lookup"><span data-stu-id="60582-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="60582-285">Informationen zu festen Versionen in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="60582-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="60582-286">Falsche Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="60582-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="60582-287">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="60582-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="60582-288">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="60582-288">UEFI scan capability</span></span>
- <span data-ttu-id="60582-289">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="60582-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="60582-290">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-290">Known Issues</span></span>
<span data-ttu-id="60582-291">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-292">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="60582-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="60582-293">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="60582-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="60582-294">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="60582-295">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="60582-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="60582-296">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="60582-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="60582-297">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="60582-298">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-298">What's new</span></span>

- <span data-ttu-id="60582-299">Zu [MpCmdRun hinzugefügte CPU-Einschränkungsoption](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="60582-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="60582-300">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="60582-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="60582-301">Reduzieren des Timeouts für Sicherheitsintelligenz (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="60582-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="60582-302">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="60582-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="60582-303">Verbessern der Benachrichtigung für prozessblockierung</span><span class="sxs-lookup"><span data-stu-id="60582-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="60582-304">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-304">Known Issues</span></span>
<span data-ttu-id="60582-305">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="60582-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="60582-306">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="60582-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="60582-307">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="60582-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="60582-308">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="60582-309">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="60582-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="60582-310">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="60582-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="60582-311">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="60582-312">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="60582-313">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-313">Known Issues</span></span>
<span data-ttu-id="60582-314">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-315">Januar-2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="60582-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="60582-316">Version des Security Intelligence-Updates: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="60582-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="60582-317">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="60582-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="60582-318">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="60582-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="60582-319">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="60582-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="60582-320">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="60582-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="60582-321">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-321">What's new</span></span>

- <span data-ttu-id="60582-322">Feste BSOD auf WS2016 mit Exchange</span><span class="sxs-lookup"><span data-stu-id="60582-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="60582-323">Unterstützen von Plattformupdates, wenn TMP zum Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="60582-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="60582-324">Plattform- und Modulversionen werden [WDSI hinzugefügt](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="60582-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="60582-325">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="60582-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="60582-326">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="60582-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="60582-327">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-327">Known Issues</span></span>

<span data-ttu-id="60582-328">[**Fixed**] Geräte, [die](/windows-hardware/design/device-experiences/modern-standby) den modernen Standbymodus verwenden, können eine Hängerung mit dem Windows Defender-Filtertreibers erleben, was zu einer Schutzlücke führt.</span><span class="sxs-lookup"><span data-stu-id="60582-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="60582-329">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischalwareplattform aktualisiert zu sein.</span><span class="sxs-lookup"><span data-stu-id="60582-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="60582-330">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="60582-330">This update is:</span></span>
> - <span data-ttu-id="60582-331">wird von RS1-Geräten mit niedrigerer Version der Plattform benötigt, um SHA2 zu unterstützen;</span><span class="sxs-lookup"><span data-stu-id="60582-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="60582-332">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen.</span><span class="sxs-lookup"><span data-stu-id="60582-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="60582-333">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates ersetzt, um die zukünftige Verfügbarkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="60582-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="60582-334">wird aufgrund der Neustartanforderung als Update kategorisiert; und</span><span class="sxs-lookup"><span data-stu-id="60582-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="60582-335">wird nur mit [Windows Update angeboten.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="60582-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="60582-336">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="60582-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="60582-337">Version des Security Intelligence-Updates: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="60582-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="60582-338">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="60582-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="60582-339">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="60582-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="60582-340">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="60582-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="60582-341">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="60582-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="60582-342">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="60582-342">What's new</span></span>

- <span data-ttu-id="60582-343">Feste MpCmdRun-Ablaufverfolgungsstufe</span><span class="sxs-lookup"><span data-stu-id="60582-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="60582-344">Informationen zur WDFilter-Version behoben</span><span class="sxs-lookup"><span data-stu-id="60582-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="60582-345">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="60582-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="60582-346">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="60582-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="60582-347">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="60582-347">Known Issues</span></span>
<span data-ttu-id="60582-348">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="60582-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="60582-349">Unterstützung der Microsoft Defender Antivirus-Plattform</span><span class="sxs-lookup"><span data-stu-id="60582-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="60582-350">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="60582-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="60582-351">Um vollständig unterstützt zu werden, halten Sie die neuesten Plattformupdates auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="60582-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="60582-352">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="60582-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="60582-353">**Wartungsphase** für Sicherheits- und kritische Updates– Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Anti-Malware-Plattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="60582-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="60582-354">**Phase des technischen Support (nur)** – Nachdem eine neue Plattformversion veröffentlicht wurde, wird die Unterstützung für ältere Versionen (N-2) auf nur noch technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="60582-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="60582-355">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="60582-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="60582-356">\* Der technische Support wird weiterhin für Upgrades von der Windows 10-Version (siehe In [Windows 10-Versionen](#platform-version-included-with-windows-10-releases)enthaltene Plattformversion) auf die neueste Plattformversion bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="60582-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="60582-357">Während der Phase des technischen Support (nur) werden kommerziell angemessene Supportvorfälle über den Microsoft Customer Service & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="60582-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="60582-358">Wenn für einen Supportvorfall eine Eskalation zur Entwicklung erforderlich ist, ein nicht sicherheitsunsicherheitsupdate erforderlich ist oder ein Sicherheitsupdate erforderlich ist, werden Kunden aufgefordert, ein Upgrade auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu durchführen.</span><span class="sxs-lookup"><span data-stu-id="60582-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="60582-359">In Windows 10-Versionen enthaltene Plattformversion</span><span class="sxs-lookup"><span data-stu-id="60582-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="60582-360">Die folgende Tabelle enthält die Microsoft Defender Antivirus-Plattform- und Modulversionen, die mit den neuesten Windows 10-Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="60582-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="60582-361">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="60582-361">Windows 10 release</span></span>  |<span data-ttu-id="60582-362">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="60582-362">Platform version</span></span>  |<span data-ttu-id="60582-363">Modulversion</span><span class="sxs-lookup"><span data-stu-id="60582-363">Engine version</span></span> |<span data-ttu-id="60582-364">Supportphase</span><span class="sxs-lookup"><span data-stu-id="60582-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="60582-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="60582-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="60582-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="60582-366">4.18.1909.6</span></span> |<span data-ttu-id="60582-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="60582-367">1.1.17000.2</span></span> | <span data-ttu-id="60582-368">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="60582-369">1909  (19H2)</span></span> |<span data-ttu-id="60582-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="60582-370">4.18.1902.5</span></span> |<span data-ttu-id="60582-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="60582-371">1.1.16700.3</span></span> | <span data-ttu-id="60582-372">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="60582-373">1903  (19H1)</span></span> |<span data-ttu-id="60582-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="60582-374">4.18.1902.5</span></span> |<span data-ttu-id="60582-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="60582-375">1.1.15600.4</span></span> | <span data-ttu-id="60582-376">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="60582-377">1809  (RS5)</span></span> |<span data-ttu-id="60582-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="60582-378">4.18.1807.18075</span></span> |<span data-ttu-id="60582-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="60582-379">1.1.15000.2</span></span> | <span data-ttu-id="60582-380">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="60582-381">1803  (RS4)</span></span> |<span data-ttu-id="60582-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="60582-382">4.13.17134.1</span></span> |<span data-ttu-id="60582-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="60582-383">1.1.14600.4</span></span> | <span data-ttu-id="60582-384">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="60582-385">1709  (RS3)</span></span> |<span data-ttu-id="60582-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="60582-386">4.12.16299.15</span></span> |<span data-ttu-id="60582-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="60582-387">1.1.14104.0</span></span> | <span data-ttu-id="60582-388">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="60582-389">1703  (RS2)</span></span> |<span data-ttu-id="60582-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="60582-390">4.11.15603.2</span></span> |<span data-ttu-id="60582-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="60582-391">1.1.13504.0</span></span> | <span data-ttu-id="60582-392">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="60582-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="60582-393">1607 (RS1)</span></span> |<span data-ttu-id="60582-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="60582-394">4.10.14393.3683</span></span> |<span data-ttu-id="60582-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="60582-395">1.1.12805.0</span></span> | <span data-ttu-id="60582-396">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="60582-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="60582-397">Informationen zur Windows 10-Version finden Sie im [Windows-Lifecycle-Factsheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="60582-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="60582-398">Updates für die Bereitstellungsimagewartung und -verwaltung (DISM)</span><span class="sxs-lookup"><span data-stu-id="60582-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="60582-399">Es wird empfohlen, Ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 -Betriebssysteminstallationsabbilder mit den neuesten Antiviren- und Antischantischungsupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60582-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="60582-400">Wenn Sie Ihre Betriebssysteminstallationsabbilder auf dem neuesten Stand halten, können Sie eine Lücke beim Schutz vermeiden.</span><span class="sxs-lookup"><span data-stu-id="60582-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="60582-401">Weitere Informationen finden Sie unter [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="60582-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="60582-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="60582-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="60582-403">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="60582-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="60582-404">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="60582-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="60582-405">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="60582-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="60582-406">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="60582-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-407">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-407">Fixes</span></span>
- <span data-ttu-id="60582-408">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-409">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-409">Additional information</span></span>
- <span data-ttu-id="60582-410">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="60582-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="60582-412">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="60582-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="60582-413">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="60582-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="60582-414">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="60582-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="60582-415">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="60582-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-416">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-416">Fixes</span></span>
- <span data-ttu-id="60582-417">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-418">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-418">Additional information</span></span>
- <span data-ttu-id="60582-419">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="60582-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="60582-421">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="60582-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="60582-422">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="60582-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="60582-423">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="60582-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="60582-424">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="60582-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-425">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-425">Fixes</span></span>
- <span data-ttu-id="60582-426">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-427">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-427">Additional information</span></span>
- <span data-ttu-id="60582-428">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="60582-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="60582-430">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="60582-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="60582-431">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="60582-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="60582-432">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="60582-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="60582-433">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="60582-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-434">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-434">Fixes</span></span>
- <span data-ttu-id="60582-435">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-436">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-436">Additional information</span></span>
- <span data-ttu-id="60582-437">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="60582-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="60582-439">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="60582-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="60582-440">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="60582-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="60582-441">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="60582-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="60582-442">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="60582-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-443">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-443">Fixes</span></span>
- <span data-ttu-id="60582-444">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-445">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-445">Additional information</span></span>
- <span data-ttu-id="60582-446">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="60582-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="60582-448">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="60582-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="60582-449">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="60582-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="60582-450">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="60582-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="60582-451">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="60582-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-452">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-452">Fixes</span></span>
- <span data-ttu-id="60582-453">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-454">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-454">Additional information</span></span>
- <span data-ttu-id="60582-455">Aktualisierte Microsoft Defender Antivirus-Signaturen</span><span class="sxs-lookup"><span data-stu-id="60582-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="60582-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="60582-457">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="60582-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="60582-458">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="60582-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="60582-459">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="60582-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="60582-460">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="60582-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-461">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-461">Fixes</span></span>
- <span data-ttu-id="60582-462">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-463">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-463">Additional information</span></span>
- <span data-ttu-id="60582-464">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="60582-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="60582-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="60582-466">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="60582-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="60582-467">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="60582-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="60582-468">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="60582-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="60582-469">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="60582-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="60582-470">Behebungen</span><span class="sxs-lookup"><span data-stu-id="60582-470">Fixes</span></span>
- <span data-ttu-id="60582-471">Keine</span><span class="sxs-lookup"><span data-stu-id="60582-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="60582-472">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60582-472">Additional information</span></span>
- <span data-ttu-id="60582-473">Unterstützung für Windows 10 RS1 oder höher Betriebssysteminstallationsabbilder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60582-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="60582-474">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="60582-474">Additional resources</span></span>

| <span data-ttu-id="60582-475">Artikel</span><span class="sxs-lookup"><span data-stu-id="60582-475">Article</span></span> | <span data-ttu-id="60582-476">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60582-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="60582-477">Microsoft Defender Update für Windows-Betriebssysteminstallationsabbilder</span><span class="sxs-lookup"><span data-stu-id="60582-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="60582-478">Überprüfen Sie Antischadwareupdatepakete für Ihre Betriebssysteminstallationsabbilder (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="60582-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="60582-479">Hier erhalten Sie Microsoft Defender Antivirus-Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019- und Windows Server 2016-Installationsabbilder.</span><span class="sxs-lookup"><span data-stu-id="60582-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="60582-480">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="60582-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="60582-481">Schutzupdates können über viele Quellen zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="60582-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="60582-482">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="60582-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="60582-483">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60582-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="60582-484">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="60582-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="60582-485">Wenn ein Endpunkt ein Update oder einen geplanten Scan verpasst, können Sie ein Update erzwingen oder bei der nächsten Benutzeran meldet.</span><span class="sxs-lookup"><span data-stu-id="60582-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="60582-486">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="60582-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="60582-487">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten in der Cloud übermittelten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="60582-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="60582-488">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="60582-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="60582-489">Sie können Einstellungen angeben, z. B. ob Updates für die Akkuleistung erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="60582-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
