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
ms.openlocfilehash: f7a620ad56496b1a26e193a18fa93f4d217431df
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684147"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="eb9f9-104">Unterstütze Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="eb9f9-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb9f9-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="eb9f9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="eb9f9-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="eb9f9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eb9f9-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="eb9f9-108">Endpunkt-URI und Versionsing</span><span class="sxs-lookup"><span data-stu-id="eb9f9-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="eb9f9-109">Endpunkt-URI</span><span class="sxs-lookup"><span data-stu-id="eb9f9-109">Endpoint URI</span></span>

> <span data-ttu-id="eb9f9-110">Der Dienstbasis-URI ist: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="eb9f9-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="eb9f9-111">Die abfragenbasierten OData haben das Präfix "/api".</span><span class="sxs-lookup"><span data-stu-id="eb9f9-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="eb9f9-112">Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="eb9f9-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="eb9f9-113">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="eb9f9-113">Versioning</span></span>

> <span data-ttu-id="eb9f9-114">Die API unterstützt die Versionsierung.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="eb9f9-115">Die aktuelle Version ist **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="eb9f9-116">Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="eb9f9-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="eb9f9-117">Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="eb9f9-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="eb9f9-118">Wenn Sie keine Version (z. B. ) angeben, erhalten Sie `https://api.securitycenter.microsoft.com/api/alerts` die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="eb9f9-119">Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb9f9-120">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="eb9f9-120">In this section</span></span>

<span data-ttu-id="eb9f9-121">Thema</span><span class="sxs-lookup"><span data-stu-id="eb9f9-121">Topic</span></span> | <span data-ttu-id="eb9f9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9f9-122">Description</span></span>
:---|:---
[<span data-ttu-id="eb9f9-123">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="eb9f9-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="eb9f9-124">Führen Sie Abfragen aus der API aus.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-124">Run queries from API.</span></span>
[<span data-ttu-id="eb9f9-125">Warnungsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="eb9f9-126">Führen Sie API-Aufrufe \- aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="eb9f9-127">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="eb9f9-127">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md) | <span data-ttu-id="eb9f9-128">Führen Sie API-Aufrufe wie \- export secure configuration assessment, export software inventory assessment und export software vulnerabilities assessment aus.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-128">Run API calls such as \- export secure configuration assessment, export software inventory assessment,  and export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="eb9f9-129">Methoden und Eigenschaften der automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="eb9f9-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="eb9f9-130">Führen Sie API-Aufrufe aus, \- z. B. Abrufen der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="eb9f9-131">Domänenbezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="eb9f9-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="eb9f9-132">Führen Sie API-Aufrufe aus, z. B. \- domänenbezogene Geräte, Domänenstatistiken und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="eb9f9-133">Dateimethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="eb9f9-134">Führen Sie API-Aufrufe aus, z. \- B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="eb9f9-135">Methoden und Eigenschaften von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="eb9f9-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="eb9f9-136">Führen Sie API-Aufrufe aus, z. \- B. Indikatoren abrufen, Indikator erstellen und Indikatoren löschen.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="eb9f9-137">IP-bezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="eb9f9-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="eb9f9-138">Führen Sie API-Aufrufe \- aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="eb9f9-139">Computermethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="eb9f9-140">Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten \- Benutzern, Bearbeiten von Tags und mehr.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="eb9f9-141">Computer-Aktionsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="eb9f9-142">Führen Sie API-Aufrufe \- wie Isolation, Virenschutzscan ausführen und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="eb9f9-143">Methoden und Eigenschaften für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="eb9f9-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="eb9f9-144">Führen Sie API-Aufrufe aus, \- z. B. Empfehlung nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="eb9f9-145">Methoden und Eigenschaften der Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="eb9f9-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="eb9f9-146">Führen Sie API-Aufrufe aus, z. B. alle Wartungsaufgaben abrufen, Aufgaben zur Behebung verfügbarer Geräte abrufen und eine Problembehebungsaufgabe \- nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="eb9f9-147">Bewertungsmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="eb9f9-148">Führen Sie API-Aufrufe aus, z. B. das Abrufen \- der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="eb9f9-149">Softwaremethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9f9-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="eb9f9-150">Führen Sie API-Aufrufe wie \- z. B. das Auflisten von Sicherheitsrisiken nach Software aus.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="eb9f9-151">Benutzermethoden</span><span class="sxs-lookup"><span data-stu-id="eb9f9-151">User methods</span></span>](user.md) | <span data-ttu-id="eb9f9-152">Führen Sie API-Aufrufe aus, z. B. \- benutzerbezogene Warnungen und benutzerbezogene Geräte.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="eb9f9-153">Methoden und Eigenschaften für Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="eb9f9-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="eb9f9-154">Führen Sie API-Aufrufe wie \- z. B. Listengeräte nach Sicherheitsrisiko aus.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb9f9-155">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="eb9f9-155">See also</span></span>

- [<span data-ttu-id="eb9f9-156">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="eb9f9-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="eb9f9-157">Versionshinweise zur Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="eb9f9-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
