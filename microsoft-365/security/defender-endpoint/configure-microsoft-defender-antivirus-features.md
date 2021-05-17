---
title: Konfigurieren von Microsoft Defender Antivirus-Features
description: Sie können Microsoft Defender Antivirus Mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinie und PowerShell konfigurieren.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Konfigurieren, Konfiguration, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, Verwaltung mobiler Geräte, GP, Gruppenrichtlinie, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275108"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="9087a-104">Konfigurieren von Microsoft Defender Antivirus-Features</span><span class="sxs-lookup"><span data-stu-id="9087a-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9087a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9087a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9087a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9087a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9087a-107">Sie können Microsoft Defender Antivirus mit einer Reihe von Tools konfigurieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="9087a-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="9087a-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9087a-108">Microsoft Intune</span></span>
- <span data-ttu-id="9087a-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9087a-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="9087a-110">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9087a-110">Group Policy</span></span>
- <span data-ttu-id="9087a-111">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9087a-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="9087a-112">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="9087a-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="9087a-113">Die folgenden breiten Kategorien von Features können konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="9087a-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="9087a-114">Aus der Cloud gelieferter Schutz</span><span class="sxs-lookup"><span data-stu-id="9087a-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="9087a-115">Always-on-Echtzeitschutz, einschließlich verhaltensbasierter, heuristischer und machine-learning-basierter Schutz</span><span class="sxs-lookup"><span data-stu-id="9087a-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="9087a-116">Interaktion von Endbenutzern mit dem Client auf einzelnen Endpunkten</span><span class="sxs-lookup"><span data-stu-id="9087a-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="9087a-117">In den folgenden Artikeln wird beschrieben, wie Sie wichtige Aufgaben beim Konfigurieren von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9087a-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9087a-118">Jeder Artikel enthält Anweisungen für das entsprechende Konfigurationstool (oder Tools).</span><span class="sxs-lookup"><span data-stu-id="9087a-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="9087a-119">Artikel</span><span class="sxs-lookup"><span data-stu-id="9087a-119">Article</span></span>  |<span data-ttu-id="9087a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9087a-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="9087a-121">Nutzen des von Microsoft in der Cloud bereitgestellten Microsoft Defender Antivirus Schutz</span><span class="sxs-lookup"><span data-stu-id="9087a-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="9087a-122">Verwenden Sie den in der Cloud zugestellten Schutz für eine erweiterte, schnelle und robuste Antivirenerkennung.</span><span class="sxs-lookup"><span data-stu-id="9087a-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="9087a-123">Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="9087a-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="9087a-124">Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeit-Virenschutz.</span><span class="sxs-lookup"><span data-stu-id="9087a-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="9087a-125">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9087a-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="9087a-126">Konfigurieren Sie, wie Endbenutzer in Ihrer Organisation mit Microsoft Defender Antivirus, welche Benachrichtigungen angezeigt werden und ob sie Einstellungen außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="9087a-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="9087a-127">Sie können auch das Thema Referenzthemen für Verwaltungs- und [Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md) lesen, um eine Übersicht über die einzelnen Tools und Links zu weiteren Hilfen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9087a-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>