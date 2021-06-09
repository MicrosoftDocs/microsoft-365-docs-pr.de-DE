---
title: Ressourcen für Microsoft Defender für Endpunkt auf mac
description: Ressourcen für Microsoft Defender für Endpunkt auf dem Mac, einschließlich der Deinstallation, der Erfassung von Diagnoseprotokollen, CLI-Befehlen und bekannten Problemen mit dem Produkt.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Installation, bereitstellen, Deinstallation, Intune, jamf, macos, aus, mojave, high sierra
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
ms.openlocfilehash: fa5d5b4470644e1ff50af46a8dd3f035cd9b3184
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842866"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="8f231-104">Ressourcen für Microsoft Defender für Endpunkt unter macOS</span><span class="sxs-lookup"><span data-stu-id="8f231-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f231-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8f231-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f231-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8f231-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f231-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f231-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f231-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="8f231-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8f231-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8f231-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="8f231-110">Sammeln von Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="8f231-110">Collecting diagnostic information</span></span>

<span data-ttu-id="8f231-111">Wenn Sie ein Problem reproduzieren können, erhöhen Sie die Protokollierungsstufe, führen Sie das System für einige Zeit aus, und stellen Sie die Protokollierungsstufe auf die Standardeinstellung wieder her.</span><span class="sxs-lookup"><span data-stu-id="8f231-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="8f231-112">Erhöhen Sie die Protokollierungsstufe:</span><span class="sxs-lookup"><span data-stu-id="8f231-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="8f231-113">Reproduzieren des Problems</span><span class="sxs-lookup"><span data-stu-id="8f231-113">Reproduce the problem</span></span>

3. <span data-ttu-id="8f231-114">Führen Sie die Ausführung `sudo mdatp diagnostic create` aus, um die Microsoft Defender für Endpunkt-Protokolle zu sichern.</span><span class="sxs-lookup"><span data-stu-id="8f231-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="8f231-115">Die Dateien werden in einem .zip Archiv gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8f231-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="8f231-116">Dieser Befehl gibt auch den Dateipfad zur Sicherung aus, nachdem der Vorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8f231-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="8f231-117">Diagnoseprotokolle werden standardmäßig in `/Library/Application Support/Microsoft/Defender/wdavdiag/` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8f231-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="8f231-118">Um das Verzeichnis zu ändern, in dem Diagnoseprotokolle gespeichert werden, übergeben Sie den befehl unten, und ersetzen Sie es `--path [directory]` durch das gewünschte `[directory]` Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8f231-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="8f231-119">Protokollierungsstufe wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="8f231-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="8f231-120">Protokollieren von Installationsproblemen</span><span class="sxs-lookup"><span data-stu-id="8f231-120">Logging installation issues</span></span>

<span data-ttu-id="8f231-121">Wenn während der Installation ein Fehler auftritt, meldet das Installationsprogramm nur einen allgemeinen Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f231-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="8f231-122">Das detaillierte Protokoll wird in `/Library/Logs/Microsoft/mdatp/install.log` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8f231-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="8f231-123">Wenn während der Installation Probleme auftreten, senden Sie uns diese Datei, damit wir Ihnen bei der Diagnose der Ursache helfen können.</span><span class="sxs-lookup"><span data-stu-id="8f231-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="8f231-124">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="8f231-124">Uninstalling</span></span>

<span data-ttu-id="8f231-125">Es gibt mehrere Möglichkeiten, Microsoft Defender für Endpunkt unter macOS zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="8f231-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="8f231-126">Beachten Sie, dass die zentral verwaltete Deinstallation in JAMF zwar verfügbar ist, aber noch nicht für Microsoft Intune verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8f231-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="8f231-127">Interaktive Deinstallation</span><span class="sxs-lookup"><span data-stu-id="8f231-127">Interactive uninstallation</span></span>

