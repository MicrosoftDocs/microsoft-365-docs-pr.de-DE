---
title: Intune-basierte Bereitstellung für Microsoft Defender for Endpoint auf Dem Mac
description: Installieren Sie Microsoft Defender for Endpoint auf dem Mac mithilfe Microsoft Intune.
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
ms.openlocfilehash: 5aeffdaff39c2f10dfa5164764bff38e99c00010
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684219"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="a3a7a-104">Intune-basierte Bereitstellung für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="a3a7a-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3a7a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3a7a-106">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="a3a7a-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="a3a7a-107">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint auf macOS über Intune bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="a3a7a-108">Für eine erfolgreiche Bereitstellung sind alle folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="a3a7a-109">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="a3a7a-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="a3a7a-110">Setup des Clientgeräts</span><span class="sxs-lookup"><span data-stu-id="a3a7a-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="a3a7a-111">Genehmigen von Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="a3a7a-112">Erstellen von Systemkonfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="a3a7a-113">Anwendung veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="a3a7a-114">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="a3a7a-115">Bevor Sie beginnen, finden Sie auf der [Hauptseite von Microsoft Defender for Endpoint auf macOS](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="a3a7a-116">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a3a7a-116">Overview</span></span>

<span data-ttu-id="a3a7a-117">In der folgenden Tabelle sind die Schritte zusammengefasst, die Sie zum Bereitstellen und Verwalten von Microsoft Defender for Endpoint auf Macs über Intune ausführen müssten.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="a3a7a-118">Ausführlichere Schritte finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="a3a7a-119">Schritt</span><span class="sxs-lookup"><span data-stu-id="a3a7a-119">Step</span></span> | <span data-ttu-id="a3a7a-120">Beispieldateinamen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-120">Sample file names</span></span> | <span data-ttu-id="a3a7a-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="a3a7a-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="a3a7a-122">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="a3a7a-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="a3a7a-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="a3a7a-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="a3a7a-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="a3a7a-125">Genehmigen der Systemerweiterung für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a7a-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="a3a7a-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="a3a7a-127">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a3a7a-127">N/A</span></span> |
| [<span data-ttu-id="a3a7a-128">Genehmigen der Kernelerweiterung für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a7a-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="a3a7a-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="a3a7a-130">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a3a7a-130">N/A</span></span> |
| [<span data-ttu-id="a3a7a-131">Gewähren des vollständigen Datenträgerzugriffs auf Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a7a-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="a3a7a-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="a3a7a-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="a3a7a-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="a3a7a-134">Netzwerkerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a3a7a-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="a3a7a-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="a3a7a-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a3a7a-136">N/A</span></span> |
| [<span data-ttu-id="a3a7a-137">Konfigurieren von Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="a3a7a-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="a3a7a-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="a3a7a-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="a3a7a-140">Konfigurationseinstellungen für Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a7a-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="a3a7a-141">**Hinweis:** Wenn Sie planen, einen Drittanbieter-AV für macOS ausführen zu können, legen Sie auf `passiveMode` `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="a3a7a-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="a3a7a-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="a3a7a-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="a3a7a-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="a3a7a-144">Konfigurieren von Microsoft Defender für Endpoint- und MS AutoUpdate (MAU)-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="a3a7a-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="a3a7a-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="a3a7a-146">com.microsoft.autoupdate2 oder com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="a3a7a-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="a3a7a-147">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="a3a7a-147">Download the onboarding package</span></span>

<span data-ttu-id="a3a7a-148">Laden Sie die Onboardingpakete von Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="a3a7a-149">In Microsoft Defender Security Center wechseln Sie zu **Einstellungen**  >  **Device Management**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="a3a7a-150">Legen Sie das Betriebssystem auf **macOS und** die Bereitstellungsmethode auf **Mobile Device Management /Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Screenshot der Onboardingeinstellungen](images/atp-mac-install.png)

3. <span data-ttu-id="a3a7a-152">Wählen **Sie Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="a3a7a-153">Speichern Sie es _WindowsDefenderATPOnboardingPackage.zip_ im gleichen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="a3a7a-154">Extrahieren Sie den Inhalt der .zip Datei:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-154">Extract the contents of the .zip file:</span></span>

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

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="a3a7a-155">Erstellen von Systemkonfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-155">Create System Configuration profiles</span></span>

<span data-ttu-id="a3a7a-156">Der nächste Schritt besteht im Erstellen von Systemkonfigurationsprofilen, die Microsoft Defender for Endpoint benötigt.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="a3a7a-157">Öffnen Sie [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/) **gerätekonfigurationsprofile**  >  .</span><span class="sxs-lookup"><span data-stu-id="a3a7a-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="a3a7a-158">Onboarding-Blob</span><span class="sxs-lookup"><span data-stu-id="a3a7a-158">Onboarding blob</span></span>

<span data-ttu-id="a3a7a-159">Dieses Profil enthält lizenzinformationen für Microsoft Defender for Endpoint, ohne dass es darüber informiert wird, dass es nicht lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="a3a7a-160">Wählen **Sie Profil erstellen** unter **Konfigurationsprofile aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="a3a7a-161">Wählen **Sie Plattform** = **macOS**, **Profiltyp** = **Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="a3a7a-162">**Vorlagenname** = **Benutzerdefinierte .**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="a3a7a-163">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-164">![Erstellung eines benutzerdefinierten Konfigurationsprofils](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="a3a7a-165">Wählen Sie einen Namen für das Profil aus, z. B. "MDATP Onboarding für macOS".</span><span class="sxs-lookup"><span data-stu-id="a3a7a-165">Choose a name for the profile, e.g., "MDATP onboarding for macOS".</span></span> <span data-ttu-id="a3a7a-166">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-167">![Benutzerdefiniertes Konfigurationsprofil – Name](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="a3a7a-168">Wählen Sie einen Namen für den Konfigurationsprofilnamen aus, z. B. "MDATP für macOS".</span><span class="sxs-lookup"><span data-stu-id="a3a7a-168">Choose a name for the configuration profile name, e.g., "MDATP onboarding for macOS".</span></span>
1. <span data-ttu-id="a3a7a-169">Wählen Sie intune/WindowsDefenderATPOnboarding.xml, die Sie aus dem obigen Onboardingpaket als Konfigurationsprofildatei extrahiert haben.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-170">![Importieren einer Konfiguration aus einer Datei für benutzerdefiniertes Konfigurationsprofil](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="a3a7a-171">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-171">Click **Next**.</span></span>
1. <span data-ttu-id="a3a7a-172">Zuweisen von Geräten auf der **Registerkarte Zuordnung.** Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-173">![Benutzerdefiniertes Konfigurationsprofil – Zuordnung](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="a3a7a-174">Überprüfen und **Erstellen** von .</span><span class="sxs-lookup"><span data-stu-id="a3a7a-174">Review and **Create**.</span></span>
1. <span data-ttu-id="a3a7a-175">Öffnen **Sie**  >  **GeräteKonfigurationsprofile,** sie können Ihr erstelltes Profil dort sehen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-176">![Benutzerdefiniertes Konfigurationsprofil – fertig](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="a3a7a-177">Genehmigen von Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-177">Approve System Extensions</span></span>

<span data-ttu-id="a3a7a-178">Dieses Profil ist für macOS 10.15 (Catalina) oder neuer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="a3a7a-179">Er wird auf älteren macOS ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="a3a7a-180">Wählen **Sie Profil erstellen** unter **Konfigurationsprofile aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="a3a7a-181">Wählen **Sie Plattform** = **macOS**, **Profiltyp** = **Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="a3a7a-182">**Vorlagenname** = **Erweiterungen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="a3a7a-183">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-183">Click **Create**.</span></span>
1. <span data-ttu-id="a3a7a-184">Geben Sie **auf der Registerkarte** Grundlagen diesem neuen Profil einen Namen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="a3a7a-185">Erweitern Sie **auf der** Registerkarte Konfigurationseinstellungen **die Folgenden** Einträge im Abschnitt Zulässige **Systemerweiterungen:**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="a3a7a-186">Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="a3a7a-186">Bundle identifier</span></span>         | <span data-ttu-id="a3a7a-187">Team-ID</span><span class="sxs-lookup"><span data-stu-id="a3a7a-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="a3a7a-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="a3a7a-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="a3a7a-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="a3a7a-189">UBF8T346G9</span></span>
    <span data-ttu-id="a3a7a-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="a3a7a-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="a3a7a-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="a3a7a-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-192">![Systemerweiterungseinstellungen](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="a3a7a-193">Weisen Sie **auf** der Registerkarte Zuweisungen dieses Profil allen Benutzern & **Allen Geräten zu.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="a3a7a-194">Überprüfen und erstellen Sie dieses Konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="a3a7a-195">Kernelerweiterungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-195">Kernel Extensions</span></span>

<span data-ttu-id="a3a7a-196">Dieses Profil ist für macOS 10.15 (Catalina) oder älter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="a3a7a-197">Sie wird unter neueren macOS ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="a3a7a-198">Apple Silicon (M1)-Geräte unterstützen KEXT nicht.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="a3a7a-199">Bei der Installation eines Konfigurationsprofils, das aus KEXT-Richtlinien besteht, wird auf diesen Geräten ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="a3a7a-200">Wählen **Sie Profil erstellen** unter **Konfigurationsprofile aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="a3a7a-201">Wählen **Sie Plattform** = **macOS**, **Profiltyp** = **Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="a3a7a-202">**Vorlagenname** = **Erweiterungen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="a3a7a-203">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-203">Click **Create**.</span></span>
1. <span data-ttu-id="a3a7a-204">Geben Sie **auf der Registerkarte** Grundlagen diesem neuen Profil einen Namen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="a3a7a-205">Erweitern Sie **auf der Registerkarte** Konfigurationseinstellungen die Erweiterung **Kernelerweiterungen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="a3a7a-206">Legen **Sie den Teambezeichner** **auf UBF8T346G9 und** klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-207">![Kernelerweiterungseinstellungen](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="a3a7a-208">Weisen Sie **auf** der Registerkarte Zuweisungen dieses Profil allen Benutzern & **Allen Geräten zu.**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="a3a7a-209">Überprüfen und erstellen Sie dieses Konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="a3a7a-210">Vollständiger Festplattenzugriff</span><span class="sxs-lookup"><span data-stu-id="a3a7a-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="a3a7a-211">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="a3a7a-212">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="a3a7a-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="a3a7a-213">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="a3a7a-214">Dieses Konfigurationsprofil gewährt Volldatenträgerzugriff auf Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a3a7a-215">Wenn Sie Microsoft Defender for Endpoint zuvor über Intune konfiguriert haben, wird empfohlen, die Bereitstellung mit diesem Konfigurationsprofil zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="a3a7a-216">Laden [**Sie fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) aus [unserem GitHub herunter.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="a3a7a-217">Befolgen Sie die Anweisungen für [das Onboarding-Blob](#onboarding-blob) von oben, indem Sie "MDATP Full Disk Access" als Profilnamen verwenden und **fulldisk.mobileconfig** als Konfigurationsprofilnamen heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="a3a7a-218">Netzwerkfilter</span><span class="sxs-lookup"><span data-stu-id="a3a7a-218">Network Filter</span></span>

<span data-ttu-id="a3a7a-219">Im Rahmen der Funktionen für die Erkennung und Reaktion von Endpunkten prüft Microsoft Defender for Endpoint auf macOS den Socketdatenverkehr und meldet diese Informationen Microsoft Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="a3a7a-220">Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="a3a7a-221">Laden [**Sie netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) aus [unserem GitHub herunter.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="a3a7a-222">Befolgen Sie die Anweisungen für [das Onboarding-Blob](#onboarding-blob) von oben, indem Sie "MDATP Network Filter" als Profilnamen verwenden und **netfilter.mobileconfig** als Konfigurationsprofilnamen heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="a3a7a-223">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-223">Notifications</span></span>

<span data-ttu-id="a3a7a-224">Dieses Profil wird verwendet, um Microsoft Defender for Endpoint unter macOS und Microsoft Auto Update das Anzeigen von Benachrichtigungen in der Benutzeroberfläche unter macOS 10.15 (Catalina) oder neuer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="a3a7a-225">Laden [**Sie notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) aus [unserem GitHub herunter.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="a3a7a-226">Befolgen Sie die Anweisungen für [das Onboarding-Blob](#onboarding-blob) von oben, indem Sie "MDATP Netzwerkfilter" als Profilnamen verwenden und **notif.mobileconfig** als Konfigurationsprofilnamen heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="a3a7a-227">Status anzeigen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-227">View Status</span></span>

<span data-ttu-id="a3a7a-228">Sobald die Intune-Änderungen an die registrierten Geräte übertragen wurden, werden sie unter **Monitor**  >  **Device status aufgeführt:**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3a7a-229">![Anzeigen des Gerätestatus im Monitor](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="a3a7a-230">Anwendung veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="a3a7a-230">Publish application</span></span>

<span data-ttu-id="a3a7a-231">Dieser Schritt ermöglicht die Bereitstellung von Microsoft Defender for Endpoint auf registrierten Computern.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="a3a7a-232">Öffnen Sie [im Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/) **Apps**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-233">![Bereit zum Erstellen einer Anwendung](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="a3a7a-234">Wählen Sie Nach Plattform > macOS > Hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="a3a7a-235">Wählen **Sie App-Typ** = **macOS** aus, klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-236">![Angeben des Anwendungstyps](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="a3a7a-237">Halten Sie die Standardwerte bei, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-238">![Anwendungseigenschaften](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="a3a7a-239">Fügen Sie Zuordnungen hinzu, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-240">![Screenshot der Intune-Zuweisungen](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="a3a7a-241">Überprüfen und **Erstellen** von .</span><span class="sxs-lookup"><span data-stu-id="a3a7a-241">Review and **Create**.</span></span>
1. <span data-ttu-id="a3a7a-242">Sie können **Apps**  >  **nach Plattform**  >  **macOS besuchen,** um es in der Liste aller Anwendungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-243">![Anwendungsliste](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="a3a7a-244">(Ausführliche Informationen finden Sie auf der [Intune-Seite für die Defender-Bereitstellung.)](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="a3a7a-245">Sie müssen alle erforderlichen Konfigurationsprofile erstellen und wie oben erläutert auf allen Computern pushen.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="a3a7a-246">Setup des Clientgeräts</span><span class="sxs-lookup"><span data-stu-id="a3a7a-246">Client device setup</span></span>

<span data-ttu-id="a3a7a-247">Sie benötigen keine spezielle Bereitstellung für ein Mac-Gerät, das über eine Standardinstallation [Unternehmensportal hinaus geht.](/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="a3a7a-248">Bestätigen Sie die Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-249">![Bildschirmfoto zur Geräteverwaltung bestätigen](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="a3a7a-250">Wählen **Sie Systemeinstellungen öffnen** aus, suchen Sie **in** der Liste nach Verwaltungsprofil, und wählen Sie **Genehmigen...** aus. Ihr Verwaltungsprofil wird als Überprüft **angezeigt:**</span><span class="sxs-lookup"><span data-stu-id="a3a7a-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Screenshot des Verwaltungsprofils](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="a3a7a-252">Wählen **Sie Weiter** aus, und schließen Sie die Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="a3a7a-253">Sie können jetzt weitere Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-253">You may now enroll more devices.</span></span> <span data-ttu-id="a3a7a-254">Sie können sie auch später registrieren, nachdem Sie die Bereitstellung von Systemkonfigurations- und Anwendungspaketen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="a3a7a-255">Öffnen Sie in Intune **Geräte**  >  **verwalten**  >  **Alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="a3a7a-256">Hier sehen Sie Ihr Gerät unter den aufgeführten:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3a7a-257">![Screenshot "Geräte hinzufügen"](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="a3a7a-258">Überprüfen des Clientgerätestatus</span><span class="sxs-lookup"><span data-stu-id="a3a7a-258">Verify client device state</span></span>

1. <span data-ttu-id="a3a7a-259">Nachdem die Konfigurationsprofile auf Ihren Geräten bereitgestellt wurden, öffnen Sie **Systemeinstellungsprofile**  >  **auf** Ihrem Mac-Gerät.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-260">![Screenshot der Systemeinstellungen](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![Screenshot der Systemeinstellungenprofile](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="a3a7a-262">Stellen Sie sicher, dass die folgenden Konfigurationsprofile vorhanden und installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="a3a7a-263">Das **Verwaltungsprofil** sollte das Intune-Systemprofil sein.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="a3a7a-264">_Wdav-config_ und _wdav-kext_ sind Systemkonfigurationsprofile, die in Intune hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![Screenshot der Profile](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="a3a7a-266">Außerdem sollte das Microsoft Defender for Endpoint-Symbol in der oberen rechten Ecke angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a3a7a-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a3a7a-267">![Microsoft Defender for Endpoint(Symbol) im Screenshot der Statusleiste](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="a3a7a-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a3a7a-268">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a3a7a-268">Troubleshooting</span></span>

<span data-ttu-id="a3a7a-269">Problem: Es wurde keine Lizenz gefunden.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-269">Issue: No license found.</span></span>

<span data-ttu-id="a3a7a-270">Lösung: Führen Sie die obigen Schritte aus, um ein Geräteprofil mithilfe von WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="a3a7a-271">Probleme bei der Protokollierung der Installation</span><span class="sxs-lookup"><span data-stu-id="a3a7a-271">Logging installation issues</span></span>

<span data-ttu-id="a3a7a-272">Weitere Informationen zum Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter [Logging installation issues](mac-resources.md#logging-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="a3a7a-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="a3a7a-273">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="a3a7a-273">Uninstallation</span></span>

<span data-ttu-id="a3a7a-274">Weitere [Informationen zum Entfernen](mac-resources.md#uninstalling) von Microsoft Defender for Endpoint auf macOS von Clientgeräten finden Sie unter Deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
