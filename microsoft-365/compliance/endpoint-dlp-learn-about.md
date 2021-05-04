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
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114103"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="dd6d6-104">Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="dd6d6-105">Sie können Microsoft 365-DLP (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um die Aktionen zu überwachen, die an Elementen ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="dd6d6-106">Weitere Informationen zu DLP finden Sie unter [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="dd6d6-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="dd6d6-107">**Verhinderung von Datenverlust am Endpunkt** (Endpunkt-DLP) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von DLP auf sensible Elemente auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="dd6d6-108">Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="dd6d6-109">Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können</span><span class="sxs-lookup"><span data-stu-id="dd6d6-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="dd6d6-110">Mit Microsoft Endpunkt-DLP können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="dd6d6-111">Aktivität</span><span class="sxs-lookup"><span data-stu-id="dd6d6-111">Activity</span></span> |<span data-ttu-id="dd6d6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd6d6-112">Description</span></span>  | <span data-ttu-id="dd6d6-113">Überwachbar/einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="dd6d6-114">In einen Clouddienst hochladen oder über nicht zugelassene Browser zugreifen</span><span class="sxs-lookup"><span data-stu-id="dd6d6-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="dd6d6-115">Erkennt, wenn ein Benutzer versucht, ein Element in eine eingeschränkte Dienstdomäne hochzuladen oder über einen Browser auf ein Element zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="dd6d6-116">Wird ein Browser verwendet, der im DLP als nicht zugelassener Browser aufgeführt ist, wird die Uploadaktivität blockiert, und der Benutzer wird umgeleitet, um Edge Chromium zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="dd6d6-117">Edge Chromium kann dann, basierend auf der DLP-Richtlinienkonfiguration, entweder den Upload erlauben oder blockieren oder auf das Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="dd6d6-118">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-118">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-119">In andere App kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-119">copy to other app</span></span>    |<span data-ttu-id="dd6d6-120">Erkennt, wenn ein Benutzer versucht, Informationen aus einem geschützten Element zu kopieren und in eine andere App, einen Prozess oder ein Element einzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="dd6d6-121">Das Kopieren und Einfügen von Informationen innerhalb derselben App, desselben Prozesses oder desselben Elements wird von dieser Aktivität nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="dd6d6-122">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-122">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-123">Auf USB-Wechseldatenträger kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-123">copy to USB removable media</span></span> |<span data-ttu-id="dd6d6-124">Erkennt, wenn ein Benutzer versucht, ein Element oder Informationen auf einen Wechseldatenträger oder ein USB-Gerät zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="dd6d6-125">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-125">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-126">Auf eine Netzwerkfreigabe kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-126">copy to a network share</span></span>    |<span data-ttu-id="dd6d6-127">Erkennt, wenn ein Benutzer versucht, ein Element auf eine Netzwerkfreigabe oder ein zugeordnetes Netzlaufwerk zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="dd6d6-128">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-128">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-129">Dokument drucken</span><span class="sxs-lookup"><span data-stu-id="dd6d6-129">print a document</span></span>    |<span data-ttu-id="dd6d6-130">Erkennt, wenn ein Benutzer versucht, ein geschütztes Element auf einem lokalen oder Netzwerkdrucker zu drucken.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="dd6d6-131">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="dd6d6-132">In eine Remotesitzung kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-132">copy to a remote session</span></span>|<span data-ttu-id="dd6d6-133">Erkennt, wenn ein Benutzer versucht, ein Element in eine Remote-Desktop-Sitzung zu kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="dd6d6-134">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-134">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-135">Auf ein Bluetooth-Gerät kopieren</span><span class="sxs-lookup"><span data-stu-id="dd6d6-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="dd6d6-136">Erkennt, wenn ein Benutzer versucht, ein Element in eine nicht zugelassene Bluetooth-App zu kopieren (wie in der Liste der nicht zugelassenen Bluetooth-Apps in den Endpunkt DLP-Einstellungen definiert).</span><span class="sxs-lookup"><span data-stu-id="dd6d6-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="dd6d6-137">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-137">auditable and restrictable</span></span>|
|<span data-ttu-id="dd6d6-138">Element erstellen</span><span class="sxs-lookup"><span data-stu-id="dd6d6-138">create an item</span></span>|<span data-ttu-id="dd6d6-139">Erkennt, wenn ein Benutzer ein Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-139">Detects when a user creates an item</span></span>| <span data-ttu-id="dd6d6-140">überwachbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-140">auditable</span></span>|
|<span data-ttu-id="dd6d6-141">Element umbenennen</span><span class="sxs-lookup"><span data-stu-id="dd6d6-141">rename an item</span></span>|<span data-ttu-id="dd6d6-142">Erkennt, wenn ein Benutzer ein Element umbenennt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-142">Detects when a user renames an item</span></span>| <span data-ttu-id="dd6d6-143">überwachbar</span><span class="sxs-lookup"><span data-stu-id="dd6d6-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="dd6d6-144">Überwachte Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-144">Monitored files</span></span>

