---
title: Unterstütze Microsoft Defender für Endpoint-APIs
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073829"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="7575e-104">Unterstütze Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="7575e-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7575e-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7575e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7575e-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7575e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7575e-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7575e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="7575e-108">Endpunkt-URI und Versionsing</span><span class="sxs-lookup"><span data-stu-id="7575e-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="7575e-109">Endpunkt-URI</span><span class="sxs-lookup"><span data-stu-id="7575e-109">Endpoint URI</span></span>

> <span data-ttu-id="7575e-110">Der Dienstbasis-URI ist: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="7575e-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="7575e-111">Die abfragenbasierten OData haben das Präfix "/api".</span><span class="sxs-lookup"><span data-stu-id="7575e-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="7575e-112">Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="7575e-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="7575e-113">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="7575e-113">Versioning</span></span>

> <span data-ttu-id="7575e-114">Die API unterstützt die Versionsierung.</span><span class="sxs-lookup"><span data-stu-id="7575e-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="7575e-115">Die aktuelle Version ist **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="7575e-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="7575e-116">Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="7575e-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="7575e-117">Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="7575e-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="7575e-118">Wenn Sie keine Version (z. B. ) angeben, erhalten Sie `https://api.securitycenter.microsoft.com/api/alerts` die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="7575e-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="7575e-119">Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.</span><span class="sxs-lookup"><span data-stu-id="7575e-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7575e-120">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="7575e-120">In this section</span></span>

<span data-ttu-id="7575e-121">Thema</span><span class="sxs-lookup"><span data-stu-id="7575e-121">Topic</span></span> | <span data-ttu-id="7575e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7575e-122">Description</span></span>
:---|:---
[<span data-ttu-id="7575e-123">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="7575e-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="7575e-124">Führen Sie Abfragen aus der API aus.</span><span class="sxs-lookup"><span data-stu-id="7575e-124">Run queries from API.</span></span>
[<span data-ttu-id="7575e-125">Warnungsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="7575e-126">Führen Sie API-Aufrufe \- aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="7575e-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="7575e-127">Methoden und Eigenschaften der automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="7575e-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="7575e-128">Führen Sie API-Aufrufe aus, \- z. B. Abrufen der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="7575e-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="7575e-129">Domänenbezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="7575e-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="7575e-130">Führen Sie API-Aufrufe aus, z. B. \- domänenbezogene Geräte, Domänenstatistiken und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="7575e-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="7575e-131">Dateimethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="7575e-132">Führen Sie API-Aufrufe aus, z. \- B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.</span><span class="sxs-lookup"><span data-stu-id="7575e-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="7575e-133">Methoden und Eigenschaften von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="7575e-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="7575e-134">Führen Sie API-Aufrufe aus, z. \- B. Indikatoren abrufen, Indikator erstellen und Indikatoren löschen.</span><span class="sxs-lookup"><span data-stu-id="7575e-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="7575e-135">IP-bezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="7575e-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="7575e-136">Führen Sie API-Aufrufe \- aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.</span><span class="sxs-lookup"><span data-stu-id="7575e-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="7575e-137">Computermethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="7575e-138">Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten \- Benutzern, Bearbeiten von Tags und mehr.</span><span class="sxs-lookup"><span data-stu-id="7575e-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="7575e-139">Computer-Aktionsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="7575e-140">Führen Sie API-Aufrufe \- wie Isolation, Virenschutzscan ausführen und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="7575e-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="7575e-141">Methoden und Eigenschaften für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="7575e-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="7575e-142">Führen Sie API-Aufrufe aus, \- z. B. Empfehlung nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="7575e-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="7575e-143">Bewertungsmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="7575e-144">Führen Sie API-Aufrufe aus, z. B. das Abrufen \- der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.</span><span class="sxs-lookup"><span data-stu-id="7575e-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="7575e-145">Softwaremethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7575e-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="7575e-146">Führen Sie API-Aufrufe wie \- z. B. das Auflisten von Sicherheitsrisiken nach Software aus.</span><span class="sxs-lookup"><span data-stu-id="7575e-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="7575e-147">Benutzermethoden</span><span class="sxs-lookup"><span data-stu-id="7575e-147">User methods</span></span>](user.md) | <span data-ttu-id="7575e-148">Führen Sie API-Aufrufe aus, z. B. \- benutzerbezogene Warnungen und benutzerbezogene Geräte.</span><span class="sxs-lookup"><span data-stu-id="7575e-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="7575e-149">Methoden und Eigenschaften für Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="7575e-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="7575e-150">Führen Sie API-Aufrufe wie \- z. B. Listengeräte nach Sicherheitsrisiko aus.</span><span class="sxs-lookup"><span data-stu-id="7575e-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="7575e-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7575e-151">See also</span></span>

- [<span data-ttu-id="7575e-152">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="7575e-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="7575e-153">Versionshinweise zur Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="7575e-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
