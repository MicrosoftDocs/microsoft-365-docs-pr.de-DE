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
ms.openlocfilehash: ab3d3aa9a13b71f65d3d4335646e32a7e4270242
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061049"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="cb416-104">Unterstütze Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="cb416-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb416-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cb416-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cb416-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cb416-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb416-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cb416-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="cb416-108">Endpunkt-URI und Versionsing</span><span class="sxs-lookup"><span data-stu-id="cb416-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="cb416-109">Endpunkt-URI</span><span class="sxs-lookup"><span data-stu-id="cb416-109">Endpoint URI</span></span>

> <span data-ttu-id="cb416-110">Der Dienstbasis-URI ist: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cb416-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="cb416-111">Die abfragenbasierten OData haben das Präfix "/api".</span><span class="sxs-lookup"><span data-stu-id="cb416-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="cb416-112">Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="cb416-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="cb416-113">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cb416-113">Versioning</span></span>

> <span data-ttu-id="cb416-114">Die API unterstützt die Versionsierung.</span><span class="sxs-lookup"><span data-stu-id="cb416-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="cb416-115">Die aktuelle Version ist **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="cb416-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="cb416-116">Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="cb416-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="cb416-117">Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="cb416-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="cb416-118">Wenn Sie keine Version (z. B. ) angeben, erhalten Sie `https://api.securitycenter.microsoft.com/api/alerts` die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="cb416-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="cb416-119">Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.</span><span class="sxs-lookup"><span data-stu-id="cb416-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cb416-120">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="cb416-120">In this section</span></span>

<span data-ttu-id="cb416-121">Thema</span><span class="sxs-lookup"><span data-stu-id="cb416-121">Topic</span></span> | <span data-ttu-id="cb416-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb416-122">Description</span></span>
:---|:---
[<span data-ttu-id="cb416-123">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="cb416-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="cb416-124">Führen Sie Abfragen aus der API aus.</span><span class="sxs-lookup"><span data-stu-id="cb416-124">Run queries from API.</span></span>
[<span data-ttu-id="cb416-125">Warnungsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="cb416-126">Führen Sie API-Aufrufe \- aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="cb416-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="cb416-127">Methoden und Eigenschaften der automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="cb416-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="cb416-128">Führen Sie API-Aufrufe aus, \- z. B. Abrufen der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="cb416-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="cb416-129">Domänenbezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="cb416-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="cb416-130">Führen Sie API-Aufrufe aus, z. B. \- domänenbezogene Geräte, Domänenstatistiken und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="cb416-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="cb416-131">Dateimethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="cb416-132">Führen Sie API-Aufrufe aus, z. \- B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.</span><span class="sxs-lookup"><span data-stu-id="cb416-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="cb416-133">Methoden und Eigenschaften von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="cb416-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="cb416-134">Führen Sie API-Aufrufe aus, z. \- B. Indikatoren abrufen, Indikator erstellen und Indikatoren löschen.</span><span class="sxs-lookup"><span data-stu-id="cb416-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="cb416-135">IP-bezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="cb416-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="cb416-136">Führen Sie API-Aufrufe \- aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.</span><span class="sxs-lookup"><span data-stu-id="cb416-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="cb416-137">Computermethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="cb416-138">Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten \- Benutzern, Bearbeiten von Tags und mehr.</span><span class="sxs-lookup"><span data-stu-id="cb416-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="cb416-139">Computer-Aktionsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="cb416-140">Führen Sie API-Aufrufe \- wie Isolation, Virenschutzscan ausführen und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="cb416-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="cb416-141">Methoden und Eigenschaften für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="cb416-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="cb416-142">Führen Sie API-Aufrufe aus, \- z. B. Empfehlung nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="cb416-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="cb416-143">Methoden und Eigenschaften der Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="cb416-143">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="cb416-144">Führen Sie API-Aufrufe aus, z. B. alle Wartungsaufgaben abrufen, Aufgaben zur Behebung verfügbarer Geräte abrufen und eine Problembehebungsaufgabe \- nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="cb416-144">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="cb416-145">Bewertungsmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-145">Score methods and properties</span></span>](score.md) | <span data-ttu-id="cb416-146">Führen Sie API-Aufrufe aus, z. B. das Abrufen \- der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.</span><span class="sxs-lookup"><span data-stu-id="cb416-146">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="cb416-147">Softwaremethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb416-147">Software methods and properties</span></span>](software.md) | <span data-ttu-id="cb416-148">Führen Sie API-Aufrufe wie \- z. B. das Auflisten von Sicherheitsrisiken nach Software aus.</span><span class="sxs-lookup"><span data-stu-id="cb416-148">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="cb416-149">Benutzermethoden</span><span class="sxs-lookup"><span data-stu-id="cb416-149">User methods</span></span>](user.md) | <span data-ttu-id="cb416-150">Führen Sie API-Aufrufe aus, z. B. \- benutzerbezogene Warnungen und benutzerbezogene Geräte.</span><span class="sxs-lookup"><span data-stu-id="cb416-150">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="cb416-151">Methoden und Eigenschaften für Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="cb416-151">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="cb416-152">Führen Sie API-Aufrufe wie \- z. B. Listengeräte nach Sicherheitsrisiko aus.</span><span class="sxs-lookup"><span data-stu-id="cb416-152">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb416-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb416-153">See also</span></span>

- [<span data-ttu-id="cb416-154">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="cb416-154">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="cb416-155">Versionshinweise zur Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="cb416-155">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
