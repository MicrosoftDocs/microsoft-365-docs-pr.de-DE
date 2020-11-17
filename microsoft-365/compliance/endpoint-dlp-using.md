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
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073104"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="7fbde-103">Nutzen der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7fbde-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="7fbde-104">In diesem Artikel werden drei Szenarien beschrieben, in denen Sie eine DLP-Richtlinie erstellen und ändern, die Geräte als Speicherort verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fbde-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="7fbde-105">DLP-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7fbde-105">DLP settings</span></span>

<span data-ttu-id="7fbde-p101">Bevor Sie beginnen, sollten Sie die DLP-Einstellungen festlegen, die auf alle DLP-Richtlinien für Geräte angewendet werden. Diese müssen konfiguriert werden, wenn Sie beabsichtigen, Richtlinien zu erstellen, die Folgendes erzwingen:</span><span class="sxs-lookup"><span data-stu-id="7fbde-p101">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices. You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="7fbde-108">Einschränkungen des Cloud-Ausgangs</span><span class="sxs-lookup"><span data-stu-id="7fbde-108">cloud egress restrictions</span></span>
- <span data-ttu-id="7fbde-109">Beschränkungen für nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="7fbde-109">unallowed apps restrictions</span></span>

<span data-ttu-id="7fbde-110">Oder</span><span class="sxs-lookup"><span data-stu-id="7fbde-110">Or</span></span>

- <span data-ttu-id="7fbde-111">Wenn Sie „verrauschte“ Dateipfade von der Überwachung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="7fbde-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="7fbde-112">![DLP-Einstellungen](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="7fbde-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="7fbde-113">Ausschluss von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="7fbde-113">File path exclusions</span></span>

<span data-ttu-id="7fbde-p102">Möglicherweise möchten Sie bestimmte Pfade von der DLP-Überwachung, -Benachrichtigung und -Richtlinienerzwingung auf Ihren Geräten ausschließen, weil sie zu "verrauscht" sind oder keine Dateien enthalten, die Sie interessieren. Dateien an diesen Speicherorten werden nicht überwacht, und solche, die an diesen Speicherorten erstellt oder geändert werden, unterliegen nicht der DLP-Richtlinienerzwingung. Pfadausschlüsse können in den DLP-Einstellungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p102">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in. Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement. You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="7fbde-117">Sie können zum Erstellen Ihrer Pfadausschlüsse die folgende Logik verwenden:</span><span class="sxs-lookup"><span data-stu-id="7fbde-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="7fbde-118">Gültiger Dateipfad, der mit "\" endet, was für Dateien nur unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="7fbde-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="7fbde-119">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="7fbde-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="7fbde-120">Gültiger Dateipfad, der mit "\*" endet, was für Dateien nur in Unterordnern zusätzlich zu den Dateien unmittelbar in dem Ordner steht.</span><span class="sxs-lookup"><span data-stu-id="7fbde-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="7fbde-121">Beispiel: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="7fbde-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="7fbde-122">Gültiger Dateipfad, der ohne "\" oder "\*" endet, was alle Dateien unmittelbar in dem Ordner und allen Unterordnern bedeutet.</span><span class="sxs-lookup"><span data-stu-id="7fbde-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="7fbde-123">Beispiel: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="7fbde-123">For example: C:\Temp</span></span>

- <span data-ttu-id="7fbde-124">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite.</span><span class="sxs-lookup"><span data-stu-id="7fbde-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="7fbde-125">Beispiel: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="7fbde-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="7fbde-126">Ein Pfad mit Platzhalter zwischen "\" von jeder Seite und mit "(number)", um die genaue Anzahl von Unterordnern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7fbde-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="7fbde-127">Beispiel: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="7fbde-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="7fbde-128">Ein Pfad mit SYSTEM-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="7fbde-129">Beispiel: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="7fbde-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="7fbde-130">Eine Kombination aus allen vorstehenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-130">A mix of all the above.</span></span> <br/><span data-ttu-id="7fbde-131">Beispiel: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="7fbde-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="7fbde-132">Dienstdomänen</span><span class="sxs-lookup"><span data-stu-id="7fbde-132">Service domains</span></span>

