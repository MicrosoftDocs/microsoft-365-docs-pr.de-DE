---
title: Aktivieren des kontrollierten Ordnerzugriffs
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner, aktivieren, aktivieren, verwenden
description: Erfahren Sie, wie Sie Ihre wichtigen Dateien schützen, indem Sie den kontrollierten Ordnerzugriff aktivieren.
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218760"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="0c801-104">Aktivieren des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="0c801-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c801-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0c801-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c801-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c801-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c801-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c801-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0c801-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0c801-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c801-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0c801-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="0c801-110">[Der kontrollierte Ordnerzugriff](controlled-folders.md) hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen.</span><span class="sxs-lookup"><span data-stu-id="0c801-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="0c801-111">Der kontrollierte Ordnerzugriff ist in Windows 10 und Windows Server 2019 enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c801-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="0c801-112">Sie können den kontrollierten Ordnerzugriff mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="0c801-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="0c801-113">Windows Security App</span><span class="sxs-lookup"><span data-stu-id="0c801-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="0c801-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0c801-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="0c801-115">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="0c801-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="0c801-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c801-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="0c801-117">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0c801-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="0c801-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c801-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="0c801-119">[Im Überwachungsmodus](evaluate-controlled-folder-access.md) können Sie testen, wie das Feature funktionieren würde (und Ereignisse überprüfen), ohne sich auf die normale Verwendung des Geräts auswirken zu müssen.</span><span class="sxs-lookup"><span data-stu-id="0c801-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="0c801-120">Gruppenrichtlinieneinstellungen, die das Zusammenführen lokaler Administratorlisten deaktivieren, setzen die Einstellungen für den kontrollierten Ordnerzugriff außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="0c801-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="0c801-121">Außerdem überschreiben sie geschützte Ordner und zugelassene Apps, die vom lokalen Administrator über den kontrollierten Ordnerzugriff festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c801-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="0c801-122">Zu diesen Richtlinien gehören:</span><span class="sxs-lookup"><span data-stu-id="0c801-122">These policies include:</span></span>

