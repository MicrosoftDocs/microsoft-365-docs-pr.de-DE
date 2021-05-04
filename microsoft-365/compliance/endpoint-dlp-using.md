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
ms.openlocfilehash: 1b918346467f9878582dfb301f48e530bfb400f8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114093"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="81100-103">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="81100-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="81100-104">In diesem Artikel werden drei Szenarien beschrieben, in denen Sie eine DLP-Richtlinie erstellen und ändern, die Geräte als Speicherort verwendet.</span><span class="sxs-lookup"><span data-stu-id="81100-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="81100-105">DLP-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="81100-105">DLP settings</span></span>

<span data-ttu-id="81100-106">Bevor Sie beginnen, sollten Sie die DLP-Einstellungen festlegen, die auf alle DLP-Richtlinien für Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="81100-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="81100-107">Diese müssen konfiguriert werden, wenn Sie beabsichtigen, Richtlinien zu erstellen, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="81100-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="81100-108">Einschränkungen des Cloud-Ausgangs</span><span class="sxs-lookup"><span data-stu-id="81100-108">cloud egress restrictions</span></span>
- <span data-ttu-id="81100-109">Beschränkungen für nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="81100-109">unallowed apps restrictions</span></span>

<span data-ttu-id="81100-110">Oder</span><span class="sxs-lookup"><span data-stu-id="81100-110">Or</span></span>

- <span data-ttu-id="81100-111">Wenn Sie „verrauschte“ Dateipfade von der Überwachung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="81100-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="81100-112">![DLP-Einstellungen](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="81100-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="81100-113">Ausschluss von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="81100-113">File path exclusions</span></span>

<span data-ttu-id="81100-114">Es empfiehlt sich, bestimmte Pfade von der DLP-Überwachung, -Benachrichtigung und -Richtlinienerzwingung auf Ihren Geräten auszuschließen, wenn sie zu verrauscht sind oder keine Dateien enthalten, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="81100-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="81100-115">Dateien an diesen Speicherorten werden nicht überwacht, und solche, die an diesen Speicherorten erstellt oder geändert werden, unterliegen nicht der DLP-Richtlinienerzwingung.</span><span class="sxs-lookup"><span data-stu-id="81100-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="81100-116">In den DLP-Einstellungen können Sie Pfadausschlüsse konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="81100-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="81100-117">Sie können diese Logik verwenden, um Ihre Pfadausschlüsse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="81100-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="81100-118">Gültiger Dateipfad, der mit "\" endet, was für Dateien nur unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="81100-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="81100-119">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="81100-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="81100-120">Gültiger Dateipfad, der mit "\*" endet, was für Dateien nur in Unterordnern zusätzlich zu den Dateien unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="81100-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="81100-121">Beispiel: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="81100-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="81100-122">Gültiger Dateipfad, der ohne "\" oder "\*" endet, was alle Dateien unmittelbar in dem Ordner und allen Unterordnern bedeutet.</span><span class="sxs-lookup"><span data-stu-id="81100-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="81100-123">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="81100-123">For example: C:\Temp</span></span>

- <span data-ttu-id="81100-124">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite.</span><span class="sxs-lookup"><span data-stu-id="81100-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="81100-125">Beispiel: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="81100-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="81100-126">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite und mit "(number)", um die genaue Anzahl von Unterordnern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="81100-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="81100-127">Beispiel: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="81100-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="81100-128">Ein Pfad mit SYSTEM-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="81100-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="81100-129">Beispiel: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="81100-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="81100-130">Eine Kombination aus allen vorstehenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="81100-130">A mix of all the above.</span></span> <br/><span data-ttu-id="81100-131">Beispiel: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="81100-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="81100-132">Nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="81100-132">Unallowed apps</span></span>

