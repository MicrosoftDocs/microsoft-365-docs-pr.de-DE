---
title: Nutzung von Endpunkt-DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) so konfigurieren können, dass Microsoft 365-EPDLP-Speicherorte (Endpoint Data Loss Prevention) verwendet werden.
ms.openlocfilehash: 0a6883bd785141af6f198f0cd871c11794618e27
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561682"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="5e0c8-103">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5e0c8-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="5e0c8-104">In diesem Artikel werden drei Szenarien beschrieben, in denen Sie eine DLP-Richtlinie erstellen und ändern, die Geräte als Speicherort verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="5e0c8-105">DLP-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5e0c8-105">DLP settings</span></span>

<span data-ttu-id="5e0c8-106">Bevor Sie beginnen, sollten Sie die DLP-Einstellungen festlegen, die auf alle DLP-Richtlinien für Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="5e0c8-107">Diese müssen konfiguriert werden, wenn Sie beabsichtigen, Richtlinien zu erstellen, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="5e0c8-108">Einschränkungen des Cloud-Ausgangs</span><span class="sxs-lookup"><span data-stu-id="5e0c8-108">cloud egress restrictions</span></span>
- <span data-ttu-id="5e0c8-109">Beschränkungen für nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="5e0c8-109">unallowed apps restrictions</span></span>

<span data-ttu-id="5e0c8-110">Oder</span><span class="sxs-lookup"><span data-stu-id="5e0c8-110">Or</span></span>

