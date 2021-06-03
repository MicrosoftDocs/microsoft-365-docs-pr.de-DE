---
title: Übersicht über die Verwaltung und APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die Verwaltungstools und API-Kategorien in Microsoft Defender for Endpoint
keywords: onboarding, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 78ab364f8a261b1201fad17ebf86adc1a7456a46
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730839"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="812ad-104">Übersicht über die Verwaltung und APIs</span><span class="sxs-lookup"><span data-stu-id="812ad-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="812ad-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="812ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="812ad-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="812ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="812ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="812ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="812ad-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="812ad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="812ad-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="812ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="812ad-110">Defender for Endpoint unterstützt eine Vielzahl von Optionen, um sicherzustellen, dass Kunden die Plattform problemlos übernehmen können.</span><span class="sxs-lookup"><span data-stu-id="812ad-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="812ad-111">In der Erkenntnis, dass Kundenumgebungen und -strukturen variieren können, wurde Defender for Endpoint mit Flexibilität und präziser Steuerung erstellt, um unterschiedliche Kundenanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="812ad-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="812ad-112">Endpunkt-Onboarding und Portalzugriff</span><span class="sxs-lookup"><span data-stu-id="812ad-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="812ad-113">Das Geräte onboarding ist vollständig in Microsoft Endpoint Manager und Microsoft Intune für Clientgeräte und Azure Defender für Servergeräte integriert und bietet eine vollständige End-to-End-Erfahrung in Konfiguration, Bereitstellung und Überwachung.</span><span class="sxs-lookup"><span data-stu-id="812ad-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="812ad-114">Darüber hinaus unterstützt Microsoft Defender for Endpoint Gruppenrichtlinien und andere Tools von Drittanbietern, die für die Geräteverwaltung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="812ad-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="812ad-115">Defender for Endpoint bietet eine feinkörnige Kontrolle darüber, was Benutzer mit Zugriff auf das Portal durch die Flexibilität der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) sehen und tun können.</span><span class="sxs-lookup"><span data-stu-id="812ad-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="812ad-116">Das RBAC-Modell unterstützt alle Varianten der Struktur von Sicherheitsteams:</span><span class="sxs-lookup"><span data-stu-id="812ad-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="812ad-117">Global verteilte Organisationen und Sicherheitsteams</span><span class="sxs-lookup"><span data-stu-id="812ad-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="812ad-118">Teams für mehrstufige Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="812ad-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="812ad-119">Vollständig getrennte Abteilungen mit einzelnen zentralen teams für globale Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="812ad-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="812ad-120">Verfügbare APIs</span><span class="sxs-lookup"><span data-stu-id="812ad-120">Available APIs</span></span>
<span data-ttu-id="812ad-121">Die Microsoft Defender for Endpoint-Lösung baut auf einer integrationsbereiten Plattform auf.</span><span class="sxs-lookup"><span data-stu-id="812ad-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="812ad-122">Defender for Endpoint macht einen großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="812ad-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="812ad-123">Mit diesen APIs können Sie Workflows automatisieren und innovationen basierend auf defender for Endpoint-Funktionen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="812ad-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Abbildung der verfügbaren API und Integration in Microsoft Defender for Endpoint](images/mdatp-apis.png)  

