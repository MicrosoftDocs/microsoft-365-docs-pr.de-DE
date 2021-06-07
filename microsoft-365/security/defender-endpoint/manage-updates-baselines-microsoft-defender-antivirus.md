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
ms.date: 06/03/2021
ms.openlocfilehash: e67f783552cca5cc36c1563f5e5557796028ea18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772017"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="255d2-104">Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen</span><span class="sxs-lookup"><span data-stu-id="255d2-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="255d2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="255d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="255d2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="255d2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="255d2-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="255d2-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="255d2-108">Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:</span><span class="sxs-lookup"><span data-stu-id="255d2-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="255d2-109">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="255d2-109">Security intelligence updates</span></span>
- <span data-ttu-id="255d2-110">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="255d2-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="255d2-111">Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="255d2-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="255d2-112">Aktualisieren Sie den Virenschutz auch dann, wenn Microsoft Defender Antivirus im [passiven Modus](./microsoft-defender-antivirus-compatibility.md)ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="255d2-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="255d2-113">Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="255d2-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="255d2-114">Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="255d2-114">Security intelligence updates</span></span>

<span data-ttu-id="255d2-115">Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="255d2-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="255d2-116">Updates werden unter den folgenden KB-Nummern veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="255d2-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="255d2-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="255d2-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="255d2-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="255d2-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="255d2-119">Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="255d2-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="255d2-120">Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="255d2-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="255d2-121">Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="255d2-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="255d2-122">Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="255d2-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="255d2-123">Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="255d2-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="255d2-124">Produktupdates</span><span class="sxs-lookup"><span data-stu-id="255d2-124">Product updates</span></span>

<span data-ttu-id="255d2-125">Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.</span><span class="sxs-lookup"><span data-stu-id="255d2-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="255d2-126">Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten:</span><span class="sxs-lookup"><span data-stu-id="255d2-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="255d2-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="255d2-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="255d2-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="255d2-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="255d2-129">Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="255d2-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="255d2-130">Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="255d2-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="255d2-131">Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="255d2-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="255d2-132">Monatliche Plattform- und Modulversionen</span><span class="sxs-lookup"><span data-stu-id="255d2-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="255d2-133">Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="255d2-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="255d2-134">Alle unsere Updates enthalten</span><span class="sxs-lookup"><span data-stu-id="255d2-134">All our updates contain</span></span> 
- <span data-ttu-id="255d2-135">Leistungsverbesserungen;</span><span class="sxs-lookup"><span data-stu-id="255d2-135">performance improvements;</span></span>
- <span data-ttu-id="255d2-136">Verbesserungen der Dienstbarkeit; Und</span><span class="sxs-lookup"><span data-stu-id="255d2-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="255d2-137">Integrationsverbesserungen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="255d2-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="255d2-138">April-2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="255d2-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="255d2-139">&ensp;Security Intelligence Update Version: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="255d2-140">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="255d2-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="255d2-141">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="255d2-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="255d2-142">&ensp;Modul: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="255d2-143">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="255d2-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-144">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-144">What's new</span></span>
- <span data-ttu-id="255d2-145">Zusätzliche Verhaltensüberwachungslogik</span><span class="sxs-lookup"><span data-stu-id="255d2-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="255d2-146">Verbesserte Kernelmodus-Keyloggererkennung</span><span class="sxs-lookup"><span data-stu-id="255d2-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-147">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-147">Known Issues</span></span>
<span data-ttu-id="255d2-148">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-149">März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="255d2-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="255d2-150">&ensp;Version des Security Intelligence-Updates: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="255d2-151">&ensp;Veröffentlicht: **1. April 2021**</span><span class="sxs-lookup"><span data-stu-id="255d2-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="255d2-152">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="255d2-153">&ensp;Modul: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="255d2-154">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="255d2-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-155">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-155">What's new</span></span>

