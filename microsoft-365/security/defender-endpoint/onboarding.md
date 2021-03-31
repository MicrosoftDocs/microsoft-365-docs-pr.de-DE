---
title: Onboarding in den Microsoft Defender ATP-Dienst
description: Informationen zum Onboarding von Endpunkten in den Microsoft Defender ATP-Dienst
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56a62ca4ebbd140f507d1735c663924014ca4771
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445732"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4c4e2-103">Onboarding für den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="4c4e2-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4c4e2-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-104">**Applies to:**</span></span>
- [<span data-ttu-id="4c4e2-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4c4e2-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4c4e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c4e2-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4c4e2-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4c4e2-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4c4e2-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4c4e2-109">Erfahren Sie mehr über die verschiedenen Phasen der Bereitstellung von Microsoft Defender for Endpoint und über die Konfiguration der Funktionen innerhalb der Lösung.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="4c4e2-110">Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:</span><span class="sxs-lookup"><span data-stu-id="4c4e2-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="4c4e2-111">[![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4c4e2-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="4c4e2-112">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="4c4e2-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="4c4e2-113">[![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4c4e2-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="4c4e2-114">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="4c4e2-114">Phase 2: Setup</span></span>](production-deployment.md) | ![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="4c4e2-116">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="4c4e2-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="4c4e2-117">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="4c4e2-117">*You are here!*</span></span>|

<span data-ttu-id="4c4e2-118">Sie befinden sich derzeit in der Onboardingphase.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="4c4e2-119">Dies sind die Schritte, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="4c4e2-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="4c4e2-120">Schritt 1: Onboarding von Endpunkten für den Dienst</span><span class="sxs-lookup"><span data-stu-id="4c4e2-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="4c4e2-121">Schritt 2: Konfigurieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="4c4e2-122">Schritt 1: Onboarding von Endpunkten mithilfe eines der unterstützten Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="4c4e2-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="4c4e2-123">Im [Thema Bereitstellung planen](deployment-strategy.md) werden die allgemeinen Schritte beschrieben, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="4c4e2-124">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten, und erfahren Sie mehr über die verfügbaren Tools und Methoden.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="4c4e2-125">Nachdem Sie Ihre Architektur identifiziert haben, müssen Sie entscheiden, welche Bereitstellungsmethode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="4c4e2-126">Das von Ihnen auswählende Bereitstellungstool beeinflusst, wie Sie Endpunkte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="4c4e2-127">Onboardingtooloptionen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-127">Onboarding tool options</span></span>

<span data-ttu-id="4c4e2-128">In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="4c4e2-129">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4c4e2-129">Endpoint</span></span>     | <span data-ttu-id="4c4e2-130">Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="4c4e2-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-131">**Windows**</span></span>  |  [<span data-ttu-id="4c4e2-132">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="4c4e2-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="4c4e2-133">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4c4e2-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="4c4e2-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="4c4e2-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="4c4e2-136">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="4c4e2-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="4c4e2-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-137">**macOS**</span></span>    | [<span data-ttu-id="4c4e2-138">Lokale Skripts</span><span class="sxs-lookup"><span data-stu-id="4c4e2-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="4c4e2-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="4c4e2-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="4c4e2-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="4c4e2-141">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="4c4e2-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="4c4e2-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-142">**Linux Server**</span></span> | [<span data-ttu-id="4c4e2-143">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="4c4e2-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="4c4e2-144">100</span><span class="sxs-lookup"><span data-stu-id="4c4e2-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="4c4e2-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="4c4e2-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="4c4e2-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-146">**iOS**</span></span>      | [<span data-ttu-id="4c4e2-147">App-basiert</span><span class="sxs-lookup"><span data-stu-id="4c4e2-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="4c4e2-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="4c4e2-148">**Android**</span></span>  | [<span data-ttu-id="4c4e2-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="4c4e2-150">Schritt 2: Konfigurieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="4c4e2-151">Nach dem Onboarding der Endpunkte konfigurieren Sie die verschiedenen Funktionen, z. B. Endpunkterkennung und -reaktion, Schutz der nächsten Generation und Reduzierung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="4c4e2-152">Beispielbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-152">Example deployments</span></span>
<span data-ttu-id="4c4e2-153">In diesem Bereitstellungshandbuch führen wir Sie durch die Verwendung von zwei Bereitstellungstools zum Onboarding von Endpunkten und zum Konfigurieren von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4c4e2-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="4c4e2-154">Die Tools in den Beispielbereitstellungen sind:</span><span class="sxs-lookup"><span data-stu-id="4c4e2-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="4c4e2-155">Onboarding mithilfe des Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4c4e2-156">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="4c4e2-157">Mithilfe der oben genannten Bereitstellungstools werden Sie dann bei der Konfiguration der folgenden Defender for Endpoint-Funktionen geführt:</span><span class="sxs-lookup"><span data-stu-id="4c4e2-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="4c4e2-158">Endpunkterkennung und Reaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="4c4e2-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="4c4e2-159">Schutzkonfiguration der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="4c4e2-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="4c4e2-160">Konfiguration der Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="4c4e2-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c4e2-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4c4e2-161">Related topics</span></span>
- [<span data-ttu-id="4c4e2-162">Onboarding mithilfe des Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4c4e2-163">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4c4e2-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="4c4e2-164">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4c4e2-164">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
