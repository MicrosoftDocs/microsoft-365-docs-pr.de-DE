---
title: Planen der Bereitstellung von Microsoft Defender for Endpoint
description: Wählen Sie die beste Microsoft Defender for Endpoint-Bereitstellungsstrategie für Ihre Umgebung aus.
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163575"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="2d164-104">Planen der Bereitstellung von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d164-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d164-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2d164-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d164-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2d164-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2d164-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d164-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2d164-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2d164-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2d164-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2d164-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="2d164-110">Planen Sie Ihre Microsoft Defender for Endpoint-Bereitstellung, damit Sie die Sicherheitsfunktionen innerhalb der Suite maximieren und Ihr Unternehmen besser vor Cyberbedrohungen schützen können.</span><span class="sxs-lookup"><span data-stu-id="2d164-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="2d164-111">Diese Lösung enthält Anleitungen zum Identifizieren Ihrer Umgebungsarchitektur, zum Auswählen der Art des Bereitstellungstools, das Ihren Anforderungen am besten entspricht, und Anleitungen zum Konfigurieren von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2d164-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Abbildung des Bereitstellungsflusses](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="2d164-113">Schritt 1: Identifizieren der Architektur</span><span class="sxs-lookup"><span data-stu-id="2d164-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="2d164-114">Wir wissen, dass jede Unternehmensumgebung einzigartig ist, daher haben wir verschiedene Optionen bereitgestellt, um Ihnen die Flexibilität bei der Auswahl der Bereitstellung des Diensts zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2d164-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="2d164-115">Je nach Ihrer Umgebung eignen sich einige Tools für bestimmte Architekturen besser.</span><span class="sxs-lookup"><span data-stu-id="2d164-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="2d164-116">Verwenden Sie das folgende Material, um die geeignete Defender for Endpoint-Architektur auszuwählen, die am besten in Ihrer Organisation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d164-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="2d164-117">Element</span><span class="sxs-lookup"><span data-stu-id="2d164-117">Item</span></span> | <span data-ttu-id="2d164-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d164-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="2d164-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="2d164-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="2d164-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="2d164-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="2d164-121">Das Architekturmaterial hilft Ihnen bei der Planung der Bereitstellung für die folgenden Architekturen:</span><span class="sxs-lookup"><span data-stu-id="2d164-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="2d164-122">Cloudspezifisch</span><span class="sxs-lookup"><span data-stu-id="2d164-122">Cloud-native</span></span> </li><li> <span data-ttu-id="2d164-123">Co-Management</span><span class="sxs-lookup"><span data-stu-id="2d164-123">Co-management</span></span> </li><li> <span data-ttu-id="2d164-124">Lokal</span><span class="sxs-lookup"><span data-stu-id="2d164-124">On-premise</span></span></li><li><span data-ttu-id="2d164-125">Auswertung und lokales Onboarding</span><span class="sxs-lookup"><span data-stu-id="2d164-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="2d164-126">Schritt 2: Bereitstellungsmethode auswählen</span><span class="sxs-lookup"><span data-stu-id="2d164-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="2d164-127">Defender for Endpoint unterstützt eine Vielzahl von Endpunkten, die Sie in den Dienst integrieren können.</span><span class="sxs-lookup"><span data-stu-id="2d164-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="2d164-128">In der folgenden Tabelle sind die unterstützten Endpunkte und das entsprechende Bereitstellungstool aufgeführt, das Sie verwenden können, damit Sie die Bereitstellung entsprechend planen können.</span><span class="sxs-lookup"><span data-stu-id="2d164-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="2d164-129">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2d164-129">Endpoint</span></span>     | <span data-ttu-id="2d164-130">Bereitstellungstool</span><span class="sxs-lookup"><span data-stu-id="2d164-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="2d164-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2d164-131">**Windows**</span></span>  |  [<span data-ttu-id="2d164-132">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="2d164-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="2d164-133">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2d164-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="2d164-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="2d164-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="2d164-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2d164-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="2d164-136">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="2d164-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="2d164-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="2d164-137">**macOS**</span></span>    | [<span data-ttu-id="2d164-138">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="2d164-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="2d164-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2d164-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="2d164-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="2d164-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="2d164-141">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="2d164-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="2d164-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="2d164-142">**Linux Server**</span></span> | [<span data-ttu-id="2d164-143">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="2d164-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="2d164-144">100</span><span class="sxs-lookup"><span data-stu-id="2d164-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="2d164-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="2d164-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="2d164-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2d164-146">**iOS**</span></span>      | [<span data-ttu-id="2d164-147">App-basiert</span><span class="sxs-lookup"><span data-stu-id="2d164-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="2d164-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="2d164-148">**Android**</span></span>  | [<span data-ttu-id="2d164-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2d164-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="2d164-150">Schritt 3: Konfigurieren von Funktionen</span><span class="sxs-lookup"><span data-stu-id="2d164-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="2d164-151">Konfigurieren Sie nach dem Onboarding von Endpunkten die Sicherheitsfunktionen in Defender for Endpoint, damit Sie den robusten Sicherheitsschutz maximieren können, der in der Suite verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2d164-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="2d164-152">Zu den Funktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="2d164-152">Capabilities include:</span></span>

- <span data-ttu-id="2d164-153">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2d164-153">Endpoint detection and response</span></span>
- <span data-ttu-id="2d164-154">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="2d164-154">Next-generation protection</span></span>
- <span data-ttu-id="2d164-155">Angriffsfläche verringern</span><span class="sxs-lookup"><span data-stu-id="2d164-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="2d164-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2d164-156">Related topics</span></span>
- [<span data-ttu-id="2d164-157">Bereitstellungsphasen</span><span class="sxs-lookup"><span data-stu-id="2d164-157">Deployment phases</span></span>](deployment-phases.md)
