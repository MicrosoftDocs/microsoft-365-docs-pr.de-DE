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
ms.openlocfilehash: d9260da3e007885821441c8217e01650823eb8b4
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48768963"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="fbb0a-104">Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="fbb0a-105">Sie können Microsoft 365-DLP (Data Loss Prevention, Verhinderung von Datenverlust) verwenden, um die Aktionen zu überwachen, die an Elementen ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="fbb0a-106">Weitere Informationen zu DLP finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fbb0a-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="fbb0a-107">**Verhinderung von Datenverlust am Endpunkt** (Endpunkt-DLP) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von DLP auf sensible Elemente auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="fbb0a-108">Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="fbb0a-109">Endpunktaktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können</span><span class="sxs-lookup"><span data-stu-id="fbb0a-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="fbb0a-110">Mit Microsoft Endpunkt-DLP können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="fbb0a-111">Hierzu zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="fbb0a-111">This includes:</span></span>


|<span data-ttu-id="fbb0a-112">Aktivität am Element</span><span class="sxs-lookup"><span data-stu-id="fbb0a-112">activity on item</span></span> |<span data-ttu-id="fbb0a-113">überwachbar/einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="fbb0a-114">erstellt</span><span class="sxs-lookup"><span data-stu-id="fbb0a-114">created</span></span>    | <span data-ttu-id="fbb0a-115">überwachbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-115">auditable</span></span>      |
|<span data-ttu-id="fbb0a-116">umbenannt</span><span class="sxs-lookup"><span data-stu-id="fbb0a-116">renamed</span></span>    |  <span data-ttu-id="fbb0a-117">überwachbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-117">auditable</span></span>       |
|<span data-ttu-id="fbb0a-118">auf Wechselmedium kopiert oder erstellt</span><span class="sxs-lookup"><span data-stu-id="fbb0a-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="fbb0a-119">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-119">auditable and restrictable</span></span>|
|<span data-ttu-id="fbb0a-120">in Netzwerkfreigabe kopiert, z. B. \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="fbb0a-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="fbb0a-121">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="fbb0a-122">gedruckt</span><span class="sxs-lookup"><span data-stu-id="fbb0a-122">printed</span></span> |    <span data-ttu-id="fbb0a-123">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="fbb0a-124">über Chromium Edge in die Cloud kopiert</span><span class="sxs-lookup"><span data-stu-id="fbb0a-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="fbb0a-125">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="fbb0a-126">Zugriff über nicht zulässige Apps und Browser</span><span class="sxs-lookup"><span data-stu-id="fbb0a-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="fbb0a-127">überwachbar und einschränkbar</span><span class="sxs-lookup"><span data-stu-id="fbb0a-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="fbb0a-128">Was ist bei Endpunkt-DLP anders?</span><span class="sxs-lookup"><span data-stu-id="fbb0a-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="fbb0a-129">Es gibt ein paar zusätzliche Konzepte, die Sie kennen sollten, bevor Sie sich mit Endpunkt-DLP befassen.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="fbb0a-130">Aktivieren der Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="fbb0a-130">Enabling Device management</span></span>

<span data-ttu-id="fbb0a-131">Bei der Geräteverwaltung handelt es sich um die Funktionalität, die das Erfassen von Telemetriedaten von Geräten ermöglicht und sie in Microsoft 365-Compliance-Lösungen wie Endpunkt-DLP und [Insider-Risikomanagement](insider-risk-management.md) überträgt.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="fbb0a-132">Sie müssen alle Geräte, die Sie als Speicherorte in DLP-Richtlinien verwenden möchten, einbinden.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="fbb0a-134">Onboarding und Offboarding werden über Skripts verarbeitet, die Sie über das Center zur Geräteverwaltung herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="fbb0a-135">Im Center sind benutzerdefinierte Skripts für jede der folgenden Bereitstellungsmethoden verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fbb0a-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="fbb0a-136">lokales Skript (bis zu 10 Computer)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="fbb0a-137">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="fbb0a-137">Group policy</span></span>
- <span data-ttu-id="fbb0a-138">System Center Konfigurationsmanager (Version 1610 oder höher)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="fbb0a-139">Verwaltung mobiler Geräte/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fbb0a-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="fbb0a-140">VDI-Onboarding-Skripts für nicht persistente Computer</span><span class="sxs-lookup"><span data-stu-id="fbb0a-140">VDI onboarding scripts for non-persistent machines</span></span>