- <span data-ttu-id="255d2-156">Verbesserung des Verhaltensüberwachungsmoduls</span><span class="sxs-lookup"><span data-stu-id="255d2-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="255d2-157">Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="255d2-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="255d2-158">Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="255d2-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-159">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-159">Known Issues</span></span>
<span data-ttu-id="255d2-160">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="255d2-161">Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="255d2-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="255d2-162">&ensp;Version des Security Intelligence-Updates: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="255d2-163">&ensp;Veröffentlicht: **9. März 2021**</span><span class="sxs-lookup"><span data-stu-id="255d2-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="255d2-164">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="255d2-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="255d2-165">&ensp;Modul: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="255d2-166">&ensp;Supportphase: **Sicherheits- und kritische Updates**</span><span class="sxs-lookup"><span data-stu-id="255d2-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-167">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-167">What's new</span></span>

- <span data-ttu-id="255d2-168">Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="255d2-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="255d2-169">Erweitern des Umfangs des Manipulationsschutzes</span><span class="sxs-lookup"><span data-stu-id="255d2-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-170">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-170">Known Issues</span></span>
<span data-ttu-id="255d2-171">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="255d2-172">Frühere Versionsupdates: Nur Support für technische Upgrades</span><span class="sxs-lookup"><span data-stu-id="255d2-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="255d2-173">Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="255d2-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="255d2-174">Ältere Versionen sind in diesem Abschnitt aufgeführt und werden nur für technischen Upgrade-Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="255d2-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="255d2-175">Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="255d2-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="255d2-176">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="255d2-177">&ensp;Veröffentlicht: **2. Februar 2021**</span><span class="sxs-lookup"><span data-stu-id="255d2-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="255d2-178">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="255d2-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="255d2-179">&ensp;Modul: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="255d2-180">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-181">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-181">What's new</span></span>

- <span data-ttu-id="255d2-182">Verbesserungen bei der Shellcode-Exploit-Erkennung</span><span class="sxs-lookup"><span data-stu-id="255d2-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="255d2-183">Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="255d2-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="255d2-184">Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten</span><span class="sxs-lookup"><span data-stu-id="255d2-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="255d2-185">Verbesserte Unterstützung für ARM x64-Emulation</span><span class="sxs-lookup"><span data-stu-id="255d2-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="255d2-186">Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat</span><span class="sxs-lookup"><span data-stu-id="255d2-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-187">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-187">Known Issues</span></span>
<span data-ttu-id="255d2-188">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="255d2-189">November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="255d2-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="255d2-190">&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="255d2-191">&ensp;Veröffentlicht: **03. Dezember 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="255d2-192">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="255d2-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="255d2-193">&ensp;Modul: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="255d2-194">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-195">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-195">What's new</span></span>

- <span data-ttu-id="255d2-196">Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung</span><span class="sxs-lookup"><span data-stu-id="255d2-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-197">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-197">Known Issues</span></span>
<span data-ttu-id="255d2-198">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="255d2-199">Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="255d2-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="255d2-200">&ensp;Security Intelligence Update-Version: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="255d2-201">&ensp;Veröffentlicht: **29. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="255d2-202">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="255d2-203">&ensp;Modul: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="255d2-204">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-205">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-205">What's new</span></span>

- <span data-ttu-id="255d2-206">Neue Beschreibungen für besondere Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="255d2-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="255d2-207">Verbesserte Emulationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="255d2-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="255d2-208">Verbesserte Hostadressen-Allow/Block-Funktionen</span><span class="sxs-lookup"><span data-stu-id="255d2-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="255d2-209">Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse</span><span class="sxs-lookup"><span data-stu-id="255d2-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-210">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-210">Known Issues</span></span>

<span data-ttu-id="255d2-211">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="255d2-212">September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="255d2-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="255d2-213">&ensp;Version des Security Intelligence-Updates: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="255d2-214">&ensp;Veröffentlicht: **01. Oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="255d2-215">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="255d2-216">&ensp;Modul: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="255d2-217">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-218">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-218">What's new</span></span>

