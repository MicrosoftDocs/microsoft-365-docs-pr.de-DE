---
title: Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Schutzfunktionen
description: Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Echtzeitschutzfeatures wie Verhaltensüberwachung, Heuristik und maschinellem Lernen
keywords: Antivirus, Echtzeitschutz, RTP, Maschinelles Lernen, Verhaltensüberwachung, Heuristik
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 7fa4f90282bf87c1def1917037e090b213cad3db
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690326"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a><span data-ttu-id="f19f9-104">Aktivieren und Konfigurieren des immer aktivierten Microsoft Defender Antivirus-Schutzes in Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f19f9-104">Enable and configure Microsoft Defender Antivirus always-on protection in Group Policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f19f9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f19f9-105">**Applies to:**</span></span>

- [<span data-ttu-id="f19f9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f19f9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f19f9-107">Der Always-On-Schutz besteht aus Echtzeitschutz, Verhaltensüberwachung und Heuristik, um Schadsoftware basierend auf bekannten verdächtigen und schädlichen Aktivitäten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f19f9-107">Always-on protection consists of real-time protection, behavior monitoring, and heuristics to identify malware based on known suspicious and malicious activities.</span></span>

<span data-ttu-id="f19f9-108">Zu diesen Aktivitäten gehören Ereignisse, z. B. Prozesse, die ungewöhnliche Änderungen an vorhandenen Dateien vornehmen, das Ändern oder Erstellen automatischer Startregistrierungsschlüssel und Startstandorte (auch bekannt als Erweiterungspunkte für den automatischen Start oder ASEPs) sowie andere Änderungen am Dateisystem oder der Dateistruktur.</span><span class="sxs-lookup"><span data-stu-id="f19f9-108">These activities include events, such as processes making unusual changes to existing files, modifying or creating automatic startup registry keys and startup locations (also known as auto-start extensibility points, or ASEPs), and other changes to the file system or file structure.</span></span>

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a><span data-ttu-id="f19f9-109">Aktivieren und Konfigurieren des immer aktivierten Schutzes in Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f19f9-109">Enable and configure always-on protection in Group Policy</span></span>

<span data-ttu-id="f19f9-110">Sie können den **Editor für lokale Gruppenrichtlinien verwenden,** um Die Einstellungen für den immer aktivierten Schutz von Microsoft Defender Antivirus zu aktivieren und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f19f9-110">You can use **Local Group Policy Editor** to enable and configure Microsoft Defender Antivirus always-on protection settings.</span></span>

<span data-ttu-id="f19f9-111">So aktivieren und konfigurieren Sie den immer aktivierten Schutz:</span><span class="sxs-lookup"><span data-stu-id="f19f9-111">To enable and configure always-on protection:</span></span>

1. <span data-ttu-id="f19f9-112">Öffnen **Sie den Editor für lokale Gruppenrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-112">Open **Local Group Policy Editor**.</span></span> <span data-ttu-id="f19f9-113">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f19f9-113">To do this:</span></span>  

    1. <span data-ttu-id="f19f9-114">Geben Sie im Suchfeld Windows 10-Taskleiste **gpedit ein.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-114">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
    
    1. <span data-ttu-id="f19f9-115">Klicken **Sie unter Beste Übereinstimmung** auf **Gruppenrichtlinie bearbeiten,** um den Editor für **lokale Gruppenrichtlinien zu starten.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-115">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>
    
       ![GPEdit-Taskleistensuchergebnis](images/gpedit-search.png)

2. <span data-ttu-id="f19f9-117">Erweitern Sie im linken Bereich des **Editors** für lokale Gruppenrichtlinien die Struktur auf **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-117">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus**.</span></span> 

3. <span data-ttu-id="f19f9-118">Konfigurieren Sie die Microsoft Defender Antivirus-Antischasoftwaredienstrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-118">Configure the Microsoft Defender Antivirus antimalware service policy settings.</span></span> <span data-ttu-id="f19f9-119">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f19f9-119">To do this:</span></span>  

    1. <span data-ttu-id="f19f9-120">**Doppelklicken Sie im** Detailbereich von Microsoft Defender Antivirus auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="f19f9-120">In the **Microsoft Defender Antivirus** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="f19f9-121">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-121">Setting</span></span> | <span data-ttu-id="f19f9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f19f9-122">Description</span></span> | <span data-ttu-id="f19f9-123">Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-123">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="f19f9-124">Starten des Antischalwarediensts mit normaler Priorität zulassen</span><span class="sxs-lookup"><span data-stu-id="f19f9-124">Allow antimalware service to startup with normal priority</span></span> | <span data-ttu-id="f19f9-125">Sie können die Priorität des Microsoft Defender Antivirus-Moduls senken, was in einfachen Bereitstellungen nützlich sein kann, bei denen Sie einen möglichst schlanken Startprozess wünschen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-125">You can lower the priority of the Microsoft Defender Antivirus engine, which may be useful in lightweight deployments where you want to have as lean a startup process as possible.</span></span> <span data-ttu-id="f19f9-126">Dies kann sich auf den Schutz des Endpunkts auswirken.</span><span class="sxs-lookup"><span data-stu-id="f19f9-126">This may impact protection on the endpoint.</span></span> | <span data-ttu-id="f19f9-127">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-127">Enabled</span></span>
       | <span data-ttu-id="f19f9-128">Zulassen, dass der Antischalwaredienst immer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f19f9-128">Allow antimalware service to remain running always</span></span> | <span data-ttu-id="f19f9-129">Wenn Schutzupdates deaktiviert wurden, können Sie festlegen, dass Microsoft Defender Antivirus weiterhin ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f19f9-129">If protection updates have been disabled, you can set Microsoft Defender Antivirus to still run.</span></span> <span data-ttu-id="f19f9-130">Dadurch wird der Schutz auf dem Endpunkt gesenkt.</span><span class="sxs-lookup"><span data-stu-id="f19f9-130">This lowers the protection on the endpoint.</span></span> | <span data-ttu-id="f19f9-131">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-131">Disabled</span></span> |
    
    1. <span data-ttu-id="f19f9-132">Konfigurieren Sie die Einstellung entsprechend, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-132">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="f19f9-133">Wiederholen Sie die vorherigen Schritte für jede Einstellung in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f19f9-133">Repeat the previous steps for each setting in the table.</span></span>

4. <span data-ttu-id="f19f9-134">Konfigurieren Sie die Microsoft Defender Antivirus-Echtzeitschutzrichtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-134">Configure the Microsoft Defender Antivirus real-time protection policy settings.</span></span> <span data-ttu-id="f19f9-135">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f19f9-135">To do this:</span></span>

    1. <span data-ttu-id="f19f9-136">**Doppelklicken Sie im Detailbereich** von Microsoft Defender Antivirus auf **Echtzeitschutz**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-136">In the **Microsoft Defender Antivirus** details pane, double-click **Real-time Protection**.</span></span> <span data-ttu-id="f19f9-137">Oder klicken Sie in der **Microsoft Defender Antivirus-Struktur** im linken Bereich auf **Echtzeitschutz**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-137">Or, from the **Microsoft Defender Antivirus** tree on left pane, click **Real-time Protection**.</span></span>
    
    1. <span data-ttu-id="f19f9-138">Doppelklicken **Sie im** Detailbereich Echtzeitschutz auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="f19f9-138">In the **Real-time Protection** details pane on right, double-click the policy setting as specified in the following table:</span></span>  

       | <span data-ttu-id="f19f9-139">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-139">Setting</span></span> | <span data-ttu-id="f19f9-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f19f9-140">Description</span></span> | <span data-ttu-id="f19f9-141">Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-141">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|
       | <span data-ttu-id="f19f9-142">Aktivieren der Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="f19f9-142">Turn on behavior monitoring</span></span> | <span data-ttu-id="f19f9-143">Das AV-Modul überwacht Dateiprozesse, Datei- und Registrierungsänderungen und andere Ereignisse auf Ihren Endpunkten auf verdächtige und bekannte bösartige Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="f19f9-143">The AV engine will monitor file processes, file and registry changes, and other events on your endpoints for suspicious and known malicious activity.</span></span> | <span data-ttu-id="f19f9-144">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-144">Enabled</span></span> |
       | <span data-ttu-id="f19f9-145">Überprüfen aller heruntergeladenen Dateien und Anlagen</span><span class="sxs-lookup"><span data-stu-id="f19f9-145">Scan all downloaded files and attachments</span></span> | <span data-ttu-id="f19f9-146">Heruntergeladene Dateien und Anlagen werden automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="f19f9-146">Downloaded files and attachments are automatically scanned.</span></span> <span data-ttu-id="f19f9-147">Dies funktioniert zusätzlich zum Windows Defender SmartScreen-Filter, der Dateien vor und während des Herunterladens überprüft.</span><span class="sxs-lookup"><span data-stu-id="f19f9-147">This operates in addition to the Windows Defender SmartScreen filter, which scans files before and during downloading.</span></span> | <span data-ttu-id="f19f9-148">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-148">Enabled</span></span> |
       | <span data-ttu-id="f19f9-149">Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="f19f9-149">Monitor file and program activity on your computer</span></span> | <span data-ttu-id="f19f9-150">Das Microsoft Defender Antivirus-Modul notiert Alle Dateiänderungen (Datei schreibt, z. B. Verschiebevorgänge, Kopien oder Änderungen) und allgemeine Programmaktivitäten (Programme, die geöffnet oder ausgeführt werden und die dazu führen, dass andere Programme ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="f19f9-150">The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run).</span></span> | <span data-ttu-id="f19f9-151">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-151">Enabled</span></span> |
       | <span data-ttu-id="f19f9-152">Aktivieren von unformatierte Volume-Schreibbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f19f9-152">Turn on raw volume write notifications</span></span> | <span data-ttu-id="f19f9-153">Informationen zu unformatierten Volume-Schreibvorgängen werden durch die Verhaltensüberwachung analysiert.</span><span class="sxs-lookup"><span data-stu-id="f19f9-153">Information about raw volume writes will be analyzed by behavior monitoring.</span></span> | <span data-ttu-id="f19f9-154">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-154">Enabled</span></span> |
       | <span data-ttu-id="f19f9-155">Aktivieren der Prozessprüfung, wenn Echtzeitschutz aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="f19f9-155">Turn on process scanning whenever real-time protection is enabled</span></span> | <span data-ttu-id="f19f9-156">Sie können das Microsoft Defender Antivirus-Modul unabhängig voneinander aktivieren, um laufende Prozesse auf verdächtige Änderungen oder Verhaltensweisen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-156">You can independently enable the Microsoft Defender Antivirus engine to scan running processes for suspicious modifications or behaviors.</span></span> <span data-ttu-id="f19f9-157">Dies ist hilfreich, wenn Sie den Echtzeitschutz vorübergehend deaktiviert haben und Prozesse automatisch überprüfen möchten, die während des Deaktivierens gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-157">This is useful if you have temporarily disabled real-time protection and want to automatically scan processes that started while it was disabled.</span></span> | <span data-ttu-id="f19f9-158">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-158">Enabled</span></span> |
       | <span data-ttu-id="f19f9-159">Definieren der maximalen Größe der heruntergeladenen Dateien und Anlagen, die überprüft werden sollen</span><span class="sxs-lookup"><span data-stu-id="f19f9-159">Define the maximum size of downloaded files and attachments to be scanned</span></span> | <span data-ttu-id="f19f9-160">Sie können die Größe in Kilobyte definieren.</span><span class="sxs-lookup"><span data-stu-id="f19f9-160">You can define the size in kilobytes.</span></span> | <span data-ttu-id="f19f9-161">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-161">Enabled</span></span> |
       | <span data-ttu-id="f19f9-162">Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren der Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="f19f9-162">Configure local setting override for turn on behavior monitoring</span></span> | <span data-ttu-id="f19f9-163">Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Verhaltensüberwachung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-163">Configure a local override for the configuration of behavior monitoring.</span></span> <span data-ttu-id="f19f9-164">Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-164">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f19f9-165">Wenn Sie diese Einstellung aktivieren, hat die lokale Einstellung Vorrang vor gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f19f9-165">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f19f9-166">Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat gruppenrichtlinien Vorrang vor der lokalen Einstellungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-166">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f19f9-167">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-167">Enabled</span></span> |
       | <span data-ttu-id="f19f9-168">Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Scannen aller heruntergeladenen Dateien und Anlagen</span><span class="sxs-lookup"><span data-stu-id="f19f9-168">Configure local setting override for scanning all downloaded files and attachments</span></span> | <span data-ttu-id="f19f9-169">Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überprüfung für alle heruntergeladenen Dateien und Anlagen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-169">Configure a local override for the configuration of scanning for all downloaded files and attachments.</span></span> <span data-ttu-id="f19f9-170">Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-170">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f19f9-171">Wenn Sie diese Einstellung aktivieren, hat die lokale Einstellung Vorrang vor gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f19f9-171">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f19f9-172">Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat gruppenrichtlinien Vorrang vor der lokalen Einstellungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-172">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f19f9-173">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-173">Enabled</span></span> |
       | <span data-ttu-id="f19f9-174">Konfigurieren der Außerkraftsetzung lokaler Einstellungen für Überwachungsdatei- und Programmaktivitäten auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="f19f9-174">Configure local setting override for monitoring file and program activity on your computer</span></span> | <span data-ttu-id="f19f9-175">Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überwachung für Datei- und Programmaktivitäten auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="f19f9-175">Configure a local override for the configuration of monitoring for file and program activity on your computer.</span></span> <span data-ttu-id="f19f9-176">Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-176">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f19f9-177">Wenn Sie diese Einstellung aktivieren, hat die lokale Einstellung Vorrang vor gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f19f9-177">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f19f9-178">Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat gruppenrichtlinien Vorrang vor der lokalen Einstellungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-178">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f19f9-179">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-179">Enabled</span></span> |
       | <span data-ttu-id="f19f9-180">Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="f19f9-180">Configure local setting override to turn on real-time protection</span></span> | <span data-ttu-id="f19f9-181">Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration, um den Echtzeitschutz zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f19f9-181">Configure a local override for the configuration to turn on real-time protection.</span></span> <span data-ttu-id="f19f9-182">Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-182">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f19f9-183">Wenn Sie diese Einstellung aktivieren, hat die lokale Einstellung Vorrang vor gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f19f9-183">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f19f9-184">Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat gruppenrichtlinien Vorrang vor der lokalen Einstellungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-184">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span>| <span data-ttu-id="f19f9-185">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-185">Enabled</span></span> |
       | <span data-ttu-id="f19f9-186">Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung eingehender und ausgehender Dateiaktivitäten</span><span class="sxs-lookup"><span data-stu-id="f19f9-186">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | <span data-ttu-id="f19f9-187">Konfigurieren Sie eine lokale Außerkraftsetzung für die Konfiguration der Überwachung eingehender und ausgehender Dateiaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="f19f9-187">Configure a local override for the configuration of monitoring for incoming and outgoing file activity.</span></span> <span data-ttu-id="f19f9-188">Diese Einstellung kann nur durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f19f9-188">This setting can only be set by Group Policy.</span></span> <span data-ttu-id="f19f9-189">Wenn Sie diese Einstellung aktivieren, hat die lokale Einstellung Vorrang vor gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="f19f9-189">If you enable this setting, the local preference setting will take priority over Group Policy.</span></span> <span data-ttu-id="f19f9-190">Wenn Sie diese Einstellung deaktivieren oder nicht konfigurieren, hat gruppenrichtlinien Vorrang vor der lokalen Einstellungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="f19f9-190">If you disable or do not configure this setting, Group Policy will take priority over the local preference setting.</span></span> | <span data-ttu-id="f19f9-191">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-191">Enabled</span></span> |
       | <span data-ttu-id="f19f9-192">Konfigurieren der Überwachung für eingehende und ausgehende Datei- und Programmaktivitäten</span><span class="sxs-lookup"><span data-stu-id="f19f9-192">Configure monitoring for incoming and outgoing file and program activity</span></span> | <span data-ttu-id="f19f9-193">Geben Sie an, ob die Überwachung für eingehende, ausgehende, beide oder keine Richtung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="f19f9-193">Specify whether monitoring should occur on incoming, outgoing, both, or neither direction.</span></span> <span data-ttu-id="f19f9-194">Dies ist für Windows Server-Installationen relevant, bei denen Sie bestimmte Server oder Serverrollen definiert haben, bei denen große Mengen von Dateiänderungen nur in eine Richtung geändert werden und Sie die Netzwerkleistung verbessern möchten.</span><span class="sxs-lookup"><span data-stu-id="f19f9-194">This is relevant for Windows Server installations where you have defined specific servers or Server Roles that see large amounts of file changes in only one direction and you want to improve network performance.</span></span> <span data-ttu-id="f19f9-195">Vollständig aktualisierte Endpunkte (und Server) in einem Netzwerk haben geringe Auswirkungen auf die Leistung, unabhängig von der Anzahl oder Richtung der Dateiänderungen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-195">Fully updated endpoints (and servers) on a network will see little performance impact irrespective of the number or direction of file changes.</span></span> | <span data-ttu-id="f19f9-196">Aktiviert (beide Richtungen)</span><span class="sxs-lookup"><span data-stu-id="f19f9-196">Enabled (both directions)</span></span> |

    1. <span data-ttu-id="f19f9-197">Konfigurieren Sie die Einstellung entsprechend, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-197">Configure the setting as appropriate, and click **OK**.</span></span>
    
    1. <span data-ttu-id="f19f9-198">Wiederholen Sie die vorherigen Schritte für jede Einstellung in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f19f9-198">Repeat the previous steps for each setting in the table.</span></span>

5. <span data-ttu-id="f19f9-199">Konfigurieren Sie die Einstellung der Microsoft Defender Antivirus-Überprüfungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="f19f9-199">Configure the Microsoft Defender Antivirus scanning policy setting.</span></span> <span data-ttu-id="f19f9-200">Gehen Sie hierfür folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f19f9-200">To do this:</span></span>  

    1. <span data-ttu-id="f19f9-201">Klicken Sie **in der Microsoft Defender Antivirus-Struktur** im linken Bereich auf **Scannen**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-201">From the **Microsoft Defender Antivirus** tree on left pane, click **Scan**.</span></span>
    
       ![Microsoft Defender Antivirus Scan-Optionen](images/gpedit-windows-defender-antivirus-scan.png)

    1. <span data-ttu-id="f19f9-203">**Doppelklicken Sie im** Bereich Details überprüfen auf der rechten Seite auf die Richtlinieneinstellung, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="f19f9-203">In the **Scan** details pane on right, double-click the policy setting as specified in the following table:</span></span>

       | <span data-ttu-id="f19f9-204">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-204">Setting</span></span> | <span data-ttu-id="f19f9-205">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f19f9-205">Description</span></span> | <span data-ttu-id="f19f9-206">Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="f19f9-206">Default setting</span></span> |
       |-----------------------------|------------------------|-------------------------------|    
       | <span data-ttu-id="f19f9-207">Aktivieren von Heuristiken</span><span class="sxs-lookup"><span data-stu-id="f19f9-207">Turn on heuristics</span></span> | <span data-ttu-id="f19f9-208">Heuristischer Schutz deaktiviert oder blockiert verdächtige Aktivitäten unmittelbar, bevor das Microsoft Defender Antivirus-Modul aufgefordert wird, die Aktivität zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-208">Heuristic protection will disable or block suspicious activity immediately before the Microsoft Defender Antivirus engine is asked to detect the activity.</span></span> | <span data-ttu-id="f19f9-209">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f19f9-209">Enabled</span></span> |

    1. <span data-ttu-id="f19f9-210">Konfigurieren Sie die Einstellung entsprechend, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-210">Configure the setting as appropriate, and click **OK**.</span></span>
    
6. <span data-ttu-id="f19f9-211">Schließen **Sie den Editor für lokale Gruppenrichtlinien.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-211">Close **Local Group Policy Editor**.</span></span>


## <a name="disable-real-time-protection-in-group-policy"></a><span data-ttu-id="f19f9-212">Deaktivieren des Echtzeitschutzes in Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f19f9-212">Disable real-time protection in Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="f19f9-213">Das Deaktivieren des Echtzeitschutzes reduziert den Schutz auf Ihren Endpunkten erheblich und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f19f9-213">Disabling real-time protection drastically reduces the protection on your endpoints and is not recommended.</span></span>

<span data-ttu-id="f19f9-214">Die Hauptfunktion für den Echtzeitschutz ist standardmäßig aktiviert, Sie können sie jedoch mithilfe des Editors für lokale **Gruppenrichtlinien deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-214">The main real-time protection capability is enabled by default, but you can disable it by using **Local Group Policy Editor**.</span></span>

<span data-ttu-id="f19f9-215">So deaktivieren Sie den Echtzeitschutz in Gruppenrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="f19f9-215">To disable real-time protection in Group policy:</span></span>

1. <span data-ttu-id="f19f9-216">Öffnen **Sie den Editor für lokale Gruppenrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-216">Open **Local Group Policy Editor**.</span></span>

   1. <span data-ttu-id="f19f9-217">Geben Sie im Suchfeld Windows 10-Taskleiste **gpedit ein.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-217">In your Windows 10 taskbar search box, type **gpedit**.</span></span>
   
   1. <span data-ttu-id="f19f9-218">Klicken **Sie unter Beste Übereinstimmung** auf **Gruppenrichtlinie bearbeiten,** um den Editor für **lokale Gruppenrichtlinien zu starten.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-218">Under **Best match**, click **Edit group policy** to launch **Local Group Policy Editor**.</span></span>

2.  <span data-ttu-id="f19f9-219">Erweitern Sie im linken Bereich des **Editors** für lokale Gruppenrichtlinien die Struktur auf **Computerkonfiguration** Administrative Vorlagen  >    >  **Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Echtzeitschutz**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-219">In the left pane of **Local Group Policy Editor**, expand the tree to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Real-time Protection**.</span></span>

3. <span data-ttu-id="f19f9-220">**Doppelklicken** Sie im Detailbereich Echtzeitschutz auf der rechten Seite auf **Echtzeitschutz deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-220">In the **Real-time Protection** details pane on right, double-click **Turn off real-time protection**.</span></span>

   ![Deaktivieren des Echtzeitschutzes](images/gpedit-turn-off-real-time-protection.png)

4. <span data-ttu-id="f19f9-222">Legen Sie **im Einstellungsfenster Echtzeitschutz** deaktivieren die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="f19f9-222">In the **Turn off real-time protection** setting window, set the option to **Enabled**.</span></span>

   ![Deaktivieren des Echtzeitschutzes](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. <span data-ttu-id="f19f9-224">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19f9-224">Click **OK**.</span></span>

6. <span data-ttu-id="f19f9-225">Schließen **Sie den Editor für lokale Gruppenrichtlinien.**</span><span class="sxs-lookup"><span data-stu-id="f19f9-225">Close **Local Group Policy Editor**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f19f9-226">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f19f9-226">Related articles</span></span>

- [<span data-ttu-id="f19f9-227">Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="f19f9-227">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f19f9-228">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f19f9-228">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)