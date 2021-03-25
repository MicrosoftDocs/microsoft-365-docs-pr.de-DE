---
title: Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender ATP für Mac
description: Installieren Sie Microsoft Defender ATP für Mac auf anderen Verwaltungslösungen.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e3a20f0a356a32eddc05b3792c0c04c23197a7b0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185695"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ab263-104">Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="ab263-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab263-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ab263-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab263-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ab263-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab263-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab263-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab263-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ab263-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab263-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ab263-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="ab263-110">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="ab263-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="ab263-111">Bevor Sie beginnen, finden Sie auf der Hauptseite [von Microsoft Defender for Endpoint für Mac](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="ab263-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="ab263-112">Ansatz</span><span class="sxs-lookup"><span data-stu-id="ab263-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="ab263-113">Derzeit unterstützt Microsoft offiziell nur Intune und JAMF für die Bereitstellung und Verwaltung von Microsoft Defender for Endpoint für Mac.</span><span class="sxs-lookup"><span data-stu-id="ab263-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="ab263-114">Microsoft gibt keine ausdrücklichen oder impliziten Gewährleistungen in Bezug auf die unten angegebenen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="ab263-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="ab263-115">Wenn Ihre Organisation eine mobile Geräteverwaltungslösung (Mobile Device Management, MDM) verwendet, die offiziell nicht unterstützt wird, bedeutet dies nicht, dass Sie Microsoft Defender for Endpoint für Mac nicht bereitstellen oder ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ab263-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="ab263-116">Microsoft Defender für Endpoint für Mac ist nicht von herstellerspezifischen Features abhängig.</span><span class="sxs-lookup"><span data-stu-id="ab263-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="ab263-117">Es kann mit jeder beliebigen MDM-Lösung verwendet werden, die die folgenden Features unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ab263-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="ab263-118">Stellen Sie ein macOS .pkg auf verwalteten Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ab263-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="ab263-119">Bereitstellen von macOS-Systemkonfigurationsprofilen auf verwalteten Geräten.</span><span class="sxs-lookup"><span data-stu-id="ab263-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="ab263-120">Führen Sie ein beliebiges vom Administrator konfiguriertes Tool/Skript auf verwalteten Geräten aus.</span><span class="sxs-lookup"><span data-stu-id="ab263-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="ab263-121">Die meisten modernen MDM-Lösungen enthalten diese Features, können sie jedoch anders aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ab263-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="ab263-122">Sie können Defender jedoch ohne die letzte Anforderung aus der vorherigen Liste bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ab263-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="ab263-123">Sie können den Status nicht zentral erfassen</span><span class="sxs-lookup"><span data-stu-id="ab263-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="ab263-124">Wenn Sie sich für die Deinstallation von Defender entscheiden, müssen Sie sich lokal als Administrator am Clientgerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="ab263-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="ab263-125">Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="ab263-125">Deployment</span></span>

<span data-ttu-id="ab263-126">Die meisten MDM-Lösungen verwenden dasselbe Modell für die Verwaltung von macOS-Geräten mit ähnlicher Terminologie.</span><span class="sxs-lookup"><span data-stu-id="ab263-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="ab263-127">Verwenden [Sie die JAMF-basierte Bereitstellung](mac-install-with-jamf.md) als Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ab263-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="ab263-128">Paket</span><span class="sxs-lookup"><span data-stu-id="ab263-128">Package</span></span>

<span data-ttu-id="ab263-129">Konfigurieren Sie die Bereitstellung eines [erforderlichen Anwendungspakets](mac-install-with-jamf.md)mit dem Installationspaket (wdav.pkg), das von [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="ab263-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="ab263-130">Verwenden Sie zum Bereitstellen des Pakets in Ihrem Unternehmen die Anweisungen, die Ihrer MDM-Lösung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ab263-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="ab263-131">Lizenzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="ab263-131">License settings</span></span>

<span data-ttu-id="ab263-132">Richten Sie [ein Systemkonfigurationsprofil ein.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="ab263-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="ab263-133">Ihre MDM-Lösung kann sie etwa als "Profil für benutzerdefinierte Einstellungen" bezeichnen, da Microsoft Defender for Endpoint für Mac nicht Teil von macOS ist.</span><span class="sxs-lookup"><span data-stu-id="ab263-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="ab263-134">Verwenden Sie die Eigenschaftenliste jamf/WindowsDefenderATPOnboarding.plist, die aus einem onboarding-Paket extrahiert werden kann, das aus [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="ab263-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="ab263-135">Ihr System unterstützt möglicherweise eine beliebige Eigenschaftenliste im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="ab263-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="ab263-136">Sie können die Datei jamf/WindowsDefenderATPOnboarding.plist wie in diesem Fall hochladen.</span><span class="sxs-lookup"><span data-stu-id="ab263-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="ab263-137">Alternativ müssen Sie die Eigenschaftenliste möglicherweise zuerst in ein anderes Format konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ab263-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="ab263-138">In der Regel verfügt Ihr benutzerdefiniertes Profil über eine ID, einen Namen oder ein Domänenattribut.</span><span class="sxs-lookup"><span data-stu-id="ab263-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="ab263-139">Sie müssen genau "com.microsoft.wdav.atp" für diesen Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab263-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="ab263-140">MDM verwendet sie zum Bereitstellen der **Einstellungsdatei in /Library/Managed Preferences/com.microsoft.wdav.atp.plist** auf einem Clientgerät, und Defender verwendet diese Datei zum Laden der Onboardinginformationen.</span><span class="sxs-lookup"><span data-stu-id="ab263-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="ab263-141">Kernelerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ab263-141">Kernel extension policy</span></span>

<span data-ttu-id="ab263-142">Richten Sie eine KEXT- oder Kernelerweiterungsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ab263-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="ab263-143">Verwenden Sie die **Team-ID UBF8T346G9,** um von Microsoft bereitgestellte Kernelerweiterungen zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="ab263-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="ab263-144">Systemerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ab263-144">System extension policy</span></span>

<span data-ttu-id="ab263-145">Richten Sie eine Systemerweiterungsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ab263-145">Set up a system extension policy.</span></span> <span data-ttu-id="ab263-146">Verwenden Sie den **Teambezeichner UBF8T346G9,** und genehmigen Sie die folgenden Bündelbezeichner:</span><span class="sxs-lookup"><span data-stu-id="ab263-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="ab263-147">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="ab263-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="ab263-148">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="ab263-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="ab263-149">Richtlinie für den vollständigen Datenträgerzugriff</span><span class="sxs-lookup"><span data-stu-id="ab263-149">Full disk access policy</span></span>

<span data-ttu-id="ab263-150">Gewähren Des vollständigen Festplattenzugriffs auf die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ab263-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="ab263-151">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ab263-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="ab263-152">Bezeichner: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="ab263-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="ab263-153">Bezeichnertyp: Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="ab263-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="ab263-154">Codeanforderung: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ab263-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="ab263-155">Microsoft Defender for Endpoint Security Extension</span><span class="sxs-lookup"><span data-stu-id="ab263-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="ab263-156">Bezeichner: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="ab263-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="ab263-157">Bezeichnertyp: Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="ab263-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="ab263-158">Codeanforderung: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ab263-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="ab263-159">Netzwerkerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ab263-159">Network extension policy</span></span>

<span data-ttu-id="ab263-160">Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint für Mac den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="ab263-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="ab263-161">Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab263-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="ab263-162">Filtertyp: Plugin</span><span class="sxs-lookup"><span data-stu-id="ab263-162">Filter type: Plugin</span></span>
- <span data-ttu-id="ab263-163">Plug-In-Bundle-ID: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="ab263-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="ab263-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="ab263-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="ab263-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ab263-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="ab263-166">Filtersockets: `true`</span><span class="sxs-lookup"><span data-stu-id="ab263-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="ab263-167">Überprüfen des Installationsstatus</span><span class="sxs-lookup"><span data-stu-id="ab263-167">Check installation status</span></span>

<span data-ttu-id="ab263-168">Führen [Sie Microsoft Defender for Endpoint](mac-install-with-jamf.md) auf einem Clientgerät aus, um den Onboardingstatus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ab263-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