- <span data-ttu-id="255d2-219">Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="255d2-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="255d2-220">XML-formatierte Ereignisse werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="255d2-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="255d2-221">CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen</span><span class="sxs-lookup"><span data-stu-id="255d2-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="255d2-222">Neue Verwaltungsschnittstellen für:</span><span class="sxs-lookup"><span data-stu-id="255d2-222">New management interfaces for:</span></span>
   - <span data-ttu-id="255d2-223">UDP-Prüfung</span><span class="sxs-lookup"><span data-stu-id="255d2-223">UDP Inspection</span></span>
   - <span data-ttu-id="255d2-224">Netzwerkschutz auf Server 2019</span><span class="sxs-lookup"><span data-stu-id="255d2-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="255d2-225">IP-Adressausschlüsse für Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="255d2-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="255d2-226">Verbesserte Sichtbarkeit von TPM-Messungen</span><span class="sxs-lookup"><span data-stu-id="255d2-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="255d2-227">Verbesserte Office VBA-Modulüberprüfung</span><span class="sxs-lookup"><span data-stu-id="255d2-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-228">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-228">Known Issues</span></span>

<span data-ttu-id="255d2-229">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="255d2-230">August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="255d2-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="255d2-231">&ensp;Security Intelligence-Updateversion: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="255d2-232">&ensp;Veröffentlicht: **27. August 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="255d2-233">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="255d2-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="255d2-234">&ensp;Modul: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="255d2-235">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="255d2-236">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-236">What's new</span></span>

- <span data-ttu-id="255d2-237">Hinzufügen weiterer Telemetrieereignisse</span><span class="sxs-lookup"><span data-stu-id="255d2-237">Add more telemetry events</span></span>
- <span data-ttu-id="255d2-238">Verbesserte Telemetrie für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="255d2-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="255d2-239">Verbesserte Verhaltensüberwachung für Speicherscans</span><span class="sxs-lookup"><span data-stu-id="255d2-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="255d2-240">Verbessertes Scannen von Makrodatenströmen</span><span class="sxs-lookup"><span data-stu-id="255d2-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="255d2-241">`AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="255d2-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="255d2-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="255d2-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="255d2-243">Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="255d2-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="255d2-244">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-244">Known Issues</span></span>
<span data-ttu-id="255d2-245">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-246">Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="255d2-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="255d2-247">&ensp;Security Intelligence Update-Version: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="255d2-248">&ensp;Veröffentlicht: **28. Juli 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="255d2-249">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="255d2-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="255d2-250">&ensp;Modul: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="255d2-251">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-252">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-252">What's new</span></span>

- <span data-ttu-id="255d2-253">Verbesserte Telemetrie für BITS</span><span class="sxs-lookup"><span data-stu-id="255d2-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="255d2-254">Verbesserte Authenticode-Codesignaturzertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="255d2-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-255">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-255">Known Issues</span></span>
<span data-ttu-id="255d2-256">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-257">Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="255d2-258">&ensp;Version des Security Intelligence-Updates: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="255d2-259">&ensp;Veröffentlicht: **22. Juni 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="255d2-260">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="255d2-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="255d2-261">&ensp;Modul: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="255d2-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="255d2-262">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-263">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-263">What's new</span></span>

- <span data-ttu-id="255d2-264">Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben</span><span class="sxs-lookup"><span data-stu-id="255d2-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="255d2-265">Überspringen des aggressiven Nachholscans im passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="255d2-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="255d2-266">Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="255d2-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="255d2-267">Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung</span><span class="sxs-lookup"><span data-stu-id="255d2-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="255d2-268">Feste Registrierungsabfrage</span><span class="sxs-lookup"><span data-stu-id="255d2-268">Fixed registry query</span></span> 
- <span data-ttu-id="255d2-269">Randomisierung der Scanzeit in ADMX behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-270">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-270">Known Issues</span></span>
<span data-ttu-id="255d2-271">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-272">Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="255d2-273">&ensp;Security Intelligence Update-Version: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="255d2-274">&ensp;Veröffentlicht: **26. Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="255d2-275">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="255d2-276">&ensp;Modul: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="255d2-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="255d2-277">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-278">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-278">What's new</span></span>