<span data-ttu-id="81100-133">Wenn die Einstellung **Zugriff durch nicht zulässige Apps und Browser** einer Richtlinie aktiviert ist und Benutzer versuchen, solche Apps für den Zugriff auf eine geschützte Datei zu verwenden, wird die Aktivität zugelassen, blockiert oder blockiert, aber die Benutzer können die Einschränkung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="81100-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="81100-134">Alle Aktivitäten werden überwacht und können im Aktivitäten-Explorer überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="81100-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81100-135">Es wird nicht der Pfad zu der ausführbaren Datei angegeben, sondern nur der ausführbare Name (z. B. „browser.exe“).</span><span class="sxs-lookup"><span data-stu-id="81100-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="81100-136">Browser- und Domäneneinschränkungen:</span><span class="sxs-lookup"><span data-stu-id="81100-136">Browser and domain restrictions</span></span>
<span data-ttu-id="81100-137">Schränken Sie die Freigabe sensibler Dateien, die Ihren Richtlinien entsprechen, für uneingeschränkte Clouddienstdomänen ein.</span><span class="sxs-lookup"><span data-stu-id="81100-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="81100-138">Dienstdomänen</span><span class="sxs-lookup"><span data-stu-id="81100-138">Service domains</span></span>

<span data-ttu-id="81100-139">Sie können steuern, ob sensible Dateien, die durch Ihre Richtlinien geschützt sind, von Microsoft Edge aus in bestimmte Dienstdomänen hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="81100-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="81100-140">Wenn der Listenmodus auf **Blockieren** festgelegt ist, können Benutzer keine vertraulichen Elemente in diese Domänen hochladen.</span><span class="sxs-lookup"><span data-stu-id="81100-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="81100-141">Wenn eine Upload-Aktion blockiert wird, weil ein Element von einer DLP-Richtlinie betroffen ist, generiert DLP entweder eine Warnung oder sperrt den Upload des vertraulichen Elements.</span><span class="sxs-lookup"><span data-stu-id="81100-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="81100-142">Wenn der Listenmodus auf **Zulassen** festgelegt ist, können Benutzer vertrauliche Elemente **_nur_** in diese Domänen hochladen, während der Uploadzugriff auf alle anderen Domänen nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="81100-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81100-143">Wenn der Diensteinschränkungsmodus auf „Zulassen“ festgelegt ist, müssen Sie über mindestens eine Dienstdomäne verfügen, die konfiguriert wurde, bevor die Einschränkungen erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="81100-143">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="81100-144">Nicht zulässige Browser</span><span class="sxs-lookup"><span data-stu-id="81100-144">Unallowed browsers</span></span>

<span data-ttu-id="81100-145">Sie können Browser hinzufügen, die anhand ihrer ausführbaren Namen identifiziert werden und am Zugriff auf Dateien gehindert werden, die den Bedingungen einer erzwungenen DLP-Richtlinie entsprechen, bei denen die Einschränkung von Clouddienst-Uploads auf „Blockieren“ oder „Blockieren/außer Kraft setzen“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="81100-145">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="81100-146">Wenn diese Browser am Zugriff auf eine Datei gehindert werden, wird den Endbenutzern eine Popupbenachrichtigung angezeigt, in der sie aufgefordert werden, die Datei über Edge Chromium zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="81100-146">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="81100-147">Geschäftliche Begründung in Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="81100-147">Business justification in policy tips</span></span>

<span data-ttu-id="81100-148">Sie können mit den Optionen für die geschäftliche Begründung in den DLP-Richtlinientipp-Benachrichtigung steuern, wie Benutzer interagieren.</span><span class="sxs-lookup"><span data-stu-id="81100-148">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="81100-149">Diese Option erscheint, wenn ein Benutzer eine Aktivität durchführt, die durch die Einstellung **Sperren mit Überschreiben** in einer DLP-Richtlinie geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="81100-149">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="81100-150">Sie können eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="81100-150">You can choose from one the following options:</span></span>

- <span data-ttu-id="81100-151">Standardmäßig kann der Benutzer entweder eine integrierte Begründung auswählen oder seinen eigenen Text eingeben.</span><span class="sxs-lookup"><span data-stu-id="81100-151">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="81100-152">Benutzer können nur eine integrierte Begründung auswählen.</span><span class="sxs-lookup"><span data-stu-id="81100-152">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="81100-153">Benutzer können nur ihre eigene Begründung eingeben.</span><span class="sxs-lookup"><span data-stu-id="81100-153">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="81100-154">DLP-Einstellungen kombinieren</span><span class="sxs-lookup"><span data-stu-id="81100-154">Tying DLP settings together</span></span>

