---
title: Kontrollierte Ordnerzugriff aktivieren
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, schützen, Dateien, Ordner, aktivieren, aktivieren, aktivieren, verwenden
description: Erfahren Sie, wie Sie Ihre wichtigen Dateien schützen, indem Sie den kontrollierten Ordnerzugriff aktivieren.
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924683"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="4a488-104">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="4a488-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a488-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4a488-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a488-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4a488-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a488-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a488-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4a488-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4a488-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a488-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4a488-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4a488-110">[Der kontrollierte Ordnerzugriff](controlled-folders.md) hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4a488-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="4a488-111">Der kontrollierte Ordnerzugriff ist in Windows 10 und Windows Server 2019 enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a488-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="4a488-112">Sie können den kontrollierten Ordnerzugriff mithilfe einer der folgenden Methoden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4a488-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="4a488-113">Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="4a488-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="4a488-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4a488-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="4a488-115">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="4a488-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="4a488-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4a488-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="4a488-117">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4a488-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="4a488-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a488-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="4a488-119">Im [Überwachungsmodus](evaluate-controlled-folder-access.md) können Sie testen, wie das Feature funktioniert (und Ereignisse überprüfen), ohne die normale Verwendung des Geräts zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="4a488-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="4a488-120">Gruppenrichtlinieneinstellungen, die das Zusammenführen von lokalen Administratorlisten deaktivieren, setzen die Einstellungen für den kontrollierten Ordnerzugriff außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="4a488-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="4a488-121">Sie setzen auch geschützte Ordner und zulässige Apps außer Kraft, die vom lokalen Administrator durch kontrollierten Ordnerzugriff festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="4a488-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="4a488-122">Zu diesen Richtlinien gehören:</span><span class="sxs-lookup"><span data-stu-id="4a488-122">These policies include:</span></span>

