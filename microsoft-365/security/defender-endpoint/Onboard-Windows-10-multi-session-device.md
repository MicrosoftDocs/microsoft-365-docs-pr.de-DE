---
title: Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop
description: Weitere Informationen zum Onboarding von Windows 10 Geräten mit mehreren Sitzungen in Windows Virtual Desktop finden Sie in diesem Artikel.
keywords: Windows Virtual Desktop, WVD, Microsoft Defender, Endpunkt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339478"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="0c38c-104">Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="0c38c-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="0c38c-105">6 Minuten zu lesen</span><span class="sxs-lookup"><span data-stu-id="0c38c-105">6 minutes to read</span></span> 

<span data-ttu-id="0c38c-106">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="0c38c-106">Applies to:</span></span> 
- <span data-ttu-id="0c38c-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="0c38c-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="0c38c-108">Microsoft Defender für Endpunkt unterstützt die Überwachung von VDI- und Windows Virtual Desktop-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="0c38c-109">Je nach den Anforderungen Ihrer Organisation müssen Sie möglicherweise VDI- oder Windows Virtual Desktop-Sitzungen implementieren, damit Ihre Mitarbeiter über ein nicht verwaltetes Gerät, einen Remotestandort oder ein ähnliches Szenario auf Unternehmensdaten und Apps zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0c38c-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="0c38c-110">Mit Microsoft Defender für Endpunkt können Sie diese virtuellen Computer auf anomale Aktivitäten überwachen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="0c38c-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="0c38c-111">Before you begin</span></span>
<span data-ttu-id="0c38c-112">Machen Sie sich mit den [Überlegungen für nicht persistente VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)vertraut.</span><span class="sxs-lookup"><span data-stu-id="0c38c-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="0c38c-113">[Während Windows Virtual Desktop](/azure/virtual-desktop/overview) keine Nichtpersistenzoptionen bereitstellt, bietet es möglichkeiten, ein goldenen Windows-Image zu verwenden, das zum Bereitstellen neuer Hosts und zum erneuten Bereitstellen von Computern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c38c-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="0c38c-114">Dies erhöht die Aufmerksamkeit in der Umgebung und wirkt sich daher darauf aus, welche Einträge im Microsoft Defender für Endpunkt-Portal erstellt und verwaltet werden, wodurch die Sichtbarkeit für Ihre Sicherheitsanalysten möglicherweise reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="0c38c-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="0c38c-115">Je nachdem, welche Onboardingmethode Sie auswählen, können Geräte im Microsoft Defender für Endpunkt-Portal als eine der folgenden Optionen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="0c38c-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="0c38c-116">Einzelner Eintrag für jeden virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="0c38c-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="0c38c-117">Mehrere Einträge für jeden virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="0c38c-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="0c38c-118">Microsoft empfiehlt, Windows virtuellen Desktop als einzelnen Eintrag pro virtuellem Desktop zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="0c38c-119">Dadurch wird sichergestellt, dass sich die Untersuchung im Microsoft Defender Endpoint-Portal im Kontext eines Geräts basierend auf dem Computernamen befindet.</span><span class="sxs-lookup"><span data-stu-id="0c38c-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="0c38c-120">Organisationen, die häufig WVD-Hosts löschen und erneut bereitstellen, sollten die Verwendung dieser Methode dringend in Betracht ziehen, da sie verhindert, dass mehrere Objekte für denselben Computer im Microsoft Defender für Endpunkt-Portal erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c38c-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="0c38c-121">Dies kann bei der Untersuchung von Vorfällen zu Verwirrung führen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="0c38c-122">Für Testumgebungen oder nicht veränderliche Umgebungen können Sie sich für eine andere Auswahl entscheiden.</span><span class="sxs-lookup"><span data-stu-id="0c38c-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="0c38c-123">Microsoft empfiehlt das Hinzufügen des Microsoft Defender für Endpunkt-Onboarding-Skripts zum goldenen WVD-Image.</span><span class="sxs-lookup"><span data-stu-id="0c38c-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="0c38c-124">Auf diese Weise können Sie sicher sein, dass dieses Onboardingskript sofort beim ersten Start ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c38c-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="0c38c-125">Es wird als Startskript beim ersten Start auf allen WVD-Computern ausgeführt, die vom goldenen WVD-Image bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c38c-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="0c38c-126">Wenn Sie jedoch eines der Katalogbilder ohne Änderung verwenden, platzieren Sie das Skript an einem freigegebenen Speicherort, und rufen Sie es aus der lokalen oder Domänengruppenrichtlinie auf.</span><span class="sxs-lookup"><span data-stu-id="0c38c-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="0c38c-127">Die Platzierung und Konfiguration des VDI-Onboarding-Startskripts auf dem goldenen WVD-Image konfiguriert es als Startskript, das beim Starten der WVD ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c38c-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="0c38c-128">Es wird NICHT empfohlen, das eigentliche WVD-Golden-Image zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="0c38c-129">Eine weitere Überlegung ist die Methode, die zum Ausführen des Skripts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c38c-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="0c38c-130">Es sollte so früh wie möglich im Start-/Bereitstellungsprozess ausgeführt werden, um die Zeit zwischen dem Computer, der für den Empfang von Sitzungen verfügbar ist, und dem Onboarding des Geräts in den Dienst zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="0c38c-131">In den folgenden Szenarien 1 & 2 wird dies berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="0c38c-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="0c38c-132">Szenarien</span><span class="sxs-lookup"><span data-stu-id="0c38c-132">Scenarios</span></span>
<span data-ttu-id="0c38c-133">Es gibt mehrere Möglichkeiten zum Onboarding eines WVD-Hostcomputers:</span><span class="sxs-lookup"><span data-stu-id="0c38c-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="0c38c-134">Führen Sie das Skript während des Starts im goldenen Bild (oder von einem freigegebenen Speicherort) aus.</span><span class="sxs-lookup"><span data-stu-id="0c38c-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="0c38c-135">Verwenden Sie ein Verwaltungstool, um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="0c38c-136">*Szenario 1: Verwenden einer lokalen Gruppenrichtlinie*</span><span class="sxs-lookup"><span data-stu-id="0c38c-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="0c38c-137">Dieses Szenario erfordert, dass das Skript in einem goldenen Image platziert wird und die lokale Gruppenrichtlinie verwendet wird, um früh im Startprozess ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="0c38c-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="0c38c-138">Verwenden Sie die Anweisungen unter [Onboarding der nicht persistenten VDI-Geräte (Virtual Desktop Infrastructure).](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices)</span><span class="sxs-lookup"><span data-stu-id="0c38c-138">Use the instructions in [Onboard the non-persistent virtual desktop infrastructure (VDI) devices](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices).</span></span>

