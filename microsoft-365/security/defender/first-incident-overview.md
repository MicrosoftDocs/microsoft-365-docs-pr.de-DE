---
title: Einführung in die Reaktion auf Ihren ersten Vorfall
description: Die Grundlagen der Reaktion auf Ihren ersten Vorfall in Microsoft 365 Defender.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114629"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="cb99e-104">Einführung in die Reaktion auf Ihren ersten Vorfall</span><span class="sxs-lookup"><span data-stu-id="cb99e-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cb99e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cb99e-105">**Applies to:**</span></span>
- <span data-ttu-id="cb99e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb99e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cb99e-107">Die Strategie für die Reaktion auf Vorfälle in einer Organisation bestimmt, dass sie zunehmend störende Sicherheitsvorfälle und Cyberkriminalität umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="cb99e-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="cb99e-108">Es ist zwar wichtig, vorbeugende Maßnahmen zu ergreifen, aber die Fähigkeit, schnell zu handeln, um erkannte Vorfälle zu eindähmen, auszulöschen und von erkannten Vorfällen wiederhergestellt zu werden, kann Schäden und Geschäftsverluste minimieren.</span><span class="sxs-lookup"><span data-stu-id="cb99e-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="cb99e-109">Diese exemplarische Vorgehensweise zur Reaktion auf Vorfälle zeigt, wie Sie als Teil eines Sicherheitseinsatzteams die meisten der wichtigsten Schritte zur Reaktion auf Vorfälle in Microsoft 365 ausführen können.</span><span class="sxs-lookup"><span data-stu-id="cb99e-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="cb99e-110">Die Schritte sind hier aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="cb99e-110">Here are the steps:</span></span>

- <span data-ttu-id="cb99e-111">Vorbereiten Ihrer Sicherheitslage</span><span class="sxs-lookup"><span data-stu-id="cb99e-111">Preparation of your security posture</span></span>
- <span data-ttu-id="cb99e-112">Für jeden Vorfall:</span><span class="sxs-lookup"><span data-stu-id="cb99e-112">For each incident:</span></span>
  - <span data-ttu-id="cb99e-113">Schritt 1: Triage und Analyse</span><span class="sxs-lookup"><span data-stu-id="cb99e-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="cb99e-114">Schritt 2: Korrektur (Eindämmung, Auslöschung und Wiederherstellung)</span><span class="sxs-lookup"><span data-stu-id="cb99e-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="cb99e-115">Schritt 3: Überprüfung nach einem Vorfall</span><span class="sxs-lookup"><span data-stu-id="cb99e-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="cb99e-116">Ein Sicherheitsvorfall wird vom National Institute of Standards and Technology (NIST) als "ein Ereignis definiert, das tatsächlich oder potenziell die Vertraulichkeit, Integrität oder Verfügbarkeit eines Informationssystems gefährdet; oder die Informationen, die das System verarbeitet, speichert oder überträgt; oder die eine Verletzung oder unmittelbar bevorstehende Gefahr einer Verletzung von Sicherheitsrichtlinien, Sicherheitsverfahren oder akzeptablen Verwendungsrichtlinien darstellt."</span><span class="sxs-lookup"><span data-stu-id="cb99e-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="cb99e-117">Vorfälle in Microsoft 365 Defender sind die logischen Ausgangspunkte für die Analyse und Reaktion auf Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="cb99e-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="cb99e-118">Die Analyse und Behebung von Vorfällen macht in der Regel die meisten Aufgaben eines Sicherheitsteams aus.</span><span class="sxs-lookup"><span data-stu-id="cb99e-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="cb99e-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="cb99e-119">Next step</span></span>

<span data-ttu-id="cb99e-120">[![Vorbereiten Ihrer Organisation und Microsoft 365 Mandanten](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="cb99e-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="cb99e-121">Stellen Sie sicher, dass Ihre Organisation Microsoft 365 Mandanten [für die Behandlung von Vorfällen vorbereitet ist.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="cb99e-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb99e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb99e-122">See also</span></span>

- [<span data-ttu-id="cb99e-123">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="cb99e-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="cb99e-124">Analysieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cb99e-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="cb99e-125">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="cb99e-125">Manage incidents</span></span>](manage-incidents.md)
