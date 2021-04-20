---
title: Onboarding-Tools und -Methoden für Windows 10-Computer
description: Onboarding von Windows 10-Geräten, damit sie Sensordaten an den Microsoft Defender for Endpoint-Sensor senden können
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892829"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="0d197-104">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="0d197-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0d197-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0d197-105">**Applies to:**</span></span>
- [<span data-ttu-id="0d197-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0d197-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0d197-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d197-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="0d197-108">Microsoft 365 Endpoint Data Loss Prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="0d197-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="0d197-109">Microsoft 365 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="0d197-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="0d197-110">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0d197-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0d197-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0d197-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="0d197-112">Geräte in Ihrer Organisation müssen so konfiguriert werden, dass der Defender for Endpoint-Dienst Sensordaten von ihnen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="0d197-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="0d197-113">Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Konfigurieren der Geräte in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0d197-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="0d197-114">Die folgenden Bereitstellungstools und -methoden werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0d197-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="0d197-115">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0d197-115">Group Policy</span></span>
- <span data-ttu-id="0d197-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0d197-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0d197-117">Verwaltung mobiler Geräte (einschließlich Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="0d197-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="0d197-118">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="0d197-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0d197-119">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="0d197-119">In this section</span></span>
<span data-ttu-id="0d197-120">Thema</span><span class="sxs-lookup"><span data-stu-id="0d197-120">Topic</span></span> | <span data-ttu-id="0d197-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d197-121">Description</span></span>
:---|:---
[<span data-ttu-id="0d197-122">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0d197-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="0d197-123">Verwenden Sie Gruppenrichtlinien zum Bereitstellen des Konfigurationspakets auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="0d197-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0d197-124">Onboarding von Windows-Geräten mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0d197-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="0d197-125">Sie können entweder Microsoft Endpoint Manager (current branch) Version 1606 oder Microsoft Endpoint Manager (current branch) version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0d197-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0d197-126">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="0d197-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="0d197-127">Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d197-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="0d197-128">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="0d197-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="0d197-129">Erfahren Sie, wie Sie das lokale Skript zum Bereitstellen des Konfigurationspakets auf Endpunkten verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d197-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="0d197-130">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="0d197-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="0d197-131">Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d197-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="0d197-132">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0d197-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0d197-133">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0d197-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
