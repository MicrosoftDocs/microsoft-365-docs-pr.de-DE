---
title: Hardwarebasierte Isolation (Windows 10)
ms.reviewer: ''
description: Erfahren Sie, wie die hardwarebasierte Isolation in Windows 10 bei der Bekämpfung von Schadsoftware hilft.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: 82841ccdb2a6ad09f43d0bf8d12cb54fe44d6dfe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186905"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="5ae8a-103">Hardwarebasierte Isolation in Windows 10</span><span class="sxs-lookup"><span data-stu-id="5ae8a-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ae8a-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5ae8a-104">**Applies to:**</span></span>
- [<span data-ttu-id="5ae8a-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5ae8a-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ae8a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ae8a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ae8a-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5ae8a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ae8a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="5ae8a-109">Die hardwarebasierte Isolation schützt die Systemintegrität in Windows 10 und ist in Microsoft Defender for Endpoint integriert.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="5ae8a-110">Feature</span><span class="sxs-lookup"><span data-stu-id="5ae8a-110">Feature</span></span> | <span data-ttu-id="5ae8a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ae8a-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="5ae8a-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="5ae8a-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="5ae8a-113">Application Guard schützt Ihr Gerät vor erweiterten Angriffen und hält Sie gleichzeitig produktiv.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="5ae8a-114">Mithilfe eines eindeutigen hardwarebasierten Isolationsansatzes besteht das Ziel darin, nicht vertrauenswürdige Websites und PDF-Dokumente in einem einfachen Container zu isolieren, der über den systemeigenen Windows Hypervisor vom Betriebssystem getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="5ae8a-115">Wenn sich herausstellt, dass eine nicht vertrauenswürdige Website oder ein nicht vertrauenswürdiges DOKUMENT schädlich ist, bleibt es weiterhin im sicheren Container von Application Guard enthalten, um den Desktop-PC und den Angreifer von Ihren Unternehmensdaten fern zu halten.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="5ae8a-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="5ae8a-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="5ae8a-117">System Guard schützt und verwaltet die Integrität des Systems beim Start und nach der Ausführung und überprüft die Systemintegrität mithilfe eines Attests.</span><span class="sxs-lookup"><span data-stu-id="5ae8a-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

