---
title: Erhöhen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie
description: Die Microsoft Defender for Endpoint-Sicherheitsgrundlinie legt Sicherheitssteuerelemente fest, um optimalen Schutz zu bieten.
keywords: Intune-Verwaltung, Microsoft Defender for Endpoint, Microsoft Defender, Microsoft Defender for Endpoint ASR, Sicherheitsgrundlinie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933601"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="1a3c5-104">Erhöhen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie</span><span class="sxs-lookup"><span data-stu-id="1a3c5-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a3c5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1a3c5-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a3c5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1a3c5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a3c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a3c5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1a3c5-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1a3c5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a3c5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="1a3c5-110">Sicherheitsgrundwerte stellen sicher, dass Sicherheitsfeatures gemäß den Anweisungen von Sicherheitsexperten und erfahrenen Windows-Systemadministratoren konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="1a3c5-111">Bei der Bereitstellung legt die Sicherheitsgrundlinie von Defender for Endpoint die Sicherheitssteuerelemente für Defender for Endpoint so fest, dass ein optimaler Schutz bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="1a3c5-112">Informationen zu Sicherheitsgrundwerten und deren Zugewiesenung in Intune mithilfe von Konfigurationsprofilen finden Sie [in diesen Häufig gestellten Fragen](https://docs.microsoft.com/intune/security-baselines#q--a).</span><span class="sxs-lookup"><span data-stu-id="1a3c5-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="1a3c5-113">Bevor Sie die Einhaltung von Sicherheitsgrundwerten bereitstellen und nachverfolgen können:</span><span class="sxs-lookup"><span data-stu-id="1a3c5-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="1a3c5-114">Registrieren Ihrer Geräte bei der Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="1a3c5-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="1a3c5-115">Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="1a3c5-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="1a3c5-116">Vergleichen der Microsoft Defender for Endpoint- und Windows Intune-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="1a3c5-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="1a3c5-117">Die Windows Intune-Sicherheitsgrundlinie enthält eine umfassende Reihe empfohlener Einstellungen, die zum sicheren Konfigurieren von Geräten unter Windows erforderlich sind, einschließlich Browsereinstellungen, PowerShell-Einstellungen sowie Einstellungen für einige Sicherheitsfeatures wie Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1a3c5-118">Im Gegensatz dazu enthält die Defender for Endpoint-Baseline Einstellungen, mit denen alle Sicherheitssteuerelemente im Defender for Endpoint-Stapel optimiert werden, einschließlich Einstellungen für endpunkterkennung und -reaktion (Endpoint Detection and Response, EDR) sowie Einstellungen, die auch in der Windows Intune-Sicherheitsgrundlinie zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="1a3c5-119">Weitere Informationen zu den einzelnen Baselines finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="1a3c5-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="1a3c5-120">Windows-Sicherheitsgrundeinstellungen für Intune</span><span class="sxs-lookup"><span data-stu-id="1a3c5-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="1a3c5-121">Basiseinstellungen für Microsoft Defender for Endpoint für Intune</span><span class="sxs-lookup"><span data-stu-id="1a3c5-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="1a3c5-122">Im Idealfall werden die in Defender for Endpoint integrierten Geräte beide Basiswerte bereitgestellt: die Windows Intune-Sicherheitsgrundlinie zum anfänglichen Sichern von Windows und anschließend die Defender for Endpoint-Sicherheitsgrundlinie, die sich auf einer Schicht befindet, um die Defender for Endpoint-Sicherheitssteuerelemente optimal zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="1a3c5-123">Um von den neuesten Daten zu Risiken und Bedrohungen zu profitieren und Konflikte bei der Entwicklung der Basiswerte zu minimieren, wenden Sie immer die neuesten Versionen der Basiswerte für alle Produkte an, sobald sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="1a3c5-124">Die Sicherheitsgrundlinie von Defender for Endpoint wurde für physische Geräte optimiert und wird derzeit nicht für die Verwendung auf virtuellen Computern (VMs) oder VDI-Endpunkten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="1a3c5-125">Bestimmte Basiseinstellungen können sich auf interaktive Remotesitzungen in virtualisierten Umgebungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="1a3c5-126">Überwachen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a3c5-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="1a3c5-127">Die **Sicherheitsgrundkarte** für die [Gerätekonfigurationsverwaltung](configure-machines.md) bietet eine Übersicht über die Kompatibilität auf Windows 10-Geräten, denen die Sicherheitsbasislinie Defender for Endpoint zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="1a3c5-128">![Sicherheitsgrundkarte](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="1a3c5-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="1a3c5-129">*Karte, auf der die Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint angezeigt wird*</span><span class="sxs-lookup"><span data-stu-id="1a3c5-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="1a3c5-130">Jedem Gerät wird einer der folgenden Statustypen gegeben:</span><span class="sxs-lookup"><span data-stu-id="1a3c5-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="1a3c5-131">**Entspricht dem Basisplan**– Geräteeinstellungen entsprechen allen Einstellungen in der Basislinie</span><span class="sxs-lookup"><span data-stu-id="1a3c5-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="1a3c5-132">**Nicht mit dem Basisplan** übereinstimmen – mindestens eine Geräteeinstellung ist nicht mit der Basislinie übereinstimmend</span><span class="sxs-lookup"><span data-stu-id="1a3c5-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="1a3c5-133">**Falsch konfiguriert –** Mindestens eine Basiseinstellung ist auf dem Gerät nicht ordnungsgemäß konfiguriert und befindet sich in einem Konflikt-, Fehler- oder Ausstehendzustand.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="1a3c5-134">**Nicht zutreffend**– Mindestens eine Basiseinstellung gilt nicht auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="1a3c5-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="1a3c5-135">Wählen Sie Zum Überprüfen bestimmter Geräte **die Option Sicherheitsbasisplan auf** der Karte konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="1a3c5-136">Dies führt Sie zur Intune-Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-136">This takes you to Intune device management.</span></span> <span data-ttu-id="1a3c5-137">Wählen Sie dort **Gerätestatus** für die Namen und Status der Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="1a3c5-138">Möglicherweise gibt es Abweichungen in aggregierten Daten, die auf der Seite für die Gerätekonfigurationsverwaltung angezeigt werden, und in den auf Übersichtsbildschirmen in Intune angezeigten Daten.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="1a3c5-139">Überprüfen und Zuweisen der Microsoft Defender for Endpoint-Sicherheitsgrundlinie</span><span class="sxs-lookup"><span data-stu-id="1a3c5-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="1a3c5-140">Die Gerätekonfigurationsverwaltung überwacht die Grundlegende Kompatibilität nur von Windows 10-Geräten, denen speziell die Microsoft Defender for Endpoint-Sicherheitsbasis zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="1a3c5-141">Sie können die Basislinie bequem überprüfen und sie Geräten in der Intune-Geräteverwaltung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="1a3c5-142">Wählen **Sie Sicherheitsbasisplan konfigurieren** auf der **Basiskarte Sicherheit** aus, um zu Intune-Geräteverwaltung zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="1a3c5-143">Eine ähnliche Übersicht über die Basiskonformität wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="1a3c5-144">Alternativ können Sie im Microsoft Azure-Portal von Allen Diensten > Intune > Gerätesicherheit > Sicherheitsgrundlinien > Microsoft Defender ATP-Basislinie zur Sicherheitsbasislinie von Defender for Endpoint **navigieren.**</span><span class="sxs-lookup"><span data-stu-id="1a3c5-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="1a3c5-145">Erstellen Sie ein neues Profil.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-145">Create a new profile.</span></span>

   <span data-ttu-id="1a3c5-146">![Übersicht über die Sicherheitsgrundlinie von Microsoft Defender for Endpoint in Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="1a3c5-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="1a3c5-147">*Übersicht über die Sicherheitsgrundlinie von Microsoft Defender for Endpoint in Intune*</span><span class="sxs-lookup"><span data-stu-id="1a3c5-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="1a3c5-148">Während der Profilerstellung können Sie bestimmte Einstellungen für den Basisplan überprüfen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="1a3c5-149">![Sicherheitsgrundlinienoptionen während der Profilerstellung in Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="1a3c5-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="1a3c5-150">*Sicherheitsgrundlinienoptionen während der Profilerstellung in Intune*</span><span class="sxs-lookup"><span data-stu-id="1a3c5-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="1a3c5-151">Weisen Sie das Profil der entsprechenden Gerätegruppe zu.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="1a3c5-152">![Sicherheitsgrundlinienprofile in Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="1a3c5-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="1a3c5-153">*Zuweisen des Sicherheitsgrundlinienprofils in Intune*</span><span class="sxs-lookup"><span data-stu-id="1a3c5-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="1a3c5-154">Erstellen Sie das Profil, um es zu speichern und in der zugewiesenen Gerätegruppe zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="1a3c5-155">![Zuweisen der Sicherheitsgrundlinie in Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="1a3c5-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="1a3c5-156">*Erstellen des Sicherheitsgrundprofils in Intune*</span><span class="sxs-lookup"><span data-stu-id="1a3c5-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="1a3c5-157">Sicherheitsgrundwerte in Intune bieten eine bequeme Möglichkeit, Ihre Geräte umfassend zu sichern und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="1a3c5-158">[Erfahren Sie mehr über Sicherheitsgrundwerte in Intune](https://docs.microsoft.com/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="1a3c5-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="1a3c5-159">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1a3c5-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1a3c5-160">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1a3c5-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="1a3c5-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1a3c5-161">Related topics</span></span>
- [<span data-ttu-id="1a3c5-162">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="1a3c5-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="1a3c5-163">Get devices onboarded to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a3c5-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="1a3c5-164">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="1a3c5-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
