---
title: Mindestanforderungen für Microsoft Defender für Endpunkt
description: Grundlegendes zu den Lizenzierungsanforderungen und Anforderungen für das Onboarding von Geräten in den Dienst
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
ms.openlocfilehash: ccff6abcfcd1a2da32a8e1614a2de45afed69aef
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842998"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="4244f-104">Mindestanforderungen für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4244f-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4244f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4244f-105">**Applies to:**</span></span>

- [<span data-ttu-id="4244f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4244f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4244f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4244f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4244f-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4244f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4244f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4244f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="4244f-110">Es gibt einige Mindestanforderungen für das Onboarding von Geräten in den Dienst.</span><span class="sxs-lookup"><span data-stu-id="4244f-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="4244f-111">Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen und andere Konfigurationseinstellungen zum Onboarding von Geräten in den Dienst.</span><span class="sxs-lookup"><span data-stu-id="4244f-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="4244f-112">Erfahren Sie mehr über die neuesten Verbesserungen in Defender für Endpunkt: [Defender für Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="4244f-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="4244f-113">Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="4244f-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="4244f-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="4244f-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4244f-115">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4244f-115">Licensing requirements</span></span>

<span data-ttu-id="4244f-116">Microsoft Defender für Endpunkt erfordert eines der folgenden Microsoft-Volumenlizenzierungsangebote:</span><span class="sxs-lookup"><span data-stu-id="4244f-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="4244f-117">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="4244f-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="4244f-118">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="4244f-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="4244f-119">Microsoft 365 E5 (M365 E5), das Windows 10 Enterprise E5 enthält</span><span class="sxs-lookup"><span data-stu-id="4244f-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="4244f-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="4244f-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="4244f-121">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="4244f-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="4244f-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="4244f-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="4244f-123">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4244f-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-124">Berechtigte lizenzierte Benutzer können Microsoft Defender für Endpunkt auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4244f-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="4244f-125">Microsoft Defender für Endpunkt steht auch zum Kauf über einen Cloud Solution Provider (CSP) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4244f-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="4244f-126">RDSH-VMs erfordern keine separate Defender für Endpunkt-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="4244f-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="4244f-127">Microsoft Defender für Endpunkt für Server erfordert eine der folgenden Lizenzierungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="4244f-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="4244f-128">Azure Security Center mit aktiviertem Azure Defender</span><span class="sxs-lookup"><span data-stu-id="4244f-128">Azure Security Center with Azure Defender enabled</span></span>](/azure/security-center/security-center-pricing)
- <span data-ttu-id="4244f-129">Microsoft Defender für Endpunkt für Server (eine pro abgedeckten Server)</span><span class="sxs-lookup"><span data-stu-id="4244f-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-130">Kunden können Serverlizenzen (eine pro abgedeckter Serverbetriebssystemumgebung (OSE)) für Microsoft Defender für Endpunkt für Server erwerben, wenn sie insgesamt mindestens 50 Lizenzen für eine oder mehrere der folgenden Benutzerlizenzen besitzen:</span><span class="sxs-lookup"><span data-stu-id="4244f-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="4244f-131">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4244f-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="4244f-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="4244f-132">Windows E5/A5</span></span>
> * <span data-ttu-id="4244f-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="4244f-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="4244f-134">Microsoft 365 E5/A5 Security</span><span class="sxs-lookup"><span data-stu-id="4244f-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="4244f-135">Ausführliche Informationen zur Lizenzierung finden Sie auf der [Website der Produktbedingungen](https://www.microsoft.com/licensing/terms/) und in Zusammenarbeit mit Ihrem Kontoteam, um mehr über die Geschäftsbedingungen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="4244f-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="4244f-136">Weitere Informationen zum Array von Features in Windows 10 Editionen finden Sie unter [Vergleichen Windows 10 Editionen.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="4244f-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="4244f-137">Eine detaillierte Vergleichstabelle Windows 10 Vergleichs der kommerziellen Edition finden Sie in der [PDF-Vergleichstabelle.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="4244f-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="4244f-138">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="4244f-138">Browser requirements</span></span>

<span data-ttu-id="4244f-139">Der Zugriff auf Defender für Endpunkt erfolgt über einen Browser, der die folgenden Browser unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4244f-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="4244f-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4244f-140">Microsoft Edge</span></span>
- <span data-ttu-id="4244f-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="4244f-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-142">Während andere Browser möglicherweise funktionieren, werden die erwähnten Browser unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4244f-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="4244f-143">Hardware- und Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="4244f-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="4244f-144">Unterstützte Windows Versionen</span><span class="sxs-lookup"><span data-stu-id="4244f-144">Supported Windows versions</span></span>

- <span data-ttu-id="4244f-145">Windows 7 SP1-Enterprise ([Erfordert ESU für Support.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="4244f-145">Windows 7 SP1 Enterprise ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="4244f-146">Windows 7 SP1-Pro ([Erfordert ESU für Support.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="4244f-146">Windows 7 SP1 Pro ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="4244f-147">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4244f-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="4244f-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="4244f-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="4244f-149">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4244f-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="4244f-150">Windows 10 Enterprise LTSC 2016 (oder höher)</span><span class="sxs-lookup"><span data-stu-id="4244f-150">Windows 10 Enterprise LTSC 2016 (or later)</span></span>](/windows/whats-new/ltsc/)
- <span data-ttu-id="4244f-151">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="4244f-151">Windows 10 Education</span></span>
- <span data-ttu-id="4244f-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="4244f-152">Windows 10 Pro</span></span>
- <span data-ttu-id="4244f-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="4244f-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="4244f-154">Windows-Server</span><span class="sxs-lookup"><span data-stu-id="4244f-154">Windows server</span></span>
  - <span data-ttu-id="4244f-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="4244f-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="4244f-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4244f-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="4244f-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4244f-157">Windows Server 2016</span></span>
  - <span data-ttu-id="4244f-158">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="4244f-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="4244f-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4244f-159">Windows Server 2019</span></span>
- <span data-ttu-id="4244f-160">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="4244f-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="4244f-161">Auf Geräten in Ihrem Netzwerk muss eine dieser Editionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4244f-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="4244f-162">Die Hardwareanforderungen für Defender für Endpunkt auf Geräten sind für die unterstützten Editionen identisch.</span><span class="sxs-lookup"><span data-stu-id="4244f-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-163">Computer mit mobilen Versionen von Windows (z. B. Windows CE und Windows 10 Mobile) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4244f-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="4244f-164">Bei virtuellen Computern, die Windows 10 Enterprise 2016 LTSB ausgeführt werden, können Leistungsprobleme auftreten, wenn sie auf Nicht-Microsoft-Virtualisierungsplattformen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4244f-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="4244f-165">Für virtuelle Umgebungen empfehlen wir die Verwendung Windows 10 Enterprise LTSC 2019 oder höher.</span><span class="sxs-lookup"><span data-stu-id="4244f-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="4244f-166">Andere unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="4244f-166">Other supported operating systems</span></span>

- [<span data-ttu-id="4244f-167">Android</span><span class="sxs-lookup"><span data-stu-id="4244f-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="4244f-168">iOS</span><span class="sxs-lookup"><span data-stu-id="4244f-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="4244f-169">Linux</span><span class="sxs-lookup"><span data-stu-id="4244f-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="4244f-170">macOS</span><span class="sxs-lookup"><span data-stu-id="4244f-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="4244f-171">Sie müssen bestätigen, dass die Linux-Distributionen und -Versionen von Android, iOS und macOS mit Defender für Endpunkt kompatibel sind, damit die Integration funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4244f-171">You'll need to confirm the Linux distributions and versions of Android, iOS, and macOS are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="4244f-172">Netzwerk- und Datenspeicherungs- und Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4244f-172">Network and data storage and configuration requirements</span></span>

<span data-ttu-id="4244f-173">Wenn Sie den Onboarding-Assistenten zum ersten Mal ausführen, müssen Sie auswählen, wo Ihre Microsoft Defender für Endpunkt-bezogenen Informationen gespeichert werden: in der Europäischen Union, im Vereinigten Königreich oder im Rechenzentrum der Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="4244f-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="4244f-174">Sie können ihren Datenspeicherort nach der erstmaligen Einrichtung nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="4244f-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="4244f-175">Weitere Informationen dazu, wo und wie Microsoft Ihre Daten speichert, finden Sie im [Microsoft Defender für Endpunkt-Datenspeicherungs- und -datenschutz.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="4244f-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="4244f-176">Diagnosedateneinstellungen</span><span class="sxs-lookup"><span data-stu-id="4244f-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-177">Microsoft Defender für Endpunkt erfordert keine bestimmte Diagnosestufe, solange es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4244f-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="4244f-178">Stellen Sie sicher, dass der Diagnosedatendienst auf allen Geräten in Ihrer Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4244f-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="4244f-179">Standardmäßig ist dieser Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4244f-179">By default, this service is enabled.</span></span> <span data-ttu-id="4244f-180">Es empfiehlt sich, zu überprüfen, ob Sie Sensordaten von diesen abrufen.</span><span class="sxs-lookup"><span data-stu-id="4244f-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="4244f-181">**Verwenden Sie die Befehlszeile, um den Starttyp Windows 10 Diagnosedatendiensts zu überprüfen:**</span><span class="sxs-lookup"><span data-stu-id="4244f-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="4244f-182">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät:</span><span class="sxs-lookup"><span data-stu-id="4244f-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="4244f-183">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="4244f-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="4244f-184">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="4244f-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4244f-185">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE:**</span><span class="sxs-lookup"><span data-stu-id="4244f-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="4244f-186">Wenn der Dienst aktiviert ist, sollte das Ergebnis wie im folgenden Screenshot aussehen:</span><span class="sxs-lookup"><span data-stu-id="4244f-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Ergebnis des Sc-Abfragebefehls für diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="4244f-188">Sie müssen festlegen, dass der Dienst automatisch gestartet wird, wenn der **START_TYPE** nicht auf **AUTO_START** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4244f-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="4244f-189">**Verwenden Sie die Befehlszeile, um den Windows 10 Diagnosedatendienst so festzulegen, dass er automatisch gestartet wird:**</span><span class="sxs-lookup"><span data-stu-id="4244f-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="4244f-190">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Endpunkt:</span><span class="sxs-lookup"><span data-stu-id="4244f-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="4244f-191">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="4244f-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="4244f-192">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="4244f-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="4244f-193">Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE:**</span><span class="sxs-lookup"><span data-stu-id="4244f-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="4244f-194">Eine Erfolgsmeldung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4244f-194">A success message is displayed.</span></span> <span data-ttu-id="4244f-195">Überprüfen Sie die Änderung, indem Sie den folgenden Befehl eingeben, und drücken Sie die **EINGABETASTE:**</span><span class="sxs-lookup"><span data-stu-id="4244f-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="4244f-196">Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="4244f-196">Internet connectivity</span></span>

<span data-ttu-id="4244f-197">Internetkonnektivität auf Geräten ist entweder direkt oder über Proxy erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4244f-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="4244f-198">Der Defender für Endpunkt-Sensor kann eine tägliche durchschnittliche Bandbreite von 5 MB verwenden, um mit dem Defender für Endpunkt-Clouddienst zu kommunizieren und Cyberdaten zu melden.</span><span class="sxs-lookup"><span data-stu-id="4244f-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="4244f-199">Einmalige Aktivitäten wie Dateiuploads und Untersuchungspaketsammlungen sind in dieser durchschnittlichen Täglichen Bandbreite nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="4244f-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="4244f-200">Weitere Informationen zu zusätzlichen Proxykonfigurationseinstellungen finden Sie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="4244f-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="4244f-201">Bevor Sie Geräte integrieren, muss der Diagnosedatendienst aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="4244f-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="4244f-202">Der Dienst ist in Windows 10 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4244f-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="4244f-203">Microsoft Defender Antivirus Konfigurationsanforderung</span><span class="sxs-lookup"><span data-stu-id="4244f-203">Microsoft Defender Antivirus configuration requirement</span></span>

<span data-ttu-id="4244f-204">Der Defender für Endpunkt-Agent hängt von der Fähigkeit von Microsoft Defender Antivirus ab, Dateien zu scannen und Informationen darüber bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4244f-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="4244f-205">Konfigurieren Von Security Intelligence-Updates auf den Defender für Endpunkt-Geräten, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischadsoftware ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4244f-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="4244f-206">Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="4244f-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="4244f-207">Wenn Microsoft Defender Antivirus nicht die aktive Antischadsoftware in Ihrer Organisation ist und Sie den Defender für Endpunkt-Dienst verwenden, wechselt Microsoft Defender Antivirus in den passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="4244f-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="4244f-208">Wenn Ihre Organisation Microsoft Defender Antivirus über Gruppenrichtlinien oder andere Methoden deaktiviert hat, müssen die integrierten Geräte von dieser Gruppenrichtlinie ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4244f-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="4244f-209">Wenn Sie Server integrieren und Microsoft Defender Antivirus nicht die aktive Antischadsoftware auf Ihren Servern ist, müssen Microsoft Defender Antivirus entweder für den passiven Modus konfiguriert oder deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="4244f-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="4244f-210">Die Konfiguration hängt von der Serverversion ab.</span><span class="sxs-lookup"><span data-stu-id="4244f-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="4244f-211">Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](/security/defender-endpoint/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="4244f-211">For more information, see [Microsoft Defender Antivirus compatibility](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="4244f-212">Ihre reguläre Gruppenrichtlinie gilt nicht für Manipulationsschutz, und Änderungen an Microsoft Defender Antivirus Einstellungen werden ignoriert, wenn der Manipulationsschutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4244f-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="4244f-213">Microsoft Defender Antivirus ELAM-Treiber (Early Launch Antimalware) ist aktiviert</span><span class="sxs-lookup"><span data-stu-id="4244f-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>

<span data-ttu-id="4244f-214">Wenn Sie Microsoft Defender Antivirus als primäres Antischadsoftwareprodukt auf Ihren Geräten ausführen, wird der Defender für Endpunkt-Agent erfolgreich integriert.</span><span class="sxs-lookup"><span data-stu-id="4244f-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="4244f-215">Wenn Sie einen Antischadsoftwareclient eines Drittanbieters ausführen und Lösungen für die mobile Geräteverwaltung oder Microsoft Endpoint Manager (current branch) verwenden, müssen Sie sicherstellen, dass der Microsoft Defender Antivirus ELAM-Treiber aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4244f-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="4244f-216">Weitere Informationen finden Sie unter [Sicherstellen, dass Microsoft Defender Antivirus nicht durch eine Richtlinie deaktiviert ist.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="4244f-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="4244f-217">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4244f-217">Related topics</span></span>

- [<span data-ttu-id="4244f-218">Einrichten der Bereitstellung von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4244f-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="4244f-219">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="4244f-219">Onboard devices</span></span>](onboard-configure.md)
