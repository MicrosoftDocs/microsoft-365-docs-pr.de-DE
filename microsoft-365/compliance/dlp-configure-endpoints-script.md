---
title: Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts
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
description: Verwenden Sie ein lokales Skript, um das Konfigurationspaket auf Geräten bereitzustellen, damit diese in den Dienst eingehen.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769471"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="b16f6-103">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="b16f6-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="b16f6-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b16f6-104">**Applies to:**</span></span>

- [<span data-ttu-id="b16f6-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="b16f6-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="b16f6-106">Sie können auch einzelne Geräte manuell an die Microsoft 365-Endpunkt Verhinderung von Datenverlusten an Bord integrieren.</span><span class="sxs-lookup"><span data-stu-id="b16f6-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="b16f6-107">Möglicherweise möchten Sie dies zunächst beim Testen des Diensts tun, bevor Sie ein Commit für das Onboarding aller Geräte in Ihrem Netzwerk ausführen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b16f6-108">Dieses Skript wurde für die Verwendung auf bis zu 10 Geräten optimiert.</span><span class="sxs-lookup"><span data-stu-id="b16f6-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="b16f6-109">Verwenden Sie [andere Bereitstellungsoptionen](dlp-configure-endpoints.md), um eine Skalierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="b16f6-110">Beispielsweise können Sie ein Onboarding-Skript für mehr als 10 Geräte in der Produktion mit dem Skript bereitstellen, das in integrierten [Windows 10-Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b16f6-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="b16f6-111">Integrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="b16f6-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="b16f6-112">Öffnen Sie die ZIP-Datei des GP-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="b16f6-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="b16f6-113">Sie können das Paket auch über das [Microsoft Compliance Center](https://compliance.microsoft.com) abrufen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b16f6-114">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="b16f6-115">Wählen Sie im Feld **Bereitstellungsmethode** die Option **Lokales Skript** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="b16f6-116">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="b16f6-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="b16f6-117">Extrahieren Sie den Inhalt des Konfigurationspakets an einen Speicherort auf dem Gerät, das Sie onboardieren möchten (beispielsweise den Desktop).</span><span class="sxs-lookup"><span data-stu-id="b16f6-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="b16f6-118">Sie sollten über eine Datei mit dem Namen " *DeviceOnboardingScript. cmd* " verfügen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="b16f6-119">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="b16f6-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b16f6-120">Wechseln Sie zu **Start** , und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="b16f6-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="b16f6-121">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Fenster Start Menü, das auf als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b16f6-123">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="b16f6-123">Type the location of the script file.</span></span> <span data-ttu-id="b16f6-124">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%UserProfile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="b16f6-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="b16f6-125">Drücken Sie die **Eingabe** Taste, oder klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="b16f6-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="b16f6-126">Informationen dazu, wie Sie manuell überprüfen können, ob das Gerät kompatibel ist und Sensordaten ordnungsgemäß meldet, finden Sie unter [Troubleshoot Microsoft Defender Advanced Threat Protection Onboarding Issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="b16f6-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="b16f6-127">Extern-Geräte mit einem lokalen Skript</span><span class="sxs-lookup"><span data-stu-id="b16f6-127">Offboard devices using a local script</span></span>
<span data-ttu-id="b16f6-128">Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab.</span><span class="sxs-lookup"><span data-stu-id="b16f6-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="b16f6-129">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="b16f6-130">Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="b16f6-131">Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.</span><span class="sxs-lookup"><span data-stu-id="b16f6-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="b16f6-132">Abrufen des offboarding-Pakets im [Microsoft Compliance Center](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b16f6-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="b16f6-133">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät offboarding** .</span><span class="sxs-lookup"><span data-stu-id="b16f6-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="b16f6-134">Wählen Sie im Feld **Bereitstellungsmethode** die Option **Lokales Skript** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="b16f6-135">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="b16f6-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="b16f6-136">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Geräte zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b16f6-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="b16f6-137">Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="b16f6-138">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="b16f6-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="b16f6-139">Wechseln Sie zu **Start** , und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="b16f6-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="b16f6-140">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Fenster Start Menü, das auf als Administrator ausführen zeigt](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="b16f6-142">Geben Sie den Speicherort der Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="b16f6-142">Type the location of the script file.</span></span> <span data-ttu-id="b16f6-143">Wenn Sie die Datei auf den Desktop kopiert haben, geben Sie Folgendes ein: *%UserProfile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*</span><span class="sxs-lookup"><span data-stu-id="b16f6-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="b16f6-144">Drücken Sie die **Eingabe** Taste, oder klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="b16f6-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b16f6-145">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet.</span><span class="sxs-lookup"><span data-stu-id="b16f6-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="b16f6-146">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="b16f6-146">Monitor device configuration</span></span>
<span data-ttu-id="b16f6-147">Sie können die unterschiedlichen Überprüfungsschritte im Thema [Problembehandlung bei Problemen mit dem Onboarding] befolgen ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) um zu überprüfen, ob das Skript erfolgreich abgeschlossen wurde und der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b16f6-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="b16f6-148">Die Überwachung kann auch direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b16f6-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="b16f6-149">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="b16f6-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="b16f6-150">Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b16f6-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="b16f6-151">Wählen Sie **Einstellungen**  >  **Geräte-Onboarding**  >  - **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="b16f6-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="b16f6-152">Stellen Sie sicher, dass die Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b16f6-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b16f6-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b16f6-153">Related topics</span></span>
- [<span data-ttu-id="b16f6-154">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="b16f6-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b16f6-155">Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b16f6-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b16f6-156">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="b16f6-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b16f6-157">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="b16f6-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="b16f6-158">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät</span><span class="sxs-lookup"><span data-stu-id="b16f6-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="b16f6-159">Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b16f6-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
