---
title: Exportieren der Bewertung von Softwarerisiken pro Gerät
description: Die API-Antwort ist pro Gerät und enthält anfällige Software, die auf Ihren verfügbar gemachten Geräten installiert ist, sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten. Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilites assessment, software vulnerability report, vulnerability report by machine,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689213"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="40871-105">Exportieren der Bewertung von Softwarerisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="40871-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40871-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="40871-106">**Applies to:**</span></span>

- [<span data-ttu-id="40871-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="40871-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40871-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40871-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="40871-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="40871-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40871-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="40871-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="40871-111">Gibt alle bekannten Softwarerisiken und deren Details für alle Geräte auf Gerätebasis zurück.</span><span class="sxs-lookup"><span data-stu-id="40871-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="40871-112">Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40871-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="40871-113">Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten zum Abrufen:</span><span class="sxs-lookup"><span data-stu-id="40871-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="40871-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  Die API verwendet alle Daten in Ihrer Organisation als Json-Antworten nach dem OData-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="40871-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="40871-115">Diese Methode ist am besten für _kleine Organisationen mit weniger als 100 K Geräten._</span><span class="sxs-lookup"><span data-stu-id="40871-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="40871-116">Die Antwort wird paginiert, sodass Sie das odata.nextLink-Feld aus der Antwort verwenden können, \@ um die nächsten Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40871-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="40871-117">[Exportieren der Bewertung von Softwarerisiken über Dateien](#2-export-software-vulnerabilities-assessment-via-files) Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="40871-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="40871-118">Daher wird es für große Organisationen mit mehr als 100 K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="40871-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="40871-119">Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien.</span><span class="sxs-lookup"><span data-stu-id="40871-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="40871-120">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="40871-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="40871-121">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="40871-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="40871-122">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40871-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="40871-123">Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.</span><span class="sxs-lookup"><span data-stu-id="40871-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="40871-124">Erfasste Daten (entweder mithilfe von _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="40871-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="40871-125">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="40871-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="40871-126">Sofern nicht anders angegeben, sind \*\*\*\* alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**</span><span class="sxs-lookup"><span data-stu-id="40871-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="40871-127">1. Export software vulnerabilities assessment (OData)</span><span class="sxs-lookup"><span data-stu-id="40871-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="40871-128">Beschreibung der 1.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="40871-128">1.1 API method description</span></span>

<span data-ttu-id="40871-129">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="40871-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="40871-130">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.</span><span class="sxs-lookup"><span data-stu-id="40871-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="40871-131">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="40871-131">Limitations</span></span>

>- <span data-ttu-id="40871-132">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="40871-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="40871-133">Die Tarifeinschränkungen für diese API sind 30 Anrufe pro Minute und 1000 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="40871-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="40871-134">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="40871-134">1.2 Permissions</span></span>

<span data-ttu-id="40871-135">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40871-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40871-136">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="40871-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="40871-137">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="40871-137">Permission type</span></span> | <span data-ttu-id="40871-138">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="40871-138">Permission</span></span> | <span data-ttu-id="40871-139">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="40871-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="40871-140">Anwendung</span><span class="sxs-lookup"><span data-stu-id="40871-140">Application</span></span> | <span data-ttu-id="40871-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="40871-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="40871-142">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="40871-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="40871-143">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="40871-143">Delegated (work or school account)</span></span> | <span data-ttu-id="40871-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="40871-144">Vulnerability.Read</span></span> | <span data-ttu-id="40871-145">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="40871-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="40871-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="40871-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="40871-147">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="40871-147">1.4 Parameters</span></span>

- <span data-ttu-id="40871-148">pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort</span><span class="sxs-lookup"><span data-stu-id="40871-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="40871-149">$top – Anzahl der zurückzukehrende Ergebnisse (gibt @odata.nextLink nicht zurück und zieht daher nicht alle Daten zurück)</span><span class="sxs-lookup"><span data-stu-id="40871-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="40871-150">1.5 Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="40871-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="40871-151">Jeder Datensatz beträgt ca. 1 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="40871-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="40871-152">Berücksichtigen Sie dies bei der Auswahl des richtigen pageSize-Parameters für Sie.</span><span class="sxs-lookup"><span data-stu-id="40871-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="40871-153">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40871-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="40871-154">Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="40871-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="40871-155">Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="40871-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="40871-156">Beim Ausführen dieser API wird die resultierende Ausgabe nicht unbedingt in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40871-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="40871-157">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="40871-157">Property (ID)</span></span> | <span data-ttu-id="40871-158">Datentyp</span><span class="sxs-lookup"><span data-stu-id="40871-158">Data type</span></span> | <span data-ttu-id="40871-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40871-159">Description</span></span> | <span data-ttu-id="40871-160">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="40871-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="40871-161">CveId</span><span class="sxs-lookup"><span data-stu-id="40871-161">CveId</span></span> | <span data-ttu-id="40871-162">string</span><span class="sxs-lookup"><span data-stu-id="40871-162">string</span></span> | <span data-ttu-id="40871-163">Eindeutige ID, die der Sicherheitslücke unter dem System für häufige Sicherheitsrisiken und -risiken (Common Vulnerabilities and Exposures, CVE) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="40871-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="40871-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="40871-164">CVE-2020-15992</span></span>
<span data-ttu-id="40871-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="40871-165">CvssScore</span></span> | <span data-ttu-id="40871-166">string</span><span class="sxs-lookup"><span data-stu-id="40871-166">string</span></span> | <span data-ttu-id="40871-167">Die CVSS-Bewertung des CVE.</span><span class="sxs-lookup"><span data-stu-id="40871-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="40871-168">6.2</span><span class="sxs-lookup"><span data-stu-id="40871-168">6.2</span></span>
<span data-ttu-id="40871-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="40871-169">DeviceId</span></span> | <span data-ttu-id="40871-170">string</span><span class="sxs-lookup"><span data-stu-id="40871-170">string</span></span> | <span data-ttu-id="40871-171">Eindeutige ID für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="40871-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="40871-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="40871-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="40871-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="40871-173">DeviceName</span></span> | <span data-ttu-id="40871-174">string</span><span class="sxs-lookup"><span data-stu-id="40871-174">string</span></span> | <span data-ttu-id="40871-175">Vollqualifizierter Domänenname (FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="40871-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="40871-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40871-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="40871-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="40871-177">DiskPaths</span></span>  | <span data-ttu-id="40871-178">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="40871-178">Array\[string\]</span></span> | <span data-ttu-id="40871-179">Datenträgerbeweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="40871-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="40871-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="40871-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="40871-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="40871-181">ExploitabilityLevel</span></span> | <span data-ttu-id="40871-182">string</span><span class="sxs-lookup"><span data-stu-id="40871-182">string</span></span> | <span data-ttu-id="40871-183">Die Ausnutzungsebene dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="40871-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="40871-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="40871-184">ExploitIsInKit</span></span>
<span data-ttu-id="40871-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="40871-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="40871-186">string</span><span class="sxs-lookup"><span data-stu-id="40871-186">string</span></span> | <span data-ttu-id="40871-187">Das erste Mal, dass der CVE dieses Produkts auf dem Gerät angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="40871-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="40871-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="40871-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="40871-189">Id</span><span class="sxs-lookup"><span data-stu-id="40871-189">Id</span></span> | <span data-ttu-id="40871-190">string</span><span class="sxs-lookup"><span data-stu-id="40871-190">string</span></span> | <span data-ttu-id="40871-191">Eindeutige ID für den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="40871-191">Unique identifier for the record.</span></span> | <span data-ttu-id="40871-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="40871-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="40871-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="40871-193">LastSeenTimestamp</span></span> | <span data-ttu-id="40871-194">string</span><span class="sxs-lookup"><span data-stu-id="40871-194">string</span></span> | <span data-ttu-id="40871-195">Das letzte Mal, dass der CVE auf dem Gerät angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="40871-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="40871-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="40871-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="40871-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="40871-197">OSPlatform</span></span> | <span data-ttu-id="40871-198">string</span><span class="sxs-lookup"><span data-stu-id="40871-198">string</span></span> | <span data-ttu-id="40871-199">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40871-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="40871-200">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="40871-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="40871-201">Weitere Informationen finden Sie unter tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="40871-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="40871-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="40871-202">Windows10</span></span>
<span data-ttu-id="40871-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="40871-203">RbacGroupName</span></span>  | <span data-ttu-id="40871-204">string</span><span class="sxs-lookup"><span data-stu-id="40871-204">string</span></span> | <span data-ttu-id="40871-205">Die rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="40871-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="40871-206">Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40871-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="40871-207">Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="40871-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="40871-208">Server</span><span class="sxs-lookup"><span data-stu-id="40871-208">Servers</span></span>
<span data-ttu-id="40871-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="40871-209">RecommendationReference</span></span> | <span data-ttu-id="40871-210">string</span><span class="sxs-lookup"><span data-stu-id="40871-210">string</span></span> | <span data-ttu-id="40871-211">Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.</span><span class="sxs-lookup"><span data-stu-id="40871-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="40871-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="40871-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="40871-213">RecommendedSecurityUpdate (optional)</span><span class="sxs-lookup"><span data-stu-id="40871-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="40871-214">string</span><span class="sxs-lookup"><span data-stu-id="40871-214">string</span></span> | <span data-ttu-id="40871-215">Name oder Beschreibung des Sicherheitsupdates, das vom Softwareanbieter bereitgestellt wird, um die Sicherheitslücke zu bean standen.</span><span class="sxs-lookup"><span data-stu-id="40871-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="40871-216">Sicherheitsupdates vom April 2020</span><span class="sxs-lookup"><span data-stu-id="40871-216">April 2020 Security Updates</span></span>
<span data-ttu-id="40871-217">RecommendedSecurityUpdateId (optional)</span><span class="sxs-lookup"><span data-stu-id="40871-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="40871-218">string</span><span class="sxs-lookup"><span data-stu-id="40871-218">string</span></span> | <span data-ttu-id="40871-219">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="40871-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="40871-220">4550961</span><span class="sxs-lookup"><span data-stu-id="40871-220">4550961</span></span>
<span data-ttu-id="40871-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="40871-221">RegistryPaths</span></span>  | <span data-ttu-id="40871-222">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="40871-222">Array\[string\]</span></span> | <span data-ttu-id="40871-223">Registrierungsbeweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="40871-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="40871-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="40871-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="40871-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="40871-225">SoftwareName</span></span> | <span data-ttu-id="40871-226">string</span><span class="sxs-lookup"><span data-stu-id="40871-226">string</span></span> | <span data-ttu-id="40871-227">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="40871-227">Name of the software product.</span></span> | <span data-ttu-id="40871-228">chrome</span><span class="sxs-lookup"><span data-stu-id="40871-228">chrome</span></span>
<span data-ttu-id="40871-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="40871-229">SoftwareVendor</span></span> | <span data-ttu-id="40871-230">string</span><span class="sxs-lookup"><span data-stu-id="40871-230">string</span></span> | <span data-ttu-id="40871-231">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="40871-231">Name of the software vendor.</span></span> | <span data-ttu-id="40871-232">google</span><span class="sxs-lookup"><span data-stu-id="40871-232">google</span></span>
<span data-ttu-id="40871-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="40871-233">SoftwareVersion</span></span> | <span data-ttu-id="40871-234">string</span><span class="sxs-lookup"><span data-stu-id="40871-234">string</span></span> | <span data-ttu-id="40871-235">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="40871-235">Version number of the software product.</span></span> | <span data-ttu-id="40871-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="40871-236">81.0.4044.138</span></span>
<span data-ttu-id="40871-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="40871-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="40871-238">string</span><span class="sxs-lookup"><span data-stu-id="40871-238">string</span></span> | <span data-ttu-id="40871-239">Schweregrad, der der Sicherheitslücke zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="40871-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="40871-240">Mittel</span><span class="sxs-lookup"><span data-stu-id="40871-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="40871-241">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="40871-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="40871-242">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="40871-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="40871-243">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="40871-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="40871-244">2. Bewertung von Softwarerisiken exportieren (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="40871-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="40871-245">Beschreibung der 2.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="40871-245">2.1 API method description</span></span>

<span data-ttu-id="40871-246">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="40871-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="40871-247">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.</span><span class="sxs-lookup"><span data-stu-id="40871-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="40871-248">2.1.2 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="40871-248">2.1.2 Limitations</span></span>

<span data-ttu-id="40871-249">Die Tarifeinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="40871-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="40871-250">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="40871-250">2.2 Permissions</span></span>

<span data-ttu-id="40871-251">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40871-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40871-252">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="40871-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="40871-253">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="40871-253">Permission type</span></span> | <span data-ttu-id="40871-254">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="40871-254">Permission</span></span> | <span data-ttu-id="40871-255">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="40871-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="40871-256">Anwendung</span><span class="sxs-lookup"><span data-stu-id="40871-256">Application</span></span> | <span data-ttu-id="40871-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="40871-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="40871-258">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="40871-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="40871-259">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="40871-259">Delegated (work or school account)</span></span> | <span data-ttu-id="40871-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="40871-260">Vulnerability.Read</span></span> | <span data-ttu-id="40871-261">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="40871-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="40871-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="40871-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="40871-263">2.4-Parameter</span><span class="sxs-lookup"><span data-stu-id="40871-263">2.4 Parameters</span></span>

- <span data-ttu-id="40871-264">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (Maximal 24 Stunden)</span><span class="sxs-lookup"><span data-stu-id="40871-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="40871-265">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="40871-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="40871-266">Die Dateien sind gzip-komprimierte & im mehrstufigen Json-Format.</span><span class="sxs-lookup"><span data-stu-id="40871-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="40871-267">Die #A0 sind nur für 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="40871-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="40871-268">Um die maximale Downloadgeschwindigkeit Ihrer Daten zu erhalten, können Sie sicherstellen, dass Sie aus derselben Azure-Region heruntergeladen werden, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="40871-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="40871-269">Jeder Datensatz beträgt ca. 1 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="40871-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="40871-270">Berücksichtigen Sie dies bei der Auswahl des richtigen pageSize-Parameters für Sie.</span><span class="sxs-lookup"><span data-stu-id="40871-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="40871-271">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40871-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="40871-272">Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="40871-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="40871-273">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="40871-273">Property (ID)</span></span> | <span data-ttu-id="40871-274">Datentyp</span><span class="sxs-lookup"><span data-stu-id="40871-274">Data type</span></span> | <span data-ttu-id="40871-275">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40871-275">Description</span></span> | <span data-ttu-id="40871-276">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="40871-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="40871-277">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="40871-277">Export files</span></span> | <span data-ttu-id="40871-278">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="40871-278">array\[string\]</span></span>  | <span data-ttu-id="40871-279">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="40871-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="40871-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="40871-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="40871-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="40871-281">GeneratedTime</span></span> | <span data-ttu-id="40871-282">string</span><span class="sxs-lookup"><span data-stu-id="40871-282">string</span></span> | <span data-ttu-id="40871-283">Der Zeitpunkt, zu dem der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="40871-283">The time that the export was generated.</span></span> | <span data-ttu-id="40871-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="40871-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="40871-285">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="40871-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="40871-286">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="40871-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="40871-287">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="40871-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="40871-288">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="40871-288">See also</span></span>

- [<span data-ttu-id="40871-289">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="40871-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="40871-290">Exportieren einer sicheren Konfigurationsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="40871-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="40871-291">Exportieren der Softwareinventarbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="40871-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="40871-292">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="40871-292">Other related</span></span>

- [<span data-ttu-id="40871-293">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="40871-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="40871-294">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="40871-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
