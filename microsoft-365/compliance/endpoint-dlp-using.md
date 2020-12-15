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
ms.openlocfilehash: 531fd5506aeb255e261c3cce35473f1ddad2aa42
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667810"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="e0897-103">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e0897-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="e0897-104">In diesem Artikel werden drei Szenarien beschrieben, in denen Sie eine DLP-Richtlinie erstellen und ändern, die Geräte als Speicherort verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0897-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="e0897-105">DLP-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e0897-105">DLP settings</span></span>

<span data-ttu-id="e0897-106">Bevor Sie beginnen, sollten Sie die DLP-Einstellungen festlegen, die auf alle DLP-Richtlinien für Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="e0897-107">Diese müssen konfiguriert werden, wenn Sie beabsichtigen, Richtlinien zu erstellen, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="e0897-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="e0897-108">Einschränkungen des Cloud-Ausgangs</span><span class="sxs-lookup"><span data-stu-id="e0897-108">cloud egress restrictions</span></span>
- <span data-ttu-id="e0897-109">Beschränkungen für nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="e0897-109">unallowed apps restrictions</span></span>

<span data-ttu-id="e0897-110">Oder</span><span class="sxs-lookup"><span data-stu-id="e0897-110">Or</span></span>

- <span data-ttu-id="e0897-111">Wenn Sie „verrauschte“ Dateipfade von der Überwachung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="e0897-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e0897-112">![DLP-Einstellungen](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="e0897-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="e0897-113">Ausschluss von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="e0897-113">File path exclusions</span></span>

<span data-ttu-id="e0897-114">Es empfiehlt sich, bestimmte Pfade von der DLP-Überwachung, -Benachrichtigung und -Richtlinienerzwingung auf Ihren Geräten auszuschließen, wenn sie zu verrauscht sind oder keine Dateien enthalten, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="e0897-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="e0897-115">Dateien an diesen Speicherorten werden nicht überwacht, und solche, die an diesen Speicherorten erstellt oder geändert werden, unterliegen nicht der DLP-Richtlinienerzwingung.</span><span class="sxs-lookup"><span data-stu-id="e0897-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="e0897-116">In den DLP-Einstellungen können Sie Pfadausschlüsse konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e0897-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="e0897-117">Sie können diese Logik verwenden, um Ihre Pfadausschlüsse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e0897-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="e0897-118">Gültiger Dateipfad, der mit "\" endet, was für Dateien nur unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="e0897-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="e0897-119">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="e0897-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="e0897-120">Gültiger Dateipfad, der mit "\*" endet, was für Dateien nur in Unterordnern zusätzlich zu den Dateien unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="e0897-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="e0897-121">Beispiel: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="e0897-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="e0897-122">Gültiger Dateipfad, der ohne "\" oder "\*" endet, was alle Dateien unmittelbar in dem Ordner und allen Unterordnern bedeutet.</span><span class="sxs-lookup"><span data-stu-id="e0897-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="e0897-123">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="e0897-123">For example: C:\Temp</span></span>

- <span data-ttu-id="e0897-124">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite.</span><span class="sxs-lookup"><span data-stu-id="e0897-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="e0897-125">Beispiel: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="e0897-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="e0897-126">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite und mit "(number)", um die genaue Anzahl von Unterordnern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0897-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="e0897-127">Beispiel: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="e0897-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="e0897-128">Ein Pfad mit SYSTEM-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="e0897-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="e0897-129">Beispiel: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="e0897-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="e0897-130">Eine Kombination aus allen vorstehenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="e0897-130">A mix of all the above.</span></span> <br/><span data-ttu-id="e0897-131">Beispiel: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="e0897-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="e0897-132">Nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="e0897-132">Unallowed apps</span></span>

<span data-ttu-id="e0897-133">Wenn die Einstellung **Zugriff durch nicht zulässige Apps und Browser** einer Richtlinie aktiviert ist und Benutzer versuchen, solche Apps für den Zugriff auf eine geschützte Datei zu verwenden, wird die Aktivität zugelassen, blockiert oder blockiert, aber die Benutzer können die Einschränkung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="e0897-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="e0897-134">Alle Aktivitäten werden überwacht und können im Aktivitäten-Explorer überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0897-135">Es wird nicht der Pfad zu der ausführbaren Datei angegeben, sondern nur der ausführbare Name (z. B. „browser.exe“).</span><span class="sxs-lookup"><span data-stu-id="e0897-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="e0897-136">Browser- und Domäneneinschränkungen:</span><span class="sxs-lookup"><span data-stu-id="e0897-136">Browser and domain restrictions</span></span>
<span data-ttu-id="e0897-137">Schränken Sie die Freigabe sensibler Dateien, die Ihren Richtlinien entsprechen, für uneingeschränkte Clouddienstdomänen ein.</span><span class="sxs-lookup"><span data-stu-id="e0897-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="e0897-138">Dienstdomänen</span><span class="sxs-lookup"><span data-stu-id="e0897-138">Service domains</span></span>

<span data-ttu-id="e0897-139">Sie können steuern, ob sensible Dateien, die durch Ihre Richtlinien geschützt sind, von Microsoft Edge aus in bestimmte Dienstdomänen hochgeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="e0897-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="e0897-140">Wenn der Listenmodus auf **Blockieren** festgelegt ist, können Benutzer keine vertraulichen Elemente in diese Domänen hochladen.</span><span class="sxs-lookup"><span data-stu-id="e0897-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="e0897-141">Wenn eine Upload-Aktion blockiert wird, weil ein Element von einer DLP-Richtlinie betroffen ist, generiert DLP entweder eine Warnung oder sperrt den Upload des vertraulichen Elements.</span><span class="sxs-lookup"><span data-stu-id="e0897-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="e0897-142">Wenn der Listenmodus auf **Zulassen** festgelegt ist, können Benutzer vertrauliche Elemente \**_nur_* _ in diese Domänen hochladen, während der Uploadzugriff auf alle anderen Domänen nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e0897-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="e0897-143">Nicht zulässige Browser</span><span class="sxs-lookup"><span data-stu-id="e0897-143">Unallowed browsers</span></span>

<span data-ttu-id="e0897-144">Sie können Browser hinzufügen, die anhand ihrer ausführbaren Namen identifiziert werden und am Zugriff auf Dateien gehindert werden, die den Bedingungen einer erzwungenen DLP-Richtlinie entsprechen, bei denen die Einschränkung von Clouddienst-Uploads auf „Blockieren“ oder „Blockieren/außer Kraft setzen“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e0897-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="e0897-145">Wenn diese Browser am Zugriff auf eine Datei gehindert werden, wird den Endbenutzern eine Popupbenachrichtigung angezeigt, in der sie aufgefordert werden, die Datei über Edge Chromium zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e0897-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="e0897-146">DLP-Einstellungen kombinieren</span><span class="sxs-lookup"><span data-stu-id="e0897-146">Tying DLP settings together</span></span>

<span data-ttu-id="e0897-147">Mithilfe von Endpunkt-DLP und des Edge Chromium-Webbrowsers können Sie die unbeabsichtigte Freigabe von vertraulichen Elementen für nicht zulässige Cloud-Apps und -Dienste einschränken.</span><span class="sxs-lookup"><span data-stu-id="e0897-147">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="e0897-148">Edge Chromium erkennt, wenn für ein Element eine Einschränkung aufgrund einer Endpunkt-DLP-Richtlinie gilt, und erzwingt entsprechende Zugriffsbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e0897-148">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="e0897-149">Bei Verwendung von Endpunkt-DLP als Speicherort in einer entsprechend konfigurierten DLP-Richtlinie und des Edge Chromium-Browsers, werden die nicht zugelassenen Browser, die Sie in diesen Einstellungen definiert haben, am Zugriff auf vertrauliche Elemente gehindert, die Ihren DLP-Richtlinienvorgaben entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0897-149">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="e0897-150">Stattdessen werden Benutzer zur Verwendung von Edge Chromium umgeleitet, und dieser kann aufgrund von DLP-Restriktionen Aktivitäten blockieren oder einschränken, wenn die Bedingungen in der DLP-Richtlinie erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="e0897-150">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="e0897-151">Um diese Einschränkung nutzen zu können, müssen Sie drei wichtige Elemente konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e0897-151">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="e0897-152">Angabe der Speicherorte – Dienste, Domänen und IP-Adressen –, aus denen keine vertraulichen Elemente freigegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0897-152">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="e0897-153">Hinzufügen der Browser, die nicht berechtigt sind, auf bestimmte vertrauliche Elemente zuzugreifen, wenn eine DLP-Richtlinienübereinstimmung gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e0897-153">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="e0897-154">Konfigurieren von DLP-Richtlinien, um die Arten von vertraulichen Elementen zu definieren, für die Uploads auf diese Orte beschränkt werden sollen, indem Sie _ *Zu Clouddiensten hochladen*\* und **Zugriff durch nicht zulässige Browser** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e0897-154">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on _ *Upload to cloud services*\* and **Access from unallowed browser**.</span></span>

<span data-ttu-id="e0897-155">Sie können weitere neue Dienste, Apps und Richtlinien hinzufügen, um Ihre Beschränkungen zur Erfüllung Ihrer geschäftlichen Anforderungen und zum Schutz vertraulicher Daten auszudehnen und restriktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="e0897-155">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="e0897-156">Diese Konfiguration trägt dazu bei, sicherzustellen, dass Ihre Daten geschützt bleiben, zugleich werden unnötige Beschränkungen vermieden, die Benutzer am Zugriff auf und Freigeben von nicht vertraulichen Elementen hindern oder dies einschränken.</span><span class="sxs-lookup"><span data-stu-id="e0897-156">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="e0897-157">Szenarien für Endpunkt-DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e0897-157">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="e0897-158">Damit Sie sich mit Endpunkt-DLP-Features und deren Wirkungsweise in DLP-Richtlinien vertraut machen können, haben wir einige Szenarien für Sie zur Übung zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="e0897-158">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="e0897-159">Sämtliche Endpunkt-DLP-Inhalte werden in den Haupt-DLP-Inhalt einbezogen, sobald Endpunkt-DLP allgemein verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="e0897-159">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0897-160">Diese Endpunkt-DLP-Szenarien stellen nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien dar.</span><span class="sxs-lookup"><span data-stu-id="e0897-160">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="e0897-161">In den folgenden Beiträgen finden Sie Informationen zum Arbeiten mit DLP-Richtlinien in Situationen allgemeiner Art:</span><span class="sxs-lookup"><span data-stu-id="e0897-161">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="e0897-162">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e0897-162">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="e0897-163">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e0897-163">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="e0897-164">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="e0897-164">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="e0897-165">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e0897-165">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="e0897-166">Szenario 1: Erstellen einer Richtlinie aus einer Vorlage, nur überwachen</span><span class="sxs-lookup"><span data-stu-id="e0897-166">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="e0897-167">Bei diesen Szenarien ist es erforderlich, dass Sie bereits über Geräte verfügen, die in den Aktivitäten-Explorer eingebunden sind und für die Berichte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-167">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="e0897-168">Wenn Sie noch keine Geräte eingebunden haben, lesen Sie [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="e0897-168">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="e0897-169">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="e0897-169">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e0897-170">Wählen Sie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-170">Choose **Create policy**.</span></span>

3. <span data-ttu-id="e0897-171">Wählen Sie für dieses Szenario **Datenschutz**, dann **USA – Daten mit personenbezogenen Informationen (PII)** und schließlich **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-171">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="e0897-172">Setzen Sie das Feld **Status** für alle Orte außer **Geräte** auf "Aus".</span><span class="sxs-lookup"><span data-stu-id="e0897-172">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="e0897-173">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-173">Choose **Next**.</span></span>

5. <span data-ttu-id="e0897-174">Übernehmen Sie die Standardauswahl **Einstellungen in der Vorlage überprüfen und anpassen** Auswahl, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-174">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="e0897-175">Übernehmen Sie die standardmäßigen Werte für **Schutzmaßnahmen**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-175">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="e0897-176">Wählen Sie **Aktivitäten auf Windows-Geräten überwachen oder einschränken** aus, und lassen Sie die Aktionen auf **Nur Überwachung** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e0897-176">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="e0897-177">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-177">Choose **Next**.</span></span>

8. <span data-ttu-id="e0897-178">Übernehmen Sie den standardmäßigen Wert **Ich möchte sie zuerst testen** und wählen Sie **Richtlinientipps im Testmodus anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-178">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="e0897-179">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-179">Choose **Next**.</span></span>

9. <span data-ttu-id="e0897-180">Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-180">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="e0897-181">Die neue DLP-Richtlinie wird nun in der Richtlinienliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0897-181">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="e0897-182">Überprüfen Sie den Aktivitäten-Explorer auf Daten aus den überwachten Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="e0897-182">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="e0897-183">Legen Sie den Speicherortfilter für Geräte fest, fügen Sie die Richtlinie hinzu, und filtern Sie anschließend nach dem Richtliniennamen, um festzustellen, welche Auswirkungen diese Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="e0897-183">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="e0897-184">Lesen Sie bei Bedarf [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="e0897-184">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="e0897-185">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e0897-185">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e0897-186">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-186">This should trigger the policy.</span></span>

13. <span data-ttu-id="e0897-187">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="e0897-187">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="e0897-188">Szenario 2: Ändern der bestehenden Richtlinie, Festlegen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="e0897-188">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="e0897-189">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="e0897-189">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e0897-190">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA – Daten mit persönlich identifizierbaren Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-190">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="e0897-191">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-191">Choose **edit policy**.</span></span>

4. <span data-ttu-id="e0897-192">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="e0897-192">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="e0897-193">Scrollen Sie nach unten zum Abschnitt **Vorfallberichte**, und legen Sie **Benachrichtigung an Administratoren senden, wenn es eine Regelübereinstimmung gibt** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="e0897-193">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="e0897-194">Es werden automatisch E-Mail-Benachrichtigungen an den Administrator und alle anderen Personen gesendet, die Sie der Empfängerliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e0897-194">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0897-195">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="e0897-195">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="e0897-196">Wählen Sie im Rahmen dieses Szenarios **Benachrichtigung jedes Mal senden, wenn eine Aktivität der Regel entspricht** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-196">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="e0897-197">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-197">Choose **Save**.</span></span>

8. <span data-ttu-id="e0897-198">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="e0897-198">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="e0897-199">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e0897-199">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e0897-200">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-200">This should trigger the policy.</span></span>

10. <span data-ttu-id="e0897-201">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="e0897-201">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="e0897-202">Szenario 3: Ändern der bestehenden Richtlinie, Blockieren der Aktion mit erlaubter Außerkraftsetzung</span><span class="sxs-lookup"><span data-stu-id="e0897-202">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="e0897-203">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="e0897-203">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e0897-204">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA – Daten mit persönlich identifizierbaren Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-204">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="e0897-205">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-205">Choose **edit policy**.</span></span>

4. <span data-ttu-id="e0897-206">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="e0897-206">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="e0897-207">Scrollen Sie nach unten zum Abschnitt **Aktivitäten auf Windows-Geräten überwachen oder einschränken**, und legen Sie für jede Aktivität die entsprechende Aktion auf **Blockieren mit Außerkraftsetzung** fest.</span><span class="sxs-lookup"><span data-stu-id="e0897-207">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0897-208">![Festlegen der Aktion "Blockieren mit Außerkraftsetzung"](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="e0897-208">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="e0897-209">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e0897-209">Choose **Save**.</span></span>

7. <span data-ttu-id="e0897-210">Wiederholen Sie die Schritte 4-7 für **Große Menge an Inhalten erkannt. USA – persönlich identifizierbare Informationen**.</span><span class="sxs-lookup"><span data-stu-id="e0897-210">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="e0897-211">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="e0897-211">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="e0897-212">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die Bedingung "USA – Daten mit persönlich identifizierbaren Informationen (PII)" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e0897-212">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e0897-213">Hierdurch müsste die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e0897-213">This should trigger the policy.</span></span>

   <span data-ttu-id="e0897-214">Auf dem Clientgerät wird ein Popup wie das folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e0897-214">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0897-215">![Benachrichtigung über Außerkraftsetzung von Endpunkt-DLP durch Client](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="e0897-215">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="e0897-216">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="e0897-216">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0897-217">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0897-217">See also</span></span>

- [<span data-ttu-id="e0897-218">Informationen zu Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="e0897-218">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e0897-219">Endpunkt-DLP – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="e0897-219">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="e0897-220">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e0897-220">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e0897-221">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e0897-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e0897-222">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="e0897-222">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e0897-223">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e0897-223">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="e0897-224">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="e0897-224">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="e0897-225">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="e0897-225">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="e0897-226">Azure Active Directory (AAD) Einbindung</span><span class="sxs-lookup"><span data-stu-id="e0897-226">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="e0897-227">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e0897-227">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="e0897-228">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e0897-228">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="e0897-229">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="e0897-229">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
