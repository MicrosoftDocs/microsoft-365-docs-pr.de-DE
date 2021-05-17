---
title: Microsoft Defender for Endpoint auf Linux-Ressourcen
ms.reviewer: ''
description: Beschreibt Ressourcen für Microsoft Defender for Endpoint unter Linux, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 176ee89c8d60a1515855296e2565f0649f908a33
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933325"
---
# <a name="resources"></a><span data-ttu-id="e5887-104">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e5887-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5887-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e5887-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5887-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e5887-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5887-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5887-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e5887-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e5887-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e5887-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e5887-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="e5887-110">Sammeln von Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="e5887-110">Collect diagnostic information</span></span>

<span data-ttu-id="e5887-111">Wenn Sie ein Problem reproduzieren können, erhöhen Sie zuerst die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie dann die Protokollierungsstufe auf die Standardeinstellung wieder dar.</span><span class="sxs-lookup"><span data-stu-id="e5887-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="e5887-112">Erhöhen des Protokollierungsgrads:</span><span class="sxs-lookup"><span data-stu-id="e5887-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="e5887-113">Reproduzieren Sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="e5887-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="e5887-114">Führen Sie den folgenden Befehl aus, um die Protokolle von Defender for Endpoint zu sichern.</span><span class="sxs-lookup"><span data-stu-id="e5887-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="e5887-115">Die Dateien werden innerhalb eines .zip gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5887-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="e5887-116">Mit diesem Befehl wird auch der Dateipfad zur Sicherung gedruckt, nachdem der Vorgang erfolgreich war:</span><span class="sxs-lookup"><span data-stu-id="e5887-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="e5887-117">Protokollierungsstufe wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="e5887-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="e5887-118">Probleme bei der Protokollinstallation</span><span class="sxs-lookup"><span data-stu-id="e5887-118">Log installation issues</span></span>

<span data-ttu-id="e5887-119">Wenn während der Installation ein Fehler auftritt, wird vom Installationsprogramm nur ein allgemeiner Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5887-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="e5887-120">Das detaillierte Protokoll wird in `/var/log/microsoft/mdatp_install.log` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5887-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="e5887-121">Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir die Ursache diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="e5887-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="e5887-122">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="e5887-122">Uninstall</span></span>

<span data-ttu-id="e5887-123">Es gibt verschiedene Möglichkeiten, Defender for Endpoint unter Linux zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="e5887-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="e5887-124">Wenn Sie ein Konfigurationstool wie "Puppet" verwenden, befolgen Sie die Anweisungen zur Paketentinstallation für das Konfigurationstool.</span><span class="sxs-lookup"><span data-stu-id="e5887-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="e5887-125">Manuelle Deinstallation</span><span class="sxs-lookup"><span data-stu-id="e5887-125">Manual uninstallation</span></span>

