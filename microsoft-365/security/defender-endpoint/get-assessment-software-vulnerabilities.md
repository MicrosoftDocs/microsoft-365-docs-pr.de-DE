---
title: Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät
description: Die API-Antwort ist pro Gerät und enthält anfällige Software, die auf Ihren verfügbar gemachten Geräten installiert ist, sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten. Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.
keywords: API, APIs, Exportbewertung, Bewertung pro Gerät, Bericht zur Bewertung von Sicherheitsrisiken, Bewertung der Sicherheitslücken des Geräts, Bericht über Sicherheitsrisiken, Bewertung der sicheren Konfiguration, Bericht über sichere Konfiguration, Bewertung von Software-Sicherheitsrisiken, Bericht über Software-Sicherheitsrisiken, Sicherheitsrisikobericht nach Computer,
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
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052963"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="4b60b-105">Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4b60b-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b60b-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4b60b-106">**Applies to:**</span></span>

- [<span data-ttu-id="4b60b-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4b60b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4b60b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b60b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4b60b-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4b60b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4b60b-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="4b60b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="4b60b-111">Gibt alle bekannten Softwarerisiken und deren Details für alle Geräte pro Gerät zurück.</span><span class="sxs-lookup"><span data-stu-id="4b60b-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="4b60b-112">Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="4b60b-113">Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:</span><span class="sxs-lookup"><span data-stu-id="4b60b-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="4b60b-114">[ **JSON-Antwort zur** Bewertung von Software-Sicherheitsrisiken exportieren](#1-export-software-vulnerabilities-assessment-json-response)  Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten ab.</span><span class="sxs-lookup"><span data-stu-id="4b60b-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="4b60b-115">Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100 K-Geräten._</span><span class="sxs-lookup"><span data-stu-id="4b60b-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="4b60b-116">Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="4b60b-117">Exportieren der [Bewertung von Software-Sicherheitsrisiken **über Dateien**](#2-export-software-vulnerabilities-assessment-via-files) Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="4b60b-118">Via-Dateien werden für große Organisationen mit mehr als 100 K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="4b60b-119">Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab.</span><span class="sxs-lookup"><span data-stu-id="4b60b-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="4b60b-120">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="4b60b-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="4b60b-121">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="4b60b-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="4b60b-122">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="4b60b-123">Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4b60b-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="4b60b-124">[ **JSON-Antwort zur** Bewertung von Software-Sicherheitsrisiken im Delta-Export](#3-delta-export-software-vulnerabilities-assessment-json-response)  Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination von: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId und EventTimestamp zurück.</span><span class="sxs-lookup"><span data-stu-id="4b60b-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="4b60b-125">Die API ruft Daten in Ihrer Organisation als JSON-Antworten ab.</span><span class="sxs-lookup"><span data-stu-id="4b60b-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="4b60b-126">Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="4b60b-127">Im Gegensatz zur vollständigen "Bewertung von Software-Sicherheitsrisiken (JSON-Antwort)" – die verwendet wird, um eine vollständige Momentaufnahme der Bewertung der Software-Sicherheitsrisiken Ihrer Organisation nach Gerät zu erhalten – wird der Delta-Export-API-Aufruf verwendet, um nur die Änderungen abzurufen, die zwischen einem ausgewählten Datum und dem aktuellen Datum (dem "Delta"-API-Aufruf) aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4b60b-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="4b60b-128">Anstatt jedes Mal einen vollständigen Export mit einer großen Datenmenge zu erhalten, erhalten Sie nur spezifische Informationen zu neuen, festen und aktualisierten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="4b60b-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="4b60b-129">Der JSON-Antwort-API-Aufruf des Deltaexports kann auch verwendet werden, um verschiedene KPIs zu berechnen, z. B. "wie viele Sicherheitsrisiken wurden behoben?"</span><span class="sxs-lookup"><span data-stu-id="4b60b-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="4b60b-130">oder "wie viele neue Sicherheitsrisiken wurden zu meiner Organisation hinzugefügt?"</span><span class="sxs-lookup"><span data-stu-id="4b60b-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="4b60b-131">Da der JSON-Antwort-API-Aufruf des Delta-Exports für Softwarerisiken nur Daten für einen zielgerichteten Datumsbereich zurückgibt, wird er nicht als _vollständiger Export_ betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4b60b-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="4b60b-132">Daten, die gesammelt werden (mithilfe der _JSON-Antwort_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-132">Data that is collected (using either _Json response_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="4b60b-133">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="4b60b-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="4b60b-134">Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="4b60b-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="4b60b-135">1. Bewertung von Software-Sicherheitsrisiken exportieren (JSON-Antwort)</span><span class="sxs-lookup"><span data-stu-id="4b60b-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="4b60b-136">1.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-136">1.1 API method description</span></span>

<span data-ttu-id="4b60b-137">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="4b60b-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="4b60b-138">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.</span><span class="sxs-lookup"><span data-stu-id="4b60b-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="4b60b-139">1.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="4b60b-140">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="4b60b-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="4b60b-141">Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="4b60b-142">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-142">1.2 Permissions</span></span>

<span data-ttu-id="4b60b-143">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4b60b-144">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4b60b-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="4b60b-145">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-145">Permission type</span></span> | <span data-ttu-id="4b60b-146">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-146">Permission</span></span> | <span data-ttu-id="4b60b-147">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="4b60b-148">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4b60b-148">Application</span></span> | <span data-ttu-id="4b60b-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4b60b-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="4b60b-150">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4b60b-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="4b60b-151">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4b60b-151">Delegated (work or school account)</span></span> | <span data-ttu-id="4b60b-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4b60b-152">Vulnerability.Read</span></span> | <span data-ttu-id="4b60b-153">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4b60b-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="4b60b-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="4b60b-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="4b60b-155">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="4b60b-155">1.4 Parameters</span></span>

- <span data-ttu-id="4b60b-156">pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort</span><span class="sxs-lookup"><span data-stu-id="4b60b-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="4b60b-157">$top – Anzahl der zurückzugebenden Ergebnisse (gibt nicht @odata.nextLink zurück und ruft daher nicht alle Daten ab)</span><span class="sxs-lookup"><span data-stu-id="4b60b-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="4b60b-158">1.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b60b-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="4b60b-159">Jeder Datensatz enthält ca. 1 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="4b60b-160">Berücksichtigen Sie dies, wenn Sie den richtigen pageSize-Parameter für Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="4b60b-161">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="4b60b-162">Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="4b60b-163">Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b60b-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="4b60b-164">Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="4b60b-165">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="4b60b-165">Property (ID)</span></span> | <span data-ttu-id="4b60b-166">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-166">Data type</span></span> | <span data-ttu-id="4b60b-167">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-167">Description</span></span> | <span data-ttu-id="4b60b-168">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="4b60b-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4b60b-169">CveId</span><span class="sxs-lookup"><span data-stu-id="4b60b-169">CveId</span></span> | <span data-ttu-id="4b60b-170">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-170">string</span></span> | <span data-ttu-id="4b60b-171">Eindeutiger Bezeichner, der dem Sicherheitsrisiko unter dem System für allgemeine Sicherheitsrisiken und Sicherheitsrisiken (CVE) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="4b60b-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="4b60b-172">CVE-2020-15992</span></span>
<span data-ttu-id="4b60b-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="4b60b-173">CvssScore</span></span> | <span data-ttu-id="4b60b-174">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-174">string</span></span> | <span data-ttu-id="4b60b-175">Die CVSS-Bewertung des CVE.</span><span class="sxs-lookup"><span data-stu-id="4b60b-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="4b60b-176">6.2</span><span class="sxs-lookup"><span data-stu-id="4b60b-176">6.2</span></span>
<span data-ttu-id="4b60b-177">Deviceid</span><span class="sxs-lookup"><span data-stu-id="4b60b-177">DeviceId</span></span> | <span data-ttu-id="4b60b-178">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-178">string</span></span> | <span data-ttu-id="4b60b-179">Eindeutiger Bezeichner für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="4b60b-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="4b60b-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="4b60b-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="4b60b-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="4b60b-181">DeviceName</span></span> | <span data-ttu-id="4b60b-182">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-182">string</span></span> | <span data-ttu-id="4b60b-183">Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="4b60b-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b60b-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="4b60b-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="4b60b-185">DiskPaths</span></span>  | <span data-ttu-id="4b60b-186">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="4b60b-186">Array\[string\]</span></span> | <span data-ttu-id="4b60b-187">Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="4b60b-188">[ "C:\Programme (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="4b60b-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="4b60b-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="4b60b-189">ExploitabilityLevel</span></span> | <span data-ttu-id="4b60b-190">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-190">string</span></span> | <span data-ttu-id="4b60b-191">Die Ausnutzbarkeitsstufe dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="4b60b-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="4b60b-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="4b60b-192">ExploitIsInKit</span></span>
<span data-ttu-id="4b60b-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="4b60b-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="4b60b-194">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-194">string</span></span> | <span data-ttu-id="4b60b-195">Die CVE dieses Produkts wurde zum ersten Mal auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b60b-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="4b60b-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="4b60b-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="4b60b-197">Id</span><span class="sxs-lookup"><span data-stu-id="4b60b-197">Id</span></span> | <span data-ttu-id="4b60b-198">string</span><span class="sxs-lookup"><span data-stu-id="4b60b-198">string</span></span> | <span data-ttu-id="4b60b-199">Eindeutiger Bezeichner für den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="4b60b-199">Unique identifier for the record.</span></span> | <span data-ttu-id="4b60b-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="4b60b-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="4b60b-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="4b60b-201">LastSeenTimestamp</span></span> | <span data-ttu-id="4b60b-202">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-202">string</span></span> | <span data-ttu-id="4b60b-203">Das letzte Mal, als das CVE auf dem Gerät angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="4b60b-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="4b60b-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="4b60b-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="4b60b-205">OSPlatform</span></span> | <span data-ttu-id="4b60b-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-206">string</span></span> | <span data-ttu-id="4b60b-207">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b60b-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4b60b-208">Diese Eigenschaft gibt bestimmte Betriebssysteme an, einschließlich Variationen innerhalb derselben Familie, z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4b60b-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="4b60b-209">Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="4b60b-210">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b60b-210">Windows10</span></span>
<span data-ttu-id="4b60b-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="4b60b-211">RbacGroupName</span></span>  | <span data-ttu-id="4b60b-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-212">string</span></span> | <span data-ttu-id="4b60b-213">Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4b60b-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="4b60b-214">Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen".</span><span class="sxs-lookup"><span data-stu-id="4b60b-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="4b60b-215">Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="4b60b-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="4b60b-216">Server</span><span class="sxs-lookup"><span data-stu-id="4b60b-216">Servers</span></span>
<span data-ttu-id="4b60b-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="4b60b-217">RecommendationReference</span></span> | <span data-ttu-id="4b60b-218">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-218">string</span></span> | <span data-ttu-id="4b60b-219">Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.</span><span class="sxs-lookup"><span data-stu-id="4b60b-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="4b60b-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="4b60b-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="4b60b-221">RecommendedSecurityUpdate (optional)</span><span class="sxs-lookup"><span data-stu-id="4b60b-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="4b60b-222">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-222">string</span></span> | <span data-ttu-id="4b60b-223">Name oder Beschreibung des sicherheitsrelevanten Updates, das vom Softwareanbieter bereitgestellt wurde, um die Sicherheitsanfälligkeit zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="4b60b-224">Sicherheitsupdates vom April 2020</span><span class="sxs-lookup"><span data-stu-id="4b60b-224">April 2020 Security Updates</span></span>
<span data-ttu-id="4b60b-225">RecommendedSecurityUpdateId (optional)</span><span class="sxs-lookup"><span data-stu-id="4b60b-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="4b60b-226">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-226">string</span></span> | <span data-ttu-id="4b60b-227">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="4b60b-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="4b60b-228">4550961</span><span class="sxs-lookup"><span data-stu-id="4b60b-228">4550961</span></span>
<span data-ttu-id="4b60b-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="4b60b-229">RegistryPaths</span></span>  | <span data-ttu-id="4b60b-230">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="4b60b-230">Array\[string\]</span></span> | <span data-ttu-id="4b60b-231">Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="4b60b-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="4b60b-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="4b60b-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="4b60b-233">SoftwareName</span></span> | <span data-ttu-id="4b60b-234">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-234">string</span></span> | <span data-ttu-id="4b60b-235">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-235">Name of the software product.</span></span> | <span data-ttu-id="4b60b-236">Chrome</span><span class="sxs-lookup"><span data-stu-id="4b60b-236">chrome</span></span>
<span data-ttu-id="4b60b-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="4b60b-237">SoftwareVendor</span></span> | <span data-ttu-id="4b60b-238">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-238">string</span></span> | <span data-ttu-id="4b60b-239">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="4b60b-239">Name of the software vendor.</span></span> | <span data-ttu-id="4b60b-240">Google</span><span class="sxs-lookup"><span data-stu-id="4b60b-240">google</span></span>
<span data-ttu-id="4b60b-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="4b60b-241">SoftwareVersion</span></span> | <span data-ttu-id="4b60b-242">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-242">string</span></span> | <span data-ttu-id="4b60b-243">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-243">Version number of the software product.</span></span> | <span data-ttu-id="4b60b-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="4b60b-244">81.0.4044.138</span></span>
<span data-ttu-id="4b60b-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="4b60b-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="4b60b-246">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-246">string</span></span> | <span data-ttu-id="4b60b-247">Schweregrad, der dem Sicherheitsrisiko zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="4b60b-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="4b60b-248">Mittel</span><span class="sxs-lookup"><span data-stu-id="4b60b-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="4b60b-249">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="4b60b-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="4b60b-250">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="4b60b-251">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="4b60b-252">2. Exportieren der Bewertung von Software-Sicherheitsrisiken (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="4b60b-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="4b60b-253">2.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-253">2.1 API method description</span></span>

<span data-ttu-id="4b60b-254">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="4b60b-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="4b60b-255">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.</span><span class="sxs-lookup"><span data-stu-id="4b60b-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="4b60b-256">2.1.2 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-256">2.1.2 Limitations</span></span>

<span data-ttu-id="4b60b-257">Die Rateneinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="4b60b-258">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-258">2.2 Permissions</span></span>

<span data-ttu-id="4b60b-259">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4b60b-260">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4b60b-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="4b60b-261">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-261">Permission type</span></span> | <span data-ttu-id="4b60b-262">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-262">Permission</span></span> | <span data-ttu-id="4b60b-263">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="4b60b-264">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4b60b-264">Application</span></span> | <span data-ttu-id="4b60b-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4b60b-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="4b60b-266">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4b60b-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="4b60b-267">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4b60b-267">Delegated (work or school account)</span></span> | <span data-ttu-id="4b60b-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4b60b-268">Vulnerability.Read</span></span> | <span data-ttu-id="4b60b-269">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4b60b-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="4b60b-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="4b60b-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="4b60b-271">2.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="4b60b-271">2.4 Parameters</span></span>

- <span data-ttu-id="4b60b-272">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (maximal 24 Stunden)</span><span class="sxs-lookup"><span data-stu-id="4b60b-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="4b60b-273">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b60b-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="4b60b-274">Die Dateien werden & im mehrzeiligen JSON-Format gzipkomprimiert.</span><span class="sxs-lookup"><span data-stu-id="4b60b-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="4b60b-275">Die Download-URLs sind nur 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b60b-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="4b60b-276">Für eine maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie aus derselben Azure-Region herunterladen, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="4b60b-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="4b60b-277">Jeder Datensatz enthält ca. 1 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="4b60b-278">Berücksichtigen Sie dies, wenn Sie den richtigen pageSize-Parameter für Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="4b60b-279">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="4b60b-280">Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="4b60b-281">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="4b60b-281">Property (ID)</span></span> | <span data-ttu-id="4b60b-282">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-282">Data type</span></span> | <span data-ttu-id="4b60b-283">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-283">Description</span></span> | <span data-ttu-id="4b60b-284">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="4b60b-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4b60b-285">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="4b60b-285">Export files</span></span> | <span data-ttu-id="4b60b-286">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="4b60b-286">array\[string\]</span></span>  | <span data-ttu-id="4b60b-287">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="4b60b-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="4b60b-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="4b60b-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="4b60b-289">GeneratedTime</span></span> | <span data-ttu-id="4b60b-290">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-290">string</span></span> | <span data-ttu-id="4b60b-291">Die Zeit, zu der der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-291">The time that the export was generated.</span></span> | <span data-ttu-id="4b60b-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="4b60b-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="4b60b-293">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="4b60b-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="4b60b-294">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="4b60b-295">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="4b60b-296">3. Bewertung von Software-Sicherheitsrisiken im Delta-Export (JSON-Antwort)</span><span class="sxs-lookup"><span data-stu-id="4b60b-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="4b60b-297">3.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-297">3.1 API method description</span></span>

<span data-ttu-id="4b60b-298">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId zurück.</span><span class="sxs-lookup"><span data-stu-id="4b60b-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="4b60b-299">Die API ruft Daten in Ihrer Organisation als JSON-Antworten ab.</span><span class="sxs-lookup"><span data-stu-id="4b60b-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="4b60b-300">Die Antwort ist paginiert, sodass Sie das Feld @odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="4b60b-301">Im Gegensatz zur vollständigen Bewertung von Software-Sicherheitsrisiken (JSON-Antwort), die verwendet wird, um eine vollständige Momentaufnahme der Bewertung der Softwarerisiken Ihrer Organisation nach Gerät zu erhalten, wird der JSON-Antwort-API-Aufruf für den Deltaexport verwendet, um nur die Änderungen abzurufen, die zwischen einem ausgewählten Datum und dem aktuellen Datum (dem "Delta"-API-Aufruf) aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4b60b-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="4b60b-302">Anstatt jedes Mal einen vollständigen Export mit einer großen Datenmenge zu erhalten, erhalten Sie nur spezifische Informationen zu neuen, festen und aktualisierten Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="4b60b-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="4b60b-303">Der JSON-Antwort-API-Aufruf des Deltaexports kann auch verwendet werden, um verschiedene KPIs zu berechnen, z. B. "wie viele Sicherheitsrisiken wurden behoben?"</span><span class="sxs-lookup"><span data-stu-id="4b60b-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="4b60b-304">oder "wie viele neue Sicherheitsrisiken wurden zu meiner Organisation hinzugefügt?"</span><span class="sxs-lookup"><span data-stu-id="4b60b-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="4b60b-305">Es wird dringend empfohlen, mindestens einmal pro Woche die vollständige Bewertung der Software-Sicherheitsrisiken nach Geräte-API-Aufruf zu verwenden, und diese zusätzlichen Exportsoftware-Sicherheitsrisiken ändern sich nach Geräte (Delta)-API-Aufruf alle anderen Tage der Woche.</span><span class="sxs-lookup"><span data-stu-id="4b60b-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="4b60b-306">Im Gegensatz zu den anderen JSON-Antwort-APIs für Bewertungen ist der "Deltaexport" kein vollständiger Export.</span><span class="sxs-lookup"><span data-stu-id="4b60b-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="4b60b-307">Der Deltaexport enthält nur die Änderungen, die zwischen einem ausgewählten Datum und dem aktuellen Datum (dem "Delta"-API-Aufruf) vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="4b60b-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="4b60b-308">3.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="4b60b-309">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="4b60b-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="4b60b-310">Der Parameter "sinceTime" hat maximal 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="4b60b-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="4b60b-311">Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="4b60b-312">3.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-312">3.2 Permissions</span></span>

<span data-ttu-id="4b60b-313">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4b60b-314">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4b60b-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="4b60b-315">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-315">Permission type</span></span> | <span data-ttu-id="4b60b-316">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-316">Permission</span></span> | <span data-ttu-id="4b60b-317">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4b60b-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="4b60b-318">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4b60b-318">Application</span></span> | <span data-ttu-id="4b60b-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4b60b-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="4b60b-320">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="4b60b-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="4b60b-321">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4b60b-321">Delegated (work or school account)</span></span> | <span data-ttu-id="4b60b-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4b60b-322">Vulnerability.Read</span></span> | <span data-ttu-id="4b60b-323">"Informationen zu Sicherheitsrisiken und Sicherheitsrisikoverwaltung lesen"</span><span class="sxs-lookup"><span data-stu-id="4b60b-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="4b60b-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="4b60b-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="4b60b-325">3.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="4b60b-325">3.4 Parameters</span></span>

- <span data-ttu-id="4b60b-326">sinceTime (erforderlich) – Die Daten zwischen einer ausgewählten Zeit und heute.</span><span class="sxs-lookup"><span data-stu-id="4b60b-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="4b60b-327">pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort</span><span class="sxs-lookup"><span data-stu-id="4b60b-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="4b60b-328">$top – Anzahl der zurückzugebenden Ergebnisse (gibt nicht @odata.nextLink zurück und ruft daher nicht alle Daten ab)</span><span class="sxs-lookup"><span data-stu-id="4b60b-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="4b60b-329">3.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b60b-329">3.5 Properties</span></span>

<span data-ttu-id="4b60b-330">Jeder zurückgegebene Datensatz enthält alle Daten aus der Bewertung von Software-Sicherheitsrisiken beim vollständigen Export nach Geräte-API sowie zwei zusätzliche Felder: _**EventTimestamp**_ und _**Status.**_</span><span class="sxs-lookup"><span data-stu-id="4b60b-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="4b60b-331">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="4b60b-332">Diese Spalten sind temporär und können entfernt werden. Verwenden Sie daher nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4b60b-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="4b60b-333">Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b60b-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="4b60b-334">Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="4b60b-335">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="4b60b-335">Property (ID)</span></span> | <span data-ttu-id="4b60b-336">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4b60b-336">Data type</span></span> | <span data-ttu-id="4b60b-337">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b60b-337">Description</span></span> | <span data-ttu-id="4b60b-338">Beispiel für zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="4b60b-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4b60b-339">CveId</span><span class="sxs-lookup"><span data-stu-id="4b60b-339">CveId</span></span> | <span data-ttu-id="4b60b-340">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-340">string</span></span> | <span data-ttu-id="4b60b-341">Eindeutiger Bezeichner, der dem Sicherheitsrisiko unter dem System für allgemeine Sicherheitsrisiken und Sicherheitsrisiken (CVE) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="4b60b-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="4b60b-342">CVE-2020-15992</span></span>  
<span data-ttu-id="4b60b-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="4b60b-343">CvssScore</span></span> | <span data-ttu-id="4b60b-344">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-344">string</span></span> | <span data-ttu-id="4b60b-345">Die CVSS-Bewertung des CVE.</span><span class="sxs-lookup"><span data-stu-id="4b60b-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="4b60b-346">6.2</span><span class="sxs-lookup"><span data-stu-id="4b60b-346">6.2</span></span>  
<span data-ttu-id="4b60b-347">Deviceid</span><span class="sxs-lookup"><span data-stu-id="4b60b-347">DeviceId</span></span> | <span data-ttu-id="4b60b-348">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-348">string</span></span> | <span data-ttu-id="4b60b-349">Eindeutiger Bezeichner für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="4b60b-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="4b60b-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="4b60b-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="4b60b-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="4b60b-351">DeviceName</span></span> | <span data-ttu-id="4b60b-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-352">string</span></span> | <span data-ttu-id="4b60b-353">Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="4b60b-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b60b-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="4b60b-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="4b60b-355">DiskPaths</span></span> | <span data-ttu-id="4b60b-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="4b60b-356">Array[string]</span></span> | <span data-ttu-id="4b60b-357">Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="4b60b-358">[ "C:\Programme (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="4b60b-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="4b60b-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="4b60b-359">EventTimestamp</span></span> | <span data-ttu-id="4b60b-360">String</span><span class="sxs-lookup"><span data-stu-id="4b60b-360">String</span></span> | <span data-ttu-id="4b60b-361">Die Zeit, zu der dieses Delta-Ereignis gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-361">The time this delta event was found.</span></span> | <span data-ttu-id="4b60b-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="4b60b-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="4b60b-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="4b60b-363">ExploitabilityLevel</span></span> | <span data-ttu-id="4b60b-364">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-364">string</span></span> | <span data-ttu-id="4b60b-365">Die Ausnutzbarkeitsstufe dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="4b60b-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="4b60b-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="4b60b-366">ExploitIsInKit</span></span>  
<span data-ttu-id="4b60b-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="4b60b-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="4b60b-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-368">string</span></span> | <span data-ttu-id="4b60b-369">Die CVE dieses Produkts wurde zum ersten Mal auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b60b-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="4b60b-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="4b60b-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="4b60b-371">Id</span><span class="sxs-lookup"><span data-stu-id="4b60b-371">Id</span></span> | <span data-ttu-id="4b60b-372">string</span><span class="sxs-lookup"><span data-stu-id="4b60b-372">string</span></span> | <span data-ttu-id="4b60b-373">Eindeutiger Bezeichner für den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="4b60b-373">Unique identifier for the record.</span></span> | <span data-ttu-id="4b60b-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="4b60b-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="4b60b-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="4b60b-375">LastSeenTimestamp</span></span> | <span data-ttu-id="4b60b-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-376">string</span></span> | <span data-ttu-id="4b60b-377">Das letzte Mal, als das CVE auf dem Gerät angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="4b60b-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="4b60b-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="4b60b-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="4b60b-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="4b60b-379">OSPlatform</span></span> | <span data-ttu-id="4b60b-380">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-380">string</span></span> | <span data-ttu-id="4b60b-381">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b60b-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4b60b-382">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4b60b-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="4b60b-383">Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="4b60b-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="4b60b-384">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b60b-384">Windows10</span></span>  
<span data-ttu-id="4b60b-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="4b60b-385">RbacGroupName</span></span> | <span data-ttu-id="4b60b-386">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-386">string</span></span> | <span data-ttu-id="4b60b-387">Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4b60b-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="4b60b-388">Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen".</span><span class="sxs-lookup"><span data-stu-id="4b60b-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="4b60b-389">Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="4b60b-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="4b60b-390">Server</span><span class="sxs-lookup"><span data-stu-id="4b60b-390">Servers</span></span>  
<span data-ttu-id="4b60b-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="4b60b-391">RecommendationReference</span></span> | <span data-ttu-id="4b60b-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-392">string</span></span> | <span data-ttu-id="4b60b-393">Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.</span><span class="sxs-lookup"><span data-stu-id="4b60b-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="4b60b-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="4b60b-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="4b60b-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="4b60b-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="4b60b-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-396">string</span></span> | <span data-ttu-id="4b60b-397">Name oder Beschreibung des sicherheitsrelevanten Updates, das vom Softwareanbieter bereitgestellt wurde, um die Sicherheitsanfälligkeit zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4b60b-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="4b60b-398">Sicherheitsupdates vom April 2020</span><span class="sxs-lookup"><span data-stu-id="4b60b-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="4b60b-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="4b60b-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="4b60b-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-400">string</span></span> | <span data-ttu-id="4b60b-401">Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel</span><span class="sxs-lookup"><span data-stu-id="4b60b-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="4b60b-402">4550961</span><span class="sxs-lookup"><span data-stu-id="4b60b-402">4550961</span></span>  
<span data-ttu-id="4b60b-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="4b60b-403">RegistryPaths</span></span>  | <span data-ttu-id="4b60b-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="4b60b-404">Array[string]</span></span> | <span data-ttu-id="4b60b-405">Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4b60b-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="4b60b-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="4b60b-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="4b60b-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="4b60b-407">SoftwareName</span></span> | <span data-ttu-id="4b60b-408">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-408">string</span></span> | <span data-ttu-id="4b60b-409">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-409">Name of the software product.</span></span> | <span data-ttu-id="4b60b-410">Chrome</span><span class="sxs-lookup"><span data-stu-id="4b60b-410">chrome</span></span>  
<span data-ttu-id="4b60b-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="4b60b-411">SoftwareVendor</span></span> | <span data-ttu-id="4b60b-412">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-412">string</span></span> | <span data-ttu-id="4b60b-413">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="4b60b-413">Name of the software vendor.</span></span> | <span data-ttu-id="4b60b-414">Google</span><span class="sxs-lookup"><span data-stu-id="4b60b-414">google</span></span>  
<span data-ttu-id="4b60b-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="4b60b-415">SoftwareVersion</span></span> | <span data-ttu-id="4b60b-416">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-416">string</span></span> | <span data-ttu-id="4b60b-417">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="4b60b-417">Version number of the software product.</span></span> | <span data-ttu-id="4b60b-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="4b60b-418">81.0.4044.138</span></span>  
<span data-ttu-id="4b60b-419">Status</span><span class="sxs-lookup"><span data-stu-id="4b60b-419">Status</span></span> | <span data-ttu-id="4b60b-420">String</span><span class="sxs-lookup"><span data-stu-id="4b60b-420">String</span></span> | <span data-ttu-id="4b60b-421">**Neu**   (für eine neue Sicherheitslücke, die auf einem Gerät eingeführt wurde)  (1) **Behoben**   (wenn diese Sicherheitslücke nicht mehr auf dem Gerät vorhanden ist, was bedeutet, dass sie behoben wurde).</span><span class="sxs-lookup"><span data-stu-id="4b60b-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="4b60b-422">(2)  **Aktualisiert**   (Wenn sich eine Sicherheitslücke auf einem Gerät geändert hat.</span><span class="sxs-lookup"><span data-stu-id="4b60b-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="4b60b-423">Die möglichen Änderungen sind: CVSS-Bewertung, Ausnutzbarkeitsgrad, Schweregrad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="4b60b-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="4b60b-424">Fest</span><span class="sxs-lookup"><span data-stu-id="4b60b-424">Fixed</span></span>
<span data-ttu-id="4b60b-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="4b60b-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="4b60b-426">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4b60b-426">string</span></span> | <span data-ttu-id="4b60b-427">Schweregrad, der dem Sicherheitsrisiko zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="4b60b-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="4b60b-428">Mittel</span><span class="sxs-lookup"><span data-stu-id="4b60b-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="4b60b-429">Klarstellungen</span><span class="sxs-lookup"><span data-stu-id="4b60b-429">Clarifications</span></span>

- <span data-ttu-id="4b60b-430">Wenn die Software von Version 1.0 auf Version 2.0 aktualisiert wurde und beide Versionen für CVE-A verfügbar gemacht werden, erhalten Sie zwei separate Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="4b60b-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="4b60b-431">Behoben – CVE-A in Version 1.0 wurde behoben</span><span class="sxs-lookup"><span data-stu-id="4b60b-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="4b60b-432">Neu – CVE-A in Version 2.0 wurde hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="4b60b-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="4b60b-433">Wenn eine bestimmte Sicherheitslücke (z. B. CVE-A) zu einem bestimmten Zeitpunkt (z. B. am 10. Januar) auf Software mit Version 1.0 angezeigt wurde und diese Software ein paar Tage später auf Version 2.0 aktualisiert wurde, die ebenfalls für die gleiche CVE-A verfügbar gemacht wurde, erhalten Sie diese beiden getrennten Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="4b60b-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="4b60b-434">Behoben – CVE-X, FirstSeenTimestamp 10. Januar, Version 1,0.</span><span class="sxs-lookup"><span data-stu-id="4b60b-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="4b60b-435">Neu – CVE-X, FirstSeenTimestamp 10. Januar, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="4b60b-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="4b60b-436">3.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="4b60b-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="4b60b-437">3.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="4b60b-438">3.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b60b-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="4b60b-439">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b60b-439">See also</span></span>

- [<span data-ttu-id="4b60b-440">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4b60b-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="4b60b-441">Exportieren der Bewertung der sicheren Konfiguration pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4b60b-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="4b60b-442">Exportieren der Softwareinventarisierungsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4b60b-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="4b60b-443">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="4b60b-443">Other related</span></span>

- [<span data-ttu-id="4b60b-444">Risikobasierte bedrohungsbasierte & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="4b60b-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="4b60b-445">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4b60b-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
