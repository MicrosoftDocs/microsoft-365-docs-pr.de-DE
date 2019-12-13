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
ms.openlocfilehash: 989184c5dd8af6aafc525100e34e0172d96adcfe
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911120"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="b5a90-104">Übersicht über Vorfälle in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b5a90-104">Incidents overview in Microsoft Threat Protection</span></span>

<span data-ttu-id="b5a90-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b5a90-105">**Applies to:**</span></span>
- <span data-ttu-id="b5a90-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b5a90-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="b5a90-107">Grundlage aller Vorfälle sind Warnungen.</span><span class="sxs-lookup"><span data-stu-id="b5a90-107">The basis of all incidents are alerts.</span></span> <span data-ttu-id="b5a90-108">Warnungen werden erstellt, wenn in Ihrem Netzwerk ein bösartiges Ereignis oder eine schädliche Aktivität erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="b5a90-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="b5a90-109">Einzelne Warnungen bieten wertvolle Anhaltspunkte dafür, was bei einzelnen Ereignissen oder Entitäten geschieht.</span><span class="sxs-lookup"><span data-stu-id="b5a90-109">Individual alerts provide valuable clues in what's happening on individual events or entities.</span></span> <span data-ttu-id="b5a90-110">Angriffe nutzen allerdings in der Regel verschiedene Angriffsvektoren zur Durchführung einer Sicherheitsverletzung.</span><span class="sxs-lookup"><span data-stu-id="b5a90-110">However, attacks typically employ various attack vectors to carry out a breach.</span></span> <span data-ttu-id="b5a90-111">Die einzelnen Anhaltspunkte zusammenzustellen, kann eine herausfordernde und zeitraubende Aufgabe sein.</span><span class="sxs-lookup"><span data-stu-id="b5a90-111">Piecing individual clues together can be a challenging and time-consuming task.</span></span> 

<span data-ttu-id="b5a90-112">Microsoft Threat Protection verknüpft die Anhaltspunkte einzelner Warnungen.</span><span class="sxs-lookup"><span data-stu-id="b5a90-112">Microsoft Threat Protection connects the dots on individual alerts.</span></span> <span data-ttu-id="b5a90-113">Im Microsoft 365 Security Center werden bösartige Ereignisse für die folgenden Entitäten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b5a90-113">Malicious events on the following entities are surfaced in the Microsoft 365 security center:</span></span>
- <span data-ttu-id="b5a90-114">Geräte</span><span class="sxs-lookup"><span data-stu-id="b5a90-114">Devices</span></span>
- <span data-ttu-id="b5a90-115">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b5a90-115">Users</span></span>
- <span data-ttu-id="b5a90-116">Postfächer</span><span class="sxs-lookup"><span data-stu-id="b5a90-116">Mailboxes</span></span>

<span data-ttu-id="b5a90-117">Verdächtige Ereignisse, die Merkmale aufweisen, Teil eines größeren Angriffs zu sein, werden in einen Vorfall aggregiert.</span><span class="sxs-lookup"><span data-stu-id="b5a90-117">Suspicious events that show characteristics of being part of a larger attack are aggregated into an incident.</span></span> 

<span data-ttu-id="b5a90-118">Sie erfahren genau, wo ein Angriff begonnen hat, und erhalten weitere Details, die den Umfang des Angriffs verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="b5a90-118">You'll know exactly where an attack started and other details to help you see the extent of the attack.</span></span>

<span data-ttu-id="b5a90-119">Die Plattform bietet Sicherheitsdefender mit geeigneten visuellen Objekte und Datendarstellungen, um komplexe entitätsübergreifende Bedrohungen zu verstehen und zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b5a90-119">The platform provides security defenders with the right visuals and data representations to understand and address complex cross-entity threats.</span></span> 

<span data-ttu-id="b5a90-120">Sie verfügen nicht nur über einen Einblick in den Umfang eines Angriffs, sondern auch über Zugriff auf Dienste, mit denen Sie taktische Schritte zur Eindämmung eines Vorfalls unternehmen können.</span><span class="sxs-lookup"><span data-stu-id="b5a90-120">Not only will you have visibility on the scope of an attack, but you'll also have access to services that will allow you to take tactical steps to contain an incident.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b5a90-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b5a90-121">Related topics</span></span>
- [<span data-ttu-id="b5a90-122">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b5a90-122">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b5a90-123">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b5a90-123">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b5a90-124">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b5a90-124">Manage incidents</span></span>](manage-incidents.md)