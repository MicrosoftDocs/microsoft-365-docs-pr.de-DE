---
title: Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender for Endpoint für Mac
description: Installieren Sie Microsoft Defender for Endpoint für Mac auf anderen Verwaltungslösungen.
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
ms.openlocfilehash: e929c17ada761a334700f6e66d2921483686834b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861563"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="70aa6-104">Bereitstellung mit einem anderen Mobile Device Management (MDM)-System für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="70aa6-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="70aa6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="70aa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="70aa6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="70aa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="70aa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70aa6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="70aa6-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="70aa6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="70aa6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="70aa6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="70aa6-110">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="70aa6-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="70aa6-111">Bevor Sie beginnen, finden Sie auf der [Hauptseite von Microsoft Defender for Endpoint auf macOS](microsoft-defender-endpoint-mac.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="70aa6-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="approach"></a><span data-ttu-id="70aa6-112">Ansatz</span><span class="sxs-lookup"><span data-stu-id="70aa6-112">Approach</span></span>

> [!CAUTION]

> <span data-ttu-id="70aa6-113">Derzeit unterstützt Microsoft offiziell nur Intune und JAMF für die Bereitstellung und Verwaltung von Microsoft Defender for Endpoint unter macOS.</span><span class="sxs-lookup"><span data-stu-id="70aa6-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="70aa6-114">Microsoft gibt keine ausdrücklichen oder impliziten Gewährleistungen in Bezug auf die unten angegebenen Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="70aa6-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="70aa6-115">Wenn Ihre Organisation eine mobile Geräteverwaltungslösung (Mobile Device Management, MDM) verwendet, die offiziell nicht unterstützt wird, bedeutet dies nicht, dass Sie Microsoft Defender for Endpoint auf macOS nicht bereitstellen oder ausführen können.</span><span class="sxs-lookup"><span data-stu-id="70aa6-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="70aa6-116">Microsoft Defender for Endpoint auf macOS ist nicht von herstellerspezifischen Features abhängig.</span><span class="sxs-lookup"><span data-stu-id="70aa6-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="70aa6-117">Es kann mit jeder beliebigen MDM-Lösung verwendet werden, die die folgenden Features unterstützt:</span><span class="sxs-lookup"><span data-stu-id="70aa6-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="70aa6-118">Stellen Sie ein macOS .pkg auf verwalteten Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="70aa6-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="70aa6-119">Bereitstellen von macOS-Systemkonfigurationsprofilen auf verwalteten Geräten.</span><span class="sxs-lookup"><span data-stu-id="70aa6-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="70aa6-120">Führen Sie ein beliebiges vom Administrator konfiguriertes Tool/Skript auf verwalteten Geräten aus.</span><span class="sxs-lookup"><span data-stu-id="70aa6-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="70aa6-121">Die meisten modernen MDM-Lösungen enthalten diese Features, können sie jedoch anders aufrufen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="70aa6-122">Sie können Defender jedoch ohne die letzte Anforderung aus der vorherigen Liste bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="70aa6-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="70aa6-123">Sie können den Status nicht zentral erfassen</span><span class="sxs-lookup"><span data-stu-id="70aa6-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="70aa6-124">Wenn Sie sich für die Deinstallation von Defender entscheiden, müssen Sie sich lokal als Administrator am Clientgerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="70aa6-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="70aa6-125">Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="70aa6-125">Deployment</span></span>

<span data-ttu-id="70aa6-126">Die meisten MDM-Lösungen verwenden dasselbe Modell für die Verwaltung von macOS-Geräten mit ähnlicher Terminologie.</span><span class="sxs-lookup"><span data-stu-id="70aa6-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="70aa6-127">Verwenden [Sie die JAMF-basierte Bereitstellung](mac-install-with-jamf.md) als Vorlage.</span><span class="sxs-lookup"><span data-stu-id="70aa6-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="70aa6-128">Paket</span><span class="sxs-lookup"><span data-stu-id="70aa6-128">Package</span></span>

<span data-ttu-id="70aa6-129">Konfigurieren Sie die Bereitstellung eines [erforderlichen Anwendungspakets](mac-install-with-jamf.md)mit dem Installationspaket (wdav.pkg), das von [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="70aa6-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="70aa6-130">Verwenden Sie zum Bereitstellen des Pakets in Ihrem Unternehmen die Anweisungen, die Ihrer MDM-Lösung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="70aa6-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="70aa6-131">Lizenzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="70aa6-131">License settings</span></span>

<span data-ttu-id="70aa6-132">Richten Sie [ein Systemkonfigurationsprofil ein.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="70aa6-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> 

<span data-ttu-id="70aa6-133">Ihre MDM-Lösung kann sie etwa als "Profil für benutzerdefinierte Einstellungen" bezeichnen, da Microsoft Defender for Endpoint auf macOS nicht Teil von macOS ist.</span><span class="sxs-lookup"><span data-stu-id="70aa6-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="70aa6-134">Verwenden Sie die Eigenschaftenliste jamf/WindowsDefenderATPOnboarding.plist, die aus einem onboarding-Paket extrahiert werden kann, das aus [Microsoft Defender Security Center heruntergeladen wurde.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="70aa6-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="70aa6-135">Ihr System unterstützt möglicherweise eine beliebige Eigenschaftenliste im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="70aa6-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="70aa6-136">Sie können die Datei jamf/WindowsDefenderATPOnboarding.plist wie in diesem Fall hochladen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="70aa6-137">Alternativ müssen Sie die Eigenschaftenliste möglicherweise zuerst in ein anderes Format konvertieren.</span><span class="sxs-lookup"><span data-stu-id="70aa6-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="70aa6-138">In der Regel verfügt Ihr benutzerdefiniertes Profil über eine ID, einen Namen oder ein Domänenattribut.</span><span class="sxs-lookup"><span data-stu-id="70aa6-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="70aa6-139">Sie müssen genau "com.microsoft.wdav.atp" für diesen Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="70aa6-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="70aa6-140">MDM verwendet sie zum Bereitstellen der **Einstellungsdatei in /Library/Managed Preferences/com.microsoft.wdav.atp.plist** auf einem Clientgerät, und Defender verwendet diese Datei zum Laden der Onboardinginformationen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="70aa6-141">Kernelerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="70aa6-141">Kernel extension policy</span></span>

<span data-ttu-id="70aa6-142">Richten Sie eine KEXT- oder Kernelerweiterungsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="70aa6-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="70aa6-143">Verwenden Sie die **Team-ID UBF8T346G9,** um von Microsoft bereitgestellte Kernelerweiterungen zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="70aa6-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="70aa6-144">Wenn Ihre Umgebung aus Apple Silicon (M1)-Geräten besteht, sollten diese Computer keine Konfigurationsprofile mit KEXT-Richtlinien erhalten.</span><span class="sxs-lookup"><span data-stu-id="70aa6-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="70aa6-145">Apple unterstützt KEXT auf diesen Computern nicht, die Bereitstellung eines solchen Profils würde auf M1-Computern fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="70aa6-146">Systemerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="70aa6-146">System extension policy</span></span>

<span data-ttu-id="70aa6-147">Richten Sie eine Systemerweiterungsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="70aa6-147">Set up a system extension policy.</span></span> <span data-ttu-id="70aa6-148">Verwenden Sie den **Teambezeichner UBF8T346G9,** und genehmigen Sie die folgenden Bündelbezeichner:</span><span class="sxs-lookup"><span data-stu-id="70aa6-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="70aa6-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="70aa6-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="70aa6-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="70aa6-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="70aa6-151">Richtlinie für den vollständigen Datenträgerzugriff</span><span class="sxs-lookup"><span data-stu-id="70aa6-151">Full disk access policy</span></span>

<span data-ttu-id="70aa6-152">Gewähren Des vollständigen Festplattenzugriffs auf die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="70aa6-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="70aa6-153">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="70aa6-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="70aa6-154">Bezeichner: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="70aa6-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="70aa6-155">Bezeichnertyp: Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="70aa6-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="70aa6-156">Codeanforderung: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="70aa6-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="70aa6-157">Microsoft Defender for Endpoint Security Extension</span><span class="sxs-lookup"><span data-stu-id="70aa6-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="70aa6-158">Bezeichner: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="70aa6-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="70aa6-159">Bezeichnertyp: Bundle-ID</span><span class="sxs-lookup"><span data-stu-id="70aa6-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="70aa6-160">Codeanforderung: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="70aa6-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="70aa6-161">Netzwerkerweiterungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="70aa6-161">Network extension policy</span></span>

<span data-ttu-id="70aa6-162">Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint auf macOS den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="70aa6-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="70aa6-163">Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="70aa6-164">Filtertyp: Plugin</span><span class="sxs-lookup"><span data-stu-id="70aa6-164">Filter type: Plugin</span></span>
- <span data-ttu-id="70aa6-165">Plug-In-Bundle-ID: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="70aa6-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="70aa6-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="70aa6-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="70aa6-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="70aa6-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="70aa6-168">Filtersockets: `true`</span><span class="sxs-lookup"><span data-stu-id="70aa6-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="70aa6-169">Überprüfen des Installationsstatus</span><span class="sxs-lookup"><span data-stu-id="70aa6-169">Check installation status</span></span>

<span data-ttu-id="70aa6-170">Führen [Sie Microsoft Defender for Endpoint](mac-install-with-jamf.md) auf einem Clientgerät aus, um den Onboardingstatus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="70aa6-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
