---
title: Exportieren der Softwareinventarisierungsbewertung pro Gerät
description: Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.
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
ms.openlocfilehash: 639f850119498222684c4b3804b32a29dda3eac4
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022882"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="a2afe-104">Exportieren der Softwareinventarisierungsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="a2afe-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2afe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a2afe-105">**Applies to:**</span></span>

- [<span data-ttu-id="a2afe-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a2afe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2afe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2afe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a2afe-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="a2afe-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a2afe-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="a2afe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="a2afe-110">Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="a2afe-111">Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:</span><span class="sxs-lookup"><span data-stu-id="a2afe-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="a2afe-112">[Exportieren der **JSON-Antwort zur** Softwareinventarbewertung](#1-export-software-inventory-assessment-json-response) Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten ab.</span><span class="sxs-lookup"><span data-stu-id="a2afe-112">[Export software inventory assessment **JSON response**](#1-export-software-inventory-assessment-json-response) The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="a2afe-113">Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100-K-Geräten._</span><span class="sxs-lookup"><span data-stu-id="a2afe-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="a2afe-114">Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="a2afe-115">Exportieren der [Softwareinventarisierungsbewertung **über Dateien**](#2-export-software-inventory-assessment-via-files)  Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="a2afe-116">Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="a2afe-117">Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab.</span><span class="sxs-lookup"><span data-stu-id="a2afe-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="a2afe-118">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="a2afe-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="a2afe-119">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="a2afe-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="a2afe-120">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="a2afe-121">Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="a2afe-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="a2afe-122">Daten, die gesammelt werden (entweder mit _OData_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="a2afe-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="a2afe-123">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="a2afe-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="a2afe-124">Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="a2afe-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-json-response"></a><span data-ttu-id="a2afe-125">1. Exportieren der Softwareinventarisierungsbewertung (JSON-Antwort)</span><span class="sxs-lookup"><span data-stu-id="a2afe-125">1. Export software inventory assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="a2afe-126">1.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a2afe-126">1.1 API method description</span></span>

<span data-ttu-id="a2afe-127">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="a2afe-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="a2afe-128">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.</span><span class="sxs-lookup"><span data-stu-id="a2afe-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="a2afe-129">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a2afe-129">Limitations</span></span>

- <span data-ttu-id="a2afe-130">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="a2afe-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="a2afe-131">Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a2afe-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="a2afe-132">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a2afe-132">1.2 Permissions</span></span>

<span data-ttu-id="a2afe-133">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a2afe-134">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a2afe-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a2afe-135">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a2afe-135">Permission type</span></span> | <span data-ttu-id="a2afe-136">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2afe-136">Permission</span></span> | <span data-ttu-id="a2afe-137">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2afe-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="a2afe-138">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a2afe-138">Application</span></span> | <span data-ttu-id="a2afe-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a2afe-139">Software.Read.All</span></span> | <span data-ttu-id="a2afe-140">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="a2afe-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a2afe-141">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a2afe-141">Delegated (work or school account)</span></span> | <span data-ttu-id="a2afe-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a2afe-142">Software.Read</span></span> | <span data-ttu-id="a2afe-143">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="a2afe-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="a2afe-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="a2afe-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="a2afe-145">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="a2afe-145">1.4 Parameters</span></span>

- <span data-ttu-id="a2afe-146">pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort.</span><span class="sxs-lookup"><span data-stu-id="a2afe-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="a2afe-147">$top – Anzahl der zurückzugebenden Ergebnisse (gibt nicht @odata.nextLink zurück und ruft daher nicht alle Daten ab)</span><span class="sxs-lookup"><span data-stu-id="a2afe-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="a2afe-148">1.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a2afe-148">1.5 Properties</span></span>

>[!NOTE]
>
>- <span data-ttu-id="a2afe-149">Jeder Datensatz hat ca. 0,5 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="a2afe-149">Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="a2afe-150">Berücksichtigen Sie dies, wenn Sie den richtigen pageSize-Parameter für Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="a2afe-151">Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a2afe-151">The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="a2afe-152">Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2afe-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="a2afe-153">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2afe-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="a2afe-154">Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="a2afe-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<br/>

<span data-ttu-id="a2afe-155">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="a2afe-155">Property (ID)</span></span> | <span data-ttu-id="a2afe-156">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a2afe-156">Data type</span></span> | <span data-ttu-id="a2afe-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2afe-157">Description</span></span> | <span data-ttu-id="a2afe-158">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="a2afe-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a2afe-159">Deviceid</span><span class="sxs-lookup"><span data-stu-id="a2afe-159">DeviceId</span></span> | <span data-ttu-id="a2afe-160">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-160">string</span></span> | <span data-ttu-id="a2afe-161">Eindeutiger Bezeichner für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="a2afe-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="a2afe-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="a2afe-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="a2afe-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="a2afe-163">DeviceName</span></span> | <span data-ttu-id="a2afe-164">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-164">string</span></span> | <span data-ttu-id="a2afe-165">Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="a2afe-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="a2afe-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a2afe-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="a2afe-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="a2afe-167">DiskPaths</span></span> | <span data-ttu-id="a2afe-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="a2afe-168">Array[string]</span></span>  | <span data-ttu-id="a2afe-169">Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a2afe-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="a2afe-170">[ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight Application \\ \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="a2afe-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="a2afe-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="a2afe-171">EndOfSupportDate</span></span> | <span data-ttu-id="a2afe-172">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-172">string</span></span> | <span data-ttu-id="a2afe-173">Das Datum, an dem die Unterstützung für diese Software endet oder endet.</span><span class="sxs-lookup"><span data-stu-id="a2afe-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="a2afe-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="a2afe-174">2020-12-30</span></span>
<span data-ttu-id="a2afe-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="a2afe-175">EndOfSupportStatus</span></span> | <span data-ttu-id="a2afe-176">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-176">string</span></span> | <span data-ttu-id="a2afe-177">Ende des Supportstatus.</span><span class="sxs-lookup"><span data-stu-id="a2afe-177">End of support status.</span></span> <span data-ttu-id="a2afe-178">Kann diese möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span><span class="sxs-lookup"><span data-stu-id="a2afe-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="a2afe-179">Bevorstehende EOS</span><span class="sxs-lookup"><span data-stu-id="a2afe-179">Upcoming EOS</span></span>
<span data-ttu-id="a2afe-180">Id</span><span class="sxs-lookup"><span data-stu-id="a2afe-180">Id</span></span> | <span data-ttu-id="a2afe-181">string</span><span class="sxs-lookup"><span data-stu-id="a2afe-181">string</span></span> | <span data-ttu-id="a2afe-182">Eindeutiger Bezeichner für den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="a2afe-182">Unique identifier for the record.</span></span> | <span data-ttu-id="a2afe-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="a2afe-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="a2afe-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="a2afe-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="a2afe-185">int</span><span class="sxs-lookup"><span data-stu-id="a2afe-185">int</span></span> | <span data-ttu-id="a2afe-186">Anzahl der Schwachstellen dieser Software auf diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="a2afe-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="a2afe-187">3</span><span class="sxs-lookup"><span data-stu-id="a2afe-187">3</span></span>
<span data-ttu-id="a2afe-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="a2afe-188">OSPlatform</span></span> | <span data-ttu-id="a2afe-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-189">string</span></span> | <span data-ttu-id="a2afe-190">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a2afe-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a2afe-191">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a2afe-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="a2afe-192">Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="a2afe-193">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a2afe-193">Windows10</span></span>
<span data-ttu-id="a2afe-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="a2afe-194">RbacGroupName</span></span> | <span data-ttu-id="a2afe-195">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-195">string</span></span> | <span data-ttu-id="a2afe-196">Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a2afe-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="a2afe-197">Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen".</span><span class="sxs-lookup"><span data-stu-id="a2afe-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="a2afe-198">Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="a2afe-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="a2afe-199">Server</span><span class="sxs-lookup"><span data-stu-id="a2afe-199">Servers</span></span>
<span data-ttu-id="a2afe-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="a2afe-200">RegistryPaths</span></span> | <span data-ttu-id="a2afe-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="a2afe-201">Array[string]</span></span> | <span data-ttu-id="a2afe-202">Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a2afe-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="a2afe-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="a2afe-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="a2afe-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="a2afe-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="a2afe-205">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-205">string</span></span> | <span data-ttu-id="a2afe-206">Diese Software wurde zum ersten Mal auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2afe-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="a2afe-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="a2afe-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="a2afe-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="a2afe-208">SoftwareName</span></span> | <span data-ttu-id="a2afe-209">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-209">string</span></span> | <span data-ttu-id="a2afe-210">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="a2afe-210">Name of the software product.</span></span> | <span data-ttu-id="a2afe-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="a2afe-211">Silverlight</span></span>
<span data-ttu-id="a2afe-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="a2afe-212">SoftwareVendor</span></span> | <span data-ttu-id="a2afe-213">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-213">string</span></span> | <span data-ttu-id="a2afe-214">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="a2afe-214">Name of the software vendor.</span></span> | <span data-ttu-id="a2afe-215">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2afe-215">microsoft</span></span>
<span data-ttu-id="a2afe-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="a2afe-216">SoftwareVersion</span></span> | <span data-ttu-id="a2afe-217">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-217">string</span></span> | <span data-ttu-id="a2afe-218">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="a2afe-218">Version number of the software product.</span></span> | <span data-ttu-id="a2afe-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="a2afe-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="a2afe-220">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="a2afe-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="a2afe-221">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="a2afe-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="a2afe-222">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="a2afe-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="a2afe-223">2. Exportieren der Softwareinventarbewertung (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="a2afe-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="a2afe-224">2.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a2afe-224">2.1 API method description</span></span>

<span data-ttu-id="a2afe-225">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="a2afe-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="a2afe-226">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.</span><span class="sxs-lookup"><span data-stu-id="a2afe-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="a2afe-227">2.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a2afe-227">2.1.1 Limitations</span></span>

<span data-ttu-id="a2afe-228">Die Rateneinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="a2afe-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="a2afe-229">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a2afe-229">2.2 Permissions</span></span>

<span data-ttu-id="a2afe-230">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a2afe-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a2afe-231">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a2afe-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a2afe-232">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a2afe-232">Permission type</span></span> | <span data-ttu-id="a2afe-233">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2afe-233">Permission</span></span> | <span data-ttu-id="a2afe-234">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2afe-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="a2afe-235">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a2afe-235">Application</span></span> | <span data-ttu-id="a2afe-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a2afe-236">Software.Read.All</span></span> | <span data-ttu-id="a2afe-237">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="a2afe-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a2afe-238">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a2afe-238">Delegated (work or school account)</span></span> | <span data-ttu-id="a2afe-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a2afe-239">Software.Read</span></span> | <span data-ttu-id="a2afe-240">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="a2afe-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="a2afe-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="a2afe-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="a2afe-242">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2afe-242">Parameters</span></span>

- <span data-ttu-id="a2afe-243">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (maximal 24 Stunden)</span><span class="sxs-lookup"><span data-stu-id="a2afe-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="a2afe-244">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a2afe-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="a2afe-245">Die Dateien werden im mehrzeiligen JSON-Format & gzipkomprimiert.</span><span class="sxs-lookup"><span data-stu-id="a2afe-245">The files are gzip compressed & in multiline JSON format.</span></span>
>
>- <span data-ttu-id="a2afe-246">Die Download-URLs sind nur 3 Stunden gültig.</span><span class="sxs-lookup"><span data-stu-id="a2afe-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="a2afe-247">Andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2afe-247">Otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="a2afe-248">Für eine maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie aus derselben Azure-Region herunterladen, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="a2afe-248">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>

<br/><br/>

<span data-ttu-id="a2afe-249">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="a2afe-249">Property (ID)</span></span> | <span data-ttu-id="a2afe-250">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a2afe-250">Data type</span></span> | <span data-ttu-id="a2afe-251">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2afe-251">Description</span></span> | <span data-ttu-id="a2afe-252">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="a2afe-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a2afe-253">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="a2afe-253">Export files</span></span> | <span data-ttu-id="a2afe-254">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="a2afe-254">array\[string\]</span></span> | <span data-ttu-id="a2afe-255">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten</span><span class="sxs-lookup"><span data-stu-id="a2afe-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="a2afe-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="a2afe-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="a2afe-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="a2afe-257">GeneratedTime</span></span> | <span data-ttu-id="a2afe-258">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2afe-258">string</span></span> | <span data-ttu-id="a2afe-259">Die Zeit, zu der der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a2afe-259">The time that the export was generated.</span></span> | <span data-ttu-id="a2afe-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="a2afe-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="a2afe-261">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="a2afe-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="a2afe-262">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="a2afe-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="a2afe-263">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="a2afe-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="a2afe-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2afe-264">See also</span></span>

- [<span data-ttu-id="a2afe-265">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="a2afe-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="a2afe-266">Exportieren der Bewertung der sicheren Konfiguration pro Gerät</span><span class="sxs-lookup"><span data-stu-id="a2afe-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="a2afe-267">Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="a2afe-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="a2afe-268">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="a2afe-268">Other related</span></span>

- [<span data-ttu-id="a2afe-269">Risikobasierte bedrohungsbasierte & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="a2afe-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a2afe-270">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a2afe-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
