---
title: Bereitstellen von Microsoft Defender for Endpoint in Ringen
description: Informationen zum Bereitstellen von Microsoft Defender for Endpoint in Ringen
keywords: deploy, rings, evaluate, pilot, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2d34b984436b3ed0537af2eebcd8475ec270cd8e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165789"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="b2452-104">Bereitstellen von Microsoft Defender for Endpoint in Ringen</span><span class="sxs-lookup"><span data-stu-id="b2452-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b2452-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b2452-105">**Applies to:**</span></span>
- [<span data-ttu-id="b2452-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2452-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b2452-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2452-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b2452-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b2452-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b2452-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b2452-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b2452-110">Die Bereitstellung von Microsoft Defender for Endpoint kann mithilfe eines ringbasierten Bereitstellungsansatzes durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b2452-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="b2452-111">Die Bereitstellungsringe können in den folgenden Szenarien angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="b2452-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="b2452-112">Neue Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="b2452-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="b2452-113">Vorhandene Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="b2452-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="b2452-114">Neue Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="b2452-114">New deployments</span></span>

![Abbildung von Bereitstellungsringen](images/deployment-rings.png)


<span data-ttu-id="b2452-116">Ein ringbasierter Ansatz ist eine Methode zum Identifizieren einer Gruppe von Endpunkten, die onboardiert werden müssen, und zum Überprüfen, ob bestimmte Kriterien erfüllt sind, bevor der Dienst auf einer größeren Gruppe von Geräten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b2452-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="b2452-117">Sie können die Beendigungskriterien für jeden Ring definieren und sicherstellen, dass sie erfüllt sind, bevor Sie zum nächsten Ring fahren.</span><span class="sxs-lookup"><span data-stu-id="b2452-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="b2452-118">Die Einführung einer ringbasierten Bereitstellung trägt dazu bei, potenzielle Probleme zu reduzieren, die beim Einführung des Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b2452-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="b2452-119">Indem Sie zuerst eine bestimmte Anzahl von Geräten pilotieren, können Sie potenzielle Probleme identifizieren und potenzielle Risiken mindern, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b2452-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="b2452-120">Tabelle 1 enthält ein Beispiel für die Bereitstellungsringe, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b2452-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="b2452-121">**Tabelle 1**</span><span class="sxs-lookup"><span data-stu-id="b2452-121">**Table 1**</span></span>

|<span data-ttu-id="b2452-122">**Bereitstellungsring**</span><span class="sxs-lookup"><span data-stu-id="b2452-122">**Deployment ring**</span></span>|<span data-ttu-id="b2452-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b2452-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="b2452-124">Auswerten</span><span class="sxs-lookup"><span data-stu-id="b2452-124">Evaluate</span></span> | <span data-ttu-id="b2452-125">Ring 1: Identifizieren von 50 Systemen für Pilottests</span><span class="sxs-lookup"><span data-stu-id="b2452-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="b2452-126">Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="b2452-126">Pilot</span></span> | <span data-ttu-id="b2452-127">Ring 2: Identifizieren der nächsten 50-100 Endpunkte in der Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="b2452-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="b2452-128">Vollständige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b2452-128">Full deployment</span></span> | <span data-ttu-id="b2452-129">Ring 3: Rollout des Diensts für den Rest der Umgebung in größeren Schritten</span><span class="sxs-lookup"><span data-stu-id="b2452-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="b2452-130">Beendigungskriterien</span><span class="sxs-lookup"><span data-stu-id="b2452-130">Exit criteria</span></span>
<span data-ttu-id="b2452-131">Ein Beispielsatz von Beendigungskriterien für diese Ringe kann Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="b2452-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="b2452-132">Geräte werden in der Geräteinventarliste angezeigt</span><span class="sxs-lookup"><span data-stu-id="b2452-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="b2452-133">Warnungen werden im Dashboard angezeigt</span><span class="sxs-lookup"><span data-stu-id="b2452-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="b2452-134">Ausführen eines Erkennungstests</span><span class="sxs-lookup"><span data-stu-id="b2452-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="b2452-135">Ausführen eines simulierten Angriffs auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="b2452-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="b2452-136">Auswerten</span><span class="sxs-lookup"><span data-stu-id="b2452-136">Evaluate</span></span>
<span data-ttu-id="b2452-137">Identifizieren Sie eine kleine Anzahl von Testcomputern in Ihrer Umgebung, die für das Onboarding in den Dienst verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2452-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="b2452-138">Idealerweise wären diese Computer weniger als 50 Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="b2452-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="b2452-139">Pilotprojekt</span><span class="sxs-lookup"><span data-stu-id="b2452-139">Pilot</span></span>
<span data-ttu-id="b2452-140">Microsoft Defender ATP unterstützt eine Vielzahl von Endpunkten, die Sie in den Dienst integrieren können.</span><span class="sxs-lookup"><span data-stu-id="b2452-140">Microsoft Defender ATP supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="b2452-141">Identifizieren Sie in diesem Ring mehrere Zu integrierende Geräte, und fahren Sie basierend auf den von Ihnen definierten Beendigungskriterien mit dem nächsten Bereitstellungsring fort.</span><span class="sxs-lookup"><span data-stu-id="b2452-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="b2452-142">In der folgenden Tabelle sind die unterstützten Endpunkte und das entsprechende Tool aufgeführt, mit dem Sie Geräte in den Dienst integrieren können.</span><span class="sxs-lookup"><span data-stu-id="b2452-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="b2452-143">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2452-143">Endpoint</span></span>     | <span data-ttu-id="b2452-144">Bereitstellungstool</span><span class="sxs-lookup"><span data-stu-id="b2452-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="b2452-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b2452-145">**Windows**</span></span>  |  [<span data-ttu-id="b2452-146">Lokales Skript (bis zu 10 Geräte)</span><span class="sxs-lookup"><span data-stu-id="b2452-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="b2452-147">HINWEIS: Wenn Sie mehr als 10 Geräte in einer Produktionsumgebung bereitstellen möchten, verwenden Sie stattdessen die Gruppenrichtlinienmethode oder die anderen unten aufgeführten unterstützten Tools.</span><span class="sxs-lookup"><span data-stu-id="b2452-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="b2452-148">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b2452-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="b2452-149">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="b2452-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="b2452-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b2452-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="b2452-151">VDI-Skripts</span><span class="sxs-lookup"><span data-stu-id="b2452-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="b2452-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b2452-152">**macOS**</span></span>    | [<span data-ttu-id="b2452-153">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="b2452-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="b2452-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b2452-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="b2452-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="b2452-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="b2452-156">Verwaltung mobiler Geräte - Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="b2452-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="b2452-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="b2452-157">**Linux Server**</span></span> | [<span data-ttu-id="b2452-158">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="b2452-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="b2452-159">100</span><span class="sxs-lookup"><span data-stu-id="b2452-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="b2452-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="b2452-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="b2452-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b2452-161">**iOS**</span></span>      | [<span data-ttu-id="b2452-162">App-basiert</span><span class="sxs-lookup"><span data-stu-id="b2452-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="b2452-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="b2452-163">**Android**</span></span>  | [<span data-ttu-id="b2452-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b2452-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="b2452-165">Vollständige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b2452-165">Full deployment</span></span>
<span data-ttu-id="b2452-166">In dieser Phase können Sie das [Bereitstellungsmaterial planen](deployment-strategy.md) verwenden, um Die Bereitstellung zu planen.</span><span class="sxs-lookup"><span data-stu-id="b2452-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="b2452-167">Verwenden Sie das folgende Material, um die geeignete Microsoft Defender ATP-Architektur auszuwählen, die Am besten in Ihre Organisation einwählt.</span><span class="sxs-lookup"><span data-stu-id="b2452-167">Use the following material to select the appropriate Microsoft Defender ATP architecture that best suites your organization.</span></span>

|<span data-ttu-id="b2452-168">**Aspekt**</span><span class="sxs-lookup"><span data-stu-id="b2452-168">**Item**</span></span>|<span data-ttu-id="b2452-169">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b2452-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2452-170">[![Miniaturbild zur Microsoft Defender ATP-Bereitstellungsstrategie](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="b2452-170">[![Thumb image for Microsoft Defender ATP deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="b2452-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="b2452-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="b2452-172">Das Architekturmaterial hilft Ihnen bei der Planung der Bereitstellung für die folgenden Architekturen:</span><span class="sxs-lookup"><span data-stu-id="b2452-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="b2452-173">Cloudspezifisch</span><span class="sxs-lookup"><span data-stu-id="b2452-173">Cloud-native</span></span> </li><li> <span data-ttu-id="b2452-174">Co-Management</span><span class="sxs-lookup"><span data-stu-id="b2452-174">Co-management</span></span> </li><li> <span data-ttu-id="b2452-175">Lokal</span><span class="sxs-lookup"><span data-stu-id="b2452-175">On-premise</span></span></li><li><span data-ttu-id="b2452-176">Auswertung und lokales Onboarding</span><span class="sxs-lookup"><span data-stu-id="b2452-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="b2452-177">Vorhandene Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="b2452-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="b2452-178">Windows-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="b2452-178">Windows endpoints</span></span>
<span data-ttu-id="b2452-179">Für Windows- und/oder Windows-Server wählen Sie mehrere Computer aus, die Sie mit dem Security **Update Validation Program (SUVP)** im Voraus testen möchten (vor patch Tuesday).</span><span class="sxs-lookup"><span data-stu-id="b2452-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="b2452-180">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="b2452-180">For more information, see:</span></span>
- [<span data-ttu-id="b2452-181">Was ist das Validierungsprogramm für Sicherheitsupdates?</span><span class="sxs-lookup"><span data-stu-id="b2452-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="b2452-182">Softwareupdatevalidierungsprogramm und Microsoft Center zum Schutz vor Malware Einrichtung – Interaktive TwC-Zeitachse Teil 4</span><span class="sxs-lookup"><span data-stu-id="b2452-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="b2452-183">Nicht-Windows-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="b2452-183">Non-Windows endpoints</span></span>
<span data-ttu-id="b2452-184">Mit macOS und Linux können Sie einige Systeme verwenden und im Kanal "InsidersFast" ausführen.</span><span class="sxs-lookup"><span data-stu-id="b2452-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="b2452-185">Idealerweise mindestens ein Sicherheitsadministrator und ein Entwickler, damit Sie Kompatibilitäts-, Leistungs- und Zuverlässigkeitsprobleme finden können, bevor der Build den Build in den "Production"-Kanal schafft.</span><span class="sxs-lookup"><span data-stu-id="b2452-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="b2452-186">Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="b2452-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="b2452-187">Geräte in insiders-fast sind die ersten, die Updates und neue Features erhalten, gefolgt von insiders-slow und schließlich von prod.</span><span class="sxs-lookup"><span data-stu-id="b2452-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![Bild von Insiderringen](images/insider-rings.png)

<span data-ttu-id="b2452-189">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder insider-schnell oder insider-slow verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2452-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="b2452-190">Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b2452-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="b2452-191">Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b2452-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>