---
title: Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst onboardiert werden.
keywords: Konfigurieren von Geräten mithilfe eines lokalen Skripts, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte
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
ms.technology: mde
ms.openlocfilehash: 056268ed093d371d39a6136dd0b272c12ab6f9d7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933913"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="34797-104">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="34797-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="34797-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34797-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="34797-106">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="34797-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34797-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="34797-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="34797-108">Sie können auch einzelne Geräte manuell in Defender for Endpoint integrieren.</span><span class="sxs-lookup"><span data-stu-id="34797-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="34797-109">Möglicherweise möchten Sie dies zuerst tun, wenn Sie den Dienst testen, bevor Sie sich zum Onboarding aller Geräte in Ihrem Netzwerk verpflichten.</span><span class="sxs-lookup"><span data-stu-id="34797-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34797-110">Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.</span><span class="sxs-lookup"><span data-stu-id="34797-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="34797-111">Verwenden Sie andere Bereitstellungsoptionen, um die Bereitstellung [in der Skalierung zu implementieren.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="34797-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="34797-112">Beispielsweise können Sie ein Onboardingskript auf mehr als 10 Geräten in der Produktion bereitstellen, mit dem Skript, das unter [Onboard Windows 10 devices using Group Policy verfügbar ist.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="34797-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="34797-113">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="34797-113">Onboard devices</span></span> 

<span data-ttu-id="34797-114">[![Abbildung der PDF mit den verschiedenen Bereitstellungspfaden](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="34797-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="34797-115">Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender for Endpoint zu sehen.</span><span class="sxs-lookup"><span data-stu-id="34797-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="34797-116">Öffnen Sie die ZIP-Datei des *GP-Konfigurationspakets*(WindowsDefenderATPOnboardingPackage.zip), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="34797-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="34797-117">Sie können das Paket auch über [das Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="34797-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="34797-118">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="34797-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="34797-119">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="34797-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="34797-120">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**</span><span class="sxs-lookup"><span data-stu-id="34797-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="34797-121">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="34797-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="34797-122">Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie onboarden möchten (z. B. desktop).</span><span class="sxs-lookup"><span data-stu-id="34797-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="34797-123">Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="34797-123">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="34797-124">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="34797-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="34797-125">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="34797-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="34797-126">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="34797-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](images/run-as-admin.png)

4.  <span data-ttu-id="34797-128">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="34797-128">Type the location of the script file.</span></span> <span data-ttu-id="34797-129">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="34797-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="34797-130">Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34797-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="34797-131">Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter Problembehandlung bei [Microsoft Defender for Endpoint-Onboardingproblemen.](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="34797-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="34797-132">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass ein Gerät ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="34797-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="34797-133">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu](run-detection-test.md)integrierten Microsoft Defender for Endpoint-Endpunkt .</span><span class="sxs-lookup"><span data-stu-id="34797-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="34797-134">Konfigurieren von Beispielsammlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="34797-134">Configure sample collection settings</span></span>
<span data-ttu-id="34797-135">Für jedes Gerät können Sie einen Konfigurationswert festlegen, um zu bestimmen, ob Beispiele vom Gerät gesammelt werden können, wenn über das Microsoft Defender Security Center eine Anforderung zum Übermitteln einer Datei zur tiefen Analyse gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="34797-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="34797-136">Sie können die Beispielfreigabeeinstellung auf dem Gerät manuell konfigurieren, indem Sie *regedit* verwenden oder eine *REG-Datei erstellen und* ausführen.</span><span class="sxs-lookup"><span data-stu-id="34797-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="34797-137">Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:</span><span class="sxs-lookup"><span data-stu-id="34797-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="34797-138">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="34797-138">Where:</span></span><br>
<span data-ttu-id="34797-139">Name type is a D-WORD.</span><span class="sxs-lookup"><span data-stu-id="34797-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="34797-140">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="34797-140">Possible values are:</span></span>
- <span data-ttu-id="34797-141">0 – lässt keine Beispielfreigabe von diesem Gerät zu</span><span class="sxs-lookup"><span data-stu-id="34797-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="34797-142">1 – Ermöglicht die Freigabe aller Dateitypen von diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="34797-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="34797-143">Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.</span><span class="sxs-lookup"><span data-stu-id="34797-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="34797-144">Offboardgeräte mit einem lokalen Skript</span><span class="sxs-lookup"><span data-stu-id="34797-144">Offboard devices using a local script</span></span>
<span data-ttu-id="34797-145">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="34797-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="34797-146">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="34797-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="34797-147">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="34797-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="34797-148">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="34797-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="34797-149">Das offboarding-Paket aus [dem Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="34797-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="34797-150">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="34797-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="34797-151">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="34797-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="34797-152">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**</span><span class="sxs-lookup"><span data-stu-id="34797-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="34797-153">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="34797-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="34797-154">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Geräte zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="34797-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="34797-155">Sie sollten über eine Datei namens *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="34797-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="34797-156">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="34797-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="34797-157">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="34797-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="34797-158">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="34797-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](images/run-as-admin.png)

4.  <span data-ttu-id="34797-160">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="34797-160">Type the location of the script file.</span></span> <span data-ttu-id="34797-161">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="34797-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="34797-162">Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34797-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34797-163">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="34797-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="34797-164">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="34797-164">Monitor device configuration</span></span>
<span data-ttu-id="34797-165">Sie können die verschiedenen Überprüfungsschritte in [der Problembehandlung](troubleshoot-onboarding.md) bei onboarding ausführen, um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34797-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="34797-166">Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34797-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="34797-167">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="34797-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="34797-168">Wechseln Sie zu Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="34797-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="34797-169">Klicken Sie **auf Geräteliste**.</span><span class="sxs-lookup"><span data-stu-id="34797-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="34797-170">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="34797-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="34797-171">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="34797-171">Related topics</span></span>
- [<span data-ttu-id="34797-172">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="34797-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="34797-173">Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="34797-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="34797-174">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="34797-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="34797-175">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="34797-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="34797-176">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="34797-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="34797-177">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34797-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