- <span data-ttu-id="255d2-279">Verbesserte Protokollierung für Scanereignisse</span><span class="sxs-lookup"><span data-stu-id="255d2-279">Improved logging for scan events</span></span>
- <span data-ttu-id="255d2-280">Verbesserte Absturzbehandlung im Benutzermodus.</span><span class="sxs-lookup"><span data-stu-id="255d2-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="255d2-281">Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="255d2-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="255d2-282">Amsi-Beispielübermittlung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="255d2-283">Amsi Cloud-Blockierung wurde behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="255d2-284">Installationsprotokoll für feste Sicherheitsupdates</span><span class="sxs-lookup"><span data-stu-id="255d2-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-285">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-285">Known Issues</span></span>
<span data-ttu-id="255d2-286">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-287">April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="255d2-288">&ensp;Security Intelligence Update-Version: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="255d2-289">&ensp;Veröffentlicht: **30. April 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="255d2-290">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="255d2-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="255d2-291">&ensp;Modul: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="255d2-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="255d2-292">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-293">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-293">What's new</span></span>
- <span data-ttu-id="255d2-294">WDfilter-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="255d2-294">WDfilter improvements</span></span>
- <span data-ttu-id="255d2-295">Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="255d2-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="255d2-296">Informationen zur festen Version in Diagnosedaten und WMI</span><span class="sxs-lookup"><span data-stu-id="255d2-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="255d2-297">Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="255d2-298">Dynamic URL intel for Fileless Threat Protection</span><span class="sxs-lookup"><span data-stu-id="255d2-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="255d2-299">UEFI-Scanfunktion</span><span class="sxs-lookup"><span data-stu-id="255d2-299">UEFI scan capability</span></span>
- <span data-ttu-id="255d2-300">Erweitern der Protokollierung für Updates</span><span class="sxs-lookup"><span data-stu-id="255d2-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="255d2-301">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-301">Known Issues</span></span>
<span data-ttu-id="255d2-302">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-303">März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="255d2-304">&ensp;Version des Security Intelligence-Updates: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="255d2-305">&ensp;Veröffentlicht: **24. März 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="255d2-306">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="255d2-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="255d2-307">&ensp;Modul: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="255d2-308">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="255d2-309">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-309">What's new</span></span>

