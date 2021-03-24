---
title: Übersicht über Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, bei Benutzern und in Postfächern auftreten.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060739"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="889b4-104">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="889b4-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="889b4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="889b4-105">**Applies to:**</span></span>
- <span data-ttu-id="889b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="889b4-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="889b4-107">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="889b4-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="889b4-108">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="889b4-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="889b4-109">Vorfälle basieren auf verwandten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="889b4-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="889b4-110">Warnungen werden erstellt, wenn in Ihrem Netzwerk ein bösartiges Ereignis oder eine schädliche Aktivität erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="889b4-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="889b4-111">Einzelne Warnungen liefern wertvolle Hinweise auf einen angriffs geraden Angriff.</span><span class="sxs-lookup"><span data-stu-id="889b4-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="889b4-112">Bei Angriffen werden jedoch in der Regel verschiedene Vektoren und Techniken zum Durchführen einer Verletzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="889b4-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="889b4-113">Das Zusammenkniffen einzelner Hinweise kann schwierig und zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="889b4-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="889b4-114">Dieses kurze Video bietet eine Übersicht über Vorfälle in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="889b4-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="889b4-115">Bei einem Vorfall handelt es sich um eine Sammlung korrelierter Warnungen, aus der die Geschichte eines Angriffs besteht.</span><span class="sxs-lookup"><span data-stu-id="889b4-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="889b4-116">Bösartige und verdächtige Ereignisse, die in verschiedenen Geräte-, Benutzer- und Postfachentitäten im Netzwerk gefunden werden, werden von Microsoft 365 Defender automatisch aggregiert.</span><span class="sxs-lookup"><span data-stu-id="889b4-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="889b4-117">Das Gruppieren verwandter Warnungen zu einem Vorfall bietet Sicherheitsverteidigern eine umfassende Ansicht eines Angriffs.</span><span class="sxs-lookup"><span data-stu-id="889b4-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="889b4-118">Sicherheitsaktivisten können beispielsweise sehen, wo der Angriff begonnen hat, welche Taktiken verwendet wurden und wie weit der Angriff in das Netzwerk gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="889b4-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="889b4-119">Sie können auch den Umfang des Angriffs sehen, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren, wie schwer die Auswirkungen waren, und andere Details zu den betroffenen Entitäten.</span><span class="sxs-lookup"><span data-stu-id="889b4-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="889b4-120">Wenn diese Option aktiviert ist, kann Microsoft 365 Defender die einzelnen Warnungen automatisch durch Automatisierung und künstliche Intelligenz untersuchen und auflösen.</span><span class="sxs-lookup"><span data-stu-id="889b4-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="889b4-121">Sicherheitsverteidiger können auch zusätzliche Korrekturschritte ausführen, um den Angriff direkt aus der Sicht der Vorfälle zu beheben.</span><span class="sxs-lookup"><span data-stu-id="889b4-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="889b4-122">Vorfälle aus den letzten 30 Tagen werden in der Vorfallwarteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="889b4-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="889b4-123">Von hier aus können Sicherheitsaktivisten sehen, welche Vorfälle basierend auf der Risikostufe und anderen Faktoren priorisiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="889b4-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="889b4-124">Sicherheitsaktivisten können Vorfälle auch umbenennen, einzelnen Analysten zuweisen, Vorfälle klassifizieren und Tags zu Vorfällen hinzufügen, um eine bessere und angepasste Vorfallverwaltungserfahrung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="889b4-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="889b4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="889b4-125">See also</span></span>
- [<span data-ttu-id="889b4-126">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="889b4-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="889b4-127">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="889b4-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="889b4-128">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="889b4-128">Manage incidents</span></span>](manage-incidents.md)