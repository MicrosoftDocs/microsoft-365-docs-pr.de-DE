---
title: Manuelle Bereitstellung für Microsoft Defender for Endpoint unter macOS
description: Installieren Sie Microsoft Defender for Endpoint auf macOS manuell über die Befehlszeile.
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935329"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="7e4b4-104">Manuelle Bereitstellung für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="7e4b4-104">Manual deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e4b4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e4b4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7e4b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7e4b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e4b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7e4b4-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7e4b4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7e4b4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7e4b4-110">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint manuell auf macOS bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-110">This topic describes how to deploy Microsoft Defender for Endpoint on macOS manually.</span></span> <span data-ttu-id="7e4b4-111">Für eine erfolgreiche Bereitstellung sind alle folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="7e4b4-112">Herunterladen von Installations- und Onboardingpaketen</span><span class="sxs-lookup"><span data-stu-id="7e4b4-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="7e4b4-113">Anwendungsinstallation (macOS 10.15 und ältere Versionen)</span><span class="sxs-lookup"><span data-stu-id="7e4b4-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="7e4b4-114">Anwendungsinstallation (macOS 11 und neuere Versionen)</span><span class="sxs-lookup"><span data-stu-id="7e4b4-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="7e4b4-115">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7e4b4-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="7e4b4-116">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="7e4b4-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="7e4b4-117">Bevor Sie beginnen, finden Sie auf der [Hauptseite von Microsoft Defender for Endpoint auf macOS](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-117">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="7e4b4-118">Herunterladen von Installations- und Onboardingpaketen</span><span class="sxs-lookup"><span data-stu-id="7e4b4-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="7e4b4-119">Laden Sie die Installations- und Onboardingpakete von Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="7e4b4-120">Wechseln Microsoft Defender Security Center zu Einstellungen > **Device Management > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="7e4b4-121">Legen Sie in Abschnitt 1 der Seite das Betriebssystem auf **macOS** und die Deployment-Methode auf **Lokales Skript .**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="7e4b4-122">Wählen Sie in Abschnitt 2 der Seite **Installationspaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="7e4b4-123">Speichern Sie es als wdav.pkg in einem lokalen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="7e4b4-124">Wählen Sie in Abschnitt 2 der Seite Die Option **Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="7e4b4-125">Speichern Sie es WindowsDefenderATPOnboardingPackage.zip im gleichen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender Security Center Screenshot](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="7e4b4-127">Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die beiden Dateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="7e4b4-128">Anwendungsinstallation (macOS 10.15 und ältere Versionen)</span><span class="sxs-lookup"><span data-stu-id="7e4b4-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="7e4b4-129">Zum Abschließen dieses Vorgangs müssen Sie über Administratorrechte auf dem Gerät verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="7e4b4-130">Navigieren Sie zum heruntergeladenen wdav.pkg in Finder, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Screenshot der App-Installation1](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="7e4b4-132">Wählen **Sie Weiter** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Screenshot der App-Installation2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="7e4b4-134">Sie werden aufgefordert, die Installation eines Treibers von Microsoft zu erlauben (entweder "Systemerweiterung blockiert" oder "Installation ist gesperrt" oder beides.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="7e4b4-135">Der Treiber muss installiert werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-135">The driver must be allowed to be installed.</span></span>

   ![Screenshot der App-Installation3](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="7e4b4-137">Wählen **Sie Open Security Preferences** oder Open System **Preferences > Security & Privacy aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="7e4b4-138">Wählen Sie **Zulassen** aus:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-138">Select **Allow**:</span></span>

    ![Screenshot des Sicherheits- und Datenschutzfensters](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="7e4b4-140">Die Installation wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="7e4b4-141">Wenn Sie nicht zulassen **auswählen,** wird die Installation nach 5 Minuten fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="7e4b4-142">Microsoft Defender for Endpoint wird geladen, aber einige Features, z. B. der Echtzeitschutz, werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="7e4b4-143">Informationen [zur Lösung dieses Problems finden](mac-support-kext.md) Sie unter Problembehandlung bei Kernelerweiterungen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="7e4b4-144">MacOS kann bei der ersten Installation von Microsoft Defender for Endpoint den Neustart des Geräts anfordern.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7e4b4-145">Echtzeitschutz ist erst verfügbar, wenn das Gerät neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="7e4b4-146">Anwendungsinstallation (macOS 11 und neuere Versionen)</span><span class="sxs-lookup"><span data-stu-id="7e4b4-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="7e4b4-147">Zum Abschließen dieses Vorgangs müssen Sie über Administratorrechte auf dem Gerät verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="7e4b4-148">Navigieren Sie zum heruntergeladenen wdav.pkg in Finder, und öffnen Sie es.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Screenshot der App-Installation4](images/big-sur-install-1.png)

2. <span data-ttu-id="7e4b4-150">Wählen **Sie Weiter** aus, stimmen Sie den Lizenzbedingungen zu, und geben Sie das Kennwort ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="7e4b4-151">Am Ende des Installationsprozesses werden Sie heraufgestuft, um die vom Produkt verwendeten Systemerweiterungen zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="7e4b4-152">Wählen **Sie Sicherheitseinstellungen öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-152">Select **Open Security Preferences**.</span></span>

    ![Systemerweiterungsgenehmigung](images/big-sur-install-2.png)

4. <span data-ttu-id="7e4b4-154">Wählen Sie **im Fenster & Datenschutz** die Option Zulassen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Sicherheitseinstellungen für Systemerweiterungen1](images/big-sur-install-3.png)

5. <span data-ttu-id="7e4b4-156">Wiederholen Sie die Schritte 3 & 4 für alle Systemerweiterungen, die mit Microsoft Defender for Endpoint auf Dem Mac verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint on Mac.</span></span>

6. <span data-ttu-id="7e4b4-157">Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint auf Mac den Socketdatenverkehr und meldet diese Informationen Microsoft Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="7e4b4-158">Wenn Sie aufgefordert werden, Microsoft Defender for Endpoint Berechtigungen zum Filtern von Netzwerkdatenverkehr zu erteilen, wählen Sie **Zulassen aus.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Sicherheitseinstellungen für Systemerweiterungen2](images/big-sur-install-4.png)

7. <span data-ttu-id="7e4b4-160">Öffnen **Sie Systemeinstellungen** Sicherheit & Datenschutz, und navigieren Sie zur Registerkarte Datenschutz. Erteilen Sie der Endpunktsicherheitserweiterung Microsoft Defender ATP und Microsoft Defender ATP die Berechtigung "Vollständiger  >   **Datenträgerzugriff".**   </span><span class="sxs-lookup"><span data-stu-id="7e4b4-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Vollständiger Datenträgerzugriff](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="7e4b4-162">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7e4b4-162">Client configuration</span></span>

1. <span data-ttu-id="7e4b4-163">Kopieren Sie wdav.pkg und MicrosoftDefenderATPOnboardingMacOs.py auf das Gerät, auf dem Sie Microsoft Defender for Endpoint unter macOS bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint on macOS.</span></span>

    <span data-ttu-id="7e4b4-164">Das Clientgerät ist nicht mit org_id.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-164">The client device isn't associated with org_id.</span></span> <span data-ttu-id="7e4b4-165">Beachten Sie, *dass org_id-Attribut* leer ist.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-165">Note that the *org_id* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="7e4b4-166">Führen Sie das Python-Skript aus, um die Konfigurationsdatei zu installieren:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="7e4b4-167">Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und melden Sie eine gültige Organisations-ID:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-167">Verify that the device is now associated with your organization and reports a valid org ID:</span></span>

    ```bash
    mdatp health --field org_id
    ```

    <span data-ttu-id="7e4b4-168">Nach der Installation wird das Microsoft Defender-Symbol in der macOS-Statusleiste in der oberen rechten Ecke angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7e4b4-169">![Microsoft Defender-Symbol im Screenshot der Statusleiste](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="7e4b4-169">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>


## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="7e4b4-170">Zulassen des vollständigen Festplattenzugriffs</span><span class="sxs-lookup"><span data-stu-id="7e4b4-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="7e4b4-171">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="7e4b4-172">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="7e4b4-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="7e4b4-173">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

1. <span data-ttu-id="7e4b4-174">Um die Zustimmung zu erteilen, öffnen Sie **system preferences**  >  **Security & Privacy**  >  **Privacy** Full  >  **Disk Access**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-174">To grant consent, open **System Preferences** > **Security & Privacy** > **Privacy** > **Full Disk Access**.</span></span> <span data-ttu-id="7e4b4-175">Klicken Sie auf das Sperrsymbol, um Änderungen vorzunehmen (unten im Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="7e4b4-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="7e4b4-176">Wählen Sie Microsoft Defender for Endpoint aus.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-176">Select Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="7e4b4-177">Führen Sie einen AV-Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-177">Run an AV detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="7e4b4-178">Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-178">Perform the following steps on the newly onboarded device:</span></span>

    1. <span data-ttu-id="7e4b4-179">Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (wird durch ein Ergebnis von 1 davon bezeichnet, dass der folgende Befehl ausgeführt wird):</span><span class="sxs-lookup"><span data-stu-id="7e4b4-179">Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. <span data-ttu-id="7e4b4-180">Öffnen Sie ein Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-180">Open a Terminal window.</span></span> <span data-ttu-id="7e4b4-181">Kopieren Sie den folgenden Befehl, und führen Sie diesen aus:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-181">Copy and execute the following command:</span></span>

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. <span data-ttu-id="7e4b4-182">Die Datei sollte von Defender for Endpoint auf Dem Mac isoliert worden sein.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-182">The file should have been quarantined by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="7e4b4-183">Verwenden Sie den folgenden Befehl, um alle erkannten Bedrohungen auflisten:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-183">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

3. <span data-ttu-id="7e4b4-184">Führen Sie EDR Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-184">Run an EDR detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="7e4b4-185">Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-185">Perform the following steps on the newly onboarded device:</span></span>

   1. <span data-ttu-id="7e4b4-186">In Ihrem Browser, z. B. Microsoft Edge für Mac oder Safari.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-186">In your browser such as Microsoft Edge for Mac or Safari.</span></span>

   1. <span data-ttu-id="7e4b4-187">Laden MDATP MacOS-DIY.zip aus und https://aka.ms/mdatpmacosdiy extrahieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-187">Download MDATP MacOS DIY.zip from https://aka.ms/mdatpmacosdiy and extract.</span></span>

      <span data-ttu-id="7e4b4-188">Möglicherweise werden Sie dazu aufgefordert:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-188">You may be prompted:</span></span>

      > <span data-ttu-id="7e4b4-189">Möchten Sie Downloads auf "mdatpclientanalyzer.blob.core.windows.net" zulassen?</span><span class="sxs-lookup"><span data-stu-id="7e4b4-189">Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?</span></span><br/>
      > <span data-ttu-id="7e4b4-190">Sie können ändern, welche Websites Dateien in den Einstellungen für Websites herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-190">You can change which websites can download files in Websites Preferences.</span></span>

4. <span data-ttu-id="7e4b4-191">Klicken Sie **auf Zulassen**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-191">Click **Allow**.</span></span>

5. <span data-ttu-id="7e4b4-192">Öffnen **Sie Downloads**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-192">Open **Downloads**.</span></span>

6. <span data-ttu-id="7e4b4-193">Sie sollten MDATP **MacOS DIY sehen.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-193">You should see **MDATP MacOS DIY**.</span></span>

   > [!TIP]
   > <span data-ttu-id="7e4b4-194">Wenn Sie doppelklicken, erhalten Sie die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-194">If you double-click, you will get the following message:</span></span>
   > 
   > > <span data-ttu-id="7e4b4-195">**"MDATP MacOS DIY" kann nicht geöffnet werden, da der Entwickler nicht überprüft werden kann.**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-195">**"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**</span></span><br/>
   > > <span data-ttu-id="7e4b4-196">MacOS kann nicht überprüfen, ob diese App frei von Schadsoftware ist.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-196">macOS cannot verify that this app is free from malware.</span></span><br/>
   > > <span data-ttu-id="7e4b4-197">**\[ Move to \] Trash** **\[ Cancel \]**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-197">**\[Move to Trash\]** **\[Cancel\]**</span></span> 
  
7. <span data-ttu-id="7e4b4-198">Klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-198">Click **Cancel**.</span></span>

8. <span data-ttu-id="7e4b4-199">Klicken Sie mit **der rechten MDATP MacOS-HEIMWERKING**, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-199">Right-click **MDATP MacOS DIY**, and then click **Open**.</span></span> 

    <span data-ttu-id="7e4b4-200">Das System sollte die folgende Meldung anzeigen:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-200">The system should display the following message:</span></span>

    > <span data-ttu-id="7e4b4-201">**macOS kann den Entwickler von MDATP **MacOS DIY nicht überprüfen.** Möchten Sie es wirklich öffnen?**</span><span class="sxs-lookup"><span data-stu-id="7e4b4-201">**macOS cannot verify the developer of **MDATP MacOS DIY**. Are you sure you want to open it?**</span></span><br/>
    > <span data-ttu-id="7e4b4-202">Durch das Öffnen dieser App überschreiben Sie die Systemsicherheit, die Ihren Computer und persönliche Informationen Schadsoftware zur Verfügung stellt, die Ihren Mac beeinträchtigt oder Ihre Privatsphäre gefährdet.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-202">By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.</span></span>

10. <span data-ttu-id="7e4b4-203">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-203">Click **Open**.</span></span>

    <span data-ttu-id="7e4b4-204">Das System sollte die folgende Meldung anzeigen:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-204">The system should display the following message:</span></span>

    > <span data-ttu-id="7e4b4-205">Microsoft Defender for Endpoint – macOS EDR -TESTdatei</span><span class="sxs-lookup"><span data-stu-id="7e4b4-205">Microsoft Defender for Endpoint - macOS EDR DIY test file</span></span><br/>
    > <span data-ttu-id="7e4b4-206">Entsprechende Benachrichtigungen sind im MDATP verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-206">Corresponding alert will be available in the MDATP portal.</span></span>

11. <span data-ttu-id="7e4b4-207">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-207">Click **Open**.</span></span>

    <span data-ttu-id="7e4b4-208">In wenigen Minuten sollte eine Warnung namens "macOS EDR Test Alert" ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-208">In a few minutes an alert named "macOS EDR Test Alert" should be raised.</span></span>

12. <span data-ttu-id="7e4b4-209">Wechseln Sie zu Microsoft Defender Security Center ( https://SecurityCenter.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="7e4b4-209">Go to Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).</span></span>

13. <span data-ttu-id="7e4b4-210">Wechseln Sie zur Warnwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-210">Go to the Alert Queue.</span></span>

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Beispiel für eine macOS-EDR, die den Schweregrad, die Kategorie, die Erkennungsquelle und ein reduziertes Menü mit Aktionen zeigt.":::
    
    <span data-ttu-id="7e4b4-212">Sehen Sie sich die Warnungsdetails und die Gerätezeitachse an, und führen Sie die regulären Untersuchungsschritte aus.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-212">Look at the alert details and the device timeline, and perform the regular investigation steps.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="7e4b4-213">Probleme bei der Protokollierung der Installation</span><span class="sxs-lookup"><span data-stu-id="7e4b4-213">Logging installation issues</span></span>

<span data-ttu-id="7e4b4-214">Weitere [Informationen zum](mac-resources.md#logging-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollierungsinstallationsprobleme.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-214">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="7e4b4-215">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="7e4b4-215">Uninstallation</span></span>

<span data-ttu-id="7e4b4-216">Weitere [Informationen zum Entfernen](mac-resources.md#uninstalling) von Microsoft Defender for Endpoint auf macOS von Clientgeräten finden Sie unter Deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-216">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
