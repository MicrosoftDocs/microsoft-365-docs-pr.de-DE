---
title: Bereitstellen von Updates für Microsoft Defender for Endpoint für Mac
description: Steuern von Updates für Microsoft Defender for Endpoint für Mac in Unternehmensumgebungen.
keywords: microsoft, defender, atp, mac, updates, deploy
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
ms.openlocfilehash: 9d373594771efe4eb647c007db3a26efe83e330e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860315"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c28f1-104">Bereitstellen von Updates für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="c28f1-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c28f1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c28f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="c28f1-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="c28f1-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c28f1-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c28f1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c28f1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c28f1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c28f1-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c28f1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c28f1-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c28f1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c28f1-111">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c28f1-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="c28f1-112">Zum Aktualisieren von Microsoft Defender for Endpoint auf macOS wird ein Programm mit dem Namen Microsoft AutoUpdate (MAU) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c28f1-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="c28f1-113">Mau sucht standardmäßig täglich automatisch nach Updates, Sie können dies jedoch wöchentlich, monatlich oder manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="c28f1-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU-Screenshot](images/MDATP-34-MAU.png)

<span data-ttu-id="c28f1-115">Wenn Sie sich für die Bereitstellung von Updates mit Ihren Softwareverteilungstools entscheiden, sollten Sie MAU so konfigurieren, dass sie manuell auf Softwareupdates überprüft.</span><span class="sxs-lookup"><span data-stu-id="c28f1-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="c28f1-116">Sie können Einstellungen bereitstellen, um zu konfigurieren, wie und wann MAU nach Updates für die Macs in Ihrer Organisation sucht.</span><span class="sxs-lookup"><span data-stu-id="c28f1-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="c28f1-117">Msupdate verwenden</span><span class="sxs-lookup"><span data-stu-id="c28f1-117">Use msupdate</span></span>

