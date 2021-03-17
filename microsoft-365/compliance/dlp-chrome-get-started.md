---
title: Erste Schritte mit der Microsoft Compliance Erweiterung (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Vorbereitung und Bereitstellung der Microsoft Compliance Erweiterung.
ms.openlocfilehash: d71c04433ec369856a510e9fb6382709ecb092f9
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826263"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="51918-103">Erste Schritte mit Microsoft Compliance Erweiterung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="51918-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="51918-104">Verwenden Sie diese Verfahren, um die Microsoft Compliance Erweiterung auszurollen.</span><span class="sxs-lookup"><span data-stu-id="51918-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="51918-105">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="51918-105">Before you begin</span></span>

<span data-ttu-id="51918-106">Um Microsoft Compliance Erweiterung zu verwenden, muss das Gerät in Endpunkt-DLP eingebunden sein.</span><span class="sxs-lookup"><span data-stu-id="51918-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="51918-107">Lesen Sie diese Artikel, wenn Sie neu im Bereich DLP oder Endpunkt-DLP sind</span><span class="sxs-lookup"><span data-stu-id="51918-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="51918-108">Erfahren Sie mehr über die Microsoft Compliance Erweiterung</span><span class="sxs-lookup"><span data-stu-id="51918-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="51918-109">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="51918-109">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="51918-110">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="51918-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="51918-111">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="51918-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="51918-112">Informationen zur Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="51918-113">Verhinderung von Datenverlust am Endpunkt – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="51918-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="51918-114">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="51918-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="51918-115">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="51918-116">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="51918-117">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="51918-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="51918-118">Bevor Sie loslegen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons bestätigen.</span><span class="sxs-lookup"><span data-stu-id="51918-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="51918-119">Für den Zugriff auf und die Verwendung von Endpunkt-DLP-Funktionen müssen Sie über eines der folgenden Abonnements oder Add-Ons verfügen.</span><span class="sxs-lookup"><span data-stu-id="51918-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="51918-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="51918-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="51918-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="51918-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="51918-122">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="51918-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="51918-123">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="51918-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="51918-124">Microsoft 365 E5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="51918-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="51918-125">Microsoft 365 A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="51918-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="51918-126">Ausführliche Informationen zur Lizenzierung finden Sie unter: [Microsoft 365-Lizenzierungsrichtlinien für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="51918-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="51918-127">Ihre Organisation muss für Endpoint-DLP lizenziert sein</span><span class="sxs-lookup"><span data-stu-id="51918-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="51918-128">Auf Ihren Geräten muss Windows 10 x64 Build 1809 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51918-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="51918-129">Auf dem Gerät muss die Antimalware Client Version 4.18.2101.9 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="51918-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="51918-130">Überprüfen Sie die aktuelle Version, indem Sie die **Windows-Sicherheits**-App öffnen, das Symbol **Einstellungen** und dann **Info** auswählen.</span><span class="sxs-lookup"><span data-stu-id="51918-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="51918-131">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="51918-131">Permissions</span></span>

<span data-ttu-id="51918-132">Endpunkt-DLP-Daten können im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="51918-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="51918-133">Es gibt sieben Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren. Das Konto, das Sie für den Zugriff auf die Daten verwenden, muss Mitglied einer dieser Rollen sein.</span><span class="sxs-lookup"><span data-stu-id="51918-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="51918-134">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="51918-134">Global admin</span></span>
- <span data-ttu-id="51918-135">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="51918-135">Compliance admin</span></span>
- <span data-ttu-id="51918-136">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="51918-136">Security admin</span></span>
- <span data-ttu-id="51918-137">Compliancedaten-Administrator</span><span class="sxs-lookup"><span data-stu-id="51918-137">Compliance data admin</span></span>
- <span data-ttu-id="51918-138">Globale Leseberechtigung</span><span class="sxs-lookup"><span data-stu-id="51918-138">Global reader</span></span>
- <span data-ttu-id="51918-139">Benutzer mit Leseberechtigung für Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="51918-139">Security reader</span></span>
- <span data-ttu-id="51918-140">Berichtleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="51918-140">Reports reader</span></span>

### <a name="chrome-dependency"></a><span data-ttu-id="51918-141">Chrome-Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="51918-141">Chrome dependency</span></span>

<span data-ttu-id="51918-142">Die Microsoft Compliance Erweiterung wird für die aktuelle Version von Chrome und die vergangenen drei Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51918-142">The Microsoft Compliance Extension is supported for the current version of Chrome and the past three versions.</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="51918-143">Gesamter Installationsablauf</span><span class="sxs-lookup"><span data-stu-id="51918-143">Overall installation workflow</span></span>

<span data-ttu-id="51918-144">Die Bereitstellung von Microsoft Compliance Erweiterung ist ein mehrstufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="51918-144">Deploying Microsoft Compliance Extension is a multi-phase process.</span></span> <span data-ttu-id="51918-145">Sie können wählen, ob Sie die Installation auf einem einzelnen Computer durchführen möchten, oder ob Sie den Microsoft Endpoint Manager oder die Gruppenrichtlinie für eine unternehmensweite Bereitstellung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="51918-145">You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="51918-146">[Bereiten Sie Ihre Geräte vor](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="51918-146">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="51918-147">Grundlegende Einrichtung Einzel Computer Selfhost</span><span class="sxs-lookup"><span data-stu-id="51918-147">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="51918-148">Bereitstellen mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="51918-148">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="51918-149">Bereitstellen über Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="51918-149">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="51918-150">Testen der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="51918-150">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="51918-151">Verwenden Sie das Verwaltung von Benachrichtigungen Dashboard, um Chrome DLP-Benachrichtigungen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="51918-151">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. <span data-ttu-id="51918-152">[Anzeigen von Chrome-DLP-Daten im Aktivitäten-Explorer](#viewing-chrome-dlp-data-in-activity-explorer) </span><span class="sxs-lookup"><span data-stu-id="51918-152">[Viewing Chrome DLP data in activity explorer](#viewing-chrome-dlp-data-in-activity-explorer)</span></span> 

### <a name="prepare-infrastructure"></a><span data-ttu-id="51918-153">Infrastruktur vorbereiten</span><span class="sxs-lookup"><span data-stu-id="51918-153">Prepare infrastructure</span></span>

<span data-ttu-id="51918-154">Wenn Sie die Microsoft Compliance Erweiterung auf alle Ihre überwachten Windows 10-Geräte ausrollen, sollten Sie Google Chrome aus der Liste der nicht zugelassenen Apps entfernen.</span><span class="sxs-lookup"><span data-stu-id="51918-154">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed apps list.</span></span> <span data-ttu-id="51918-155">Weitere Informationen finden Sie unter [Unerlaubte Browser](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="51918-155">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="51918-156">Wenn Sie es nur auf einige wenige Geräte ausrollen, können Sie Chrome auf der Liste der nicht zugelassenen Browser belassen.</span><span class="sxs-lookup"><span data-stu-id="51918-156">If you are only rolling it out to a few devices you can leave Chrome on the unallowed browser list.</span></span> <span data-ttu-id="51918-157">Die Microsoft Compliance Erweiterung umgeht die Beschränkungen der Liste der nicht zugelassenen Apps für die Computer, auf denen sie installiert ist.</span><span class="sxs-lookup"><span data-stu-id="51918-157">The Microsoft Compliance Extension will bypass the restrictions of the unallowed apps list for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="51918-158">Bereiten Sie Ihre Geräte vor</span><span class="sxs-lookup"><span data-stu-id="51918-158">Prepare your devices</span></span>

1. <span data-ttu-id="51918-159">Verwenden Sie die Verfahren in diesen Topics, um Ihre Geräte zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="51918-159">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="51918-160">Verhinderung von Datenverlust am Endpunkt – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="51918-160">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="51918-161">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="51918-161">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="51918-162">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-162">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="51918-163">Grundlegende Einrichtung Einzel Computer Selfhost</span><span class="sxs-lookup"><span data-stu-id="51918-163">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="51918-164">Diese Methode wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="51918-164">This is the recommended method.</span></span> 

1. <span data-ttu-id="51918-165">Melden Sie sich an dem Windows 10-Computer an, auf dem Sie die Microsoft Compliance Erweiterung installieren möchten, und führen Sie das PowerShell-Skript als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="51918-165">Sign on to the Windows 10 computer that you want to install the Microsoft Compliance Extension on and run the this PowerShell script as an administrator.</span></span> 

```powershell
Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
``` 

2.  <span data-ttu-id="51918-166">[Navigieren Sie zu Microsoft Compliance Erweiterung- Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="51918-166">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>
3.  <span data-ttu-id="51918-167">Installieren Sie die Erweiterung anhand der Anweisungen auf der Seite des Chrome Web Store.</span><span class="sxs-lookup"><span data-stu-id="51918-167">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="51918-168">Bereitstellen mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="51918-168">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="51918-169">Verwenden Sie diese Einrichtungsmethode für organisationsweite Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="51918-169">Use this setup method for organization Wide deployments</span></span> 

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="51918-170">Erforderlichen Registrierungsschlüssel über Microsoft Endpoint Manager aktivieren</span><span class="sxs-lookup"><span data-stu-id="51918-170">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="51918-171">Erstellen Sie ein PowerShell-Skript mit dem folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="51918-171">Create a PowerShell script with the following contents:</span></span>
```powershell
Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```
2.  <span data-ttu-id="51918-172">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="51918-172">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>
3.  <span data-ttu-id="51918-173">Navigieren Sie zu **Geräte** > **-Skripte** und wählen Sie **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="51918-173">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>
4.  <span data-ttu-id="51918-174">Navigieren Sie zu dem Speicherort des erstellten Skripts, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="51918-174">Browse to the location of the script created when prompted.</span></span>
5.  <span data-ttu-id="51918-175">Wählen Sie die folgenden Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="51918-175">Select the following settings:</span></span>
    1. <span data-ttu-id="51918-176">Führen Sie dieses Skript mit den angemeldeten Anmeldedaten aus: JA</span><span class="sxs-lookup"><span data-stu-id="51918-176">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="51918-177">Skript-Signaturprüfung erzwingen: NEIN</span><span class="sxs-lookup"><span data-stu-id="51918-177">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="51918-178">Skript in 64-Bit-PowerShell-Host ausführen: JA</span><span class="sxs-lookup"><span data-stu-id="51918-178">Run script in 64-bit PowerShell Host: YES</span></span>
6.  <span data-ttu-id="51918-179">Wählen Sie die richtigen Gerätegruppen aus und wenden Sie die Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="51918-179">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="51918-180">Microsoft Endpoint Manager Schritte zur erzwungenen Installation</span><span class="sxs-lookup"><span data-stu-id="51918-180">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="51918-181">Bevor Sie die Microsoft Compliance Erweiterung in die Liste der zwangsinstallierten Erweiterungen aufnehmen, ist es wichtig, das Chrome-ADMX einzulesen.</span><span class="sxs-lookup"><span data-stu-id="51918-181">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="51918-182">Die Schritte für diesen Vorgang im Microsoft Endpoint Manager werden von Google dokumentiert: [Verwalten des Chrome-Browsers mit Microsoft Intune – Google Chrome Enterprise-Hilfe](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="51918-182">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="51918-183">Nach dem Einlesen des ADMX können die folgenden Schritte ausgeführt werden, um ein Konfigurationsprofil für diese Erweiterung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51918-183">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="51918-184">Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="51918-184">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com)</span></span>
2.  <span data-ttu-id="51918-185">Navigieren Sie zu den Konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="51918-185">Navigate to Configuration Profiles.</span></span>
3.  <span data-ttu-id="51918-186">Wählen Sie **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="51918-186">Select **Create Profile**.</span></span>
4.  <span data-ttu-id="51918-187">Wählen Sie **Windows 10** als Plattform aus.</span><span class="sxs-lookup"><span data-stu-id="51918-187">Select **Windows 10** as the platform.</span></span>
5.  <span data-ttu-id="51918-188">Wählen Sie **Benutzerdefiniert** als Profiltyp.</span><span class="sxs-lookup"><span data-stu-id="51918-188">Select **Custom** as profile type.</span></span>
6.  <span data-ttu-id="51918-189">Wählen Sie die Registerkarte **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="51918-189">Select the **Settings** tab.</span></span>
7.  <span data-ttu-id="51918-190">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="51918-190">Select **Add**.</span></span>
8.  <span data-ttu-id="51918-191">Geben Sie die folgenden Richtlinieninformationen ein.</span><span class="sxs-lookup"><span data-stu-id="51918-191">Enter the following policy information.</span></span>
<span data-ttu-id="51918-192">OMA-URI: ./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist Datentyp: String Wert: <enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/></span><span class="sxs-lookup"><span data-stu-id="51918-192">OMA-URI: ./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist Data type: String Value: <enabled/><data id=”ExtensionInstallForcelistDesc” value=”1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/></span></span>

9.  <span data-ttu-id="51918-193">Klicken Sie auf Erstellen.</span><span class="sxs-lookup"><span data-stu-id="51918-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="51918-194">Bereitstellen über Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="51918-194">Deploy using Group Policy</span></span>

<span data-ttu-id="51918-195">Wenn Sie Microsoft Endpoint Manager nicht verwenden möchten, können Sie Gruppenrichtlinien verwenden, um die Microsoft Compliance Erweiterung in Ihrem Unternehmen bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="51918-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="51918-196">Ihre Geräte müssen über Gruppenrichtlinien verwaltbar sein, und Sie müssen alle Chrome-ADMXs in den zentralen Gruppenrichtlinienspeicher importieren.</span><span class="sxs-lookup"><span data-stu-id="51918-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="51918-197">Weitere Informationen finden Sie unter [Erstellen und Verwalten des zentralen Speichers für administrative Gruppenrichtlinienvorlagen in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="51918-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>
2.  <span data-ttu-id="51918-198">Erstellen Sie damit ein PowerShell-Skript:</span><span class="sxs-lookup"><span data-stu-id="51918-198">Create a PowerShell script using this:</span></span>

```powershell
et-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

3.  <span data-ttu-id="51918-199">Öffnen Sie die **Gruppenrichtlinien-Verwaltungskonsole** und navigieren Sie zu Ihrer Organisationseinheit (OU).</span><span class="sxs-lookup"><span data-stu-id="51918-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>
4.  <span data-ttu-id="51918-200">Klicken Sie mit der rechten Maustaste und wählen Sie **GPO in dieser Domäne erstellen und hier verlinken**.</span><span class="sxs-lookup"><span data-stu-id="51918-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="51918-201">Wenn Sie dazu aufgefordert werden, geben Sie diesem Gruppenrichtlinienobjekt (GPO) einen beschreibenden Namen und schließen Sie die Erstellung ab.</span><span class="sxs-lookup"><span data-stu-id="51918-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>
5.  <span data-ttu-id="51918-202">Klicken Sie mit der rechten Maustaste auf das GPO und wählen Sie **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="51918-202">Right-click the GPO and select **Edit**.</span></span>
6.  <span data-ttu-id="51918-203">Gehen Sie zu **Computerkonfiguration** > **Einstellungen** > **Systemsteuerung Einstellungen** > **Geplante Tasks**.</span><span class="sxs-lookup"><span data-stu-id="51918-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>
7.  <span data-ttu-id="51918-204">Erstellen Sie eine neue Sofortaufgabe, indem Sie mit der rechten Maustaste klicken und **Neue** > **Sofortaufgabe wählen (mindestens Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="51918-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>
8.  <span data-ttu-id="51918-205">Geben Sie der Aufgabe einen Namen und eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="51918-205">Give the task a name & description.</span></span>
9.  <span data-ttu-id="51918-206">Wählen Sie das entsprechende Konto, um die Sofortaufgabe auszuführen, z. B. NT Authority</span><span class="sxs-lookup"><span data-stu-id="51918-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>
10. <span data-ttu-id="51918-207">Wählen Sie **Ausführen mit höchsten Rechten**.</span><span class="sxs-lookup"><span data-stu-id="51918-207">Select **Run with highest privileges**.</span></span>
11. <span data-ttu-id="51918-208">Konfigurieren Sie die Richtlinie für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="51918-208">Configure the policy for Windows 10.</span></span>
12. <span data-ttu-id="51918-209">Wählen Sie auf der Registerkarte **Aktionen** die Aktion **Programm starten**.</span><span class="sxs-lookup"><span data-stu-id="51918-209">In the **Actions** tab, select the action **Start a program**.</span></span>
13. <span data-ttu-id="51918-210">Geben Sie den Pfad zu dem in Schritt 1 erstellten Programm/Skript ein.</span><span class="sxs-lookup"><span data-stu-id="51918-210">Enter the path to the Program/Script created in Step 1.</span></span>
14. <span data-ttu-id="51918-211">Wählen Sie **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="51918-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="51918-212">Hinzufügen der Chrome-Erweiterung zur ForceInstall-Liste</span><span class="sxs-lookup"><span data-stu-id="51918-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="51918-213">Navigieren Sie im Gruppenrichtlinien-Verwaltungseditor zu Ihrer OU.</span><span class="sxs-lookup"><span data-stu-id="51918-213">In the Group Policy Management Editor, navigate to your OU.</span></span>
2.  <span data-ttu-id="51918-214">Erweitern Sie den folgenden Pfad **Computer-/Benutzerkonfiguration** > **Richtlinien** > **Administrative Vorlagen** > **Klassische administrative Vorlagen** > **Google** > **Google Chrome** > **Erweiterungen**.</span><span class="sxs-lookup"><span data-stu-id="51918-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="51918-215">Dieser Pfad kann je nach Ihrer Konfiguration variieren.</span><span class="sxs-lookup"><span data-stu-id="51918-215">This path may vary depending on your configuration.</span></span>
3.  <span data-ttu-id="51918-216">Wählen Sie **Liste der zwangsinstallierten Erweiterungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="51918-216">Select **Configure the list of force-installed extensions**.</span></span>
4.  <span data-ttu-id="51918-217">Klicken Sie mit der rechten Maustaste und wählen Sie **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="51918-217">Right click and select **Edit**.</span></span>
5.  <span data-ttu-id="51918-218">Wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="51918-218">Select **Enabled**.</span></span>
6.  <span data-ttu-id="51918-219">Wählen Sie **Anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="51918-219">Select **Show**.</span></span>
7.  <span data-ttu-id="51918-220">Fügen Sie unter **Wert** den folgenden Eintrag hinzu: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="51918-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>
8.  <span data-ttu-id="51918-221">Wählen Sie **OK** und dann **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="51918-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="51918-222">Testen der Erweiterung</span><span class="sxs-lookup"><span data-stu-id="51918-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="51918-223">Zum Cloud-Dienst hochladen oder Zugriff durch nicht zugelassene Browser Cloud Egress</span><span class="sxs-lookup"><span data-stu-id="51918-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="51918-224">Ein vertrauliches Element erstellen oder beziehen und versuchen, eine Datei in eine der eingeschränkten Dienstdomänen Ihres Unternehmens hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="51918-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="51918-225">Die vertraulichen Daten müssen einem unserer eingebauten [Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md) oder einem der Typ vertraulicher Informationen Ihrer Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="51918-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="51918-226">Sie sollten auf dem Gerät, von dem aus Sie testen, eine DLP-Popupbenachrichtigung erhalten, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51918-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="51918-227">Testen anderer DLP-Szenarien in Chrome</span><span class="sxs-lookup"><span data-stu-id="51918-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="51918-228">Nachdem Sie nun Chrome aus der Liste der nicht zugelassenen Browser/Apps entfernt haben, können Sie die folgenden Szenarien testen, um zu bestätigen, dass das Verhalten den Anforderungen Ihrer Organisation entspricht:</span><span class="sxs-lookup"><span data-stu-id="51918-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="51918-229">Daten aus einem vertraulichem Element in ein anderes Dokument über die Zwischenablage kopieren</span><span class="sxs-lookup"><span data-stu-id="51918-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="51918-230">Öffnen Sie zum Testen eine Datei, die gegen Aktionen von Kopieren in die Zwischenablage geschützt ist, im Chrome-Browser und versuchen Sie, Daten aus der Datei zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="51918-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="51918-231">Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51918-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="51918-232">Drucken eines Dokuments</span><span class="sxs-lookup"><span data-stu-id="51918-232">Print a document</span></span>
    - <span data-ttu-id="51918-233">Öffnen Sie zum Testen eine Datei, die gegen Druckaktionen geschützt ist, im Chrome-Browser und versuchen Sie, die Datei zu drucken.</span><span class="sxs-lookup"><span data-stu-id="51918-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="51918-234">Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51918-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="51918-235">Auf USB-Wechseldatenträger kopieren</span><span class="sxs-lookup"><span data-stu-id="51918-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="51918-236">Versuchen Sie zum Test, die Datei auf einem Wechselmedium zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51918-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="51918-237">Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51918-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="51918-238">Auf Netzwerkfreigabe kopieren</span><span class="sxs-lookup"><span data-stu-id="51918-238">Copy to Network Share</span></span>
    - <span data-ttu-id="51918-239">Versuchen Sie zum Test, die Datei auf einer Netzwerkfreigabe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51918-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="51918-240">Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="51918-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="51918-241">Verwenden Sie das Verwaltung von Benachrichtigungen Dashboard, um Chrome DLP-Benachrichtigungen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="51918-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="51918-242">Öffnen Sie die **Seite zur Verhinderung von Datenverlust** im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) und wählen Sie **Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="51918-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="51918-243">Wenden Sie in [Konfigurieren und Anzeigen von Benachrichtigungen für DLP-Richtlinien](dlp-configure-view-alerts-policies.md) beschriebenen Verfahrensweisen an, um Benachrichtigungen für Ihre Endpunkt-DLP-Richtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="51918-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="51918-244">Anzeigen von Endpunkt-DLP-Daten im Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="51918-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="51918-245">Öffnen Sie im Microsoft 365 Compliance Center die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne, und wählen Sie den **Aktivitäten-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="51918-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="51918-246">Unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) erfahren Sie Näheres dazu, wie Sie auf alle Daten zu Ihren Endpunktgeräten zugreifen und diese filtern können.</span><span class="sxs-lookup"><span data-stu-id="51918-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51918-247">![Aktivitäten-Explorer-Filter für Endpunktgeräte](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="51918-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="51918-248">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="51918-248">Next steps</span></span>
<span data-ttu-id="51918-249">Jetzt, da Geräte eingebunden sind und entsprechende Aktivitätsdaten im Aktivitäten-Explorer angezeigt werden, können Sie mit dem nächsten Schritt fortfahren, bei dem Sie DLP-Richtlinien zum Schutz Ihrer vertraulichen Elemente erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="51918-249">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="51918-250">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-250">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="51918-251">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51918-251">See also</span></span>

- [<span data-ttu-id="51918-252">Informationen zur Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-252">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="51918-253">Verwenden der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-253">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="51918-254">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="51918-254">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="51918-255">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="51918-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="51918-256">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="51918-256">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="51918-257">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51918-257">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="51918-258">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="51918-258">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="51918-259">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="51918-259">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="51918-260">Azure AD-verbundene Geräte</span><span class="sxs-lookup"><span data-stu-id="51918-260">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="51918-261">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="51918-261">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