<span data-ttu-id="7fbde-133">Sie können dieser Liste Domänen hinzufügen, auf die Edge Chromium beim Durchsetzen der in einer Endpunkt-DLP-Richtlinie festgelegten Einschränkung des Cloud-Uploadzugriffs zurückgreifen wird.</span><span class="sxs-lookup"><span data-stu-id="7fbde-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="7fbde-p103">Wenn der Listenmodus auf **Blockieren** festgelegt ist, können Benutzer keine vertraulichen Elemente in diese Domänen hochladen. Wenn eine Upload-Aktion blockiert wird, weil ein Element von einer DLP-Richtlinie betroffen ist, generiert DLP entweder eine Warnung oder blockiert den Upload des vertraulichen Elements.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p103">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains. When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="7fbde-136">Wenn der Listenmodus auf **Zulassen** festgelegt ist, können Benutzer vertrauliche Elemente \**_nur_* _ in diese Domänen hochladen, während der Upload-Zugriff auf alle anderen Domänen nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="7fbde-136">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="7fbde-137">Nicht zulässige Apps</span><span class="sxs-lookup"><span data-stu-id="7fbde-137">Unallowed apps</span></span>

<span data-ttu-id="7fbde-p104">Wenn die Einstellung _ *Zugriff durch nicht zulässige Apps und Browser*\* einer Richtlinie aktiviert ist und Benutzer versuchen, solche Apps für den Zugriff auf eine geschützte Datei zu verwenden, wird die Aktivität zugelassen, blockiert, oder blockiert mit der Möglichkeit für Benutzer, die Einschränkung außer Kraft zu setzen. Alle Aktivitäten werden überwacht und können im Aktivitäten-Explorer überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p104">When a policy's _ *Access by unallowed apps and browsers*\* setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction. All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="7fbde-140">Nicht zulässige Browser</span><span class="sxs-lookup"><span data-stu-id="7fbde-140">Unallowed browsers</span></span>

<span data-ttu-id="7fbde-p105">Sie können Browser hinzufügen, die anhand ihrer ausführbaren Namen identifiziert werden und am Zugriff auf Dateien gehindert werden, die den Bedingungen einer erzwungenen DLP-Richtlinie entsprechen, bei denen die Einschränkung von Clouddienst-Uploads auf „Blockieren“ oder „Blockieren/außer Kraft setzen“ festgelegt ist. Wenn diese Browser am Zugriff auf eine Datei gehindert werden, wird den Endbenutzern eine Popupbenachrichtigung angezeigt, in der sie aufgefordert werden, die Datei über Edge Chromium zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p105">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override. When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

[!IMPORTANT]
<span data-ttu-id="7fbde-143">Es wird nicht der Pfad zu der ausführbaren Datei angegeben, sondern nur der ausführbare Name (z. B. browser.exe).</span><span class="sxs-lookup"><span data-stu-id="7fbde-143">Do not include the path to the executable, but only the executable name (i.e., browser.exe).</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="7fbde-144">DLP-Einstellungen kombinieren</span><span class="sxs-lookup"><span data-stu-id="7fbde-144">Tying DLP settings together</span></span>

