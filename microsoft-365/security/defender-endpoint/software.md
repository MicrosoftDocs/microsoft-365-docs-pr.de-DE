---
title: Softwaremethoden und -eigenschaften
description: Ruft die wichtigsten warnungen der letzten Zeit ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771403"
---
# <a name="software-resource-type"></a><span data-ttu-id="79c1e-104">Softwareressourcentyp</span><span class="sxs-lookup"><span data-stu-id="79c1e-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79c1e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="79c1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="79c1e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="79c1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79c1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79c1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="79c1e-108">**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="79c1e-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="79c1e-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="79c1e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79c1e-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="79c1e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="79c1e-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="79c1e-111">Methods</span></span>

<span data-ttu-id="79c1e-112">Methode</span><span class="sxs-lookup"><span data-stu-id="79c1e-112">Method</span></span> |<span data-ttu-id="79c1e-113">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="79c1e-113">Return Type</span></span> |<span data-ttu-id="79c1e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79c1e-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="79c1e-115">Software auflisten</span><span class="sxs-lookup"><span data-stu-id="79c1e-115">List software</span></span>](get-software.md) | <span data-ttu-id="79c1e-116">Softwaresammlung</span><span class="sxs-lookup"><span data-stu-id="79c1e-116">Software collection</span></span> | <span data-ttu-id="79c1e-117">Auflisten des Softwarebestands der Organisation.</span><span class="sxs-lookup"><span data-stu-id="79c1e-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="79c1e-118">Software nach ID erhalten</span><span class="sxs-lookup"><span data-stu-id="79c1e-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="79c1e-119">Software</span><span class="sxs-lookup"><span data-stu-id="79c1e-119">Software</span></span> | <span data-ttu-id="79c1e-120">Rufen Sie eine bestimmte Software anhand ihrer Software-ID ab.</span><span class="sxs-lookup"><span data-stu-id="79c1e-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="79c1e-121">Softwareversionsverteilung auflisten</span><span class="sxs-lookup"><span data-stu-id="79c1e-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="79c1e-122">Distributionssammlung</span><span class="sxs-lookup"><span data-stu-id="79c1e-122">Distribution collection</span></span> | <span data-ttu-id="79c1e-123">Auflisten der Softwareversionsverteilung nach Software-ID.</span><span class="sxs-lookup"><span data-stu-id="79c1e-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="79c1e-124">Auflisten von Computern nach Software</span><span class="sxs-lookup"><span data-stu-id="79c1e-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="79c1e-125">MachineRef-Sammlung</span><span class="sxs-lookup"><span data-stu-id="79c1e-125">MachineRef collection</span></span> | <span data-ttu-id="79c1e-126">Rufen Sie eine Liste der Geräte ab, die der Software-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="79c1e-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="79c1e-127">Auflisten von Sicherheitsrisiken nach Software</span><span class="sxs-lookup"><span data-stu-id="79c1e-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="79c1e-128">[Sammlung von Sicherheitsrisiken](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="79c1e-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="79c1e-129">Rufen Sie eine Liste der Sicherheitsrisiken ab, die der Software-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="79c1e-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="79c1e-130">Fehlende KBs erhalten</span><span class="sxs-lookup"><span data-stu-id="79c1e-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="79c1e-131">KB-Auflistung</span><span class="sxs-lookup"><span data-stu-id="79c1e-131">KB collection</span></span> | <span data-ttu-id="79c1e-132">Abrufen einer Liste fehlender KBs, die der Software-ID zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="79c1e-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="79c1e-133">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="79c1e-133">Properties</span></span>

<span data-ttu-id="79c1e-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="79c1e-134">Property</span></span> |   <span data-ttu-id="79c1e-135">Typ</span><span class="sxs-lookup"><span data-stu-id="79c1e-135">Type</span></span>   |   <span data-ttu-id="79c1e-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79c1e-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="79c1e-137">id</span><span class="sxs-lookup"><span data-stu-id="79c1e-137">id</span></span> | <span data-ttu-id="79c1e-138">String</span><span class="sxs-lookup"><span data-stu-id="79c1e-138">String</span></span> | <span data-ttu-id="79c1e-139">Software-ID</span><span class="sxs-lookup"><span data-stu-id="79c1e-139">Software ID</span></span>
<span data-ttu-id="79c1e-140">Name</span><span class="sxs-lookup"><span data-stu-id="79c1e-140">Name</span></span> | <span data-ttu-id="79c1e-141">String</span><span class="sxs-lookup"><span data-stu-id="79c1e-141">String</span></span> | <span data-ttu-id="79c1e-142">Softwarename</span><span class="sxs-lookup"><span data-stu-id="79c1e-142">Software name</span></span>
<span data-ttu-id="79c1e-143">Anbieter</span><span class="sxs-lookup"><span data-stu-id="79c1e-143">Vendor</span></span> | <span data-ttu-id="79c1e-144">String</span><span class="sxs-lookup"><span data-stu-id="79c1e-144">String</span></span> | <span data-ttu-id="79c1e-145">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="79c1e-145">Software vendor name</span></span>
<span data-ttu-id="79c1e-146">Schwächen</span><span class="sxs-lookup"><span data-stu-id="79c1e-146">Weaknesses</span></span> | <span data-ttu-id="79c1e-147">Long</span><span class="sxs-lookup"><span data-stu-id="79c1e-147">Long</span></span> | <span data-ttu-id="79c1e-148">Anzahl der entdeckten Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="79c1e-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="79c1e-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="79c1e-149">publicExploit</span></span> | <span data-ttu-id="79c1e-150">Boolesch</span><span class="sxs-lookup"><span data-stu-id="79c1e-150">Boolean</span></span> | <span data-ttu-id="79c1e-151">Öffentliche Exploits sind für einige der Sicherheitsrisiken vorhanden</span><span class="sxs-lookup"><span data-stu-id="79c1e-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="79c1e-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="79c1e-152">activeAlert</span></span> | <span data-ttu-id="79c1e-153">Boolesch</span><span class="sxs-lookup"><span data-stu-id="79c1e-153">Boolean</span></span> | <span data-ttu-id="79c1e-154">Dieser Software ist eine aktive Warnung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="79c1e-154">Active alert is associated with this software</span></span>
<span data-ttu-id="79c1e-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="79c1e-155">exposedMachines</span></span> | <span data-ttu-id="79c1e-156">Long</span><span class="sxs-lookup"><span data-stu-id="79c1e-156">Long</span></span> | <span data-ttu-id="79c1e-157">Anzahl der verfügbar gemachten Geräte</span><span class="sxs-lookup"><span data-stu-id="79c1e-157">Number of exposed devices</span></span>
<span data-ttu-id="79c1e-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="79c1e-158">impactScore</span></span> | <span data-ttu-id="79c1e-159">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="79c1e-159">Double</span></span> | <span data-ttu-id="79c1e-160">Auswirkung dieser Software auf die Belichtungsbewertung</span><span class="sxs-lookup"><span data-stu-id="79c1e-160">Exposure score impact of this software</span></span>