* <span data-ttu-id="0c801-123">Microsoft Defender Antivirus **Konfigurieren des Zusammenführungsverhaltens lokaler Administratoren für Listen**</span><span class="sxs-lookup"><span data-stu-id="0c801-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="0c801-124">System Center Endpoint Protection **Benutzern das Hinzufügen von Ausschlüssen und Außerkraftsetzungen ermöglichen**</span><span class="sxs-lookup"><span data-stu-id="0c801-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="0c801-125">Weitere Informationen zum Deaktivieren des Zusammenführens lokaler Listen finden Sie unter [Prevent or allow users to local modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span><span class="sxs-lookup"><span data-stu-id="0c801-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="0c801-126">Windows Security App</span><span class="sxs-lookup"><span data-stu-id="0c801-126">Windows Security app</span></span>

1. <span data-ttu-id="0c801-127">Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c801-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="0c801-128">Sie können auch im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="0c801-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="0c801-129">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="0c801-130">Legen Sie die Option für **kontrollierten Ordnerzugriff auf** **Ein .**</span><span class="sxs-lookup"><span data-stu-id="0c801-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c801-131">Wenn der kontrollierte Ordnerzugriff mit Gruppenrichtlinien, PowerShell- oder MDM-CSPs konfiguriert ist, ändert sich der Status in der Windows Security-App nach einem Neustart des Geräts.</span><span class="sxs-lookup"><span data-stu-id="0c801-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="0c801-132">Wenn das Feature  mit einem dieser Tools auf den Überwachungsmodus festgelegt ist, zeigt die Windows-Sicherheits-App den Status **Aus an.**</span><span class="sxs-lookup"><span data-stu-id="0c801-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="0c801-133">Wenn Sie Benutzerprofildaten schützen, wird empfohlen, dass sich das Benutzerprofil auf dem Standardmäßigen Windows-Installationslaufwerk befinden sollte.</span><span class="sxs-lookup"><span data-stu-id="0c801-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="0c801-134">Intune</span><span class="sxs-lookup"><span data-stu-id="0c801-134">Intune</span></span>

1. <span data-ttu-id="0c801-135">Melden Sie sich beim [Azure-Portal an, und](https://portal.azure.com) öffnen Sie Intune.</span><span class="sxs-lookup"><span data-stu-id="0c801-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="0c801-136">Wechseln Sie zu **Gerätekonfigurationsprofile**  >    >  **Profil erstellen.**</span><span class="sxs-lookup"><span data-stu-id="0c801-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="0c801-137">Benennen Sie das Profil, wählen **Sie Windows 10 und höher und** Endpoint Protection **aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="0c801-138">![Erstellen eines Endpunktschutzprofils](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="0c801-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="0c801-139">Wechseln Sie **zu Configure** Windows Defender  >  **Exploit Guard** Controlled folder  >  **access**  >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="0c801-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="0c801-140">Geben Sie den Pfad zu jeder Anwendung ein, die Zugriff auf geschützte Ordner hat, und den Pfad zu jedem zusätzlichen Ordner, der Schutz benötigt.</span><span class="sxs-lookup"><span data-stu-id="0c801-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="0c801-141">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c801-141">Select **Add**.</span></span><br/> <span data-ttu-id="0c801-142">![Aktivieren des kontrollierten Ordnerzugriffs in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="0c801-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="0c801-143">Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c801-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="0c801-144">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="0c801-144">Subfolders are not protected.</span></span> <span data-ttu-id="0c801-145">Zugelassene Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c801-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="0c801-146">Wählen **Sie OK** aus, um jedes geöffnete Blatt zu speichern, und erstellen **.**</span><span class="sxs-lookup"><span data-stu-id="0c801-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="0c801-147">Wählen Sie die **Profilzuweisungen** aus, weisen **Sie allen Benutzern & Alle Geräte** zu, und speichern **.**</span><span class="sxs-lookup"><span data-stu-id="0c801-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="0c801-148">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="0c801-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0c801-149">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders-Konfigurationsdienstanbieter (CSP),](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) damit Apps Änderungen an geschützten Ordnern vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="0c801-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="0c801-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0c801-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="0c801-151">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="0c801-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="0c801-152">Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="0c801-153">Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **kontrollierten** Ordnerzugriff aus, und wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="0c801-154">Wählen Sie aus, ob Änderungen blockiert oder überwacht werden, andere Apps zulassen oder andere Ordner hinzugefügt werden, und wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0c801-155">Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c801-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="0c801-156">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="0c801-156">Subfolders are not protected.</span></span> <span data-ttu-id="0c801-157">Zugelassene Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c801-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="0c801-158">Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c801-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="0c801-159">Nachdem die Richtlinie erstellt wurde, schließen **Sie**.</span><span class="sxs-lookup"><span data-stu-id="0c801-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="0c801-160">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0c801-160">Group Policy</span></span>

1. <span data-ttu-id="0c801-161">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="0c801-162">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="0c801-163">Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Kontrollierter Ordnerzugriff**.</span><span class="sxs-lookup"><span data-stu-id="0c801-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="0c801-164">Doppelklicken Sie auf **die Einstellung Kontrollierten Ordnerzugriff** konfigurieren, und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="0c801-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="0c801-165">Im Abschnitt Optionen müssen Sie eine der folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="0c801-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="0c801-166">**Aktivieren** – Bösartige und verdächtige Apps dürfen keine Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0c801-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="0c801-167">Im Windows-Ereignisprotokoll wird eine Benachrichtigung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0c801-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="0c801-168">**Disable (Standard)** – Das Feature für den kontrollierten Ordnerzugriff funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="0c801-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="0c801-169">Alle Apps können Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0c801-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="0c801-170">**Überwachungsmodus** – Änderungen sind zulässig, wenn eine schädliche oder verdächtige App versucht, eine Datei in einem geschützten Ordner zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0c801-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="0c801-171">Sie wird jedoch im Windows-Ereignisprotokoll aufgezeichnet, in dem Sie die Auswirkungen auf Ihre Organisation bewerten können.</span><span class="sxs-lookup"><span data-stu-id="0c801-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="0c801-172">**Nur Datenträgeränderung blockieren** – Versuche nicht vertrauenswürdiger Apps, auf Datenträgersektoren zu schreiben, werden im Windows-Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="0c801-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="0c801-173">Diese Protokolle finden Sie unter **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="0c801-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="0c801-174">**Nur Datenträgeränderung** überwachen – Nur Versuche, in geschützte Datenträgersektoren zu schreiben, werden im Windows-Ereignisprotokoll aufgezeichnet (unter **Anwendungs-** und Dienstprotokolle  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**  >  **ID 1124**).</span><span class="sxs-lookup"><span data-stu-id="0c801-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="0c801-175">Versuche, Dateien in geschützten Ordnern zu ändern oder zu löschen, werden nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0c801-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Screenshot der in der Dropdownliste ausgewählten Gruppenrichtlinienoption "Aktiviert" und "Überwachungsmodus"](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="0c801-177">Um den kontrollierten Ordnerzugriff vollständig zu aktivieren, müssen Sie die Option Gruppenrichtlinie auf **Aktiviert** festlegen und **im** Dropdownmenü Optionen blockieren auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c801-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="0c801-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c801-178">PowerShell</span></span>

1. <span data-ttu-id="0c801-179">Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **Maustaste auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="0c801-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="0c801-180">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="0c801-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="0c801-181">Sie können das Feature im Überwachungsmodus aktivieren, indem Sie anstelle von `AuditMode` `Enabled` angeben.</span><span class="sxs-lookup"><span data-stu-id="0c801-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="0c801-182">Verwenden `Disabled` Sie, um das Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c801-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c801-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c801-183">See also</span></span>

* [<span data-ttu-id="0c801-184">Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="0c801-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="0c801-185">Anpassen des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="0c801-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="0c801-186">Bewerten von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c801-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