<span data-ttu-id="7fbde-p106">Mithilfe von Endpunkt-DLP und des Edge Chromium-Webbrowsers können Sie die unbeabsichtigte Freigabe von vertraulichen Elementen für unautorisierte Cloud-Apps und -Dienste einschränken. Edge Chromium erkennt, wenn für ein Element eine Einschränkung aufgrund einer Endpunkt-DLP-Richtlinie gilt, und erzwingt entsprechende Zugriffsbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p106">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services. Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="7fbde-p107">Bei Verwendung von Endpunkt-DLP als Speicherort in einer entsprechend konfigurierten DLP-Richtlinie und des Edge Chromium-Browsers, werden die nicht zugelassenen Browser, die Sie in diesen Einstellungen definiert haben, am Zugriff auf vertrauliche Elemente gehindert, die Ihren DLP-Richtlinienvorgaben entsprechen. Stattdessen werden Benutzer zur Verwendung von Edge Chromium umgeleitet, und dieser kann DLP-Restriktionen erkennen und Aktivitäten blockieren oder einschränken, wenn die Bedingungen in der DLP-Richtlinie erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p107">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls. Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="7fbde-149">Um diese Einschränkung nutzen zu können, müssen Sie drei wichtige Elemente konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="7fbde-149">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="7fbde-150">Angabe der Speicherorte – Dienste, Domänen und IP-Adressen –, aus denen keine vertraulichen Elemente freigegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-150">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="7fbde-151">Hinzufügen der Browser, die nicht berechtigt sind, auf bestimmte vertrauliche Elemente zuzugreifen, wenn eine DLP-Richtlinienübereinstimmung gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7fbde-151">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="7fbde-152">Konfigurieren von DLP-Richtlinien, um die Arten von vertraulichen Elementen zu definieren, für die Uploads auf diese Orte beschränkt werden sollen, indem Sie **Zu Clouddiensten hochladen** und **Zugriff durch nicht zulässige Browser** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7fbde-152">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="7fbde-153">Sie können weitere neue Dienste, Apps und Richtlinien hinzufügen, um Ihre Beschränkungen zur Erfüllung Ihrer geschäftlichen Anforderungen und zum Schutz vertraulicher Daten auszudehnen und restriktiver zu machen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-153">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="7fbde-154">Diese Konfiguration trägt dazu bei, sicherzustellen, dass Ihre Daten geschützt bleiben, zugleich werden unnötige Beschränkungen vermieden, die Benutzer am Zugriff auf und Freigeben von nicht vertraulichen Elementen hindern oder dies einschränken.</span><span class="sxs-lookup"><span data-stu-id="7fbde-154">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="7fbde-155">Szenarien für Endpunkt-DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="7fbde-155">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="7fbde-p108">Damit Sie sich mit Endpunkt-DLP-Features und deren Wirkungsweise in DLP-Richtlinien vertraut machen können, haben wir einige Szenarien für Sie zur Übung zusammengestellt. Sämtliche Endpunkt-DLP-Inhalte werden in den Haupt-DLP-Inhalt einbezogen, sobald Endpunkt-DLP allgemein verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p108">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow. All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fbde-p109">Diese Endpunkt-DLP-Szenarien stellen nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien dar. In den nachstehend aufgeführten Beiträgen finden Sie Informationen zum Arbeiten mit DLP-Richtlinien in Situationen allgemeiner Art:</span><span class="sxs-lookup"><span data-stu-id="7fbde-p109">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies. Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="7fbde-160">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7fbde-160">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="7fbde-161">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7fbde-161">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="7fbde-162">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="7fbde-162">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="7fbde-163">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7fbde-163">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="7fbde-164">Szenario 1: Erstellen einer Richtlinie aus einer Vorlage, nur überwachen</span><span class="sxs-lookup"><span data-stu-id="7fbde-164">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="7fbde-p110">Bei diesen Szenarien ist es erforderlich, dass Sie bereits über Geräte verfügen, die bereits eingebunden sind und Berichte an den Aktivitäten-Explorer senden. Lesen Sie [Erste Schritte mit Endpunkt-DLP](endpoint-dlp-getting-started.md), falls Sie noch nicht über eingebundene Geräte verfügen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p110">These scenarios require that you already have devices onboarded and reporting into Activity explorer. If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="7fbde-167">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="7fbde-167">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="7fbde-168">Wählen Sie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-168">Choose **Create policy**.</span></span>

3. <span data-ttu-id="7fbde-169">Wählen Sie für dieses Szenario **Datenschutz**, dann **USA: Personenbezogene Informationen (PII)** und schließlich **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-169">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="7fbde-p111">Setzen Sie das Feld **Status** für alle Orte außer **Geräte** auf "Aus". Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p111">Toggle the **Status** field to off for all locations except **Devices**. Choose **Next**.</span></span>

5. <span data-ttu-id="7fbde-172">Übernehmen Sie die Standardauswahl **Einstellungen in der Vorlage überprüfen und anpassen**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-172">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="7fbde-173">Übernehmen Sie die Standardwerte für **Schutzmaßnahmen**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-173">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="7fbde-p112">Wählen Sie **Aktivitäten auf Windows-Geräten überwachen oder einschränken** aus, und lassen Sie die Aktionen auf **Nur Überwachung** festgelegt. Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p112">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**. Choose **Next**.</span></span>

8. <span data-ttu-id="7fbde-p113">Übernehmen Sie den Standardwert **Ich möchte dies zuerst testen** und wählen Sie **Richtlinientipps im Testmodus anzeigen** aus. Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p113">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**. Choose **Next**.</span></span>

