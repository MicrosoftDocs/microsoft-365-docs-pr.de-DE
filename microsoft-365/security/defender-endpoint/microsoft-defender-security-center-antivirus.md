---
title: Microsoft Defender Antivirus in der Windows-Sicherheit App
description: Mit Microsoft Defender Antivirus, die jetzt in der Windows-Sicherheit-App enthalten sind, können Sie allgemeine Aufgaben überprüfen, vergleichen und ausführen.
keywords: wdav, antivirus, firewall, security, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275408"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="06f17-104">Microsoft Defender Antivirus in der Windows-Sicherheit App</span><span class="sxs-lookup"><span data-stu-id="06f17-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06f17-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="06f17-105">**Applies to:**</span></span>

- [<span data-ttu-id="06f17-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="06f17-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="06f17-107">In Windows 10 Version 1703 und höher ist die Windows Defender-App Teil der Windows-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="06f17-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="06f17-108">Einstellungen, die zuvor Teil des Windows Defender- und Hauptclients Windows Einstellungen waren, wurden kombiniert und in die neue App verschoben, die standardmäßig als Teil von Windows 10, Version 1703, installiert ist.</span><span class="sxs-lookup"><span data-stu-id="06f17-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06f17-109">Das Deaktivieren des Windows-Sicherheit Center-Diensts deaktiviert nicht Microsoft Defender Antivirus oder [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="06f17-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="06f17-110">Diese werden automatisch deaktiviert, wenn ein Antiviren- oder Firewallprodukt eines Drittanbieters installiert und auf dem neuesten Stand gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="06f17-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="06f17-111">Wenn Sie den Windows-Sicherheit Center-Dienst deaktivieren oder die zugehörigen Gruppenrichtlinieneinstellungen so konfigurieren, dass er nicht gestartet oder ausgeführt wird, zeigt die Windows-Sicherheit-App möglicherweise veraltete oder ungenaue Informationen zu Antiviren- oder Firewallprodukten an, die Sie auf dem Gerät installiert haben.</span><span class="sxs-lookup"><span data-stu-id="06f17-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="06f17-112">Es kann auch verhindern, Microsoft Defender Antivirus, sich selbst zu aktivieren, wenn Sie über einen alten oder veralteten Antivirenprogramm eines Drittanbieters verfügen oder wenn Sie Antivirenprodukte von Drittanbietern deinstallieren, die Sie möglicherweise zuvor installiert haben.</span><span class="sxs-lookup"><span data-stu-id="06f17-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="06f17-113">Dies verringert den Schutz Ihres Geräts erheblich und kann zu einer Schadsoftwareinfektion führen.</span><span class="sxs-lookup"><span data-stu-id="06f17-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="06f17-114">Weitere Informationen zu Windows-Sicherheit Sicherheitsfeatures, die in der App überwacht werden können Windows finden Sie im Artikel Windows-Sicherheit. [](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="06f17-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="06f17-115">Die Windows-Sicherheit-App ist eine Clientschnittstelle auf Windows 10 Version 1703 und höher.</span><span class="sxs-lookup"><span data-stu-id="06f17-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="06f17-116">Es ist nicht das Microsoft Defender Security Center, das zum Überprüfen und Verwalten von [Microsoft Defender for Endpoint verwendet wird.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="06f17-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="06f17-117">Überprüfen der Viren- und Bedrohungsschutzeinstellungen in Windows-Sicherheit App</span><span class="sxs-lookup"><span data-stu-id="06f17-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="06f17-119">Öffnen Sie Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="06f17-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="06f17-120">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="06f17-121">In den folgenden Abschnitten wird beschrieben, wie Sie einige der am häufigsten verwendeten Aufgaben beim Überprüfen oder Interagieren mit dem bedrohungsschutz ausführen, der von Microsoft Defender Antivirus in der Windows-Sicherheit bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="06f17-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="06f17-122">Wenn diese Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen ausgegraut und für die Verwendung auf einzelnen Endpunkten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06f17-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="06f17-123">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="06f17-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="06f17-124">Im [Thema Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) wird beschrieben, wie Lokale Richtlinienüberschreibungseinstellungen konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="06f17-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="06f17-125">Ausführen einer Überprüfung mit der Windows-Sicherheit App</span><span class="sxs-lookup"><span data-stu-id="06f17-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="06f17-126">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach **Sicherheit** suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-127">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-128">Wählen Sie **Schnellscan aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-128">Select **Quick scan**.</span></span> <span data-ttu-id="06f17-129">Wenn Sie einen vollständigen Scan ausführen möchten, wählen Sie **Scanoptionen** aus, und wählen Sie dann eine Option aus, z. B. **Vollständige Überprüfung.**</span><span class="sxs-lookup"><span data-stu-id="06f17-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="06f17-130">Überprüfen Sie die Version des Security Intelligence-Updates, und laden Sie die neuesten Updates in der Windows-Sicherheit herunter</span><span class="sxs-lookup"><span data-stu-id="06f17-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Informationen zur Versionsnummer der Sicherheitsintelligenz](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="06f17-132">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-133">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-134">Wählen **Sie Virenschutzupdates & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="06f17-135">Die aktuell installierte Version wird zusammen mit einigen Informationen zum Download angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06f17-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="06f17-136">Sie können Ihre aktuelle Version mit der neuesten Version überprüfen, die für den manuellen Download verfügbar ist, oder das Änderungsprotokoll für diese Version überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06f17-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="06f17-137">Weitere Informationen finden Sie unter Security [Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="06f17-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="06f17-138">Wählen **Sie Nach Updates suchen aus,** um neue Schutzupdates herunterzuladen (sofern verfügbar).</span><span class="sxs-lookup"><span data-stu-id="06f17-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="06f17-139">Sicherstellen, Microsoft Defender Antivirus in der app aktiviert Windows-Sicherheit ist</span><span class="sxs-lookup"><span data-stu-id="06f17-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="06f17-140">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-141">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-142">Wählen **Sie Virenschutzeinstellungen & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="06f17-143">Umschalten Sie **die Option Echtzeitschutz** auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="06f17-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06f17-144">Wenn Sie den **Echtzeitschutz deaktivieren,** wird er nach kurzer Verzögerung automatisch wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="06f17-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="06f17-145">Dadurch wird sichergestellt, dass Sie vor Schadsoftware und Bedrohungen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="06f17-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="06f17-146">Wenn Sie ein anderes Antivirenprodukt installieren, Microsoft Defender Antivirus automatisch selbst deaktiviert und wird als solches in der Windows-Sicherheit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06f17-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="06f17-147">Es wird eine Einstellung angezeigt, mit der Sie eine eingeschränkte regelmäßige [Überprüfung aktivieren können.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="06f17-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="06f17-148">Hinzufügen von Ausschlüssen für Microsoft Defender Antivirus in der Windows-Sicherheit App</span><span class="sxs-lookup"><span data-stu-id="06f17-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="06f17-149">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-150">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-151">Wählen Sie **unter Einstellungen verwalten** die Option **Virenschutz & Bedrohungsschutzeinstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="06f17-152">Wählen Sie unter der Einstellung **Ausschlüsse** die Option **Ausschlüsse hinzufügen oder entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="06f17-153">Wählen Sie das Plussymbol ( **+** ) aus, um den Typ auszuwählen und die Optionen für jeden Ausschluss festlegen.</span><span class="sxs-lookup"><span data-stu-id="06f17-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="06f17-154">In der folgenden Tabelle werden Ausschlusstypen und die folgenden Schritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="06f17-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="06f17-155">Ausschlusstyp</span><span class="sxs-lookup"><span data-stu-id="06f17-155">Exclusion type</span></span>  |<span data-ttu-id="06f17-156">Definiert durch</span><span class="sxs-lookup"><span data-stu-id="06f17-156">Defined by</span></span>  |<span data-ttu-id="06f17-157">Aktionen</span><span class="sxs-lookup"><span data-stu-id="06f17-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="06f17-158">**Datei**</span><span class="sxs-lookup"><span data-stu-id="06f17-158">**File**</span></span> |<span data-ttu-id="06f17-159">Speicherort</span><span class="sxs-lookup"><span data-stu-id="06f17-159">Location</span></span> <br/><span data-ttu-id="06f17-160">Beispiel: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="06f17-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="06f17-161">Die spezifische Datei wird von der Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="06f17-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="06f17-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="06f17-162">**Folder**</span></span>    |<span data-ttu-id="06f17-163">Speicherort</span><span class="sxs-lookup"><span data-stu-id="06f17-163">Location</span></span> <br/><span data-ttu-id="06f17-164">Beispiel: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="06f17-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="06f17-165">Alle Elemente im angegebenen Ordner werden von der Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="06f17-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="06f17-166">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="06f17-166">**File type**</span></span>   |<span data-ttu-id="06f17-167">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="06f17-167">File extension</span></span> <br/><span data-ttu-id="06f17-168">Beispiel: `.test`</span><span class="sxs-lookup"><span data-stu-id="06f17-168">Example: `.test`</span></span> |<span data-ttu-id="06f17-169">Alle Dateien mit der Erweiterung an einer beliebigen Stelle auf Ihrem Gerät werden `.test` von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="06f17-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="06f17-170">**Prozess**</span><span class="sxs-lookup"><span data-stu-id="06f17-170">**Process**</span></span>     |<span data-ttu-id="06f17-171">Pfad der ausführbaren Datei</span><span class="sxs-lookup"><span data-stu-id="06f17-171">Executable file path</span></span> <br><span data-ttu-id="06f17-172">Beispiel: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="06f17-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="06f17-173">Der spezifische Prozess und alle Dateien, die von diesem Prozess geöffnet werden, werden von der Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="06f17-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="06f17-174">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="06f17-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="06f17-175">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="06f17-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="06f17-176">Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="06f17-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="06f17-177">Überprüfen des Verlaufs der Bedrohungserkennung in Windows Defender Security Center-App</span><span class="sxs-lookup"><span data-stu-id="06f17-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="06f17-178">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-179">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-180">Wählen **Sie Schutzverlauf aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-180">Select **Protection history**.</span></span> <span data-ttu-id="06f17-181">Alle zuletzt verwendeten Elemente werden aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="06f17-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="06f17-182">Festlegen von Schutz- und Wiederherstellungsoptionen für Ransomware</span><span class="sxs-lookup"><span data-stu-id="06f17-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="06f17-183">Öffnen Sie Windows-Sicherheit App, indem Sie im Startmenü nach *Sicherheit* suchen und dann **Windows-Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="06f17-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="06f17-184">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus.</span><span class="sxs-lookup"><span data-stu-id="06f17-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="06f17-185">Wählen **Sie unter Ransomware-Schutz** die Option **Ransomware-Schutz verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="06f17-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="06f17-186">Informationen zum **Ändern der Einstellungen für den kontrollierten** Ordnerzugriff finden Sie unter Schützen wichtiger Ordner mit [kontrolliertem Ordnerzugriff.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="06f17-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="06f17-187">Zum Einrichten von Ransomware-Wiederherstellungsoptionen wählen Sie Unter **Ransomware** Datenwiederherstellung einrichten aus, und folgen Sie den Anweisungen zum Verknüpfen oder Einrichten Ihres OneDrive-Kontos, damit Sie sich problemlos von einem Ransomware-Angriff wiederherstellen können. </span><span class="sxs-lookup"><span data-stu-id="06f17-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="06f17-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06f17-188">See also</span></span>
- [<span data-ttu-id="06f17-189">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="06f17-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)