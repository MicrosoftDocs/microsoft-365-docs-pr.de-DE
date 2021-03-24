---
title: Offboardgeräte aus dem Microsoft Defender ATP-Dienst
description: Onboarding von Windows 10-Geräten, -Servern und Nicht-Windows-Geräten aus dem Microsoft Defender ATP-Dienst
keywords: offboarding, microsoft defender for endpoint offboarding, windows atp offboarding
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
ms.openlocfilehash: db22a19da58ba70ff09af781ca56e0b3c0d88dfd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061176"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="709c9-104">Offboardgeräte aus dem Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="709c9-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="709c9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="709c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="709c9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="709c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="709c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="709c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="709c9-108">**Plattformen**</span><span class="sxs-lookup"><span data-stu-id="709c9-108">**Platforms**</span></span>
- <span data-ttu-id="709c9-109">macOS</span><span class="sxs-lookup"><span data-stu-id="709c9-109">macOS</span></span>
- <span data-ttu-id="709c9-110">Linux</span><span class="sxs-lookup"><span data-stu-id="709c9-110">Linux</span></span>
- <span data-ttu-id="709c9-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="709c9-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="709c9-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="709c9-112">Windows Server 2016</span></span>

><span data-ttu-id="709c9-113">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="709c9-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="709c9-114">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="709c9-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="709c9-115">Befolgen Sie die entsprechenden Anweisungen in Abhängigkeit von Ihrer bevorzugten Bereitstellungsmethode.</span><span class="sxs-lookup"><span data-stu-id="709c9-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="709c9-116">Der Status eines Geräts wird 7 Tage nach dem Offboarding in [Inaktiv](fix-unhealthy-sensors.md#inactive-devices) geschaltet.</span><span class="sxs-lookup"><span data-stu-id="709c9-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="709c9-117">Daten von Offboardgeräten (z. B. Zeitachse, Warnungen, Sicherheitsrisiken usw.) verbleiben im Portal, bis der [konfigurierte](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) Aufbewahrungszeitraum abläuft.</span><span class="sxs-lookup"><span data-stu-id="709c9-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="709c9-118">Das Geräteprofil (ohne Daten) bleibt [](machines-view-overview.md) nicht länger als 180 Tage in der Geräteliste.</span><span class="sxs-lookup"><span data-stu-id="709c9-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="709c9-119">Darüber hinaus werden Geräte, die in den letzten 30 Tagen nicht aktiv sind, nicht mit [](tvm-exposure-score.md) den Daten in Verbindung mit der Gefährdungs- und Sicherheitsrisikoverwaltung ihrer Organisation und der Microsoft Secure Score für Geräte verwendet.</span><span class="sxs-lookup"><span data-stu-id="709c9-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="709c9-120">Wenn Sie nur aktive Geräte anzeigen möchten, können Sie nach [Integritätsstatus,](machines-view-overview.md#health-state) [Gerätetags oder](machine-tags.md) [Computergruppen filtern.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="709c9-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="709c9-121">Offboard für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="709c9-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="709c9-122">Offboardgeräte mit einem lokalen Skript</span><span class="sxs-lookup"><span data-stu-id="709c9-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="709c9-123">Offboardgeräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="709c9-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="709c9-124">Offboardgeräte mit Mobile Device Management Tools</span><span class="sxs-lookup"><span data-stu-id="709c9-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="709c9-125">Offboardserver</span><span class="sxs-lookup"><span data-stu-id="709c9-125">Offboard Servers</span></span>
- [<span data-ttu-id="709c9-126">Offboardserver</span><span class="sxs-lookup"><span data-stu-id="709c9-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="709c9-127">Offboard-Nicht-Windows-Geräte</span><span class="sxs-lookup"><span data-stu-id="709c9-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="709c9-128">Offboard-Nicht-Windows-Geräte</span><span class="sxs-lookup"><span data-stu-id="709c9-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