- <span data-ttu-id="255d2-310">CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="255d2-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="255d2-311">Verbessern der Diagnosefunktion</span><span class="sxs-lookup"><span data-stu-id="255d2-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="255d2-312">Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)</span><span class="sxs-lookup"><span data-stu-id="255d2-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="255d2-313">Erweitern der internen Protokollfunktion des AMSI-Moduls</span><span class="sxs-lookup"><span data-stu-id="255d2-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="255d2-314">Verbessern der Benachrichtigung für das Blockieren von Prozessen</span><span class="sxs-lookup"><span data-stu-id="255d2-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="255d2-315">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-315">Known Issues</span></span>
<span data-ttu-id="255d2-316">[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="255d2-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="255d2-317">Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="255d2-318">&ensp;Version des Security Intelligence-Updates: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="255d2-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="255d2-319">&ensp;Veröffentlicht: **25. Februar 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="255d2-320">&ensp;Plattform/Client: **-**</span><span class="sxs-lookup"><span data-stu-id="255d2-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="255d2-321">&ensp;Modul: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="255d2-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="255d2-322">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="255d2-323">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="255d2-324">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-324">Known Issues</span></span>
<span data-ttu-id="255d2-325">Keine bekannten Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-326">Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="255d2-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="255d2-327">Security Intelligence Update-Version: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="255d2-328">Veröffentlicht: **30. Januar 2020**</span><span class="sxs-lookup"><span data-stu-id="255d2-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="255d2-329">Plattform/Client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="255d2-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="255d2-330">Modul: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="255d2-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="255d2-331">&ensp;Supportphase: **Technischer Upgrade-Support (nur)**</span><span class="sxs-lookup"><span data-stu-id="255d2-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="255d2-332">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-332">What's new</span></span>

- <span data-ttu-id="255d2-333">BSOD in WS2016 mit Exchange behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="255d2-334">Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="255d2-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="255d2-335">Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="255d2-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="255d2-336">Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="255d2-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="255d2-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="255d2-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="255d2-338">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-338">Known Issues</span></span>

<span data-ttu-id="255d2-339">[**Behoben**] Geräte, die den [modernen Standbymodus verwenden,](/windows-hardware/design/device-experiences/modern-standby) können mit dem Windows Defender Filtertreiber hängen bleiben, was zu einer Schutzlücke führt.</span><span class="sxs-lookup"><span data-stu-id="255d2-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="255d2-340">Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="255d2-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="255d2-341">Dieses Update ist:</span><span class="sxs-lookup"><span data-stu-id="255d2-341">This update is:</span></span>
> - <span data-ttu-id="255d2-342">von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;</span><span class="sxs-lookup"><span data-stu-id="255d2-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="255d2-343">verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;</span><span class="sxs-lookup"><span data-stu-id="255d2-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="255d2-344">wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;</span><span class="sxs-lookup"><span data-stu-id="255d2-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="255d2-345">wird aufgrund der Neustartanforderung als Update kategorisiert; Und</span><span class="sxs-lookup"><span data-stu-id="255d2-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="255d2-346">wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.</span><span class="sxs-lookup"><span data-stu-id="255d2-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="255d2-347">November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="255d2-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="255d2-348">Security Intelligence Update-Version: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="255d2-349">Veröffentlicht: **7. Dezember 2019**</span><span class="sxs-lookup"><span data-stu-id="255d2-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="255d2-350">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="255d2-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="255d2-351">Modul: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="255d2-352">Supportphase: **Keine Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="255d2-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="255d2-353">Neuerungen</span><span class="sxs-lookup"><span data-stu-id="255d2-353">What's new</span></span>

- <span data-ttu-id="255d2-354">MpCmdRun-Ablaufverfolgungsebene wurde behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="255d2-355">WDFilter-Versionsinformationen wurden behoben</span><span class="sxs-lookup"><span data-stu-id="255d2-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="255d2-356">Verbessern von Benachrichtigungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="255d2-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="255d2-357">Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien</span><span class="sxs-lookup"><span data-stu-id="255d2-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="255d2-358">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="255d2-358">Known Issues</span></span>
<span data-ttu-id="255d2-359">Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.</span><span class="sxs-lookup"><span data-stu-id="255d2-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="255d2-360">Microsoft Defender Antivirus Plattformunterstützung</span><span class="sxs-lookup"><span data-stu-id="255d2-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="255d2-361">Plattform- und Modulupdates werden monatlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="255d2-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="255d2-362">Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="255d2-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="255d2-363">Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="255d2-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="255d2-364">**Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="255d2-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="255d2-365">Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert.</span><span class="sxs-lookup"><span data-stu-id="255d2-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="255d2-366">Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="255d2-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="255d2-367">\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion, die in Windows 10-Versionen enthalten ist)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="255d2-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="255d2-368">Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die verwalteten Supportangebote von Microsoft (z. B. Premier Support) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="255d2-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="255d2-369">Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (\*) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="255d2-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="255d2-370">In Windows 10-Versionen enthaltene Plattformversion</span><span class="sxs-lookup"><span data-stu-id="255d2-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="255d2-371">Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10 Versionen ausgeliefert werden:</span><span class="sxs-lookup"><span data-stu-id="255d2-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="255d2-372">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="255d2-372">Windows 10 release</span></span>  |<span data-ttu-id="255d2-373">Plattformversion</span><span class="sxs-lookup"><span data-stu-id="255d2-373">Platform version</span></span>  |<span data-ttu-id="255d2-374">Modulversion</span><span class="sxs-lookup"><span data-stu-id="255d2-374">Engine version</span></span> |<span data-ttu-id="255d2-375">Supportphase</span><span class="sxs-lookup"><span data-stu-id="255d2-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="255d2-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="255d2-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="255d2-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="255d2-377">4.18.1909.6</span></span> |<span data-ttu-id="255d2-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="255d2-378">1.1.17000.2</span></span> | <span data-ttu-id="255d2-379">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="255d2-380">1909  (19H2)</span></span> |<span data-ttu-id="255d2-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="255d2-381">4.18.1902.5</span></span> |<span data-ttu-id="255d2-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="255d2-382">1.1.16700.3</span></span> | <span data-ttu-id="255d2-383">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="255d2-384">1903  (19H1)</span></span> |<span data-ttu-id="255d2-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="255d2-385">4.18.1902.5</span></span> |<span data-ttu-id="255d2-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="255d2-386">1.1.15600.4</span></span> | <span data-ttu-id="255d2-387">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="255d2-388">1809  (RS5)</span></span> |<span data-ttu-id="255d2-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="255d2-389">4.18.1807.18075</span></span> |<span data-ttu-id="255d2-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="255d2-390">1.1.15000.2</span></span> | <span data-ttu-id="255d2-391">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="255d2-392">1803  (RS4)</span></span> |<span data-ttu-id="255d2-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="255d2-393">4.13.17134.1</span></span> |<span data-ttu-id="255d2-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="255d2-394">1.1.14600.4</span></span> | <span data-ttu-id="255d2-395">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="255d2-396">1709  (RS3)</span></span> |<span data-ttu-id="255d2-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="255d2-397">4.12.16299.15</span></span> |<span data-ttu-id="255d2-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="255d2-398">1.1.14104.0</span></span> | <span data-ttu-id="255d2-399">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="255d2-400">1703  (RS2)</span></span> |<span data-ttu-id="255d2-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="255d2-401">4.11.15603.2</span></span> |<span data-ttu-id="255d2-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="255d2-402">1.1.13504.0</span></span> | <span data-ttu-id="255d2-403">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="255d2-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="255d2-404">1607 (RS1)</span></span> |<span data-ttu-id="255d2-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="255d2-405">4.10.14393.3683</span></span> |<span data-ttu-id="255d2-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="255d2-406">1.1.12805.0</span></span> | <span data-ttu-id="255d2-407">Support für technische Upgrades (nur)</span><span class="sxs-lookup"><span data-stu-id="255d2-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="255d2-408">Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="255d2-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="255d2-409">Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)</span><span class="sxs-lookup"><span data-stu-id="255d2-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="255d2-410">Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antiviren- und Antischadsoftwareupdates zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="255d2-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="255d2-411">Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz.</span><span class="sxs-lookup"><span data-stu-id="255d2-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="255d2-412">Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Installationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="255d2-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="255d2-413">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="255d2-413">1.1.2106.01</span></span></summary>