- <span data-ttu-id="8f231-128">Öffnen **Sie finder > Applications**.</span><span class="sxs-lookup"><span data-stu-id="8f231-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="8f231-129">Klicken Sie mit der rechten Maustaste auf **Microsoft Defender für Endpunkt > In Papierkorb verschieben.**</span><span class="sxs-lookup"><span data-stu-id="8f231-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="8f231-130">Über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="8f231-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="8f231-131">Konfigurieren über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="8f231-131">Configuring from the command line</span></span>

<span data-ttu-id="8f231-132">Wichtige Aufgaben, z. B. das Steuern von Produkteinstellungen und das Auslösen von Scans bei Bedarf, können über die Befehlszeile ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8f231-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="8f231-133">Gruppe</span><span class="sxs-lookup"><span data-stu-id="8f231-133">Group</span></span>        |<span data-ttu-id="8f231-134">Szenario</span><span class="sxs-lookup"><span data-stu-id="8f231-134">Scenario</span></span>                                   |<span data-ttu-id="8f231-135">Befehl</span><span class="sxs-lookup"><span data-stu-id="8f231-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="8f231-136">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-136">Configuration</span></span>|<span data-ttu-id="8f231-137">Aktivieren/Deaktivieren des Echtzeitschutzes</span><span class="sxs-lookup"><span data-stu-id="8f231-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="8f231-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-138">Configuration</span></span>|<span data-ttu-id="8f231-139">Aktivieren/Deaktivieren des Cloudschutzes</span><span class="sxs-lookup"><span data-stu-id="8f231-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="8f231-140">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-140">Configuration</span></span>|<span data-ttu-id="8f231-141">Aktivieren/Deaktivieren der Produktdiagnose</span><span class="sxs-lookup"><span data-stu-id="8f231-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="8f231-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-142">Configuration</span></span>|<span data-ttu-id="8f231-143">Aktivieren/Deaktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="8f231-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="8f231-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-144">Configuration</span></span>|<span data-ttu-id="8f231-145">Hinzufügen eines Bedrohungsnamens zur Liste zugelassener Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="8f231-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="8f231-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-146">Configuration</span></span>|<span data-ttu-id="8f231-147">Entfernen eines Bedrohungsnamens aus der Liste der zulässigen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="8f231-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="8f231-148">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-148">Configuration</span></span>|<span data-ttu-id="8f231-149">Auflisten aller zulässigen Bedrohungsnamen</span><span class="sxs-lookup"><span data-stu-id="8f231-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="8f231-150">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-150">Configuration</span></span>|<span data-ttu-id="8f231-151">Aktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="8f231-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="8f231-152">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-152">Configuration</span></span>|<span data-ttu-id="8f231-153">Deaktivieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="8f231-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="8f231-154">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-154">Configuration</span></span>|<span data-ttu-id="8f231-155">Aktivieren des Überwachungsmodus für PUA-Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="8f231-156">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f231-156">Configuration</span></span>|<span data-ttu-id="8f231-157">PassiveMode aktivieren/deaktivieren</span><span class="sxs-lookup"><span data-stu-id="8f231-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="8f231-158">Diagnose</span><span class="sxs-lookup"><span data-stu-id="8f231-158">Diagnostics</span></span>  |<span data-ttu-id="8f231-159">Ändern der Protokollebene</span><span class="sxs-lookup"><span data-stu-id="8f231-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="8f231-160">Diagnose</span><span class="sxs-lookup"><span data-stu-id="8f231-160">Diagnostics</span></span>  |<span data-ttu-id="8f231-161">Generieren von Diagnoseprotokollen</span><span class="sxs-lookup"><span data-stu-id="8f231-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="8f231-162">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="8f231-162">Health</span></span>       |<span data-ttu-id="8f231-163">Überprüfen der Integrität des Produkts</span><span class="sxs-lookup"><span data-stu-id="8f231-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="8f231-164">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="8f231-164">Health</span></span>       |<span data-ttu-id="8f231-165">Überprüfen auf ein spefic-Produktattribut</span><span class="sxs-lookup"><span data-stu-id="8f231-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="8f231-166">Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-166">Protection</span></span>   |<span data-ttu-id="8f231-167">Scannen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="8f231-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="8f231-168">Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-168">Protection</span></span>   |<span data-ttu-id="8f231-169">Durchführen eines Schnellscans</span><span class="sxs-lookup"><span data-stu-id="8f231-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="8f231-170">Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-170">Protection</span></span>   |<span data-ttu-id="8f231-171">Durchführen einer vollständigen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="8f231-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="8f231-172">Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-172">Protection</span></span>   |<span data-ttu-id="8f231-173">Abbrechen einer laufenden Überprüfung nach Bedarf</span><span class="sxs-lookup"><span data-stu-id="8f231-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="8f231-174">Schutz</span><span class="sxs-lookup"><span data-stu-id="8f231-174">Protection</span></span>   |<span data-ttu-id="8f231-175">Anfordern eines Security Intelligence-Updates</span><span class="sxs-lookup"><span data-stu-id="8f231-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="8f231-176">EDR</span><span class="sxs-lookup"><span data-stu-id="8f231-176">EDR</span></span>          |<span data-ttu-id="8f231-177">Fügen Sie dem Gerät ein Gruppentag hinzu.</span><span class="sxs-lookup"><span data-stu-id="8f231-177">Add group tag to device.</span></span> <span data-ttu-id="8f231-178">EDR Tags werden für die Verwaltung von Gerätegruppen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f231-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="8f231-179">Weitere Informationen finden Sie unter /microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="8f231-179">For more information, please visit /microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="8f231-180">EDR</span><span class="sxs-lookup"><span data-stu-id="8f231-180">EDR</span></span>          |<span data-ttu-id="8f231-181">Gruppentag vom Gerät entfernen</span><span class="sxs-lookup"><span data-stu-id="8f231-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="8f231-182">EDR</span><span class="sxs-lookup"><span data-stu-id="8f231-182">EDR</span></span>          |<span data-ttu-id="8f231-183">Hinzufügen der Gruppen-ID</span><span class="sxs-lookup"><span data-stu-id="8f231-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="8f231-184">So aktivieren Sie die automatische Kompletion</span><span class="sxs-lookup"><span data-stu-id="8f231-184">How to enable autocompletion</span></span>

