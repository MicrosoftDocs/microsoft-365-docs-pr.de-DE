---
title: Ressourcen für Microsoft Defender for Endpoint auf Dem Mac
description: Ressourcen für Microsoft Defender for Endpoint auf Mac, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29e9eefdf85c80b6d3c44eba01d0df57be0193a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346390"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="55861-104">Ressourcen für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="55861-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55861-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="55861-105">**Applies to:**</span></span>

- [<span data-ttu-id="55861-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="55861-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55861-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55861-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="55861-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="55861-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="55861-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="55861-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="55861-110">Sammeln von Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="55861-110">Collecting diagnostic information</span></span>

<span data-ttu-id="55861-111">Wenn Sie ein Problem reproduzieren können, erhöhen Sie die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie den Protokollierungsgrad auf den Standardwert wieder dar.</span><span class="sxs-lookup"><span data-stu-id="55861-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="55861-112">Erhöhen des Protokollierungsgrads:</span><span class="sxs-lookup"><span data-stu-id="55861-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="55861-113">Reproduzieren des Problems</span><span class="sxs-lookup"><span data-stu-id="55861-113">Reproduce the problem</span></span>

3. <span data-ttu-id="55861-114">Führen `sudo mdatp diagnostic create` Sie aus, um die Microsoft Defender for Endpoint-Protokolle zu sichern.</span><span class="sxs-lookup"><span data-stu-id="55861-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="55861-115">Die Dateien werden in einem .zip gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55861-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="55861-116">Mit diesem Befehl wird auch der Dateipfad zur Sicherung gedruckt, nachdem der Vorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="55861-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="55861-117">Diagnoseprotokolle werden standardmäßig in `/Library/Application Support/Microsoft/Defender/wdavdiag/` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55861-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="55861-118">Um das Verzeichnis zu ändern, in dem Diagnoseprotokolle gespeichert werden, übergeben Sie an den folgenden Befehl, und ersetzen Sie durch `--path [directory]` `[directory]` das gewünschte Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="55861-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="55861-119">Protokollierungsstufe wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="55861-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="55861-120">Probleme bei der Protokollierung der Installation</span><span class="sxs-lookup"><span data-stu-id="55861-120">Logging installation issues</span></span>

<span data-ttu-id="55861-121">Wenn während der Installation ein Fehler auftritt, wird vom Installationsprogramm nur ein allgemeiner Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="55861-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="55861-122">Das detaillierte Protokoll wird in `/Library/Logs/Microsoft/mdatp/install.log` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55861-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="55861-123">Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir die Ursache diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="55861-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="55861-124">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="55861-124">Uninstalling</span></span>

<span data-ttu-id="55861-125">Es gibt mehrere Möglichkeiten, Microsoft Defender for Endpoint unter macOS zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="55861-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="55861-126">Beachten Sie, dass die zentral verwaltete Deinstallation zwar auf JAMF verfügbar ist, aber noch nicht für Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="55861-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="55861-127">Interaktive Deinstallation</span><span class="sxs-lookup"><span data-stu-id="55861-127">Interactive uninstallation</span></span>

- <span data-ttu-id="55861-128">Öffnen **Sie finder > Applications**.</span><span class="sxs-lookup"><span data-stu-id="55861-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="55861-129">Klicken Sie mit der rechten Maustaste **auf Microsoft Defender for Endpoint > Move to Trash**.</span><span class="sxs-lookup"><span data-stu-id="55861-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="55861-130">Über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="55861-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="55861-131">Konfigurieren über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="55861-131">Configuring from the command line</span></span>

<span data-ttu-id="55861-132">Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Bedarfsscans, können über die Befehlszeile ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="55861-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="55861-133">Gruppe</span><span class="sxs-lookup"><span data-stu-id="55861-133">Group</span></span>        |<span data-ttu-id="55861-134">Szenario</span><span class="sxs-lookup"><span data-stu-id="55861-134">Scenario</span></span>                                   |<span data-ttu-id="55861-135">Get-Help</span><span class="sxs-lookup"><span data-stu-id="55861-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="55861-136">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-136">Configuration</span></span>|<span data-ttu-id="55861-137">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="55861-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="55861-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-138">Configuration</span></span>|<span data-ttu-id="55861-139">Aktivieren/Deaktivieren des Cloudschutzes</span><span class="sxs-lookup"><span data-stu-id="55861-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="55861-140">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-140">Configuration</span></span>|<span data-ttu-id="55861-141">Aktivieren/Deaktivieren der Produktdiagnose</span><span class="sxs-lookup"><span data-stu-id="55861-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="55861-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-142">Configuration</span></span>|<span data-ttu-id="55861-143">Aktivieren/Deaktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="55861-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="55861-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-144">Configuration</span></span>|<span data-ttu-id="55861-145">Hinzufügen eines Bedrohungsnamens zur liste der zulässigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="55861-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="55861-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-146">Configuration</span></span>|<span data-ttu-id="55861-147">Entfernen eines Bedrohungsnamens aus der liste der zulässigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="55861-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="55861-148">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-148">Configuration</span></span>|<span data-ttu-id="55861-149">Auflisten aller zulässigen Bedrohungsnamen</span><span class="sxs-lookup"><span data-stu-id="55861-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="55861-150">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-150">Configuration</span></span>|<span data-ttu-id="55861-151">Aktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="55861-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="55861-152">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-152">Configuration</span></span>|<span data-ttu-id="55861-153">Deaktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="55861-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="55861-154">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-154">Configuration</span></span>|<span data-ttu-id="55861-155">Aktivieren des Überwachungsmodus für den PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="55861-156">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="55861-156">Configuration</span></span>|<span data-ttu-id="55861-157">Ein-/Ausschalten von passivem Modus</span><span class="sxs-lookup"><span data-stu-id="55861-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="55861-158">Diagnose</span><span class="sxs-lookup"><span data-stu-id="55861-158">Diagnostics</span></span>  |<span data-ttu-id="55861-159">Ändern der Protokollebene</span><span class="sxs-lookup"><span data-stu-id="55861-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="55861-160">Diagnose</span><span class="sxs-lookup"><span data-stu-id="55861-160">Diagnostics</span></span>  |<span data-ttu-id="55861-161">Generieren von Diagnoseprotokollen</span><span class="sxs-lookup"><span data-stu-id="55861-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="55861-162">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="55861-162">Health</span></span>       |<span data-ttu-id="55861-163">Überprüfen des Produktzustands</span><span class="sxs-lookup"><span data-stu-id="55861-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="55861-164">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="55861-164">Health</span></span>       |<span data-ttu-id="55861-165">Suchen nach einem spefic-Produktattribut</span><span class="sxs-lookup"><span data-stu-id="55861-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="55861-166">Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-166">Protection</span></span>   |<span data-ttu-id="55861-167">Überprüfen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="55861-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="55861-168">Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-168">Protection</span></span>   |<span data-ttu-id="55861-169">Schnellscan durchführen</span><span class="sxs-lookup"><span data-stu-id="55861-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="55861-170">Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-170">Protection</span></span>   |<span data-ttu-id="55861-171">Durchführen einer vollständigen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="55861-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="55861-172">Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-172">Protection</span></span>   |<span data-ttu-id="55861-173">Abbrechen einer laufenden Überprüfung bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="55861-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="55861-174">Schutz</span><span class="sxs-lookup"><span data-stu-id="55861-174">Protection</span></span>   |<span data-ttu-id="55861-175">Anfordern eines Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="55861-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="55861-176">EDR</span><span class="sxs-lookup"><span data-stu-id="55861-176">EDR</span></span>          |<span data-ttu-id="55861-177">Fügen Sie dem Gerät ein Gruppentag hinzu.</span><span class="sxs-lookup"><span data-stu-id="55861-177">Add group tag to device.</span></span> <span data-ttu-id="55861-178">EDR-Tags werden zum Verwalten von Gerätegruppen verwendet.</span><span class="sxs-lookup"><span data-stu-id="55861-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="55861-179">Weitere Informationen finden Sie unter https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="55861-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="55861-180">EDR</span><span class="sxs-lookup"><span data-stu-id="55861-180">EDR</span></span>          |<span data-ttu-id="55861-181">Entfernen des Gruppentags vom Gerät</span><span class="sxs-lookup"><span data-stu-id="55861-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="55861-182">EDR</span><span class="sxs-lookup"><span data-stu-id="55861-182">EDR</span></span>          |<span data-ttu-id="55861-183">Hinzufügen von Gruppen-ID</span><span class="sxs-lookup"><span data-stu-id="55861-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="55861-184">Aktivieren der automatischen Vervollständigung</span><span class="sxs-lookup"><span data-stu-id="55861-184">How to enable autocompletion</span></span>

<span data-ttu-id="55861-185">Führen Sie zum Aktivieren der autocompletion in bash den folgenden Befehl aus, und starten Sie die Terminalsitzung neu:</span><span class="sxs-lookup"><span data-stu-id="55861-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="55861-186">So aktivieren Sie die automatische Vervollständigung in zsh:</span><span class="sxs-lookup"><span data-stu-id="55861-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="55861-187">Überprüfen Sie, ob die automatische Vervollständigung auf Ihrem Gerät aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="55861-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="55861-188">Wenn der vorangehende Befehl keine Ausgabe erzeugt, können Sie die automatische Vervollständigung mithilfe des folgenden Befehls aktivieren:</span><span class="sxs-lookup"><span data-stu-id="55861-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="55861-189">Führen Sie die folgenden Befehle aus, um die automatische Kompletion für Microsoft Defender for Endpoint unter macOS zu aktivieren und die Terminalsitzung neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="55861-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="55861-190">Microsoft Defender for Endpoint-Quarantäneverzeichnis des Clients</span><span class="sxs-lookup"><span data-stu-id="55861-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="55861-191">`/Library/Application Support/Microsoft/Defender/quarantine/` enthält die Dateien, die von isoliert `mdatp` werden.</span><span class="sxs-lookup"><span data-stu-id="55861-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="55861-192">Die Dateien sind nach der Threat TrackingId benannt.</span><span class="sxs-lookup"><span data-stu-id="55861-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="55861-193">Die aktuellen trackingIds wird mit `mdatp threat list` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55861-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="55861-194">Informationen zum Microsoft Defender for Endpoint-Portal</span><span class="sxs-lookup"><span data-stu-id="55861-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="55861-195">EDR Funktionen für [macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)sind nun im Microsoft Defender for Endpoint-Blog eingetroffen und bieten detaillierte Anleitungen zu den Vorkehrungen in Microsoft Defender for Endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="55861-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
