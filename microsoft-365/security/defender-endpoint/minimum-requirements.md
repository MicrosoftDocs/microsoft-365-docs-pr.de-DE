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
ms.openlocfilehash: 6607d5029e45c77754a431c87eb61cd281e013c1
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730726"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="2c3fd-104">Mindestanforderungen für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c3fd-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c3fd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2c3fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="2c3fd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2c3fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c3fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c3fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c3fd-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2c3fd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2c3fd-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="2c3fd-110">Es gibt einige Mindestanforderungen für das Onboarding von Geräten in den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="2c3fd-111">Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen, um Geräte in den Dienst zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="2c3fd-112">Erfahren Sie mehr über die neuesten Verbesserungen in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="2c3fd-113">Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="2c3fd-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2c3fd-115">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-115">Licensing requirements</span></span>

<span data-ttu-id="2c3fd-116">Microsoft Defender for Endpoint erfordert eines der folgenden Microsoft Volumenlizenzangebote:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="2c3fd-117">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2c3fd-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="2c3fd-118">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="2c3fd-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="2c3fd-119">Microsoft 365 E5 (M365 E5) einschließlich Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2c3fd-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="2c3fd-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="2c3fd-121">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="2c3fd-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="2c3fd-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="2c3fd-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="2c3fd-123">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2c3fd-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-124">Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="2c3fd-125">Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="2c3fd-126">RDSH-VMs benötigen keine separate Defender for Endpoint-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="2c3fd-127">Microsoft Defender for Endpoint für Server erfordert eine der folgenden Lizenzierungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="2c3fd-128">Azure Security Center mit aktivierter Azure Defender</span><span class="sxs-lookup"><span data-stu-id="2c3fd-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="2c3fd-129">Microsoft Defender for Endpoint for Server (1 pro abgedeckten Server)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-130">Kunden können Serverlizenzen (eine pro abgedeckte Serverbetriebssystemumgebung (OSE)) für Microsoft Defender for Endpoint für Server erwerben, wenn sie über mindestens 50 Lizenzen für eine oder mehrere der folgenden Benutzerlizenzen verfügen:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="2c3fd-131">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2c3fd-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="2c3fd-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c3fd-132">Windows E5/A5</span></span>
> * <span data-ttu-id="2c3fd-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c3fd-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="2c3fd-134">Microsoft 365 E5/A5-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2c3fd-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="2c3fd-135">Ausführliche Lizenzierungsinformationen finden Sie auf der [Website "Produktbedingungen",](https://www.microsoft.com/licensing/terms/) und arbeiten Sie mit Ihrem Kontoteam zusammen, um mehr über die Geschäftsbedingungen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="2c3fd-136">Weitere Informationen zum Array von Features in Windows 10 finden Sie unter [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="2c3fd-137">Eine detaillierte Vergleichstabelle mit Windows 10 kommerziellen Editionen finden Sie in der [PDF-Vergleichstabelle](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2c3fd-138">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-138">Browser requirements</span></span>

<span data-ttu-id="2c3fd-139">Der Zugriff auf Defender for Endpoint erfolgt über einen Browser, der die folgenden Browser unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="2c3fd-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2c3fd-140">Microsoft Edge</span></span>
- <span data-ttu-id="2c3fd-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2c3fd-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-142">Während andere Browser möglicherweise funktionieren, werden die genannten Browser unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="2c3fd-143">Hardware- und Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="2c3fd-144">Unterstützte Windows Versionen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-144">Supported Windows versions</span></span>

