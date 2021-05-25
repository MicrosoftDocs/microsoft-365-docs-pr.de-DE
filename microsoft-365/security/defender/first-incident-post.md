---
title: 'SCHRITT 3: Durchführen einer Überprüfung Ihres ersten Vorfalls nach dem Vorfall'
description: Durchführen einer Überprüfung Ihres ersten Vorfalls in Microsoft 365 Defender.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
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
ms.openlocfilehash: 6b5311a2923d7b299ba4f70ef3c2e8d91809e7c8
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651368"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="b6d10-105">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="b6d10-105">Step 3.</span></span> <span data-ttu-id="b6d10-106">Durchführen einer Überprüfung Ihres ersten Vorfalls nach dem Vorfall</span><span class="sxs-lookup"><span data-stu-id="b6d10-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b6d10-107">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b6d10-107">**Applies to:**</span></span>
- <span data-ttu-id="b6d10-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d10-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="b6d10-109">Das National Institute of Standards and Technology (NIST) empfiehlt, dass Organisationen den Vorfall überprüfen müssen, um daraus zu lernen und die Sicherheitslage oder Prozesse zu verbessern, sobald alle Schritte zur Wiederherstellung nach dem Angriff unternommen wurden.</span><span class="sxs-lookup"><span data-stu-id="b6d10-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and improve security posture or processes.</span></span> <span data-ttu-id="b6d10-110">Die Bewertung der verschiedenen Aspekte der Behandlung von Vorfällen wird bei der Vorbereitung auf den nächsten Vorfall wichtig.</span><span class="sxs-lookup"><span data-stu-id="b6d10-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="b6d10-111">Microsoft 365 Defender kann bei der Durchführung von Aktivitäten nach einem Vorfall helfen, indem es einer Organisation Warnungen zur Verfügung stellt, die mit [MITRE ATT&CK Framework ausgerichtet sind.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="b6d10-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="b6d10-112">Alle Microsoft Defender-Lösungen beschriften Angriffe in Übereinstimmung mit einer ATT-&CK-Taktik oder -Technik.</span><span class="sxs-lookup"><span data-stu-id="b6d10-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="b6d10-113">Durch Zuordnen von Warnungen zu diesem Branchenframework können Sie:</span><span class="sxs-lookup"><span data-stu-id="b6d10-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="b6d10-114">Führen Sie eine Analyse der Lücken in der Sicherheitsabdeckung durch.</span><span class="sxs-lookup"><span data-stu-id="b6d10-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="b6d10-115">Bestimmen der Zuschreibung von Widersachern und Kampagnen.</span><span class="sxs-lookup"><span data-stu-id="b6d10-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="b6d10-116">Führen Sie Trendanalysen durch.</span><span class="sxs-lookup"><span data-stu-id="b6d10-116">Perform trend analysis.</span></span>
- <span data-ttu-id="b6d10-117">Identifizieren von Kompetenzlücken im Bewusstsein für Angriffsmethode.</span><span class="sxs-lookup"><span data-stu-id="b6d10-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="b6d10-118">Erstellen Sie ein Power Automate Playbook für eine schnellere Korrektur.</span><span class="sxs-lookup"><span data-stu-id="b6d10-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="b6d10-119">Die Aktivitäten nach dem Vorfall können auch dazu führen, dass Die Sicherheitskonfiguration und die Prozesse des Sicherheitsteams optimieren und die Reaktionsfunktionen Ihrer Organisation verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="b6d10-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="b6d10-120">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b6d10-120">Next step</span></span>

<span data-ttu-id="b6d10-121">Sehen Sie sich die folgenden zusätzlichen Untersuchungspfade an:</span><span class="sxs-lookup"><span data-stu-id="b6d10-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="b6d10-122">Phishing-E-Mail</span><span class="sxs-lookup"><span data-stu-id="b6d10-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="b6d10-123">Identitätsbasierter Angriff</span><span class="sxs-lookup"><span data-stu-id="b6d10-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="b6d10-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6d10-124">See also</span></span>

- [<span data-ttu-id="b6d10-125">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="b6d10-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b6d10-126">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b6d10-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b6d10-127">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b6d10-127">Manage incidents</span></span>](manage-incidents.md)