<span data-ttu-id="255d2-414">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-414">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="255d2-415">&ensp;Plattformversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="255d2-415">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="255d2-416">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="255d2-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="255d2-417">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-417">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-418">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-418">Fixes</span></span>
- <span data-ttu-id="255d2-419">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-420">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-420">Additional information</span></span>
- <span data-ttu-id="255d2-421">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-422">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="255d2-422">1.1.2105.01</span></span></summary>

<span data-ttu-id="255d2-423">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-423">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="255d2-424">&ensp;Plattformversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="255d2-424">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="255d2-425">&ensp;Modulversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="255d2-425">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="255d2-426">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-426">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-427">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-427">Fixes</span></span>
- <span data-ttu-id="255d2-428">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-429">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-429">Additional information</span></span>
- <span data-ttu-id="255d2-430">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-431">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="255d2-431">1.1.2104.01</span></span></summary>

<span data-ttu-id="255d2-432">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-432">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="255d2-433">&ensp;Plattformversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="255d2-433">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="255d2-434">&ensp;Modulversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-434">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="255d2-435">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-435">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-436">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-436">Fixes</span></span>
- <span data-ttu-id="255d2-437">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-438">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-438">Additional information</span></span>
- <span data-ttu-id="255d2-439">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-440">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="255d2-440">1.1.2103.01</span></span></summary>

<span data-ttu-id="255d2-441">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-441">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="255d2-442">&ensp;Plattformversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="255d2-442">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="255d2-443">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="255d2-444">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-444">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-445">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-445">Fixes</span></span>
- <span data-ttu-id="255d2-446">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-447">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-447">Additional information</span></span>
- <span data-ttu-id="255d2-448">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-449">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="255d2-449">1.1.2102.03</span></span></summary>

<span data-ttu-id="255d2-450">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="255d2-450">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="255d2-451">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="255d2-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="255d2-452">&ensp;Modulversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-452">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="255d2-453">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-453">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-454">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-454">Fixes</span></span>
- <span data-ttu-id="255d2-455">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-456">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-456">Additional information</span></span>
- <span data-ttu-id="255d2-457">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-458">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="255d2-458">1.1.2101.02</span></span></summary>