<span data-ttu-id="0c38c-139">Befolgen Sie die Anweisungen für einen einzelnen Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="0c38c-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="0c38c-140">*Szenario 2: Verwenden von Domänengruppenrichtlinien*</span><span class="sxs-lookup"><span data-stu-id="0c38c-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="0c38c-141">In diesem Szenario wird ein zentral gespeichertes Skript verwendet und mithilfe einer domänenbasierten Gruppenrichtlinie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c38c-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="0c38c-142">Sie können das Skript auch im goldenen Bild platzieren und auf die gleiche Weise ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="0c38c-143">**Laden Sie die datei WindowsDefenderATPOnboardingPackage.zip aus dem Windows Defender Security Center herunter.**</span><span class="sxs-lookup"><span data-stu-id="0c38c-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="0c38c-144">Öffnen Des VDI-Konfigurationspakets .zip Datei (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="0c38c-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="0c38c-145">Wählen Sie im Navigationsbereich Microsoft Defender Security Center **Einstellungen**  >  **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="0c38c-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="0c38c-146">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="0c38c-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="0c38c-147">Wählen Sie im Feld **"Bereitstellungsmethode"** VDI-Onboardingskripts für nicht persistente Endpunkte aus.</span><span class="sxs-lookup"><span data-stu-id="0c38c-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="0c38c-148">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="0c38c-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="0c38c-149">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0c38c-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0c38c-150">Sie sollten über einen Ordner namens **"OptionalParamsPolicy"** und die Dateien **"WindowsDefenderATPOnboardingScript.cmd"** und **Onboard-NonPersistentMachine.ps1** verfügen.</span><span class="sxs-lookup"><span data-stu-id="0c38c-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="0c38c-151">**Verwenden der Gruppenrichtlinien-Verwaltungskonsole zum Ausführen des Skripts beim Starten des virtuellen Computers**</span><span class="sxs-lookup"><span data-stu-id="0c38c-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="0c38c-152">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="0c38c-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="0c38c-153">Wechseln Sie im Gruppenrichtlinienverwaltungs-Editor zu Einstellungen der Systemsteuerung für **die Computerkonfiguration.** \>  \> </span><span class="sxs-lookup"><span data-stu-id="0c38c-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="0c38c-154">Klicken Sie mit der rechten Maustaste auf **Geplante Vorgänge,** klicken Sie auf **Neu** und dann auf **"Sofortvorgang"** (mindestens Windows 7).</span><span class="sxs-lookup"><span data-stu-id="0c38c-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="0c38c-155">Wechseln Sie im geöffneten Aufgabenfenster zur Registerkarte **"Allgemein".** Klicken Sie unter **"Sicherheitsoptionen"** auf **"Benutzer oder Gruppe ändern",** und geben Sie "SYSTEM" ein.</span><span class="sxs-lookup"><span data-stu-id="0c38c-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="0c38c-156">Klicken Sie auf **"Namen überprüfen",** und klicken Sie dann auf "OK".</span><span class="sxs-lookup"><span data-stu-id="0c38c-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="0c38c-157">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c38c-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="0c38c-158">Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit höchsten Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="0c38c-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="0c38c-159">Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu".**</span><span class="sxs-lookup"><span data-stu-id="0c38c-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="0c38c-160">Stellen Sie sicher, dass **"Programm starten"** im Feld "Aktion" ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0c38c-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="0c38c-161">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="0c38c-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="0c38c-162">Wählen Sie dann **OK** aus, und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="0c38c-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="0c38c-163">*Szenario 3: Onboarding mithilfe von Verwaltungstools*</span><span class="sxs-lookup"><span data-stu-id="0c38c-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="0c38c-164">Wenn Sie beabsichtigen, Ihre Computer mit einem Verwaltungstool zu verwalten, können Sie Geräte mit Microsoft Endpoint Configuration Manager integrieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="0c38c-165">Weitere Informationen finden Sie unter [Onboarding Windows 10 Geräte mit Configuration Manager.](configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="0c38c-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="0c38c-166">Wenn Sie die [Attack Surface Reduction-Regeln](attack-surface-reduction.md)verwenden möchten, beachten Sie, dass die Regel["Prozesserstellungen blockieren, die von PSExec- und WMI-Befehlen stammen"](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)nicht verwendet werden sollte, da diese Regel mit der Verwaltung über Microsoft Endpoint Configuration Manager nicht kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0c38c-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="0c38c-167">Die Regel blockiert WMI-Befehle, die der Configuration Manager-Client verwendet, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="0c38c-168">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob das Gerät ordnungsgemäß in den Dienst integriert ist.</span><span class="sxs-lookup"><span data-stu-id="0c38c-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="0c38c-169">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="0c38c-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="0c38c-170">Kennzeichnen Ihrer Computer beim Erstellen ihres goldenen Bilds</span><span class="sxs-lookup"><span data-stu-id="0c38c-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="0c38c-171">Im Rahmen Ihres Onboardings sollten Sie erwägen, ein Computertag festzulegen, um WVD-Computer im Microsoft Security Center einfacher unterscheiden zu können.</span><span class="sxs-lookup"><span data-stu-id="0c38c-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="0c38c-172">Weitere Informationen finden Sie unter [Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="0c38c-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="0c38c-173">Andere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="0c38c-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="0c38c-174">Beim Erstellen ihres goldenen Images sollten Sie auch die anfänglichen Schutzeinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0c38c-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="0c38c-175">Weitere Informationen finden Sie unter ["Weitere empfohlene Konfigurationseinstellungen".](configure-endpoints-gp.md#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="0c38c-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="0c38c-176">Wenn Sie FSlogix-Benutzerprofile verwenden, wird außerdem empfohlen, die folgenden Dateien vom always-on-Schutz auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="0c38c-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="0c38c-177">**Ausschließen von Dateien:**</span><span class="sxs-lookup"><span data-stu-id="0c38c-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="0c38c-178">**Ausschließen von Prozessen:**</span><span class="sxs-lookup"><span data-stu-id="0c38c-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="0c38c-179">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="0c38c-179">Licensing requirements</span></span> 

<span data-ttu-id="0c38c-180">Hinweis zur Lizenzierung: Wenn Sie Windows 10 Enterprise mehrere Sitzung verwenden, können Sie je nach Ihren Anforderungen auswählen, ob alle Benutzer über Microsoft Defender für Endpunkt (pro Benutzer), Windows Enterprise E5, Microsoft 365 Security oder Microsoft 365 E5 lizenziert sind oder ob der virtuelle Computer über Azure Defender lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="0c38c-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="0c38c-181">Die Lizenzierungsanforderungen für Microsoft Defender für Endpunkt finden Sie unter: [Lizenzierungsanforderungen.](minimum-requirements.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="0c38c-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

#### <a name="related-links"></a><span data-ttu-id="0c38c-182">Links zu verwandten Themen</span><span class="sxs-lookup"><span data-stu-id="0c38c-182">Related Links</span></span>

[<span data-ttu-id="0c38c-183">Hinzufügen von Ausschlüssen für Microsoft Defender mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c38c-183">Add exclusions for Microsoft Defender by using PowerShell</span></span>](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
