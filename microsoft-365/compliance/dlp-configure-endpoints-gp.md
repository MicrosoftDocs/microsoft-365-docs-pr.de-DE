---
title: Onboard-Windows 10-Geräte über Gruppenrichtlinien
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
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10-Geräten bereitzustellen, damit Sie mit dem Dienst an Bord sind.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769415"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="90e61-103">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="90e61-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="90e61-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="90e61-104">**Applies to:**</span></span>

- [<span data-ttu-id="90e61-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="90e61-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="90e61-106">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="90e61-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="90e61-107">Damit Sie das Paket mithilfe von Gruppenrichtlinienupdates (GP) bereitstellen können, müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.</span><span class="sxs-lookup"><span data-stu-id="90e61-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="90e61-108">Für Windows Server 2019 müssen Sie möglicherweise NT-AUTHORITY\Well-known-System-Account durch NT-AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="90e61-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="90e61-109">Integrierte Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="90e61-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="90e61-110">Öffnen Sie die ZIP-Datei des GP-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="90e61-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="90e61-111">Sie können das Paket auch über das [Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding) abrufen.</span><span class="sxs-lookup"><span data-stu-id="90e61-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="90e61-112">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="90e61-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="90e61-113">Wählen Sie im Feld **Bereitstellungsmethode** die Option **Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="90e61-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="90e61-114">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="90e61-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="90e61-115">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="90e61-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="90e61-116">Sie sollten über einen Ordner namens " *OptionalParamsPolicy* " und die Datei " *DeviceComplianceLocalOnboardingScript. cmd* " verfügen.</span><span class="sxs-lookup"><span data-stu-id="90e61-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="90e61-117">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="90e61-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="90e61-118">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computer Konfiguration** , **Einstellungen und** dann in **System** Steuerung.</span><span class="sxs-lookup"><span data-stu-id="90e61-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="90e61-119">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge** , dann auf **neu** , und klicken Sie dann auf **sofortige Aufgabe (mindestens Windows 7)** .</span><span class="sxs-lookup"><span data-stu-id="90e61-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="90e61-120">Wechseln Sie im **Aufgaben** Fenster, das geöffnet wird, zur Registerkarte **Allgemein** . Klicken Sie unter **Sicherheitsoptionen** auf **Benutzer oder Gruppe ändern** , und geben Sie System ein, und klicken Sie dann auf **Namen überprüfen** und dann auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="90e61-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="90e61-121">NT-AUTHORITY\SYSTEM wird als das Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90e61-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="90e61-122">Wählen Sie **ausführen, ob Benutzer angemeldet ist oder nicht** , und aktivieren Sie das Kontrollkästchen **mit den höchsten Rechten ausführen** .</span><span class="sxs-lookup"><span data-stu-id="90e61-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="90e61-123">Wechseln Sie zur Registerkarte **Aktionen** , und klicken Sie auf **neu...** Stellen Sie sicher, dass im Feld **Aktion** die Option **Programm starten** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="90e61-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="90e61-124">Geben Sie den Dateinamen und den Speicherort der freigegebenen Datei *WindowsDefenderATPOnboardingScript. cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="90e61-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="90e61-125">Klicken Sie auf **OK** , und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="90e61-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="90e61-126">Extern-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="90e61-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="90e61-127">Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab.</span><span class="sxs-lookup"><span data-stu-id="90e61-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="90e61-128">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="90e61-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="90e61-129">Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="90e61-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="90e61-130">Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.</span><span class="sxs-lookup"><span data-stu-id="90e61-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="90e61-131">Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)ab.</span><span class="sxs-lookup"><span data-stu-id="90e61-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="90e61-132">Wählen Sie im Navigationsbereich die Option **Einstellungen**  >  **//Device Onboarding**  >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="90e61-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="90e61-133">Wählen Sie im Feld **Bereitstellungsmethode** die Option **Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="90e61-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="90e61-134">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="90e61-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="90e61-135">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="90e61-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="90e61-136">Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.</span><span class="sxs-lookup"><span data-stu-id="90e61-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="90e61-137">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="90e61-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="90e61-138">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computer Konfiguration,** **Einstellungen und** dann in **System** Steuerung.</span><span class="sxs-lookup"><span data-stu-id="90e61-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="90e61-139">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge** , dann auf **neu** , und klicken Sie dann auf **sofortige Aufgabe** .</span><span class="sxs-lookup"><span data-stu-id="90e61-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="90e61-140">Wechseln Sie im **Aufgaben** Fenster, das geöffnet wird, zur Registerkarte **Allgemein** . Wählen Sie das lokale System Benutzerkonto (BUILTIN\SYSTEM) unter **Sicherheitsoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="90e61-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="90e61-141">Wählen Sie **ausführen, ob der Benutzer angemeldet ist oder nicht** , und aktivieren Sie das Kontrollkästchen **mit den höchsten Rechten ausführen** .</span><span class="sxs-lookup"><span data-stu-id="90e61-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="90e61-142">Wechseln Sie zur Registerkarte **Aktionen** , und klicken Sie auf **neu...** . Stellen Sie sicher, dass im Feld **Aktion** die Option **Programm starten** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="90e61-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="90e61-143">Geben Sie den Dateinamen und den Speicherort der freigegebenen  *DeviceComplianceOffboardingScript_valid_until_YYYY Datei-mm-dd. cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="90e61-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="90e61-144">Klicken Sie auf **OK** , und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="90e61-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90e61-145">Offboarding bewirkt, dass das Gerät keine Sensordaten mehr an das Portal sendet, sondern Daten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="90e61-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="90e61-146">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="90e61-146">Monitor device configuration</span></span>
<span data-ttu-id="90e61-147">Mit Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten.</span><span class="sxs-lookup"><span data-stu-id="90e61-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="90e61-148">Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.</span><span class="sxs-lookup"><span data-stu-id="90e61-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="90e61-149">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="90e61-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="90e61-150">Wechseln Sie zum [Microsoft Compliance Center](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="90e61-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="90e61-151">Klicken Sie auf **Geräte** Liste.</span><span class="sxs-lookup"><span data-stu-id="90e61-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="90e61-152">Stellen Sie sicher, dass die Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90e61-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="90e61-153">Es kann mehrere Tage dauern, bis Geräte in der **Liste Geräte** gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="90e61-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="90e61-154">Dies umfasst die Zeit, die für die Verteilung der Richtlinien auf das Gerät benötigt wird, die Zeit bis zum Anmelden des Benutzers und die Zeit, die für den Endpunkt zum Starten der Berichterstellung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="90e61-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="90e61-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="90e61-155">Related topics</span></span>
- [<span data-ttu-id="90e61-156">Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="90e61-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="90e61-157">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="90e61-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="90e61-158">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="90e61-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="90e61-159">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="90e61-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="90e61-160">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät</span><span class="sxs-lookup"><span data-stu-id="90e61-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="90e61-161">Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90e61-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