<span data-ttu-id="8f231-185">Um die automatische Kompletion in Bash zu aktivieren, führen Sie den folgenden Befehl aus, und starten Sie die Terminalsitzung neu:</span><span class="sxs-lookup"><span data-stu-id="8f231-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="8f231-186">So aktivieren Sie die automatische Kompletion in zsh:</span><span class="sxs-lookup"><span data-stu-id="8f231-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="8f231-187">Überprüfen Sie, ob die automatische Kompletion auf Ihrem Gerät aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="8f231-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="8f231-188">Wenn der vorherige Befehl keine Ausgabe erzeugt, können Sie die automatische Kompletion mit dem folgenden Befehl aktivieren:</span><span class="sxs-lookup"><span data-stu-id="8f231-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="8f231-189">Führen Sie die folgenden Befehle aus, um die automatische Kompletion für Microsoft Defender für Endpunkt unter macOS zu aktivieren und die Terminalsitzung neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="8f231-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="8f231-190">Client-Quarantäneverzeichnis für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8f231-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="8f231-191">`/Library/Application Support/Microsoft/Defender/quarantine/`enthält die Dateien, die in Quarantäne gestellt werden. `mdatp`</span><span class="sxs-lookup"><span data-stu-id="8f231-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="8f231-192">Die Dateien werden nach der Bedrohungsverfolgungs-ID benannt.</span><span class="sxs-lookup"><span data-stu-id="8f231-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="8f231-193">Die aktuellen TrackingIds werden mit `mdatp threat list` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f231-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="8f231-194">Informationen zum Microsoft Defender für Endpunkt-Portal</span><span class="sxs-lookup"><span data-stu-id="8f231-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="8f231-195">[EDR Funktionen für macOS sind nun im](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)Microsoft Defender für Endpunkt-Blog angekommen und bieten detaillierte Anleitungen dazu, was Sie in Microsoft Defender für Endpoint Security Center erwarten können.</span><span class="sxs-lookup"><span data-stu-id="8f231-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
