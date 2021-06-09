---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten bereitzustellen, sodass sie in den Dienst integriert sind.
keywords: Onboarding von Geräten mit sccm, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte
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
ms.topic: article
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d827fb89a082286b1b7b77ea0a14e588ce171161
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842194"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="71eac-104">Onboarding von Windows 10-Geräten mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71eac-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71eac-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="71eac-105">**Applies to:**</span></span>

- [<span data-ttu-id="71eac-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71eac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71eac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71eac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="71eac-108">Microsoft Endpoint Configuration Manager aktuelle Verzweigung</span><span class="sxs-lookup"><span data-stu-id="71eac-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="71eac-109">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71eac-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="71eac-110">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="71eac-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="71eac-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="71eac-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="71eac-112">Unterstützte Clientbetriebssysteme</span><span class="sxs-lookup"><span data-stu-id="71eac-112">Supported client operating systems</span></span>

<span data-ttu-id="71eac-113">Basierend auf der Version von Configuration Manager, die Sie ausführen, können die folgenden Clientbetriebssysteme integriert werden:</span><span class="sxs-lookup"><span data-stu-id="71eac-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="71eac-114">Configuration Manager, Version 1910 und früher</span><span class="sxs-lookup"><span data-stu-id="71eac-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="71eac-115">Clients, auf denen Windows 10 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="71eac-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="71eac-116">Configuration Manager, Version 2002 und höher</span><span class="sxs-lookup"><span data-stu-id="71eac-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="71eac-117">Ab Configuration Manager, Version 2002, können Sie die folgenden Betriebssysteme integrieren:</span><span class="sxs-lookup"><span data-stu-id="71eac-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="71eac-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="71eac-118">Windows 8.1</span></span>
- <span data-ttu-id="71eac-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="71eac-119">Windows 10</span></span>
- <span data-ttu-id="71eac-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="71eac-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="71eac-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="71eac-121">Windows Server 2016</span></span>
- <span data-ttu-id="71eac-122">Windows Server 2016, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="71eac-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="71eac-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="71eac-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="71eac-124">Weitere Informationen zum Onboarding von Windows Server 2012 R2, Windows Server 2016 und Windows Server 2019 finden Sie unter [Onboarding Windows Server.](configure-server-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="71eac-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="71eac-125">Onboarding von Geräten mit System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71eac-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="71eac-126">[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="71eac-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="71eac-127">Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender für Endpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="71eac-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="71eac-128">Öffnen Sie das Configuration Manager-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="71eac-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="71eac-129">Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:</span><span class="sxs-lookup"><span data-stu-id="71eac-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="71eac-130">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="71eac-131">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="71eac-132">Wählen Sie im Feld **"Bereitstellungsmethode"** **System Center Configuration Manager 2012/2012 R2/1511/1602** aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="71eac-133">Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="71eac-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="71eac-134">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71eac-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="71eac-135">Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="71eac-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="71eac-136">Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="71eac-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="71eac-137">a.</span><span class="sxs-lookup"><span data-stu-id="71eac-137">a.</span></span> <span data-ttu-id="71eac-138">Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="71eac-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="71eac-139">Defender für Endpunkt unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht.</span><span class="sxs-lookup"><span data-stu-id="71eac-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="71eac-140">Stellen Sie sicher, dass Benutzer die Windows-Willkommensseite nach der Ausführung Windows Installation oder des Upgrades abschließen.</span><span class="sxs-lookup"><span data-stu-id="71eac-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="71eac-141">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integriert ist.</span><span class="sxs-lookup"><span data-stu-id="71eac-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="71eac-142">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="71eac-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="71eac-143">Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät integriert wurde.</span><span class="sxs-lookup"><span data-stu-id="71eac-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="71eac-144">Eine Anwendung ist ein anderer Objekttyp als ein Paket und ein Programm.</span><span class="sxs-lookup"><span data-stu-id="71eac-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="71eac-145">Wenn ein Gerät noch nicht integriert ist (aufgrund eines ausstehenden OoBE-Abschlusses oder aus einem anderen Grund), versucht Configuration Manager erneut, das Gerät zu integrieren, bis die Regel die Statusänderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="71eac-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="71eac-146">Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.</span><span class="sxs-lookup"><span data-stu-id="71eac-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="71eac-147">Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="71eac-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="71eac-148">Weitere Informationen finden Sie unter [Konfigurieren von Erkennungsmethoden in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="71eac-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="71eac-149">Konfigurieren von Beispielsammlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="71eac-149">Configure sample collection settings</span></span>

<span data-ttu-id="71eac-150">Für jedes Gerät können Sie einen Konfigurationswert festlegen, um anzugeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft Defender Security Center zum Übermitteln einer Datei für eine umfassende Analyse gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="71eac-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="71eac-151">Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="71eac-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="71eac-152">Sie können eine Complianceregel für ein Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.</span><span class="sxs-lookup"><span data-stu-id="71eac-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="71eac-153">Diese Regel sollte *ein* Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf Zielgeräten festlegt, um sicherzustellen, dass diese beschwerden.</span><span class="sxs-lookup"><span data-stu-id="71eac-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="71eac-154">Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:</span><span class="sxs-lookup"><span data-stu-id="71eac-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="71eac-155">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="71eac-155">Where:</span></span><br>
<span data-ttu-id="71eac-156">Der Schlüsseltyp ist D-WORD.</span><span class="sxs-lookup"><span data-stu-id="71eac-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="71eac-157">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="71eac-157">Possible values are:</span></span>
- <span data-ttu-id="71eac-158">0 – lässt keine Beispielfreigabe von diesem Gerät zu</span><span class="sxs-lookup"><span data-stu-id="71eac-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="71eac-159">1 – ermöglicht die Freigabe aller Dateitypen von diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="71eac-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="71eac-160">Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.</span><span class="sxs-lookup"><span data-stu-id="71eac-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="71eac-161">Weitere Informationen zu System Center Configuration Manager Compliance finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="71eac-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="71eac-162">Andere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="71eac-162">Other recommended configuration settings</span></span>
<span data-ttu-id="71eac-163">Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Bedrohungsschutzfunktionen zu nutzen, indem Sie diese mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="71eac-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="71eac-164">Gerätesammlungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="71eac-164">Device collection configuration</span></span>
<span data-ttu-id="71eac-165">Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung erweitern, um Server oder Untergeordnete Clients einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="71eac-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="71eac-166">Schutzkonfiguration der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="71eac-166">Next generation protection configuration</span></span>
<span data-ttu-id="71eac-167">Die folgenden Konfigurationseinstellungen werden empfohlen:</span><span class="sxs-lookup"><span data-stu-id="71eac-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="71eac-168">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="71eac-168">**Scan**</span></span> <br>
- <span data-ttu-id="71eac-169">Scannen von Wechselmedien wie USB-Laufwerken: Ja</span><span class="sxs-lookup"><span data-stu-id="71eac-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="71eac-170">**Echtzeitschutz**</span><span class="sxs-lookup"><span data-stu-id="71eac-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="71eac-171">Aktivieren der Verhaltensüberwachung: Ja</span><span class="sxs-lookup"><span data-stu-id="71eac-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="71eac-172">Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Download und vor der Installation: Ja</span><span class="sxs-lookup"><span data-stu-id="71eac-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="71eac-173">**Cloud Protection Service**</span><span class="sxs-lookup"><span data-stu-id="71eac-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="71eac-174">Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="71eac-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="71eac-175">**Verringerung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="71eac-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="71eac-176">Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="71eac-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="71eac-177">Der beste Ansatz besteht darin, alles zu überwachen, zu identifizieren, welche sicher aktiviert werden können, und dann die Einstellungen auf Endpunkten zu aktivieren, die keine falsch positiven Erkennungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="71eac-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="71eac-178">**Netzwerkschutz**</span><span class="sxs-lookup"><span data-stu-id="71eac-178">**Network protection**</span></span> <br>
<span data-ttu-id="71eac-179">Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockierungsmodus sicher, dass Sie das Antischadsoftware-Plattformupdate installiert haben, das über die [Supportseite](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="71eac-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="71eac-180">**Kontrollierter Ordnerzugriff**</span><span class="sxs-lookup"><span data-stu-id="71eac-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="71eac-181">Aktivieren Sie das Feature mindestens 30 Tage lang im Überwachungsmodus.</span><span class="sxs-lookup"><span data-stu-id="71eac-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="71eac-182">Überprüfen Sie nach ablaufen diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.</span><span class="sxs-lookup"><span data-stu-id="71eac-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="71eac-183">Weitere Informationen finden Sie unter [Auswerten des kontrollierten Ordnerzugriffs.](evaluate-controlled-folder-access.md)</span><span class="sxs-lookup"><span data-stu-id="71eac-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="71eac-184">Offboarding von Geräten mit Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71eac-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="71eac-185">Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="71eac-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="71eac-186">Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="71eac-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="71eac-187">Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="71eac-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="71eac-188">Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.</span><span class="sxs-lookup"><span data-stu-id="71eac-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="71eac-189">Offboarding von Geräten mit Microsoft Endpoint Manager aktuellen Verzweigung</span><span class="sxs-lookup"><span data-stu-id="71eac-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="71eac-190">Wenn Sie Microsoft Endpoint Manager aktuelle Verzweigung verwenden, lesen [Sie Erstellen einer Offboarding-Konfigurationsdatei .](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="71eac-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="71eac-191">Offboarding von Geräten mit System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="71eac-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="71eac-192">Rufen Sie das Offboarding-Paket aus [Microsoft Defender Security Center](https://securitycenter.windows.com/)ab:</span><span class="sxs-lookup"><span data-stu-id="71eac-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="71eac-193">Wählen Sie im Navigationsbereich **Einstellungen**  >   **Offboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="71eac-194">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="71eac-195">Wählen Sie im Feld **"Bereitstellungsmethode"** **System Center Configuration Manager 2012/2012 R2/1511/1602** aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="71eac-196">Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="71eac-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="71eac-197">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71eac-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="71eac-198">Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="71eac-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="71eac-199">Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="71eac-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="71eac-200">a.</span><span class="sxs-lookup"><span data-stu-id="71eac-200">a.</span></span> <span data-ttu-id="71eac-201">Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="71eac-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71eac-202">Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="71eac-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="71eac-203">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="71eac-203">Monitor device configuration</span></span>

<span data-ttu-id="71eac-204">Wenn Sie Microsoft Endpoint Manager aktuelle Verzweigung verwenden, verwenden Sie das integrierte Defender für Endpunkt-Dashboard in der Configuration Manager-Konsole.</span><span class="sxs-lookup"><span data-stu-id="71eac-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="71eac-205">Weitere Informationen finden Sie unter [Defender für Endpunkt – Überwachen.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="71eac-205">For more information, see [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="71eac-206">Wenn Sie System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="71eac-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="71eac-207">Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).</span><span class="sxs-lookup"><span data-stu-id="71eac-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="71eac-208">Überprüfen, ob die Geräte mit dem Defender für Endpunkt-Dienst kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Integrationsprozess abschließen und weiterhin Daten an den Dienst melden kann).</span><span class="sxs-lookup"><span data-stu-id="71eac-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="71eac-209">Sicherstellen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="71eac-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="71eac-210">Klicken Sie in der Configuration Manager-Konsole unten im Navigationsbereich auf **"Überwachung".**</span><span class="sxs-lookup"><span data-stu-id="71eac-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="71eac-211">Wählen Sie **"Übersicht"** und dann **"Bereitstellungen" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eac-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="71eac-212">Wählen Sie die Bereitstellung mit dem Paketnamen aus.</span><span class="sxs-lookup"><span data-stu-id="71eac-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="71eac-213">Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus.**</span><span class="sxs-lookup"><span data-stu-id="71eac-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="71eac-214">Wenn fehlerbehinddete Bereitstellungen (Geräte mit **Fehler,** **Anforderungen nicht erfüllt** oder **Fehlerstatus)** auftreten, müssen Sie die Geräte möglicherweise beheben.</span><span class="sxs-lookup"><span data-stu-id="71eac-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="71eac-215">Weitere Informationen finden Sie unter ["Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten".](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="71eac-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="71eac-217">Überprüfen Sie, ob die Geräte mit dem Microsoft Defender für Endpunktdienst kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="71eac-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="71eac-218">Sie können eine Kompatibilitätsregel für Konfigurationselemente in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="71eac-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="71eac-219">Bei dieser Regel sollte es sich um ein *nicht korrigierende* Complianceregel-Konfigurationselement handeln, das den Wert eines Registrierungsschlüssels auf Zielgeräten überwacht.</span><span class="sxs-lookup"><span data-stu-id="71eac-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="71eac-220">Überwachen Sie den folgenden Registrierungsschlüsseleintrag:</span><span class="sxs-lookup"><span data-stu-id="71eac-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="71eac-221">Weitere Informationen finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="71eac-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="71eac-222">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="71eac-222">Related topics</span></span>
- [<span data-ttu-id="71eac-223">Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="71eac-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="71eac-224">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="71eac-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="71eac-225">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="71eac-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="71eac-226">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="71eac-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="71eac-227">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät</span><span class="sxs-lookup"><span data-stu-id="71eac-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="71eac-228">Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten</span><span class="sxs-lookup"><span data-stu-id="71eac-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
