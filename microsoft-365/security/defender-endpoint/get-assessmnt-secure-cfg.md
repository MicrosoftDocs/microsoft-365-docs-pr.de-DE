---
title: Exportieren der Bewertung der sicheren Konfiguration pro Gerät
description: Gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.
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
ms.openlocfilehash: ab33db7fb7acf1969973a7af8f80ea97ef3d378f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778334"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="4d233-104">Exportieren der Bewertung der sicheren Konfiguration pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4d233-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d233-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4d233-105">**Applies to:**</span></span>

- [<span data-ttu-id="4d233-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4d233-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d233-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d233-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4d233-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4d233-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d233-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4d233-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="4d233-110">Gibt alle Konfigurationen und deren Status pro Gerät zurück.</span><span class="sxs-lookup"><span data-stu-id="4d233-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="4d233-111">Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d233-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="4d233-112">Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:</span><span class="sxs-lookup"><span data-stu-id="4d233-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="4d233-113">[Exportieren Sie **OData**](#1-export-secure-configuration-assessment-odata)zur Bewertung der sicheren Konfiguration: Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab.</span><span class="sxs-lookup"><span data-stu-id="4d233-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="4d233-114">Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100 K-Geräten._</span><span class="sxs-lookup"><span data-stu-id="4d233-114">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="4d233-115">Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d233-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="4d233-116">Exportieren der [Bewertung der sicheren Konfiguration **über Dateien:**](#2-export-secure-configuration-assessment-via-files)Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="4d233-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="4d233-117">Daher wird es für große Organisationen mit mehr als 100 K-Geräten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4d233-117">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="4d233-118">Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab.</span><span class="sxs-lookup"><span data-stu-id="4d233-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="4d233-119">Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="4d233-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="4d233-120">Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:</span><span class="sxs-lookup"><span data-stu-id="4d233-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="4d233-121">Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d233-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="4d233-122">Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4d233-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="4d233-123">Daten, die gesammelt werden (entweder mit _OData_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten.</span><span class="sxs-lookup"><span data-stu-id="4d233-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="4d233-124">Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.</span><span class="sxs-lookup"><span data-stu-id="4d233-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="4d233-125">Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="4d233-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="4d233-126">1. Exportieren der Bewertung der sicheren Konfiguration (OData)</span><span class="sxs-lookup"><span data-stu-id="4d233-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="4d233-127">1.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4d233-127">1.1 API method description</span></span>

<span data-ttu-id="4d233-128">Diese API-Antwort enthält die Bewertung der sicheren Konfiguration auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.</span><span class="sxs-lookup"><span data-stu-id="4d233-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="4d233-129">1.1.1 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4d233-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="4d233-130">Die maximale Seitengröße beträgt 200.000.</span><span class="sxs-lookup"><span data-stu-id="4d233-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="4d233-131">Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4d233-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="4d233-132">1.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4d233-132">1.2 Permissions</span></span>

<span data-ttu-id="4d233-133">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d233-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4d233-134">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4d233-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4d233-135">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4d233-135">Permission type</span></span> | <span data-ttu-id="4d233-136">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4d233-136">Permission</span></span> | <span data-ttu-id="4d233-137">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4d233-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="4d233-138">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4d233-138">Application</span></span> | <span data-ttu-id="4d233-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4d233-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="4d233-140">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4d233-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="4d233-141">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4d233-141">Delegated (work or school account)</span></span> | <span data-ttu-id="4d233-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4d233-142">Vulnerability.Read</span></span> | <span data-ttu-id="4d233-143">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="4d233-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="4d233-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="4d233-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="4d233-145">1.4 Parameter</span><span class="sxs-lookup"><span data-stu-id="4d233-145">1.4 Parameters</span></span>

- <span data-ttu-id="4d233-146">pageSize \( default = 50.000 \) – Anzahl der Ergebnisse als Antwort</span><span class="sxs-lookup"><span data-stu-id="4d233-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="4d233-147">\$top – Anzahl der zurückzugebenden Ergebnisse \( gibt \@ odata.nextLink nicht zurück und ruft daher nicht alle Daten ab\)</span><span class="sxs-lookup"><span data-stu-id="4d233-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="4d233-148">1.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4d233-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="4d233-149">Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4d233-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="4d233-150">Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4d233-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="4d233-151">Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4d233-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="4d233-152">Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4d233-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="4d233-153">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="4d233-153">Property (ID)</span></span> | <span data-ttu-id="4d233-154">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4d233-154">Data type</span></span> | <span data-ttu-id="4d233-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d233-155">Description</span></span> | <span data-ttu-id="4d233-156">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="4d233-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4d233-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="4d233-157">ConfigurationCategory</span></span> | <span data-ttu-id="4d233-158">string</span><span class="sxs-lookup"><span data-stu-id="4d233-158">string</span></span> | <span data-ttu-id="4d233-159">Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="4d233-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="4d233-160">Sicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="4d233-160">Security controls</span></span>
<span data-ttu-id="4d233-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="4d233-161">ConfigurationId</span></span> | <span data-ttu-id="4d233-162">string</span><span class="sxs-lookup"><span data-stu-id="4d233-162">string</span></span> | <span data-ttu-id="4d233-163">Eindeutiger Bezeichner für eine bestimmte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4d233-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="4d233-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="4d233-164">scid-10000</span></span>
<span data-ttu-id="4d233-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="4d233-165">ConfigurationImpact</span></span> | <span data-ttu-id="4d233-166">string</span><span class="sxs-lookup"><span data-stu-id="4d233-166">string</span></span> | <span data-ttu-id="4d233-167">Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10)</span><span class="sxs-lookup"><span data-stu-id="4d233-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="4d233-168">9 </span><span class="sxs-lookup"><span data-stu-id="4d233-168">9</span></span>
<span data-ttu-id="4d233-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="4d233-169">ConfigurationName</span></span> | <span data-ttu-id="4d233-170">string</span><span class="sxs-lookup"><span data-stu-id="4d233-170">string</span></span> | <span data-ttu-id="4d233-171">Anzeigename der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4d233-171">Display name of the configuration</span></span> | <span data-ttu-id="4d233-172">Geräte in Microsoft Defender für Endpunkt onboarden</span><span class="sxs-lookup"><span data-stu-id="4d233-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="4d233-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="4d233-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="4d233-174">string</span><span class="sxs-lookup"><span data-stu-id="4d233-174">string</span></span> | <span data-ttu-id="4d233-175">Unterkategorie oder Untergruppe, zu der die Konfiguration gehört.</span><span class="sxs-lookup"><span data-stu-id="4d233-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="4d233-176">In vielen Fällen beschreibt dies bestimmte Funktionen oder Features.</span><span class="sxs-lookup"><span data-stu-id="4d233-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="4d233-177">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="4d233-177">Onboard Devices</span></span>
<span data-ttu-id="4d233-178">Deviceid</span><span class="sxs-lookup"><span data-stu-id="4d233-178">DeviceId</span></span> | <span data-ttu-id="4d233-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-179">string</span></span> | <span data-ttu-id="4d233-180">Eindeutiger Bezeichner für das Gerät im Dienst.</span><span class="sxs-lookup"><span data-stu-id="4d233-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="4d233-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="4d233-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="4d233-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="4d233-182">DeviceName</span></span> | <span data-ttu-id="4d233-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-183">string</span></span> | <span data-ttu-id="4d233-184">Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="4d233-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="4d233-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d233-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="4d233-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="4d233-186">IsApplicable</span></span> | <span data-ttu-id="4d233-187">bool</span><span class="sxs-lookup"><span data-stu-id="4d233-187">bool</span></span> | <span data-ttu-id="4d233-188">Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="4d233-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="4d233-189">true</span><span class="sxs-lookup"><span data-stu-id="4d233-189">true</span></span>
<span data-ttu-id="4d233-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="4d233-190">IsCompliant</span></span> | <span data-ttu-id="4d233-191">bool</span><span class="sxs-lookup"><span data-stu-id="4d233-191">bool</span></span> | <span data-ttu-id="4d233-192">Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="4d233-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="4d233-193">false</span><span class="sxs-lookup"><span data-stu-id="4d233-193">false</span></span>
<span data-ttu-id="4d233-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="4d233-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="4d233-195">bool</span><span class="sxs-lookup"><span data-stu-id="4d233-195">bool</span></span> | <span data-ttu-id="4d233-196">Gibt an, ob es Auswirkungen auf den Benutzer gibt, wenn die Konfiguration angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d233-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="4d233-197">true</span><span class="sxs-lookup"><span data-stu-id="4d233-197">true</span></span>
<span data-ttu-id="4d233-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="4d233-198">OSPlatform</span></span> | <span data-ttu-id="4d233-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-199">string</span></span> | <span data-ttu-id="4d233-200">Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d233-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4d233-201">Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4d233-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="4d233-202">Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="4d233-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="4d233-203">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d233-203">Windows10</span></span>
<span data-ttu-id="4d233-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="4d233-204">RbacGroupName</span></span> | <span data-ttu-id="4d233-205">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-205">string</span></span> | <span data-ttu-id="4d233-206">Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4d233-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="4d233-207">Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen".</span><span class="sxs-lookup"><span data-stu-id="4d233-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="4d233-208">Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None".</span><span class="sxs-lookup"><span data-stu-id="4d233-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="4d233-209">Server</span><span class="sxs-lookup"><span data-stu-id="4d233-209">Servers</span></span>
<span data-ttu-id="4d233-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="4d233-210">RecommendationReference</span></span> | <span data-ttu-id="4d233-211">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-211">string</span></span> | <span data-ttu-id="4d233-212">Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software.</span><span class="sxs-lookup"><span data-stu-id="4d233-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="4d233-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="4d233-213">sca-_-scid-20000</span></span>
<span data-ttu-id="4d233-214">Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="4d233-214">Timestamp</span></span> | <span data-ttu-id="4d233-215">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-215">string</span></span> | <span data-ttu-id="4d233-216">Zeitpunkt, zu dem die Konfiguration zuletzt auf dem Gerät angezeigt wurde</span><span class="sxs-lookup"><span data-stu-id="4d233-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="4d233-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="4d233-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="4d233-218">1.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="4d233-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="4d233-219">1.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="4d233-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="4d233-220">1.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="4d233-220">1.6.2 Response example</span></span>

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

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="4d233-221">2. Exportieren der Bewertung der sicheren Konfiguration (über Dateien)</span><span class="sxs-lookup"><span data-stu-id="4d233-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="4d233-222">2.1 API-Methodenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4d233-222">2.1 API method description</span></span>

<span data-ttu-id="4d233-223">Diese API-Antwort enthält die Bewertung der sicheren Konfiguration auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.</span><span class="sxs-lookup"><span data-stu-id="4d233-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="4d233-224">2.1.2 Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4d233-224">2.1.2 Limitations</span></span>

<span data-ttu-id="4d233-225">Die Rateneinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.</span><span class="sxs-lookup"><span data-stu-id="4d233-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="4d233-226">2.2 Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4d233-226">2.2 Permissions</span></span>

<span data-ttu-id="4d233-227">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d233-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4d233-228">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4d233-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="4d233-229">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4d233-229">Permission type</span></span> | <span data-ttu-id="4d233-230">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4d233-230">Permission</span></span> | <span data-ttu-id="4d233-231">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="4d233-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="4d233-232">Anwendung</span><span class="sxs-lookup"><span data-stu-id="4d233-232">Application</span></span> | <span data-ttu-id="4d233-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="4d233-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="4d233-234">\'Sicherheitsrisikoinformationen "Bedrohungs- und Sicherheitsrisikomanagement" lesen\'</span><span class="sxs-lookup"><span data-stu-id="4d233-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="4d233-235">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="4d233-235">Delegated (work or school account)</span></span> | <span data-ttu-id="4d233-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="4d233-236">Vulnerability.Read</span></span> | <span data-ttu-id="4d233-237">\'Sicherheitsrisikoinformationen "Bedrohungs- und Sicherheitsrisikomanagement" lesen\'</span><span class="sxs-lookup"><span data-stu-id="4d233-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="4d233-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="4d233-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="4d233-239">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d233-239">Parameters</span></span>

- <span data-ttu-id="4d233-240">sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (maximal 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="4d233-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="4d233-241">2.5-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4d233-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="4d233-242">Die Dateien werden & im mehrzeiligen JSON-Format gzipkomprimiert.</span><span class="sxs-lookup"><span data-stu-id="4d233-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="4d233-243">Die Download-URLs sind nur 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d233-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="4d233-244">Für eine maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie die Daten aus derselben Azure-Region herunterladen, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="4d233-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="4d233-245">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="4d233-245">Property (ID)</span></span> | <span data-ttu-id="4d233-246">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4d233-246">Data type</span></span> | <span data-ttu-id="4d233-247">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d233-247">Description</span></span> | <span data-ttu-id="4d233-248">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="4d233-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="4d233-249">Exportieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="4d233-249">Export files</span></span> | <span data-ttu-id="4d233-250">\[Arrayzeichenfolge\]</span><span class="sxs-lookup"><span data-stu-id="4d233-250">array\[string\]</span></span> | <span data-ttu-id="4d233-251">Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten</span><span class="sxs-lookup"><span data-stu-id="4d233-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="4d233-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="4d233-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="4d233-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="4d233-253">GeneratedTime</span></span> | <span data-ttu-id="4d233-254">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4d233-254">string</span></span> | <span data-ttu-id="4d233-255">Die Zeit, zu der der Export generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4d233-255">The time that the export was generated.</span></span> | <span data-ttu-id="4d233-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="4d233-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="4d233-257">2.6 Beispiele</span><span class="sxs-lookup"><span data-stu-id="4d233-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="4d233-258">2.6.1 Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="4d233-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="4d233-259">2.6.2 Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="4d233-259">2.6.2 Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4d233-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d233-260">See also</span></span>

- [<span data-ttu-id="4d233-261">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4d233-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="4d233-262">Exportieren der Softwareinventarisierungsbewertung pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4d233-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="4d233-263">Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät</span><span class="sxs-lookup"><span data-stu-id="4d233-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="4d233-264">Andere verwandte</span><span class="sxs-lookup"><span data-stu-id="4d233-264">Other related</span></span>

- [<span data-ttu-id="4d233-265">Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="4d233-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="4d233-266">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4d233-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