<span data-ttu-id="dd6d6-145">Endpunkt-DLP unterstützt die Überwachung dieser Dateitypen:</span><span class="sxs-lookup"><span data-stu-id="dd6d6-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="dd6d6-146">Word-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-146">Word files</span></span>
- <span data-ttu-id="dd6d6-147">PowerPoint-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-147">PowerPoint files</span></span>
- <span data-ttu-id="dd6d6-148">Excel-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-148">Excel files</span></span>
- <span data-ttu-id="dd6d6-149">PDF-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-149">PDF files</span></span>
- <span data-ttu-id="dd6d6-150">CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-150">.csv files</span></span>
- <span data-ttu-id="dd6d6-151">TSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-151">.tsv files</span></span>
- <span data-ttu-id="dd6d6-152">TXT-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-152">.txt files</span></span>
- <span data-ttu-id="dd6d6-153">RTF-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-153">.rtf files</span></span>
- <span data-ttu-id="dd6d6-154">C-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-154">.c files</span></span>
- <span data-ttu-id="dd6d6-155">CLASS-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-155">.class files</span></span>
- <span data-ttu-id="dd6d6-156">CPP-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-156">.cpp files</span></span>
- <span data-ttu-id="dd6d6-157">CS-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-157">.cs files</span></span>
- <span data-ttu-id="dd6d6-158">H-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-158">.h files</span></span>
- <span data-ttu-id="dd6d6-159">JAVA-Dateien</span><span class="sxs-lookup"><span data-stu-id="dd6d6-159">.java files</span></span>
 
<span data-ttu-id="dd6d6-160">Standardmäßig überwacht Endpunkt-DLP die Aktivitäten für diese Dateitypen, auch wenn keine Richtlinienübereinstimmung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="dd6d6-161">Wenn Sie nur Daten aus Richtlinienübereinstimmungen überwachen möchten, können Sie **Dateiaktivität für Geräte immer überwachen** in den globalen Endpunkt-DLP-Einstellungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="dd6d6-162">Wenn diese Einstellung aktiviert ist, werden alle Aktivitäten für Word-, PowerPoint-, Excel-, PDF- und CSV-Dateien immer überwacht, auch wenn das Gerät von keiner Richtlinie betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="dd6d6-163">Verhinderung von Datenverlust am Endpunkt (Endpunkt-DLP) überwacht Aktivitäten basierend auf dem MIME-Typ, sodass sie auch dann erfasst werden, wenn die Dateierweiterung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="dd6d6-164">Was ist bei Endpunkt-DLP anders?</span><span class="sxs-lookup"><span data-stu-id="dd6d6-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="dd6d6-165">Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="dd6d6-166">Aktivieren der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="dd6d6-166">Enabling Device management</span></span>

