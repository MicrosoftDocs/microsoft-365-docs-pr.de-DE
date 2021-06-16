---
title: Microsoft Defender Antivirus in der Windows-Sicherheit-App
description: Da Microsoft Defender Antivirus jetzt in der Windows-Sicherheit App enthalten ist, können Sie allgemeine Aufgaben überprüfen, vergleichen und ausführen.
keywords: Wdav, Antivirus, Firewall, Sicherheit, Fenster
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 48ab72e9700e45cd4eab520a43d6f3d9ef18e227
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926535"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="7d7d0-104">Microsoft Defender Antivirus in der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="7d7d0-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d7d0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-105">**Applies to:**</span></span>

- [<span data-ttu-id="7d7d0-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7d7d0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7d7d0-107">In Windows 10, Version 1703 und höher, ist die Windows Defender-App Teil des Windows-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="7d7d0-108">Einstellungen, die zuvor Teil des Windows Defender-Clients und haupt-Windows Einstellungen waren, wurden kombiniert und in die neue App verschoben, die standardmäßig als Teil von Windows 10, Version 1703, installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d7d0-109">Durch das Deaktivieren des Windows-Sicherheit Center-Diensts wird Microsoft Defender Antivirus oder [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="7d7d0-110">Diese werden automatisch deaktiviert, wenn ein Antiviren- oder Firewallprodukt eines Drittanbieters installiert und auf dem neuesten Stand gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="7d7d0-111">Wenn Sie den Windows-Sicherheit Center-Dienst deaktivieren oder die zugehörigen Gruppenrichtlinieneinstellungen konfigurieren, um zu verhindern, dass er gestartet oder ausgeführt wird, zeigt die Windows-Sicherheit App möglicherweise veraltete oder ungenaue Informationen zu antiviren- oder Firewallprodukten an, die Sie auf dem Gerät installiert haben.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="7d7d0-112">Es kann auch verhindern, dass Microsoft Defender Antivirus sich selbst aktiviert, wenn Sie über ein altes oder veraltetes Antivirenprogramm eines Drittanbieters verfügen oder wenn Sie Antivirenprodukte von Drittanbietern deinstallieren, die Sie möglicherweise zuvor installiert haben.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="7d7d0-113">Dies verringert den Schutz Ihres Geräts erheblich und kann zu einer Infektion mit Schadsoftware führen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="7d7d0-114">Weitere Informationen zu anderen Windows Sicherheitsfeatures, die in der App überwacht werden können, finden Sie im [artikel](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) Windows-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="7d7d0-115">Die Windows-Sicherheit-App ist eine Clientschnittstelle auf Windows 10 Version 1703 und höher.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="7d7d0-116">Es ist nicht das Microsoft Defender Security Center Webportal, das zum Überprüfen und Verwalten von [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="7d7d0-117">Überprüfen der Viren- und Bedrohungsschutzeinstellungen in der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="7d7d0-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="7d7d0-119">Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder das Startmenü nach **Defender** durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="7d7d0-120">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="7d7d0-121">In den folgenden Abschnitten wird beschrieben, wie Sie einige der gängigsten Aufgaben beim Überprüfen oder Interagieren mit dem Bedrohungsschutz ausführen, der von Microsoft Defender Antivirus in der Windows-Sicherheit-App bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="7d7d0-122">Wenn diese Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen abgeblendet und für die Verwendung auf einzelnen Endpunkten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="7d7d0-123">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="7d7d0-124">Im Thema "Konfigurieren der [Endbenutzerinteraktion mit Microsoft Defender Antivirus"](configure-end-user-interaction-microsoft-defender-antivirus.md) wird beschrieben, wie Einstellungen für die Außerkraftsetzung lokaler Richtlinien konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="7d7d0-125">Ausführen einer Überprüfung mit der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="7d7d0-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="7d7d0-126">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach **Sicherheit** suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-127">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-128">Wählen Sie **"Schnellscan"** aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-128">Select **Quick scan**.</span></span> <span data-ttu-id="7d7d0-129">Oder wählen Sie zum Ausführen eines vollständigen Scans **die Scanoptionen** aus, und wählen Sie dann eine Option aus, z. B. **vollständige Überprüfung.**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="7d7d0-130">Überprüfen Sie die Version des Security Intelligence-Updates, und laden Sie die neuesten Updates in der Windows-Sicherheit-App herunter.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Informationen zur Versionsnummer der Security Intelligence](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="7d7d0-132">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-133">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-134">Wählen Sie **Viren- & Bedrohungsschutzupdates** aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="7d7d0-135">Die aktuell installierte Version wird zusammen mit einigen Informationen darüber angezeigt, wann sie heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="7d7d0-136">Sie können Ihre aktuelle Version mit der neuesten Version abgleichen, die für den manuellen Download verfügbar ist, oder das Änderungsprotokoll für diese Version überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="7d7d0-137">Informationen [zu Microsoft Defender Antivirus und anderen Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft finden Sie unter Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="7d7d0-138">Wählen Sie **"Nach Updates suchen"** aus, um neue Schutzupdates herunterzuladen (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="7d7d0-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="7d7d0-139">Stellen Sie sicher, dass Microsoft Defender Antivirus in der Windows-Sicherheit-App aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="7d7d0-140">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-141">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-142">Wählen Sie **Einstellungen für den Viren- & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="7d7d0-143">Umschalten des **Echtzeitschutzschalters** auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d7d0-144">Wenn Sie den **Echtzeitschutz** deaktivieren, wird er nach kurzer Verzögerung automatisch wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="7d7d0-145">Dadurch wird sichergestellt, dass Sie vor Schadsoftware und Bedrohungen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="7d7d0-146">Wenn Sie ein anderes Antivirenprodukt installieren, deaktiviert Microsoft Defender Antivirus sich automatisch selbst und wird in der Windows-Sicherheit-App als solche gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="7d7d0-147">Es wird eine Einstellung angezeigt, mit der Sie [eingeschränkte regelmäßige Überprüfungen](limited-periodic-scanning-microsoft-defender-antivirus.md)aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="7d7d0-148">Hinzufügen von Ausschlüssen für Microsoft Defender Antivirus in der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="7d7d0-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="7d7d0-149">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-150">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-151">Wählen Sie unter **"Einstellungen verwalten"** **die Einstellungen für den Viren- & Bedrohungsschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="7d7d0-152">Wählen Sie unter der Einstellung **"Ausschlüsse"** die Option **"Ausschlüsse hinzufügen oder entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="7d7d0-153">Wählen Sie das Plussymbol ( **+** ) aus, um den Typ auszuwählen, und legen Sie die Optionen für jeden Ausschluss fest.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="7d7d0-154">In der folgenden Tabelle sind Ausschlusstypen zusammengefasst und was passiert:</span><span class="sxs-lookup"><span data-stu-id="7d7d0-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="7d7d0-155">Ausschlusstyp</span><span class="sxs-lookup"><span data-stu-id="7d7d0-155">Exclusion type</span></span>  |<span data-ttu-id="7d7d0-156">Definiert durch</span><span class="sxs-lookup"><span data-stu-id="7d7d0-156">Defined by</span></span>  |<span data-ttu-id="7d7d0-157">Aktionen</span><span class="sxs-lookup"><span data-stu-id="7d7d0-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7d7d0-158">**Datei**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-158">**File**</span></span> |<span data-ttu-id="7d7d0-159">Speicherort</span><span class="sxs-lookup"><span data-stu-id="7d7d0-159">Location</span></span> <br/><span data-ttu-id="7d7d0-160">Beispiel: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="7d7d0-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="7d7d0-161">Die spezifische Datei wird von Microsoft Defender Antivirus übersprungen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="7d7d0-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-162">**Folder**</span></span>    |<span data-ttu-id="7d7d0-163">Speicherort</span><span class="sxs-lookup"><span data-stu-id="7d7d0-163">Location</span></span> <br/><span data-ttu-id="7d7d0-164">Beispiel: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="7d7d0-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="7d7d0-165">Alle Elemente im angegebenen Ordner werden von Microsoft Defender Antivirus übersprungen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="7d7d0-166">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-166">**File type**</span></span>   |<span data-ttu-id="7d7d0-167">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="7d7d0-167">File extension</span></span> <br/><span data-ttu-id="7d7d0-168">Beispiel: `.test`</span><span class="sxs-lookup"><span data-stu-id="7d7d0-168">Example: `.test`</span></span> |<span data-ttu-id="7d7d0-169">Alle Dateien mit der `.test` Erweiterung an beliebiger Stelle auf Ihrem Gerät werden von Microsoft Defender Antivirus übersprungen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="7d7d0-170">**Prozess**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-170">**Process**</span></span>     |<span data-ttu-id="7d7d0-171">Pfad der ausführbaren Datei</span><span class="sxs-lookup"><span data-stu-id="7d7d0-171">Executable file path</span></span> <br><span data-ttu-id="7d7d0-172">Beispiel: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="7d7d0-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="7d7d0-173">Der spezifische Prozess und alle Dateien, die von diesem Prozess geöffnet werden, werden von Microsoft Defender Antivirus übersprungen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="7d7d0-174">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="7d7d0-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="7d7d0-175">Konfigurieren und Überprüfen von Ausschlüssen basierend auf der Dateierweiterung und dem Speicherort des Ordners</span><span class="sxs-lookup"><span data-stu-id="7d7d0-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="7d7d0-176">Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="7d7d0-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="7d7d0-177">Überprüfen des Verlaufs der Bedrohungserkennung in der Windows Defender Security Center-App</span><span class="sxs-lookup"><span data-stu-id="7d7d0-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="7d7d0-178">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-179">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-180">Wählen Sie **"Schutzverlauf" aus.**</span><span class="sxs-lookup"><span data-stu-id="7d7d0-180">Select **Protection history**.</span></span> <span data-ttu-id="7d7d0-181">Alle zuletzt verwendeten Elemente werden aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="7d7d0-182">Festlegen von Ransomware-Schutz- und Wiederherstellungsoptionen</span><span class="sxs-lookup"><span data-stu-id="7d7d0-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="7d7d0-183">Öffnen Sie die Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7d7d0-184">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7d7d0-185">Wählen Sie unter **Ransomware-Schutz** Den **Ransomware-Schutz verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="7d7d0-186">Informationen zum Ändern der Einstellungen für den **kontrollierten Ordnerzugriff** finden Sie unter ["Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff".](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="7d7d0-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="7d7d0-187">Um Ransomware-Wiederherstellungsoptionen einzurichten, wählen Sie unter **Ransomware-Datenwiederherstellung** **einrichten** aus, und folgen Sie den Anweisungen zum Verknüpfen oder Einrichten Ihres OneDrive Kontos, damit Sie sich leicht von einem Ransomware-Angriff wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="7d7d0-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d7d0-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d7d0-188">See also</span></span>
- [<span data-ttu-id="7d7d0-189">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7d7d0-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)