<span data-ttu-id="81100-155">Mithilfe von Endpunkt-DLP und des Edge Chromium-Webbrowsers können Sie die unbeabsichtigte Freigabe von vertraulichen Elementen für nicht zulässige Cloud-Apps und -Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="81100-155">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="81100-156">Edge Chromium erkennt, wenn für ein Element eine Einschränkung aufgrund einer Endpunkt-DLP-Richtlinie gilt, und erzwingt entsprechende Zugriffsbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="81100-156">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="81100-157">Bei Verwendung von Endpunkt-DLP als Speicherort in einer entsprechend konfigurierten DLP-Richtlinie und des Edge Chromium-Browsers, werden die nicht zugelassenen Browser, die Sie in diesen Einstellungen definiert haben, am Zugriff auf vertrauliche Elemente gehindert, die Ihren DLP-Richtlinienvorgaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81100-157">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="81100-158">Stattdessen werden Benutzer zur Verwendung von Edge Chromium umgeleitet, und dieser kann aufgrund von DLP-Restriktionen Aktivitäten blockieren oder einschränken, wenn die Bedingungen in der DLP-Richtlinie erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="81100-158">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="81100-159">Um diese Einschränkung nutzen zu können, müssen Sie drei wichtige Elemente konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="81100-159">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="81100-160">Angabe der Speicherorte – Dienste, Domänen und IP-Adressen –, aus denen keine vertraulichen Elemente freigegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="81100-160">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="81100-161">Hinzufügen der Browser, die nicht berechtigt sind, auf bestimmte vertrauliche Elemente zuzugreifen, wenn eine DLP-Richtlinienübereinstimmung gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="81100-161">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="81100-162">Konfigurieren von DLP-Richtlinien, um die Arten von vertraulichen Elementen zu definieren, für die Uploads auf diese Orte beschränkt werden sollen, indem Sie **Zu Clouddiensten hochladen** und **Zugriff durch nicht zulässige Browser** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81100-162">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="81100-163">Sie können weitere neue Dienste, Apps und Richtlinien hinzufügen, um Ihre Beschränkungen zur Erfüllung Ihrer geschäftlichen Anforderungen und zum Schutz vertraulicher Daten auszudehnen und restriktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="81100-163">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="81100-164">Diese Konfiguration trägt dazu bei, sicherzustellen, dass Ihre Daten geschützt bleiben, zugleich werden unnötige Beschränkungen vermieden, die Benutzer am Zugriff auf und Freigeben von nicht vertraulichen Elementen hindern oder dies einschränken.</span><span class="sxs-lookup"><span data-stu-id="81100-164">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="81100-165">Szenarien für Endpunkt-DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="81100-165">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="81100-166">Damit Sie sich mit Endpunkt-DLP-Features und deren Wirkungsweise in DLP-Richtlinien vertraut machen können, haben wir einige Szenarien für Sie zur Übung zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="81100-166">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81100-167">Diese Endpunkt-DLP-Szenarien stellen nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien dar.</span><span class="sxs-lookup"><span data-stu-id="81100-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="81100-168">In den folgenden Beiträgen finden Sie Informationen zum Arbeiten mit DLP-Richtlinien in Situationen allgemeiner Art:</span><span class="sxs-lookup"><span data-stu-id="81100-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>

