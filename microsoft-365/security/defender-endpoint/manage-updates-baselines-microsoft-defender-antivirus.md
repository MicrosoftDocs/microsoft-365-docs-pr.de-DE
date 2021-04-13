---
title: Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten
description: Verwalten, wie Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
keywords: updates, security baselines, protection, schedule updates, force updates, mobile updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690392"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="d9163-104">Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten</span><span class="sxs-lookup"><span data-stu-id="d9163-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="d9163-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d9163-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9163-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d9163-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="d9163-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="d9163-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d9163-108">Es gibt zwei Arten von Updates im Zusammenhang mit der Aktualisierung von Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="d9163-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="d9163-109">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="d9163-109">Security intelligence updates</span></span>
- <span data-ttu-id="d9163-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="d9163-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9163-111">Microsoft Defender Antivirus auf dem neuesten Stand zu halten, ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d9163-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="d9163-112">Achten Sie darauf, Ihren Antivirenschutz zu aktualisieren, auch wenn Microsoft Defender Antivirus im [passiven Modus ausgeführt wird.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d9163-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="d9163-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="d9163-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="d9163-114">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="d9163-114">Security intelligence updates</span></span>

<span data-ttu-id="d9163-115">Microsoft Defender Antivirus verwendet in der [Cloud](cloud-protection-microsoft-defender-antivirus.md) übermittelten Schutz (auch Microsoft Advanced Protection Service oder MAPS genannt) und lädt regelmäßig Sicherheitsintelligenzupdates herunter, um Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="d9163-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="d9163-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="d9163-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="d9163-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="d9163-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="d9163-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="d9163-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="d9163-119">Der von der Cloud übermittelte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, um zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d9163-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="d9163-120">Sicherheitsintelligenzupdates erfolgen in einer geplanten Schrittfrequenz (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="d9163-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="d9163-121">Weitere Informationen finden Sie unter [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d9163-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="d9163-122">Eine Liste der aktuellen Sicherheitsintelligenzupdates finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="d9163-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="d9163-123">Modulupdates sind in Sicherheitsintelligenzupdates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="d9163-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="d9163-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="d9163-124">Product updates</span></span>

<span data-ttu-id="d9163-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (auch als Plattformupdates bezeichnet) und erhält wichtige Featureupdates zusammen mit Windows 10-Versionen. </span><span class="sxs-lookup"><span data-stu-id="d9163-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="d9163-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="d9163-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="d9163-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="d9163-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="d9163-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d9163-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="d9163-129">Die übliche Methode, mit der Sie Microsoft- und Windows-Updates auf Endpunkten in Ihrem Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9163-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="d9163-130">Weitere Informationen finden Sie unter [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="d9163-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="d9163-131">Monatliche Updates werden in Phasen veröffentlicht, was zu mehreren Paketen führt, die in Ihren [Window Server Update Services angezeigt werden.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="d9163-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="d9163-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="d9163-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="d9163-133">Weitere Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update for Windows Defender anmalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="d9163-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="d9163-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="d9163-134">All our updates contain</span></span> 
- <span data-ttu-id="d9163-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="d9163-135">performance improvements;</span></span>
- <span data-ttu-id="d9163-136">Verbesserungen bei der Dienstbarkeit; und</span><span class="sxs-lookup"><span data-stu-id="d9163-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="d9163-137">Integrationsverbesserungen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="d9163-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="d9163-138">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="d9163-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="d9163-139">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="d9163-140">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="d9163-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="d9163-141">&ensp;Plattform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="d9163-142">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="d9163-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="d9163-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-144">What's new</span></span>

- <span data-ttu-id="d9163-145">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="d9163-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="d9163-146">Risikominderungen für Brute-Force-Attack im erweiterten Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d9163-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="d9163-147">Zusätzliche fehlgeschlagene Manipulationsversuchsereignisgenerierung, [wenn Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="d9163-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-148">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-148">Known Issues</span></span>
<span data-ttu-id="d9163-149">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d9163-150">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="d9163-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="d9163-151">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="d9163-152">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="d9163-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="d9163-153">&ensp;Plattform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="d9163-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="d9163-154">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="d9163-155">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="d9163-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-156">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-156">What's new</span></span>

- <span data-ttu-id="d9163-157">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d9163-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="d9163-158">Erweitern des Schutzes von Manipulationen</span><span class="sxs-lookup"><span data-stu-id="d9163-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-159">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-159">Known Issues</span></span>
<span data-ttu-id="d9163-160">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d9163-161">Januar-2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="d9163-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="d9163-162">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d9163-163">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="d9163-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="d9163-164">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="d9163-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="d9163-165">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="d9163-166">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="d9163-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-167">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-167">What's new</span></span>

- <span data-ttu-id="d9163-168">Verbesserungen bei der Erkennung von Shellcode-Exploits</span><span class="sxs-lookup"><span data-stu-id="d9163-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="d9163-169">Verbesserte Sichtbarkeit für Versuche zum Stehlen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="d9163-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="d9163-170">Verbesserungen bei antitampering-Features in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="d9163-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="d9163-171">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="d9163-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="d9163-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="d9163-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-173">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-173">Known Issues</span></span>
<span data-ttu-id="d9163-174">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="d9163-175">Updates früherer Versionen: Nur support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="d9163-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="d9163-176">Nachdem eine neue Paketversion veröffentlicht wurde, wird die Unterstützung für die beiden vorherigen Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="d9163-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="d9163-177">Versionen, die älter sind als die in diesem Abschnitt aufgeführten, werden nur für technischen Upgradesupport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d9163-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="d9163-178">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="d9163-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="d9163-179">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d9163-180">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="d9163-181">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="d9163-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="d9163-182">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="d9163-183">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="d9163-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-184">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-184">What's new</span></span>

- <span data-ttu-id="d9163-185">Verbesserte [Unterstützung der SmartScreen-Statusprotokollierung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="d9163-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-186">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-186">Known Issues</span></span>
<span data-ttu-id="d9163-187">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d9163-188">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="d9163-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="d9163-189">&ensp;Version des Security Intelligence-Updates: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="d9163-190">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="d9163-191">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="d9163-192">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="d9163-193">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="d9163-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-194">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-194">What's new</span></span>

- <span data-ttu-id="d9163-195">Neue Beschreibungen für spezielle Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="d9163-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="d9163-196">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d9163-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="d9163-197">Verbesserte Funktionen zum Zulassen/Blockieren von Hostadressen</span><span class="sxs-lookup"><span data-stu-id="d9163-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="d9163-198">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="d9163-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-199">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-199">Known Issues</span></span>

<span data-ttu-id="d9163-200">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d9163-201">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="d9163-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="d9163-202">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="d9163-203">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="d9163-204">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="d9163-205">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="d9163-206">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-207">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-207">What's new</span></span>

- <span data-ttu-id="d9163-208">Administratorberechtigungen sind erforderlich, um Dateien in Quarantäne wiederherzustellen</span><span class="sxs-lookup"><span data-stu-id="d9163-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="d9163-209">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="d9163-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="d9163-210">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="d9163-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="d9163-211">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="d9163-211">New management interfaces for:</span></span>
   - <span data-ttu-id="d9163-212">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="d9163-212">UDP Inspection</span></span>
   - <span data-ttu-id="d9163-213">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="d9163-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="d9163-214">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="d9163-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="d9163-215">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="d9163-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="d9163-216">Verbesserte Überprüfung des Office VBA-Moduls</span><span class="sxs-lookup"><span data-stu-id="d9163-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-217">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-217">Known Issues</span></span>

<span data-ttu-id="d9163-218">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="d9163-219">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="d9163-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="d9163-220">&ensp;Updateversion der Sicherheitsintelligenz: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="d9163-221">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="d9163-222">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="d9163-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="d9163-223">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="d9163-224">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="d9163-225">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-225">What's new</span></span>

- <span data-ttu-id="d9163-226">Hinzufügen von weiteren Telemetrieereignissen</span><span class="sxs-lookup"><span data-stu-id="d9163-226">Add more telemetry events</span></span>
- <span data-ttu-id="d9163-227">Verbesserte Telemetrie des Scanereigniss</span><span class="sxs-lookup"><span data-stu-id="d9163-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="d9163-228">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="d9163-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="d9163-229">Verbesserte Überprüfung von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="d9163-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="d9163-230">Hinzugefügt `AMRunningMode` zu Get-MpComputerStatus PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d9163-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="d9163-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d9163-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="d9163-232">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="d9163-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="d9163-233">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-233">Known Issues</span></span>
<span data-ttu-id="d9163-234">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-235">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="d9163-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="d9163-236">&ensp;Version des Security Intelligence-Updates: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="d9163-237">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="d9163-238">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="d9163-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="d9163-239">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="d9163-240">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-241">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-241">What's new</span></span>

- <span data-ttu-id="d9163-242">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="d9163-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="d9163-243">Verbesserte Validierung von Authenticode-Codesignaturzertifikaten</span><span class="sxs-lookup"><span data-stu-id="d9163-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-244">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-244">Known Issues</span></span>
<span data-ttu-id="d9163-245">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-246">Juni-2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="d9163-247">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="d9163-248">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="d9163-249">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="d9163-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="d9163-250">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="d9163-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="d9163-251">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-252">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-252">What's new</span></span>

- <span data-ttu-id="d9163-253">Möglichkeit zum Angeben des [Speicherorts der Supportprotokolle](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="d9163-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="d9163-254">Überspringen der aggressiven Nachholscan im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="d9163-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="d9163-255">Zulassen, dass Defender bei gemessenen Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="d9163-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="d9163-256">Leistungsoptimierung behoben, wenn die Zwischenspeicherung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="d9163-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="d9163-257">Registrierungsabfrage wurde behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-257">Fixed registry query</span></span> 
- <span data-ttu-id="d9163-258">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-259">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-259">Known Issues</span></span>
<span data-ttu-id="d9163-260">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-261">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="d9163-262">&ensp;Version des Security Intelligence-Updates: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="d9163-263">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="d9163-264">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="d9163-265">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="d9163-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="d9163-266">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-267">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-267">What's new</span></span>

- <span data-ttu-id="d9163-268">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="d9163-268">Improved logging for scan events</span></span>
- <span data-ttu-id="d9163-269">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="d9163-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="d9163-270">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="d9163-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="d9163-271">AmSI-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="d9163-272">Blockierung der AMSI-Cloud behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="d9163-273">Installationsprotokoll für Sicherheitsupdates behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-274">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-274">Known Issues</span></span>
<span data-ttu-id="d9163-275">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-276">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="d9163-277">&ensp;Version des Security Intelligence-Updates: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="d9163-278">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="d9163-279">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="d9163-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="d9163-280">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="d9163-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="d9163-281">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-282">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-282">What's new</span></span>
- <span data-ttu-id="d9163-283">Verbesserungen bei WDfilter</span><span class="sxs-lookup"><span data-stu-id="d9163-283">WDfilter improvements</span></span>
- <span data-ttu-id="d9163-284">Hinzufügen von ereignisfähigeren Ereignisdaten zum Angriff auf Erkennungsereignisse zur Oberflächenreduzierung</span><span class="sxs-lookup"><span data-stu-id="d9163-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="d9163-285">Informationen zu festen Versionen in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="d9163-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="d9163-286">Falsche Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="d9163-287">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d9163-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="d9163-288">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="d9163-288">UEFI scan capability</span></span>
- <span data-ttu-id="d9163-289">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="d9163-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="d9163-290">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-290">Known Issues</span></span>
<span data-ttu-id="d9163-291">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-292">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="d9163-293">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="d9163-294">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="d9163-295">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="d9163-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="d9163-296">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="d9163-297">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d9163-298">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-298">What's new</span></span>

- <span data-ttu-id="d9163-299">Zu [MpCmdRun hinzugefügte CPU-Einschränkungsoption](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d9163-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="d9163-300">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="d9163-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="d9163-301">Reduzieren des Timeouts für Sicherheitsintelligenz (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="d9163-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="d9163-302">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="d9163-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="d9163-303">Verbessern der Benachrichtigung für prozessblockierung</span><span class="sxs-lookup"><span data-stu-id="d9163-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d9163-304">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-304">Known Issues</span></span>
<span data-ttu-id="d9163-305">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="d9163-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="d9163-306">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="d9163-307">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="d9163-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="d9163-308">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="d9163-309">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="d9163-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="d9163-310">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="d9163-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="d9163-311">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d9163-312">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="d9163-313">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-313">Known Issues</span></span>
<span data-ttu-id="d9163-314">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-315">Januar-2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="d9163-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="d9163-316">Version des Security Intelligence-Updates: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="d9163-317">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="d9163-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="d9163-318">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="d9163-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="d9163-319">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="d9163-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="d9163-320">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="d9163-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d9163-321">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-321">What's new</span></span>

- <span data-ttu-id="d9163-322">Feste BSOD auf WS2016 mit Exchange</span><span class="sxs-lookup"><span data-stu-id="d9163-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="d9163-323">Unterstützen von Plattformupdates, wenn TMP zum Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="d9163-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="d9163-324">Plattform- und Modulversionen werden [WDSI hinzugefügt](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d9163-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="d9163-325">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d9163-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="d9163-326">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="d9163-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d9163-327">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-327">Known Issues</span></span>

<span data-ttu-id="d9163-328">[**Fixed**] Geräte, [die](/windows-hardware/design/device-experiences/modern-standby) den modernen Standbymodus verwenden, können eine Hängerung mit dem Windows Defender-Filtertreibers erleben, was zu einer Schutzlücke führt.</span><span class="sxs-lookup"><span data-stu-id="d9163-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="d9163-329">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischalwareplattform aktualisiert zu sein.</span><span class="sxs-lookup"><span data-stu-id="d9163-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="d9163-330">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="d9163-330">This update is:</span></span>
> - <span data-ttu-id="d9163-331">wird von RS1-Geräten mit niedrigerer Version der Plattform benötigt, um SHA2 zu unterstützen;</span><span class="sxs-lookup"><span data-stu-id="d9163-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="d9163-332">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen.</span><span class="sxs-lookup"><span data-stu-id="d9163-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="d9163-333">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates ersetzt, um die zukünftige Verfügbarkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="d9163-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="d9163-334">wird aufgrund der Neustartanforderung als Update kategorisiert; und</span><span class="sxs-lookup"><span data-stu-id="d9163-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="d9163-335">wird nur mit [Windows Update angeboten.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="d9163-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d9163-336">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="d9163-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="d9163-337">Version des Security Intelligence-Updates: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="d9163-338">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="d9163-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="d9163-339">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="d9163-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="d9163-340">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="d9163-341">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="d9163-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="d9163-342">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="d9163-342">What's new</span></span>

- <span data-ttu-id="d9163-343">Feste MpCmdRun-Ablaufverfolgungsstufe</span><span class="sxs-lookup"><span data-stu-id="d9163-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="d9163-344">Informationen zur WDFilter-Version behoben</span><span class="sxs-lookup"><span data-stu-id="d9163-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="d9163-345">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="d9163-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="d9163-346">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="d9163-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d9163-347">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="d9163-347">Known Issues</span></span>
<span data-ttu-id="d9163-348">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="d9163-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="d9163-349">Unterstützung der Microsoft Defender Antivirus-Plattform</span><span class="sxs-lookup"><span data-stu-id="d9163-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="d9163-350">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d9163-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="d9163-351">Um vollständig unterstützt zu werden, halten Sie die neuesten Plattformupdates auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="d9163-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="d9163-352">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="d9163-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="d9163-353">**Wartungsphase** für Sicherheits- und kritische Updates– Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Anti-Malware-Plattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d9163-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="d9163-354">**Phase des technischen Support (nur)** – Nachdem eine neue Plattformversion veröffentlicht wurde, wird die Unterstützung für ältere Versionen (N-2) auf nur noch technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="d9163-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="d9163-355">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="d9163-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="d9163-356">\* Der technische Support wird weiterhin für Upgrades von der Windows 10-Version (siehe In [Windows 10-Versionen](#platform-version-included-with-windows-10-releases)enthaltene Plattformversion) auf die neueste Plattformversion bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d9163-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="d9163-357">Während der Phase des technischen Support (nur) werden kommerziell angemessene Supportvorfälle über den Microsoft Customer Service & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d9163-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="d9163-358">Wenn für einen Supportvorfall eine Eskalation zur Entwicklung erforderlich ist, ein nicht sicherheitsunsicherheitsupdate erforderlich ist oder ein Sicherheitsupdate erforderlich ist, werden Kunden aufgefordert, ein Upgrade auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu durchführen.</span><span class="sxs-lookup"><span data-stu-id="d9163-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="d9163-359">In Windows 10-Versionen enthaltene Plattformversion</span><span class="sxs-lookup"><span data-stu-id="d9163-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="d9163-360">Die folgende Tabelle enthält die Microsoft Defender Antivirus-Plattform- und Modulversionen, die mit den neuesten Windows 10-Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="d9163-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="d9163-361">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="d9163-361">Windows 10 release</span></span>  |<span data-ttu-id="d9163-362">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="d9163-362">Platform version</span></span>  |<span data-ttu-id="d9163-363">Modulversion</span><span class="sxs-lookup"><span data-stu-id="d9163-363">Engine version</span></span> |<span data-ttu-id="d9163-364">Supportphase</span><span class="sxs-lookup"><span data-stu-id="d9163-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d9163-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="d9163-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="d9163-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="d9163-366">4.18.1909.6</span></span> |<span data-ttu-id="d9163-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="d9163-367">1.1.17000.2</span></span> | <span data-ttu-id="d9163-368">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="d9163-369">1909  (19H2)</span></span> |<span data-ttu-id="d9163-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d9163-370">4.18.1902.5</span></span> |<span data-ttu-id="d9163-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="d9163-371">1.1.16700.3</span></span> | <span data-ttu-id="d9163-372">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="d9163-373">1903  (19H1)</span></span> |<span data-ttu-id="d9163-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d9163-374">4.18.1902.5</span></span> |<span data-ttu-id="d9163-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="d9163-375">1.1.15600.4</span></span> | <span data-ttu-id="d9163-376">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="d9163-377">1809  (RS5)</span></span> |<span data-ttu-id="d9163-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="d9163-378">4.18.1807.18075</span></span> |<span data-ttu-id="d9163-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="d9163-379">1.1.15000.2</span></span> | <span data-ttu-id="d9163-380">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="d9163-381">1803  (RS4)</span></span> |<span data-ttu-id="d9163-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="d9163-382">4.13.17134.1</span></span> |<span data-ttu-id="d9163-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="d9163-383">1.1.14600.4</span></span> | <span data-ttu-id="d9163-384">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="d9163-385">1709  (RS3)</span></span> |<span data-ttu-id="d9163-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="d9163-386">4.12.16299.15</span></span> |<span data-ttu-id="d9163-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="d9163-387">1.1.14104.0</span></span> | <span data-ttu-id="d9163-388">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="d9163-389">1703  (RS2)</span></span> |<span data-ttu-id="d9163-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="d9163-390">4.11.15603.2</span></span> |<span data-ttu-id="d9163-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="d9163-391">1.1.13504.0</span></span> | <span data-ttu-id="d9163-392">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d9163-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="d9163-393">1607 (RS1)</span></span> |<span data-ttu-id="d9163-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="d9163-394">4.10.14393.3683</span></span> |<span data-ttu-id="d9163-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="d9163-395">1.1.12805.0</span></span> | <span data-ttu-id="d9163-396">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="d9163-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="d9163-397">Informationen zur Windows 10-Version finden Sie im [Windows-Lifecycle-Factsheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="d9163-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="d9163-398">Updates für die Bereitstellungsimagewartung und -verwaltung (DISM)</span><span class="sxs-lookup"><span data-stu-id="d9163-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="d9163-399">Es wird empfohlen, Ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 -Betriebssysteminstallationsabbilder mit den neuesten Antiviren- und Antischantischungsupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d9163-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="d9163-400">Wenn Sie Ihre Betriebssysteminstallationsabbilder auf dem neuesten Stand halten, können Sie eine Lücke beim Schutz vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d9163-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="d9163-401">Weitere Informationen finden Sie unter [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="d9163-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="d9163-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="d9163-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="d9163-403">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="d9163-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="d9163-404">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="d9163-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="d9163-405">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="d9163-406">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-407">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-407">Fixes</span></span>
- <span data-ttu-id="d9163-408">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-409">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-409">Additional information</span></span>
- <span data-ttu-id="d9163-410">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="d9163-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="d9163-412">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="d9163-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="d9163-413">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="d9163-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="d9163-414">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d9163-415">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-416">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-416">Fixes</span></span>
- <span data-ttu-id="d9163-417">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-418">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-418">Additional information</span></span>
- <span data-ttu-id="d9163-419">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="d9163-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="d9163-421">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="d9163-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="d9163-422">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d9163-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d9163-423">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d9163-424">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-425">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-425">Fixes</span></span>
- <span data-ttu-id="d9163-426">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-427">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-427">Additional information</span></span>
- <span data-ttu-id="d9163-428">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="d9163-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="d9163-430">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="d9163-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="d9163-431">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d9163-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d9163-432">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d9163-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="d9163-433">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-434">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-434">Fixes</span></span>
- <span data-ttu-id="d9163-435">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-436">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-436">Additional information</span></span>
- <span data-ttu-id="d9163-437">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="d9163-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="d9163-439">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="d9163-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="d9163-440">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d9163-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d9163-441">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d9163-442">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-443">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-443">Fixes</span></span>
- <span data-ttu-id="d9163-444">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-445">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-445">Additional information</span></span>
- <span data-ttu-id="d9163-446">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="d9163-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="d9163-448">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="d9163-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="d9163-449">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d9163-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d9163-450">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d9163-451">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-452">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-452">Fixes</span></span>
- <span data-ttu-id="d9163-453">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-454">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-454">Additional information</span></span>
- <span data-ttu-id="d9163-455">Aktualisierte Microsoft Defender Antivirus-Signaturen</span><span class="sxs-lookup"><span data-stu-id="d9163-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="d9163-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="d9163-457">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d9163-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d9163-458">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d9163-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="d9163-459">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d9163-460">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-461">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-461">Fixes</span></span>
- <span data-ttu-id="d9163-462">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-463">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-463">Additional information</span></span>
- <span data-ttu-id="d9163-464">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d9163-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="d9163-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="d9163-466">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d9163-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d9163-467">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="d9163-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="d9163-468">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d9163-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="d9163-469">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="d9163-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d9163-470">Behebungen</span><span class="sxs-lookup"><span data-stu-id="d9163-470">Fixes</span></span>
- <span data-ttu-id="d9163-471">Keine</span><span class="sxs-lookup"><span data-stu-id="d9163-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d9163-472">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9163-472">Additional information</span></span>
- <span data-ttu-id="d9163-473">Unterstützung für Windows 10 RS1 oder höher Betriebssysteminstallationsabbilder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d9163-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="d9163-474">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d9163-474">Additional resources</span></span>

| <span data-ttu-id="d9163-475">Artikel</span><span class="sxs-lookup"><span data-stu-id="d9163-475">Article</span></span> | <span data-ttu-id="d9163-476">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9163-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="d9163-477">Microsoft Defender Update für Windows-Betriebssysteminstallationsabbilder</span><span class="sxs-lookup"><span data-stu-id="d9163-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="d9163-478">Überprüfen Sie Antischadwareupdatepakete für Ihre Betriebssysteminstallationsabbilder (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="d9163-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="d9163-479">Hier erhalten Sie Microsoft Defender Antivirus-Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019- und Windows Server 2016-Installationsabbilder.</span><span class="sxs-lookup"><span data-stu-id="d9163-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="d9163-480">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="d9163-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d9163-481">Schutzupdates können über viele Quellen zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d9163-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="d9163-482">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="d9163-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="d9163-483">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d9163-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="d9163-484">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="d9163-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="d9163-485">Wenn ein Endpunkt ein Update oder einen geplanten Scan verpasst, können Sie ein Update erzwingen oder bei der nächsten Benutzeran meldet.</span><span class="sxs-lookup"><span data-stu-id="d9163-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="d9163-486">Verwalten ereignisbasierter erzwungener Updates</span><span class="sxs-lookup"><span data-stu-id="d9163-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d9163-487">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten in der Cloud übermittelten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d9163-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="d9163-488">Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="d9163-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="d9163-489">Sie können Einstellungen angeben, z. B. ob Updates für die Akkuleistung erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="d9163-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