<span data-ttu-id="dd6d6-167">Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365-Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="dd6d6-168">Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-169">![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="dd6d6-170">Onboarding und Offboarding werden über Skripts verarbeitet, die Sie über das Center zur Geräteverwaltung herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="dd6d6-171">Im Center sind benutzerdefinierte Skripts für jede der folgenden Bereitstellungsmethoden verfügbar:</span><span class="sxs-lookup"><span data-stu-id="dd6d6-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="dd6d6-172">lokales Skript (bis zu 10 Computer)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="dd6d6-173">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="dd6d6-173">Group policy</span></span>
- <span data-ttu-id="dd6d6-174">System Center Konfigurationsmanager (Version 1610 oder höher)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="dd6d6-175">Verwaltung mobiler Geräte/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dd6d6-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="dd6d6-176">VDI-Onboarding-Skripts für nicht persistente Computer</span><span class="sxs-lookup"><span data-stu-id="dd6d6-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-177">![Seite für das Onboarding eines Geräts](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="dd6d6-178">Wenden Sie für das Geräte-Onboarding die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP-](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="dd6d6-179">Wenn das Onboarding eines Geräts über [Microsoft Defender für Endpunkt](/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-180">![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="dd6d6-181">Anzeigen von Endpunkt-DLP-Daten</span><span class="sxs-lookup"><span data-stu-id="dd6d6-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="dd6d6-182">Sie können Benachrichtigungen anzeigen, die mit auf Endpunktgeräten durchgesetzten DLP-Richtlinien verbunden sind, indem Sie zum [Verwaltungsdasboard „DLP-Benachrichtigungen“](dlp-configure-view-alerts-policies.md) wechseln.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-183">![Warninformationen](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="dd6d6-184">Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-185">![Ereignisinformationen](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="dd6d6-186">Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-187">![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="dd6d6-188">Endpunkt-DLP erfasst umfassende Informationen zu überwachten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="dd6d6-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="dd6d6-189">Wenn eine Datei beispielsweise auf einen USB-Wechseldatenträger kopiert wird, werden die folgenden Attribute in den Aktivitätsdetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd6d6-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="dd6d6-190">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="dd6d6-190">activity type</span></span>
- <span data-ttu-id="dd6d6-191">Client-IP</span><span class="sxs-lookup"><span data-stu-id="dd6d6-191">client IP</span></span>
- <span data-ttu-id="dd6d6-192">Zieldateipfad</span><span class="sxs-lookup"><span data-stu-id="dd6d6-192">target file path</span></span>
- <span data-ttu-id="dd6d6-193">Ereignis-Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="dd6d6-193">happened timestamp</span></span>
- <span data-ttu-id="dd6d6-194">Dateiname</span><span class="sxs-lookup"><span data-stu-id="dd6d6-194">file name</span></span>
- <span data-ttu-id="dd6d6-195">Benutzer</span><span class="sxs-lookup"><span data-stu-id="dd6d6-195">user</span></span>
- <span data-ttu-id="dd6d6-196">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="dd6d6-196">file extension</span></span>
- <span data-ttu-id="dd6d6-197">Dateigröße</span><span class="sxs-lookup"><span data-stu-id="dd6d6-197">file size</span></span>
- <span data-ttu-id="dd6d6-198">Typ vertraulicher Information (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="dd6d6-199">SHA1-Wert</span><span class="sxs-lookup"><span data-stu-id="dd6d6-199">sha1 value</span></span>
- <span data-ttu-id="dd6d6-200">SHA256-Wert</span><span class="sxs-lookup"><span data-stu-id="dd6d6-200">sha256 value</span></span>
- <span data-ttu-id="dd6d6-201">Vorheriger Dateiname</span><span class="sxs-lookup"><span data-stu-id="dd6d6-201">previous file name</span></span>
- <span data-ttu-id="dd6d6-202">Speicherort</span><span class="sxs-lookup"><span data-stu-id="dd6d6-202">location</span></span>
- <span data-ttu-id="dd6d6-203">übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="dd6d6-203">parent</span></span>
- <span data-ttu-id="dd6d6-204">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="dd6d6-204">filepath</span></span>
- <span data-ttu-id="dd6d6-205">Art des Quellspeicherorts</span><span class="sxs-lookup"><span data-stu-id="dd6d6-205">source location type</span></span>
- <span data-ttu-id="dd6d6-206">Plattform</span><span class="sxs-lookup"><span data-stu-id="dd6d6-206">platform</span></span>
- <span data-ttu-id="dd6d6-207">Gerätename</span><span class="sxs-lookup"><span data-stu-id="dd6d6-207">device name</span></span>
- <span data-ttu-id="dd6d6-208">Art des Zielspeicherorts</span><span class="sxs-lookup"><span data-stu-id="dd6d6-208">destination location type</span></span>
- <span data-ttu-id="dd6d6-209">Anwendung, über die die Kopie erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="dd6d6-209">application that performed the copy</span></span>
- <span data-ttu-id="dd6d6-210">Microsoft Defender für Endpunkt-Geräte-ID (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="dd6d6-211">Hersteller des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="dd6d6-211">removable media device manufacturer</span></span>
- <span data-ttu-id="dd6d6-212">Modell des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="dd6d6-212">removable media device model</span></span>
- <span data-ttu-id="dd6d6-213">Seriennummer des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="dd6d6-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6d6-214">![Attribute der Aktivität auf USB kopieren](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="dd6d6-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd6d6-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd6d6-215">Next steps</span></span>

<span data-ttu-id="dd6d6-216">Jetzt, da Sie die Basics zu Endpunkt-DLP kennen, sind die nächsten Schritte folgende:</span><span class="sxs-lookup"><span data-stu-id="dd6d6-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="dd6d6-217">Erste Schritte mit Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="dd6d6-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="dd6d6-218">Nutzung von Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="dd6d6-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="dd6d6-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd6d6-219">See also</span></span>

- [<span data-ttu-id="dd6d6-220">Erste Schritte mit Microsoft Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="dd6d6-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="dd6d6-221">Nutzung von Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="dd6d6-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="dd6d6-222">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="dd6d6-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="dd6d6-223">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="dd6d6-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dd6d6-224">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="dd6d6-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dd6d6-225">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dd6d6-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="dd6d6-226">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="dd6d6-226">Insider Risk management</span></span>](insider-risk-management.md)