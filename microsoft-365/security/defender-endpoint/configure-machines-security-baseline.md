---
title: Erhöhen der Compliance für die Microsoft Defender für Endpunkt-Sicherheitsgrundwerte
description: Die Sicherheitsgrundwerte von Microsoft Defender für Endpunkt legen Sicherheitskontrollen fest, um optimalen Schutz zu bieten.
keywords: Intune-Verwaltung, Microsoft Defender für Endpunkt, Microsoft Defender, Microsoft Defender für Endpunkt ASR, Sicherheitsgrundwerte
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
ms.openlocfilehash: a5f3d2de452a8a1ab201f558b93d45dfa6ded3e6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841546"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cc7b0-104">Erhöhen der Compliance für die Microsoft Defender für Endpunkt-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="cc7b0-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc7b0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc7b0-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc7b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc7b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc7b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cc7b0-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cc7b0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc7b0-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="cc7b0-110">Sicherheitsgrundwerte stellen sicher, dass Sicherheitsfeatures gemäß den Anweisungen von Sicherheitsexperten und Experten Windows Systemadministratoren konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="cc7b0-111">Bei der Bereitstellung legt die Defender für Endpunkt-Sicherheitsgrundwerte Defender für Endpunkt-Sicherheitskontrollen fest, um optimalen Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="cc7b0-112">Lesen Sie [diese häufig gestellten Fragen,](/intune/security-baselines#q--a)um die Sicherheitsgrundwerte zu verstehen und zu verstehen, wie sie in Intune mithilfe von Konfigurationsprofilen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="cc7b0-113">Bevor Sie die Compliance in Sicherheitsgrundwerten bereitstellen und nachverfolgen können:</span><span class="sxs-lookup"><span data-stu-id="cc7b0-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="cc7b0-114">Registrieren Ihrer Geräte bei der Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="cc7b0-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="cc7b0-115">Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="cc7b0-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="cc7b0-116">Vergleichen der Sicherheitsgrundwerte von Microsoft Defender für Endpunkt und Windows Intune</span><span class="sxs-lookup"><span data-stu-id="cc7b0-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="cc7b0-117">Die Windows Intune-Sicherheitsgrundwerte bieten einen umfassenden Satz empfohlener Einstellungen, die zum sicheren Konfigurieren Windows ausgeführter Geräte erforderlich sind, einschließlich Browsereinstellungen, PowerShell-Einstellungen sowie Einstellungen für einige Sicherheitsfeatures wie Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="cc7b0-118">Im Gegensatz dazu bietet die Defender für Endpunkt-Baseline Einstellungen, die alle Sicherheitssteuerelemente im Defender für Endpunkt-Stapel optimieren, einschließlich Einstellungen für EDR (EDR) sowie Einstellungen, die auch in der Windows Intune-Sicherheitsbaseline zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="cc7b0-119">Weitere Informationen zu den einzelnen Baselines finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cc7b0-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="cc7b0-120">einstellungen für Windows Sicherheitsgrundwerte für Intune</span><span class="sxs-lookup"><span data-stu-id="cc7b0-120">Windows security baseline settings for Intune</span></span>](/intune/security-baseline-settings-windows)
- [<span data-ttu-id="cc7b0-121">Microsoft Defender für Endpunkt-Basisplaneinstellungen für Intune</span><span class="sxs-lookup"><span data-stu-id="cc7b0-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="cc7b0-122">Im Idealfall werden geräte, die in Defender für Endpunkt integriert sind, beide Baselines bereitgestellt: die Windows Intune-Sicherheitsgrundwerte, um zunächst Windows zu sichern, und dann die Defender für Endpunkt-Sicherheitsgrundwerte, die übereinander liegen, um die Sicherheitskontrollen von Defender für Endpunkt optimal zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="cc7b0-123">Um von den neuesten Daten zu Risiken und Bedrohungen zu profitieren und Konflikte bei der Weiterentwicklung der Basispläne zu minimieren, wenden Sie immer die neuesten Versionen der Baselines auf alle Produkte an, sobald sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="cc7b0-124">Die Defender für Endpunkt-Sicherheitsbaseline wurde für physische Geräte optimiert und wird derzeit nicht für die Verwendung auf virtuellen Computern (VMs) oder VDI-Endpunkten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="cc7b0-125">Bestimmte Basiseinstellungen können sich auf interaktive Remotesitzungen in virtualisierten Umgebungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cc7b0-126">Überwachen der Einhaltung der Sicherheitsgrundwerte für Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc7b0-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="cc7b0-127">Die Karte mit den **Sicherheitsgrundwerten** für [die Gerätekonfigurationsverwaltung](configure-machines.md) bietet eine Übersicht über die Compliance auf Windows 10 Geräten, denen die Defender für Endpunkt-Sicherheitsgrundlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="cc7b0-128">![Karte der Sicherheitsgrundwerte](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="cc7b0-129">*Karte mit Compliance für die Defender für Endpunkt-Sicherheitsgrundwerte*</span><span class="sxs-lookup"><span data-stu-id="cc7b0-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="cc7b0-130">Jedem Gerät wird einer der folgenden Statustypen zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="cc7b0-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="cc7b0-131">**Entspricht dem Basisplan**– Geräteeinstellungen stimmen mit allen Einstellungen in der Baseline überein</span><span class="sxs-lookup"><span data-stu-id="cc7b0-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="cc7b0-132">**Entspricht nicht dem Basisplan**– mindestens eine Geräteeinstellung stimmt nicht mit der Grundlinie überein.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="cc7b0-133">**Falsch konfiguriert**– mindestens eine Basisplaneinstellung ist auf dem Gerät nicht ordnungsgemäß konfiguriert und befindet sich in einem Konflikt-, Fehler- oder ausstehenden Zustand.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="cc7b0-134">**Nicht zutreffend**– Mindestens eine Baseline-Einstellung ist auf dem Gerät nicht anwendbar.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="cc7b0-135">Um bestimmte Geräte zu überprüfen, wählen Sie **Sicherheitsgrundwerte** auf der Karte konfigurieren aus.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="cc7b0-136">Dadurch gelangen Sie zur Intune-Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-136">This takes you to Intune device management.</span></span> <span data-ttu-id="cc7b0-137">Wählen Sie dort den **Gerätestatus** für die Namen und Status der Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="cc7b0-138">Möglicherweise treten Abweichungen in aggregierten Daten auf der Seite für die Gerätekonfigurationsverwaltung und auf Übersichtsbildschirmen in Intune auf.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="cc7b0-139">Überprüfen und Zuweisen der Microsoft Defender für Endpunkt-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="cc7b0-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="cc7b0-140">Die Gerätekonfigurationsverwaltung überwacht die Baseline-Compliance nur für Windows 10 Geräte, denen speziell die Sicherheitsgrundwerte von Microsoft Defender für Endpunkt zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="cc7b0-141">Sie können den Basisplan bequem überprüfen und den Geräten in der Intune-Geräteverwaltung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="cc7b0-142">Wählen Sie **"Sicherheitsbasisplan** konfigurieren" auf der Karte **"Sicherheitsgrundwerte"** aus, um zur Intune-Geräteverwaltung zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="cc7b0-143">Eine ähnliche Übersicht über die Baseline-Compliance wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="cc7b0-144">Alternativ können Sie im Microsoft Azure-Portal von **allen Diensten > Intune > Gerätesicherheits->-Sicherheitsgrundwerte > Microsoft Defender ATP Baseline** zur Defender für Endpunkt-Sicherheitsbaseline navigieren.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="cc7b0-145">Erstellen Sie ein neues Profil.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-145">Create a new profile.</span></span>

   <span data-ttu-id="cc7b0-146">![Übersicht über die Microsoft Defender für Endpunkt-Sicherheitsgrundwerte in Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="cc7b0-147">*Übersicht über die Microsoft Defender für Endpunkt-Sicherheitsgrundwerte in Intune*</span><span class="sxs-lookup"><span data-stu-id="cc7b0-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="cc7b0-148">Während der Profilerstellung können Sie bestimmte Einstellungen auf der Basislinie überprüfen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="cc7b0-149">![Optionen für Sicherheitsgrundwerte während der Profilerstellung in Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="cc7b0-150">*Optionen für Sicherheitsgrundwerte während der Profilerstellung in Intune*</span><span class="sxs-lookup"><span data-stu-id="cc7b0-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="cc7b0-151">Weisen Sie das Profil der entsprechenden Gerätegruppe zu.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="cc7b0-152">![Sicherheitsgrundwerteprofile in Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="cc7b0-153">*Zuweisen des Sicherheitsbasisplanprofils in Intune*</span><span class="sxs-lookup"><span data-stu-id="cc7b0-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="cc7b0-154">Erstellen Sie das Profil, um es zu speichern und in der zugewiesenen Gerätegruppe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="cc7b0-155">![Zuweisen der Sicherheitsgrundwerte in Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="cc7b0-156">*Erstellen des Sicherheitsbasisplanprofils in Intune*</span><span class="sxs-lookup"><span data-stu-id="cc7b0-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="cc7b0-157">Sicherheitsgrundwerte in Intune bieten eine bequeme Möglichkeit, Ihre Geräte umfassend zu sichern und zu schützen.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="cc7b0-158">[Erfahren Sie mehr über Sicherheitsgrundwerte in Intune.](/intune/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-158">[Learn more about security baselines on Intune](/intune/security-baselines).</span></span>

><span data-ttu-id="cc7b0-159">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cc7b0-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc7b0-160">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="cc7b0-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cc7b0-161">Related topics</span></span>
- [<span data-ttu-id="cc7b0-162">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="cc7b0-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="cc7b0-163">Geräte in Microsoft Defender für Endpunkt integrieren</span><span class="sxs-lookup"><span data-stu-id="cc7b0-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="cc7b0-164">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="cc7b0-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