- <span data-ttu-id="e5887-126">`sudo yum remove mdatp` für RHEL und variants(CentOS und Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="e5887-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="e5887-127">`sudo zypper remove mdatp` für SLES und Varianten.</span><span class="sxs-lookup"><span data-stu-id="e5887-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="e5887-128">`sudo apt-get purge mdatp` für Ubuntu- und Debian-Systeme.</span><span class="sxs-lookup"><span data-stu-id="e5887-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="e5887-129">Konfigurieren über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="e5887-129">Configure from the command line</span></span>

<span data-ttu-id="e5887-130">Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Bedarfsscans, können über die Befehlszeile ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5887-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="e5887-131">Globale Optionen</span><span class="sxs-lookup"><span data-stu-id="e5887-131">Global options</span></span>

<span data-ttu-id="e5887-132">Standardmäßig gibt das Befehlszeilentool das Ergebnis im lesbaren Format aus.</span><span class="sxs-lookup"><span data-stu-id="e5887-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="e5887-133">Darüber hinaus unterstützt das Tool auch die Ausgabe des Ergebnisses als JSON, was für Automatisierungsszenarien nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5887-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="e5887-134">Um die Ausgabe in JSON zu ändern, übergeben Sie `--output json` an einen der folgenden Befehle.</span><span class="sxs-lookup"><span data-stu-id="e5887-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="e5887-135">Unterstützte Befehle</span><span class="sxs-lookup"><span data-stu-id="e5887-135">Supported commands</span></span>

<span data-ttu-id="e5887-136">In der folgenden Tabelle sind Befehle für einige der gängigsten Szenarien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5887-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="e5887-137">Führen `mdatp help` Sie das Terminal aus, um die vollständige Liste der unterstützten Befehle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5887-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="e5887-138">Gruppe</span><span class="sxs-lookup"><span data-stu-id="e5887-138">Group</span></span>                 |<span data-ttu-id="e5887-139">Szenario</span><span class="sxs-lookup"><span data-stu-id="e5887-139">Scenario</span></span>                                                |<span data-ttu-id="e5887-140">Get-Help</span><span class="sxs-lookup"><span data-stu-id="e5887-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="e5887-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-141">Configuration</span></span>         |<span data-ttu-id="e5887-142">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="e5887-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="e5887-143">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-143">Configuration</span></span>         |<span data-ttu-id="e5887-144">Aktivieren/Deaktivieren der Verhaltensüberwachung</span><span class="sxs-lookup"><span data-stu-id="e5887-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="e5887-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-145">Configuration</span></span>         |<span data-ttu-id="e5887-146">Aktivieren/Deaktivieren des Cloudschutzes</span><span class="sxs-lookup"><span data-stu-id="e5887-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="e5887-147">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-147">Configuration</span></span>         |<span data-ttu-id="e5887-148">Aktivieren/Deaktivieren der Produktdiagnose</span><span class="sxs-lookup"><span data-stu-id="e5887-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="e5887-149">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-149">Configuration</span></span>         |<span data-ttu-id="e5887-150">Aktivieren/Deaktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="e5887-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="e5887-151">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-151">Configuration</span></span>         |<span data-ttu-id="e5887-152">Aktivieren/Deaktivieren des passiven AV-Modus</span><span class="sxs-lookup"><span data-stu-id="e5887-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="e5887-153">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-153">Configuration</span></span>         |<span data-ttu-id="e5887-154">Hinzufügen/Entfernen eines Antivirenausschlusses für eine Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="e5887-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="e5887-155">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-155">Configuration</span></span>         |<span data-ttu-id="e5887-156">Hinzufügen/Entfernen eines Antivirenausschlusses für eine Datei</span><span class="sxs-lookup"><span data-stu-id="e5887-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="e5887-157">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-157">Configuration</span></span>         |<span data-ttu-id="e5887-158">Hinzufügen/Entfernen eines Antivirenausschlusses für ein Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="e5887-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="e5887-159">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-159">Configuration</span></span>         |<span data-ttu-id="e5887-160">Hinzufügen/Entfernen eines Antivirenausschlusses für einen Prozess</span><span class="sxs-lookup"><span data-stu-id="e5887-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="e5887-161">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-161">Configuration</span></span>         |<span data-ttu-id="e5887-162">Auflisten aller Antivirenausschlüsse</span><span class="sxs-lookup"><span data-stu-id="e5887-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="e5887-163">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-163">Configuration</span></span>         |<span data-ttu-id="e5887-164">Hinzufügen eines Bedrohungsnamens zur liste der zulässigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="e5887-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="e5887-165">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-165">Configuration</span></span>         |<span data-ttu-id="e5887-166">Entfernen eines Bedrohungsnamens aus der liste der zulässigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="e5887-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="e5887-167">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-167">Configuration</span></span>         |<span data-ttu-id="e5887-168">Auflisten aller zulässigen Bedrohungsnamen</span><span class="sxs-lookup"><span data-stu-id="e5887-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="e5887-169">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-169">Configuration</span></span>         |<span data-ttu-id="e5887-170">Aktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="e5887-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="e5887-171">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-171">Configuration</span></span>         |<span data-ttu-id="e5887-172">Deaktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="e5887-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="e5887-173">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e5887-173">Configuration</span></span>         |<span data-ttu-id="e5887-174">Aktivieren des Überwachungsmodus für den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="e5887-175">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e5887-175">Diagnostics</span></span>           |<span data-ttu-id="e5887-176">Ändern der Protokollebene</span><span class="sxs-lookup"><span data-stu-id="e5887-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="e5887-177">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e5887-177">Diagnostics</span></span>           |<span data-ttu-id="e5887-178">Generieren von Diagnoseprotokollen</span><span class="sxs-lookup"><span data-stu-id="e5887-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="e5887-179">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="e5887-179">Health</span></span>                |<span data-ttu-id="e5887-180">Überprüfen des Produktzustands</span><span class="sxs-lookup"><span data-stu-id="e5887-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="e5887-181">Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-181">Protection</span></span>            |<span data-ttu-id="e5887-182">Überprüfen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="e5887-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="e5887-183">Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-183">Protection</span></span>            |<span data-ttu-id="e5887-184">Schnellscan durchführen</span><span class="sxs-lookup"><span data-stu-id="e5887-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="e5887-185">Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-185">Protection</span></span>            |<span data-ttu-id="e5887-186">Durchführen einer vollständigen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e5887-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="e5887-187">Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-187">Protection</span></span>            |<span data-ttu-id="e5887-188">Abbrechen einer laufenden Überprüfung bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="e5887-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="e5887-189">Schutz</span><span class="sxs-lookup"><span data-stu-id="e5887-189">Protection</span></span>            |<span data-ttu-id="e5887-190">Anfordern eines Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="e5887-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="e5887-191">Schutzverlauf</span><span class="sxs-lookup"><span data-stu-id="e5887-191">Protection history</span></span>    |<span data-ttu-id="e5887-192">Drucken des vollständigen Schutzverlaufs</span><span class="sxs-lookup"><span data-stu-id="e5887-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="e5887-193">Schutzverlauf</span><span class="sxs-lookup"><span data-stu-id="e5887-193">Protection history</span></span>    |<span data-ttu-id="e5887-194">Erhalten von Bedrohungsdetails</span><span class="sxs-lookup"><span data-stu-id="e5887-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="e5887-195">Quarantäneverwaltung</span><span class="sxs-lookup"><span data-stu-id="e5887-195">Quarantine management</span></span> |<span data-ttu-id="e5887-196">Auflisten aller isolierten Dateien</span><span class="sxs-lookup"><span data-stu-id="e5887-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="e5887-197">Quarantäneverwaltung</span><span class="sxs-lookup"><span data-stu-id="e5887-197">Quarantine management</span></span> |<span data-ttu-id="e5887-198">Entfernen aller Dateien aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="e5887-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="e5887-199">Quarantäneverwaltung</span><span class="sxs-lookup"><span data-stu-id="e5887-199">Quarantine management</span></span> |<span data-ttu-id="e5887-200">Hinzufügen einer Als Bedrohung erkannten Datei zur Quarantäne</span><span class="sxs-lookup"><span data-stu-id="e5887-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="e5887-201">Quarantäneverwaltung</span><span class="sxs-lookup"><span data-stu-id="e5887-201">Quarantine management</span></span> |<span data-ttu-id="e5887-202">Entfernen einer als Bedrohung erkannten Datei aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="e5887-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="e5887-203">Quarantäneverwaltung</span><span class="sxs-lookup"><span data-stu-id="e5887-203">Quarantine management</span></span> |<span data-ttu-id="e5887-204">Wiederherstellen einer Datei aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="e5887-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="e5887-205">Endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="e5887-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="e5887-206">Festlegen einer frühen Vorschau (nicht verwendet)</span><span class="sxs-lookup"><span data-stu-id="e5887-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="e5887-207">Endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="e5887-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="e5887-208">Festlegen der Gruppen-ID</span><span class="sxs-lookup"><span data-stu-id="e5887-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="e5887-209">Endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="e5887-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="e5887-210">Set/Remove-Tag, nur `GROUP` unterstützt</span><span class="sxs-lookup"><span data-stu-id="e5887-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="e5887-211">Endpunkterkennung und -reaktion</span><span class="sxs-lookup"><span data-stu-id="e5887-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="e5887-212">Listenausschlüsse (Stamm)</span><span class="sxs-lookup"><span data-stu-id="e5887-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="e5887-213">Informationen zum Microsoft Defender for Endpoint-Portal</span><span class="sxs-lookup"><span data-stu-id="e5887-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="e5887-214">Im Defender for Endpoint-Portal werden zwei Kategorien von Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e5887-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="e5887-215">Antiviruswarnungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="e5887-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="e5887-216">Severity</span><span class="sxs-lookup"><span data-stu-id="e5887-216">Severity</span></span>
  - <span data-ttu-id="e5887-217">Scantyp</span><span class="sxs-lookup"><span data-stu-id="e5887-217">Scan type</span></span>
  - <span data-ttu-id="e5887-218">Geräteinformationen (Hostname, Geräte-ID, Mandanten-ID, App-Version und Betriebssystemtyp)</span><span class="sxs-lookup"><span data-stu-id="e5887-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="e5887-219">Dateiinformationen (Name, Pfad, Größe und Hash)</span><span class="sxs-lookup"><span data-stu-id="e5887-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="e5887-220">Bedrohungsinformationen (Name, Typ und Status)</span><span class="sxs-lookup"><span data-stu-id="e5887-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="e5887-221">Geräteinformationen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="e5887-221">Device information, including:</span></span>
  - <span data-ttu-id="e5887-222">Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="e5887-222">Device identifier</span></span>
  - <span data-ttu-id="e5887-223">Mandanten-ID</span><span class="sxs-lookup"><span data-stu-id="e5887-223">Tenant identifier</span></span>
  - <span data-ttu-id="e5887-224">Version der App</span><span class="sxs-lookup"><span data-stu-id="e5887-224">App version</span></span>
  - <span data-ttu-id="e5887-225">Hostname</span><span class="sxs-lookup"><span data-stu-id="e5887-225">Hostname</span></span>
  - <span data-ttu-id="e5887-226">Betriebssystemtyp</span><span class="sxs-lookup"><span data-stu-id="e5887-226">OS type</span></span>
  - <span data-ttu-id="e5887-227">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="e5887-227">OS version</span></span>
  - <span data-ttu-id="e5887-228">Computermodell</span><span class="sxs-lookup"><span data-stu-id="e5887-228">Computer model</span></span>
  - <span data-ttu-id="e5887-229">Prozessorarchitektur</span><span class="sxs-lookup"><span data-stu-id="e5887-229">Processor architecture</span></span>
  - <span data-ttu-id="e5887-230">Gibt an, ob es sich bei dem Gerät um einen virtuellen Computer handelt</span><span class="sxs-lookup"><span data-stu-id="e5887-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="e5887-231">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="e5887-231">Known issues</span></span>

- <span data-ttu-id="e5887-232">Möglicherweise wird auf der Computerinformationsseite des Microsoft Defender Security Center-Portals "Keine Sensordaten, beeinträchtigte Kommunikation" angezeigt, obwohl das Produkt wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e5887-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="e5887-233">Wir arbeiten daran, dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e5887-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="e5887-234">Angemeldete Benutzer werden nicht im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5887-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="e5887-235">Wenn bei der Installation von *libatomic1* in SUSE-Verteilungen ein Fehler auftritt, sollten Sie überprüfen, ob Ihr Betriebssystem registriert ist:</span><span class="sxs-lookup"><span data-stu-id="e5887-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
