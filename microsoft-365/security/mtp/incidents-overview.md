---
title: Übersicht über Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, bei Benutzern und in Postfächern auftreten.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357611"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="21ba4-104">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21ba4-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="21ba4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="21ba4-105">**Applies to:**</span></span>
- <span data-ttu-id="21ba4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21ba4-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="21ba4-107">Möchten Sie Microsoft 365 Defender erfahren?</span><span class="sxs-lookup"><span data-stu-id="21ba4-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="21ba4-108">Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [ihr Pilotprojekt in der Produktion ausführen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="21ba4-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="21ba4-109">Vorfälle basieren auf entsprechenden Warnungen.</span><span class="sxs-lookup"><span data-stu-id="21ba4-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="21ba4-110">Warnungen werden erstellt, wenn in Ihrem Netzwerk ein bösartiges Ereignis oder eine schädliche Aktivität erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="21ba4-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="21ba4-111">Einzelne Warnungen liefern wertvolle Anhaltspunkte für einen fortlaufenden Angriff.</span><span class="sxs-lookup"><span data-stu-id="21ba4-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="21ba4-112">Angriffe verwenden jedoch in der Regel verschiedene Vektoren und Techniken für die Durchführung einer Sicherheitsverletzung.</span><span class="sxs-lookup"><span data-stu-id="21ba4-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="21ba4-113">Einzelne Anhaltspunkte zusammen zu stellen, kann herausfordernd und zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="21ba4-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="21ba4-114">Dieses kurze Video bietet eine Übersicht über Vorfälle in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="21ba4-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="21ba4-115">Bei einem Vorfall handelt es sich um eine Sammlung korrelierter Warnungen, aus denen sich die Geschichte eines Angriffs zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="21ba4-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="21ba4-116">Böswillige und verdächtige Ereignisse, die sich in unterschiedlichen Geräten, Benutzern und Post Fach Entitäten im Netzwerk befinden, werden automatisch von Microsoft 365 Defender aggregiert.</span><span class="sxs-lookup"><span data-stu-id="21ba4-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="21ba4-117">Durch das Gruppieren von zugehörigen Warnungen in einen Vorfall erhalten Sicherheits Verteidiger eine umfassende Ansicht eines Angriffs.</span><span class="sxs-lookup"><span data-stu-id="21ba4-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="21ba4-118">Beispielsweise können Sicherheits Verteidiger sehen, wo der Angriff gestartet wurde, welche Taktik verwendet wurde und wie weit der Angriff in das Netzwerk verlaufen ist.</span><span class="sxs-lookup"><span data-stu-id="21ba4-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="21ba4-119">Sie können auch den Umfang des Angriffs sehen, wie viele Geräte, Benutzer und Postfächer betroffen waren, wie schwerwiegend die Auswirkungen waren, und andere Details zu betroffenen Entitäten.</span><span class="sxs-lookup"><span data-stu-id="21ba4-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="21ba4-120">Wenn diese Option aktiviert ist, kann Microsoft 365 Defender die einzelnen Warnungen automatisch mithilfe von Automatisierung und künstlicher Intelligenz untersuchen und lösen.</span><span class="sxs-lookup"><span data-stu-id="21ba4-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="21ba4-121">Sicherheits Verteidiger können auch zusätzliche korrekturschritte ausführen, um den Angriff direkt aus der Vorfallansicht zu lösen.</span><span class="sxs-lookup"><span data-stu-id="21ba4-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="21ba4-122">Vorfälle aus den letzten 30 Tagen werden in der Vorfall Warteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21ba4-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="21ba4-123">Von hier aus können Sicherheits Verteidiger sehen, welche Vorfälle basierend auf der Risikostufe und anderen Faktoren priorisiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="21ba4-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="21ba4-124">Sicherheits Verteidiger können Vorfälle auch umbenennen, Sie einzelnen Analysten zuweisen, Vorfälle klassifizieren und Tags hinzufügen, um eine bessere und Benutzer spezifischere Vorfall Verwaltungserfahrung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="21ba4-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="21ba4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21ba4-125">See also</span></span>
- [<span data-ttu-id="21ba4-126">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="21ba4-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="21ba4-127">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="21ba4-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="21ba4-128">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="21ba4-128">Manage incidents</span></span>](manage-incidents.md)
