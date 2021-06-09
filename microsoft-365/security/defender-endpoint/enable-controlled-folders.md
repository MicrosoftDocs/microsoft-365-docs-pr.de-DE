---
title: Kontrollierte Ordnerzugriff aktivieren
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, schützen, Dateien, Ordner, aktivieren, aktivieren, aktivieren, verwenden
description: Erfahren Sie, wie Sie Ihre wichtigen Dateien schützen, indem Sie den kontrollierten Ordnerzugriff aktivieren.
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841978"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="cae73-104">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="cae73-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cae73-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cae73-105">**Applies to:**</span></span>
- [<span data-ttu-id="cae73-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cae73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cae73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cae73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cae73-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="cae73-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cae73-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cae73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="cae73-110">[Der kontrollierte Ordnerzugriff](controlled-folders.md) hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen.</span><span class="sxs-lookup"><span data-stu-id="cae73-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="cae73-111">Der kontrollierte Ordnerzugriff ist in Windows 10 und Windows Server 2019 enthalten.</span><span class="sxs-lookup"><span data-stu-id="cae73-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="cae73-112">Sie können den kontrollierten Ordnerzugriff mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="cae73-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="cae73-113">Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="cae73-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="cae73-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cae73-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="cae73-115">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="cae73-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="cae73-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cae73-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="cae73-117">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cae73-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="cae73-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae73-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="cae73-119">Im [Überwachungsmodus](evaluate-controlled-folder-access.md) können Sie testen, wie das Feature funktioniert (und Ereignisse überprüfen), ohne die normale Verwendung des Geräts zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="cae73-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="cae73-120">Gruppenrichtlinieneinstellungen, die das Zusammenführen von lokalen Administratorlisten deaktivieren, setzen die Einstellungen für den kontrollierten Ordnerzugriff außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="cae73-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="cae73-121">Sie setzen auch geschützte Ordner und zulässige Apps außer Kraft, die vom lokalen Administrator durch kontrollierten Ordnerzugriff festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="cae73-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="cae73-122">Zu diesen Richtlinien gehören:</span><span class="sxs-lookup"><span data-stu-id="cae73-122">These policies include:</span></span>

* <span data-ttu-id="cae73-123">Microsoft Defender Antivirus Konfigurieren **des Zusammenführungsverhaltens lokaler Administratoren für Listen**</span><span class="sxs-lookup"><span data-stu-id="cae73-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="cae73-124">System Center Endpoint Protection Benutzern **das Hinzufügen von Ausschlüssen und Außerkraftsetzungen gestatten**</span><span class="sxs-lookup"><span data-stu-id="cae73-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="cae73-125">Weitere Informationen zum Deaktivieren der lokalen Listenzusammenführung finden Sie unter "Verhindern oder Zulassen der lokalen Änderung von [Microsoft Defender AV-Richtlinieneinstellungen durch Benutzer".](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="cae73-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="cae73-126">Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="cae73-126">Windows Security app</span></span>

1. <span data-ttu-id="cae73-127">Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="cae73-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="cae73-128">Sie können auch das Startmenü nach **Defender** durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="cae73-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="cae73-129">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="cae73-130">Legen Sie den Schalter für **den kontrollierten Ordnerzugriff** auf **"Ein"** fest.</span><span class="sxs-lookup"><span data-stu-id="cae73-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="cae73-131">Wenn der kontrollierte Ordnerzugriff mit Gruppenrichtlinien, PowerShell oder MDM-CSPs konfiguriert ist, ändert sich der Status in der Windows-Sicherheit-App nach einem Neustart des Geräts.</span><span class="sxs-lookup"><span data-stu-id="cae73-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="cae73-132">Wenn das Feature mit einem dieser Tools auf den **Überwachungsmodus** festgelegt ist, zeigt die Windows-Sicherheit App den Status **"Aus"** an.</span><span class="sxs-lookup"><span data-stu-id="cae73-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="cae73-133">Wenn Sie Benutzerprofildaten schützen, wird empfohlen, dass sich das Benutzerprofil auf dem Standardmäßigen Windows Installationslaufwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="cae73-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="cae73-134">Intune</span><span class="sxs-lookup"><span data-stu-id="cae73-134">Intune</span></span>

1. <span data-ttu-id="cae73-135">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an, und öffnen Sie Intune.</span><span class="sxs-lookup"><span data-stu-id="cae73-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="cae73-136">Wechseln Sie zu **"Gerätekonfigurationsprofile**  >    >  **erstellen".**</span><span class="sxs-lookup"><span data-stu-id="cae73-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="cae73-137">Benennen Sie das Profil, wählen Sie **Windows 10 und höher und** **Endpunktschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="cae73-138">![Erstellen eines Endpunktschutzprofils](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="cae73-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="cae73-139">Wechseln **Sie** zu Configure  >  **Windows Defender Exploit Guard**  >  **Controlled folder access**  >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="cae73-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="cae73-140">Geben Sie den Pfad zu jeder Anwendung ein, die Zugriff auf geschützte Ordner hat, und den Pfad zu allen zusätzlichen Ordnern, die Schutz benötigen.</span><span class="sxs-lookup"><span data-stu-id="cae73-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="cae73-141">Wählen Sie **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cae73-141">Select **Add**.</span></span><br/> <span data-ttu-id="cae73-142">![Aktivieren des kontrollierten Ordnerzugriffs in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="cae73-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="cae73-143">Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cae73-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="cae73-144">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="cae73-144">Subfolders are not protected.</span></span> <span data-ttu-id="cae73-145">Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="cae73-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="cae73-146">Klicken Sie auf **"OK",** um jedes geöffnete Blatt zu speichern und **zu erstellen.**</span><span class="sxs-lookup"><span data-stu-id="cae73-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="cae73-147">Wählen Sie die **Profilzuweisungen aus,** weisen Sie **alle Benutzer & Alle Geräte** zu, und speichern **Sie**.</span><span class="sxs-lookup"><span data-stu-id="cae73-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="cae73-148">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="cae73-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="cae73-149">Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cae73-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="cae73-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cae73-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="cae73-151">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="cae73-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="cae73-152">Wählen Sie **"Home**  >  **Create Exploit Guard Policy" aus.**</span><span class="sxs-lookup"><span data-stu-id="cae73-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="cae73-153">Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **"Kontrollierter Ordnerzugriff"** aus, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="cae73-154">Wählen Sie aus, ob Änderungen blockiert oder überwacht werden sollen, andere Apps zulassen oder andere Ordner hinzufügen, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="cae73-155">Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cae73-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="cae73-156">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="cae73-156">Subfolders are not protected.</span></span> <span data-ttu-id="cae73-157">Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="cae73-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="cae73-158">Überprüfen Sie die Einstellungen, und wählen Sie **"Weiter"** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cae73-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="cae73-159">Nachdem die Richtlinie erstellt wurde, **schließen Sie**.</span><span class="sxs-lookup"><span data-stu-id="cae73-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="cae73-160">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cae73-160">Group Policy</span></span>

1. <span data-ttu-id="cae73-161">Öffnen Sie auf Ihrem Gerät für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="cae73-162">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="cae73-163">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Windows Defender Exploit Guard > kontrollierten Ordnerzugriff.**</span><span class="sxs-lookup"><span data-stu-id="cae73-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="cae73-164">Doppelklicken Sie auf die Einstellung **"Kontrollierten Ordnerzugriff konfigurieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="cae73-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="cae73-165">Im Abschnitt "Optionen" müssen Sie eine der folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="cae73-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="cae73-166">**Aktivieren –** Schädliche und verdächtige Apps dürfen keine Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cae73-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="cae73-167">Eine Benachrichtigung wird im Windows Ereignisprotokoll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cae73-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="cae73-168">**Deaktivieren (Standard)** – Das Feature für den kontrollierten Ordnerzugriff funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="cae73-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="cae73-169">Alle Apps können Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cae73-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="cae73-170">**Überwachungsmodus:** Änderungen sind zulässig, wenn eine schädliche oder verdächtige App versucht, eine Änderung an einer Datei in einem geschützten Ordner vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cae73-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="cae73-171">Es wird jedoch im Windows Ereignisprotokoll aufgezeichnet, in dem Sie die Auswirkungen auf Ihre Organisation bewerten können.</span><span class="sxs-lookup"><span data-stu-id="cae73-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="cae73-172">**Nur Datenträgeränderung blockieren** – Versuche nicht vertrauenswürdiger Apps, in Datenträgerbereiche zu schreiben, werden Windows Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="cae73-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="cae73-173">Diese Protokolle finden Sie in **den Anwendungs- und Dienstprotokollen** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="cae73-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="cae73-174">**Nur Datenträgeränderung überwachen** – Nur Versuche, in geschützte Datenträgerbereiche zu schreiben, werden im ereignisprotokoll Windows aufgezeichnet (unter **Anwendungs- und Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **Betriebs-ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="cae73-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="cae73-175">Versuche, Dateien in geschützten Ordnern zu ändern oder zu löschen, werden nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cae73-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Screenshot der in der Dropdownliste ausgewählten Gruppenrichtlinienoption "Aktiviert" und "Überwachungsmodus"](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="cae73-177">Um den kontrollierten Ordnerzugriff vollständig zu aktivieren, müssen Sie die Gruppenrichtlinienoption auf **"Aktiviert"** festlegen und im Dropdownmenü "Optionen" die Option **"Blockieren"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="cae73-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="cae73-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae73-178">PowerShell</span></span>

1. <span data-ttu-id="cae73-179">Geben Sie **powershell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="cae73-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="cae73-180">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="cae73-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="cae73-181">Sie können das Feature im Überwachungsmodus aktivieren, indem Sie `AuditMode` anstelle von `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="cae73-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="cae73-182">Wird `Disabled` verwendet, um das Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cae73-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="cae73-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cae73-183">See also</span></span>

* [<span data-ttu-id="cae73-184">Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="cae73-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="cae73-185">Kontrollierte Ordnerzugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="cae73-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="cae73-186">Auswerten des Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cae73-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