<span data-ttu-id="255d2-459">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="255d2-459">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="255d2-460">&ensp;Plattformversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="255d2-460">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="255d2-461">&ensp;Modulversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="255d2-461">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="255d2-462">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-462">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-463">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-463">Fixes</span></span>
- <span data-ttu-id="255d2-464">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-465">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-465">Additional information</span></span>
- <span data-ttu-id="255d2-466">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-467">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="255d2-467">1.1.2012.01</span></span></summary>

<span data-ttu-id="255d2-468">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-468">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="255d2-469">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="255d2-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="255d2-470">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="255d2-471">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-471">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-472">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-472">Fixes</span></span>
- <span data-ttu-id="255d2-473">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-474">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-474">Additional information</span></span>
- <span data-ttu-id="255d2-475">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-476">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="255d2-476">1.1.2011.02</span></span></summary>

<span data-ttu-id="255d2-477">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="255d2-477">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="255d2-478">&ensp;Plattformversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="255d2-478">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="255d2-479">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="255d2-480">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-480">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-481">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-481">Fixes</span></span>
- <span data-ttu-id="255d2-482">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-483">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-483">Additional information</span></span>
- <span data-ttu-id="255d2-484">Aktualisierte Microsoft Defender Antivirus Signaturen</span><span class="sxs-lookup"><span data-stu-id="255d2-484">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-485">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="255d2-485">1.1.2011.01</span></span></summary>

<span data-ttu-id="255d2-486">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="255d2-487">&ensp;Plattformversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="255d2-487">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="255d2-488">&ensp;Modulversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-488">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="255d2-489">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-489">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-490">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-490">Fixes</span></span>
- <span data-ttu-id="255d2-491">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-492">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-492">Additional information</span></span>
- <span data-ttu-id="255d2-493">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-493">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="255d2-494">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="255d2-494">1.1.2009.10</span></span></summary>

<span data-ttu-id="255d2-495">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="255d2-495">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="255d2-496">&ensp;Plattformversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="255d2-496">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="255d2-497">&ensp;Modulversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="255d2-497">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="255d2-498">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="255d2-498">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="255d2-499">Behebungen</span><span class="sxs-lookup"><span data-stu-id="255d2-499">Fixes</span></span>
- <span data-ttu-id="255d2-500">Keine</span><span class="sxs-lookup"><span data-stu-id="255d2-500">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="255d2-501">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="255d2-501">Additional information</span></span>
- <span data-ttu-id="255d2-502">Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="255d2-502">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="255d2-503">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="255d2-503">Additional resources</span></span>

| <span data-ttu-id="255d2-504">Artikel</span><span class="sxs-lookup"><span data-stu-id="255d2-504">Article</span></span> | <span data-ttu-id="255d2-505">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="255d2-505">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="255d2-506">Microsoft Defender-Update für Windows Betriebssysteminstallationsimages</span><span class="sxs-lookup"><span data-stu-id="255d2-506">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="255d2-507">Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien).</span><span class="sxs-lookup"><span data-stu-id="255d2-507">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="255d2-508">Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.</span><span class="sxs-lookup"><span data-stu-id="255d2-508">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="255d2-509">Verwalten, wie Schutzupdates heruntergeladen und angewendet werden</span><span class="sxs-lookup"><span data-stu-id="255d2-509">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="255d2-510">Schutzupdates können über viele Quellen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="255d2-510">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="255d2-511">Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="255d2-511">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="255d2-512">Sie können planen, wann Schutzupdates heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="255d2-512">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="255d2-513">Verwalten von Updates für veraltete Endpunkte</span><span class="sxs-lookup"><span data-stu-id="255d2-513">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="255d2-514">Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="255d2-514">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="255d2-515">Verwalten von ereignisbasierten erzwungenen Updates</span><span class="sxs-lookup"><span data-stu-id="255d2-515">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="255d2-516">Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="255d2-516">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="255d2-517">Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)</span><span class="sxs-lookup"><span data-stu-id="255d2-517">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="255d2-518">Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="255d2-518">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