<span data-ttu-id="812ad-125">Die Defender for Endpoint-APIs können in drei gruppen:</span><span class="sxs-lookup"><span data-stu-id="812ad-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="812ad-126">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="812ad-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="812ad-127">API für das Streaming von Rohdaten</span><span class="sxs-lookup"><span data-stu-id="812ad-127">Raw data streaming API</span></span>
- <span data-ttu-id="812ad-128">SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="812ad-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="812ad-129">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="812ad-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="812ad-130">Defender for Endpoint bietet ein mehrschichtiges API-Modell, das Daten und Funktionen in einem strukturierten, übersichtlichen und einfach zu verwendenden Modell verfügbar macht, das über ein standardmäßiges Azure AD-basiertes Authentifizierungs- und Autorisierungsmodell verfügbar gemacht wird, das den Zugriff im Kontext von Benutzern oder SaaS-Anwendungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="812ad-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="812ad-131">Das API-Modell wurde entwickelt, um Entitäten und Funktionen in einer konsistenten Form verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="812ad-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="812ad-132">Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender for Endpoint zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="812ad-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="812ad-133">Die **Untersuchungs-API** macht den Reichhaltigen von Defender for Endpoint verfügbar – das Verfügbar machen berechnete oder "profilierte" Entitäten (z. B. Gerät, Benutzer und Datei) und diskrete Ereignisse (z. B. Prozesserstellung und Dateierstellung), die in der Regel ein Verhalten im Zusammenhang mit einer Entität beschreiben und den Zugriff auf Daten über Untersuchungsschnittstellen ermöglichen, die einen abfragebasierten Zugriff auf Daten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="812ad-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="812ad-134">Weitere Informationen finden Sie unter [Supported APIs](exposed-apis-list.md).</span><span class="sxs-lookup"><span data-stu-id="812ad-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="812ad-135">Die **Reaktions-API** macht die Möglichkeit verfügbar, Aktionen im Dienst und auf Geräten zu ergreifen, sodass Kunden Indikatoren abrufen, Einstellungen verwalten, Warnungsstatus verwalten sowie Reaktionsaktionen auf Geräten programmgesteuert ausführen können, z. B. Geräte vom Netzwerk isolieren, Quarantänedateien und andere.</span><span class="sxs-lookup"><span data-stu-id="812ad-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="streaming-api"></a><span data-ttu-id="812ad-136">Streaming-API</span><span class="sxs-lookup"><span data-stu-id="812ad-136">Streaming API</span></span> 
<span data-ttu-id="812ad-137">Die Streaming-API bietet Kunden die Möglichkeit, Echtzeitereignisse und Warnungen von ihren Instanzen innerhalb eines einzelnen Datenstroms zu senden, was einen Mechanismus für die Zustellung mit niedriger Latenz und hohem Durchsatz bietet.</span><span class="sxs-lookup"><span data-stu-id="812ad-137">Streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="812ad-138">Ereignisinformationen werden zur langfristigen Datenaufbewahrung direkt an den Azure-Speicher oder an Azure Event Hubs zur Nutzung durch Visualisierungsdienste oder zusätzliche Datenverarbeitungsmodule bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="812ad-138">Event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

>[!NOTE]
><span data-ttu-id="812ad-139">Die Streaming-API wurde nun zu Microsoft 365 Defender verschoben.</span><span class="sxs-lookup"><span data-stu-id="812ad-139">Streaming API has now moved to Microsoft 365 Defender.</span></span> <span data-ttu-id="812ad-140">Weitere Informationen finden Sie unter [Streaming-API](raw-data-export.md).</span><span class="sxs-lookup"><span data-stu-id="812ad-140">For more information, see [Streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="812ad-141">SIEM-API</span><span class="sxs-lookup"><span data-stu-id="812ad-141">SIEM API</span></span>
<span data-ttu-id="812ad-142">Wenn Sie die Integration von Sicherheitsinformationen und Ereignisverwaltung (SECURITY Information and Event Management, SIEM) aktivieren, können Sie Erkennungen von Microsoft Defender Security Center mithilfe Ihrer SIEM-Lösung abrufen oder eine direkte Verbindung mit der REST-API für Erkennungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="812ad-142">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="812ad-143">Dadurch wird der Abschnitt MITM-Connectorzugriffsdetails mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD) erstellt.</span><span class="sxs-lookup"><span data-stu-id="812ad-143">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="812ad-144">Weitere Informationen finden Sie unter [SIEM-Integration](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="812ad-144">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="812ad-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="812ad-145">Related topics</span></span>
- [<span data-ttu-id="812ad-146">Zugreifen auf die Microsoft Defender for Endpoint-APIs </span><span class="sxs-lookup"><span data-stu-id="812ad-146">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="812ad-147">Unterstützte APIs</span><span class="sxs-lookup"><span data-stu-id="812ad-147">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="812ad-148">Chancen für technische Partner</span><span class="sxs-lookup"><span data-stu-id="812ad-148">Technical partner opportunities</span></span>](partner-integration.md)

