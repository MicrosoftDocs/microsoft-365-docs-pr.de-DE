---
title: Onboarding-Tools und -Methoden für Windows 10-Computer
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
description: Onboarding Windows 10-Geräten, damit sie Sensordaten an die Microsoft 365 Senden von Compliancelösungen senden können
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917851"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="fc893-103">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="fc893-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="fc893-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fc893-104">**Applies to:**</span></span>
- [<span data-ttu-id="fc893-105">Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="fc893-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="fc893-106">Geräte in Ihrer Organisation müssen so konfiguriert sein, dass Microsoft 365 Endpoint Data Loss Prevention Service Sensordaten von ihnen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="fc893-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="fc893-107">Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Konfigurieren der Geräte in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fc893-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="fc893-108">Die folgenden Bereitstellungstools und -methoden werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fc893-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="fc893-109">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="fc893-109">group policy</span></span>
- <span data-ttu-id="fc893-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fc893-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="fc893-111">Verwaltung mobiler Geräte (einschließlich Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="fc893-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="fc893-112">lokales Skript</span><span class="sxs-lookup"><span data-stu-id="fc893-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fc893-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="fc893-113">In this section</span></span>
<span data-ttu-id="fc893-114">Thema</span><span class="sxs-lookup"><span data-stu-id="fc893-114">Topic</span></span> | <span data-ttu-id="fc893-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc893-115">Description</span></span>
:---|:---
[<span data-ttu-id="fc893-116">Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fc893-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="fc893-117">Verwenden Sie Gruppenrichtlinien zum Bereitstellen des Konfigurationspakets auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="fc893-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="fc893-118">Onboarding Windows Geräte mithilfe Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fc893-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="fc893-119">Sie können entweder Microsoft Endpoint Configuration Manager (aktuelle Verzweigung) Version 1606 oder Microsoft Endpoint Configuration Manager (current branch) version 1602 oder früher verwenden, um das Konfigurationspaket auf Geräten zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fc893-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="fc893-120">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="fc893-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="fc893-121">Verwenden Sie Tools für die mobile Geräteverwaltung oder Microsoft Intune, um das Konfigurationspaket auf dem Gerät zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fc893-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="fc893-122">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="fc893-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="fc893-123">Erfahren Sie, wie Sie das lokale Skript zum Bereitstellen des Konfigurationspakets auf Endpunkten verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc893-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="fc893-124">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="fc893-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="fc893-125">Erfahren Sie, wie Sie das Konfigurationspaket zum Konfigurieren von VDI-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc893-125">Learn how to use the configuration package to configure VDI devices.</span></span>