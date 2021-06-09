---
title: Hardwarebasierte Isolation (Windows 10)
ms.reviewer: ''
description: Erfahren Sie, wie die hardwarebasierte Isolation in Windows 10 zur Bekämpfung von Schadsoftware beiträgt.
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
ms.openlocfilehash: b3babf858ac19e70119a2dc6a58b25359f1b05c1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842986"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="0db3a-103">Hardwarebasierte Isolation in Windows 10</span><span class="sxs-lookup"><span data-stu-id="0db3a-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0db3a-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0db3a-104">**Applies to:**</span></span>
- [<span data-ttu-id="0db3a-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0db3a-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0db3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db3a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0db3a-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="0db3a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0db3a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0db3a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0db3a-109">Die hardwarebasierte Isolation trägt zum Schutz der Systemintegrität in Windows 10 bei und ist in Microsoft Defender für Endpunkt integriert.</span><span class="sxs-lookup"><span data-stu-id="0db3a-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="0db3a-110">Feature</span><span class="sxs-lookup"><span data-stu-id="0db3a-110">Feature</span></span> | <span data-ttu-id="0db3a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0db3a-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="0db3a-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="0db3a-112">Windows Defender Application Guard</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="0db3a-113">Application Guard schützt Ihr Gerät vor erweiterten Angriffen und hält Sie produktiv.</span><span class="sxs-lookup"><span data-stu-id="0db3a-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="0db3a-114">Mithilfe eines eindeutigen hardwarebasierten Isolationsansatzes besteht das Ziel darin, nicht vertrauenswürdige Websites und PDF-Dokumente in einem einfachen Container zu isolieren, der über die systemeigene Windows Hypervisor vom Betriebssystem getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="0db3a-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="0db3a-115">Wenn sich eine nicht vertrauenswürdige Website oder ein PDF-Dokument als bösartig herausstellt, bleibt es weiterhin im sicheren Container von Application Guard enthalten, und der Desktop-PC wird geschützt und der Angreifer wird von Ihren Unternehmensdaten fern gehalten.</span><span class="sxs-lookup"><span data-stu-id="0db3a-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="0db3a-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="0db3a-116">Windows Defender System Guard</span></span>](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="0db3a-117">System Guard schützt und verwaltet die Integrität des Systems beim Start und nach der Ausführung und überprüft die Systemintegrität mithilfe des Nachweiss.</span><span class="sxs-lookup"><span data-stu-id="0db3a-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

