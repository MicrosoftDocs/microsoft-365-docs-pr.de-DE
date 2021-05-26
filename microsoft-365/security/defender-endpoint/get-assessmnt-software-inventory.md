---
title: Exportieren der Softwareinventarbewertung pro Gerät
description: Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.
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
ms.openlocfilehash: ecfeaa10eda6b3832b7196c0598d6584783bb5ff
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653650"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="f87f2-104">Exportieren der Softwareinventarbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="f87f2-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f87f2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f87f2-105">**Applies to:**</span></span>

- [<span data-ttu-id="f87f2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f87f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f87f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f87f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f87f2-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f87f2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f87f2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f87f2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="f87f2-110">Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="f87f2-111">Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten zum Abrufen:</span><span class="sxs-lookup"><span data-stu-id="f87f2-111">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="f87f2-112">**OData**  Die API verwendet alle Daten in Ihrer Organisation als Json-Antworten nach dem OData-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="f87f2-112">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="f87f2-113">Diese Methode ist am besten für _kleine Organisationen mit weniger als 100 K Geräten._</span><span class="sxs-lookup"><span data-stu-id="f87f2-113">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="f87f2-114">Die Antwort wird paginiert, sodass Sie das odata.nextLink-Feld aus der Antwort verwenden können, \@ um die nächsten Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="f87f2-115">**über Dateien** Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="f87f2-115">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="f87f2-116">Daher wird es für große Organisationen mit mehr als 100 K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f87f2-116">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="f87f2-117">Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien.</span><span class="sxs-lookup"><span data-stu-id="f87f2-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="f87f2-118">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="f87f2-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="f87f2-119">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="f87f2-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="f87f2-120">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="f87f2-121">Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.</span><span class="sxs-lookup"><span data-stu-id="f87f2-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="f87f2-122">Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-122">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="f87f2-123">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="f87f2-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="f87f2-124">Sofern nicht anders angegeben, sind \*\*\*\* alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**</span><span class="sxs-lookup"><span data-stu-id="f87f2-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="f87f2-125">1. Export software inventory assessment (OData)</span><span class="sxs-lookup"><span data-stu-id="f87f2-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="f87f2-126">Beschreibung der 1.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="f87f2-126">1.1 API method description</span></span>

<span data-ttu-id="f87f2-127">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="f87f2-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f87f2-128">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.</span><span class="sxs-lookup"><span data-stu-id="f87f2-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="f87f2-129">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f87f2-129">Limitations</span></span>

- <span data-ttu-id="f87f2-130">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="f87f2-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="f87f2-131">Die Tarifeinschränkungen für diese API sind 30 Anrufe pro Minute und 1000 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f87f2-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="f87f2-132">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f87f2-132">1.2 Permissions</span></span>

<span data-ttu-id="f87f2-133">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f87f2-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f87f2-134">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f87f2-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="f87f2-135">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f87f2-135">Permission type</span></span> | <span data-ttu-id="f87f2-136">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f87f2-136">Permission</span></span> | <span data-ttu-id="f87f2-137">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f87f2-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="f87f2-138">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f87f2-138">Application</span></span> | <span data-ttu-id="f87f2-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="f87f2-139">Software.Read.All</span></span> | <span data-ttu-id="f87f2-140">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="f87f2-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f87f2-141">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f87f2-141">Delegated (work or school account)</span></span> | <span data-ttu-id="f87f2-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="f87f2-142">Software.Read</span></span> | <span data-ttu-id="f87f2-143">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="f87f2-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="f87f2-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="f87f2-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="f87f2-145">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="f87f2-145">1.4 Parameters</span></span>

- <span data-ttu-id="f87f2-146">pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort.</span><span class="sxs-lookup"><span data-stu-id="f87f2-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="f87f2-147">$top – Anzahl der zurückzukehrende Ergebnisse (gibt @odata.nextLink nicht zurück und zieht daher nicht alle Daten zurück)</span><span class="sxs-lookup"><span data-stu-id="f87f2-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="f87f2-148">1.5 Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f87f2-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="f87f2-149">-Jeder Datensatz beträgt ca. 0,5 KB Daten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="f87f2-150">Berücksichtigen Sie dies bei der Auswahl des richtigen pageSize-Parameters für Sie.</span><span class="sxs-lookup"><span data-stu-id="f87f2-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="f87f2-151">-Die in der folgenden Tabelle definierten Eigenschaften werden alphanumerisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f87f2-151">-The properties defined in the following table are listed alphanumerically, by property ID.</span></span> <span data-ttu-id="f87f2-152">Beim Ausführen dieser API wird die resultierende Ausgabe nicht unbedingt in der in diesen Tabellen aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f87f2-152">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
><span data-ttu-id="f87f2-153">-Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f87f2-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="f87f2-154">Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="f87f2-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="f87f2-155">Property (id)</span><span class="sxs-lookup"><span data-stu-id="f87f2-155">Property (id)</span></span> | <span data-ttu-id="f87f2-156">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f87f2-156">Data type</span></span> | <span data-ttu-id="f87f2-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f87f2-157">Description</span></span> | <span data-ttu-id="f87f2-158">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="f87f2-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f87f2-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f87f2-159">DeviceId</span></span> | <span data-ttu-id="f87f2-160">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-160">string</span></span> | <span data-ttu-id="f87f2-161">Eindeutige ID für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="f87f2-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="f87f2-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="f87f2-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="f87f2-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="f87f2-163">DeviceName</span></span> | <span data-ttu-id="f87f2-164">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-164">string</span></span> | <span data-ttu-id="f87f2-165">Vollqualifizierter Domänenname (FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="f87f2-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="f87f2-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f87f2-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="f87f2-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="f87f2-167">DiskPaths</span></span> | <span data-ttu-id="f87f2-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="f87f2-168">Array[string]</span></span>  | <span data-ttu-id="f87f2-169">Datenträgerbeweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f87f2-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="f87f2-170">[ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="f87f2-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="f87f2-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="f87f2-171">EndOfSupportDate</span></span> | <span data-ttu-id="f87f2-172">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-172">string</span></span> | <span data-ttu-id="f87f2-173">Das Datum, an dem die Unterstützung für diese Software endet.</span><span class="sxs-lookup"><span data-stu-id="f87f2-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="f87f2-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="f87f2-174">2020-12-30</span></span>
<span data-ttu-id="f87f2-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="f87f2-175">EndOfSupportStatus</span></span> | <span data-ttu-id="f87f2-176">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-176">string</span></span> | <span data-ttu-id="f87f2-177">Ende des Supportstatus.</span><span class="sxs-lookup"><span data-stu-id="f87f2-177">End of support status.</span></span> <span data-ttu-id="f87f2-178">Kann die folgenden möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span><span class="sxs-lookup"><span data-stu-id="f87f2-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="f87f2-179">Bevorstehende EOS</span><span class="sxs-lookup"><span data-stu-id="f87f2-179">Upcoming EOS</span></span>
<span data-ttu-id="f87f2-180">Id</span><span class="sxs-lookup"><span data-stu-id="f87f2-180">Id</span></span> | <span data-ttu-id="f87f2-181">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-181">string</span></span> | <span data-ttu-id="f87f2-182">Eindeutige ID für den Datensatz.</span><span class="sxs-lookup"><span data-stu-id="f87f2-182">Unique identifier for the record.</span></span> | <span data-ttu-id="f87f2-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="f87f2-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="f87f2-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="f87f2-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="f87f2-185">int</span><span class="sxs-lookup"><span data-stu-id="f87f2-185">int</span></span> | <span data-ttu-id="f87f2-186">Anzahl der Schwachstellen dieser Software auf diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="f87f2-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="f87f2-187">3</span><span class="sxs-lookup"><span data-stu-id="f87f2-187">3</span></span>
<span data-ttu-id="f87f2-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="f87f2-188">OSPlatform</span></span> | <span data-ttu-id="f87f2-189">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-189">string</span></span> | <span data-ttu-id="f87f2-190">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f87f2-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f87f2-191">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f87f2-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="f87f2-192">Weitere Informationen finden Sie unter tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="f87f2-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="f87f2-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="f87f2-193">Windows10</span></span>
<span data-ttu-id="f87f2-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f87f2-194">RbacGroupName</span></span> | <span data-ttu-id="f87f2-195">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-195">string</span></span> | <span data-ttu-id="f87f2-196">Die rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="f87f2-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="f87f2-197">Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f87f2-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="f87f2-198">Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="f87f2-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="f87f2-199">Server</span><span class="sxs-lookup"><span data-stu-id="f87f2-199">Servers</span></span>
<span data-ttu-id="f87f2-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="f87f2-200">RegistryPaths</span></span> | <span data-ttu-id="f87f2-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="f87f2-201">Array[string]</span></span> | <span data-ttu-id="f87f2-202">Registrierungsbeweis, dass das Produkt auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f87f2-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="f87f2-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ \\ Deinstallieren von Microsoft Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="f87f2-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="f87f2-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="f87f2-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="f87f2-205">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-205">string</span></span> | <span data-ttu-id="f87f2-206">Das erste Mal, dass diese Software auf dem Gerät angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="f87f2-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="f87f2-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="f87f2-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="f87f2-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="f87f2-208">SoftwareName</span></span> | <span data-ttu-id="f87f2-209">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-209">string</span></span> | <span data-ttu-id="f87f2-210">Name des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="f87f2-210">Name of the software product.</span></span> | <span data-ttu-id="f87f2-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="f87f2-211">Silverlight</span></span>
<span data-ttu-id="f87f2-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="f87f2-212">SoftwareVendor</span></span> | <span data-ttu-id="f87f2-213">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-213">string</span></span> | <span data-ttu-id="f87f2-214">Name des Softwareanbieters.</span><span class="sxs-lookup"><span data-stu-id="f87f2-214">Name of the software vendor.</span></span> | <span data-ttu-id="f87f2-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="f87f2-215">microsoft</span></span>
<span data-ttu-id="f87f2-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="f87f2-216">SoftwareVersion</span></span> | <span data-ttu-id="f87f2-217">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-217">string</span></span> | <span data-ttu-id="f87f2-218">Versionsnummer des Softwareprodukts.</span><span class="sxs-lookup"><span data-stu-id="f87f2-218">Version number of the software product.</span></span> | <span data-ttu-id="f87f2-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="f87f2-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="f87f2-220">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="f87f2-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="f87f2-221">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="f87f2-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="f87f2-222">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="f87f2-222">1.6.2 Response example</span></span>

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

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="f87f2-223">2. Exportieren der Softwareinventarbewertung (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="f87f2-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="f87f2-224">Beschreibung der 2.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="f87f2-224">2.1 API method description</span></span>

<span data-ttu-id="f87f2-225">Diese API-Antwort enthält alle Daten der installierten Software pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="f87f2-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="f87f2-226">Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.</span><span class="sxs-lookup"><span data-stu-id="f87f2-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="f87f2-227">2.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f87f2-227">2.1.1 Limitations</span></span>

<span data-ttu-id="f87f2-228">Die Tarifeinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="f87f2-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="f87f2-229">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f87f2-229">2.2 Permissions</span></span>

<span data-ttu-id="f87f2-230">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f87f2-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f87f2-231">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f87f2-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="f87f2-232">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="f87f2-232">Permission type</span></span> | <span data-ttu-id="f87f2-233">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f87f2-233">Permission</span></span> | <span data-ttu-id="f87f2-234">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="f87f2-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="f87f2-235">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f87f2-235">Application</span></span> | <span data-ttu-id="f87f2-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="f87f2-236">Software.Read.All</span></span> | <span data-ttu-id="f87f2-237">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="f87f2-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="f87f2-238">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="f87f2-238">Delegated (work or school account)</span></span> | <span data-ttu-id="f87f2-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="f87f2-239">Software.Read</span></span> | <span data-ttu-id="f87f2-240">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="f87f2-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="f87f2-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="f87f2-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="f87f2-242">Parameter</span><span class="sxs-lookup"><span data-stu-id="f87f2-242">Parameters</span></span>

- <span data-ttu-id="f87f2-243">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (Maximal 24 Stunden)</span><span class="sxs-lookup"><span data-stu-id="f87f2-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="f87f2-244">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f87f2-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="f87f2-245">Die Dateien sind gzip-komprimierte & im mehrstufigen Json-Format.</span><span class="sxs-lookup"><span data-stu-id="f87f2-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="f87f2-246">Die Download-URLs sind nur für 3 Stunden gültig.</span><span class="sxs-lookup"><span data-stu-id="f87f2-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="f87f2-247">Andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="f87f2-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="f87f2-248">_ Für die maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie aus derselben Azure-Region heruntergeladen werden, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="f87f2-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="f87f2-249">Property (id)</span><span class="sxs-lookup"><span data-stu-id="f87f2-249">Property (id)</span></span> | <span data-ttu-id="f87f2-250">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f87f2-250">Data type</span></span> | <span data-ttu-id="f87f2-251">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f87f2-251">Description</span></span> | <span data-ttu-id="f87f2-252">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="f87f2-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f87f2-253">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="f87f2-253">Export files</span></span> | <span data-ttu-id="f87f2-254">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="f87f2-254">array\[string\]</span></span> | <span data-ttu-id="f87f2-255">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten</span><span class="sxs-lookup"><span data-stu-id="f87f2-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="f87f2-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="f87f2-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="f87f2-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="f87f2-257">GeneratedTime</span></span> | <span data-ttu-id="f87f2-258">string</span><span class="sxs-lookup"><span data-stu-id="f87f2-258">string</span></span> | <span data-ttu-id="f87f2-259">Der Zeitpunkt, zu dem der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f87f2-259">The time that the export was generated.</span></span> | <span data-ttu-id="f87f2-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="f87f2-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="f87f2-261">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="f87f2-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="f87f2-262">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="f87f2-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="f87f2-263">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="f87f2-263">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f87f2-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f87f2-264">See also</span></span>

- [<span data-ttu-id="f87f2-265">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="f87f2-265">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="f87f2-266">Exportieren einer sicheren Konfigurationsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="f87f2-266">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="f87f2-267">Exportieren der Bewertung von Softwarerisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="f87f2-267">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="f87f2-268">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="f87f2-268">Other related</span></span>

- [<span data-ttu-id="f87f2-269">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="f87f2-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f87f2-270">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f87f2-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