- <span data-ttu-id="5e0c8-111">Wenn Sie „verrauschte“ Dateipfade von der Überwachung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="5e0c8-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5e0c8-112">![DLP-Einstellungen](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="5e0c8-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="5e0c8-113">Ausschluss von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="5e0c8-113">File path exclusions</span></span>

<span data-ttu-id="5e0c8-114">Es empfiehlt sich, bestimmte Pfade von der DLP-Überwachung, -Benachrichtigung und -Richtlinienerzwingung auf Ihren Geräten auszuschließen, wenn sie zu verrauscht sind oder keine Dateien enthalten, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="5e0c8-115">Dateien an diesen Speicherorten werden nicht überwacht, und solche, die an diesen Speicherorten erstellt oder geändert werden, unterliegen nicht der DLP-Richtlinienerzwingung.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="5e0c8-116">In den DLP-Einstellungen können Sie Pfadausschlüsse konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="5e0c8-117">Sie können diese Logik verwenden, um Ihre Pfadausschlüsse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="5e0c8-118">Gültiger Dateipfad, der mit "\" endet, was für Dateien nur unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="5e0c8-119">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="5e0c8-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="5e0c8-120">Gültiger Dateipfad, der mit "\*" endet, was für Dateien nur in Unterordnern zusätzlich zu den Dateien unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="5e0c8-121">Beispiel: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="5e0c8-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="5e0c8-122">Gültiger Dateipfad, der ohne "\" oder "\*" endet, was alle Dateien unmittelbar in dem Ordner und allen Unterordnern bedeutet.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="5e0c8-123">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="5e0c8-123">For example: C:\Temp</span></span>

- <span data-ttu-id="5e0c8-124">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="5e0c8-125">Beispiel: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="5e0c8-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="5e0c8-126">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite und mit "(number)", um die genaue Anzahl von Unterordnern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="5e0c8-127">Beispiel: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="5e0c8-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="5e0c8-128">Ein Pfad mit SYSTEM-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="5e0c8-129">Beispiel: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="5e0c8-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="5e0c8-130">Eine Kombination aus allen vorstehenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-130">A mix of all the above.</span></span> <br/><span data-ttu-id="5e0c8-131">Beispiel: „%SystemDrive%\Users\*\Documents\*(2)\Sub\“</span><span class="sxs-lookup"><span data-stu-id="5e0c8-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub\</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="5e0c8-132">Nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="5e0c8-132">Unallowed apps</span></span>

<span data-ttu-id="5e0c8-133">Wenn die Einstellung **Zugriff durch nicht zulässige Apps und Browser** einer Richtlinie aktiviert ist und Benutzer versuchen, solche Apps für den Zugriff auf eine geschützte Datei zu verwenden, wird die Aktivität zugelassen, blockiert oder blockiert, aber die Benutzer können die Einschränkung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="5e0c8-134">Alle Aktivitäten werden überwacht und können im Aktivitäten-Explorer überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e0c8-135">Es wird nicht der Pfad zu der ausführbaren Datei angegeben, sondern nur der ausführbare Name (z. B. „browser.exe“).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="5e0c8-136">Browser- und Domäneneinschränkungen:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-136">Browser and domain restrictions</span></span>
<span data-ttu-id="5e0c8-137">Schränken Sie die Freigabe sensibler Dateien, die Ihren Richtlinien entsprechen, für uneingeschränkte Clouddienstdomänen ein.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="5e0c8-138">Dienstdomänen</span><span class="sxs-lookup"><span data-stu-id="5e0c8-138">Service domains</span></span>

<span data-ttu-id="5e0c8-139">Sie können steuern, ob sensible Dateien, die durch Ihre Richtlinien geschützt sind, von Microsoft Edge aus in bestimmte Dienstdomänen hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="5e0c8-140">Wenn der Listenmodus auf **Blockieren** festgelegt ist, können Benutzer keine vertraulichen Elemente in diese Domänen hochladen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="5e0c8-141">Wenn eine Upload-Aktion blockiert wird, weil ein Element von einer DLP-Richtlinie betroffen ist, generiert DLP entweder eine Warnung oder sperrt den Upload des vertraulichen Elements.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="5e0c8-142">Wenn der Listenmodus auf **Zulassen** festgelegt ist, können Benutzer vertrauliche Elemente \**_nur_* _ in diese Domänen hochladen, während der Uploadzugriff auf alle anderen Domänen nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="5e0c8-143">Nicht zulässige Browser</span><span class="sxs-lookup"><span data-stu-id="5e0c8-143">Unallowed browsers</span></span>

<span data-ttu-id="5e0c8-144">Sie können Browser hinzufügen, die anhand ihrer ausführbaren Namen identifiziert werden und am Zugriff auf Dateien gehindert werden, die den Bedingungen einer erzwungenen DLP-Richtlinie entsprechen, bei denen die Einschränkung von Clouddienst-Uploads auf „Blockieren“ oder „Blockieren/außer Kraft setzen“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="5e0c8-145">Wenn diese Browser am Zugriff auf eine Datei gehindert werden, wird den Endbenutzern eine Popupbenachrichtigung angezeigt, in der sie aufgefordert werden, die Datei über Microsoft Edge Chromium zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="always-audit-file-activity-from-onboarded-devices"></a><span data-ttu-id="5e0c8-146">Dateiaktivitäten von eingebundenen Geräten immer prüfen</span><span class="sxs-lookup"><span data-stu-id="5e0c8-146">Always audit file activity from onboarded devices</span></span>

<span data-ttu-id="5e0c8-147">Steuern Sie, ob die DLP-Aktivität für Office-, PDF- und CSV-Dateien automatisch überwacht wird und zur Überprüfung in der Überwachungstelemetrie und im Aktivitäten-Explorer von eingebundenen Geräten aus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-147">Control whether DLP activity for Office, PDF, and CSV files is automatically audited and available for review in the audit telemetry and the Activity Explorer from onboarded devices.</span></span> 

<span data-ttu-id="5e0c8-148">Wenn diese Option aktiviert ist (Standardeinstellung), wird die Dateiaktivität bei eingebundenen Geräten immer überwacht, unabhängig davon, ob sie in einer aktiven DLP-Richtlinie enthalten sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-148">If this is turned On (the default), file activity is always audited for onboarded devices, regardless of whether or not they are included in an active DLP policy.</span></span>
<span data-ttu-id="5e0c8-149">Wenn diese Option deaktiviert ist, wird die Dateiaktivität bei eingebundenen Geräten nur dann überwacht, wenn sie in einer aktiven DLP-Richtlinie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-149">If this is turned off, file activity is audited for onboarded devices only when they are included in an active DLP policy.</span></span> 


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="5e0c8-150">DLP-Einstellungen kombinieren</span><span class="sxs-lookup"><span data-stu-id="5e0c8-150">Tying DLP settings together</span></span>

<span data-ttu-id="5e0c8-151">Mithilfe von Endpunkt-DLP und des Edge Chromium-Webbrowsers können Sie die unbeabsichtigte Freigabe von vertraulichen Elementen für nicht zulässige Cloud-Apps und -Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-151">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="5e0c8-152">Edge Chromium erkennt, wenn für ein Element eine Einschränkung aufgrund einer Endpunkt-DLP-Richtlinie gilt, und erzwingt entsprechende Zugriffsbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-152">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="5e0c8-153">Bei Verwendung von Endpunkt-DLP als Speicherort in einer entsprechend konfigurierten DLP-Richtlinie und des Edge Chromium-Browsers, werden die nicht zugelassenen Browser, die Sie in diesen Einstellungen definiert haben, am Zugriff auf vertrauliche Elemente gehindert, die Ihren DLP-Richtlinienvorgaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-153">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="5e0c8-154">Stattdessen werden Benutzer zur Verwendung von Edge Chromium umgeleitet, und dieser kann aufgrund von DLP-Restriktionen Aktivitäten blockieren oder einschränken, wenn die Bedingungen in der DLP-Richtlinie erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-154">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="5e0c8-155">Um diese Einschränkung nutzen zu können, müssen Sie drei wichtige Elemente konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-155">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="5e0c8-156">Angabe der Speicherorte – Dienste, Domänen und IP-Adressen –, aus denen keine vertraulichen Elemente freigegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-156">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="5e0c8-157">Hinzufügen der Browser, die nicht berechtigt sind, auf bestimmte vertrauliche Elemente zuzugreifen, wenn eine DLP-Richtlinienübereinstimmung gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-157">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="5e0c8-158">Konfigurieren von DLP-Richtlinien, um die Arten von vertraulichen Elementen zu definieren, für die Uploads auf diese Orte beschränkt werden sollen, indem Sie _ *Zu Clouddiensten hochladen*\* und **Zugriff durch nicht zulässige Browser** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-158">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on _ *Upload to cloud services*\* and **Access from unallowed browser**.</span></span>

<span data-ttu-id="5e0c8-159">Sie können weitere neue Dienste, Apps und Richtlinien hinzufügen, um Ihre Beschränkungen zur Erfüllung Ihrer geschäftlichen Anforderungen und zum Schutz vertraulicher Daten auszudehnen und restriktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-159">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="5e0c8-160">Diese Konfiguration trägt dazu bei, sicherzustellen, dass Ihre Daten geschützt bleiben, zugleich werden unnötige Beschränkungen vermieden, die Benutzer am Zugriff auf und Freigeben von nicht vertraulichen Elementen hindern oder dies einschränken.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-160">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="5e0c8-161">Szenarien für Endpunkt-DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5e0c8-161">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="5e0c8-162">Damit Sie sich mit Endpunkt-DLP-Features und deren Wirkungsweise in DLP-Richtlinien vertraut machen können, haben wir einige Szenarien für Sie zur Übung zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-162">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="5e0c8-163">Sämtliche Endpunkt-DLP-Inhalte werden in den Haupt-DLP-Inhalt einbezogen, sobald Endpunkt-DLP allgemein verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-163">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e0c8-164">Diese Endpunkt-DLP-Szenarien stellen nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien dar.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-164">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="5e0c8-165">In den folgenden Beiträgen finden Sie Informationen zum Arbeiten mit DLP-Richtlinien in Situationen allgemeiner Art:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-165">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="5e0c8-166">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5e0c8-166">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="5e0c8-167">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5e0c8-167">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="5e0c8-168">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="5e0c8-168">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="5e0c8-169">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5e0c8-169">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="5e0c8-170">Szenario 1: Erstellen einer Richtlinie aus einer Vorlage, nur überwachen</span><span class="sxs-lookup"><span data-stu-id="5e0c8-170">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="5e0c8-171">Bei diesen Szenarien ist es erforderlich, dass Sie bereits über Geräte verfügen, die in den Aktivitäten-Explorer eingebunden sind und für die Berichte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-171">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="5e0c8-172">Wenn Sie noch keine Geräte eingebunden haben, lesen Sie [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-172">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="5e0c8-173">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-173">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="5e0c8-174">Wählen Sie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-174">Choose **Create policy**.</span></span>

3. <span data-ttu-id="5e0c8-175">Wählen Sie für dieses Szenario **Datenschutz**, dann **USA: Personenbezogene Informationen (PII)** und schließlich **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-175">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="5e0c8-176">Setzen Sie das Feld **Status** für alle Orte außer **Geräte** auf "Aus".</span><span class="sxs-lookup"><span data-stu-id="5e0c8-176">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="5e0c8-177">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-177">Choose **Next**.</span></span>

5. <span data-ttu-id="5e0c8-178">Übernehmen Sie die Standardauswahl **Einstellungen in der Vorlage überprüfen und anpassen** Auswahl, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-178">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="5e0c8-179">Übernehmen Sie die standardmäßigen Werte für **Schutzmaßnahmen**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-179">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="5e0c8-180">Wählen Sie **Aktivitäten auf Windows-Geräten überwachen oder einschränken** aus, und lassen Sie die Aktionen auf **Nur Überwachung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-180">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="5e0c8-181">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-181">Choose **Next**.</span></span>

8. <span data-ttu-id="5e0c8-182">Übernehmen Sie den standardmäßigen Wert **Ich möchte sie zuerst testen** und wählen Sie **Richtlinientipps im Testmodus anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-182">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="5e0c8-183">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-183">Choose **Next**.</span></span>

9. <span data-ttu-id="5e0c8-184">Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-184">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="5e0c8-185">Die neue DLP-Richtlinie wird nun in der Richtlinienliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-185">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="5e0c8-186">Überprüfen Sie den Aktivitäten-Explorer auf Daten aus den überwachten Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-186">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="5e0c8-187">Legen Sie den Speicherortfilter für Geräte fest, fügen Sie die Richtlinie hinzu, und filtern Sie anschließend nach dem Richtliniennamen, um festzustellen, welche Auswirkungen diese Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-187">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="5e0c8-188">Lesen Sie bei Bedarf [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-188">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="5e0c8-189">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-189">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="5e0c8-190">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-190">This should trigger the policy.</span></span>

13. <span data-ttu-id="5e0c8-191">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-191">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="5e0c8-192">Szenario 2: Ändern der bestehenden Richtlinie, Festlegen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="5e0c8-192">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="5e0c8-193">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-193">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="5e0c8-194">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA: Personenbezogene Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-194">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="5e0c8-195">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-195">Choose **edit policy**.</span></span>

4. <span data-ttu-id="5e0c8-196">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-196">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="5e0c8-197">Scrollen Sie nach unten zum Abschnitt **Vorfallberichte**, und legen Sie **Benachrichtigung an Administratoren senden, wenn es eine Regelübereinstimmung gibt** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-197">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="5e0c8-198">Es werden automatisch E-Mail-Benachrichtigungen an den Administrator und alle anderen Personen gesendet, die Sie der Empfängerliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-198">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5e0c8-199">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="5e0c8-199">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="5e0c8-200">Wählen Sie im Rahmen dieses Szenarios **Benachrichtigung jedes Mal senden, wenn eine Aktivität der Regel entspricht** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-200">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="5e0c8-201">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-201">Choose **Save**.</span></span>

8. <span data-ttu-id="5e0c8-202">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-202">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="5e0c8-203">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-203">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="5e0c8-204">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-204">This should trigger the policy.</span></span>

10. <span data-ttu-id="5e0c8-205">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-205">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="5e0c8-206">Szenario 3: Ändern der bestehenden Richtlinie, Blockieren der Aktion mit erlaubter Außerkraftsetzung</span><span class="sxs-lookup"><span data-stu-id="5e0c8-206">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="5e0c8-207">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="5e0c8-207">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="5e0c8-208">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA: Personenbezogene Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-208">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="5e0c8-209">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-209">Choose **edit policy**.</span></span>

4. <span data-ttu-id="5e0c8-210">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-210">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="5e0c8-211">Scrollen Sie nach unten zum Abschnitt **Aktivitäten auf Windows-Geräten überwachen oder einschränken**, und legen Sie für jede Aktivität die entsprechende Aktion auf **Blockieren mit Außerkraftsetzung** fest.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-211">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5e0c8-212">![Festlegen der Aktion "Blockieren mit Außerkraftsetzung"](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="5e0c8-212">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="5e0c8-213">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-213">Choose **Save**.</span></span>

7. <span data-ttu-id="5e0c8-214">Wiederholen Sie die Schritte 4-7 für **Große Menge an Inhalten erkannt. USA – persönlich identifizierbare Informationen**.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-214">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="5e0c8-215">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-215">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="5e0c8-216">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-216">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="5e0c8-217">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-217">This should trigger the policy.</span></span>

   <span data-ttu-id="5e0c8-218">Auf dem Clientgerät wird ein Popup wie das folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5e0c8-218">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5e0c8-219">![Benachrichtigung über Außerkraftsetzung von Endpunkt-DLP durch Client](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="5e0c8-219">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="5e0c8-220">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="5e0c8-220">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e0c8-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e0c8-221">See also</span></span>

- [<span data-ttu-id="5e0c8-222">Informationen zu Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="5e0c8-222">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="5e0c8-223">Endpunkt-DLP – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="5e0c8-223">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="5e0c8-224">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5e0c8-224">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="5e0c8-225">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5e0c8-225">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="5e0c8-226">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="5e0c8-226">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="5e0c8-227">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5e0c8-227">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="5e0c8-228">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="5e0c8-228">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="5e0c8-229">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="5e0c8-229">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="5e0c8-230">Azure Active Directory (AAD) Einbindung</span><span class="sxs-lookup"><span data-stu-id="5e0c8-230">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="5e0c8-231">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5e0c8-231">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="5e0c8-232">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5e0c8-232">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="5e0c8-233">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="5e0c8-233">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
