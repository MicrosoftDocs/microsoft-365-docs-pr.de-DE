---
title: Onboarding für den Microsoft Defender for Endpoint-Dienst
description: Informationen zum Onboarding von Endpunkten in den Microsoft Defender for Endpoint-Dienst
keywords: microsoft defender for endpoint, onboard, deploy
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933541"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4238c-104">Onboarding für den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="4238c-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4238c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4238c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4238c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4238c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4238c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4238c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4238c-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4238c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4238c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4238c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4238c-110">Erfahren Sie mehr über die verschiedenen Phasen der Bereitstellung von Microsoft Defender for Endpoint und über die Konfiguration der Funktionen innerhalb der Lösung.</span><span class="sxs-lookup"><span data-stu-id="4238c-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="4238c-111">Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:</span><span class="sxs-lookup"><span data-stu-id="4238c-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="4238c-112">[![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4238c-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="4238c-113">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="4238c-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="4238c-114">[![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4238c-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="4238c-115">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="4238c-115">Phase 2: Setup</span></span>](production-deployment.md) | ![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="4238c-117">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="4238c-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="4238c-118">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="4238c-118">*You are here!*</span></span>|

<span data-ttu-id="4238c-119">Sie befinden sich derzeit in der Onboardingphase.</span><span class="sxs-lookup"><span data-stu-id="4238c-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="4238c-120">Dies sind die Schritte, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="4238c-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="4238c-121">Schritt 1: Onboarding von Endpunkten für den Dienst</span><span class="sxs-lookup"><span data-stu-id="4238c-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="4238c-122">Schritt 2: Konfigurieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="4238c-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="4238c-123">Schritt 1: Onboarding von Endpunkten mithilfe eines der unterstützten Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="4238c-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="4238c-124">Im [Thema Bereitstellung planen](deployment-strategy.md) werden die allgemeinen Schritte beschrieben, die Sie zum Bereitstellen von Defender for Endpoint ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="4238c-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="4238c-125">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten, und erfahren Sie mehr über die verfügbaren Tools und Methoden.</span><span class="sxs-lookup"><span data-stu-id="4238c-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="4238c-126">Nachdem Sie Ihre Architektur identifiziert haben, müssen Sie entscheiden, welche Bereitstellungsmethode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4238c-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="4238c-127">Das von Ihnen auswählende Bereitstellungstool beeinflusst, wie Sie Endpunkte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="4238c-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="4238c-128">Onboardingtooloptionen</span><span class="sxs-lookup"><span data-stu-id="4238c-128">Onboarding tool options</span></span>

<span data-ttu-id="4238c-129">In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4238c-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="4238c-130">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4238c-130">Endpoint</span></span>     | <span data-ttu-id="4238c-131">Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="4238c-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="4238c-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4238c-132">**Windows**</span></span>  |  [<span data-ttu-id="4238c-133">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="4238c-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="4238c-134">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4238c-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="4238c-135">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="4238c-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="4238c-137">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="4238c-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="4238c-138">Integration in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="4238c-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="4238c-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="4238c-139">**macOS**</span></span>    | [<span data-ttu-id="4238c-140">Lokale Skripts</span><span class="sxs-lookup"><span data-stu-id="4238c-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="4238c-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="4238c-142">JAMF-Pro</span><span class="sxs-lookup"><span data-stu-id="4238c-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="4238c-143">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="4238c-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="4238c-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="4238c-144">**Linux Server**</span></span> | [<span data-ttu-id="4238c-145">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="4238c-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="4238c-146">100</span><span class="sxs-lookup"><span data-stu-id="4238c-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="4238c-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="4238c-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="4238c-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4238c-148">**iOS**</span></span>      | [<span data-ttu-id="4238c-149">App-basiert</span><span class="sxs-lookup"><span data-stu-id="4238c-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="4238c-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="4238c-150">**Android**</span></span>  | [<span data-ttu-id="4238c-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="4238c-152">Schritt 2: Konfigurieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="4238c-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="4238c-153">Nach dem Onboarding der Endpunkte konfigurieren Sie die verschiedenen Funktionen wie EDR, Schutz der nächsten Generation und Reduzierung der Angriffsfläche.</span><span class="sxs-lookup"><span data-stu-id="4238c-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="4238c-154">Beispielbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="4238c-154">Example deployments</span></span>
<span data-ttu-id="4238c-155">In diesem Bereitstellungshandbuch führen wir Sie durch die Verwendung von zwei Bereitstellungstools zum Onboarding von Endpunkten und zum Konfigurieren von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4238c-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="4238c-156">Die Tools in den Beispielbereitstellungen sind:</span><span class="sxs-lookup"><span data-stu-id="4238c-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="4238c-157">Onboarding mithilfe des Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4238c-158">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="4238c-159">Mithilfe der oben genannten Bereitstellungstools werden Sie dann bei der Konfiguration der folgenden Defender for Endpoint-Funktionen geführt:</span><span class="sxs-lookup"><span data-stu-id="4238c-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="4238c-160">Endpunkterkennung und Reaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="4238c-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="4238c-161">Schutzkonfiguration der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="4238c-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="4238c-162">Konfiguration der Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="4238c-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="4238c-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4238c-163">Related topics</span></span>
- [<span data-ttu-id="4238c-164">Onboarding mithilfe des Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4238c-165">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4238c-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="4238c-166">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4238c-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
