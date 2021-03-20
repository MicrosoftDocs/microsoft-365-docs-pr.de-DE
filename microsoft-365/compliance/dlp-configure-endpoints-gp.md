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
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10-Geräten so zu bereitstellen, dass sie in den Dienst onboardiert werden.
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918021"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="c615c-103">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c615c-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="c615c-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c615c-104">**Applies to:**</span></span>

- [<span data-ttu-id="c615c-105">Microsoft 365 Endpoint Data Loss Prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="c615c-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="c615c-106">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c615c-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="c615c-107">Um Gruppenrichtlinienupdates (GP)-Updates zum Bereitstellen des Pakets zu verwenden, müssen Sie sich auf Windows Server 2008 R2 oder höher.</span><span class="sxs-lookup"><span data-stu-id="c615c-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="c615c-108">Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c615c-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="c615c-109">Onboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c615c-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="c615c-110">Öffnen Sie die ZIP-Datei des *GP-Konfigurationspakets*(DeviceComplianceOnboardingPackage.zip), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="c615c-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="c615c-111">Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="c615c-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="c615c-112">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Geräte onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="c615c-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="c615c-113">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="c615c-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="c615c-114">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="c615c-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="c615c-115">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c615c-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="c615c-116">Sie sollten über einen Ordner *namens OptionalParamsPolicy* und die Datei *DeviceComplianceLocalOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="c615c-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="c615c-117">Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c615c-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="c615c-118">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. </span><span class="sxs-lookup"><span data-stu-id="c615c-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="c615c-119">Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe (Mindestens Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="c615c-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="c615c-120">Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern,** und geben Sie SYSTEM ein, und klicken Sie dann **auf Namen überprüfen** und dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="c615c-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="c615c-121">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c615c-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="c615c-122">Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen.</span><span class="sxs-lookup"><span data-stu-id="c615c-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="c615c-123">Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu...** Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="c615c-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="c615c-124">Geben Sie den Dateinamen und speicherort der freigegebenen *Datei WindowsDefenderATPOnboardingScript.cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="c615c-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="c615c-125">Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="c615c-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="c615c-126">Offboardgeräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c615c-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="c615c-127">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="c615c-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="c615c-128">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="c615c-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="c615c-129">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c615c-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="c615c-130">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="c615c-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="c615c-131">Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="c615c-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="c615c-132">Wählen Sie im Navigationsbereich **Einstellungen**  >  **/Device onboarding**  >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="c615c-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="c615c-133">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Gruppenrichtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="c615c-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="c615c-134">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="c615c-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="c615c-135">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c615c-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="c615c-136">Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="c615c-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="c615c-137">Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group [Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c615c-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="c615c-138">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** dann Einstellungen und dann **Systemsteuerungseinstellungen**. </span><span class="sxs-lookup"><span data-stu-id="c615c-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="c615c-139">Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **Sofortaufgabe**.</span><span class="sxs-lookup"><span data-stu-id="c615c-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="c615c-140">Wechseln Sie **im** geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Wählen Sie unter Sicherheitsoptionen das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) **aus.**</span><span class="sxs-lookup"><span data-stu-id="c615c-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="c615c-141">Aktivieren **Sie Ausführen, ob der** Benutzer angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen **Ausführen** mit den höchsten Rechten.</span><span class="sxs-lookup"><span data-stu-id="c615c-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="c615c-142">Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie **auf Neu...**. Stellen Sie **sicher, dass Programm starten** im Feld **Aktion ausgewählt** ist.</span><span class="sxs-lookup"><span data-stu-id="c615c-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="c615c-143">Geben Sie den Dateinamen und den Speicherort der freigegebenen  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd-Datei* ein.</span><span class="sxs-lookup"><span data-stu-id="c615c-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="c615c-144">Klicken Sie **auf OK,** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="c615c-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c615c-145">Offboarding bewirkt, dass das Gerät nicht mehr Sensordaten an das Portal sendet, sondern Daten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="c615c-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="c615c-146">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="c615c-146">Monitor device configuration</span></span>
<span data-ttu-id="c615c-147">Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten.</span><span class="sxs-lookup"><span data-stu-id="c615c-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="c615c-148">Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c615c-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="c615c-149">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="c615c-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="c615c-150">Wechseln Sie zu [Microsoft Compliance Center](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c615c-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="c615c-151">Klicken Sie **auf Geräteliste.**</span><span class="sxs-lookup"><span data-stu-id="c615c-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="c615c-152">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c615c-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="c615c-153">Es kann mehrere Tage dauern, bis Geräte in der Geräteliste **angezeigt werden.**</span><span class="sxs-lookup"><span data-stu-id="c615c-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="c615c-154">Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit, die der Benutzer benötigt, bevor sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c615c-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c615c-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c615c-155">Related topics</span></span>
- [<span data-ttu-id="c615c-156">Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c615c-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="c615c-157">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="c615c-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="c615c-158">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="c615c-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="c615c-159">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="c615c-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="c615c-160">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender ATP-Gerät</span><span class="sxs-lookup"><span data-stu-id="c615c-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="c615c-161">Behandeln von Problemen mit dem Microsoft Defender Advanced Threat Protection-Onboarding</span><span class="sxs-lookup"><span data-stu-id="c615c-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)