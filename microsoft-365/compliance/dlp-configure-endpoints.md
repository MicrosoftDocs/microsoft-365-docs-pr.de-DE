---
title: Onboarding-Tools und-Methoden für Windows 10-Geräte (Vorschau)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Onboard-Windows 10-Geräte, sodass Sie Sensordaten an die Microsoft 365-Kompatibilitätslösungen senden können
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769642"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="74010-103">Onboarding-Tools und-Methoden für Windows 10-Geräte (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="74010-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="74010-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="74010-104">**Applies to:**</span></span>
- [<span data-ttu-id="74010-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="74010-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="74010-106">Geräte in Ihrer Organisation müssen so konfiguriert werden, dass der Microsoft 365-Endpunkt für die Datenverlust-Verhinderung Sensordaten von diesen abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="74010-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="74010-107">Es gibt verschiedene Methoden und Bereitstellungstools, mit denen Sie die Geräte in Ihrer Organisation konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="74010-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="74010-108">Die folgenden Bereitstellungstools und-Methoden werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="74010-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="74010-109">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="74010-109">group policy</span></span>
- <span data-ttu-id="74010-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="74010-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="74010-111">Verwaltung mobiler Geräte (einschließlich Microsoft InTune)</span><span class="sxs-lookup"><span data-stu-id="74010-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="74010-112">lokales Skript</span><span class="sxs-lookup"><span data-stu-id="74010-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="74010-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="74010-113">In this section</span></span>
<span data-ttu-id="74010-114">Thema</span><span class="sxs-lookup"><span data-stu-id="74010-114">Topic</span></span> | <span data-ttu-id="74010-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74010-115">Description</span></span>
:---|:---
[<span data-ttu-id="74010-116">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="74010-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="74010-117">Verwenden Sie Gruppenrichtlinien, um das Konfigurationspaket auf Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="74010-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="74010-118">Onboard-Windows-Geräte mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="74010-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="74010-119">Sie können entweder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung) Version 1606 oder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung) Version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="74010-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="74010-120">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="74010-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="74010-121">Verwenden Sie die Tools zur Verwaltung mobiler Geräte oder Microsoft InTune, um das Konfigurationspaket auf dem Gerät bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="74010-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="74010-122">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="74010-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="74010-123">Erfahren Sie, wie Sie mit dem lokalen Skript das Konfigurationspaket auf Endpunkten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="74010-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="74010-124">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="74010-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="74010-125">Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="74010-125">Learn how to use the configuration package to configure VDI devices.</span></span>