>- [<span data-ttu-id="81100-169">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="81100-169">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="81100-170">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="81100-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="81100-171">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="81100-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="81100-172">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="81100-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="81100-173">Szenario 1: Erstellen einer Richtlinie aus einer Vorlage, nur überwachen</span><span class="sxs-lookup"><span data-stu-id="81100-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="81100-174">Bei diesen Szenarien ist es erforderlich, dass Sie bereits über Geräte verfügen, die in den Aktivitäten-Explorer eingebunden sind und für die Berichte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="81100-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="81100-175">Wenn Sie noch keine Geräte eingebunden haben, lesen Sie [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="81100-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="81100-176">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="81100-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="81100-177">Wählen Sie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="81100-178">Wählen Sie für dieses Szenario **Datenschutz**, dann **USA – Daten mit personenbezogenen Informationen (PII)** und schließlich **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="81100-179">Setzen Sie das Feld **Status** für alle Orte außer **Geräte** auf "Aus".</span><span class="sxs-lookup"><span data-stu-id="81100-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="81100-180">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-180">Choose **Next**.</span></span>

5. <span data-ttu-id="81100-181">Übernehmen Sie die Standardauswahl **Einstellungen in der Vorlage überprüfen und anpassen** Auswahl, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="81100-182">Übernehmen Sie die standardmäßigen Werte für **Schutzmaßnahmen**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="81100-183">Wählen Sie **Aktivitäten auf Windows-Geräten überwachen oder einschränken** aus, und lassen Sie die Aktionen auf **Nur Überwachung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="81100-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="81100-184">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-184">Choose **Next**.</span></span>

8. <span data-ttu-id="81100-185">Übernehmen Sie den standardmäßigen Wert **Ich möchte sie zuerst testen** und wählen Sie **Richtlinientipps im Testmodus anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="81100-186">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-186">Choose **Next**.</span></span>

9. <span data-ttu-id="81100-187">Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="81100-188">Die neue DLP-Richtlinie wird nun in der Richtlinienliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="81100-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="81100-189">Überprüfen Sie den Aktivitäten-Explorer auf Daten aus den überwachten Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="81100-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="81100-190">Legen Sie den Speicherortfilter für Geräte fest, fügen Sie die Richtlinie hinzu, und filtern Sie anschließend nach dem Richtliniennamen, um festzustellen, welche Auswirkungen diese Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="81100-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="81100-191">Lesen Sie bei Bedarf [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="81100-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="81100-192">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="81100-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="81100-193">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="81100-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="81100-194">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="81100-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="81100-195">Szenario 2: Ändern der bestehenden Richtlinie, Festlegen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="81100-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="81100-196">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="81100-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="81100-197">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA – Daten mit persönlich identifizierbaren Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="81100-198">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="81100-199">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="81100-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="81100-200">Scrollen Sie nach unten zum Abschnitt **Vorfallberichte**, und legen Sie **Benachrichtigung an Administratoren senden, wenn es eine Regelübereinstimmung gibt** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="81100-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="81100-201">Es werden automatisch E-Mail-Benachrichtigungen an den Administrator und alle anderen Personen gesendet, die Sie der Empfängerliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="81100-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="81100-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="81100-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="81100-203">Wählen Sie im Rahmen dieses Szenarios **Benachrichtigung jedes Mal senden, wenn eine Aktivität der Regel entspricht** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="81100-204">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-204">Choose **Save**.</span></span>

8. <span data-ttu-id="81100-205">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="81100-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="81100-206">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="81100-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="81100-207">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="81100-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="81100-208">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="81100-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="81100-209">Szenario 3: Ändern der bestehenden Richtlinie, Blockieren der Aktion mit erlaubter Außerkraftsetzung</span><span class="sxs-lookup"><span data-stu-id="81100-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="81100-210">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="81100-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="81100-211">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA – Daten mit persönlich identifizierbaren Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="81100-212">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="81100-213">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="81100-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="81100-214">Scrollen Sie nach unten zum Abschnitt **Aktivitäten auf Windows-Geräten überwachen oder einschränken**, und legen Sie für jede Aktivität die entsprechende Aktion auf **Blockieren mit Außerkraftsetzung** fest.</span><span class="sxs-lookup"><span data-stu-id="81100-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="81100-215">![Festlegen der Aktion "Blockieren mit Außerkraftsetzung"](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="81100-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="81100-216">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="81100-216">Choose **Save**.</span></span>

7. <span data-ttu-id="81100-217">Wiederholen Sie die Schritte 4-7 für **Große Menge an Inhalten erkannt. USA – persönlich identifizierbare Informationen**.</span><span class="sxs-lookup"><span data-stu-id="81100-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="81100-218">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="81100-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="81100-219">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="81100-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="81100-220">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="81100-220">This should trigger the policy.</span></span>

   <span data-ttu-id="81100-221">Auf dem Clientgerät wird ein Popup wie das folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="81100-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="81100-222">![Benachrichtigung über Außerkraftsetzung von Endpunkt-DLP durch Client](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="81100-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="81100-223">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="81100-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="81100-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81100-224">See also</span></span>

- [<span data-ttu-id="81100-225">Informationen zu Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="81100-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="81100-226">Endpunkt-DLP – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="81100-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="81100-227">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="81100-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="81100-228">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="81100-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="81100-229">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="81100-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="81100-230">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="81100-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="81100-231">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="81100-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="81100-232">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="81100-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="81100-233">Azure Active Directory (AAD) Einbindung</span><span class="sxs-lookup"><span data-stu-id="81100-233">Azure Active Directory (AAD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="81100-234">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="81100-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="81100-235">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="81100-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="81100-236">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="81100-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)