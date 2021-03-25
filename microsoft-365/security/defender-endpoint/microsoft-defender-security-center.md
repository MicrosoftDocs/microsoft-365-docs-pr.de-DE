---
title: Microsoft Defender Security Center
description: Microsoft Defender Security Center ist das Portal, in dem Sie auf Microsoft Defender for Endpoint zugreifen können.
keywords: Windows, Defender, Security, Center, Defender, Advanced, Threat, Protection
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5152a1fa13562f25a8e55617655cab934e886ff0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186617"
---
# <a name="microsoft-defender-security-center"></a><span data-ttu-id="67f36-104">Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="67f36-104">Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67f36-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="67f36-105">**Applies to:**</span></span>
- [<span data-ttu-id="67f36-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="67f36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67f36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67f36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67f36-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="67f36-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67f36-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="67f36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="67f36-110">Microsoft Defender Security Center ist das Portal, in dem Sie auf Microsoft Defender for Endpoint-Funktionen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="67f36-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="67f36-111">Sie bietet Unternehmenssicherheitsteams einen einzigen Fensterausschnitt, um Netzwerke zu schützen.</span><span class="sxs-lookup"><span data-stu-id="67f36-111">It gives enterprise security operations teams a single pane of glass experience to help secure networks.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="67f36-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="67f36-112">In this section</span></span>

<span data-ttu-id="67f36-113">Thema</span><span class="sxs-lookup"><span data-stu-id="67f36-113">Topic</span></span> | <span data-ttu-id="67f36-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67f36-114">Description</span></span>
:---|:---
<span data-ttu-id="67f36-115">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="67f36-115">Get started</span></span>  |  <span data-ttu-id="67f36-116">Erfahren Sie mehr über die Mindestanforderungen, überprüfen Sie die Lizenzierung und das vollständige Setup, erfahren Sie mehr über Vorschaufeatures, wissen Sie mehr über Datenspeicherung und Datenschutz sowie über das Zuweisen von Benutzerzugriff auf das Portal.</span><span class="sxs-lookup"><span data-stu-id="67f36-116">Learn about the minimum requirements, validate licensing and complete setup, know about preview features, understand data storage and privacy, and how to assign user access to the portal.</span></span>
[<span data-ttu-id="67f36-117">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="67f36-117">Onboard devices</span></span>](onboard-configure.md) | <span data-ttu-id="67f36-118">Erfahren Sie mehr über das Onboarding von Client-, Server- und Nicht-Windows-Geräten.</span><span class="sxs-lookup"><span data-stu-id="67f36-118">Learn about onboarding client, server, and non-Windows devices.</span></span> <span data-ttu-id="67f36-119">Erfahren Sie, wie Sie einen Erkennungstest ausführen, Proxy- und Internetverbindungseinstellungen konfigurieren und wie Sie potenzielle Onboardingprobleme beheben.</span><span class="sxs-lookup"><span data-stu-id="67f36-119">Learn how to run a detection test, configure proxy and Internet connectivity settings, and how to troubleshoot potential onboarding issues.</span></span>
[<span data-ttu-id="67f36-120">Verstehen des Portals</span><span class="sxs-lookup"><span data-stu-id="67f36-120">Understand the portal</span></span>](use.md) | <span data-ttu-id="67f36-121">Informationen zu den Sicherheitsvorgängen, Secure Score und Threat Analytics-Dashboards sowie zum Navigieren im Portal.</span><span class="sxs-lookup"><span data-stu-id="67f36-121">Understand the Security operations, Secure Score, and Threat analytics dashboards as well as how to navigate the portal.</span></span>
<span data-ttu-id="67f36-122">Untersuchen und Behebung von Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="67f36-122">Investigate and remediate threats</span></span> | <span data-ttu-id="67f36-123">Untersuchen Sie Warnungen, Geräte und ergreifen Sie Reaktionsaktionen zur Behebung von Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="67f36-123">Investigate alerts, devices, and take response actions to remediate threats.</span></span>
<span data-ttu-id="67f36-124">API- und SIEM-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="67f36-124">API and SIEM support</span></span> | <span data-ttu-id="67f36-125">Verwenden Sie die unterstützten APIs, um benutzerdefinierte Warnungen zu ziehen und zu erstellen oder Workflows zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="67f36-125">Use the supported APIs to pull and create custom alerts, or automate workflows.</span></span> <span data-ttu-id="67f36-126">Verwenden Sie die unterstützten SIEM-Tools, um Warnungen aus dem Microsoft Defender Security Center zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="67f36-126">Use the supported SIEM tools to pull alerts from Microsoft Defender Security Center.</span></span>
<span data-ttu-id="67f36-127">Reporting</span><span class="sxs-lookup"><span data-stu-id="67f36-127">Reporting</span></span> | <span data-ttu-id="67f36-128">Erstellen und Erstellen von Power BI-Berichten mithilfe von Microsoft Defender for Endpoint-Daten.</span><span class="sxs-lookup"><span data-stu-id="67f36-128">Create and build Power BI reports using Microsoft Defender for Endpoint data.</span></span>
<span data-ttu-id="67f36-129">Überprüfen des Dienststatus und des Sensorstatus</span><span class="sxs-lookup"><span data-stu-id="67f36-129">Check service health and sensor state</span></span> | <span data-ttu-id="67f36-130">Überprüfen Sie, ob der Dienst ausgeführt wird, und überprüfen Sie den Sensorstatus auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="67f36-130">Verify that the service is running and check the sensor state on devices.</span></span>
[<span data-ttu-id="67f36-131">Konfigurieren von Microsoft Defender Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="67f36-131">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="67f36-132">Konfigurieren Sie allgemeine Einstellungen, aktivieren Sie die Vorschau, Benachrichtigungen und aktivieren Sie andere Features.</span><span class="sxs-lookup"><span data-stu-id="67f36-132">Configure general settings, turn on the preview experience, notifications, and enable other features.</span></span>
[<span data-ttu-id="67f36-133">Zugreifen auf das Microsoft Defender for Endpoint Community Center</span><span class="sxs-lookup"><span data-stu-id="67f36-133">Access the Microsoft Defender for Endpoint Community Center</span></span>](community.md) | <span data-ttu-id="67f36-134">Greifen Sie auf das Microsoft Defender for Endpoint Community Center zu, um erfahrungen mit dem Produkt zu erfahren, zusammenzuarbeiten und auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="67f36-134">Access the Microsoft Defender for Endpoint Community Center to learn, collaborate, and share experiences about the product.</span></span>
[<span data-ttu-id="67f36-135">Behandeln von Dienstproblemen</span><span class="sxs-lookup"><span data-stu-id="67f36-135">Troubleshoot service issues</span></span>](troubleshoot-mdatp.md) | <span data-ttu-id="67f36-136">In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft Defender for Endpoint-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="67f36-136">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>