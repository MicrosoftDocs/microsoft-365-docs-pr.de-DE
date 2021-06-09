---
title: Onboarding von Windows 10 Geräten in Microsoft Defender für Endpunkt über Gruppenrichtlinien
description: Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Windows 10 Geräten bereitzustellen, sodass sie in den Dienst integriert sind.
keywords: Konfigurieren von Geräten mithilfe von Gruppenrichtlinien, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte, Onboarding von Microsoft Defender für Endpunktgeräte, Gruppenrichtlinie
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: f607e36cef85f30fa1d6e073da871ac1c140684c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841834"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="52da1-104">Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="52da1-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52da1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="52da1-105">**Applies to:**</span></span>

- <span data-ttu-id="52da1-106">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="52da1-106">Group Policy</span></span>
- [<span data-ttu-id="52da1-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="52da1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="52da1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52da1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="52da1-109">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="52da1-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="52da1-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="52da1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="52da1-111">Um Gruppenrichtlinienupdates zum Bereitstellen des Pakets zu verwenden, müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.</span><span class="sxs-lookup"><span data-stu-id="52da1-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="52da1-112">Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="52da1-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="52da1-113">Onboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="52da1-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="52da1-114">[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="52da1-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="52da1-115">Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender für Endpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="52da1-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="52da1-116">Öffnen Sie das GP-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="52da1-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="52da1-117">Sie können das Paket auch von [Microsoft Defender Security Center](https://securitycenter.windows.com/)abrufen:</span><span class="sxs-lookup"><span data-stu-id="52da1-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="52da1-118">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="52da1-119">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="52da1-120">Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="52da1-121">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="52da1-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="52da1-122">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="52da1-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="52da1-123">Sie sollten über einen Ordner namens *"OptionalParamsPolicy"* und die Datei *"WindowsDefenderATPOnboardingScript.cmd" verfügen.*</span><span class="sxs-lookup"><span data-stu-id="52da1-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="52da1-124">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="52da1-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="52da1-125">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="52da1-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="52da1-126">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang" (mindestens Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="52da1-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="52da1-127">Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Klicken Sie unter **"Sicherheitsoptionen"** auf **"Benutzer oder Gruppe ändern",** und geben Sie "SYSTEM" ein, und klicken Sie dann auf **"Namen überprüfen",** und klicken Sie dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="52da1-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="52da1-128">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52da1-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="52da1-129">Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit höchsten Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="52da1-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="52da1-130">Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...** Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="52da1-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="52da1-131">Geben Sie den Dateinamen und speicherort der freigegebenen *Datei "WindowsDefenderATPOnboardingScript.cmd"* ein.</span><span class="sxs-lookup"><span data-stu-id="52da1-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="52da1-132">Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="52da1-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="52da1-133">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob das Gerät ordnungsgemäß in den Dienst integriert ist.</span><span class="sxs-lookup"><span data-stu-id="52da1-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="52da1-134">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="52da1-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="52da1-135">Zusätzliche Konfigurationseinstellungen für Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="52da1-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="52da1-136">Für jedes Gerät können Sie angeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft Defender Security Center gestellt wird, um eine Datei für eine umfassende Analyse zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="52da1-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="52da1-137">Sie können Gruppenrichtlinien (GP) verwenden, um Einstellungen zu konfigurieren, z. B. Einstellungen für die Beispielfreigabe, die im Feature für die umfassende Analyse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="52da1-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="52da1-138">Konfigurieren von Beispielsammlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="52da1-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="52da1-139">Kopieren Sie auf Ihrem GP-Verwaltungsgerät die folgenden Dateien aus dem Konfigurationspaket:</span><span class="sxs-lookup"><span data-stu-id="52da1-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="52da1-140">Kopieren von _"AtpConfiguration.admx"_ in _"C: \\ Windows \\ PolicyDefinitions"_</span><span class="sxs-lookup"><span data-stu-id="52da1-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="52da1-141">Kopieren von _"AtpConfiguration.adml"_ in _"C: \\ Windows \\ PolicyDefinitions \\ en-US"_</span><span class="sxs-lookup"><span data-stu-id="52da1-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="52da1-142">Wenn Sie eine [zentrale Store für administrative Gruppenrichtlinienvorlagen](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)verwenden, kopieren Sie die folgenden Dateien aus dem Konfigurationspaket:</span><span class="sxs-lookup"><span data-stu-id="52da1-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="52da1-143">Kopieren von _"AtpConfiguration.admx"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions"_</span><span class="sxs-lookup"><span data-stu-id="52da1-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="52da1-144">Kopieren von _"AtpConfiguration.adml"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US"_</span><span class="sxs-lookup"><span data-stu-id="52da1-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="52da1-145">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)klicken Sie mit der rechten Maustaste auf das gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="52da1-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="52da1-146">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="52da1-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="52da1-147">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="52da1-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="52da1-148">Klicken Sie auf **Windows Komponenten,** und **Windows Defender Sie SmartScreen.**</span><span class="sxs-lookup"><span data-stu-id="52da1-148">Click **Windows components** and then **Windows Defender SmartScreen**.</span></span>

6.  <span data-ttu-id="52da1-149">Wählen Sie aus, ob Sie die Beispielfreigabe auf Ihren Geräten aktivieren oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="52da1-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="52da1-150">Wenn Sie keinen Wert festlegen, wird standardmäßig die Beispielsammlung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="52da1-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="52da1-151">Andere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="52da1-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="52da1-152">Aktualisieren der Endpunktschutzkonfiguration</span><span class="sxs-lookup"><span data-stu-id="52da1-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="52da1-153">Fahren Sie nach dem Konfigurieren des Onboardingskripts mit der Bearbeitung derselben Gruppenrichtlinie fort, um Endpunktschutzkonfigurationen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="52da1-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="52da1-154">Führen Sie Gruppenrichtlinienbearbeitungen von einem System aus durch, auf dem Windows 10 oder Server 2019 ausgeführt wird, um sicherzustellen, dass Sie über alle erforderlichen Microsoft Defender Antivirus Funktionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="52da1-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="52da1-155">Möglicherweise müssen Sie das Gruppenrichtlinienobjekt schließen und erneut öffnen, um die Defender ATP-Konfigurationseinstellungen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="52da1-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="52da1-156">Alle Richtlinien befinden sich unter `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="52da1-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="52da1-157">**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender SmartScreen\*</span><span class="sxs-lookup"><span data-stu-id="52da1-157">**Policy location:** \Windows Components\Windows Defender SmartScreen\*</span></span>

<span data-ttu-id="52da1-158">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-158">Policy</span></span> | <span data-ttu-id="52da1-159">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-159">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="52da1-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="52da1-161">Aktiviert – "Beispielsammlung auf Computern aktivieren" aktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="52da1-162">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="52da1-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="52da1-163">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-163">Policy</span></span> | <span data-ttu-id="52da1-164">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-164">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-165">Konfigurieren der Erkennung für potenziell unerwünschte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="52da1-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="52da1-166">Aktiviert, Blockieren</span><span class="sxs-lookup"><span data-stu-id="52da1-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="52da1-167">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="52da1-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="52da1-168">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-168">Policy</span></span> | <span data-ttu-id="52da1-169">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-169">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-170">Microsoft MAPS beitreten</span><span class="sxs-lookup"><span data-stu-id="52da1-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="52da1-171">Aktiviert, Erweiterte KARTEN</span><span class="sxs-lookup"><span data-stu-id="52da1-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="52da1-172">Senden von Dateibeispielen, wenn eine weitere Analyse erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="52da1-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="52da1-173">Aktiviert, Sichere Beispiele senden</span><span class="sxs-lookup"><span data-stu-id="52da1-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="52da1-174">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="52da1-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="52da1-175">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-175">Policy</span></span> | <span data-ttu-id="52da1-176">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-176">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-177">Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="52da1-177">Turn off real-time protection</span></span>|<span data-ttu-id="52da1-178">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-178">Disabled</span></span>
<span data-ttu-id="52da1-179">Aktivieren der Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="52da1-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="52da1-180">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-180">Enabled</span></span>
<span data-ttu-id="52da1-181">Scannen aller heruntergeladenen Dateien und Anlagen</span><span class="sxs-lookup"><span data-stu-id="52da1-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="52da1-182">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-182">Enabled</span></span>
<span data-ttu-id="52da1-183">Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="52da1-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="52da1-184">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-184">Enabled</span></span>

<br/>

<span data-ttu-id="52da1-185">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender AntivirusScan</span><span class="sxs-lookup"><span data-stu-id="52da1-185">**Policy location:**  \Windows Components\Microsoft Defender AntivirusScan</span></span>

<span data-ttu-id="52da1-186">Diese Einstellungen konfigurieren regelmäßige Scans des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="52da1-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="52da1-187">Es wird empfohlen, einen wöchentlichen Schnellscan durchzuführen, der die Leistung zulässt.</span><span class="sxs-lookup"><span data-stu-id="52da1-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="52da1-188">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-188">Policy</span></span> | <span data-ttu-id="52da1-189">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-189">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-190">Überprüfen Sie die neuesten Informationen zur Viren- und Spywaresicherheit, bevor Sie einen geplanten Scan ausführen.</span><span class="sxs-lookup"><span data-stu-id="52da1-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="52da1-191">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="52da1-191">Enabled</span></span>


<br/>

<span data-ttu-id="52da1-192">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="52da1-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="52da1-193">Abrufen der aktuellen Liste der GUIDs zur Verringerung der Angriffsfläche aus dem Anpassen der Regeln zur Verringerung der [Angriffsfläche](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="52da1-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="52da1-194">Öffnen Sie die **Richtlinie "Attack Surface Reduction konfigurieren".**</span><span class="sxs-lookup"><span data-stu-id="52da1-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="52da1-195">Wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="52da1-196">Wählen Sie die Schaltfläche **"Anzeigen"** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="52da1-197">Fügen Sie jede GUID im **Feld Wertname** mit dem Wert 2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="52da1-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="52da1-198">Dadurch wird jede nur für die Überwachung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="52da1-198">This will set each up for audit only.</span></span>

   ![Abbildung der Attack Surface Reduction-Konfiguration](images/asr-guid.png)



<span data-ttu-id="52da1-200">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52da1-200">Policy</span></span> | <span data-ttu-id="52da1-201">Einstellung</span><span class="sxs-lookup"><span data-stu-id="52da1-201">Setting</span></span> 
:---|:---
<span data-ttu-id="52da1-202">Konfigurieren des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="52da1-202">Configure Controlled folder access</span></span>| <span data-ttu-id="52da1-203">Aktiviert, Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="52da1-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="52da1-204">Offboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="52da1-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="52da1-205">Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="52da1-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="52da1-206">Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="52da1-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="52da1-207">Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="52da1-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="52da1-208">Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.</span><span class="sxs-lookup"><span data-stu-id="52da1-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="52da1-209">Rufen Sie das Offboarding-Paket aus [Microsoft Defender Security Center](https://securitycenter.windows.com/)ab:</span><span class="sxs-lookup"><span data-stu-id="52da1-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="52da1-210">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="52da1-211">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="52da1-212">Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="52da1-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="52da1-213">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="52da1-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="52da1-214">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="52da1-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="52da1-215">Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="52da1-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="52da1-216">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="52da1-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="52da1-217">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="52da1-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="52da1-218">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang".**</span><span class="sxs-lookup"><span data-stu-id="52da1-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="52da1-219">Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Wählen Sie das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) unter **"Sicherheitsoptionen" aus.**</span><span class="sxs-lookup"><span data-stu-id="52da1-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="52da1-220">Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit den höchsten Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="52da1-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="52da1-221">Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...**. Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="52da1-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="52da1-222">Geben Sie den Dateinamen und Speicherort der freigegebenen  *Datei WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="52da1-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="52da1-223">Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="52da1-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52da1-224">Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="52da1-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="52da1-225">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="52da1-225">Monitor device configuration</span></span>
<span data-ttu-id="52da1-226">Bei Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten.</span><span class="sxs-lookup"><span data-stu-id="52da1-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="52da1-227">Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.</span><span class="sxs-lookup"><span data-stu-id="52da1-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="52da1-228">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="52da1-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="52da1-229">Wechseln Sie zu [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="52da1-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="52da1-230">Klicken Sie auf **"Geräteliste".**</span><span class="sxs-lookup"><span data-stu-id="52da1-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="52da1-231">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="52da1-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="52da1-232">Es kann mehrere Tage dauern, bis Geräte in der Geräteliste angezeigt **werden.**</span><span class="sxs-lookup"><span data-stu-id="52da1-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="52da1-233">Dies umfasst die Zeit, die es dauert, bis die Richtlinien auf das Gerät verteilt werden, die Zeit, bis sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="52da1-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="52da1-234">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="52da1-234">Related topics</span></span>
- [<span data-ttu-id="52da1-235">Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="52da1-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="52da1-236">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="52da1-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="52da1-237">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="52da1-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="52da1-238">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="52da1-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="52da1-239">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="52da1-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="52da1-240">Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten</span><span class="sxs-lookup"><span data-stu-id="52da1-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
