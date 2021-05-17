---
title: Softwaremethoden und -eigenschaften
description: Ruft die aktuellsten Warnungen ab.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187198"
---
# <a name="software-resource-type"></a><span data-ttu-id="d41ee-104">Softwareressourcentyp</span><span class="sxs-lookup"><span data-stu-id="d41ee-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d41ee-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d41ee-105">**Applies to:**</span></span>
- [<span data-ttu-id="d41ee-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d41ee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d41ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d41ee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d41ee-108">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d41ee-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d41ee-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d41ee-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d41ee-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d41ee-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="d41ee-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="d41ee-111">Methods</span></span>

<span data-ttu-id="d41ee-112">Methode</span><span class="sxs-lookup"><span data-stu-id="d41ee-112">Method</span></span> |<span data-ttu-id="d41ee-113">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="d41ee-113">Return Type</span></span> |<span data-ttu-id="d41ee-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d41ee-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="d41ee-115">Software auflisten</span><span class="sxs-lookup"><span data-stu-id="d41ee-115">List software</span></span>](get-software.md) | <span data-ttu-id="d41ee-116">Softwaresammlung</span><span class="sxs-lookup"><span data-stu-id="d41ee-116">Software collection</span></span> | <span data-ttu-id="d41ee-117">Listet das Inventar der Organisationssoftware auf.</span><span class="sxs-lookup"><span data-stu-id="d41ee-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="d41ee-118">Software nach ID erhalten</span><span class="sxs-lookup"><span data-stu-id="d41ee-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="d41ee-119">Software</span><span class="sxs-lookup"><span data-stu-id="d41ee-119">Software</span></span> | <span data-ttu-id="d41ee-120">Erhalten Sie eine bestimmte Software nach ihrer Software-ID.</span><span class="sxs-lookup"><span data-stu-id="d41ee-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="d41ee-121">Softwareversionsverteilung auflisten</span><span class="sxs-lookup"><span data-stu-id="d41ee-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="d41ee-122">Verteilungssammlung</span><span class="sxs-lookup"><span data-stu-id="d41ee-122">Distribution collection</span></span> | <span data-ttu-id="d41ee-123">Listet die Softwareversionsverteilung nach Software-ID auf.</span><span class="sxs-lookup"><span data-stu-id="d41ee-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="d41ee-124">Auflisten von Computern nach Software</span><span class="sxs-lookup"><span data-stu-id="d41ee-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="d41ee-125">MachineRef-Auflistung</span><span class="sxs-lookup"><span data-stu-id="d41ee-125">MachineRef collection</span></span> | <span data-ttu-id="d41ee-126">Rufen Sie eine Liste der Geräte ab, die der Software-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d41ee-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="d41ee-127">Auflisten von Sicherheitsrisiken nach Software</span><span class="sxs-lookup"><span data-stu-id="d41ee-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="d41ee-128">[Vulnerability-Auflistung](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="d41ee-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="d41ee-129">Rufen Sie eine Liste der Sicherheitsrisiken ab, die der Software-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d41ee-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="d41ee-130">Fehlende KBs erhalten</span><span class="sxs-lookup"><span data-stu-id="d41ee-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="d41ee-131">KB-Auflistung</span><span class="sxs-lookup"><span data-stu-id="d41ee-131">KB collection</span></span> | <span data-ttu-id="d41ee-132">Erhalten einer Liste fehlender KBs, die der Software-ID zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="d41ee-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="d41ee-133">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d41ee-133">Properties</span></span>

<span data-ttu-id="d41ee-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d41ee-134">Property</span></span> |   <span data-ttu-id="d41ee-135">Typ</span><span class="sxs-lookup"><span data-stu-id="d41ee-135">Type</span></span>   |   <span data-ttu-id="d41ee-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d41ee-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="d41ee-137">id</span><span class="sxs-lookup"><span data-stu-id="d41ee-137">id</span></span> | <span data-ttu-id="d41ee-138">String</span><span class="sxs-lookup"><span data-stu-id="d41ee-138">String</span></span> | <span data-ttu-id="d41ee-139">Software-ID</span><span class="sxs-lookup"><span data-stu-id="d41ee-139">Software ID</span></span>
<span data-ttu-id="d41ee-140">Name</span><span class="sxs-lookup"><span data-stu-id="d41ee-140">Name</span></span> | <span data-ttu-id="d41ee-141">String</span><span class="sxs-lookup"><span data-stu-id="d41ee-141">String</span></span> | <span data-ttu-id="d41ee-142">Softwarename</span><span class="sxs-lookup"><span data-stu-id="d41ee-142">Software name</span></span>
<span data-ttu-id="d41ee-143">Anbieter</span><span class="sxs-lookup"><span data-stu-id="d41ee-143">Vendor</span></span> | <span data-ttu-id="d41ee-144">String</span><span class="sxs-lookup"><span data-stu-id="d41ee-144">String</span></span> | <span data-ttu-id="d41ee-145">Name des Softwareanbieters</span><span class="sxs-lookup"><span data-stu-id="d41ee-145">Software vendor name</span></span>
<span data-ttu-id="d41ee-146">Schwächen</span><span class="sxs-lookup"><span data-stu-id="d41ee-146">Weaknesses</span></span> | <span data-ttu-id="d41ee-147">Long</span><span class="sxs-lookup"><span data-stu-id="d41ee-147">Long</span></span> | <span data-ttu-id="d41ee-148">Anzahl der erkannten Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="d41ee-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="d41ee-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="d41ee-149">publicExploit</span></span> | <span data-ttu-id="d41ee-150">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d41ee-150">Boolean</span></span> | <span data-ttu-id="d41ee-151">Für einige der Sicherheitsrisiken ist ein öffentlicher Exploit vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d41ee-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="d41ee-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="d41ee-152">activeAlert</span></span> | <span data-ttu-id="d41ee-153">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d41ee-153">Boolean</span></span> | <span data-ttu-id="d41ee-154">Dieser Software ist eine aktive Warnung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d41ee-154">Active alert is associated with this software</span></span>
<span data-ttu-id="d41ee-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="d41ee-155">exposedMachines</span></span> | <span data-ttu-id="d41ee-156">Long</span><span class="sxs-lookup"><span data-stu-id="d41ee-156">Long</span></span> | <span data-ttu-id="d41ee-157">Anzahl der verfügbar gemachten Geräte</span><span class="sxs-lookup"><span data-stu-id="d41ee-157">Number of exposed devices</span></span>
<span data-ttu-id="d41ee-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="d41ee-158">impactScore</span></span> | <span data-ttu-id="d41ee-159">Gleitkommawert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="d41ee-159">Double</span></span> | <span data-ttu-id="d41ee-160">Auswirkungen dieser Software auf die Belichtungswertung</span><span class="sxs-lookup"><span data-stu-id="d41ee-160">Exposure score impact of this software</span></span>
