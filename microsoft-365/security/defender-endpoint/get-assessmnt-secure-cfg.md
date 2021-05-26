---
title: Exportieren einer sicheren Konfigurationsbewertung pro Gerät
description: Gibt einen Eintrag für jede eindeutige Kombination von DeviceId, ConfigurationId zurück.
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
ms.openlocfilehash: f2e20415cb64903e8dfe2c82646c1970036b8f6b
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653645"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="286df-104">Exportieren einer sicheren Konfigurationsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="286df-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="286df-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="286df-105">**Applies to:**</span></span>

- [<span data-ttu-id="286df-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="286df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="286df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="286df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="286df-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="286df-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="286df-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="286df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="286df-110">Gibt alle Konfigurationen und deren Status auf Gerätebasis zurück.</span><span class="sxs-lookup"><span data-stu-id="286df-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="286df-111">Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="286df-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="286df-112">Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten zum Abrufen:</span><span class="sxs-lookup"><span data-stu-id="286df-112">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="286df-113">**OData**  Die API verwendet alle Daten in Ihrer Organisation als Json-Antworten nach dem OData-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="286df-113">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="286df-114">Diese Methode ist am besten für _kleine Organisationen mit weniger als 100K-Geräten._</span><span class="sxs-lookup"><span data-stu-id="286df-114">This method is best for _small organizations with less than 100K devices_.</span></span> <span data-ttu-id="286df-115">Die Antwort wird paginiert, sodass Sie das odata.nextLink-Feld aus der Antwort verwenden können, \@ um die nächsten Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="286df-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="286df-116">**über Dateien** Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="286df-116">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="286df-117">Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="286df-117">Therefore, it is recommended for large organizations, with more than 100K devices.</span></span> <span data-ttu-id="286df-118">Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien.</span><span class="sxs-lookup"><span data-stu-id="286df-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="286df-119">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="286df-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="286df-120">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="286df-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="286df-121">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="286df-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="286df-122">Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.</span><span class="sxs-lookup"><span data-stu-id="286df-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="286df-123">Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="286df-123">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="286df-124">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="286df-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="286df-125">Sofern nicht anders angegeben, sind \*\*\*\* alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**</span><span class="sxs-lookup"><span data-stu-id="286df-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="286df-126">1. Export secure configuration assessment (OData)</span><span class="sxs-lookup"><span data-stu-id="286df-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="286df-127">Beschreibung der 1.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="286df-127">1.1 API method description</span></span>

<span data-ttu-id="286df-128">Diese API-Antwort enthält die Secure Configuration Assessment auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination von DeviceId, ConfigurationId zurück.</span><span class="sxs-lookup"><span data-stu-id="286df-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="286df-129">1.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="286df-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="286df-130">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="286df-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="286df-131">Die Tarifeinschränkungen für diese API sind 30 Anrufe pro Minute und 1000 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="286df-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="286df-132">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="286df-132">1.2 Permissions</span></span>

<span data-ttu-id="286df-133">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="286df-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="286df-134">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for Details.</span><span class="sxs-lookup"><span data-stu-id="286df-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="286df-135">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="286df-135">Permission type</span></span> | <span data-ttu-id="286df-136">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="286df-136">Permission</span></span> | <span data-ttu-id="286df-137">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="286df-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="286df-138">Anwendung</span><span class="sxs-lookup"><span data-stu-id="286df-138">Application</span></span> | <span data-ttu-id="286df-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="286df-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="286df-140">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="286df-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="286df-141">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="286df-141">Delegated (work or school account)</span></span> | <span data-ttu-id="286df-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="286df-142">Vulnerability.Read</span></span> | <span data-ttu-id="286df-143">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="286df-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="286df-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="286df-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="286df-145">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="286df-145">1.4 Parameters</span></span>

- <span data-ttu-id="286df-146">pageSize \( default = 50.000 \) – Anzahl der Ergebnisse als Antwort</span><span class="sxs-lookup"><span data-stu-id="286df-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="286df-147">\$top – Die Anzahl der zurückzukehrende Ergebnisse gibt \( nicht odata.nextLink zurück und zieht daher nicht \@ alle Daten ab.\)</span><span class="sxs-lookup"><span data-stu-id="286df-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="286df-148">1.5 Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="286df-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="286df-149">Die in der folgenden Tabelle definierten Eigenschaften werden alphanumerisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="286df-149">The properties defined in the following table are listed alphanumerically, by property ID.</span></span>  <span data-ttu-id="286df-150">Beim Ausführen dieser API wird die resultierende Ausgabe nicht unbedingt in der in diesen Tabellen aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="286df-150">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
>- <span data-ttu-id="286df-151">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="286df-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="286df-152">Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="286df-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="286df-153">Property (id)</span><span class="sxs-lookup"><span data-stu-id="286df-153">Property (id)</span></span> | <span data-ttu-id="286df-154">Datentyp</span><span class="sxs-lookup"><span data-stu-id="286df-154">Data type</span></span> | <span data-ttu-id="286df-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="286df-155">Description</span></span> | <span data-ttu-id="286df-156">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="286df-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="286df-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="286df-157">ConfigurationCategory</span></span> | <span data-ttu-id="286df-158">string</span><span class="sxs-lookup"><span data-stu-id="286df-158">string</span></span> | <span data-ttu-id="286df-159">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="286df-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="286df-160">Sicherheitssteuerelemente</span><span class="sxs-lookup"><span data-stu-id="286df-160">Security controls</span></span>
<span data-ttu-id="286df-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="286df-161">ConfigurationId</span></span> | <span data-ttu-id="286df-162">string</span><span class="sxs-lookup"><span data-stu-id="286df-162">string</span></span> | <span data-ttu-id="286df-163">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="286df-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="286df-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="286df-164">scid-10000</span></span>
<span data-ttu-id="286df-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="286df-165">ConfigurationImpact</span></span> | <span data-ttu-id="286df-166">string</span><span class="sxs-lookup"><span data-stu-id="286df-166">string</span></span> | <span data-ttu-id="286df-167">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="286df-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="286df-168">9 </span><span class="sxs-lookup"><span data-stu-id="286df-168">9</span></span>
<span data-ttu-id="286df-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="286df-169">ConfigurationName</span></span> | <span data-ttu-id="286df-170">string</span><span class="sxs-lookup"><span data-stu-id="286df-170">string</span></span> | <span data-ttu-id="286df-171">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="286df-171">Display name of the configuration</span></span> | <span data-ttu-id="286df-172">Geräte in Microsoft Defender für Endpunkt onboarden</span><span class="sxs-lookup"><span data-stu-id="286df-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="286df-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="286df-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="286df-174">string</span><span class="sxs-lookup"><span data-stu-id="286df-174">string</span></span> | <span data-ttu-id="286df-175">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="286df-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="286df-176">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="286df-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="286df-177">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="286df-177">Onboard Devices</span></span>
<span data-ttu-id="286df-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="286df-178">DeviceId</span></span> | <span data-ttu-id="286df-179">string</span><span class="sxs-lookup"><span data-stu-id="286df-179">string</span></span> | <span data-ttu-id="286df-180">Eindeutige ID für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="286df-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="286df-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="286df-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="286df-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="286df-182">DeviceName</span></span> | <span data-ttu-id="286df-183">string</span><span class="sxs-lookup"><span data-stu-id="286df-183">string</span></span> | <span data-ttu-id="286df-184">Vollqualifizierter Domänenname (FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="286df-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="286df-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="286df-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="286df-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="286df-186">IsApplicable</span></span> | <span data-ttu-id="286df-187">bool</span><span class="sxs-lookup"><span data-stu-id="286df-187">bool</span></span> | <span data-ttu-id="286df-188">Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist</span><span class="sxs-lookup"><span data-stu-id="286df-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="286df-189">true</span><span class="sxs-lookup"><span data-stu-id="286df-189">true</span></span>
<span data-ttu-id="286df-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="286df-190">IsCompliant</span></span> | <span data-ttu-id="286df-191">bool</span><span class="sxs-lookup"><span data-stu-id="286df-191">bool</span></span> | <span data-ttu-id="286df-192">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="286df-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="286df-193">false</span><span class="sxs-lookup"><span data-stu-id="286df-193">false</span></span>
<span data-ttu-id="286df-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="286df-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="286df-195">bool</span><span class="sxs-lookup"><span data-stu-id="286df-195">bool</span></span> | <span data-ttu-id="286df-196">Gibt an, ob sich benutzer auswirken wird, wenn die Konfiguration angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="286df-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="286df-197">true</span><span class="sxs-lookup"><span data-stu-id="286df-197">true</span></span>
<span data-ttu-id="286df-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="286df-198">OSPlatform</span></span> | <span data-ttu-id="286df-199">string</span><span class="sxs-lookup"><span data-stu-id="286df-199">string</span></span> | <span data-ttu-id="286df-200">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="286df-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="286df-201">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="286df-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="286df-202">Weitere Informationen finden Sie unter tvm supported operating systems and platforms.</span><span class="sxs-lookup"><span data-stu-id="286df-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="286df-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="286df-203">Windows10</span></span>
<span data-ttu-id="286df-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="286df-204">RbacGroupName</span></span> | <span data-ttu-id="286df-205">string</span><span class="sxs-lookup"><span data-stu-id="286df-205">string</span></span> | <span data-ttu-id="286df-206">Die rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="286df-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="286df-207">Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="286df-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="286df-208">Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="286df-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="286df-209">Server</span><span class="sxs-lookup"><span data-stu-id="286df-209">Servers</span></span>
<span data-ttu-id="286df-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="286df-210">RecommendationReference</span></span> | <span data-ttu-id="286df-211">string</span><span class="sxs-lookup"><span data-stu-id="286df-211">string</span></span> | <span data-ttu-id="286df-212">Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.</span><span class="sxs-lookup"><span data-stu-id="286df-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="286df-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="286df-213">sca-_-scid-20000</span></span>
<span data-ttu-id="286df-214">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="286df-214">Timestamp</span></span> | <span data-ttu-id="286df-215">string</span><span class="sxs-lookup"><span data-stu-id="286df-215">string</span></span> | <span data-ttu-id="286df-216">Das letzte Mal, als die Konfiguration auf dem Gerät angezeigt wurde</span><span class="sxs-lookup"><span data-stu-id="286df-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="286df-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="286df-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="286df-218">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="286df-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="286df-219">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="286df-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="286df-220">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="286df-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="286df-221">2. Exportieren einer sicheren Konfigurationsbewertung (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="286df-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="286df-222">Beschreibung der 2.1-API-Methode</span><span class="sxs-lookup"><span data-stu-id="286df-222">2.1 API method description</span></span>

<span data-ttu-id="286df-223">Diese API-Antwort enthält die Secure Configuration Assessment auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination von DeviceId, ConfigurationId zurück.</span><span class="sxs-lookup"><span data-stu-id="286df-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="286df-224">2.1.2 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="286df-224">2.1.2 Limitations</span></span>

<span data-ttu-id="286df-225">Die Tarifeinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="286df-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="286df-226">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="286df-226">2.2 Permissions</span></span>

<span data-ttu-id="286df-227">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="286df-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="286df-228">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="286df-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="286df-229">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="286df-229">Permission type</span></span> | <span data-ttu-id="286df-230">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="286df-230">Permission</span></span> | <span data-ttu-id="286df-231">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="286df-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="286df-232">Anwendung</span><span class="sxs-lookup"><span data-stu-id="286df-232">Application</span></span> | <span data-ttu-id="286df-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="286df-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="286df-234">\'Informationen zu Bedrohungs- und Sicherheitsrisikomanagement Sicherheitsrisiko lesen\'</span><span class="sxs-lookup"><span data-stu-id="286df-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="286df-235">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="286df-235">Delegated (work or school account)</span></span> | <span data-ttu-id="286df-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="286df-236">Vulnerability.Read</span></span> | <span data-ttu-id="286df-237">\'Informationen zu Bedrohungs- und Sicherheitsrisikomanagement Sicherheitsrisiko lesen\'</span><span class="sxs-lookup"><span data-stu-id="286df-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="286df-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="286df-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="286df-239">Parameter</span><span class="sxs-lookup"><span data-stu-id="286df-239">Parameters</span></span>

- <span data-ttu-id="286df-240">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (Maximal 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="286df-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="286df-241">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="286df-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="286df-242">Die Dateien sind gzip-komprimierte & im mehrstufigen Json-Format.</span><span class="sxs-lookup"><span data-stu-id="286df-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="286df-243">Die #A0 sind nur für 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="286df-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="286df-244">Um die maximale Downloadgeschwindigkeit Ihrer Daten zu erhalten, können Sie sicherstellen, dass Sie aus derselben Azure-Region heruntergeladen werden, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="286df-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="286df-245">Property (id)</span><span class="sxs-lookup"><span data-stu-id="286df-245">Property (id)</span></span> | <span data-ttu-id="286df-246">Datentyp</span><span class="sxs-lookup"><span data-stu-id="286df-246">Data type</span></span> | <span data-ttu-id="286df-247">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="286df-247">Description</span></span> | <span data-ttu-id="286df-248">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="286df-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="286df-249">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="286df-249">Export files</span></span> | <span data-ttu-id="286df-250">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="286df-250">array\[string\]</span></span> | <span data-ttu-id="286df-251">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten</span><span class="sxs-lookup"><span data-stu-id="286df-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="286df-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="286df-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="286df-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="286df-253">GeneratedTime</span></span> | <span data-ttu-id="286df-254">string</span><span class="sxs-lookup"><span data-stu-id="286df-254">string</span></span> | <span data-ttu-id="286df-255">Der Zeitpunkt, zu dem der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="286df-255">The time that the export was generated.</span></span> | <span data-ttu-id="286df-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="286df-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="286df-257">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="286df-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="286df-258">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="286df-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="286df-259">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="286df-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="286df-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="286df-260">See also</span></span>

- [<span data-ttu-id="286df-261">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="286df-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="286df-262">Exportieren der Softwareinventarbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="286df-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="286df-263">Exportieren der Bewertung von Softwarerisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="286df-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="286df-264">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="286df-264">Other related</span></span>

- [<span data-ttu-id="286df-265">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="286df-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="286df-266">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="286df-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
