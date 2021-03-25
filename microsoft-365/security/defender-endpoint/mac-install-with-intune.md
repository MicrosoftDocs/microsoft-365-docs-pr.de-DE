---
title: Intune-basierte Bereitstellung für Microsoft Defender ATP für Mac
description: Installieren Sie Microsoft Defender für Endpoint für Mac mithilfe von Microsoft Intune.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: cb2923c3f2cb3f27a864fdc3c5070107998823d5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066847"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="77bd2-104">Intune-basierte Bereitstellung für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="77bd2-104">Intune-based deployment for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> <span data-ttu-id="77bd2-105">In dieser Dokumentation wird die ältere Methode zum Bereitstellen und Konfigurieren von Microsoft Defender for Endpoint auf macOS-Geräten erläutert.</span><span class="sxs-lookup"><span data-stu-id="77bd2-105">This documentation explains the legacy method for deploying and configuring Microsoft Defender for Endpoint on macOS devices.</span></span> <span data-ttu-id="77bd2-106">Die systemeigene Benutzererfahrung ist jetzt in der MEM-Konsole verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77bd2-106">The native experience is now available in the MEM console.</span></span> <span data-ttu-id="77bd2-107">Die Veröffentlichung der systemeigenen Benutzeroberfläche in der MEM-Konsole bietet Administratoren eine wesentlich einfachere Möglichkeit, die Anwendung zu konfigurieren und zu bereitstellen und an macOS-Geräte zu senden.</span><span class="sxs-lookup"><span data-stu-id="77bd2-107">The release of the native UI in the MEM console provide admins with a much simpler way to configure and deploy the application and send it down to macOS devices.</span></span> <br> <br>
><span data-ttu-id="77bd2-108">Der Blogbeitrag [MEM vereinfacht die Bereitstellung von Microsoft Defender for Endpoint für macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) und erläutert die neuen Features.</span><span class="sxs-lookup"><span data-stu-id="77bd2-108">The blog post [MEM simplifies deployment of Microsoft Defender for Endpoint for macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explains the new features.</span></span> <span data-ttu-id="77bd2-109">Um die App zu konfigurieren, wechseln Sie zu [Einstellungen für Microsoft Defender for Endpoint für Mac in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span><span class="sxs-lookup"><span data-stu-id="77bd2-109">To configure the app, go to [Settings for Microsoft Defender for Endpoint for Mac in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span></span> <span data-ttu-id="77bd2-110">Um die App bereitzustellen, wechseln Sie zu [Hinzufügen von Microsoft Defender for Endpoint zu macOS-Geräten mithilfe von Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span><span class="sxs-lookup"><span data-stu-id="77bd2-110">To deploy the app, go to [Add Microsoft Defender for Endpoint to macOS devices using Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span></span>

<span data-ttu-id="77bd2-111">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="77bd2-111">**Applies to:**</span></span>

- [<span data-ttu-id="77bd2-112">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="77bd2-112">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="77bd2-113">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint für Mac über Intune bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-113">This topic describes how to deploy Microsoft Defender for Endpoint for Mac through Intune.</span></span> <span data-ttu-id="77bd2-114">Für eine erfolgreiche Bereitstellung sind alle folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="77bd2-114">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="77bd2-115">Herunterladen von Installations- und Onboardingpaketen</span><span class="sxs-lookup"><span data-stu-id="77bd2-115">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
1. [<span data-ttu-id="77bd2-116">Setup des Clientgeräts</span><span class="sxs-lookup"><span data-stu-id="77bd2-116">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="77bd2-117">Genehmigen von Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="77bd2-117">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="77bd2-118">Erstellen von Systemkonfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="77bd2-118">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="77bd2-119">Anwendung veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="77bd2-119">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="77bd2-120">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="77bd2-120">Prerequisites and system requirements</span></span>

<span data-ttu-id="77bd2-121">Bevor Sie beginnen, finden Sie auf der Hauptseite [von Microsoft Defender for Endpoint für Mac](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="77bd2-121">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="77bd2-122">Übersicht</span><span class="sxs-lookup"><span data-stu-id="77bd2-122">Overview</span></span>

<span data-ttu-id="77bd2-123">In der folgenden Tabelle sind die Schritte zusammengefasst, die Sie zum Bereitstellen und Verwalten von Microsoft Defender for Endpoint für Macs über Intune ausführen müssten.</span><span class="sxs-lookup"><span data-stu-id="77bd2-123">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint for Macs, via Intune.</span></span> <span data-ttu-id="77bd2-124">Ausführlichere Schritte finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="77bd2-124">More detailed steps are available below.</span></span>

| <span data-ttu-id="77bd2-125">Schritt</span><span class="sxs-lookup"><span data-stu-id="77bd2-125">Step</span></span> | <span data-ttu-id="77bd2-126">Beispieldateinamen</span><span class="sxs-lookup"><span data-stu-id="77bd2-126">Sample file names</span></span> | <span data-ttu-id="77bd2-127">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="77bd2-127">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="77bd2-128">Herunterladen von Installations- und Onboardingpaketen</span><span class="sxs-lookup"><span data-stu-id="77bd2-128">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="77bd2-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="77bd2-130">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="77bd2-130">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="77bd2-131">Genehmigen der Systemerweiterung für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77bd2-131">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="77bd2-132">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-132">MDATP_SysExt.xml</span></span> | <span data-ttu-id="77bd2-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="77bd2-133">N/A</span></span> |
| [<span data-ttu-id="77bd2-134">Genehmigen der Kernelerweiterung für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77bd2-134">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="77bd2-135">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-135">MDATP_KExt.xml</span></span> | <span data-ttu-id="77bd2-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="77bd2-136">N/A</span></span> |
| [<span data-ttu-id="77bd2-137">Gewähren des vollständigen Datenträgerzugriffs auf Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77bd2-137">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#create-system-configuration-profiles-step-8) | <span data-ttu-id="77bd2-138">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-138">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="77bd2-139">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="77bd2-139">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="77bd2-140">Netzwerkerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="77bd2-140">Network Extension policy</span></span>](#create-system-configuration-profiles-step-9) | <span data-ttu-id="77bd2-141">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-141">MDATP_NetExt.xml</span></span> | <span data-ttu-id="77bd2-142">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="77bd2-142">N/A</span></span> |
| [<span data-ttu-id="77bd2-143">Konfigurieren von Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="77bd2-143">Configure Microsoft AutoUpdate (MAU)</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | <span data-ttu-id="77bd2-144">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-144">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="77bd2-145">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="77bd2-145">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="77bd2-146">Konfigurationseinstellungen für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77bd2-146">Microsoft Defender for Endpoint configuration settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> <span data-ttu-id="77bd2-147">**Hinweis:** Wenn Sie planen, einen Drittanbieter-AV für macOS ausführen zu können, legen Sie auf `passiveMode` `true` fest.</span><span class="sxs-lookup"><span data-stu-id="77bd2-147">**Note:** If you are planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="77bd2-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="77bd2-149">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="77bd2-149">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="77bd2-150">Konfigurieren von Microsoft Defender für Endpoint- und MS AutoUpdate (MAU)-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="77bd2-150">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](#create-system-configuration-profiles-step-10) | <span data-ttu-id="77bd2-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="77bd2-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="77bd2-152">com.microsoft.autoupdate2 oder com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="77bd2-152">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="77bd2-153">Herunterladen von Installations- und Onboardingpaketen</span><span class="sxs-lookup"><span data-stu-id="77bd2-153">Download installation and onboarding packages</span></span>

<span data-ttu-id="77bd2-154">Laden Sie die Installations- und Onboardingpakete von Microsoft Defender Security Center herunter:</span><span class="sxs-lookup"><span data-stu-id="77bd2-154">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="77bd2-155">Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-155">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="77bd2-156">Legen Sie das Betriebssystem auf **macOS und** die Bereitstellungsmethode auf **Mobile Device Management /Microsoft Intune .**</span><span class="sxs-lookup"><span data-stu-id="77bd2-156">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Screenshot der Onboardingeinstellungen](images/atp-mac-install.png)

3. <span data-ttu-id="77bd2-158">Wählen **Sie Installationspaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-158">Select **Download installation package**.</span></span> <span data-ttu-id="77bd2-159">Speichern Sie es _als wdav.pkg_ in einem lokalen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="77bd2-159">Save it as _wdav.pkg_ to a local directory.</span></span>

4. <span data-ttu-id="77bd2-160">Wählen **Sie Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-160">Select **Download onboarding package**.</span></span> <span data-ttu-id="77bd2-161">Speichern Sie es _WindowsDefenderATPOnboardingPackage.zip_ im gleichen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="77bd2-161">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

5. <span data-ttu-id="77bd2-162">Laden **Sie IntuneAppUtil von** [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) herunter.</span><span class="sxs-lookup"><span data-stu-id="77bd2-162">Download **IntuneAppUtil** from [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos).</span></span>

6. <span data-ttu-id="77bd2-163">Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die drei Dateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-163">From a command prompt, verify that you have the three files.</span></span>
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. <span data-ttu-id="77bd2-164">Extrahieren Sie den Inhalt der ZIP-Dateien:</span><span class="sxs-lookup"><span data-stu-id="77bd2-164">Extract the contents of the .zip files:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

8. <span data-ttu-id="77bd2-165">Machen Sie IntuneAppUtil zu einer ausführbaren Datei:</span><span class="sxs-lookup"><span data-stu-id="77bd2-165">Make IntuneAppUtil an executable:</span></span>

    ```bash
    chmod +x IntuneAppUtil
    ```

9. <span data-ttu-id="77bd2-166">Erstellen Sie das wdav.pkg.intunemac-Paket aus wdav.pkg:</span><span class="sxs-lookup"><span data-stu-id="77bd2-166">Create the wdav.pkg.intunemac package from wdav.pkg:</span></span>

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a><span data-ttu-id="77bd2-167">Setup des Clientgeräts</span><span class="sxs-lookup"><span data-stu-id="77bd2-167">Client device setup</span></span>

<span data-ttu-id="77bd2-168">Sie benötigen keine spezielle Bereitstellung für ein Mac-Gerät, das über eine standardmäßige Installation des [Unternehmensportals hinaus geht.](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="77bd2-168">You do not need any special provisioning for a Mac device beyond a standard [Company Portal installation](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="77bd2-169">Bestätigen Sie die Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="77bd2-169">Confirm device management.</span></span>

    ![Bildschirmfoto zur Geräteverwaltung bestätigen](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-3-confirmdevicemgmt)

    <span data-ttu-id="77bd2-171">Wählen **Sie Systemeinstellungen öffnen** aus, suchen Sie **in** der Liste nach Verwaltungsprofil, und wählen Sie **Genehmigen...** aus. Ihr Verwaltungsprofil wird als Überprüft **angezeigt:**</span><span class="sxs-lookup"><span data-stu-id="77bd2-171">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Screenshot des Verwaltungsprofils](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-4-managementprofile)

2. <span data-ttu-id="77bd2-173">Wählen **Sie Weiter** aus, und schließen Sie die Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="77bd2-173">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="77bd2-174">Sie können jetzt weitere Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="77bd2-174">You may now enroll more devices.</span></span> <span data-ttu-id="77bd2-175">Sie können sie auch später registrieren, nachdem Sie die Bereitstellung von Systemkonfigurations- und Anwendungspaketen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="77bd2-175">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="77bd2-176">Öffnen Sie in Intune **Geräte**  >  **verwalten**  >  **Alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-176">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="77bd2-177">Hier sehen Sie Ihr Gerät unter den aufgeführten:</span><span class="sxs-lookup"><span data-stu-id="77bd2-177">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77bd2-178">![Screenshot "Geräte hinzufügen"](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)</span><span class="sxs-lookup"><span data-stu-id="77bd2-178">![Add Devices screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)</span></span>

## <a name="approve-system-extensions"></a><span data-ttu-id="77bd2-179">Genehmigen von Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="77bd2-179">Approve System Extensions</span></span>

<span data-ttu-id="77bd2-180">So genehmigen Sie die Systemerweiterungen:</span><span class="sxs-lookup"><span data-stu-id="77bd2-180">To approve the system extensions:</span></span>

1. <span data-ttu-id="77bd2-181">Öffnen Sie in Intune **Die**  >  **Gerätekonfiguration verwalten.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-181">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="77bd2-182">Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-182">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="77bd2-183">Wählen Sie einen Namen für das Profil aus.</span><span class="sxs-lookup"><span data-stu-id="77bd2-183">Choose a name for the profile.</span></span> <span data-ttu-id="77bd2-184">Ändern **Sie Platform=macOS** in **Profile type=Extensions**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-184">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="77bd2-185">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd2-185">Select **Create**.</span></span>

3. <span data-ttu-id="77bd2-186">Geben Sie `Basics` auf der Registerkarte diesem neuen Profil einen Namen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-186">In the `Basics` tab, give a name to this new profile.</span></span>

4. <span data-ttu-id="77bd2-187">Fügen Sie `Configuration settings` auf der Registerkarte die folgenden Einträge im Abschnitt `Allowed system extensions` hinzu:</span><span class="sxs-lookup"><span data-stu-id="77bd2-187">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="77bd2-188">Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="77bd2-188">Bundle identifier</span></span>         | <span data-ttu-id="77bd2-189">Team-ID</span><span class="sxs-lookup"><span data-stu-id="77bd2-189">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="77bd2-190">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="77bd2-190">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="77bd2-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="77bd2-191">UBF8T346G9</span></span>
    <span data-ttu-id="77bd2-192">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="77bd2-192">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="77bd2-193">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="77bd2-193">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-194">![Screenshot der Registerkarte Konfigurationseinstellungen, einschließlich des Abschnitts "Zulässige Teambezeichner"](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="77bd2-194">![Screenshot of the Configuration settings tab, including the Allowed team identifiers section](images/mac-system-extension-intune2.png)</span></span>

5. <span data-ttu-id="77bd2-195">Weisen Sie `Assignments` auf der Registerkarte dieses Profil allen Benutzern & Allen Geräten **zu.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-195">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>

6. <span data-ttu-id="77bd2-196">Überprüfen und erstellen Sie dieses Konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="77bd2-196">Review and create this configuration profile.</span></span>

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="77bd2-197">Erstellen von Systemkonfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="77bd2-197">Create System Configuration profiles</span></span>

1. <span data-ttu-id="77bd2-198">Öffnen Sie in Intune **Die**  >  **Gerätekonfiguration verwalten.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-198">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="77bd2-199">Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-199">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="77bd2-200">Wählen Sie einen Namen für das Profil aus.</span><span class="sxs-lookup"><span data-stu-id="77bd2-200">Choose a name for the profile.</span></span> <span data-ttu-id="77bd2-201">Ändern **sie Platform=macOS** in **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-201">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="77bd2-202">Wählen Sie **Konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd2-202">Select **Configure**.</span></span>

3. <span data-ttu-id="77bd2-203">Öffnen Sie das Konfigurationsprofil, und laden Sie intune/kext.xml.</span><span class="sxs-lookup"><span data-stu-id="77bd2-203">Open the configuration profile and upload intune/kext.xml.</span></span> <span data-ttu-id="77bd2-204">Diese Datei wurde in einem der vorherigen Abschnitte erstellt.</span><span class="sxs-lookup"><span data-stu-id="77bd2-204">This file was created in one of the preceding sections.</span></span>

4. <span data-ttu-id="77bd2-205">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="77bd2-205">Select **OK**.</span></span>

    ![Screenshot der Systemkonfigurationsprofile](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-6-systemconfigurationprofiles)

5. <span data-ttu-id="77bd2-207">Wählen **Sie**  >  **Zuordnungen verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-207">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="77bd2-208">Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-208">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

6. <span data-ttu-id="77bd2-209">Wiederholen Sie die Schritte 1 bis 5 für weitere Profile.</span><span class="sxs-lookup"><span data-stu-id="77bd2-209">Repeat steps 1 through 5 for more profiles.</span></span>

7. <span data-ttu-id="77bd2-210">Erstellen Sie ein anderes Profil, geben Sie ihm einen Namen, und laden Sie die intune/WindowsDefenderATPOnboarding.xml hoch.</span><span class="sxs-lookup"><span data-stu-id="77bd2-210">Create another profile, give it a name, and upload the intune/WindowsDefenderATPOnboarding.xml file.</span></span>

8. <span data-ttu-id="77bd2-211">Laden `fulldisk.mobileconfig` Sie aus unserem [GitHub-Repository herunter,](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) und speichern Sie es unter `tcc.xml` .</span><span class="sxs-lookup"><span data-stu-id="77bd2-211">Download `fulldisk.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and save it as `tcc.xml`.</span></span> <span data-ttu-id="77bd2-212">Erstellen Sie ein anderes Profil, geben Sie ihm einen beliebigen Namen, und laden Sie diese Datei hoch.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span><span class="sxs-lookup"><span data-stu-id="77bd2-212">Create another profile, give it any name and upload this file to it.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span></span>

   > [!CAUTION]
   > <span data-ttu-id="77bd2-213">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-213">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="77bd2-214">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="77bd2-214">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="77bd2-215">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-215">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="77bd2-216">Dieses Konfigurationsprofil gewährt Volldatenträgerzugriff auf Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="77bd2-216">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="77bd2-217">Wenn Sie Microsoft Defender for Endpoint zuvor über Intune konfiguriert haben, wird empfohlen, die Bereitstellung mit diesem Konfigurationsprofil zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="77bd2-217">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

9. <span data-ttu-id="77bd2-218">Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint für Mac den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="77bd2-218">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="77bd2-219">Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-219">The following policy allows the network extension to perform this functionality.</span></span> <span data-ttu-id="77bd2-220">Laden `netfilter.mobileconfig` Sie aus unserem [GitHub-Repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)herunter, speichern Sie es netext.xml und stellen Sie es mithilfe der gleichen Schritte wie in den vorherigen Abschnitten bereit.</span><span class="sxs-lookup"><span data-stu-id="77bd2-220">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig), save it as netext.xml and deploy it using the same steps as in the previous sections.</span></span> <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. <span data-ttu-id="77bd2-221">Um Microsoft Defender for Endpoint für Mac und Microsoft Auto Update das Anzeigen von Benachrichtigungen in der Benutzeroberfläche auf macOS 10.15 (Catalina) zu ermöglichen, laden Sie es aus unserem `notif.mobileconfig` [GitHub-Repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) herunter, und importieren Sie es als benutzerdefinierte Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="77bd2-221">To allow Microsoft Defender for Endpoint for Mac and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina), download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) and import it as a custom payload.</span></span> <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. <span data-ttu-id="77bd2-222">Wählen **Sie Verwalten > Zuordnungen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-222">Select **Manage > Assignments**.</span></span>  <span data-ttu-id="77bd2-223">Wählen Sie **auf** der Registerkarte Include die Option **Allen Benutzern & Alle Geräte zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-223">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

<span data-ttu-id="77bd2-224">Sobald die Intune-Änderungen an die registrierten Geräte übertragen wurden, werden sie unter **Monitor**  >  **Device status aufgeführt:**</span><span class="sxs-lookup"><span data-stu-id="77bd2-224">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77bd2-225">![Screenshot von kext – Gerätestatus](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade)</span><span class="sxs-lookup"><span data-stu-id="77bd2-225">![Screenshot of kext - Device status](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade)</span></span>

## <a name="publish-application"></a><span data-ttu-id="77bd2-226">Anwendung veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="77bd2-226">Publish application</span></span>

1. <span data-ttu-id="77bd2-227">Öffnen Sie in Intune das **Blatt > Client-Apps verwalten.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-227">In Intune, open the **Manage > Client apps** blade.</span></span> <span data-ttu-id="77bd2-228">Wählen **Sie Apps > Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-228">Select **Apps > Add**.</span></span>

2. <span data-ttu-id="77bd2-229">Wählen **Sie App type=Other/Line-of-Business App aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-229">Select **App type=Other/Line-of-business app**.</span></span>

3. <span data-ttu-id="77bd2-230">Wählen **Sie file=wdav.pkg.intunemac aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-230">Select **file=wdav.pkg.intunemac**.</span></span> <span data-ttu-id="77bd2-231">Wählen Sie **OK** aus, um es hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-231">Select **OK** to upload.</span></span>

4. <span data-ttu-id="77bd2-232">Wählen **Sie Konfigurieren** aus, und fügen Sie die erforderlichen Informationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="77bd2-232">Select **Configure** and add the required information.</span></span>

5. <span data-ttu-id="77bd2-233">Verwenden **Sie macOS High Sierra 10.13 als** Mindestbetriebssystem.</span><span class="sxs-lookup"><span data-stu-id="77bd2-233">Use **macOS High Sierra 10.13** as the minimum OS.</span></span>

6. <span data-ttu-id="77bd2-234">Legen *Sie Die App-Version ignorieren auf* Ja **.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-234">Set *Ignore app version* to **Yes**.</span></span> <span data-ttu-id="77bd2-235">Andere Einstellungen können beliebige Werte sein.</span><span class="sxs-lookup"><span data-stu-id="77bd2-235">Other settings can be any arbitrary value.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="77bd2-236">Festlegen *der App-Version ignorieren* auf **Keine** Auswirkung auf die Fähigkeit der Anwendung, Updates über Microsoft AutoUpdate zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="77bd2-236">Setting *Ignore app version* to **No** impacts the ability of the application to receive updates through Microsoft AutoUpdate.</span></span> <span data-ttu-id="77bd2-237">Weitere Informationen zur Produktaktualisierung finden Sie unter Bereitstellen von Updates für [Microsoft Defender for Endpoint für Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="77bd2-237">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span>
    >
    > <span data-ttu-id="77bd2-238">Wenn die von Intune hochgeladene Version niedriger als die Version auf dem Gerät ist, wird die niedrigere Version installiert, und Microsoft Defender for Endpoint wird degradiert.</span><span class="sxs-lookup"><span data-stu-id="77bd2-238">If the version uploaded by Intune is lower than the version on the device, then the lower version will be installed, effectively downgrading Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="77bd2-239">Dies kann zu einer nicht funktionsfähigen Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="77bd2-239">This could result in a non-functioning application.</span></span> <span data-ttu-id="77bd2-240">Weitere Informationen zur Produktaktualisierung finden Sie unter Bereitstellen von Updates für [Microsoft Defender for Endpoint für Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="77bd2-240">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span> <span data-ttu-id="77bd2-241">Wenn Sie Microsoft Defender for Endpoint mit *der App-Version Ignorieren* auf **Nein** bereitgestellt haben, ändern Sie sie bitte in **Ja**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-241">If you deployed Microsoft Defender for Endpoint with *Ignore app version* set to **No**, please change it to **Yes**.</span></span> <span data-ttu-id="77bd2-242">Wenn Microsoft Defender for Endpoint weiterhin nicht auf einem Clientgerät installiert werden kann, deinstallieren Sie Microsoft Defender for Endpoint, und drücken Sie die aktualisierte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="77bd2-242">If Microsoft Defender for Endpoint still cannot be installed on a client device, then uninstall Microsoft Defender for Endpoint and push the updated policy.</span></span>
     
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-243">![Screenshot der Option App-Informationen konfigurieren im Dialogfeld App hinzufügen](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)</span><span class="sxs-lookup"><span data-stu-id="77bd2-243">![Screenshot of the Configure App information option in the Add app dialog box](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)</span></span>

7. <span data-ttu-id="77bd2-244">Wählen **Sie OK** und Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-244">Select **OK** and **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-245">![Screenshot einer Beispielübersicht](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)</span><span class="sxs-lookup"><span data-stu-id="77bd2-245">![Screenshot of a sample overview](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)</span></span>

8. <span data-ttu-id="77bd2-246">Es kann einige Minuten dauern, bis das Paket hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="77bd2-246">It may take a few moments to upload the package.</span></span> <span data-ttu-id="77bd2-247">Wählen Sie anschließend das Paket aus der Liste aus, und wechseln Sie zu **Zuordnungen** und **Gruppe hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-247">After it's done, select the package from the list and go to **Assignments** and **Add group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-248">![Screenshot von Client-Apps](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)</span><span class="sxs-lookup"><span data-stu-id="77bd2-248">![Client apps screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)</span></span>

9. <span data-ttu-id="77bd2-249">Ändern **des Zuweisungstyps** in **Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="77bd2-249">Change **Assignment type** to **Required**.</span></span>

10. <span data-ttu-id="77bd2-250">Wählen **Sie Eingeschlossene Gruppen aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-250">Select **Included Groups**.</span></span> <span data-ttu-id="77bd2-251">Wählen **Sie Diese App für alle Geräte erforderlich machen=Ja aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-251">Select **Make this app required for all devices=Yes**.</span></span> <span data-ttu-id="77bd2-252">Wählen **Sie Gruppe auswählen aus, um eine** Gruppe hinzuzufügen und hinzuzufügen, die die Benutzer enthält, die Sie als Ziel auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="77bd2-252">Select **Select group to include** and add a group that contains the users you want to target.</span></span> <span data-ttu-id="77bd2-253">Wählen Sie **OK** und **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="77bd2-253">Select **OK** and **Save**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-254">![Screenshot der Intune-Zuweisungen](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)</span><span class="sxs-lookup"><span data-stu-id="77bd2-254">![Intune assignments info screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)</span></span>

11. <span data-ttu-id="77bd2-255">Nach einiger Zeit wird die Anwendung auf allen registrierten Geräten veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="77bd2-255">After some time the application will be published to all enrolled devices.</span></span> <span data-ttu-id="77bd2-256">Sie finden sie unter **Monitor**  >  **Device**, under **Device install status**:</span><span class="sxs-lookup"><span data-stu-id="77bd2-256">You can see it listed in **Monitor** > **Device**, under **Device install status**:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-257">![Screenshot des Intune-Gerätestatus](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)</span><span class="sxs-lookup"><span data-stu-id="77bd2-257">![Intune device status screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="77bd2-258">Überprüfen des Clientgerätestatus</span><span class="sxs-lookup"><span data-stu-id="77bd2-258">Verify client device state</span></span>

1. <span data-ttu-id="77bd2-259">Nachdem die Konfigurationsprofile auf Ihren Geräten bereitgestellt wurden, öffnen Sie **Systemeinstellungsprofile**  >  **auf** Ihrem Mac-Gerät.</span><span class="sxs-lookup"><span data-stu-id="77bd2-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    <span data-ttu-id="77bd2-260">![Screenshot der Systemeinstellungen](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)</span><span class="sxs-lookup"><span data-stu-id="77bd2-260">![System Preferences screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)</span></span><br/>
    <span data-ttu-id="77bd2-261">![Screenshot der Systemeinstellungenprofile](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)</span><span class="sxs-lookup"><span data-stu-id="77bd2-261">![System Preferences Profiles screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)</span></span>

2. <span data-ttu-id="77bd2-262">Stellen Sie sicher, dass die folgenden Konfigurationsprofile vorhanden und installiert sind.</span><span class="sxs-lookup"><span data-stu-id="77bd2-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="77bd2-263">Das **Verwaltungsprofil** sollte das Intune-Systemprofil sein.</span><span class="sxs-lookup"><span data-stu-id="77bd2-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="77bd2-264">_Wdav-config_ und _wdav-kext_ sind Systemkonfigurationsprofile, die in Intune hinzugefügt ![ wurden: Screenshot der Profile](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)</span><span class="sxs-lookup"><span data-stu-id="77bd2-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune: ![Profiles screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)</span></span>

3. <span data-ttu-id="77bd2-265">Außerdem sollte das Microsoft Defender-Symbol in der oberen rechten Ecke angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="77bd2-265">You should also see the Microsoft Defender icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77bd2-266">![Microsoft Defender-Symbol im Screenshot der Statusleiste](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)</span><span class="sxs-lookup"><span data-stu-id="77bd2-266">![Microsoft Defender icon in status bar screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="77bd2-267">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="77bd2-267">Troubleshooting</span></span>

<span data-ttu-id="77bd2-268">Problem: Keine Lizenz gefunden</span><span class="sxs-lookup"><span data-stu-id="77bd2-268">Issue: No license found</span></span>

<span data-ttu-id="77bd2-269">Lösung: Führen Sie die obigen Schritte aus, um ein Geräteprofil mithilfe von WindowsDefenderATPOnboarding.xml</span><span class="sxs-lookup"><span data-stu-id="77bd2-269">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="77bd2-270">Probleme bei der Protokollierung der Installation</span><span class="sxs-lookup"><span data-stu-id="77bd2-270">Logging installation issues</span></span>

<span data-ttu-id="77bd2-271">Weitere Informationen zum Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter [Logging installation issues](mac-resources.md#logging-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="77bd2-271">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="77bd2-272">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="77bd2-272">Uninstallation</span></span>

<span data-ttu-id="77bd2-273">Weitere Informationen zum Entfernen von Microsoft Defender for Endpoint für Mac von Clientgeräten finden Sie unter [Uninstalling.](mac-resources.md#uninstalling)</span><span class="sxs-lookup"><span data-stu-id="77bd2-273">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for Mac from client devices.</span></span>