* <span data-ttu-id="4a488-123">Microsoft Defender Antivirus **Konfigurieren des Zusammenführungsverhaltens lokaler Administratoren für Listen**</span><span class="sxs-lookup"><span data-stu-id="4a488-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="4a488-124">System Center Endpoint Protection Benutzern **das Hinzufügen von Ausschlüssen und Außerkraftsetzungen gestatten**</span><span class="sxs-lookup"><span data-stu-id="4a488-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="4a488-125">Weitere Informationen zum Deaktivieren der lokalen Listenzusammenführung finden Sie unter "Verhindern oder Zulassen der lokalen Änderung von [Microsoft Defender AV-Richtlinieneinstellungen durch Benutzer".](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="4a488-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="4a488-126">Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="4a488-126">Windows Security app</span></span>

1. <span data-ttu-id="4a488-127">Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a488-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="4a488-128">Sie können auch das Startmenü nach **Defender** durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="4a488-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="4a488-129">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="4a488-130">Legen Sie den Schalter für **den kontrollierten Ordnerzugriff** auf **"Ein"** fest.</span><span class="sxs-lookup"><span data-stu-id="4a488-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="4a488-131">Wenn der kontrollierte Ordnerzugriff mit Gruppenrichtlinien, PowerShell oder MDM-CSPs konfiguriert ist, ändert sich der Status in der Windows-Sicherheit-App nach einem Neustart des Geräts.</span><span class="sxs-lookup"><span data-stu-id="4a488-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="4a488-132">Wenn das Feature mit einem dieser Tools auf den **Überwachungsmodus** festgelegt ist, zeigt die Windows-Sicherheit App den Status **"Aus"** an.</span><span class="sxs-lookup"><span data-stu-id="4a488-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="4a488-133">Wenn Sie Benutzerprofildaten schützen, wird empfohlen, dass sich das Benutzerprofil auf dem Standard-Windows Installationslaufwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="4a488-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="4a488-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4a488-134">Endpoint Manager</span></span>

1. <span data-ttu-id="4a488-135">Melden Sie sich beim [Endpoint Manager](https://endpoint.microsoft.com) an, und öffnen Sie **Endpoint Security.**</span><span class="sxs-lookup"><span data-stu-id="4a488-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="4a488-136">Wechseln Sie zur **Attack Surface**  >  **Reduction-Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="4a488-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="4a488-137">Wählen Sie **"Plattform",** **"Windows 10" und höher** aus, und wählen Sie das Profil **"Attack Surface Reduction"-Regeln**  >  **erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="4a488-138">Benennen Sie die Richtlinie, und fügen Sie eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a488-138">Name the policy and add a description.</span></span> <span data-ttu-id="4a488-139">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-139">Select **Next**.</span></span>

5.  <span data-ttu-id="4a488-140">Scrollen Sie nach unten, wählen Sie die Dropdownliste **"Ordnerschutz aktivieren"** aus, und wählen Sie **"Aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="4a488-141">Wählen Sie **die Liste der zusätzlichen Ordner aus, die geschützt werden müssen,** und fügen Sie die Ordner hinzu, die geschützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4a488-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="4a488-142">Wählen Sie **die Liste der Apps aus, die Zugriff auf geschützte Ordner haben,** und fügen Sie die Apps hinzu, die Zugriff auf geschützte Ordner haben.</span><span class="sxs-lookup"><span data-stu-id="4a488-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="4a488-143">Wählen Sie **"Dateien und Pfade von Attack Surface Reduction-Regeln ausschließen" aus,** und fügen Sie die Dateien und Pfade hinzu, die von Attack Surface Reduction-Regeln ausgeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4a488-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="4a488-144">Wählen Sie die **Profilzuweisungen** aus, weisen Sie **alle Benutzer & Alle Geräte** zu, und wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="4a488-145">Wählen Sie **"Weiter"** aus, um jedes geöffnete Blatt zu speichern, und **erstellen Sie** dann .</span><span class="sxs-lookup"><span data-stu-id="4a488-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4a488-146">Platzhalter werden für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a488-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="4a488-147">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="4a488-147">Subfolders are not protected.</span></span> <span data-ttu-id="4a488-148">Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="4a488-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="4a488-149">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="4a488-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="4a488-150">Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4a488-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4a488-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4a488-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="4a488-152">Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="4a488-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="4a488-153">Wählen Sie **"Home**  >  **Create Exploit Guard Policy" aus.**</span><span class="sxs-lookup"><span data-stu-id="4a488-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="4a488-154">Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **"Kontrollierter Ordnerzugriff"** aus, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="4a488-155">Wählen Sie aus, ob Änderungen blockiert oder überwacht werden sollen, andere Apps zulassen oder andere Ordner hinzufügen, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4a488-156">Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a488-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="4a488-157">Unterordner sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="4a488-157">Subfolders are not protected.</span></span> <span data-ttu-id="4a488-158">Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="4a488-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="4a488-159">Überprüfen Sie die Einstellungen, und wählen Sie **"Weiter"** aus, um die Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a488-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="4a488-160">Nachdem die Richtlinie erstellt wurde, **schließen Sie**.</span><span class="sxs-lookup"><span data-stu-id="4a488-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="4a488-161">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4a488-161">Group Policy</span></span>

1. <span data-ttu-id="4a488-162">Öffnen Sie auf Ihrem Gerät für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="4a488-163">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a488-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="4a488-164">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Windows Defender Exploit Guard > kontrollierten Ordnerzugriff.**</span><span class="sxs-lookup"><span data-stu-id="4a488-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="4a488-165">Doppelklicken Sie auf die Einstellung **"Kontrollierten Ordnerzugriff konfigurieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="4a488-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4a488-166">Im Abschnitt "Optionen" müssen Sie eine der folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="4a488-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="4a488-167">**Aktivieren –** Schädliche und verdächtige Apps dürfen keine Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4a488-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="4a488-168">Eine Benachrichtigung wird im Windows Ereignisprotokoll bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4a488-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="4a488-169">**Deaktivieren (Standard)** – Das Feature für den kontrollierten Ordnerzugriff funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="4a488-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="4a488-170">Alle Apps können Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4a488-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="4a488-171">**Überwachungsmodus:** Änderungen sind zulässig, wenn eine schädliche oder verdächtige App versucht, eine Änderung an einer Datei in einem geschützten Ordner vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4a488-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="4a488-172">Es wird jedoch im Windows Ereignisprotokoll aufgezeichnet, in dem Sie die Auswirkungen auf Ihre Organisation bewerten können.</span><span class="sxs-lookup"><span data-stu-id="4a488-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="4a488-173">**Nur Datenträgeränderung blockieren** – Versuche nicht vertrauenswürdiger Apps, in Datenträgerbereiche zu schreiben, werden Windows Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4a488-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="4a488-174">Diese Protokolle finden Sie in **den Anwendungs- und Dienstprotokollen** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="4a488-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="4a488-175">**Nur Datenträgeränderung überwachen** – Nur Versuche, in geschützte Datenträgerbereiche zu schreiben, werden im Windows Ereignisprotokoll aufgezeichnet (unter **Anwendungs- und Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **Betriebs-ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="4a488-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="4a488-176">Versuche, Dateien in geschützten Ordnern zu ändern oder zu löschen, werden nicht aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4a488-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Screenshot der in der Dropdownliste ausgewählten Gruppenrichtlinienoption "Aktiviert" und "Überwachungsmodus"](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="4a488-178">Um den kontrollierten Ordnerzugriff vollständig zu aktivieren, müssen Sie die Gruppenrichtlinienoption auf **"Aktiviert"** festlegen und im Dropdownmenü "Optionen" die Option **"Blockieren"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a488-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="4a488-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a488-179">PowerShell</span></span>

1. <span data-ttu-id="4a488-180">Geben Sie **PowerShell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **Als Administrator ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="4a488-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4a488-181">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="4a488-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="4a488-182">Sie können das Feature im Überwachungsmodus aktivieren, indem Sie `AuditMode` anstelle von `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="4a488-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="4a488-183">Wird `Disabled` verwendet, um das Feature zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a488-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a488-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a488-184">See also</span></span>

* [<span data-ttu-id="4a488-185">Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="4a488-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="4a488-186">Kontrollierte Ordnerzugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="4a488-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="4a488-187">Auswerten des Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4a488-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
