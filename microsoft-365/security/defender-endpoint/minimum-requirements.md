---
title: Mindestanforderungen für Microsoft Defender for Endpoint
description: Verstehen der Lizenzierungsanforderungen und -anforderungen für das Onboarding von Geräten in den Dienst
keywords: Mindestanforderungen, Lizenzierung, Vergleichstabelle
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
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061399"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="176db-104">Mindestanforderungen für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="176db-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="176db-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="176db-105">**Applies to:**</span></span>
- [<span data-ttu-id="176db-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="176db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="176db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="176db-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="176db-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="176db-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="176db-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="176db-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="176db-110">Es gibt einige Mindestanforderungen für das Onboarding von Geräten in den Dienst.</span><span class="sxs-lookup"><span data-stu-id="176db-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="176db-111">Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen, um Geräte in den Dienst zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="176db-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="176db-112">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="176db-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="176db-113">[Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="176db-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="176db-114">Erfahren Sie mehr über die neuesten Verbesserungen in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="176db-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="176db-115">Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="176db-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="176db-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="176db-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="176db-117">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="176db-117">Licensing requirements</span></span>
<span data-ttu-id="176db-118">Microsoft Defender for Endpoint erfordert eines der folgenden Microsoft Volumenlizenzangebote:</span><span class="sxs-lookup"><span data-stu-id="176db-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="176db-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="176db-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="176db-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="176db-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="176db-121">Microsoft 365 E5 (M365 E5) einschließlich Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="176db-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="176db-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="176db-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="176db-123">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="176db-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="176db-124">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="176db-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="176db-125">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="176db-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="176db-126">Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="176db-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="176db-127">Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="176db-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="176db-128">Microsoft Defender for Endpoint für Server erfordert eine der folgenden Lizenzierungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="176db-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="176db-129">Azure Security Center mit aktivierter Azure Defender</span><span class="sxs-lookup"><span data-stu-id="176db-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="176db-130">Microsoft Defender for Endpoint for Server (1 pro abgedeckten Server)</span><span class="sxs-lookup"><span data-stu-id="176db-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="176db-131">Kunden können Serverlizenzen (eine pro abgedeckte Serverbetriebssystemumgebung (OSE)) für Microsoft Defender for Endpoint für Server erwerben, wenn sie über mindestens 50 Lizenzen für eine oder mehrere der folgenden Benutzerlizenzen verfügen:</span><span class="sxs-lookup"><span data-stu-id="176db-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="176db-132">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="176db-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="176db-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="176db-133">Windows E5/A5</span></span>
> * <span data-ttu-id="176db-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="176db-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="176db-135">Microsoft 365 E5/A5 Security</span><span class="sxs-lookup"><span data-stu-id="176db-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="176db-136">Ausführliche Lizenzierungsinformationen finden Sie auf der [Website "Produktbedingungen",](https://www.microsoft.com/licensing/terms/) und arbeiten Sie mit Ihrem Kontoteam zusammen, um mehr über die Geschäftsbedingungen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="176db-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="176db-137">Weitere Informationen zum Array von Features in Windows 10-Editionen finden Sie unter [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span><span class="sxs-lookup"><span data-stu-id="176db-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="176db-138">Eine ausführliche Vergleichstabelle des Vergleichs der kommerziellen Windows 10-Edition finden Sie in der [PDF-Vergleichstabelle](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span><span class="sxs-lookup"><span data-stu-id="176db-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="176db-139">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="176db-139">Browser requirements</span></span>
<span data-ttu-id="176db-140">Der Zugriff auf Defender for Endpoint erfolgt über einen Browser, der die folgenden Browser unterstützt:</span><span class="sxs-lookup"><span data-stu-id="176db-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="176db-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="176db-141">Microsoft Edge</span></span>
- <span data-ttu-id="176db-142">Internet Explorer, Version 11</span><span class="sxs-lookup"><span data-stu-id="176db-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="176db-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="176db-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="176db-144">Während andere Browser möglicherweise funktionieren, werden die genannten Browser unterstützt.</span><span class="sxs-lookup"><span data-stu-id="176db-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="176db-145">Hardware- und Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="176db-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="176db-146">Unterstützte Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="176db-146">Supported Windows versions</span></span>
- <span data-ttu-id="176db-147">Windows 7 SP1 Enterprise ([Erfordert ESU für die Unterstützung](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="176db-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="176db-148">Windows 7 SP1 Pro ([Erfordert ESU für die Unterstützung](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="176db-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="176db-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="176db-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="176db-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="176db-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="176db-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="176db-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="176db-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="176db-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="176db-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="176db-153">Windows 10 Education</span></span>
- <span data-ttu-id="176db-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="176db-154">Windows 10 Pro</span></span>
- <span data-ttu-id="176db-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="176db-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="176db-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="176db-156">Windows server</span></span>
  - <span data-ttu-id="176db-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="176db-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="176db-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="176db-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="176db-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="176db-159">Windows Server 2016</span></span>
  - <span data-ttu-id="176db-160">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="176db-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="176db-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="176db-161">Windows Server 2019</span></span>
- <span data-ttu-id="176db-162">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="176db-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="176db-163">Auf Geräten in Ihrem Netzwerk muss eine dieser Editionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="176db-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="176db-164">Die Hardwareanforderungen für Defender for Endpoint auf Geräten sind für die unterstützten Editionen identisch.</span><span class="sxs-lookup"><span data-stu-id="176db-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="176db-165">Computer mit mobilen Versionen von Windows (z. B. Windows CE und Windows 10 Mobile) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="176db-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="176db-166">Bei virtuellen Computern mit Windows 10 Enterprise 2016 LTSB können Leistungsprobleme auftreten, wenn sie auf Nicht-Microsoft-Virtualisierungsplattformen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="176db-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="176db-167">Für virtuelle Umgebungen wird die Verwendung von Windows 10 Enterprise LTSC 2019 oder höher empfohlen.</span><span class="sxs-lookup"><span data-stu-id="176db-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="176db-168">Andere unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="176db-168">Other supported operating systems</span></span>
- <span data-ttu-id="176db-169">Android</span><span class="sxs-lookup"><span data-stu-id="176db-169">Android</span></span>
- <span data-ttu-id="176db-170">Linux</span><span class="sxs-lookup"><span data-stu-id="176db-170">Linux</span></span>
- <span data-ttu-id="176db-171">macOS</span><span class="sxs-lookup"><span data-stu-id="176db-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="176db-172">Sie müssen die genauen Linux-Verteilungen und -Versionen von Android und macOS kennen, die mit Defender for Endpoint kompatibel sind, damit die Integration funktioniert.</span><span class="sxs-lookup"><span data-stu-id="176db-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="176db-173">Anforderungen an Netzwerk- und Datenspeicherung und -konfiguration</span><span class="sxs-lookup"><span data-stu-id="176db-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="176db-174">Wenn Sie den Onboarding-Assistenten zum ersten Mal ausführen, müssen Sie auswählen, wo Ihre Microsoft Defender for Endpoint-bezogenen Informationen gespeichert sind: in der Europäischen Union, im Vereinigten Königreich oder im Rechenzentrum der Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="176db-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="176db-175">Der Datenspeicherort kann nach dem ersten Setup nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="176db-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="176db-176">Weitere Informationen dazu, wo und wie Microsoft Ihre Daten speichert, finden Sie unter Datenspeicherung und Datenschutz von Microsoft Defender for [Endpoint.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="176db-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="176db-177">Diagnosedateneinstellungen</span><span class="sxs-lookup"><span data-stu-id="176db-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="176db-178">Microsoft Defender for Endpoint erfordert keine bestimmte Diagnosestufe, solange sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="176db-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="176db-179">Stellen Sie sicher, dass der Diagnosedatendienst auf allen Geräten in Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="176db-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="176db-180">Standardmäßig ist dieser Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="176db-180">By default, this service is enabled.</span></span> <span data-ttu-id="176db-181">Es ist eine bewährte Methode, um sicherzustellen, dass Sie Sensordaten von ihnen erhalten.</span><span class="sxs-lookup"><span data-stu-id="176db-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="176db-182">**Verwenden Sie die Befehlszeile, um den Starttyp des Windows 10-Diagnosedatendiensts zu überprüfen:**</span><span class="sxs-lookup"><span data-stu-id="176db-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="176db-183">Öffnen Sie eine Befehlszeilenaufforderung mit erhöhten Rechten auf dem Gerät:</span><span class="sxs-lookup"><span data-stu-id="176db-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="176db-184">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="176db-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="176db-185">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="176db-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="176db-186">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="176db-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="176db-187">Wenn der Dienst aktiviert ist, sollte das Ergebnis wie der folgende Screenshot aussehen:</span><span class="sxs-lookup"><span data-stu-id="176db-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Ergebnis des sc-Abfragebefehls für diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="176db-189">Sie müssen festlegen, dass der Dienst  automatisch gestartet wird, START_TYPE nicht auf **AUTO_START.**</span><span class="sxs-lookup"><span data-stu-id="176db-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="176db-190">**Verwenden Sie die Befehlszeile, um den Windows 10-Diagnosedatendienst so zu legen, dass er automatisch gestartet wird:**</span><span class="sxs-lookup"><span data-stu-id="176db-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="176db-191">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten am Endpunkt:</span><span class="sxs-lookup"><span data-stu-id="176db-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="176db-192">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="176db-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="176db-193">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="176db-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="176db-194">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="176db-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="176db-195">Es wird eine Erfolgsmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="176db-195">A success message is displayed.</span></span> <span data-ttu-id="176db-196">Überprüfen Sie die Änderung, indem Sie den folgenden Befehl eingeben, und drücken Sie die **EINGABETASTE:**</span><span class="sxs-lookup"><span data-stu-id="176db-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="176db-197">Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="176db-197">Internet connectivity</span></span>
<span data-ttu-id="176db-198">Die Internetverbindung auf Geräten ist entweder direkt oder über Proxy erforderlich.</span><span class="sxs-lookup"><span data-stu-id="176db-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="176db-199">Der Defender for Endpoint-Sensor kann eine tägliche durchschnittliche Bandbreite von 5 MB nutzen, um mit dem Defender for Endpoint-Clouddienst zu kommunizieren und Cyberdaten zu melden.</span><span class="sxs-lookup"><span data-stu-id="176db-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="176db-200">One-off-Aktivitäten wie Dateiuploads und Untersuchungspaketsammlungen sind in dieser täglichen durchschnittlichen Bandbreite nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="176db-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="176db-201">Weitere Informationen zu zusätzlichen Proxykonfigurationseinstellungen finden Sie unter [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="176db-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="176db-202">Bevor Sie Geräte integrieren, muss der Diagnosedatendienst aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="176db-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="176db-203">Der Dienst ist in Windows 10 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="176db-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="176db-204">Konfigurationsanforderung für Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="176db-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="176db-205">Der Defender for Endpoint-Agent hängt von der Fähigkeit von Microsoft Defender Antivirus ab, Dateien zu überprüfen und Informationen darüber zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="176db-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="176db-206">Konfigurieren Sie Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischalware ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="176db-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="176db-207">Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="176db-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="176db-208">Wenn Microsoft Defender Antivirus nicht die aktive Antischalware in Ihrer Organisation ist und Sie den Defender for Endpoint-Dienst verwenden, wechselt Microsoft Defender Antivirus in den passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="176db-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="176db-209">Wenn Microsoft Defender Antivirus in Ihrer Organisation über Gruppenrichtlinien oder andere Methoden deaktiviert wurde, müssen integrierte Geräte von dieser Gruppenrichtlinie ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="176db-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="176db-210">Wenn Sie Server onboardieren und Microsoft Defender Antivirus nicht die aktive Antischalware auf Ihren Servern ist, muss Microsoft Defender Antivirus entweder für den passiven Modus konfiguriert oder deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="176db-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="176db-211">Die Konfiguration hängt von der Serverversion ab.</span><span class="sxs-lookup"><span data-stu-id="176db-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="176db-212">Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="176db-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="176db-213">Ihre reguläre Gruppenrichtlinie gilt nicht für Tamper Protection, und Änderungen an Microsoft Defender Antivirus-Einstellungen werden ignoriert, wenn Tamper Protection installiert ist.</span><span class="sxs-lookup"><span data-stu-id="176db-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="176db-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM)-Treiber ist aktiviert</span><span class="sxs-lookup"><span data-stu-id="176db-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="176db-215">Wenn Sie Microsoft Defender Antivirus als primäres Antischalwareprodukt auf Ihren Geräten ausführen, wird der Defender for Endpoint-Agent erfolgreich onboarding.</span><span class="sxs-lookup"><span data-stu-id="176db-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="176db-216">Wenn Sie einen Antischasoftwareclient eines Drittanbieters ausführen und Mobile Device Management-Lösungen oder Microsoft Endpoint Manager (aktuelle Zweigstelle) verwenden, müssen Sie sicherstellen, dass der Microsoft Defender Antivirus -ELAM-Treiber aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="176db-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="176db-217">Weitere Informationen finden Sie unter [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="176db-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="176db-218">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="176db-218">Related topics</span></span>
- [<span data-ttu-id="176db-219">Einrichten der Bereitstellung von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="176db-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="176db-220">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="176db-220">Onboard devices</span></span>](onboard-configure.md)
