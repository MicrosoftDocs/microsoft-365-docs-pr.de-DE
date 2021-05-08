---
title: Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines
description: Verwalten, Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
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
ms.openlocfilehash: 92f903f750ea5e7f2cb971b535c50bfecced65a2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242312"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="b2206-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines</span><span class="sxs-lookup"><span data-stu-id="b2206-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="b2206-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b2206-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2206-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2206-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="b2206-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b2206-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b2206-108">Es gibt zwei Arten von Updates, die Microsoft Defender Antivirus aktualisiert werden:</span><span class="sxs-lookup"><span data-stu-id="b2206-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="b2206-109">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="b2206-109">Security intelligence updates</span></span>
- <span data-ttu-id="b2206-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="b2206-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2206-111">Die Microsoft Defender Antivirus ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2206-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="b2206-112">Achten Sie darauf, den Antivirenschutz zu aktualisieren, auch wenn Microsoft Defender Antivirus im [passiven Modus ausgeführt wird.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b2206-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="b2206-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="b2206-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="b2206-114">Sicherheitsintelligenzupdates</span><span class="sxs-lookup"><span data-stu-id="b2206-114">Security intelligence updates</span></span>

<span data-ttu-id="b2206-115">Microsoft Defender Antivirus verwendet [von der Cloud](cloud-protection-microsoft-defender-antivirus.md) übermittelten Schutz (auch Microsoft Advanced Protection Service oder MAPS genannt) und lädt regelmäßig Sicherheitsintelligenzupdates herunter, um Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="b2206-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="b2206-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="b2206-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="b2206-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="b2206-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="b2206-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="b2206-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="b2206-119">Der von der Cloud übermittelte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, um zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b2206-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="b2206-120">Sicherheitsintelligenzupdates erfolgen in einer geplanten Schrittfrequenz (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="b2206-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="b2206-121">Weitere Informationen finden Sie unter [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b2206-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b2206-122">Eine Liste der aktuellen Sicherheitsintelligenzupdates finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="b2206-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="b2206-123">Modulupdates sind in Sicherheitsintelligenzupdates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b2206-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="b2206-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="b2206-124">Product updates</span></span>

<span data-ttu-id="b2206-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (auch als Plattformupdates *bezeichnet)* und erhält wichtige Featureupdates neben Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="b2206-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="b2206-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="b2206-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="b2206-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="b2206-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="b2206-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b2206-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="b2206-129">Die übliche Methode, die Sie zum Bereitstellen von Microsoft und Windows für Endpunkte in Ihrem Netzwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2206-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="b2206-130">Weitere Informationen finden Sie unter [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="b2206-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="b2206-131">Monatliche Updates werden in Phasen veröffentlicht, was zu mehreren Paketen führt, die in Ihren [Window Server Update Services angezeigt werden.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="b2206-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="b2206-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="b2206-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="b2206-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update for Windows Defender anmalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="b2206-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="b2206-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="b2206-134">All our updates contain</span></span> 
- <span data-ttu-id="b2206-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="b2206-135">performance improvements;</span></span>
- <span data-ttu-id="b2206-136">Verbesserungen bei der Dienstbarkeit; und</span><span class="sxs-lookup"><span data-stu-id="b2206-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="b2206-137">Integrationsverbesserungen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="b2206-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="b2206-138">April-2021 (Plattform: 4.19.2104.9| Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="b2206-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="b2206-139">&ensp;Version des Security Intelligence-Updates: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="b2206-140">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="b2206-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b2206-141">&ensp;Plattform: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="b2206-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="b2206-142">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="b2206-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="b2206-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-144">What's new</span></span>
- <span data-ttu-id="b2206-145">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="b2206-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="b2206-146">Verbesserte Keyloggererkennung im Kernelmodus</span><span class="sxs-lookup"><span data-stu-id="b2206-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-147">Known Issues</span></span>
<span data-ttu-id="b2206-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-149">März-2021 (Plattform: 4.19.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="b2206-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="b2206-150">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="b2206-151">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="b2206-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b2206-152">&ensp;Plattform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="b2206-153">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="b2206-154">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="b2206-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-155">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-155">What's new</span></span>

- <span data-ttu-id="b2206-156">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="b2206-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="b2206-157">Risikominderungen für Brute-Force-Attack im erweiterten Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b2206-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="b2206-158">Zusätzliche fehlgeschlagene Manipulationsversuchsereignisgenerierung, [wenn Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="b2206-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-159">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-159">Known Issues</span></span>
<span data-ttu-id="b2206-160">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2206-161">Februar-2021 (Plattform: 4.19.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="b2206-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="b2206-162">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="b2206-163">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="b2206-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="b2206-164">&ensp;Plattform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="b2206-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="b2206-165">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="b2206-166">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="b2206-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-167">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-167">What's new</span></span>

- <span data-ttu-id="b2206-168">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b2206-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="b2206-169">Erweitern des Schutzes von Manipulationen</span><span class="sxs-lookup"><span data-stu-id="b2206-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-170">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-170">Known Issues</span></span>
<span data-ttu-id="b2206-171">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="b2206-172">Updates früherer Versionen: Nur support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="b2206-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="b2206-173">Nachdem eine neue Paketversion veröffentlicht wurde, wird die Unterstützung für die beiden vorherigen Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="b2206-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="b2206-174">Versionen, die älter sind als die in diesem Abschnitt aufgeführten, werden nur für technischen Upgradesupport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2206-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="b2206-175">Januar-2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="b2206-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="b2206-176">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b2206-177">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="b2206-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="b2206-178">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="b2206-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="b2206-179">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2206-180">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-181">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-181">What's new</span></span>

- <span data-ttu-id="b2206-182">Verbesserungen bei der Erkennung von Shellcode-Exploits</span><span class="sxs-lookup"><span data-stu-id="b2206-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="b2206-183">Verbesserte Sichtbarkeit für Versuche zum Stehlen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="b2206-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="b2206-184">Verbesserungen bei Antitamperingfeatures in Microsoft Defender Antivirus Diensten</span><span class="sxs-lookup"><span data-stu-id="b2206-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="b2206-185">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="b2206-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="b2206-186">Fix: EDR Sperrbenachrichtigung verbleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die ersterkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="b2206-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-187">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-187">Known Issues</span></span>
<span data-ttu-id="b2206-188">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2206-189">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="b2206-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="b2206-190">&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b2206-191">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="b2206-192">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="b2206-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="b2206-193">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="b2206-194">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-195">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-195">What's new</span></span>

- <span data-ttu-id="b2206-196">Verbesserte [Unterstützung der SmartScreen-Statusprotokollierung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="b2206-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-197">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-197">Known Issues</span></span>
<span data-ttu-id="b2206-198">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2206-199">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="b2206-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="b2206-200">&ensp;Version des Security Intelligence-Updates: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="b2206-201">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="b2206-202">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="b2206-203">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2206-204">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-205">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-205">What's new</span></span>

- <span data-ttu-id="b2206-206">Neue Beschreibungen für spezielle Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="b2206-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="b2206-207">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b2206-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="b2206-208">Verbesserte Funktionen zum Zulassen/Blockieren von Hostadressen</span><span class="sxs-lookup"><span data-stu-id="b2206-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="b2206-209">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="b2206-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-210">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-210">Known Issues</span></span>

<span data-ttu-id="b2206-211">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2206-212">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="b2206-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="b2206-213">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="b2206-214">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="b2206-215">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="b2206-216">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="b2206-217">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-218">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-218">What's new</span></span>

- <span data-ttu-id="b2206-219">Administratorberechtigungen sind erforderlich, um Dateien in Quarantäne wiederherzustellen</span><span class="sxs-lookup"><span data-stu-id="b2206-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="b2206-220">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="b2206-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="b2206-221">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="b2206-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="b2206-222">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="b2206-222">New management interfaces for:</span></span>
   - <span data-ttu-id="b2206-223">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="b2206-223">UDP Inspection</span></span>
   - <span data-ttu-id="b2206-224">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="b2206-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="b2206-225">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="b2206-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="b2206-226">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="b2206-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="b2206-227">Verbesserte überprüfung Office VBA-Moduls</span><span class="sxs-lookup"><span data-stu-id="b2206-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-228">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-228">Known Issues</span></span>

<span data-ttu-id="b2206-229">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="b2206-230">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="b2206-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="b2206-231">&ensp;Updateversion der Sicherheitsintelligenz: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="b2206-232">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="b2206-233">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="b2206-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="b2206-234">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="b2206-235">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="b2206-236">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-236">What's new</span></span>

- <span data-ttu-id="b2206-237">Hinzufügen von weiteren Telemetrieereignissen</span><span class="sxs-lookup"><span data-stu-id="b2206-237">Add more telemetry events</span></span>
- <span data-ttu-id="b2206-238">Verbesserte Telemetrie des Scanereigniss</span><span class="sxs-lookup"><span data-stu-id="b2206-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="b2206-239">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="b2206-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="b2206-240">Verbesserte Überprüfung von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="b2206-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="b2206-241">Hinzugefügt `AMRunningMode` zu Get-MpComputerStatus PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b2206-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="b2206-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b2206-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="b2206-243">Microsoft Defender Antivirus automatisch deaktiviert, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="b2206-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="b2206-244">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-244">Known Issues</span></span>
<span data-ttu-id="b2206-245">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-246">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="b2206-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="b2206-247">&ensp;Version des Security Intelligence-Updates: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="b2206-248">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="b2206-249">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="b2206-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="b2206-250">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="b2206-251">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-252">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-252">What's new</span></span>

- <span data-ttu-id="b2206-253">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="b2206-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="b2206-254">Verbesserte Validierung von Authenticode-Codesignaturzertifikaten</span><span class="sxs-lookup"><span data-stu-id="b2206-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-255">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-255">Known Issues</span></span>
<span data-ttu-id="b2206-256">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-257">Juni-2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="b2206-258">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="b2206-259">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="b2206-260">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="b2206-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="b2206-261">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="b2206-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="b2206-262">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-263">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-263">What's new</span></span>

- <span data-ttu-id="b2206-264">Möglichkeit zum Angeben des [Speicherorts der Supportprotokolle](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="b2206-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="b2206-265">Überspringen der aggressiven Nachholscan im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="b2206-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="b2206-266">Zulassen, dass Defender bei gemessenen Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="b2206-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="b2206-267">Leistungsoptimierung behoben, wenn die Zwischenspeicherung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="b2206-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="b2206-268">Registrierungsabfrage wurde behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-268">Fixed registry query</span></span> 
- <span data-ttu-id="b2206-269">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-270">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-270">Known Issues</span></span>
<span data-ttu-id="b2206-271">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-272">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="b2206-273">&ensp;Version des Security Intelligence-Updates: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="b2206-274">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="b2206-275">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="b2206-276">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="b2206-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="b2206-277">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-278">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-278">What's new</span></span>

- <span data-ttu-id="b2206-279">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="b2206-279">Improved logging for scan events</span></span>
- <span data-ttu-id="b2206-280">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="b2206-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="b2206-281">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="b2206-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="b2206-282">AmSI-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="b2206-283">Blockierung der AMSI-Cloud behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="b2206-284">Installationsprotokoll für Sicherheitsupdates behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-285">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-285">Known Issues</span></span>
<span data-ttu-id="b2206-286">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-287">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="b2206-288">&ensp;Version des Security Intelligence-Updates: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="b2206-289">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="b2206-290">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="b2206-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="b2206-291">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="b2206-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="b2206-292">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-293">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-293">What's new</span></span>
- <span data-ttu-id="b2206-294">Verbesserungen bei WDfilter</span><span class="sxs-lookup"><span data-stu-id="b2206-294">WDfilter improvements</span></span>
- <span data-ttu-id="b2206-295">Hinzufügen von ereignisfähigeren Ereignisdaten zum Angriff auf Erkennungsereignisse zur Oberflächenreduzierung</span><span class="sxs-lookup"><span data-stu-id="b2206-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="b2206-296">Informationen zu festen Versionen in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="b2206-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="b2206-297">Falsche Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="b2206-298">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b2206-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="b2206-299">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="b2206-299">UEFI scan capability</span></span>
- <span data-ttu-id="b2206-300">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="b2206-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2206-301">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-301">Known Issues</span></span>
<span data-ttu-id="b2206-302">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-303">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="b2206-304">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="b2206-305">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="b2206-306">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="b2206-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="b2206-307">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="b2206-308">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2206-309">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-309">What's new</span></span>

- <span data-ttu-id="b2206-310">Zu [MpCmdRun hinzugefügte CPU-Einschränkungsoption](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b2206-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="b2206-311">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="b2206-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="b2206-312">Reduzieren des Timeouts für Sicherheitsintelligenz (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="b2206-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="b2206-313">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="b2206-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="b2206-314">Verbessern der Benachrichtigung für prozessblockierung</span><span class="sxs-lookup"><span data-stu-id="b2206-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2206-315">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-315">Known Issues</span></span>
<span data-ttu-id="b2206-316">[**Fixed**] Microsoft Defender Antivirus beim Ausführen einer Überprüfung werden Dateien übersprungen.</span><span class="sxs-lookup"><span data-stu-id="b2206-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="b2206-317">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="b2206-318">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="b2206-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="b2206-319">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="b2206-320">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="b2206-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="b2206-321">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="b2206-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="b2206-322">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b2206-323">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="b2206-324">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-324">Known Issues</span></span>
<span data-ttu-id="b2206-325">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-326">Januar-2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="b2206-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="b2206-327">Version des Security Intelligence-Updates: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="b2206-328">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="b2206-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="b2206-329">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="b2206-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="b2206-330">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="b2206-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="b2206-331">&ensp;Supportphase: **Support für technische Upgrades (nur)**</span><span class="sxs-lookup"><span data-stu-id="b2206-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b2206-332">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-332">What's new</span></span>

- <span data-ttu-id="b2206-333">BSOD auf WS2016 mit Exchange</span><span class="sxs-lookup"><span data-stu-id="b2206-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="b2206-334">Unterstützen von Plattformupdates, wenn TMP zum Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="b2206-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="b2206-335">Plattform- und Modulversionen werden [WDSI hinzugefügt](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="b2206-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="b2206-336">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b2206-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="b2206-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="b2206-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2206-338">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-338">Known Issues</span></span>

<span data-ttu-id="b2206-339">[**Fixed**] Geräte, [die](/windows-hardware/design/device-experiences/modern-standby) den modernen Standbymodus verwenden, können mit dem Windows Defender-Filtertreibers hängen, was zu einer Schutzlücke führt.</span><span class="sxs-lookup"><span data-stu-id="b2206-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="b2206-340">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischalwareplattform aktualisiert zu sein.</span><span class="sxs-lookup"><span data-stu-id="b2206-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="b2206-341">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="b2206-341">This update is:</span></span>
> - <span data-ttu-id="b2206-342">wird von RS1-Geräten mit niedrigerer Version der Plattform benötigt, um SHA2 zu unterstützen;</span><span class="sxs-lookup"><span data-stu-id="b2206-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="b2206-343">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen.</span><span class="sxs-lookup"><span data-stu-id="b2206-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="b2206-344">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates ersetzt, um die zukünftige Verfügbarkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="b2206-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="b2206-345">wird aufgrund der Neustartanforderung als Update kategorisiert; und</span><span class="sxs-lookup"><span data-stu-id="b2206-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="b2206-346">wird nur mit dem [update Windows angeboten.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="b2206-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2206-347">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="b2206-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="b2206-348">Version des Security Intelligence-Updates: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="b2206-349">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="b2206-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="b2206-350">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="b2206-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="b2206-351">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="b2206-352">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="b2206-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="b2206-353">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="b2206-353">What's new</span></span>

- <span data-ttu-id="b2206-354">Feste MpCmdRun-Ablaufverfolgungsstufe</span><span class="sxs-lookup"><span data-stu-id="b2206-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="b2206-355">Informationen zur WDFilter-Version behoben</span><span class="sxs-lookup"><span data-stu-id="b2206-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="b2206-356">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="b2206-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="b2206-357">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="b2206-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2206-358">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b2206-358">Known Issues</span></span>
<span data-ttu-id="b2206-359">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="b2206-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="b2206-360">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="b2206-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="b2206-361">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2206-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="b2206-362">Um vollständig unterstützt zu werden, halten Sie die neuesten Plattformupdates auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="b2206-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="b2206-363">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="b2206-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="b2206-364">**Wartungsphase** für Sicherheits- und kritische Updates– Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Anti-Malware-Plattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b2206-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="b2206-365">**Phase des technischen Support (nur)** – Nachdem eine neue Plattformversion veröffentlicht wurde, wird die Unterstützung für ältere Versionen (N-2) auf nur noch technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="b2206-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="b2206-366">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="b2206-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="b2206-367">\*Der technische Support wird weiterhin für Upgrades von der Windows 10-Version (siehe Plattformversion, die in [Windows 10](#platform-version-included-with-windows-10-releases)Versionen enthalten ist) auf die neueste Plattformversion bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2206-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="b2206-368">Während der Phase des technischen Support (nur) werden kommerziell angemessene Supportvorfälle über den Microsoft Customer Service & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2206-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="b2206-369">Wenn für einen Supportvorfall eine Eskalation zur Entwicklung erforderlich ist, ein nicht sicherheitsunsicherheitsupdate erforderlich ist oder ein Sicherheitsupdate erforderlich ist, werden Kunden aufgefordert, ein Upgrade auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu durchführen.</span><span class="sxs-lookup"><span data-stu-id="b2206-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="b2206-370">Plattformversion, die in Windows 10 enthalten ist</span><span class="sxs-lookup"><span data-stu-id="b2206-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="b2206-371">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Versionen der Windows 10 ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="b2206-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="b2206-372">Windows 10 Release</span><span class="sxs-lookup"><span data-stu-id="b2206-372">Windows 10 release</span></span>  |<span data-ttu-id="b2206-373">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="b2206-373">Platform version</span></span>  |<span data-ttu-id="b2206-374">Modulversion</span><span class="sxs-lookup"><span data-stu-id="b2206-374">Engine version</span></span> |<span data-ttu-id="b2206-375">Supportphase</span><span class="sxs-lookup"><span data-stu-id="b2206-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b2206-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="b2206-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="b2206-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="b2206-377">4.18.1909.6</span></span> |<span data-ttu-id="b2206-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="b2206-378">1.1.17000.2</span></span> | <span data-ttu-id="b2206-379">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="b2206-380">1909  (19H2)</span></span> |<span data-ttu-id="b2206-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b2206-381">4.18.1902.5</span></span> |<span data-ttu-id="b2206-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="b2206-382">1.1.16700.3</span></span> | <span data-ttu-id="b2206-383">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="b2206-384">1903  (19H1)</span></span> |<span data-ttu-id="b2206-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b2206-385">4.18.1902.5</span></span> |<span data-ttu-id="b2206-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="b2206-386">1.1.15600.4</span></span> | <span data-ttu-id="b2206-387">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="b2206-388">1809  (RS5)</span></span> |<span data-ttu-id="b2206-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="b2206-389">4.18.1807.18075</span></span> |<span data-ttu-id="b2206-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="b2206-390">1.1.15000.2</span></span> | <span data-ttu-id="b2206-391">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="b2206-392">1803  (RS4)</span></span> |<span data-ttu-id="b2206-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="b2206-393">4.13.17134.1</span></span> |<span data-ttu-id="b2206-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="b2206-394">1.1.14600.4</span></span> | <span data-ttu-id="b2206-395">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="b2206-396">1709  (RS3)</span></span> |<span data-ttu-id="b2206-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="b2206-397">4.12.16299.15</span></span> |<span data-ttu-id="b2206-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="b2206-398">1.1.14104.0</span></span> | <span data-ttu-id="b2206-399">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="b2206-400">1703  (RS2)</span></span> |<span data-ttu-id="b2206-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="b2206-401">4.11.15603.2</span></span> |<span data-ttu-id="b2206-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="b2206-402">1.1.13504.0</span></span> | <span data-ttu-id="b2206-403">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2206-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="b2206-404">1607 (RS1)</span></span> |<span data-ttu-id="b2206-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="b2206-405">4.10.14393.3683</span></span> |<span data-ttu-id="b2206-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="b2206-406">1.1.12805.0</span></span> | <span data-ttu-id="b2206-407">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="b2206-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="b2206-408">Informationen Windows 10 Veröffentlichung finden Sie im [Windows-Lifecycle-Factsheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="b2206-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="b2206-409">Updates für die Bereitstellungsimagewartung und -verwaltung (DISM)</span><span class="sxs-lookup"><span data-stu-id="b2206-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="b2206-410">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsabbilder mit den neuesten Antiviren- und Antischalwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b2206-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="b2206-411">Wenn Sie Ihre Betriebssysteminstallationsabbilder auf dem neuesten Stand halten, können Sie eine Lücke beim Schutz vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b2206-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="b2206-412">Weitere Informationen finden Sie unter [Microsoft Defender update for Windows installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="b2206-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="b2206-413">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="b2206-413">1.1.2104.01</span></span></summary>

<span data-ttu-id="b2206-414">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="b2206-414">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="b2206-415">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="b2206-415">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="b2206-416">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-416">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="b2206-417">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-417">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-418">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-418">Fixes</span></span>
- <span data-ttu-id="b2206-419">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-420">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-420">Additional information</span></span>
- <span data-ttu-id="b2206-421">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-422">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="b2206-422">1.1.2103.01</span></span></summary>

<span data-ttu-id="b2206-423">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="b2206-423">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="b2206-424">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="b2206-424">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="b2206-425">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-425">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2206-426">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-426">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-427">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-427">Fixes</span></span>
- <span data-ttu-id="b2206-428">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-429">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-429">Additional information</span></span>
- <span data-ttu-id="b2206-430">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-431">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="b2206-431">1.1.2102.03</span></span></summary>

<span data-ttu-id="b2206-432">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="b2206-432">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="b2206-433">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b2206-433">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b2206-434">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2206-435">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-435">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-436">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-436">Fixes</span></span>
- <span data-ttu-id="b2206-437">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-438">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-438">Additional information</span></span>
- <span data-ttu-id="b2206-439">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-440">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="b2206-440">1.1.2101.02</span></span></summary>

<span data-ttu-id="b2206-441">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="b2206-441">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="b2206-442">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b2206-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b2206-443">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b2206-443">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="b2206-444">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-444">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-445">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-445">Fixes</span></span>
- <span data-ttu-id="b2206-446">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-447">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-447">Additional information</span></span>
- <span data-ttu-id="b2206-448">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-449">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="b2206-449">1.1.2012.01</span></span></summary>

<span data-ttu-id="b2206-450">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="b2206-450">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="b2206-451">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b2206-451">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b2206-452">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-452">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2206-453">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-453">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-454">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-454">Fixes</span></span>
- <span data-ttu-id="b2206-455">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-456">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-456">Additional information</span></span>
- <span data-ttu-id="b2206-457">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-458">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="b2206-458">1.1.2011.02</span></span></summary>

<span data-ttu-id="b2206-459">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="b2206-459">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="b2206-460">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b2206-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b2206-461">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2206-462">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-462">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-463">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-463">Fixes</span></span>
- <span data-ttu-id="b2206-464">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-465">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-465">Additional information</span></span>
- <span data-ttu-id="b2206-466">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="b2206-466">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-467">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="b2206-467">1.1.2011.01</span></span></summary>

<span data-ttu-id="b2206-468">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b2206-468">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b2206-469">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b2206-469">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="b2206-470">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2206-471">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-471">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-472">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-472">Fixes</span></span>
- <span data-ttu-id="b2206-473">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-474">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-474">Additional information</span></span>
- <span data-ttu-id="b2206-475">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2206-476">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="b2206-476">1.1.2009.10</span></span></summary>

<span data-ttu-id="b2206-477">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b2206-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b2206-478">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="b2206-478">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="b2206-479">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b2206-479">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="b2206-480">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="b2206-480">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2206-481">Behebungen</span><span class="sxs-lookup"><span data-stu-id="b2206-481">Fixes</span></span>
- <span data-ttu-id="b2206-482">Keine</span><span class="sxs-lookup"><span data-stu-id="b2206-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2206-483">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2206-483">Additional information</span></span>
- <span data-ttu-id="b2206-484">Unterstützung für Windows 10 RS1 oder höher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b2206-484">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="b2206-485">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b2206-485">Additional resources</span></span>

| <span data-ttu-id="b2206-486">Artikel</span><span class="sxs-lookup"><span data-stu-id="b2206-486">Article</span></span> | <span data-ttu-id="b2206-487">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2206-487">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="b2206-488">Microsoft Defender Update für Windows Betriebssysteminstallationsabbilder</span><span class="sxs-lookup"><span data-stu-id="b2206-488">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="b2206-489">Überprüfen Sie Antischadwareupdatepakete für Ihre Betriebssysteminstallationsabbilder (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="b2206-489">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="b2206-490">Erhalten Microsoft Defender Antivirus Updates für Windows 10 (Enterprise, Pro und Home-Editionen), Windows Server 2019 und Windows Server 2016 Installationsabbilder.</span><span class="sxs-lookup"><span data-stu-id="b2206-490">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="b2206-491">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="b2206-491">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b2206-492">Schutzupdates können über viele Quellen zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2206-492">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="b2206-493">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="b2206-493">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="b2206-494">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2206-494">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="b2206-495">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="b2206-495">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="b2206-496">Wenn ein Endpunkt ein Update oder einen geplanten Scan verpasst, können Sie ein Update erzwingen oder bei der nächsten Benutzeran meldet.</span><span class="sxs-lookup"><span data-stu-id="b2206-496">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="b2206-497">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="b2206-497">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b2206-498">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten in der Cloud übermittelten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b2206-498">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="b2206-499">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="b2206-499">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="b2206-500">Sie können Einstellungen angeben, z. B. ob Updates für die Akkuleistung erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2206-500">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