![Seite für das Geräte-Onboarding](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="fbb0a-142">Wenden Sie für das Geräte-Onboarding die unter [Erste Schritte mit Microsoft 365 Endpunkt-DLP-](endpoint-dlp-getting-started.md) beschriebene Vorgehensweise an.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="fbb0a-143">Wenn das Geräte-Onboarding über [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/) erfolgt ist, werden diese Geräte automatisch in der Liste der Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![Liste der verwalteten Geräte](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="fbb0a-145">Anzeigen von Endpunkt-DLP-Daten</span><span class="sxs-lookup"><span data-stu-id="fbb0a-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="fbb0a-146">Endpunkt-DLP überwacht Aktivitäten basierend auf dem MIME-Typ, sodass sie auch dann erfasst werden, wenn die Dateierweiterung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="fbb0a-147">In der öffentlichen Vorschau wird Folgendes überwacht:</span><span class="sxs-lookup"><span data-stu-id="fbb0a-147">At public preview it watches all:</span></span>

- <span data-ttu-id="fbb0a-148">Word-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-148">Word files</span></span>
- <span data-ttu-id="fbb0a-149">PowerPoint-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-149">PowerPoint files</span></span>
- <span data-ttu-id="fbb0a-150">Excel-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-150">Excel files</span></span>
- <span data-ttu-id="fbb0a-151">PDF-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-151">PDF files</span></span>
- <span data-ttu-id="fbb0a-152">CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-152">.csv files</span></span>
- <span data-ttu-id="fbb0a-153">TSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-153">.tsv files</span></span>
- <span data-ttu-id="fbb0a-154">c-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-154">c files</span></span>
- <span data-ttu-id="fbb0a-155">Klassendateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-155">class files</span></span>
- <span data-ttu-id="fbb0a-156">CPP-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-156">cpp files</span></span>
- <span data-ttu-id="fbb0a-157">CS-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-157">cs files</span></span>
- <span data-ttu-id="fbb0a-158">H-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-158">h files</span></span>
- <span data-ttu-id="fbb0a-159">Java-Dateien</span><span class="sxs-lookup"><span data-stu-id="fbb0a-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="fbb0a-160">TXT- und Quellcodedateien werden standardmäßig nicht überwacht. DLP wertet sie anhand der angewendeten Richtlinien aus, anschließend werden Benutzeraktionen entsprechend überwacht oder blockiert.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="fbb0a-161">Nach dem Onboarding eines Geräts werden Informationen zu überwachten Aktivitäten an den Aktivitäten-Explorer gesendet, noch bevor Sie DLP-Richtlinien konfigurieren und bereitstellen, die Geräte als Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![Endpunkt-DLP-Ereignisse im Aktivitäten-Explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="fbb0a-163">Endpunkt-DLP erfasst umfassende Informationen zu überwachten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="fbb0a-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="fbb0a-164">Wenn eine Datei beispielsweise auf einen USB-Wechseldatenträger kopiert wird, werden die folgenden Attribute in den Aktivitätsdetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbb0a-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="fbb0a-165">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="fbb0a-165">activity type</span></span>
- <span data-ttu-id="fbb0a-166">Client-IP</span><span class="sxs-lookup"><span data-stu-id="fbb0a-166">client IP</span></span>
- <span data-ttu-id="fbb0a-167">Zieldateipfad</span><span class="sxs-lookup"><span data-stu-id="fbb0a-167">target file path</span></span>
- <span data-ttu-id="fbb0a-168">Ereignis-Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="fbb0a-168">happened timestamp</span></span>
- <span data-ttu-id="fbb0a-169">Dateiname</span><span class="sxs-lookup"><span data-stu-id="fbb0a-169">file name</span></span>
- <span data-ttu-id="fbb0a-170">Benutzer</span><span class="sxs-lookup"><span data-stu-id="fbb0a-170">user</span></span>
- <span data-ttu-id="fbb0a-171">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="fbb0a-171">file extension</span></span>
- <span data-ttu-id="fbb0a-172">Dateigröße</span><span class="sxs-lookup"><span data-stu-id="fbb0a-172">file size</span></span>
- <span data-ttu-id="fbb0a-173">Typ vertraulicher Information (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="fbb0a-174">SHA1-Wert</span><span class="sxs-lookup"><span data-stu-id="fbb0a-174">sha1 value</span></span>
- <span data-ttu-id="fbb0a-175">SHA256-Wert</span><span class="sxs-lookup"><span data-stu-id="fbb0a-175">sha256 value</span></span>
- <span data-ttu-id="fbb0a-176">Vorheriger Dateiname</span><span class="sxs-lookup"><span data-stu-id="fbb0a-176">previous file name</span></span>
- <span data-ttu-id="fbb0a-177">Speicherort</span><span class="sxs-lookup"><span data-stu-id="fbb0a-177">location</span></span>
- <span data-ttu-id="fbb0a-178">übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="fbb0a-178">parent</span></span>
- <span data-ttu-id="fbb0a-179">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="fbb0a-179">filepath</span></span>
- <span data-ttu-id="fbb0a-180">Art des Quellspeicherorts</span><span class="sxs-lookup"><span data-stu-id="fbb0a-180">source location type</span></span>
- <span data-ttu-id="fbb0a-181">Plattform</span><span class="sxs-lookup"><span data-stu-id="fbb0a-181">platform</span></span>
- <span data-ttu-id="fbb0a-182">Gerätename</span><span class="sxs-lookup"><span data-stu-id="fbb0a-182">device name</span></span>
- <span data-ttu-id="fbb0a-183">Art des Zielspeicherorts</span><span class="sxs-lookup"><span data-stu-id="fbb0a-183">destination location type</span></span>
- <span data-ttu-id="fbb0a-184">Anwendung, über die die Kopie erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="fbb0a-184">application that performed the copy</span></span>
- <span data-ttu-id="fbb0a-185">Microsoft Defender für Endpunkt-Geräte-ID (sofern zutreffend)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="fbb0a-186">Hersteller des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="fbb0a-186">removable media device manufacturer</span></span>
- <span data-ttu-id="fbb0a-187">Modell des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="fbb0a-187">removable media device model</span></span>
- <span data-ttu-id="fbb0a-188">Seriennummer des Wechselmediums</span><span class="sxs-lookup"><span data-stu-id="fbb0a-188">removable media device serial number</span></span>

![Attribute der Aktivität "nach USB kopieren"](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="fbb0a-190">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fbb0a-190">Next steps</span></span>

<span data-ttu-id="fbb0a-191">Jetzt, da Sie die Basics zu Endpunkt-DLP kennen, sind die nächsten Schritte folgende:</span><span class="sxs-lookup"><span data-stu-id="fbb0a-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="fbb0a-192">Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="fbb0a-193">Nutzung von Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="fbb0a-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbb0a-194">See also</span></span>

- [<span data-ttu-id="fbb0a-195">Erste Schritte mit Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="fbb0a-196">Nutzung von Microsoft Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="fbb0a-197">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="fbb0a-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="fbb0a-198">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="fbb0a-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="fbb0a-199">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="fbb0a-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="fbb0a-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="fbb0a-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="fbb0a-201">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="fbb0a-201">Insider Risk management</span></span>](insider-risk-management.md)