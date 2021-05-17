---
title: Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop
description: Weitere Informationen finden Sie in diesem Artikel zum Onboarding Windows 10 Geräten mit mehreren Sitzungen in Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, Microsoft Defender, Endpunkt, Onboard
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
ms.openlocfilehash: 0ef80e2aaccbf25a79083c2f95ea7399e30ea651
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764317"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="eaa9e-104">Onboarden von Windows 10-Geräten für mehrere Sitzungen in Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="eaa9e-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="eaa9e-105">6 Minuten zu lesen</span><span class="sxs-lookup"><span data-stu-id="eaa9e-105">6 minutes to read</span></span> 

<span data-ttu-id="eaa9e-106">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="eaa9e-106">Applies to:</span></span> 
- <span data-ttu-id="eaa9e-107">Windows 10, die auf einem virtuellen Windows (Virtual Desktop, WVD) ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="eaa9e-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="eaa9e-108">Microsoft Defender for Endpoint unterstützt die Überwachung von VDI- und Windows Virtual Desktop-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="eaa9e-109">Je nach Den Anforderungen Ihrer Organisation müssen Sie möglicherweise VDI- oder Windows Virtual Desktop-Sitzungen implementieren, um Ihren Mitarbeitern den Zugriff auf Unternehmensdaten und Apps von einem nicht verwalteten Gerät, Remotespeicherort oder ähnlichem Szenario zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="eaa9e-110">Mit Microsoft Defender for Endpoint können Sie diese virtuellen Computer auf anomale Aktivitäten überwachen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="eaa9e-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="eaa9e-111">Before you begin</span></span>
<span data-ttu-id="eaa9e-112">Machen Sie sich mit den [Überlegungen für nicht persistente VDI vertraut.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="eaa9e-112">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="eaa9e-113">Obwohl [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) keine Nichtpersistenzoptionen bietet, bietet es Möglichkeiten, ein goldenes Windows-Image zu verwenden, das zum Bereitstellen neuer Hosts und erneut bereitgestellter Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-113">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="eaa9e-114">Dies erhöht die Unbeständigkeit in der Umgebung und wirkt sich somit auf die Einträge aus, die im Microsoft Defender for Endpoint-Portal erstellt und verwaltet werden, wodurch die Sichtbarkeit für Ihre Sicherheitsanalysten potenziell reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="eaa9e-115">Je nach Wahl der Onboardingmethode können Geräte im Microsoft Defender for Endpoint-Portal wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="eaa9e-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="eaa9e-116">Einzelner Eintrag für jeden virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="eaa9e-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="eaa9e-117">Mehrere Einträge für jeden virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="eaa9e-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="eaa9e-118">Microsoft empfiehlt das Onboarding Windows Virtual Desktop als einzelnen Eintrag pro virtuellem Desktop.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="eaa9e-119">Dadurch wird sichergestellt, dass sich die Untersuchungserfahrung im Microsoft Defender Endpoint-Portal im Kontext eines Geräts befindet, das auf dem Computernamen basiert.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="eaa9e-120">Organisationen, die häufig WVD-Hosts löschen und erneut bereitstellen, sollten die Verwendung dieser Methode in Betracht ziehen, da dadurch verhindert wird, dass mehrere Objekte für denselben Computer im Microsoft Defender for Endpoint-Portal erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="eaa9e-121">Dies kann bei der Untersuchung von Vorfällen zu Verwirrung führen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="eaa9e-122">Für Testumgebungen oder nicht flüchtige Umgebungen können Sie eine andere Auswahl auswählen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="eaa9e-123">Microsoft empfiehlt das Hinzufügen des Microsoft Defender for Endpoint-Onboardingskripts zum goldenen WVD-Image.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="eaa9e-124">Auf diese Weise können Sie sicher sein, dass dieses Onboardingskript sofort beim ersten Start ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="eaa9e-125">Es wird beim ersten Start auf allen WVD-Computern, die aus dem goldenen WVD-Image bereitgestellt werden, als Startskript ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="eaa9e-126">Wenn Sie jedoch eines der Katalogbilder ohne Änderung verwenden, platzieren Sie das Skript an einem freigegebenen Speicherort, und rufen Sie es entweder aus einer lokalen oder einer Domänengruppenrichtlinie auf.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="eaa9e-127">Die Platzierung und Konfiguration des Startskripts für das VDI-Onboarding im goldenen WVD-Image konfiguriert es als Startskript, das beim Starten der WVD ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="eaa9e-128">Es wird NICHT empfohlen, das tatsächliche goldene WVD-Image zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="eaa9e-129">Eine weitere Überlegung ist die Methode, mit der das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="eaa9e-130">Sie sollte so früh wie möglich im Start-/Bereitstellungsprozess ausgeführt werden, um die Zeit zwischen dem Computer, der für den Empfang von Sitzungen verfügbar ist, und dem Onboarding des Geräts an den Dienst zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="eaa9e-131">In den folgenden Szenarien 1 & 2 wird dies berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="eaa9e-132">Szenarien</span><span class="sxs-lookup"><span data-stu-id="eaa9e-132">Scenarios</span></span>
<span data-ttu-id="eaa9e-133">Es gibt mehrere Möglichkeiten zum Onboarding eines WVD-Hostcomputers:</span><span class="sxs-lookup"><span data-stu-id="eaa9e-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="eaa9e-134">Führen Sie das Skript während des Startvorgangs im goldenen Bild (oder von einem freigegebenen Speicherort) aus.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="eaa9e-135">Verwenden Sie ein Verwaltungstool, um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="eaa9e-136">*Szenario 1: Verwenden der lokalen Gruppenrichtlinie*</span><span class="sxs-lookup"><span data-stu-id="eaa9e-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="eaa9e-137">In diesem Szenario muss das Skript in einem goldenen Bild platziert werden und verwendet lokale Gruppenrichtlinien, um frühzeitig im Startvorgang ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="eaa9e-138">Verwenden Sie die Anweisungen unter [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span><span class="sxs-lookup"><span data-stu-id="eaa9e-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="eaa9e-139">Befolgen Sie die Anweisungen für einen einzelnen Eintrag für jedes Gerät.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="eaa9e-140">*Szenario 2: Verwenden von Domänengruppenrichtlinien*</span><span class="sxs-lookup"><span data-stu-id="eaa9e-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="eaa9e-141">In diesem Szenario wird ein zentral gelegenes Skript verwendet und mithilfe einer domänenbasierten Gruppenrichtlinie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="eaa9e-142">Sie können das Skript auch in das goldene Bild platzieren und auf die gleiche Weise ausführen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="eaa9e-143">**Herunterladen der WindowsDefenderATPOnboardingPackage.zip aus dem Windows Defender Security Center**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="eaa9e-144">Öffnen Sie die VDI-Konfigurationspaketdatei .zip (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="eaa9e-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="eaa9e-145">Wählen Sie Microsoft Defender Security Center Navigationsbereich Einstellungen   >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="eaa9e-146">Wählen Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="eaa9e-147">Wählen Sie **im Feld Bereitstellungsmethode** die Option VDI-Onboardingskripts für nicht persistente Endpunkte aus.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="eaa9e-148">Klicken **Sie auf Paket** herunterladen, und speichern .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="eaa9e-149">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="eaa9e-150">Sie sollten über einen Ordner **namens OptionalParamsPolicy** und die **Dateien WindowsDefenderATPOnboardingScript.cmd** und **Onboard-NonPersistentMachine.ps1**.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="eaa9e-151">**Verwenden der Gruppenrichtlinienverwaltungskonsole zum Ausführen des Skripts beim Starten des virtuellen Computers**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="eaa9e-152">Öffnen Sie die Gruppenrichtlinienverwaltungskonsole (Group Policy Management Console, GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt(GPO), das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="eaa9e-153">Wechseln Sie im Gruppenrichtlinienverwaltungs-Editor zu **Einstellungen** für die \> Systemsteuerung **der** \> **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="eaa9e-154">Klicken Sie mit der rechten Maustaste auf Geplante **Vorgänge,** klicken Sie auf **Neu,** und klicken Sie dann auf Sofortaufgabe **(mindestens** Windows 7).</span><span class="sxs-lookup"><span data-stu-id="eaa9e-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="eaa9e-155">Wechseln Sie im geöffneten Aufgabenfenster zur Registerkarte **Allgemein.** Klicken **Sie unter Sicherheitsoptionen** **auf Benutzer oder Gruppe ändern, und** geben Sie SYSTEM ein.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="eaa9e-156">Klicken **Sie auf Namen** überprüfen, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="eaa9e-157">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="eaa9e-158">Aktivieren **Sie Ausführen, ob der Benutzer** angemeldet ist oder nicht, und aktivieren Sie das Kontrollkästchen Mit höchsten **Rechten** ausführen.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="eaa9e-159">Wechseln Sie zur **Registerkarte Aktionen,** und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="eaa9e-160">Stellen Sie **sicher, dass Programm starten** im Feld Aktion ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="eaa9e-161">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eaa9e-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="eaa9e-162">Wählen Sie dann **OK aus,** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="eaa9e-163">*Szenario 3: Onboarding mithilfe von Verwaltungstools*</span><span class="sxs-lookup"><span data-stu-id="eaa9e-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="eaa9e-164">Wenn Sie Planen, Ihre Computer mit einem Verwaltungstool zu verwalten, können Sie Geräte mit Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="eaa9e-165">Weitere Informationen finden Sie unter [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span><span class="sxs-lookup"><span data-stu-id="eaa9e-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="eaa9e-166">Wenn Sie attack [surface reduction Rules](attack-surface-reduction.md)verwenden möchten, beachten Sie, dass die Regel " Block process[creations from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" nicht verwendet werden sollte, da diese Regel nicht mit der Verwaltung über die Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="eaa9e-167">Die Regel blockiert WMI-Befehle, die der Configuration Manager-Client verwendet, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="eaa9e-168">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass das Gerät ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="eaa9e-169">Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="eaa9e-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="eaa9e-170">Markieren Ihrer Computer beim Erstellen Ihres goldenen Bilds</span><span class="sxs-lookup"><span data-stu-id="eaa9e-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="eaa9e-171">Im Rahmen Ihres Onboardings sollten Sie ein Computertag festlegen, um WVD-Computer im Microsoft Security Center einfacher voneinander zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="eaa9e-172">Weitere Informationen finden Sie unter [Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="eaa9e-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="eaa9e-173">Weitere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="eaa9e-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="eaa9e-174">Beim Erstellen Ihres goldenen Bilds sollten Sie möglicherweise auch die anfänglichen Schutzeinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="eaa9e-175">Weitere Informationen finden Sie unter [Weitere empfohlene Konfigurationseinstellungen](configure-endpoints-gp.md#other-recommended-configuration-settings).</span><span class="sxs-lookup"><span data-stu-id="eaa9e-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="eaa9e-176">Wenn Sie außerdem FSlogix-Benutzerprofile verwenden, wird empfohlen, die folgenden Dateien vom Immer-On-Schutz auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="eaa9e-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="eaa9e-177">**Ausschließen von Dateien:**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="eaa9e-178">**Ausschließen von Prozessen:**</span><span class="sxs-lookup"><span data-stu-id="eaa9e-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="eaa9e-179">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="eaa9e-179">Licensing requirements</span></span> 

<span data-ttu-id="eaa9e-180">Hinweis zur Lizenzierung: Wenn Sie Windows 10 Enterprise mehrere Sitzungen verwenden, können Sie je nach Ihren Anforderungen auswählen, ob alle Benutzer über Microsoft Defender for Endpoint (pro Benutzer), Windows Enterprise E5, Microsoft 365 Security oder Microsoft 365 E5 lizenziert werden oder den virtuellen Computer über Azure Defender lizenziert haben.</span><span class="sxs-lookup"><span data-stu-id="eaa9e-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="eaa9e-181">Lizenzierungsanforderungen für Microsoft Defender für Endpunkt finden Sie unter: [Lizenzierungsanforderungen](minimum-requirements.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="eaa9e-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
