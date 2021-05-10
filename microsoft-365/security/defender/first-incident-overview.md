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
ms.openlocfilehash: 5ea847e822e094049dd8f0b941f22f3bb4f7eff4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297176"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="35add-104">Einführung in die Reaktion auf Ihren ersten Vorfall</span><span class="sxs-lookup"><span data-stu-id="35add-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="35add-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="35add-105">**Applies to:**</span></span>
- <span data-ttu-id="35add-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35add-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="35add-107">Die Strategie für die Reaktion auf Vorfälle in einer Organisation bestimmt, dass sie zunehmend störende Sicherheitsvorfälle und Cyberkriminalität umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="35add-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="35add-108">Es ist zwar wichtig, vorbeugende Maßnahmen zu ergreifen, aber die Fähigkeit, schnell zu handeln, um erkannte Vorfälle zu eindähmen, auszulöschen und von erkannten Vorfällen wiederhergestellt zu werden, kann Schäden und Geschäftsverluste minimieren.</span><span class="sxs-lookup"><span data-stu-id="35add-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="35add-109">Diese exemplarische Vorgehensweise zur Reaktion auf Vorfälle zeigt, wie Sie als Teil eines Sicherheitseinsatzteams die meisten der wichtigsten Schritte zur Reaktion auf Vorfälle in Microsoft 365 ausführen können.</span><span class="sxs-lookup"><span data-stu-id="35add-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="35add-110">Die Schritte sind hier aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35add-110">Here are the steps:</span></span>

- <span data-ttu-id="35add-111">Vorbereiten Ihrer Sicherheitslage</span><span class="sxs-lookup"><span data-stu-id="35add-111">Preparation of your security posture</span></span>
- <span data-ttu-id="35add-112">Für jeden Vorfall:</span><span class="sxs-lookup"><span data-stu-id="35add-112">For each incident:</span></span>
  - <span data-ttu-id="35add-113">Schritt 1: Triage und Analyse</span><span class="sxs-lookup"><span data-stu-id="35add-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="35add-114">Schritt 2: Korrektur (Eindämmung, Auslöschung und Wiederherstellung)</span><span class="sxs-lookup"><span data-stu-id="35add-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="35add-115">Schritt 3: Überprüfung nach einem Vorfall</span><span class="sxs-lookup"><span data-stu-id="35add-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="35add-116">Ein Sicherheitsvorfall wird vom National Institute of Standards and Technology (NIST) als "ein Ereignis definiert, das tatsächlich oder potenziell die Vertraulichkeit, Integrität oder Verfügbarkeit eines Informationssystems gefährdet; oder die Informationen, die das System verarbeitet, speichert oder überträgt; oder die eine Verletzung oder unmittelbar bevorstehende Gefahr einer Verletzung von Sicherheitsrichtlinien, Sicherheitsverfahren oder akzeptablen Verwendungsrichtlinien darstellt."</span><span class="sxs-lookup"><span data-stu-id="35add-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="35add-117">Vorfälle in Microsoft 365 Defender sind die logischen Ausgangspunkte für die Analyse und Reaktion auf Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="35add-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="35add-118">Die Analyse und Behebung von Vorfällen macht in der Regel die meisten Aufgaben eines Sicherheitsteams aus.</span><span class="sxs-lookup"><span data-stu-id="35add-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="35add-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="35add-119">Next step</span></span>

<span data-ttu-id="35add-120">[![Vorbereiten Ihrer Organisation und Microsoft 365 Mandanten](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="35add-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="35add-121">Stellen Sie sicher, dass Ihre Organisation Microsoft 365 Mandanten [für die Behandlung von Vorfällen vorbereitet ist.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="35add-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35add-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35add-122">See also</span></span>

<span data-ttu-id="35add-123">Anleitung zur Reaktion auf Vorfälle für Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="35add-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="35add-124">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="35add-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="35add-125">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="35add-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="35add-126">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="35add-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="35add-127">Zusätzliche Beispiele für erste Reaktionen auf Vorfälle:</span><span class="sxs-lookup"><span data-stu-id="35add-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="35add-128">Phishing-E-Mail</span><span class="sxs-lookup"><span data-stu-id="35add-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="35add-129">Identitätsbasisangriff</span><span class="sxs-lookup"><span data-stu-id="35add-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="35add-130">Detaillierte Spielbücher zur Reaktion auf Vorfälle</span><span class="sxs-lookup"><span data-stu-id="35add-130">Detailed incident response playbooks</span></span>](https://docs.microsoft.com/security/compass/incident-response-playbooks)