- <span data-ttu-id="2c3fd-145">Windows 7 SP1 Enterprise ([Erfordert ESU für die Unterstützung](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-145">Windows 7 SP1 Enterprise ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="2c3fd-146">Windows 7 SP1 Pro ([Erfordert ESU für die Unterstützung](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-146">Windows 7 SP1 Pro ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="2c3fd-147">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c3fd-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="2c3fd-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="2c3fd-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="2c3fd-149">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c3fd-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="2c3fd-150">Windows 10 Enterprise LTSC 2016 (oder höher)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-150">Windows 10 Enterprise LTSC 2016 (or later)</span></span>](/windows/whats-new/ltsc/)
- <span data-ttu-id="2c3fd-151">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="2c3fd-151">Windows 10 Education</span></span>
- <span data-ttu-id="2c3fd-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="2c3fd-152">Windows 10 Pro</span></span>
- <span data-ttu-id="2c3fd-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="2c3fd-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="2c3fd-154">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2c3fd-154">Windows server</span></span>
  - <span data-ttu-id="2c3fd-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="2c3fd-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="2c3fd-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2c3fd-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="2c3fd-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2c3fd-157">Windows Server 2016</span></span>
  - <span data-ttu-id="2c3fd-158">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="2c3fd-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="2c3fd-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2c3fd-159">Windows Server 2019</span></span>
- <span data-ttu-id="2c3fd-160">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="2c3fd-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="2c3fd-161">Auf Geräten in Ihrem Netzwerk muss eine dieser Editionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="2c3fd-162">Die Hardwareanforderungen für Defender for Endpoint auf Geräten sind für die unterstützten Editionen identisch.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-163">Computer mit mobilen Versionen Windows (z. B. Windows CE und Windows 10 Mobile) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="2c3fd-164">Virtuelle Computer, auf Windows 10 Enterprise 2016 LTSB ausgeführt werden, können Leistungsprobleme auftreten, wenn sie auf Nicht-Microsoft-Virtualisierungsplattformen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="2c3fd-165">Für virtuelle Umgebungen wird die Verwendung Windows 10 Enterprise LTSC 2019 oder höher empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="2c3fd-166">Andere unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="2c3fd-166">Other supported operating systems</span></span>

- [<span data-ttu-id="2c3fd-167">Android</span><span class="sxs-lookup"><span data-stu-id="2c3fd-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="2c3fd-168">iOS</span><span class="sxs-lookup"><span data-stu-id="2c3fd-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="2c3fd-169">Linux</span><span class="sxs-lookup"><span data-stu-id="2c3fd-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="2c3fd-170">macOS</span><span class="sxs-lookup"><span data-stu-id="2c3fd-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="2c3fd-171">Sie müssen bestätigen, dass die Linux-Verteilungen und -Versionen von Android, iOS und macOS mit Defender for Endpoint kompatibel sind, damit die Integration funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-171">You'll need to confirm the Linux distributions and versions of Android, iOS, and macOS are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="2c3fd-172">Anforderungen an Netzwerk- und Datenspeicherung und -konfiguration</span><span class="sxs-lookup"><span data-stu-id="2c3fd-172">Network and data storage and configuration requirements</span></span>

<span data-ttu-id="2c3fd-173">Wenn Sie den Onboarding-Assistenten zum ersten Mal ausführen, müssen Sie auswählen, wo Ihre Microsoft Defender for Endpoint-bezogenen Informationen gespeichert sind: in der Europäischen Union, im Vereinigten Königreich oder im Rechenzentrum der Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="2c3fd-174">Der Datenspeicherort kann nach dem ersten Setup nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="2c3fd-175">Weitere Informationen dazu, wo und wie Microsoft Ihre Daten speichert, finden Sie unter Datenspeicherung und Datenschutz von Microsoft Defender for [Endpoint.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="2c3fd-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="2c3fd-176">Diagnosedateneinstellungen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-177">Microsoft Defender for Endpoint erfordert keine bestimmte Diagnosestufe, solange sie aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="2c3fd-178">Stellen Sie sicher, dass der Diagnosedatendienst auf allen Geräten in Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="2c3fd-179">Standardmäßig ist dieser Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-179">By default, this service is enabled.</span></span> <span data-ttu-id="2c3fd-180">Es ist eine bewährte Methode, um sicherzustellen, dass Sie Sensordaten von ihnen erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="2c3fd-181">**Verwenden Sie die Befehlszeile, um den Starttyp Windows 10 Diagnosedatendiensts zu überprüfen:**</span><span class="sxs-lookup"><span data-stu-id="2c3fd-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="2c3fd-182">Öffnen Sie eine Befehlszeilenaufforderung mit erhöhten Rechten auf dem Gerät:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="2c3fd-183">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="2c3fd-184">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2c3fd-185">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="2c3fd-186">Wenn der Dienst aktiviert ist, sollte das Ergebnis wie der folgende Screenshot aussehen:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Ergebnis des sc-Abfragebefehls für diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="2c3fd-188">Sie müssen festlegen, dass der Dienst automatisch gestartet wird, **START_TYPE** nicht auf **AUTO_START.**</span><span class="sxs-lookup"><span data-stu-id="2c3fd-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="2c3fd-189">**Verwenden Sie die Befehlszeile, um den Diagnosedatendienst Windows 10 automatisch zu starten:**</span><span class="sxs-lookup"><span data-stu-id="2c3fd-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="2c3fd-190">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten am Endpunkt:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="2c3fd-191">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="2c3fd-192">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="2c3fd-193">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:</span><span class="sxs-lookup"><span data-stu-id="2c3fd-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="2c3fd-194">Es wird eine Erfolgsmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-194">A success message is displayed.</span></span> <span data-ttu-id="2c3fd-195">Überprüfen Sie die Änderung, indem Sie den folgenden Befehl eingeben, und drücken Sie die **EINGABETASTE:**</span><span class="sxs-lookup"><span data-stu-id="2c3fd-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="2c3fd-196">Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="2c3fd-196">Internet connectivity</span></span>

<span data-ttu-id="2c3fd-197">Die Internetverbindung auf Geräten ist entweder direkt oder über Proxy erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="2c3fd-198">Der Defender for Endpoint-Sensor kann eine tägliche durchschnittliche Bandbreite von 5 MB verwenden, um mit dem Defender for Endpoint-Clouddienst zu kommunizieren und Cyberdaten zu melden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="2c3fd-199">Einmalaktivitäten wie Dateiuploads und Untersuchungspaketsammlungen sind in dieser täglichen durchschnittlichen Bandbreite nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="2c3fd-200">Weitere Informationen zu zusätzlichen Proxykonfigurationseinstellungen finden Sie unter [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="2c3fd-201">Bevor Sie Geräte integrieren, muss der Diagnosedatendienst aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="2c3fd-202">Der Dienst ist standardmäßig in der Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="2c3fd-203">Microsoft Defender Antivirus Konfigurationsanforderung</span><span class="sxs-lookup"><span data-stu-id="2c3fd-203">Microsoft Defender Antivirus configuration requirement</span></span>

<span data-ttu-id="2c3fd-204">Der Defender for Endpoint-Agent hängt von der Möglichkeit ab, Microsoft Defender Antivirus Dateien zu überprüfen und Informationen darüber zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="2c3fd-205">Konfigurieren Sie Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten, Microsoft Defender Antivirus die aktive Antischalware ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="2c3fd-206">Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="2c3fd-207">Wenn Microsoft Defender Antivirus nicht die aktive Antischalware in Ihrer Organisation ist und Sie den Defender for Endpoint-Dienst verwenden, wird Microsoft Defender Antivirus passiver Modus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="2c3fd-208">Wenn Ihre Organisation die Microsoft Defender Antivirus gruppenrichtlinien oder anderen Methoden deaktiviert hat, müssen geräte, die onboarded sind, von dieser Gruppenrichtlinie ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="2c3fd-209">Wenn Sie Server onboardieren und Microsoft Defender Antivirus nicht die aktive Antischalware auf Ihren Servern ist, muss Microsoft Defender Antivirus entweder für den passiven Modus konfiguriert oder deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="2c3fd-210">Die Konfiguration hängt von der Serverversion ab.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="2c3fd-211">Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-211">For more information, see [Microsoft Defender Antivirus compatibility](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fd-212">Ihre reguläre Gruppenrichtlinie gilt nicht für Tamper Protection, und Änderungen an Microsoft Defender Antivirus werden ignoriert, wenn Tamper Protection ein ist.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="2c3fd-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM)-Treiber ist aktiviert</span><span class="sxs-lookup"><span data-stu-id="2c3fd-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>

<span data-ttu-id="2c3fd-214">Wenn Sie die Microsoft Defender Antivirus als primäres Antischalwareprodukt auf Ihren Geräten ausführen, wird der Defender for Endpoint-Agent erfolgreich onboarding.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="2c3fd-215">Wenn Sie einen Antischalwareclient eines Drittanbieters ausführen und Mobile Device Management-Lösungen oder Microsoft Endpoint Manager (aktuelle Zweigstelle) verwenden, müssen Sie sicherstellen, dass der Microsoft Defender Antivirus-ELAM-Treiber aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2c3fd-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="2c3fd-216">Weitere Informationen finden Sie unter [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="2c3fd-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="2c3fd-217">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2c3fd-217">Related topics</span></span>

- [<span data-ttu-id="2c3fd-218">Einrichten der Bereitstellung von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c3fd-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="2c3fd-219">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="2c3fd-219">Onboard devices</span></span>](onboard-configure.md)
