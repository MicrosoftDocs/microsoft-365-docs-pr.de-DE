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
description: 'Microsoft 365 Endpunkt-DLP erweitert die Überwachung von Dateiaktivitäten und Schutzmaßnahmen für diese Dateien auf Endpunkte. Dateien werden in den Microsoft 365 Compliance-Lösungen sichtbar gemacht. '
ms.openlocfilehash: 0f69261cb5617c7d6de7900b85a5a254a04bc45e
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999474"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="c9c09-104">Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)</span><span class="sxs-lookup"><span data-stu-id="c9c09-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="c9c09-p102">Sie können Microsoft 365 Data Loss Prevention (DLP) verwenden, um Ihre Maßnahmen für vertrauliche Objekte zu überwachen und um die unbeabsichtigte gemeinsame Nutzung dieser Objekte zu verhindern. Mehr Informationen zu DLP finden Sie unter [Überblick über DLP](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c9c09-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="c9c09-p103">**Verhinderung von Datenverlust** (Endpunkt-DLP) erweitert die Aktivitätsüberwachungs- und Schutzfunktionen von DLP auf vertrauliche Objekte, die sich auf Windows 10-Geräten befinden. Sobald die Geräte in die Microsoft 365 Compliance-Lösungen integriert sind, werden die Informationen darüber, was Benutzer mit vertraulichen Objekten tun, im [Aktivitäts-Explorer](data-classification-activity-explorer.md) sichtbar. Sie können Schutzmaßnahmen für diese Objekte über [DLP-Richtlinien](create-test-tune-dlp-policy.md) durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="c9c09-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="c9c09-109">Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können</span><span class="sxs-lookup"><span data-stu-id="c9c09-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="c9c09-p104">Mit Microsoft Endpunkt-DLP können Sie folgende Arten von Aktivitäten prüfen und verwalten, die Benutzer auf Windows 10-Geräten ausführen. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="c9c09-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="c9c09-112">Aktivität am Element</span><span class="sxs-lookup"><span data-stu-id="c9c09-112">activity on item</span></span> |<span data-ttu-id="c9c09-113">überwachbar/einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="c9c09-114">erstellt</span><span class="sxs-lookup"><span data-stu-id="c9c09-114">created</span></span>    | <span data-ttu-id="c9c09-115">überwachbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-115">auditable</span></span>      |
|<span data-ttu-id="c9c09-116">umbenannt</span><span class="sxs-lookup"><span data-stu-id="c9c09-116">renamed</span></span>    |  <span data-ttu-id="c9c09-117">überwachbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-117">auditable</span></span>       |
|<span data-ttu-id="c9c09-118">auf Wechselmedium kopiert oder erstellt</span><span class="sxs-lookup"><span data-stu-id="c9c09-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="c9c09-119">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-119">auditable and restrictable</span></span>|
|<span data-ttu-id="c9c09-120">in Netzwerkfreigabe kopiert, z. B. \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="c9c09-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="c9c09-121">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="c9c09-122">gedruckt</span><span class="sxs-lookup"><span data-stu-id="c9c09-122">printed</span></span> |    <span data-ttu-id="c9c09-123">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="c9c09-124">über Chromium Edge in die Cloud kopiert</span><span class="sxs-lookup"><span data-stu-id="c9c09-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="c9c09-125">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="c9c09-126">Zugriff über nicht zulässige Apps und Browser</span><span class="sxs-lookup"><span data-stu-id="c9c09-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="c9c09-127">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="c9c09-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="c9c09-128">Was ist bei Endpunkt-DLP anders?</span><span class="sxs-lookup"><span data-stu-id="c9c09-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="c9c09-129">Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.</span><span class="sxs-lookup"><span data-stu-id="c9c09-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="c9c09-130">Geräteverwaltung aktivieren</span><span class="sxs-lookup"><span data-stu-id="c9c09-130">Enabling Device management</span></span>

<span data-ttu-id="c9c09-p105">Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365 Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt. Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.</span><span class="sxs-lookup"><span data-stu-id="c9c09-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9c09-133">![Geräteverwaltung aktivieren](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="c9c09-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="c9c09-p106">Onboarding und Offboarding werden über Skripte abgewickelt, die Sie vom Geräteverwaltungszentrum herunterladen. Das Zentrum verfügt über benutzerdefinierte Skripte für jede dieser Bereitstellungsmethoden:</span><span class="sxs-lookup"><span data-stu-id="c9c09-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="c9c09-136">lokales Skript (bis zu 10 Computer)</span><span class="sxs-lookup"><span data-stu-id="c9c09-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="c9c09-137">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c9c09-137">Group policy</span></span>
- <span data-ttu-id="c9c09-138">System Center Konfigurationsmanager (Version 1610 oder höher)</span><span class="sxs-lookup"><span data-stu-id="c9c09-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="c9c09-139">Verwaltung mobiler Geräte/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c9c09-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="c9c09-140">VDI-Onboarding-Skripts für nicht persistente Computer</span><span class="sxs-lookup"><span data-stu-id="c9c09-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9c09-141">![Seite für das Onboarding eines Geräts](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="c9c09-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="c9c09-142">Wenden Sie für das Onboarding eines Geräts die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.</span><span class="sxs-lookup"><span data-stu-id="c9c09-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="c9c09-143">Wenn das Onboarding eines Geräts über [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9c09-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9c09-144">![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="c9c09-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="c9c09-145">Endpunkt-DLP-Daten anzeigen</span><span class="sxs-lookup"><span data-stu-id="c9c09-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="c9c09-p107">Endpunkt-DLP Endpunkt-DLP überwacht Aktivitäten auf der Grundlage des MIME-Typs, so dass Aktivitäten auch dann erfasst werden, wenn die Dateierweiterung geändert wird. In der öffentlichen Vorschau folgende Dateien überwacht:</span><span class="sxs-lookup"><span data-stu-id="c9c09-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="c9c09-148">Word-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-148">Word files</span></span>
- <span data-ttu-id="c9c09-149">PowerPoint-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-149">PowerPoint files</span></span>
- <span data-ttu-id="c9c09-150">Excel-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-150">Excel files</span></span>
- <span data-ttu-id="c9c09-151">PDF-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-151">PDF files</span></span>
- <span data-ttu-id="c9c09-152">CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-152">.csv files</span></span>
- <span data-ttu-id="c9c09-153">TSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-153">.tsv files</span></span>
- <span data-ttu-id="c9c09-154">TXT-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-154">.txt files</span></span>
- <span data-ttu-id="c9c09-155">RTF-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-155">.rtf files</span></span>
- <span data-ttu-id="c9c09-156">C-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-156">.c files</span></span>
- <span data-ttu-id="c9c09-157">CLASS-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-157">.class files</span></span>
- <span data-ttu-id="c9c09-158">CPP-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-158">.cpp files</span></span>
- <span data-ttu-id="c9c09-159">CS-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-159">.cs files</span></span>
- <span data-ttu-id="c9c09-160">H-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-160">.h files</span></span>
- <span data-ttu-id="c9c09-161">JAVA-Dateien</span><span class="sxs-lookup"><span data-stu-id="c9c09-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="c9c09-p108">Endpunkt-DLP bewertet Dateien der oben genannten Dateitypen anhand der DLP-Richtlinie und wendet die entsprechenden Schutzmaßnahmen an. Alle Dateien, die mit einer DLP-Richtlinie übereinstimmen, werden auf alle unterstützten Aktionen geprüft, auch wenn sie nicht gesperrt sind. Zusätzlich werden alle auf Word-, PowerPoint-, Excel-, PDF- und CSV-Dateien ausgeführte Dateiaktivitäten standardmäßig geprüft, unabhängig davon, ob eine DLP-Richtlinie vorhanden ist oder mit diesen Dateien übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c9c09-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="c9c09-165">Sie können Benachrichtigungen anzeigen, die mit auf Endpunktgeräten durchgesetzten DLP-Richtlinien verbunden sind, indem Sie zu [DLP-Benachrichtigungs-Verwaltungsdasboard](dlp-configure-view-alerts-policies.md) wechseln.</span><span class="sxs-lookup"><span data-stu-id="c9c09-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Warninformationen](../media/Alert-info-1.png)

<span data-ttu-id="c9c09-167">Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c9c09-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![Ereignisinformationen](../media/Event-info-1.png)

<span data-ttu-id="c9c09-169">Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9c09-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9c09-170">![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="c9c09-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="c9c09-171">Endpunkt-DLP erfasst umfassende Informationen zu überwachten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="c9c09-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="c9c09-172">Wenn eine Datei beispielsweise auf einen USB-Wechseldatenträger kopiert wird, werden die folgenden Attribute in den Aktivitätsdetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c9c09-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="c9c09-173">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="c9c09-173">activity type</span></span>
- <span data-ttu-id="c9c09-174">Client-IP</span><span class="sxs-lookup"><span data-stu-id="c9c09-174">client IP</span></span>
- <span data-ttu-id="c9c09-175">Zieldateipfad</span><span class="sxs-lookup"><span data-stu-id="c9c09-175">target file path</span></span>
- <span data-ttu-id="c9c09-176">Ereignis-Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c9c09-176">happened timestamp</span></span>
- <span data-ttu-id="c9c09-177">Dateiname</span><span class="sxs-lookup"><span data-stu-id="c9c09-177">file name</span></span>
- <span data-ttu-id="c9c09-178">Benutzer</span><span class="sxs-lookup"><span data-stu-id="c9c09-178">user</span></span>
- <span data-ttu-id="c9c09-179">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="c9c09-179">file extension</span></span>
- <span data-ttu-id="c9c09-180">Dateigröße</span><span class="sxs-lookup"><span data-stu-id="c9c09-180">file size</span></span>
- <span data-ttu-id="c9c09-181">Typ vertraulicher Information (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="c9c09-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="c9c09-182">SHA1-Wert</span><span class="sxs-lookup"><span data-stu-id="c9c09-182">sha1 value</span></span>
- <span data-ttu-id="c9c09-183">SHA256-Wert</span><span class="sxs-lookup"><span data-stu-id="c9c09-183">sha256 value</span></span>
- <span data-ttu-id="c9c09-184">Vorheriger Dateiname</span><span class="sxs-lookup"><span data-stu-id="c9c09-184">previous file name</span></span>
- <span data-ttu-id="c9c09-185">Speicherort</span><span class="sxs-lookup"><span data-stu-id="c9c09-185">location</span></span>
- <span data-ttu-id="c9c09-186">übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="c9c09-186">parent</span></span>
- <span data-ttu-id="c9c09-187">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="c9c09-187">filepath</span></span>
- <span data-ttu-id="c9c09-188">Art des Quellspeicherorts</span><span class="sxs-lookup"><span data-stu-id="c9c09-188">source location type</span></span>
- <span data-ttu-id="c9c09-189">Plattform</span><span class="sxs-lookup"><span data-stu-id="c9c09-189">platform</span></span>
- <span data-ttu-id="c9c09-190">Gerätename</span><span class="sxs-lookup"><span data-stu-id="c9c09-190">device name</span></span>
- <span data-ttu-id="c9c09-191">Art des Zielspeicherorts</span><span class="sxs-lookup"><span data-stu-id="c9c09-191">destination location type</span></span>
- <span data-ttu-id="c9c09-192">Anwendung, über die die Kopie erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="c9c09-192">application that performed the copy</span></span>
- <span data-ttu-id="c9c09-193">Microsoft Defender für Endpunkt-Geräte-ID (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="c9c09-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="c9c09-194">Hersteller des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="c9c09-194">removable media device manufacturer</span></span>
- <span data-ttu-id="c9c09-195">Modell des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="c9c09-195">removable media device model</span></span>
- <span data-ttu-id="c9c09-196">Seriennummer des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="c9c09-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9c09-197">![Attribute der Aktivität auf USB kopieren](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="c9c09-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9c09-198">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c9c09-198">Next steps</span></span>

<span data-ttu-id="c9c09-199">Jetzt, da Sie die Basics zu Endpunkt-DLP kennen, sind die nächsten Schritte folgende:</span><span class="sxs-lookup"><span data-stu-id="c9c09-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="c9c09-200">Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c9c09-200">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="c9c09-201">Nutzung von Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c9c09-201">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="c9c09-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9c09-202">See also</span></span>

- [<span data-ttu-id="c9c09-203">Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c9c09-203">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="c9c09-204">Nutzung von Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c9c09-204">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="c9c09-205">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="c9c09-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="c9c09-206">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c9c09-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="c9c09-207">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="c9c09-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="c9c09-208">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c9c09-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="c9c09-209">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="c9c09-209">Insider Risk management</span></span>](insider-risk-management.md)
