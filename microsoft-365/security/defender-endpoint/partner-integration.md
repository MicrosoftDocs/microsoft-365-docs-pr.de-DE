---
title: Microsoft Defender for Endpoint-Partnerchancen und -szenarien
ms.reviewer: ''
description: Erfahren Sie, wie Sie vorhandene Sicherheitsangebote über das offene Framework und einen reichhaltigen Satz von APIs zum Erstellen von Erweiterungen und Integrationen in Microsoft Defender for Endpoint erweitern können.
keywords: API, Partner, extend, open framework, apis, extensions, integrations, detection, management, response, vulnerabilities, intelligence
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
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861109"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="a8b17-104">Microsoft Defender for Endpoint-Partnerchancen und -szenarien</span><span class="sxs-lookup"><span data-stu-id="a8b17-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8b17-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a8b17-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8b17-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a8b17-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a8b17-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8b17-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a8b17-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a8b17-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a8b17-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a8b17-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="a8b17-110">Partner können ihre vorhandenen Sicherheitsangebote auf einfache Weise über das offene Framework und einen reichhaltigen und vollständigen Satz von APIs erweitern, um Erweiterungen und Integrationen mit Defender for Endpoint zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8b17-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="a8b17-111">Die APIs umfassen Funktionsbereiche wie Erkennung, Verwaltung, Reaktion, Sicherheitsrisiken und intelligenceweite Anwendungsbereiche.</span><span class="sxs-lookup"><span data-stu-id="a8b17-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="a8b17-112">Je nach Fall und Bedarf können Partner Daten von Defender for Endpoint streamen oder abfragen.</span><span class="sxs-lookup"><span data-stu-id="a8b17-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="a8b17-113">Szenario 1: Korrelation externer Warnungen und automatisierte Untersuchung und Behebung</span><span class="sxs-lookup"><span data-stu-id="a8b17-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="a8b17-114">Defender for Endpoint bietet einzigartige automatisierte Untersuchungs- und Behebungsfunktionen, um die Reaktion auf Vorfälle in einem großen Umfang zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a8b17-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="a8b17-115">Die Integration der automatisierten Untersuchungs- und Reaktionsfunktionen in andere Lösungen wie Netzwerksicherheitsprodukte oder andere Endpunktsicherheitsprodukte hilft bei der Problembeantwortung.</span><span class="sxs-lookup"><span data-stu-id="a8b17-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="a8b17-116">Durch die Integration werden auch die Komplexitäten der Netzwerk- und Gerätesignalkorrelation minimiert und die Untersuchungs- und Bedrohungsbehebungsmaßnahmen auf Geräten effektiv reduziert.</span><span class="sxs-lookup"><span data-stu-id="a8b17-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="a8b17-117">Defender for Endpoint bietet unterstützung für dieses Szenario in den folgenden Formen:</span><span class="sxs-lookup"><span data-stu-id="a8b17-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="a8b17-118">Externe Warnungen können in Defender for Endpoint übertragen und neben zusätzlichen gerätebasierten Warnungen von Defender for Endpoint angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a8b17-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="a8b17-119">Diese Ansicht bietet den vollständigen Kontext der Warnung – mit dem tatsächlichen Prozess und der vollständigen Angriffsgeschichte.</span><span class="sxs-lookup"><span data-stu-id="a8b17-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="a8b17-120">Sobald eine Warnung generiert wurde, wird das Signal für alle geschützten Defender for Endpoint-Endpunkte im Unternehmen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a8b17-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="a8b17-121">Defender for Endpoint reagiert sofort automatisiert oder vom Operator unterstützt, um die Warnung zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="a8b17-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="a8b17-122">Szenario 2: Integration von Sicherheits orchestrierung und Automatisierungsantwort (SOAR)</span><span class="sxs-lookup"><span data-stu-id="a8b17-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="a8b17-123">Orchestrierungslösungen können beim Erstellen von Playbooks helfen und das umfassende Datenmodell und die Aktionen integrieren, die Defender for Endpoint-APIs für orchestrierte Antworten verfügbar machen, z. B. Abfrage nach Gerätedaten, Auslösen der Geräteisolation, Blockieren/Zulassen, Auflösen von Warnungen und andere.</span><span class="sxs-lookup"><span data-stu-id="a8b17-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="a8b17-124">Szenario 3: Abgleich von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="a8b17-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="a8b17-125">Der Kompromissindikator (IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung.</span><span class="sxs-lookup"><span data-stu-id="a8b17-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="a8b17-126">Diese Funktion ist in Defender for Endpoint verfügbar und bietet die Möglichkeit, eine Liste von Indikatoren für die Verhinderung, Erkennung und den Ausschluss von Entitäten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8b17-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="a8b17-127">Sie können die zu ergreifende Aktion sowie die Dauer für die Anwendung der Aktion definieren.</span><span class="sxs-lookup"><span data-stu-id="a8b17-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="a8b17-128">Die obigen Szenarien dienen als Beispiele für die Erweiterbarkeit der Plattform.</span><span class="sxs-lookup"><span data-stu-id="a8b17-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="a8b17-129">Sie sind nicht auf die Beispiele beschränkt, und wir empfehlen Ihnen, das offene Framework zu nutzen, um andere Szenarien zu entdecken und zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="a8b17-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="a8b17-130">Führen Sie die Schritte unter [Microsoft Defender for Endpoint-Partner](get-started-partner-integration.md) werden aus, um Ihre Lösung in Defender for Endpoint zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="a8b17-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a8b17-131">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="a8b17-131">Related topic</span></span>
- [<span data-ttu-id="a8b17-132">Übersicht über die Verwaltung und APIs</span><span class="sxs-lookup"><span data-stu-id="a8b17-132">Overview of management and APIs</span></span>](management-apis.md)