9. <span data-ttu-id="7fbde-178">Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Abenden** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-178">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="7fbde-179">Die neue DLP-Richtlinie wird nun in der Richtlinienliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7fbde-179">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="7fbde-p114">Überprüfen Sie den Aktivitäten-Explorer auf Daten aus den überwachten Endpunkten. Legen Sie den Speicherortfilter für Geräte fest, fügen Sie die Richtlinie hinzu, und filtern Sie anschließend nach dem Richtliniennamen, um festzustellen, welche Auswirkungen diese Richtlinie hat. Lesen Sie bei Bedarf [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="7fbde-p114">Check Activity explorer for data from the monitored endpoints. Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy. See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="7fbde-p115">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die die Bedingung "USA: Personenbezogene Informationen (PII)" ausgelöst wird. Dadurch sollte die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p115">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

13. <span data-ttu-id="7fbde-185">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="7fbde-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="7fbde-186">Szenario 2: Ändern der bestehenden Richtlinie, Festlegen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="7fbde-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="7fbde-187">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="7fbde-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="7fbde-188">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA: Personenbezogene Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="7fbde-189">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-189">Choose **edit policy**.</span></span>

4. <span data-ttu-id="7fbde-190">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="7fbde-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="7fbde-p116">Scrollen Sie nach unten zum Abschnitt **Vorfallberichte**, und legen Sie **Benachrichtigung an Administratoren senden, wenn es eine Regelübereinstimmung gibt** auf **Ein** fest. Es werden dann automatisch E-Mail-Benachrichtigungen an den Administrator und alle anderen Personen gesendet, die Sie der Empfängerliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p116">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**. Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fbde-193">![Aktivierung-von-Vorfallsberichten](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="7fbde-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="7fbde-194">Wählen Sie im Rahmen dieses Szenarios **Benachrichtigung jedes Mal senden, wenn eine Aktivität der Regel entspricht** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="7fbde-195">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-195">Choose **Save**.</span></span>

8. <span data-ttu-id="7fbde-196">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="7fbde-p117">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die die Bedingung "USA: Personenbezogene Informationen (PII)" ausgelöst wird. Dadurch sollte die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p117">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

10. <span data-ttu-id="7fbde-199">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="7fbde-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="7fbde-200">Szenario 3: Ändern der bestehenden Richtlinie, Blockieren der Aktion mit erlaubter Außerkraftsetzung</span><span class="sxs-lookup"><span data-stu-id="7fbde-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="7fbde-201">Öffnen Sie die Seite [Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="7fbde-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="7fbde-202">Wählen Sie die in Szenario 1 erstellte Richtlinie **USA: Personenbezogene Informationen (PII)** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="7fbde-203">Wählen Sie **Richtlinie bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-203">Choose **edit policy**.</span></span>

4. <span data-ttu-id="7fbde-204">Wechseln Sie zur Seite **Erweiterte DLP-Regeln**, und bearbeiten Sie **Geringe Menge an Inhalten erkannt. USA: Personenbezogene Informationen**.</span><span class="sxs-lookup"><span data-stu-id="7fbde-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="7fbde-205">Scrollen Sie nach unten zum Abschnitt **Aktivitäten auf Windows-Geräten überwachen oder einschränken**, und legen Sie für jede Aktivität die entsprechende Aktion auf **Blockieren mit Außerkraftsetzung** fest.</span><span class="sxs-lookup"><span data-stu-id="7fbde-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fbde-206">![Festlegen der Aktion "Blockieren mit Außerkraftsetzung"](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="7fbde-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="7fbde-207">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7fbde-207">Choose **Save**.</span></span>

7. <span data-ttu-id="7fbde-208">Wiederholen Sie die Schritte 4-7 für **Große Menge an Inhalten erkannt. USA – persönlich identifizierbare Informationen**.</span><span class="sxs-lookup"><span data-stu-id="7fbde-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="7fbde-209">Speichern Sie alle vorgenommenen Einstellungen, indem Sie **Weiter** und dann **Senden** der Richtlinienänderungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7fbde-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="7fbde-p118">Versuchen Sie, für jemanden außerhalb Ihrer Organisation einen Test mit Inhalten freizugeben, durch die die Bedingung "USA: Personenbezogene Informationen (PII)" ausgelöst wird. Dadurch sollte die Richtlinie ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7fbde-p118">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

   <span data-ttu-id="7fbde-212">Auf dem Clientgerät wird ein Popup wie das folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7fbde-212">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7fbde-213">![Benachrichtigung über Außerkraftsetzung von Endpunkt-DLP durch Client](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="7fbde-213">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="7fbde-214">Überprüfen Sie den Aktivitäten-Explorer auf das Ereignis hin.</span><span class="sxs-lookup"><span data-stu-id="7fbde-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fbde-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fbde-215">See also</span></span>

- [<span data-ttu-id="7fbde-216">Informationen zu Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="7fbde-216">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="7fbde-217">Endpunkt-DLP – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="7fbde-217">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="7fbde-218">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7fbde-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="7fbde-219">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7fbde-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="7fbde-220">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="7fbde-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7fbde-221">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7fbde-221">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="7fbde-222">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="7fbde-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="7fbde-223">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="7fbde-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="7fbde-224">Azure Active Directory (AAD) Einbindung</span><span class="sxs-lookup"><span data-stu-id="7fbde-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="7fbde-225">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7fbde-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="7fbde-226">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7fbde-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="7fbde-227">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="7fbde-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
