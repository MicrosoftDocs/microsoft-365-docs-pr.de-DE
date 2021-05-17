---
title: Benutzerressourcentyp
description: Abrufen der letzten Microsoft Defender for Endpoint-Warnungen im Zusammenhang mit Benutzern.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197957"
---
# <a name="user-resource-type"></a><span data-ttu-id="5cfed-104">Benutzerressourcentyp</span><span class="sxs-lookup"><span data-stu-id="5cfed-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5cfed-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5cfed-105">**Applies to:**</span></span>
- [<span data-ttu-id="5cfed-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5cfed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5cfed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cfed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5cfed-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5cfed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5cfed-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5cfed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="5cfed-110">Methode</span><span class="sxs-lookup"><span data-stu-id="5cfed-110">Method</span></span>|<span data-ttu-id="5cfed-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="5cfed-111">Return Type</span></span> |<span data-ttu-id="5cfed-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cfed-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="5cfed-113">Auflisten von benutzerbezogenen Warnungen</span><span class="sxs-lookup"><span data-stu-id="5cfed-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="5cfed-114">[Warnung](alerts.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="5cfed-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="5cfed-115">Listet alle Warnungen auf, die einem Benutzer zugeordnet [sind.](user.md)</span><span class="sxs-lookup"><span data-stu-id="5cfed-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="5cfed-116">Auflisten benutzerbezogener Geräte</span><span class="sxs-lookup"><span data-stu-id="5cfed-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="5cfed-117">[Computersammlung](machine.md)</span><span class="sxs-lookup"><span data-stu-id="5cfed-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="5cfed-118">Listet alle Geräte auf, die von einem Benutzer angemeldet [wurden.](user.md)</span><span class="sxs-lookup"><span data-stu-id="5cfed-118">List all the devices that were logged on by a [user](user.md).</span></span>
