---
title: Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: 'Microsoft 365 Endpunkt-DLP erweitert die Überwachung von Dateiaktivitäten sowie schützende Maßnahmen für diese Dateien auf Endpunkte. Die Dateien werden in den Microsoft 365 Compliance-Lösungen angezeigt. '
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279309"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="b1167-104">Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)</span><span class="sxs-lookup"><span data-stu-id="b1167-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="b1167-105">Sie können Microsoft 365-DLP (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um die Aktionen zu überwachen, die an Elementen ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b1167-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="b1167-106">Weitere Informationen zu DLP finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b1167-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="b1167-107">**Verhinderung von Datenverlust am Endpunkt** (Endpunkt-DLP) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von DLP auf sensible Elemente auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="b1167-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="b1167-108">Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b1167-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="b1167-109">Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können</span><span class="sxs-lookup"><span data-stu-id="b1167-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="b1167-110">Mit Microsoft Endpunkt-DLP können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1167-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="b1167-111">Aktivität</span><span class="sxs-lookup"><span data-stu-id="b1167-111">activity</span></span> |<span data-ttu-id="b1167-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1167-112">description</span></span>  | <span data-ttu-id="b1167-113">überwachbar/einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b1167-114">In einen Clouddienst hochladen oder über nicht zugelassene Browser zugreifen</span><span class="sxs-lookup"><span data-stu-id="b1167-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="b1167-115">Erkennt, wenn ein Benutzer versucht, ein Element in eine eingeschränkte Dienstdomäne hochzuladen oder über einen Browser auf ein Element zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b1167-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="b1167-116">Wird ein Browser verwendet, der im DLP als nicht zugelassener Browser aufgeführt ist, wird die Uploadaktivität blockiert, und der Benutzer wird umgeleitet, um Edge Chromium zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1167-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="b1167-117">Edge Chromium kann dann, basierend auf der DLP-Richtlinienkonfiguration, entweder den Upload erlauben oder blockieren oder auf das Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b1167-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="b1167-118">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-118">auditable and restrictable</span></span>|
|<span data-ttu-id="b1167-119">In andere App kopieren</span><span class="sxs-lookup"><span data-stu-id="b1167-119">copy to other app</span></span>    |<span data-ttu-id="b1167-120">Erkennt, wenn ein Benutzer versucht, Informationen aus einem geschützten Element zu kopieren und in eine andere App, einen Prozess oder ein Element einzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1167-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="b1167-121">Das Kopieren und Einfügen von Informationen innerhalb derselben App, desselben Prozesses oder desselben Elements wird von dieser Aktivität nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="b1167-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="b1167-122">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-122">auditable and restrictable</span></span>|
|<span data-ttu-id="b1167-123">Auf USB-Wechseldatenträger kopieren</span><span class="sxs-lookup"><span data-stu-id="b1167-123">copy to USB removable media</span></span> |<span data-ttu-id="b1167-124">Erkennt, wenn ein Benutzer versucht, ein Element oder Informationen auf einen Wechseldatenträger oder ein USB-Gerät zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b1167-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="b1167-125">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-125">auditable and restrictable</span></span>|
|<span data-ttu-id="b1167-126">Auf eine Netzwerkfreigabe kopieren</span><span class="sxs-lookup"><span data-stu-id="b1167-126">copy to a network share</span></span>    |<span data-ttu-id="b1167-127">Erkennt, wenn ein Benutzer versucht, ein Element auf eine Netzwerkfreigabe oder ein zugeordnetes Netzlaufwerk zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b1167-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="b1167-128">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-128">auditable and restrictable</span></span>|
|<span data-ttu-id="b1167-129">Dokument drucken</span><span class="sxs-lookup"><span data-stu-id="b1167-129">print a document</span></span>    |<span data-ttu-id="b1167-130">Erkennt, wenn ein Benutzer versucht, ein geschütztes Element auf einem lokalen oder Netzwerkdrucker zu drucken.</span><span class="sxs-lookup"><span data-stu-id="b1167-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="b1167-131">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="b1167-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="b1167-132">Element erstellen</span><span class="sxs-lookup"><span data-stu-id="b1167-132">create an item</span></span>|<span data-ttu-id="b1167-133">Erkennt, wenn ein Benutzer ein Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="b1167-133">Detects when a user creates an item</span></span>| <span data-ttu-id="b1167-134">überwachbar</span><span class="sxs-lookup"><span data-stu-id="b1167-134">auditable</span></span>|
|<span data-ttu-id="b1167-135">Element umbenennen</span><span class="sxs-lookup"><span data-stu-id="b1167-135">rename an item</span></span>|<span data-ttu-id="b1167-136">Erkennt, wenn ein Benutzer ein Element umbenennt.</span><span class="sxs-lookup"><span data-stu-id="b1167-136">Detects when a user renames an item</span></span>| <span data-ttu-id="b1167-137">überwachbar</span><span class="sxs-lookup"><span data-stu-id="b1167-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="b1167-138">Überwachte Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-138">Monitored files</span></span>

<span data-ttu-id="b1167-139">Endpunkt-DLP unterstützt die Überwachung dieser Dateitypen:</span><span class="sxs-lookup"><span data-stu-id="b1167-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="b1167-140">Word-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-140">Word files</span></span>
- <span data-ttu-id="b1167-141">PowerPoint-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-141">PowerPoint files</span></span>
- <span data-ttu-id="b1167-142">Excel-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-142">Excel files</span></span>
- <span data-ttu-id="b1167-143">PDF-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-143">PDF files</span></span>
- <span data-ttu-id="b1167-144">CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-144">.csv files</span></span>
- <span data-ttu-id="b1167-145">TSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-145">.tsv files</span></span>
- <span data-ttu-id="b1167-146">TXT-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-146">.txt files</span></span>
- <span data-ttu-id="b1167-147">RTF-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-147">.rtf files</span></span>
- <span data-ttu-id="b1167-148">C-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-148">.c files</span></span>
- <span data-ttu-id="b1167-149">CLASS-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-149">.class files</span></span>
- <span data-ttu-id="b1167-150">CPP-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-150">.cpp files</span></span>
- <span data-ttu-id="b1167-151">CS-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-151">.cs files</span></span>
- <span data-ttu-id="b1167-152">H-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-152">.h files</span></span>
- <span data-ttu-id="b1167-153">JAVA-Dateien</span><span class="sxs-lookup"><span data-stu-id="b1167-153">.java files</span></span>
 
<span data-ttu-id="b1167-154">Standardmäßig überwacht Endpunkt-DLP die Aktivitäten für diese Dateitypen, auch wenn keine Richtlinienübereinstimmung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="b1167-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="b1167-155">Wenn Sie nur Daten aus Richtlinienübereinstimmungen überwachen möchten, können Sie **Dateiaktivität für Geräte immer überwachen** in den globalen Endpunkt-DLP-Einstellungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b1167-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="b1167-156">Unabhängig davon werden Aktivitäten für sämtliche Word-, PowerPoint-, Excel-, PDF- und CSV-Dateien immer überwacht.</span><span class="sxs-lookup"><span data-stu-id="b1167-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="b1167-157">Verhinderung von Datenverlust am Endpunkt (Endpunkt-DLP) überwacht Aktivitäten basierend auf dem MIME-Typ, sodass sie auch dann erfasst werden, wenn die Dateierweiterung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1167-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="b1167-158">Was ist bei Endpunkt-DLP anders?</span><span class="sxs-lookup"><span data-stu-id="b1167-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="b1167-159">Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.</span><span class="sxs-lookup"><span data-stu-id="b1167-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="b1167-160">Aktivieren der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="b1167-160">Enabling Device management</span></span>

<span data-ttu-id="b1167-161">Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365-Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt.</span><span class="sxs-lookup"><span data-stu-id="b1167-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="b1167-162">Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.</span><span class="sxs-lookup"><span data-stu-id="b1167-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1167-163">![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="b1167-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="b1167-164">Onboarding und Offboarding werden über Skripts verarbeitet, die Sie über das Center zur Geräteverwaltung herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="b1167-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="b1167-165">Im Center sind benutzerdefinierte Skripts für jede der folgenden Bereitstellungsmethoden verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b1167-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="b1167-166">lokales Skript (bis zu 10 Computer)</span><span class="sxs-lookup"><span data-stu-id="b1167-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="b1167-167">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b1167-167">Group policy</span></span>
- <span data-ttu-id="b1167-168">System Center Konfigurationsmanager (Version 1610 oder höher)</span><span class="sxs-lookup"><span data-stu-id="b1167-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="b1167-169">Verwaltung mobiler Geräte/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b1167-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="b1167-170">VDI-Onboarding-Skripts für nicht persistente Computer</span><span class="sxs-lookup"><span data-stu-id="b1167-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1167-171">![Seite für das Onboarding eines Geräts](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="b1167-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="b1167-172">Wenden Sie für das Geräte-Onboarding die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP-](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.</span><span class="sxs-lookup"><span data-stu-id="b1167-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="b1167-173">Wenn das Onboarding eines Geräts über [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1167-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1167-174">![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="b1167-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="b1167-175">Anzeigen von Endpunkt-DLP-Daten</span><span class="sxs-lookup"><span data-stu-id="b1167-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="b1167-176">Sie können Benachrichtigungen anzeigen, die mit auf Endpunktgeräten durchgesetzten DLP-Richtlinien verbunden sind, indem Sie zum [Verwaltungsdasboard „DLP-Benachrichtigungen“](dlp-configure-view-alerts-policies.md) wechseln.</span><span class="sxs-lookup"><span data-stu-id="b1167-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Warninformationen](../media/Alert-info-1.png)

<span data-ttu-id="b1167-178">Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1167-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![Ereignisinformationen](../media/Event-info-1.png)

<span data-ttu-id="b1167-180">Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1167-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1167-181">![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="b1167-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="b1167-182">Endpunkt-DLP erfasst umfassende Informationen zu überwachten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b1167-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="b1167-183">Wenn eine Datei beispielsweise auf einen USB-Wechseldatenträger kopiert wird, werden die folgenden Attribute in den Aktivitätsdetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b1167-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="b1167-184">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="b1167-184">activity type</span></span>
- <span data-ttu-id="b1167-185">Client-IP</span><span class="sxs-lookup"><span data-stu-id="b1167-185">client IP</span></span>
- <span data-ttu-id="b1167-186">Zieldateipfad</span><span class="sxs-lookup"><span data-stu-id="b1167-186">target file path</span></span>
- <span data-ttu-id="b1167-187">Ereignis-Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="b1167-187">happened timestamp</span></span>
- <span data-ttu-id="b1167-188">Dateiname</span><span class="sxs-lookup"><span data-stu-id="b1167-188">file name</span></span>
- <span data-ttu-id="b1167-189">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b1167-189">user</span></span>
- <span data-ttu-id="b1167-190">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="b1167-190">file extension</span></span>
- <span data-ttu-id="b1167-191">Dateigröße</span><span class="sxs-lookup"><span data-stu-id="b1167-191">file size</span></span>
- <span data-ttu-id="b1167-192">Typ vertraulicher Information (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="b1167-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="b1167-193">SHA1-Wert</span><span class="sxs-lookup"><span data-stu-id="b1167-193">sha1 value</span></span>
- <span data-ttu-id="b1167-194">SHA256-Wert</span><span class="sxs-lookup"><span data-stu-id="b1167-194">sha256 value</span></span>
- <span data-ttu-id="b1167-195">Vorheriger Dateiname</span><span class="sxs-lookup"><span data-stu-id="b1167-195">previous file name</span></span>
- <span data-ttu-id="b1167-196">Speicherort</span><span class="sxs-lookup"><span data-stu-id="b1167-196">location</span></span>
- <span data-ttu-id="b1167-197">übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b1167-197">parent</span></span>
- <span data-ttu-id="b1167-198">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="b1167-198">filepath</span></span>
- <span data-ttu-id="b1167-199">Art des Quellspeicherorts</span><span class="sxs-lookup"><span data-stu-id="b1167-199">source location type</span></span>
- <span data-ttu-id="b1167-200">Plattform</span><span class="sxs-lookup"><span data-stu-id="b1167-200">platform</span></span>
- <span data-ttu-id="b1167-201">Gerätename</span><span class="sxs-lookup"><span data-stu-id="b1167-201">device name</span></span>
- <span data-ttu-id="b1167-202">Art des Zielspeicherorts</span><span class="sxs-lookup"><span data-stu-id="b1167-202">destination location type</span></span>
- <span data-ttu-id="b1167-203">Anwendung, über die die Kopie erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="b1167-203">application that performed the copy</span></span>
- <span data-ttu-id="b1167-204">Microsoft Defender für Endpunkt-Geräte-ID (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="b1167-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="b1167-205">Hersteller des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="b1167-205">removable media device manufacturer</span></span>
- <span data-ttu-id="b1167-206">Modell des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="b1167-206">removable media device model</span></span>
- <span data-ttu-id="b1167-207">Seriennummer des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="b1167-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b1167-208">![Attribute der Aktivität auf USB kopieren](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="b1167-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1167-209">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b1167-209">Next steps</span></span>

<span data-ttu-id="b1167-210">Jetzt, da Sie die Basics zu Endpunkt-DLP kennen, sind die nächsten Schritte folgende:</span><span class="sxs-lookup"><span data-stu-id="b1167-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="b1167-211">Erste Schritte mit Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="b1167-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="b1167-212">Nutzung von Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="b1167-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="b1167-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1167-213">See also</span></span>

- [<span data-ttu-id="b1167-214">Erste Schritte mit Microsoft Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="b1167-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="b1167-215">Nutzung von Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="b1167-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="b1167-216">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1167-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="b1167-217">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="b1167-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b1167-218">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="b1167-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b1167-219">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b1167-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="b1167-220">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="b1167-220">Insider Risk management</span></span>](insider-risk-management.md)
