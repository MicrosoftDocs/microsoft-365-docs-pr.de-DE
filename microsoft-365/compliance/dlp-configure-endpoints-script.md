---
title: Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst onboardiert werden.
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893306"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="78d33-103">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="78d33-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="78d33-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="78d33-104">**Applies to:**</span></span>

- [<span data-ttu-id="78d33-105">Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="78d33-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="78d33-106">Sie können auch einzelne Geräte manuell integrieren, um Microsoft 365 Verhinderung von Datenverlusten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="78d33-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="78d33-107">Möglicherweise möchten Sie dies zuerst tun, wenn Sie den Dienst testen, bevor Sie sich zum Onboarding aller Geräte in Ihrem Netzwerk verpflichten.</span><span class="sxs-lookup"><span data-stu-id="78d33-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78d33-108">Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.</span><span class="sxs-lookup"><span data-stu-id="78d33-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="78d33-109">Verwenden Sie andere Bereitstellungsoptionen, um die Bereitstellung [in der Skalierung zu implementieren.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="78d33-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="78d33-110">Sie können z. B. ein Onboardingskript auf mehr als 10 Geräten in der Produktion mit dem Skript bereitstellen, das unter Onboard Windows 10 geräte mithilfe der [Gruppenrichtlinie verfügbar ist.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="78d33-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="78d33-111">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="78d33-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="78d33-112">Öffnen Sie die Gp.zip datei (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="78d33-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="78d33-113">Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="78d33-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="78d33-114">Wählen Sie im Navigationsbereich die **option Einstellungen**  >  **Device onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="78d33-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="78d33-115">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**</span><span class="sxs-lookup"><span data-stu-id="78d33-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="78d33-116">Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="78d33-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="78d33-117">Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie onboarden möchten (z. B. desktop).</span><span class="sxs-lookup"><span data-stu-id="78d33-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="78d33-118">Sie sollten über eine Datei mit dem Namen *DeviceOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="78d33-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="78d33-119">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="78d33-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="78d33-120">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="78d33-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="78d33-121">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="78d33-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="78d33-123">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="78d33-123">Type the location of the script file.</span></span> <span data-ttu-id="78d33-124">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="78d33-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="78d33-125">Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78d33-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="78d33-126">Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter [Problembehandlung Microsoft Defender Advanced Threat Protection Onboarding- Probleme](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="78d33-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="78d33-127">Offboardgeräte mit einem lokalen Skript</span><span class="sxs-lookup"><span data-stu-id="78d33-127">Offboard devices using a local script</span></span>
<span data-ttu-id="78d33-128">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="78d33-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="78d33-129">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="78d33-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="78d33-130">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="78d33-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="78d33-131">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="78d33-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="78d33-132">Das Offboardingpaket aus dem [Microsoft Compliance Center erhalten](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="78d33-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="78d33-133">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte-Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="78d33-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="78d33-134">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Lokales Skript aus.**</span><span class="sxs-lookup"><span data-stu-id="78d33-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="78d33-135">Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="78d33-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="78d33-136">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Geräte zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="78d33-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="78d33-137">Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="78d33-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="78d33-138">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="78d33-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="78d33-139">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="78d33-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="78d33-140">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="78d33-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="78d33-142">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="78d33-142">Type the location of the script file.</span></span> <span data-ttu-id="78d33-143">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie ein: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="78d33-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="78d33-144">Drücken Sie die **EINGABETASTE,** oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78d33-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78d33-145">Offboarding bewirkt, dass das Gerät sensordaten nicht mehr an das Portal sendet.</span><span class="sxs-lookup"><span data-stu-id="78d33-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="78d33-146">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="78d33-146">Monitor device configuration</span></span>
<span data-ttu-id="78d33-147">Sie können die verschiedenen Überprüfungsschritte in der [Problembehandlung von Onboardingproblemen](( ausführen, um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="78d33-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="78d33-148">Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78d33-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="78d33-149">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="78d33-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="78d33-150">Wechseln Sie [zu Microsoft 365 Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="78d33-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="78d33-151">Wählen **Einstellungen**  >  **Geräte onboarding** Geräte  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="78d33-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="78d33-152">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78d33-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="78d33-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="78d33-153">Related topics</span></span>
- [<span data-ttu-id="78d33-154">Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="78d33-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="78d33-155">Onboarding Windows 10 Geräte mithilfe Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="78d33-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="78d33-156">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="78d33-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="78d33-157">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="78d33-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="78d33-158">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="78d33-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="78d33-159">Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen</span><span class="sxs-lookup"><span data-stu-id="78d33-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)