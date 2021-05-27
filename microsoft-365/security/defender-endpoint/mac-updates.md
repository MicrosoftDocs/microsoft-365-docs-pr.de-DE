---
title: Bereitstellen von Updates für Microsoft Defender for Endpoint auf Dem Mac
description: Steuern von Updates für Microsoft Defender for Endpoint auf Mac in Unternehmensumgebungen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
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
ms.openlocfilehash: e08781455888595d57bd8a9e6f792796ea1853cd
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684207"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5b27c-104">Bereitstellen von Updates für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="5b27c-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5b27c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5b27c-105">**Applies to:**</span></span>

- [<span data-ttu-id="5b27c-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="5b27c-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="5b27c-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5b27c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5b27c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b27c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5b27c-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5b27c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b27c-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5b27c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5b27c-111">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5b27c-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="5b27c-112">Zum Aktualisieren von Microsoft Defender for Endpoint auf macOS wird ein Programm mit dem Namen Microsoft AutoUpdate (MAU) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b27c-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="5b27c-113">Mau sucht standardmäßig täglich automatisch nach Updates, Sie können dies jedoch wöchentlich, monatlich oder manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="5b27c-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU-Screenshot](images/MDATP-34-MAU.png)

<span data-ttu-id="5b27c-115">Wenn Sie sich für die Bereitstellung von Updates mit Ihren Softwareverteilungstools entscheiden, sollten Sie MAU so konfigurieren, dass sie manuell auf Softwareupdates überprüft.</span><span class="sxs-lookup"><span data-stu-id="5b27c-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="5b27c-116">Sie können Einstellungen bereitstellen, um zu konfigurieren, wie und wann MAU nach Updates für die Macs in Ihrer Organisation sucht.</span><span class="sxs-lookup"><span data-stu-id="5b27c-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="5b27c-117">Msupdate verwenden</span><span class="sxs-lookup"><span data-stu-id="5b27c-117">Use msupdate</span></span>

<span data-ttu-id="5b27c-118">MAU enthält ein Befehlszeilentool namens *msupdate,* das für IT-Administratoren entwickelt wurde, damit sie präziser steuern können, wann Updates angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="5b27c-119">Anweisungen zur Verwendung dieses Tools finden Sie unter [Update Office für Mac using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="5b27c-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="5b27c-120">In MAU ist die Anwendungs-ID für Microsoft Defender for Endpoint auf macOS *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="5b27c-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="5b27c-121">Führen Sie den folgenden Befehl aus einem Terminalfenster aus, um die neuesten Updates für Microsoft Defender for Endpoint unter macOS herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="5b27c-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="5b27c-122">Festlegen von Einstellungen für Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="5b27c-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="5b27c-123">In diesem Abschnitt werden die gängigsten Einstellungen beschrieben, die zum Konfigurieren von MAU verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5b27c-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="5b27c-124">Diese Einstellungen können als Konfigurationsprofil über die Verwaltungskonsole bereitgestellt werden, die Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b27c-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="5b27c-125">Ein Beispiel für ein Konfigurationsprofil wird in den folgenden Abschnitten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b27c-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="5b27c-126">Festlegen des Kanalnamens</span><span class="sxs-lookup"><span data-stu-id="5b27c-126">Set the channel name</span></span>

<span data-ttu-id="5b27c-127">Der Kanal bestimmt den Typ und die Häufigkeit von Updates, die über MAU angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="5b27c-128">Geräte in `Beta` können neue Features ausprobieren, bevor Geräte in `Preview` und verwendet `Current` werden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="5b27c-129">Der `Current` Kanal enthält die stabilste Version des Produkts.</span><span class="sxs-lookup"><span data-stu-id="5b27c-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="5b27c-130">Vor Microsoft AutoUpdate, Version 4.29, hatten Kanäle unterschiedliche Namen:</span><span class="sxs-lookup"><span data-stu-id="5b27c-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="5b27c-131">`Beta` wurde benannt `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="5b27c-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="5b27c-132">`Preview` wurde benannt `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="5b27c-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="5b27c-133">`Current` wurde benannt `Production`</span><span class="sxs-lookup"><span data-stu-id="5b27c-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="5b27c-134">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen auf oder `Beta` zu `Preview` konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5b27c-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="5b27c-135">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-135">Section</span></span>|<span data-ttu-id="5b27c-136">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-137">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-138">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-138">**Key**</span></span> | <span data-ttu-id="5b27c-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="5b27c-139">ChannelName</span></span> |
| <span data-ttu-id="5b27c-140">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-140">**Data type**</span></span> | <span data-ttu-id="5b27c-141">String</span><span class="sxs-lookup"><span data-stu-id="5b27c-141">String</span></span> |
| <span data-ttu-id="5b27c-142">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="5b27c-142">**Possible values**</span></span> | <span data-ttu-id="5b27c-143">Beta</span><span class="sxs-lookup"><span data-stu-id="5b27c-143">Beta</span></span> <br/> <span data-ttu-id="5b27c-144">Vorschau</span><span class="sxs-lookup"><span data-stu-id="5b27c-144">Preview</span></span> <br/> <span data-ttu-id="5b27c-145">Current</span><span class="sxs-lookup"><span data-stu-id="5b27c-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="5b27c-146">Mit dieser Einstellung wird der Kanal für alle Anwendungen geändert, die über Microsoft AutoUpdate aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="5b27c-147">Um den Kanal nur für Microsoft Defender for Endpoint unter macOS zu ändern, führen Sie nach dem Ersetzen durch den gewünschten Kanal den folgenden `[channel-name]` Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5b27c-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="5b27c-148">Festlegen der Häufigkeit der Aktualisierungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="5b27c-148">Set update check frequency</span></span>

<span data-ttu-id="5b27c-149">Ändern Sie, wie oft MAU nach Updates sucht.</span><span class="sxs-lookup"><span data-stu-id="5b27c-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="5b27c-150">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-150">Section</span></span>|<span data-ttu-id="5b27c-151">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-152">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-153">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-153">**Key**</span></span> | <span data-ttu-id="5b27c-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="5b27c-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="5b27c-155">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-155">**Data type**</span></span> | <span data-ttu-id="5b27c-156">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="5b27c-156">Integer</span></span> |
| <span data-ttu-id="5b27c-157">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="5b27c-157">**Default value**</span></span> | <span data-ttu-id="5b27c-158">720 (Minuten)</span><span class="sxs-lookup"><span data-stu-id="5b27c-158">720 (minutes)</span></span> |
| <span data-ttu-id="5b27c-159">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="5b27c-159">**Comment**</span></span> | <span data-ttu-id="5b27c-160">Dieser Wert wird in Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5b27c-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="5b27c-161">Ändern der Interaktion von MAU mit Updates</span><span class="sxs-lookup"><span data-stu-id="5b27c-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="5b27c-162">Ändern sie, wie MAU nach Updates sucht.</span><span class="sxs-lookup"><span data-stu-id="5b27c-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="5b27c-163">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-163">Section</span></span>|<span data-ttu-id="5b27c-164">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-165">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-166">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-166">**Key**</span></span> | <span data-ttu-id="5b27c-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="5b27c-167">HowToCheck</span></span> |
| <span data-ttu-id="5b27c-168">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-168">**Data type**</span></span> | <span data-ttu-id="5b27c-169">String</span><span class="sxs-lookup"><span data-stu-id="5b27c-169">String</span></span> |
| <span data-ttu-id="5b27c-170">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="5b27c-170">**Possible values**</span></span> | <span data-ttu-id="5b27c-171">Manuell</span><span class="sxs-lookup"><span data-stu-id="5b27c-171">Manual</span></span> <br/> <span data-ttu-id="5b27c-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="5b27c-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="5b27c-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="5b27c-173">AutomaticDownload</span></span> |
| <span data-ttu-id="5b27c-174">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="5b27c-174">**Comment**</span></span> |  <span data-ttu-id="5b27c-175">Beachten Sie, dass AutomaticDownload nach Möglichkeit automatisch heruntergeladen und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b27c-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="5b27c-176">Ändern, ob die Schaltfläche "Auf Updates überprüfen" aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="5b27c-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="5b27c-177">Ändern Sie, ob lokale Benutzer auf der Benutzeroberfläche von Microsoft AutoUpdate auf die Option "Nach Updates suchen" klicken können.</span><span class="sxs-lookup"><span data-stu-id="5b27c-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="5b27c-178">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-178">Section</span></span>|<span data-ttu-id="5b27c-179">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-180">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-181">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-181">**Key**</span></span> | <span data-ttu-id="5b27c-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="5b27c-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="5b27c-183">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-183">**Data type**</span></span> | <span data-ttu-id="5b27c-184">Boolesch</span><span class="sxs-lookup"><span data-stu-id="5b27c-184">Boolean</span></span> |
| <span data-ttu-id="5b27c-185">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="5b27c-185">**Possible values**</span></span> | <span data-ttu-id="5b27c-186">True (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b27c-186">True (default)</span></span> <br/> <span data-ttu-id="5b27c-187">Falsch</span><span class="sxs-lookup"><span data-stu-id="5b27c-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="5b27c-188">Kontrollkästchen Insider deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5b27c-188">Disable Insider checkbox</span></span>

<span data-ttu-id="5b27c-189">Auf true festgelegt, um das "Join the Office Insider Program..." zu erstellen. Kontrollkästchen für Benutzer nicht verfügbar/ausgegraut.</span><span class="sxs-lookup"><span data-stu-id="5b27c-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="5b27c-190">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-190">Section</span></span>|<span data-ttu-id="5b27c-191">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-192">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-193">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-193">**Key**</span></span> | <span data-ttu-id="5b27c-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="5b27c-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="5b27c-195">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-195">**Data type**</span></span> | <span data-ttu-id="5b27c-196">Boolesch</span><span class="sxs-lookup"><span data-stu-id="5b27c-196">Boolean</span></span> |
| <span data-ttu-id="5b27c-197">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="5b27c-197">**Possible values**</span></span> | <span data-ttu-id="5b27c-198">False (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b27c-198">False (default)</span></span> <br/> <span data-ttu-id="5b27c-199">Wahr</span><span class="sxs-lookup"><span data-stu-id="5b27c-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="5b27c-200">Einschränken der Telemetrie, die von MAU gesendet wird</span><span class="sxs-lookup"><span data-stu-id="5b27c-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="5b27c-201">Auf false festgelegt, um minimale Taktdaten, keine Anwendungsverwendung und keine Umgebungsdetails zu senden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="5b27c-202">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b27c-202">Section</span></span>|<span data-ttu-id="5b27c-203">Wert</span><span class="sxs-lookup"><span data-stu-id="5b27c-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="5b27c-204">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="5b27c-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="5b27c-205">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="5b27c-205">**Key**</span></span> | <span data-ttu-id="5b27c-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="5b27c-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="5b27c-207">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5b27c-207">**Data type**</span></span> | <span data-ttu-id="5b27c-208">Boolesch</span><span class="sxs-lookup"><span data-stu-id="5b27c-208">Boolean</span></span> |
| <span data-ttu-id="5b27c-209">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="5b27c-209">**Possible values**</span></span> | <span data-ttu-id="5b27c-210">True (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b27c-210">True (default)</span></span> <br/> <span data-ttu-id="5b27c-211">Falsch</span><span class="sxs-lookup"><span data-stu-id="5b27c-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="5b27c-212">Beispielkonfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5b27c-212">Example configuration profile</span></span>

<span data-ttu-id="5b27c-213">Das folgende Konfigurationsprofil wird verwendet für:</span><span class="sxs-lookup"><span data-stu-id="5b27c-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="5b27c-214">Platzieren des Geräts im Produktionskanal</span><span class="sxs-lookup"><span data-stu-id="5b27c-214">Place the device in the Production channel</span></span>
- <span data-ttu-id="5b27c-215">Updates automatisch herunterladen und installieren</span><span class="sxs-lookup"><span data-stu-id="5b27c-215">Automatically download and install updates</span></span>
- <span data-ttu-id="5b27c-216">Aktivieren der Schaltfläche "Auf Updates überprüfen" auf der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="5b27c-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="5b27c-217">Zulassen, dass Sich Benutzer auf dem Gerät bei den Insiderkanälen registrieren</span><span class="sxs-lookup"><span data-stu-id="5b27c-217">Allow users on the device to enroll into the Insider channels</span></span>


>[!WARNING]
><span data-ttu-id="5b27c-218">Die folgende Konfiguration ist eine Beispielkonfiguration und sollte nicht in der Produktion ohne ordnungsgemäße Überprüfung der Einstellungen und Anpassung der Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b27c-218">The below configuration is an example configuration and should not be used in production without proper review of settings and tailor of configurations.</span></span>

>[!TIP]
><span data-ttu-id="5b27c-219">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen auf oder `Beta` zu `Preview` konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5b27c-219">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

### <a name="jamf"></a><span data-ttu-id="5b27c-220">JAMF</span><span class="sxs-lookup"><span data-stu-id="5b27c-220">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="5b27c-221">Intune</span><span class="sxs-lookup"><span data-stu-id="5b27c-221">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="5b27c-222">Zum Konfigurieren von MAU können Sie dieses Konfigurationsprofil über das Verwaltungstool bereitstellen, das Ihr Unternehmen verwendet:</span><span class="sxs-lookup"><span data-stu-id="5b27c-222">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="5b27c-223">Laden Sie aus JAMF dieses Konfigurationsprofil hoch, und legen Sie die Einstellungsdomäne *auf com.microsoft.autoupdate2 fest.*</span><span class="sxs-lookup"><span data-stu-id="5b27c-223">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="5b27c-224">Laden Sie in Intune dieses Konfigurationsprofil hoch, und legen Sie den namen des benutzerdefinierten *Konfigurationsprofils auf com.microsoft.autoupdate2 .*</span><span class="sxs-lookup"><span data-stu-id="5b27c-224">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="5b27c-225">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b27c-225">Resources</span></span>

- [<span data-ttu-id="5b27c-226">msupdate-Referenz</span><span class="sxs-lookup"><span data-stu-id="5b27c-226">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
