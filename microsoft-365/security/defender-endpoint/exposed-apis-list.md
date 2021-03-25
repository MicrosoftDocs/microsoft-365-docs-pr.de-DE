---
title: Unterstützte Microsoft Defender for Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die spezifischen unterstützten Microsoft Defender for Endpoint-Entitäten, an die Sie API-Aufrufe erstellen können.
keywords: apis, supported apis, actor, alerts, device, user, domain, ip, file, advanced queries, advanced hunting
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198322"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4c2b8-104">Unterstützte Microsoft Defender for Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="4c2b8-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4c2b8-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4c2b8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4c2b8-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4c2b8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4c2b8-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="4c2b8-108">Endpunkt-URI und Versionsing</span><span class="sxs-lookup"><span data-stu-id="4c2b8-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="4c2b8-109">Endpunkt-URI:            </span><span class="sxs-lookup"><span data-stu-id="4c2b8-109">Endpoint URI:</span></span>

> <span data-ttu-id="4c2b8-110">Der Dienstbasis-URI ist: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4c2b8-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="4c2b8-111">Die abfragenbasierten OData haben das Präfix "/api".</span><span class="sxs-lookup"><span data-stu-id="4c2b8-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="4c2b8-112">Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="4c2b8-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="4c2b8-113">Versionierung:</span><span class="sxs-lookup"><span data-stu-id="4c2b8-113">Versioning:</span></span>

> <span data-ttu-id="4c2b8-114">Die API unterstützt die Versionsierung.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="4c2b8-115">Die aktuelle Version ist **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="4c2b8-116">Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="4c2b8-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="4c2b8-117">Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="4c2b8-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="4c2b8-118">Wenn Sie keine Version (z. B. ) angeben, erhalten Sie https://api.securitycenter.microsoft.com/api/alerts die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="4c2b8-119">Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4c2b8-120">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="4c2b8-120">In this section</span></span>

<span data-ttu-id="4c2b8-121">Thema</span><span class="sxs-lookup"><span data-stu-id="4c2b8-121">Topic</span></span> | <span data-ttu-id="4c2b8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c2b8-122">Description</span></span>
:---|:---
<span data-ttu-id="4c2b8-123">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="4c2b8-123">Advanced Hunting</span></span> | <span data-ttu-id="4c2b8-124">Führen Sie Abfragen aus der API aus.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-124">Run queries from API.</span></span>
<span data-ttu-id="4c2b8-125">Warnungen</span><span class="sxs-lookup"><span data-stu-id="4c2b8-125">Alerts</span></span> | <span data-ttu-id="4c2b8-126">Führen Sie API-Aufrufe aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="4c2b8-127">Domänen</span><span class="sxs-lookup"><span data-stu-id="4c2b8-127">Domains</span></span> | <span data-ttu-id="4c2b8-128">Führen Sie API-Aufrufe aus, z. B. domänenbezogene Geräte, Domänenstatistiken und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="4c2b8-129">Dateien</span><span class="sxs-lookup"><span data-stu-id="4c2b8-129">Files</span></span> | <span data-ttu-id="4c2b8-130">Führen Sie API-Aufrufe aus, z. B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="4c2b8-131">IPs</span><span class="sxs-lookup"><span data-stu-id="4c2b8-131">IPs</span></span> | <span data-ttu-id="4c2b8-132">Führen Sie API-Aufrufe aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="4c2b8-133">Maschinen</span><span class="sxs-lookup"><span data-stu-id="4c2b8-133">Machines</span></span> | <span data-ttu-id="4c2b8-134">Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten Benutzern, Bearbeiten von Tags und mehr.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="4c2b8-135">Computeraktionen</span><span class="sxs-lookup"><span data-stu-id="4c2b8-135">Machine Actions</span></span> | <span data-ttu-id="4c2b8-136">Führen Sie API-Aufrufe wie Isolation, Virenschutzscan ausführen und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="4c2b8-137">Indikatoren</span><span class="sxs-lookup"><span data-stu-id="4c2b8-137">Indicators</span></span> | <span data-ttu-id="4c2b8-138">Führen Sie API-Aufrufe aus, z. B. Indikator erstellen, Indikatoren abrufen und Indikatoren löschen.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="4c2b8-139">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4c2b8-139">Users</span></span> | <span data-ttu-id="4c2b8-140">Führen Sie API-Aufrufe aus, z. B. benutzerbezogene Warnungen und benutzerbezogene Geräte.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="4c2b8-141">Bewertung</span><span class="sxs-lookup"><span data-stu-id="4c2b8-141">Score</span></span> | <span data-ttu-id="4c2b8-142">Führen Sie API-Aufrufe aus, z. B. das Abrufen der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="4c2b8-143">Software</span><span class="sxs-lookup"><span data-stu-id="4c2b8-143">Software</span></span> | <span data-ttu-id="4c2b8-144">Führen Sie API-Aufrufe wie z. B. das Auflisten von Sicherheitsrisiken nach Software aus.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="4c2b8-145">Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="4c2b8-145">Vulnerability</span></span> | <span data-ttu-id="4c2b8-146">Führen Sie API-Aufrufe wie z. B. Listengeräte nach Sicherheitsrisiko aus.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="4c2b8-147">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="4c2b8-147">Recommendation</span></span> | <span data-ttu-id="4c2b8-148">Führen Sie API-Aufrufe wie Empfehlung nach ID abrufen aus.</span><span class="sxs-lookup"><span data-stu-id="4c2b8-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c2b8-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c2b8-149">See also</span></span>
- [<span data-ttu-id="4c2b8-150">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="4c2b8-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