<span data-ttu-id="c28f1-118">MAU enthält ein Befehlszeilentool namens *msupdate,* das für IT-Administratoren entwickelt wurde, damit sie präziser steuern können, wann Updates angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c28f1-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="c28f1-119">Anweisungen zur Verwendung dieses Tools finden Sie unter [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="c28f1-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="c28f1-120">In MAU ist die Anwendungs-ID für Microsoft Defender for Endpoint auf macOS *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="c28f1-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="c28f1-121">Führen Sie den folgenden Befehl aus einem Terminalfenster aus, um die neuesten Updates für Microsoft Defender for Endpoint unter macOS herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="c28f1-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="c28f1-122">Festlegen von Einstellungen für Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="c28f1-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="c28f1-123">In diesem Abschnitt werden die gängigsten Einstellungen beschrieben, die zum Konfigurieren von MAU verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c28f1-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="c28f1-124">Diese Einstellungen können als Konfigurationsprofil über die Verwaltungskonsole bereitgestellt werden, die Ihr Unternehmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c28f1-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="c28f1-125">Ein Beispiel für ein Konfigurationsprofil wird in den folgenden Abschnitten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c28f1-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="c28f1-126">Festlegen des Kanalnamens</span><span class="sxs-lookup"><span data-stu-id="c28f1-126">Set the channel name</span></span>

<span data-ttu-id="c28f1-127">Der Kanal bestimmt den Typ und die Häufigkeit von Updates, die über MAU angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="c28f1-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="c28f1-128">Geräte in `Beta` können neue Features ausprobieren, bevor Geräte in `Preview` und verwendet `Current` werden.</span><span class="sxs-lookup"><span data-stu-id="c28f1-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="c28f1-129">Der `Current` Kanal enthält die stabilste Version des Produkts.</span><span class="sxs-lookup"><span data-stu-id="c28f1-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c28f1-130">Vor Microsoft AutoUpdate, Version 4.29, hatten Kanäle unterschiedliche Namen:</span><span class="sxs-lookup"><span data-stu-id="c28f1-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="c28f1-131">`Beta` wurde benannt `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="c28f1-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="c28f1-132">`Preview` wurde benannt `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="c28f1-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="c28f1-133">`Current` wurde benannt `Production`</span><span class="sxs-lookup"><span data-stu-id="c28f1-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="c28f1-134">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen auf oder `Beta` zu `Preview` konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c28f1-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="c28f1-135">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-135">Section</span></span>|<span data-ttu-id="c28f1-136">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-137">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-138">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-138">**Key**</span></span> | <span data-ttu-id="c28f1-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="c28f1-139">ChannelName</span></span> |
| <span data-ttu-id="c28f1-140">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-140">**Data type**</span></span> | <span data-ttu-id="c28f1-141">String</span><span class="sxs-lookup"><span data-stu-id="c28f1-141">String</span></span> |
| <span data-ttu-id="c28f1-142">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="c28f1-142">**Possible values**</span></span> | <span data-ttu-id="c28f1-143">Beta</span><span class="sxs-lookup"><span data-stu-id="c28f1-143">Beta</span></span> <br/> <span data-ttu-id="c28f1-144">Vorschau</span><span class="sxs-lookup"><span data-stu-id="c28f1-144">Preview</span></span> <br/> <span data-ttu-id="c28f1-145">Current</span><span class="sxs-lookup"><span data-stu-id="c28f1-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="c28f1-146">Mit dieser Einstellung wird der Kanal für alle Anwendungen geändert, die über Microsoft AutoUpdate aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c28f1-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="c28f1-147">Um den Kanal nur für Microsoft Defender for Endpoint unter macOS zu ändern, führen Sie nach dem Ersetzen durch den gewünschten Kanal den folgenden `[channel-name]` Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c28f1-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="c28f1-148">Festlegen der Häufigkeit der Aktualisierungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="c28f1-148">Set update check frequency</span></span>

<span data-ttu-id="c28f1-149">Ändern Sie, wie oft MAU nach Updates sucht.</span><span class="sxs-lookup"><span data-stu-id="c28f1-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="c28f1-150">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-150">Section</span></span>|<span data-ttu-id="c28f1-151">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-152">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-153">**Key**</span></span> | <span data-ttu-id="c28f1-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="c28f1-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="c28f1-155">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-155">**Data type**</span></span> | <span data-ttu-id="c28f1-156">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="c28f1-156">Integer</span></span> |
| <span data-ttu-id="c28f1-157">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="c28f1-157">**Default value**</span></span> | <span data-ttu-id="c28f1-158">720 (Minuten)</span><span class="sxs-lookup"><span data-stu-id="c28f1-158">720 (minutes)</span></span> |
| <span data-ttu-id="c28f1-159">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="c28f1-159">**Comment**</span></span> | <span data-ttu-id="c28f1-160">Dieser Wert wird in Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c28f1-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="c28f1-161">Ändern der Interaktion von MAU mit Updates</span><span class="sxs-lookup"><span data-stu-id="c28f1-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="c28f1-162">Ändern sie, wie MAU nach Updates sucht.</span><span class="sxs-lookup"><span data-stu-id="c28f1-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="c28f1-163">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-163">Section</span></span>|<span data-ttu-id="c28f1-164">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-165">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-166">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-166">**Key**</span></span> | <span data-ttu-id="c28f1-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="c28f1-167">HowToCheck</span></span> |
| <span data-ttu-id="c28f1-168">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-168">**Data type**</span></span> | <span data-ttu-id="c28f1-169">String</span><span class="sxs-lookup"><span data-stu-id="c28f1-169">String</span></span> |
| <span data-ttu-id="c28f1-170">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="c28f1-170">**Possible values**</span></span> | <span data-ttu-id="c28f1-171">Manuell</span><span class="sxs-lookup"><span data-stu-id="c28f1-171">Manual</span></span> <br/> <span data-ttu-id="c28f1-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="c28f1-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="c28f1-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="c28f1-173">AutomaticDownload</span></span> |
| <span data-ttu-id="c28f1-174">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="c28f1-174">**Comment**</span></span> |  <span data-ttu-id="c28f1-175">Beachten Sie, dass AutomaticDownload nach Möglichkeit automatisch heruntergeladen und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c28f1-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="c28f1-176">Ändern, ob die Schaltfläche "Auf Updates überprüfen" aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c28f1-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="c28f1-177">Ändern Sie, ob lokale Benutzer auf der Benutzeroberfläche von Microsoft AutoUpdate auf die Option "Nach Updates suchen" klicken können.</span><span class="sxs-lookup"><span data-stu-id="c28f1-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="c28f1-178">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-178">Section</span></span>|<span data-ttu-id="c28f1-179">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-180">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-181">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-181">**Key**</span></span> | <span data-ttu-id="c28f1-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="c28f1-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="c28f1-183">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-183">**Data type**</span></span> | <span data-ttu-id="c28f1-184">Boolesch</span><span class="sxs-lookup"><span data-stu-id="c28f1-184">Boolean</span></span> |
| <span data-ttu-id="c28f1-185">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="c28f1-185">**Possible values**</span></span> | <span data-ttu-id="c28f1-186">True (Standard)</span><span class="sxs-lookup"><span data-stu-id="c28f1-186">True (default)</span></span> <br/> <span data-ttu-id="c28f1-187">Falsch</span><span class="sxs-lookup"><span data-stu-id="c28f1-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="c28f1-188">Kontrollkästchen Insider deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c28f1-188">Disable Insider checkbox</span></span>

<span data-ttu-id="c28f1-189">Auf true festgelegt, um die "Teilnahme am Office-Insider-Programm..." zu erstellen. Kontrollkästchen für Benutzer nicht verfügbar/ausgegraut.</span><span class="sxs-lookup"><span data-stu-id="c28f1-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="c28f1-190">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-190">Section</span></span>|<span data-ttu-id="c28f1-191">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-192">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-193">**Key**</span></span> | <span data-ttu-id="c28f1-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="c28f1-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="c28f1-195">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-195">**Data type**</span></span> | <span data-ttu-id="c28f1-196">Boolesch</span><span class="sxs-lookup"><span data-stu-id="c28f1-196">Boolean</span></span> |
| <span data-ttu-id="c28f1-197">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="c28f1-197">**Possible values**</span></span> | <span data-ttu-id="c28f1-198">False (Standard)</span><span class="sxs-lookup"><span data-stu-id="c28f1-198">False (default)</span></span> <br/> <span data-ttu-id="c28f1-199">Wahr</span><span class="sxs-lookup"><span data-stu-id="c28f1-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="c28f1-200">Einschränken der Telemetrie, die von MAU gesendet wird</span><span class="sxs-lookup"><span data-stu-id="c28f1-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="c28f1-201">Auf false festgelegt, um minimale Taktdaten, keine Anwendungsverwendung und keine Umgebungsdetails zu senden.</span><span class="sxs-lookup"><span data-stu-id="c28f1-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="c28f1-202">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c28f1-202">Section</span></span>|<span data-ttu-id="c28f1-203">Wert</span><span class="sxs-lookup"><span data-stu-id="c28f1-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c28f1-204">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c28f1-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c28f1-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="c28f1-205">**Key**</span></span> | <span data-ttu-id="c28f1-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="c28f1-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="c28f1-207">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c28f1-207">**Data type**</span></span> | <span data-ttu-id="c28f1-208">Boolesch</span><span class="sxs-lookup"><span data-stu-id="c28f1-208">Boolean</span></span> |
| <span data-ttu-id="c28f1-209">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="c28f1-209">**Possible values**</span></span> | <span data-ttu-id="c28f1-210">True (Standard)</span><span class="sxs-lookup"><span data-stu-id="c28f1-210">True (default)</span></span> <br/> <span data-ttu-id="c28f1-211">Falsch</span><span class="sxs-lookup"><span data-stu-id="c28f1-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="c28f1-212">Beispielkonfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="c28f1-212">Example configuration profile</span></span>

<span data-ttu-id="c28f1-213">Das folgende Konfigurationsprofil wird verwendet für:</span><span class="sxs-lookup"><span data-stu-id="c28f1-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="c28f1-214">Platzieren des Geräts im Betakanal</span><span class="sxs-lookup"><span data-stu-id="c28f1-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="c28f1-215">Updates automatisch herunterladen und installieren</span><span class="sxs-lookup"><span data-stu-id="c28f1-215">Automatically download and install updates</span></span>
- <span data-ttu-id="c28f1-216">Aktivieren der Schaltfläche "Auf Updates überprüfen" auf der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="c28f1-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="c28f1-217">Zulassen, dass Sich Benutzer auf dem Gerät bei den Insiderkanälen registrieren</span><span class="sxs-lookup"><span data-stu-id="c28f1-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="c28f1-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="c28f1-218">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
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

### <a name="intune"></a><span data-ttu-id="c28f1-219">Intune</span><span class="sxs-lookup"><span data-stu-id="c28f1-219">Intune</span></span>

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
            <string>Beta</string>
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

<span data-ttu-id="c28f1-220">Zum Konfigurieren von MAU können Sie dieses Konfigurationsprofil über das Verwaltungstool bereitstellen, das Ihr Unternehmen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c28f1-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="c28f1-221">Laden Sie aus JAMF dieses Konfigurationsprofil hoch, und legen Sie die Einstellungsdomäne *auf com.microsoft.autoupdate2 fest.*</span><span class="sxs-lookup"><span data-stu-id="c28f1-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="c28f1-222">Laden Sie in Intune dieses Konfigurationsprofil hoch, und legen Sie den namen des benutzerdefinierten *Konfigurationsprofils auf com.microsoft.autoupdate2 .*</span><span class="sxs-lookup"><span data-stu-id="c28f1-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="c28f1-223">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c28f1-223">Resources</span></span>

- [<span data-ttu-id="c28f1-224">msupdate-Referenz</span><span class="sxs-lookup"><span data-stu-id="c28f1-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
