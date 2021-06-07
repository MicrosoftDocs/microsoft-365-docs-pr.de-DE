---
title: Unterstütze Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die spezifischen unterstützten Microsoft Defender für Endpunkt-Entitäten, an die Sie API-Aufrufe erstellen können.
keywords: APIs, unterstützte APIs, Actor, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Abfragen, erweiterte Suche
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 63e38d5c9cfe50d1fa4cda1f7ae9c7df55a45083
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788835"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f8343-104">Unterstütze Microsoft Defender für Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="f8343-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8343-105">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f8343-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f8343-106">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f8343-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8343-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f8343-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="f8343-108">Endpunkt-URI und Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f8343-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="f8343-109">Endpunkt-URI</span><span class="sxs-lookup"><span data-stu-id="f8343-109">Endpoint URI</span></span>

> <span data-ttu-id="f8343-110">Der Dienstbasis-URI lautet: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f8343-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="f8343-111">Die abfragebasierten OData-Daten haben das Präfix "/api".</span><span class="sxs-lookup"><span data-stu-id="f8343-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="f8343-112">Um beispielsweise Benachrichtigungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="f8343-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="f8343-113">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f8343-113">Versioning</span></span>

> <span data-ttu-id="f8343-114">Die API unterstützt die Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f8343-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="f8343-115">Die aktuelle Version ist **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="f8343-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="f8343-116">Verwenden Sie das folgende Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="f8343-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="f8343-117">Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="f8343-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="f8343-118">Wenn Sie keine Version (z. B. ) angeben, `https://api.securitycenter.microsoft.com/api/alerts` erhalten Sie die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="f8343-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f8343-119">Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.</span><span class="sxs-lookup"><span data-stu-id="f8343-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f8343-120">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="f8343-120">In this section</span></span>

<span data-ttu-id="f8343-121">Thema</span><span class="sxs-lookup"><span data-stu-id="f8343-121">Topic</span></span> | <span data-ttu-id="f8343-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8343-122">Description</span></span>
:---|:---
[<span data-ttu-id="f8343-123">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f8343-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="f8343-124">Führen Sie Abfragen aus der API aus.</span><span class="sxs-lookup"><span data-stu-id="f8343-124">Run queries from API.</span></span>
[<span data-ttu-id="f8343-125">Warnungsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="f8343-126">Führen Sie API-Aufrufe aus, z. \- B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="f8343-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="f8343-127">Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät</span><span class="sxs-lookup"><span data-stu-id="f8343-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="f8343-128">Führen Sie API-Aufrufe aus, z. B. die Bewertung der sicheren Konfiguration exportieren, die Bewertung des \- Softwarebestands exportieren und die Bewertung von Software-Sicherheitsrisiken exportieren.</span><span class="sxs-lookup"><span data-stu-id="f8343-128">Run API calls such as \- export secure configuration assessment, export software inventory assessment,  and export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="f8343-129">Automatisierte Untersuchungsmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="f8343-130">Führen Sie API-Aufrufe aus, \- z. B. abrufen einer Sammlung von Untersuchungen.</span><span class="sxs-lookup"><span data-stu-id="f8343-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="f8343-131">Domänenbezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="f8343-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="f8343-132">Führen Sie API-Aufrufe aus, z. \- B. abrufen von domänenbezogenen Geräten, Domänenstatistiken und mehr.</span><span class="sxs-lookup"><span data-stu-id="f8343-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="f8343-133">Dateimethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="f8343-134">Führen Sie API-Aufrufe aus, z. B. das Abrufen von \- Dateiinformationen, dateibezogenen Warnungen, dateibezogenen Geräten und Dateistatistiken.</span><span class="sxs-lookup"><span data-stu-id="f8343-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="f8343-135">Methoden und Eigenschaften von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="f8343-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="f8343-136">Führen Sie API-Aufrufe aus, z. \- B. "Indikatoren abrufen", "Indikator erstellen" und "Indikatoren löschen".</span><span class="sxs-lookup"><span data-stu-id="f8343-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="f8343-137">IP-bezogene Benachrichtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="f8343-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="f8343-138">Führen Sie API-Aufrufe aus, z. \- B. ip-bezogene Warnungen abrufen und IP-Statistiken abrufen.</span><span class="sxs-lookup"><span data-stu-id="f8343-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="f8343-139">Computermethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="f8343-140">Führen Sie API-Aufrufe aus, z. B. \- Abrufen von Geräten, Abrufen von Geräten nach ID, Informationen zu angemeldeten Benutzern, Bearbeiten von Tags und mehr.</span><span class="sxs-lookup"><span data-stu-id="f8343-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="f8343-141">Computer-Aktionsmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="f8343-142">Führen Sie API-Aufrufe wie \- Isolation, Virenscan und vieles mehr aus.</span><span class="sxs-lookup"><span data-stu-id="f8343-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="f8343-143">Methoden und Eigenschaften für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="f8343-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="f8343-144">Führen Sie API-Aufrufe aus, z. \- B. "Empfehlung nach ID abrufen".</span><span class="sxs-lookup"><span data-stu-id="f8343-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="f8343-145">Methoden und Eigenschaften der Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="f8343-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="f8343-146">Führen Sie API-Aufrufe aus, z. \- B. alle Wartungsaufgaben abrufen, die Problembehebungsaufgabe für offen gelegte Geräte abrufen und eine Korrekturaufgabe nach ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="f8343-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="f8343-147">Bewertungsmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="f8343-148">Führen Sie API-Aufrufe aus, z. \- B. das Abrufen der Belichtungsbewertung oder die Geräte-Sicherheitsbewertung.</span><span class="sxs-lookup"><span data-stu-id="f8343-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="f8343-149">Softwaremethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8343-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="f8343-150">Führen Sie API-Aufrufe wie \- z. B. Sicherheitsrisiken nach Software auf.</span><span class="sxs-lookup"><span data-stu-id="f8343-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="f8343-151">Benutzermethoden</span><span class="sxs-lookup"><span data-stu-id="f8343-151">User methods</span></span>](user.md) | <span data-ttu-id="f8343-152">Führen Sie API-Aufrufe aus, z. \- B. das Abrufen von benutzerbezogenen Warnungen und benutzerbezogenen Geräten.</span><span class="sxs-lookup"><span data-stu-id="f8343-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="f8343-153">Methoden und Eigenschaften für Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="f8343-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="f8343-154">Führen Sie API-Aufrufe, z. \- B. Geräte nach Sicherheitsrisiko auflisten, aus.</span><span class="sxs-lookup"><span data-stu-id="f8343-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8343-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8343-155">See also</span></span>

- [<span data-ttu-id="f8343-156">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="f8343-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="f8343-157">Versionshinweise zur Microsoft Defender für Endpunkt-API</span><span class="sxs-lookup"><span data-stu-id="f8343-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
