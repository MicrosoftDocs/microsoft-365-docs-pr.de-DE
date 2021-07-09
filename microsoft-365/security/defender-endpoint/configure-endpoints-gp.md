---
title: Onboarding von Windows 10 Geräten in Microsoft Defender für Endpunkt über Gruppenrichtlinien
description: Verwenden Sie die Gruppenrichtlinie, um das Konfigurationspaket auf den Windows 10 Geräten bereitzustellen, sodass sie in den Dienst integriert sind.
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
ms.openlocfilehash: 26bdb0fbdb417d9e7fb01e4c3a863c44e57b7fb7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339622"
---
# <a name="onboard-the-windows-10-devices-using-group-policy"></a><span data-ttu-id="6df76-104">Onboarding der Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6df76-104">Onboard the Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6df76-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6df76-105">**Applies to:**</span></span>

- <span data-ttu-id="6df76-106">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-106">Group Policy</span></span>
- [<span data-ttu-id="6df76-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6df76-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6df76-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6df76-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6df76-109">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="6df76-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6df76-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="6df76-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="6df76-111">Um Gruppenrichtlinienupdates zum Bereitstellen des Pakets zu verwenden, müssen Sie sich auf Windows Server 2008 R2 oder höher befinden.</span><span class="sxs-lookup"><span data-stu-id="6df76-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
>
> <span data-ttu-id="6df76-112">Für Windows Server 2019 müssen Sie möglicherweise NT AUTHORITY\Well-Known-System-Account durch NT AUTHORITY\SYSTEM der XML-Datei ersetzen, die von der Gruppenrichtlinieneinstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6df76-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="6df76-113">Onboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6df76-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="6df76-114">[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6df76-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="6df76-115">Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender für Endpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6df76-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span>

1. <span data-ttu-id="6df76-116">Öffnen Sie das GP-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="6df76-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="6df76-117">Sie können das Paket auch aus [Microsoft 365 Defender Portal](https://security.microsoft.com/)abrufen:</span><span class="sxs-lookup"><span data-stu-id="6df76-117">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="6df76-118">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Device Management**   >  **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-118">In the navigation pane, select **Settings** > **Endpoints** > **Device management**  > **Onboarding**.</span></span>

    1. <span data-ttu-id="6df76-119">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="6df76-120">Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-120">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="6df76-121">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="6df76-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="6df76-122">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="6df76-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="6df76-123">Sie sollten über einen Ordner namens *"OptionalParamsPolicy"* und die Datei *"WindowsDefenderATPOnboardingScript.cmd" verfügen.*</span><span class="sxs-lookup"><span data-stu-id="6df76-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="6df76-124">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="6df76-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="6df76-125">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="6df76-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="6df76-126">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang" (mindestens Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="6df76-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="6df76-127">Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Klicken Sie unter **"Sicherheitsoptionen"** auf **"Benutzer oder Gruppe ändern",** und geben Sie "SYSTEM" ein, und klicken Sie dann auf **"Namen überprüfen",** und klicken Sie dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="6df76-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="6df76-128">NT AUTHORITY\SYSTEM wird als Benutzerkonto angezeigt, unter dem die Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6df76-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="6df76-129">Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit höchsten Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="6df76-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="6df76-130">Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...** Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="6df76-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="6df76-131">Geben Sie den NetBIOS-Pfad der freigegebenen Datei  *"WindowsDefenderATPOnboardingScript.cmd"* ein.</span><span class="sxs-lookup"><span data-stu-id="6df76-131">Enter the NetBIOS path of the shared  *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="6df76-132">Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="6df76-132">Click **OK** and close any open GPMC windows.</span></span>

> [!TIP]
> <span data-ttu-id="6df76-133">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob das Gerät ordnungsgemäß in den Dienst integriert ist.</span><span class="sxs-lookup"><span data-stu-id="6df76-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="6df76-134">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="6df76-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="6df76-135">Zusätzliche Konfigurationseinstellungen für Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6df76-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="6df76-136">Für jedes Gerät können Sie angeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft 365 Defender zum Übermitteln einer Datei für eine umfassende Analyse gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6df76-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft 365 Defender to submit a file for deep analysis.</span></span>

<span data-ttu-id="6df76-137">Sie können Gruppenrichtlinien (GP) verwenden, um Einstellungen zu konfigurieren, z. B. Einstellungen für die Beispielfreigabe, die im Feature für die umfassende Analyse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6df76-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="6df76-138">Konfigurieren von Beispielsammlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="6df76-138">Configure sample collection settings</span></span>

1. <span data-ttu-id="6df76-139">Kopieren Sie auf Ihrem GP-Verwaltungsgerät die folgenden Dateien aus dem Konfigurationspaket:</span><span class="sxs-lookup"><span data-stu-id="6df76-139">On your GP management device, copy the following files from the  configuration package:</span></span>

    - <span data-ttu-id="6df76-140">Kopieren von _"AtpConfiguration.admx"_ in _"C: \\ Windows \\ PolicyDefinitions"_</span><span class="sxs-lookup"><span data-stu-id="6df76-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="6df76-141">Kopieren von _"AtpConfiguration.adml"_ in _"C: \\ Windows \\ PolicyDefinitions \\ en-US"_</span><span class="sxs-lookup"><span data-stu-id="6df76-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="6df76-142">Wenn Sie eine [zentrale Store für administrative Gruppenrichtlinienvorlagen](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)verwenden, kopieren Sie die folgenden Dateien aus dem Konfigurationspaket:</span><span class="sxs-lookup"><span data-stu-id="6df76-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the  configuration package:</span></span>

    - <span data-ttu-id="6df76-143">Kopieren von _"AtpConfiguration.admx"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions"_</span><span class="sxs-lookup"><span data-stu-id="6df76-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="6df76-144">Kopieren von _"AtpConfiguration.adml"_ in _\\ \\ \<forest.root\> \\ "SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US"_</span><span class="sxs-lookup"><span data-stu-id="6df76-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2. <span data-ttu-id="6df76-145">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)klicken Sie mit der rechten Maustaste auf das gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="6df76-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3. <span data-ttu-id="6df76-146">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="6df76-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4. <span data-ttu-id="6df76-147">Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="6df76-147">Click **Policies**, then **Administrative templates**.</span></span>

5. <span data-ttu-id="6df76-148">Klicken Sie auf **Windows Komponenten,** und **Windows Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="6df76-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6. <span data-ttu-id="6df76-149">Wählen Sie aus, ob Sie die Beispielfreigabe auf Ihren Geräten aktivieren oder deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6df76-149">Choose to enable or disable sample sharing from your devices.</span></span>

> [!NOTE]
> <span data-ttu-id="6df76-150">Wenn Sie keinen Wert festlegen, wird standardmäßig die Beispielsammlung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6df76-150">If you don't set a value, the default value is to enable sample collection.</span></span>

## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="6df76-151">Andere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="6df76-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="6df76-152">Aktualisieren der Endpunktschutzkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6df76-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="6df76-153">Fahren Sie nach dem Konfigurieren des Onboardingskripts mit der Bearbeitung derselben Gruppenrichtlinie fort, um Endpunktschutzkonfigurationen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6df76-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="6df76-154">Durchführen von Gruppenrichtlinienbearbeitungen von einem System, auf dem Windows 10 oder Server 2019 ausgeführt wird, um sicherzustellen, dass Sie über alle erforderlichen Microsoft Defender Antivirus Funktionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="6df76-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="6df76-155">Möglicherweise müssen Sie das Gruppenrichtlinienobjekt schließen und erneut öffnen, um die Defender ATP-Konfigurationseinstellungen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="6df76-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="6df76-156">Alle Richtlinien befinden sich unter `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="6df76-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="6df76-157">**Richtlinienspeicherort:** \Windows-Komponenten\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6df76-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="6df76-158">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-158">Policy</span></span> | <span data-ttu-id="6df76-159">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-159">Setting</span></span>
:---|:---
<span data-ttu-id="6df76-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="6df76-160">Enable\Disable Sample collection</span></span>| <span data-ttu-id="6df76-161">Aktiviert – "Beispielsammlung auf Computern aktivieren" aktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br>

<span data-ttu-id="6df76-162">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="6df76-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="6df76-163">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-163">Policy</span></span> | <span data-ttu-id="6df76-164">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-164">Setting</span></span>
:---|:---
<span data-ttu-id="6df76-165">Konfigurieren der Erkennung für potenziell unerwünschte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6df76-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="6df76-166">Aktiviert, Blockieren</span><span class="sxs-lookup"><span data-stu-id="6df76-166">Enabled, Block</span></span>

<br>

<span data-ttu-id="6df76-167">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="6df76-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="6df76-168">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-168">Policy</span></span> | <span data-ttu-id="6df76-169">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-169">Setting</span></span>
:---|:---
<span data-ttu-id="6df76-170">Microsoft MAPS beitreten</span><span class="sxs-lookup"><span data-stu-id="6df76-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="6df76-171">Aktiviert, Erweiterte KARTEN</span><span class="sxs-lookup"><span data-stu-id="6df76-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="6df76-172">Senden von Dateibeispielen, wenn eine weitere Analyse erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="6df76-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="6df76-173">Aktiviert, Sichere Beispiele senden</span><span class="sxs-lookup"><span data-stu-id="6df76-173">Enabled, Send safe samples</span></span>

<br>

<span data-ttu-id="6df76-174">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="6df76-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="6df76-175">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-175">Policy</span></span> | <span data-ttu-id="6df76-176">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-176">Setting</span></span>
:---|:---
<span data-ttu-id="6df76-177">Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="6df76-177">Turn off real-time protection</span></span>|<span data-ttu-id="6df76-178">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-178">Disabled</span></span>
<span data-ttu-id="6df76-179">Aktivieren der Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="6df76-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="6df76-180">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-180">Enabled</span></span>
<span data-ttu-id="6df76-181">Scannen aller heruntergeladenen Dateien und Anlagen</span><span class="sxs-lookup"><span data-stu-id="6df76-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="6df76-182">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-182">Enabled</span></span>
<span data-ttu-id="6df76-183">Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="6df76-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="6df76-184">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-184">Enabled</span></span>

<br>

<span data-ttu-id="6df76-185">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Scan</span><span class="sxs-lookup"><span data-stu-id="6df76-185">**Policy location:**  \Windows Components\Microsoft Defender Antivirus\Scan</span></span>

<span data-ttu-id="6df76-186">Diese Einstellungen konfigurieren regelmäßige Scans des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="6df76-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="6df76-187">Es wird empfohlen, einen wöchentlichen Schnellscan durchzuführen, der die Leistung zulässt.</span><span class="sxs-lookup"><span data-stu-id="6df76-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="6df76-188">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-188">Policy</span></span> | <span data-ttu-id="6df76-189">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-189">Setting</span></span> 
:---|:---
<span data-ttu-id="6df76-190">Überprüfen Sie die neuesten Informationen zur Viren- und Spywaresicherheit, bevor Sie einen geplanten Scan ausführen.</span><span class="sxs-lookup"><span data-stu-id="6df76-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="6df76-191">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="6df76-191">Enabled</span></span>

<br>

<span data-ttu-id="6df76-192">**Richtlinienspeicherort:** \Windows-Komponenten\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="6df76-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="6df76-193">Abrufen der aktuellen Liste der GUIDs zur Verringerung der Angriffsfläche aus der Anpassung der Regeln zur Verringerung der [Angriffsfläche](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="6df76-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="6df76-194">Öffnen Sie die **Richtlinie "Attack Surface Reduction konfigurieren".**</span><span class="sxs-lookup"><span data-stu-id="6df76-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="6df76-195">Wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="6df76-196">Wählen Sie die Schaltfläche **"Anzeigen"** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="6df76-197">Fügen Sie jede GUID im **Feld Wertname** mit dem Wert 2 hinzu.</span><span class="sxs-lookup"><span data-stu-id="6df76-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="6df76-198">Dadurch wird jede nur für die Überwachung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="6df76-198">This will set each up for audit only.</span></span>

   ![Abbildung der Attack Surface Reduction-Konfiguration](images/asr-guid.png)

<span data-ttu-id="6df76-200">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6df76-200">Policy</span></span> | <span data-ttu-id="6df76-201">Setting</span><span class="sxs-lookup"><span data-stu-id="6df76-201">Setting</span></span>
:---|:---
<span data-ttu-id="6df76-202">Konfigurieren des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="6df76-202">Configure Controlled folder access</span></span>| <span data-ttu-id="6df76-203">Aktiviert, Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="6df76-203">Enabled, Audit Mode</span></span>

## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="6df76-204">Offboarding von Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6df76-204">Offboard devices using Group Policy</span></span>

<span data-ttu-id="6df76-205">Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6df76-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="6df76-206">Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="6df76-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="6df76-207">Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="6df76-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="6df76-208">Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.</span><span class="sxs-lookup"><span data-stu-id="6df76-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="6df76-209">Rufen Sie das Offboarding-Paket aus [Microsoft 365 Defender Portal](https://security.microsoft.com/)ab:</span><span class="sxs-lookup"><span data-stu-id="6df76-209">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="6df76-210">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Device Management**  >  **Offboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-210">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Offboarding**.</span></span>

    1. <span data-ttu-id="6df76-211">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-211">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="6df76-212">Wählen Sie im Feld **"Bereitstellungsmethode"** **die Gruppenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6df76-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="6df76-213">Klicken Sie auf **"Paket herunterladen",** und speichern Sie die .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="6df76-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="6df76-214">Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="6df76-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="6df76-215">Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="6df76-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="6df76-216">Öffnen Sie die [Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console,](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt (Group Policy Object, GPO), das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="6df76-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="6df76-217">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **"Computerkonfiguration",** **"Einstellungen"** und dann **"Systemsteuerungseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="6df76-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="6df76-218">Klicken Sie mit der rechten Maustaste auf **geplante Vorgänge,** zeigen Sie auf **Neu,** und klicken Sie dann auf **"Sofortvorgang".**</span><span class="sxs-lookup"><span data-stu-id="6df76-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="6df76-219">Wechseln Sie im geöffneten **Aufgabenfenster** zur Registerkarte **"Allgemein".** Wählen Sie das lokale SYSTEM-Benutzerkonto (BUILTIN\SYSTEM) unter **"Sicherheitsoptionen" aus.**</span><span class="sxs-lookup"><span data-stu-id="6df76-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="6df76-220">Wählen Sie **"Ausführen" aus, ob der Benutzer angemeldet ist oder nicht,** und aktivieren Sie das Kontrollkästchen **"Ausführen mit den höchsten Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="6df76-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="6df76-221">Wechseln Sie zur Registerkarte **"Aktionen",** und klicken Sie auf **"Neu"...**. Stellen Sie sicher, dass **"Programm starten"** im Feld **"Aktion"** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="6df76-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="6df76-222">Geben Sie den NetBIOS-Pfad der freigegebenen *Datei WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* ein.</span><span class="sxs-lookup"><span data-stu-id="6df76-222">Enter the NetBIOS path of the shared *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="6df76-223">Klicken Sie auf **"OK",** und schließen Sie alle geöffneten GPMC-Fenster.</span><span class="sxs-lookup"><span data-stu-id="6df76-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6df76-224">Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="6df76-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="monitor-device-configuration"></a><span data-ttu-id="6df76-225">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="6df76-225">Monitor device configuration</span></span>

<span data-ttu-id="6df76-226">Bei Gruppenrichtlinien gibt es keine Option zum Überwachen der Bereitstellung von Richtlinien auf den Geräten.</span><span class="sxs-lookup"><span data-stu-id="6df76-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="6df76-227">Die Überwachung kann direkt im Portal oder mithilfe der verschiedenen Bereitstellungstools erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6df76-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="6df76-228">Überwachen von Geräten mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="6df76-228">Monitor devices using the portal</span></span>

1. <span data-ttu-id="6df76-229">Wechseln Sie zu [Microsoft 365 Defender Portal.](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6df76-229">Go to [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>
2. <span data-ttu-id="6df76-230">Klicken Sie auf **"Gerätebestand".**</span><span class="sxs-lookup"><span data-stu-id="6df76-230">Click **Devices inventory**.</span></span>
3. <span data-ttu-id="6df76-231">Stellen Sie sicher, dass Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6df76-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="6df76-232">Es kann mehrere Tage dauern, bis Geräte in der Geräteliste angezeigt **werden.**</span><span class="sxs-lookup"><span data-stu-id="6df76-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="6df76-233">Dies umfasst die Zeit, die es dauert, bis die Richtlinien auf das Gerät verteilt werden, die Zeit, bis sich der Benutzer anmeldet, und die Zeit, die der Endpunkt benötigt, um mit der Berichterstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6df76-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6df76-234">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6df76-234">Related topics</span></span>

- [<span data-ttu-id="6df76-235">Onboarding von Windows 10 Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6df76-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="6df76-236">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="6df76-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="6df76-237">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="6df76-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="6df76-238">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="6df76-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="6df76-239">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="6df76-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="6df76-240">Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten</span><span class="sxs-lookup"><span data-stu-id="6df76-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
