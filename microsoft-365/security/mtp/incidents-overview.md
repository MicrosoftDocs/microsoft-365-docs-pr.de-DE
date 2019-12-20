---
title: Untersuchen von Vorfällen in Microsoft Threat Protection
description: Untersuchen Sie Vorfälle, die auf Geräten, bei Benutzern und in Postfächern auftreten.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1e157ff8c7c2ac61790b4be74c43553eb0807eb2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808730"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="4c2b1-104">Übersicht über Vorfälle in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4c2b1-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="4c2b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4c2b1-105">**Applies to:**</span></span>
- <span data-ttu-id="4c2b1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4c2b1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4c2b1-107">Grundlage aller Vorfälle sind Warnungen.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="4c2b1-108">Warnungen werden erstellt, wenn in Ihrem Netzwerk ein bösartiges Ereignis oder eine schädliche Aktivität erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="4c2b1-109">Einzelne Warnungen bieten wertvolle Anhaltspunkte dafür, was bei einzelnen Ereignissen oder Entitäten geschieht.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="4c2b1-110">Angriffe nutzen allerdings in der Regel verschiedene Angriffsvektoren zur Durchführung einer Sicherheitsverletzung.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="4c2b1-111">Die einzelnen Anhaltspunkte zusammenzustellen, kann eine herausfordernde und zeitraubende Aufgabe sein.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="4c2b1-112">Microsoft Threat Protection verknüpft die Anhaltspunkte einzelner Warnungen.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="4c2b1-113">Im Microsoft 365 Security Center werden bösartige Ereignisse für die folgenden Entitäten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4c2b1-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="4c2b1-114">Geräte</span><span class="sxs-lookup"><span data-stu-id="4c2b1-114">Devices</span></span>
- <span data-ttu-id="4c2b1-115">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4c2b1-115">Users</span></span>
- <span data-ttu-id="4c2b1-116">Postfächer</span><span class="sxs-lookup"><span data-stu-id="4c2b1-116">Mailboxes</span></span>

<span data-ttu-id="4c2b1-117">Verdächtige Ereignisse, die Merkmale aufweisen, Teil eines größeren Angriffs zu sein, werden in einen Vorfall aggregiert.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="4c2b1-118">Sie erfahren genau, wo ein Angriff begonnen hat, und erhalten weitere Details, die den Umfang des Angriffs verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="4c2b1-119">Die Plattform bietet Sicherheitsdefender mit geeigneten visuellen Objekte und Datendarstellungen, um komplexe entitätsübergreifende Bedrohungen zu verstehen und zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="4c2b1-120">Sie verfügen nicht nur über einen Einblick in den Umfang eines Angriffs, sondern auch über Zugriff auf Dienste, mit denen Sie taktische Schritte zur Eindämmung eines Vorfalls unternehmen können.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4c2b1-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4c2b1-121">Related topics</span></span>
- [<span data-ttu-id="4c2b1-122">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="4c2b1-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="4c2b1-123">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="4c2b1-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4c2b1-124">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="4c2b1-124">Manage incidents</span></span>](manage-incidents.md)