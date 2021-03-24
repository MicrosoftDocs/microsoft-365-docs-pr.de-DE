---
title: Unterstützte Microsoft Defender Advanced Threat Protection-Antwort-APIs
description: Erfahren Sie mehr über die spezifischen reaktionsbezogenen Microsoft Defender Advanced Threat Protection-API-Aufrufe.
keywords: Antwort-APIs, Graph-API, unterstützte APIs, Akteur, Warnungen, Gerät, Benutzer, Domäne, IP, Datei
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 93184cc82972a4b1c970b026ceff78adbc1fb7f8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062120"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="2816d-104">Unterstützte Microsoft Defender for Endpoint-Abfrage-APIs</span><span class="sxs-lookup"><span data-stu-id="2816d-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2816d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2816d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2816d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2816d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

> [!TIP]
> <span data-ttu-id="2816d-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2816d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2816d-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2816d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="2816d-109">Erfahren Sie mehr über die unterstützten reaktionsbezogenen API-Aufrufe, die Sie ausführen können, sowie Details wie die erforderlichen Anforderungsheader und die erwartete Antwort von den Aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2816d-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2816d-110">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="2816d-110">In this section</span></span>
<span data-ttu-id="2816d-111">Thema</span><span class="sxs-lookup"><span data-stu-id="2816d-111">Topic</span></span> | <span data-ttu-id="2816d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2816d-112">Description</span></span>
:---|:---
<span data-ttu-id="2816d-113">Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="2816d-113">Collect investigation package</span></span> | <span data-ttu-id="2816d-114">Führen Sie diese API aus, um ein Untersuchungspaket von einem Gerät zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="2816d-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="2816d-115">Isolieren des Geräts</span><span class="sxs-lookup"><span data-stu-id="2816d-115">Isolate device</span></span> | <span data-ttu-id="2816d-116">Führen Sie diese API aus, um ein Gerät vom Netzwerk zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="2816d-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="2816d-117">Unisolates Gerät</span><span class="sxs-lookup"><span data-stu-id="2816d-117">Unisolate device</span></span> | <span data-ttu-id="2816d-118">Entfernen eines Geräts aus der Isolation.</span><span class="sxs-lookup"><span data-stu-id="2816d-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="2816d-119">Einschränken der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="2816d-119">Restrict code execution</span></span> | <span data-ttu-id="2816d-120">Führen Sie diese API aus, um einen Angriff zu enthalten, indem Sie bösartige Prozesse beenden.</span><span class="sxs-lookup"><span data-stu-id="2816d-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="2816d-121">Sie können auch ein Gerät sperren und verhindern, dass nachfolgende Versuche potenziell schädlicher Programme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2816d-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="2816d-122">Unrestrict code execution</span><span class="sxs-lookup"><span data-stu-id="2816d-122">Unrestrict code execution</span></span> | <span data-ttu-id="2816d-123">Führen Sie dies aus, um die Einschränkung der Anwendungsrichtlinie rückgängig zu machen, nachdem Sie überprüft haben, ob das gefährdete Gerät behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="2816d-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="2816d-124">Ausführen der Antivirenscans</span><span class="sxs-lookup"><span data-stu-id="2816d-124">Run antivirus scan</span></span> | <span data-ttu-id="2816d-125">Remoteinitiieren sie eine Antivirenscan, um Schadsoftware zu identifizieren und zu beheben, die möglicherweise auf einem gefährdeten Gerät vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2816d-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="2816d-126">Datei zum Beenden und Isolieren</span><span class="sxs-lookup"><span data-stu-id="2816d-126">Stop and quarantine file</span></span> |  <span data-ttu-id="2816d-127">Führen Sie diesen Aufruf aus, um die Ausführung von Prozessen, Quarantänedateien und das Löschen von Persistenz wie Registrierungsschlüsseln zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2816d-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="2816d-128">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="2816d-128">Request sample</span></span> | <span data-ttu-id="2816d-129">Führen Sie diesen Aufruf aus, um ein Beispiel einer Datei von einem bestimmten Gerät an zu fordern.</span><span class="sxs-lookup"><span data-stu-id="2816d-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="2816d-130">Die Datei wird vom Gerät gesammelt und in einen sicheren Speicher hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="2816d-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="2816d-131">Datei blockieren</span><span class="sxs-lookup"><span data-stu-id="2816d-131">Block file</span></span> | <span data-ttu-id="2816d-132">Führen Sie diese API aus, um eine weitere Verbreitung eines Angriffs in Ihrer Organisation zu verhindern, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten.</span><span class="sxs-lookup"><span data-stu-id="2816d-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="2816d-133">Aufheben der Blockierung der Datei</span><span class="sxs-lookup"><span data-stu-id="2816d-133">Unblock file</span></span> | <span data-ttu-id="2816d-134">Zulassen der Ausführung einer Datei in der Organisation mithilfe von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="2816d-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="2816d-135">Paket-SAS-URI</span><span class="sxs-lookup"><span data-stu-id="2816d-135">Get package SAS URI</span></span> | <span data-ttu-id="2816d-136">Führen Sie diese API aus, um einen URI zu erhalten, der das Herunterladen eines Untersuchungspakets ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2816d-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="2816d-137">MachineAction-Objekt erhalten</span><span class="sxs-lookup"><span data-stu-id="2816d-137">Get MachineAction object</span></span> | <span data-ttu-id="2816d-138">Führen Sie diese API aus, um das MachineAction-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2816d-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="2816d-139">MachineActions-Auflistung erhalten</span><span class="sxs-lookup"><span data-stu-id="2816d-139">Get MachineActions collection</span></span> | <span data-ttu-id="2816d-140">Führen Sie dies aus, um die MachineAction-Auflistung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2816d-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="2816d-141">FileActions-Auflistung herunterladen</span><span class="sxs-lookup"><span data-stu-id="2816d-141">Get FileActions collection</span></span> | <span data-ttu-id="2816d-142">Führen Sie diese API aus, um die FileActions-Auflistung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2816d-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="2816d-143">FileMachineAction-Objekt herunterladen</span><span class="sxs-lookup"><span data-stu-id="2816d-143">Get FileMachineAction object</span></span> | <span data-ttu-id="2816d-144">Führen Sie diese API aus, um das FileMachineAction-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2816d-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="2816d-145">FileMachineActions-Auflistung herunterladen</span><span class="sxs-lookup"><span data-stu-id="2816d-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="2816d-146">Führen Sie diese API aus, um die FileMachineAction-Auflistung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2816d-146">Run this API to get FileMachineAction collection.</span></span>
