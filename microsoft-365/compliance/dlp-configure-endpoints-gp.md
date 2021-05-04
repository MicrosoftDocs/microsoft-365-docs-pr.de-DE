---
title: Onboarding von Windows 10-Geräten über Gruppenrichtlinie
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10 bereitstellen, sodass sie in den Dienst onboardiert werden.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893286"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="9b6b5-103">Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9b6b5-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="9b6b5-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-104">**Applies to:**</span></span>

- [<span data-ttu-id="9b6b5-105">Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="9b6b5-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="9b6b5-106">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9b6b5-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="9b6b5-107">Zum Verwenden von Gruppenrichtlinienupdates zum Bereitstellen des Pakets müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="9b6b5-108">Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der VON der Gruppenrichtlinieneinstellung erstellten XML-Datei ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="9b6b5-109">Onboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9b6b5-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="9b6b5-110">Öffnen Sie die Gp.zip datei (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="9b6b5-111">Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="9b6b5-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="9b6b5-112">Wählen Sie im Navigationsbereich die **option Einstellungen**  >  **Device Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="9b6b5-113">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="9b6b5-114">Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="9b6b5-115">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="9b6b5-116">Sie sollten über einen Ordner *namens OptionalParamsPolicy* und die Datei *DeviceComplianceLocalOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="9b6b5-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="9b6b5-117">Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="9b6b5-118">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. </span><span class="sxs-lookup"><span data-stu-id="9b6b5-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="9b6b5-119">Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe (mindestens Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="9b6b5-120">Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern,** und geben Sie SYSTEM ein, und klicken Sie dann **auf Namen überprüfen** und dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="9b6b5-121">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="9b6b5-122">Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="9b6b5-123">Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu...** Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="9b6b5-124">Geben Sie den Dateinamen und speicherort der freigegebenen *Datei WindowsDefenderATPOnboardingScript.cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="9b6b5-125">Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="9b6b5-126">Offboardgeräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9b6b5-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="9b6b5-127">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="9b6b5-128">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="9b6b5-129">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="9b6b5-130">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="9b6b5-131">Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="9b6b5-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="9b6b5-132">Wählen Sie im Navigationsbereich **die option Einstellungen**  >  **/Device onboarding**  >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="9b6b5-133">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="9b6b5-134">Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="9b6b5-135">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="9b6b5-136">Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="9b6b5-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="9b6b5-137">Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="9b6b5-138">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. </span><span class="sxs-lookup"><span data-stu-id="9b6b5-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="9b6b5-139">Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe**.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="9b6b5-140">Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Wählen Sie unter Sicherheitsoptionen das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) **aus.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="9b6b5-141">Aktivieren **Sie Ausführen, ob der** Benutzer angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen **Ausführen** mit den höchsten Rechten.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="9b6b5-142">Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie **auf Neu...**. Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="9b6b5-143">Geben Sie den Dateinamen und den Speicherort der freigegebenen  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd-Datei* ein.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="9b6b5-144">Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b6b5-145">Offboarding bewirkt, dass das Gerät nicht mehr Sensordaten an das Portal sendet, sondern Daten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="9b6b5-146">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="9b6b5-146">Monitor device configuration</span></span>
<span data-ttu-id="9b6b5-147">Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="9b6b5-148">Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="9b6b5-149">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="9b6b5-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="9b6b5-150">Wechseln Sie zu [Microsoft Compliance Center](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9b6b5-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="9b6b5-151">Klicken Sie **auf Geräteliste.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="9b6b5-152">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="9b6b5-153">Es kann mehrere Tage dauern, bis Geräte in der Geräteliste **angezeigt werden.**</span><span class="sxs-lookup"><span data-stu-id="9b6b5-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="9b6b5-154">Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit, die der Benutzer benötigt, bevor sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="9b6b5-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9b6b5-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9b6b5-155">Related topics</span></span>
- [<span data-ttu-id="9b6b5-156">Onboarding Windows 10 Geräte mithilfe Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9b6b5-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="9b6b5-157">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="9b6b5-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="9b6b5-158">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="9b6b5-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="9b6b5-159">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="9b6b5-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="9b6b5-160">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="9b6b5-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="9b6b5-161">Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen</span><span class="sxs-lookup"><span data-stu-id="9b6b5-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)