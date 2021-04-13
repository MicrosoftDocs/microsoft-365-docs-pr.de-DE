---
title: Konfigurieren von Microsoft Defender Antivirus-Features
description: Sie können Microsoft Defender Antivirus-Features mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien und PowerShell konfigurieren.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Configure, Configuration, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, mobile Geräteverwaltung, GP, Gruppenrichtlinie, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690296"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="120a4-104">Konfigurieren von Microsoft Defender Antivirus-Features</span><span class="sxs-lookup"><span data-stu-id="120a4-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="120a4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="120a4-105">**Applies to:**</span></span>

- [<span data-ttu-id="120a4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="120a4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="120a4-107">Sie können Microsoft Defender Antivirus mit einer Reihe von Tools konfigurieren, darunter:</span><span class="sxs-lookup"><span data-stu-id="120a4-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="120a4-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="120a4-108">Microsoft Intune</span></span>
- <span data-ttu-id="120a4-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="120a4-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="120a4-110">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="120a4-110">Group Policy</span></span>
- <span data-ttu-id="120a4-111">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="120a4-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="120a4-112">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="120a4-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="120a4-113">Die folgenden breiten Kategorien von Features können konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="120a4-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="120a4-114">In der Cloud zugestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="120a4-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="120a4-115">Always-on-Echtzeitschutz, einschließlich verhaltensbasierter, heuristischer und machine-learning-basierter Schutz</span><span class="sxs-lookup"><span data-stu-id="120a4-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="120a4-116">Interaktion von Endbenutzern mit dem Client auf einzelnen Endpunkten</span><span class="sxs-lookup"><span data-stu-id="120a4-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="120a4-117">In den folgenden Artikeln wird beschrieben, wie Wichtige Aufgaben beim Konfigurieren von Microsoft Defender Antivirus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="120a4-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="120a4-118">Jeder Artikel enthält Anweisungen für das entsprechende Konfigurationstool (oder Tools).</span><span class="sxs-lookup"><span data-stu-id="120a4-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="120a4-119">Artikel</span><span class="sxs-lookup"><span data-stu-id="120a4-119">Article</span></span>  |<span data-ttu-id="120a4-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="120a4-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="120a4-121">Verwenden des microsoft cloudbasierten Microsoft Defender Antivirus-Schutzes</span><span class="sxs-lookup"><span data-stu-id="120a4-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="120a4-122">Verwenden Sie den in der Cloud zugestellten Schutz für eine erweiterte, schnelle und robuste Antivirenerkennung.</span><span class="sxs-lookup"><span data-stu-id="120a4-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="120a4-123">Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="120a4-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="120a4-124">Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeit-Virenschutz.</span><span class="sxs-lookup"><span data-stu-id="120a4-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="120a4-125">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="120a4-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="120a4-126">Konfigurieren Sie, wie Endbenutzer in Ihrer Organisation mit Microsoft Defender Antivirus interagieren, welche Benachrichtigungen angezeigt werden und ob sie Einstellungen außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="120a4-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="120a4-127">Sie können auch das Thema Referenzthemen für Verwaltungs- und [Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md) lesen, um eine Übersicht über die einzelnen Tools und Links zu weiteren Hilfen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="120a4-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>