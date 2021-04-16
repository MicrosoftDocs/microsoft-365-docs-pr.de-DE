---
title: Onboarding von Geräten in den Microsoft Defender for Endpoint-Dienst
description: Onboarding von Windows 10-Geräten, -Servern, Nicht-Windows-Geräten und Erfahren Sie, wie Sie einen Erkennungstest ausführen.
keywords: onboarding, microsoft defender for endpoint onboarding, windows atp onboarding, sccm, group policy, mdm, local script, detection test
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4aa3e30f34e7d9dc362cc0bbb277aaee5834b4fe
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861375"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="5c9b1-104">Onboarding von Geräten in den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="5c9b1-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c9b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c9b1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5c9b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c9b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c9b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="5c9b1-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5c9b1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c9b1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="5c9b1-110">Sie müssen den Abschnitt Onboarding des Defender for Endpoint-Portals verwenden, um alle unterstützten Geräte zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="5c9b1-111">Je nach Gerät werden Sie mit den entsprechenden Schritten geführt und die für das Gerät geeigneten Verwaltungs- und Bereitstellungstooloptionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="5c9b1-112">Im Allgemeinen, um Geräte in den Dienst zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="5c9b1-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="5c9b1-113">Überprüfen, ob das Gerät die [Mindestanforderungen erfüllt](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5c9b1-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="5c9b1-114">Führen Sie je nach Gerät die Konfigurationsschritte aus, die im Abschnitt onboarding des Defender for Endpoint-Portals bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="5c9b1-115">Verwenden des geeigneten Verwaltungstools und der bereitstellungsmethode für Ihre Geräte</span><span class="sxs-lookup"><span data-stu-id="5c9b1-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="5c9b1-116">Führen Sie einen Erkennungstest aus, um zu überprüfen, ob die Geräte ordnungsgemäß onboardiert sind, und melden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="5c9b1-117">Onboardingtooloptionen</span><span class="sxs-lookup"><span data-stu-id="5c9b1-117">Onboarding tool options</span></span>
<span data-ttu-id="5c9b1-118">In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="5c9b1-119">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5c9b1-119">Endpoint</span></span>     | <span data-ttu-id="5c9b1-120">Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="5c9b1-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="5c9b1-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-121">**Windows**</span></span>  |  [<span data-ttu-id="5c9b1-122">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="5c9b1-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="5c9b1-123">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="5c9b1-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="5c9b1-124">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="5c9b1-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="5c9b1-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5c9b1-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="5c9b1-126">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="5c9b1-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="5c9b1-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-127">**macOS**</span></span>    | [<span data-ttu-id="5c9b1-128">Lokale Skripts</span><span class="sxs-lookup"><span data-stu-id="5c9b1-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="5c9b1-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5c9b1-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="5c9b1-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="5c9b1-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="5c9b1-131">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="5c9b1-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="5c9b1-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-132">**Linux Server**</span></span> | [<span data-ttu-id="5c9b1-133">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="5c9b1-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="5c9b1-134">100</span><span class="sxs-lookup"><span data-stu-id="5c9b1-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="5c9b1-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="5c9b1-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="5c9b1-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-136">**iOS**</span></span>      | [<span data-ttu-id="5c9b1-137">App-basiert</span><span class="sxs-lookup"><span data-stu-id="5c9b1-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="5c9b1-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="5c9b1-138">**Android**</span></span>  | [<span data-ttu-id="5c9b1-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5c9b1-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="5c9b1-140">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="5c9b1-140">In this section</span></span>
<span data-ttu-id="5c9b1-141">Thema</span><span class="sxs-lookup"><span data-stu-id="5c9b1-141">Topic</span></span> | <span data-ttu-id="5c9b1-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c9b1-142">Description</span></span>
:---|:---
[<span data-ttu-id="5c9b1-143">Onboarding von früheren Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="5c9b1-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="5c9b1-144">Onboarding von Windows 7- und Windows 8.1-Geräten zu Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="5c9b1-145">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="5c9b1-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="5c9b1-146">Sie müssen Geräte integrieren, damit sie dem Defender for Endpoint-Dienst melden können.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="5c9b1-147">Erfahren Sie mehr über die Tools und Methoden, die Sie zum Konfigurieren von Geräten in Ihrem Unternehmen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="5c9b1-148">Onboarding von Servern</span><span class="sxs-lookup"><span data-stu-id="5c9b1-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="5c9b1-149">Onboarding Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) Version 1803 und höher, Windows Server 2019 und höher und Windows Server 2019 Core Edition zu Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="5c9b1-150">Onboarding von Nicht-Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="5c9b1-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="5c9b1-151">Defender for Endpoint bietet eine zentrale Sicherheitsbetriebserfahrung für Windows- und Nicht-Windows-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="5c9b1-152">Sie können Warnungen von verschiedenen unterstützten Betriebssystemen im Microsoft Defender Security Center anzeigen und das Netzwerk Ihrer Organisation besser schützen.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="5c9b1-153">Diese Erfahrung nutzt sensorische Daten eines Drittanbieters für Sicherheitsprodukte.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="5c9b1-154">Ausführen eines Erkennungstests auf einem neu integrierten Gerät</span><span class="sxs-lookup"><span data-stu-id="5c9b1-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="5c9b1-155">Führen Sie ein Skript auf einem neu integrierten Gerät aus, um sicherzustellen, dass es ordnungsgemäß an den Defender for Endpoint-Dienst berichtet.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="5c9b1-156">Konfigurieren von Proxy- und Interneteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c9b1-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="5c9b1-157">Aktivieren Sie die Kommunikation mit dem Defender for Endpoint-Clouddienst, indem Sie die Proxy- und Internetverbindungseinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="5c9b1-158">Behandeln von Onboarding-Problemen</span><span class="sxs-lookup"><span data-stu-id="5c9b1-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="5c9b1-159">Erfahren Sie mehr über das Beheben von Problemen, die beim Onboarding auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="5c9b1-160">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5c9b1-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c9b1-161">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5c9b1-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
