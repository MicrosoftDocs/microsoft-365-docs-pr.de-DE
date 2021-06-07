---
title: Benutzerressourcentyp
description: Abrufen der letzten Microsoft Defender für Endpunkt-Warnungen im Zusammenhang mit Benutzern.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
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
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772137"
---
# <a name="user-resource-type"></a><span data-ttu-id="c113d-104">Benutzerressourcentyp</span><span class="sxs-lookup"><span data-stu-id="c113d-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c113d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c113d-105">**Applies to:**</span></span>
- [<span data-ttu-id="c113d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c113d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c113d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c113d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c113d-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c113d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c113d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c113d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="c113d-110">Methode</span><span class="sxs-lookup"><span data-stu-id="c113d-110">Method</span></span>|<span data-ttu-id="c113d-111">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="c113d-111">Return Type</span></span> |<span data-ttu-id="c113d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c113d-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="c113d-113">Benutzerbezogene Warnungen auflisten</span><span class="sxs-lookup"><span data-stu-id="c113d-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="c113d-114">[Warnung](alerts.md) Sammlung</span><span class="sxs-lookup"><span data-stu-id="c113d-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="c113d-115">Listet alle Warnungen auf, die einem [Benutzer](user.md)zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c113d-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="c113d-116">Benutzerbezogene Geräte auflisten</span><span class="sxs-lookup"><span data-stu-id="c113d-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="c113d-117">[Computersammlung](machine.md)</span><span class="sxs-lookup"><span data-stu-id="c113d-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="c113d-118">Listet alle Geräte auf, die von einem [Benutzer](user.md)angemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="c113d-118">List all the devices that were logged on by a [user](user.md).</span></span>
