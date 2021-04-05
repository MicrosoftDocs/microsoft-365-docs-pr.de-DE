---
title: Ressourcentyp "Untersuchung"
description: Microsoft Defender for Endpoint Investigation-Entität.
keywords: apis, graph api, supported apis, get, alerts, investigations
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587683"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="8661f-104">Ressourcentyp "Untersuchung"</span><span class="sxs-lookup"><span data-stu-id="8661f-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8661f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8661f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8661f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8661f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8661f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8661f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8661f-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8661f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8661f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8661f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="8661f-110">Stellen Sie eine Automatisierte Untersuchungsentität in Defender for Endpoint dar.</span><span class="sxs-lookup"><span data-stu-id="8661f-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="8661f-111">Weitere [Informationen finden Sie unter Übersicht](automated-investigations.md) über automatisierte Untersuchungen.</span><span class="sxs-lookup"><span data-stu-id="8661f-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="8661f-112">Methoden</span><span class="sxs-lookup"><span data-stu-id="8661f-112">Methods</span></span>
<span data-ttu-id="8661f-113">Methode</span><span class="sxs-lookup"><span data-stu-id="8661f-113">Method</span></span>|<span data-ttu-id="8661f-114">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="8661f-114">Return Type</span></span> |<span data-ttu-id="8661f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8661f-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="8661f-116">Auflisten von Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="8661f-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="8661f-117">Untersuchungssammlung</span><span class="sxs-lookup"><span data-stu-id="8661f-117">Investigation collection</span></span> | <span data-ttu-id="8661f-118">Sammlung von Investigation erhalten</span><span class="sxs-lookup"><span data-stu-id="8661f-118">Get collection of Investigation</span></span>
[<span data-ttu-id="8661f-119">Einzelne Untersuchung erhalten</span><span class="sxs-lookup"><span data-stu-id="8661f-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="8661f-120">Untersuchungsentität</span><span class="sxs-lookup"><span data-stu-id="8661f-120">Investigation entity</span></span> | <span data-ttu-id="8661f-121">Ruft eine einzelne Investigation-Entität ab.</span><span class="sxs-lookup"><span data-stu-id="8661f-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="8661f-122">Untersuchung starten</span><span class="sxs-lookup"><span data-stu-id="8661f-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="8661f-123">Untersuchungsentität</span><span class="sxs-lookup"><span data-stu-id="8661f-123">Investigation entity</span></span> | <span data-ttu-id="8661f-124">Startet die Untersuchung auf einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="8661f-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="8661f-125">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8661f-125">Properties</span></span>
<span data-ttu-id="8661f-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8661f-126">Property</span></span> |  <span data-ttu-id="8661f-127">Typ</span><span class="sxs-lookup"><span data-stu-id="8661f-127">Type</span></span>    |   <span data-ttu-id="8661f-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8661f-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="8661f-129">id</span><span class="sxs-lookup"><span data-stu-id="8661f-129">id</span></span> | <span data-ttu-id="8661f-130">String</span><span class="sxs-lookup"><span data-stu-id="8661f-130">String</span></span> | <span data-ttu-id="8661f-131">Identität der Untersuchungsentität.</span><span class="sxs-lookup"><span data-stu-id="8661f-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="8661f-132">startTime</span><span class="sxs-lookup"><span data-stu-id="8661f-132">startTime</span></span> | <span data-ttu-id="8661f-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="8661f-133">DateTime Nullable</span></span> | <span data-ttu-id="8661f-134">Das Datum und die Uhrzeit, zu der die Untersuchung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8661f-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="8661f-135">endTime</span><span class="sxs-lookup"><span data-stu-id="8661f-135">endTime</span></span> | <span data-ttu-id="8661f-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="8661f-136">DateTime Nullable</span></span> | <span data-ttu-id="8661f-137">Datum und Uhrzeit des Abschlusses der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="8661f-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="8661f-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="8661f-138">cancelledBy</span></span> | <span data-ttu-id="8661f-139">String</span><span class="sxs-lookup"><span data-stu-id="8661f-139">String</span></span> | <span data-ttu-id="8661f-140">Die ID des Benutzers/der Anwendung, der diese Untersuchung abgebrochen hat.</span><span class="sxs-lookup"><span data-stu-id="8661f-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="8661f-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="8661f-141">investigationState</span></span> | <span data-ttu-id="8661f-142">Enum</span><span class="sxs-lookup"><span data-stu-id="8661f-142">Enum</span></span> | <span data-ttu-id="8661f-143">Der aktuelle Status der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="8661f-143">The current state of the investigation.</span></span> <span data-ttu-id="8661f-144">Mögliche Werte sind: "Unknown", "Terminated", "SuccessfullyRemediated", "Benign", "Failed", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".</span><span class="sxs-lookup"><span data-stu-id="8661f-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="8661f-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="8661f-145">statusDetails</span></span> | <span data-ttu-id="8661f-146">String</span><span class="sxs-lookup"><span data-stu-id="8661f-146">String</span></span> | <span data-ttu-id="8661f-147">Zusätzliche Informationen zum Untersuchungsstatus.</span><span class="sxs-lookup"><span data-stu-id="8661f-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="8661f-148">machineId</span><span class="sxs-lookup"><span data-stu-id="8661f-148">machineId</span></span> | <span data-ttu-id="8661f-149">String</span><span class="sxs-lookup"><span data-stu-id="8661f-149">String</span></span> | <span data-ttu-id="8661f-150">Die ID des Geräts, auf dem die Untersuchung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8661f-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="8661f-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="8661f-151">computerDnsName</span></span> | <span data-ttu-id="8661f-152">String</span><span class="sxs-lookup"><span data-stu-id="8661f-152">String</span></span> | <span data-ttu-id="8661f-153">Der Name des Geräts, auf dem die Untersuchung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8661f-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="8661f-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="8661f-154">triggeringAlertId</span></span> | <span data-ttu-id="8661f-155">String</span><span class="sxs-lookup"><span data-stu-id="8661f-155">String</span></span> | <span data-ttu-id="8661f-156">Die ID der Warnung, die die Untersuchung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="8661f-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="8661f-157">Json-Darstellung</span><span class="sxs-lookup"><span data-stu-id="8661f-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
