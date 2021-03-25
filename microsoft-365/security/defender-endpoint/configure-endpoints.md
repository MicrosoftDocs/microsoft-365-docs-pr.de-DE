---
title: Onboarding-Tools und -Methoden für Windows 10-Computer
description: Onboarding von Windows 10-Geräten, damit sie Sensordaten an den Microsoft Defender ATP-Sensor senden können
keywords: Onboarding von Windows 10-Geräten, Gruppenrichtlinie, Endpunktkonfigurations-Manager, Verwaltung mobiler Geräte, lokales Skript, gp, sccm, mdm, intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165537"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="bc7c9-104">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="bc7c9-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc7c9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bc7c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc7c9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc7c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc7c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc7c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="bc7c9-108">Microsoft 365 Endpoint Data Loss Prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="bc7c9-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="bc7c9-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bc7c9-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc7c9-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bc7c9-111">Geräte in Ihrer Organisation müssen so konfiguriert werden, dass der Defender for Endpoint-Dienst Sensordaten von ihnen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="bc7c9-112">Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Konfigurieren der Geräte in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="bc7c9-113">Die folgenden Bereitstellungstools und -methoden werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bc7c9-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="bc7c9-114">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bc7c9-114">Group Policy</span></span>
- <span data-ttu-id="bc7c9-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc7c9-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="bc7c9-116">Verwaltung mobiler Geräte (einschließlich Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="bc7c9-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="bc7c9-117">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="bc7c9-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bc7c9-118">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="bc7c9-118">In this section</span></span>
<span data-ttu-id="bc7c9-119">Thema</span><span class="sxs-lookup"><span data-stu-id="bc7c9-119">Topic</span></span> | <span data-ttu-id="bc7c9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc7c9-120">Description</span></span>
:---|:---
[<span data-ttu-id="bc7c9-121">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bc7c9-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="bc7c9-122">Verwenden Sie Gruppenrichtlinien zum Bereitstellen des Konfigurationspakets auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="bc7c9-123">Onboarding von Windows-Geräten mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc7c9-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="bc7c9-124">Sie können entweder Microsoft Endpoint Manager (current branch) Version 1606 oder Microsoft Endpoint Manager (current branch) version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="bc7c9-125">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="bc7c9-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="bc7c9-126">Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="bc7c9-127">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="bc7c9-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="bc7c9-128">Erfahren Sie, wie Sie das lokale Skript zum Bereitstellen des Konfigurationspakets auf Endpunkten verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="bc7c9-129">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="bc7c9-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="bc7c9-130">Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="bc7c9-131">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bc7c9-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc7c9-132">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bc7c9-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
