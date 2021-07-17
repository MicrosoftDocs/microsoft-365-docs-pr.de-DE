---
title: Erstellen Sie die Microsoft 365 Defender Evaluierungsumgebung. Aktivieren oder aktivieren Sie Testlizenzen, und fahren Sie mit Microsoft Defender for Identity (MDI) fort.
description: Richten Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, indem Sie Testlizenzen aktivieren. Richten Sie dann Microsoft Defender for Identity (MDI) und alle anderen M365D-Auswertungen ein.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458270"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="71b6a-105">Erstellen der Microsoft 365 Defender-Evaluierungsumgebung</span><span class="sxs-lookup"><span data-stu-id="71b6a-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="71b6a-106">Es gibt zwei gängige Möglichkeiten, diesen nächsten Schritt bei der Evaluierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71b6a-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="71b6a-107">In diesem Dokument wird davon ausgegangen, dass Sie bereits über einen M365-Produktionsmandanten verfügen und E5-Testlizenzen aktivieren, um M365 Defender in *der aktuellen Umgebung* auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="71b6a-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="71b6a-108">Mit einer direkten Auswertung können Sie alle Sicherheitsmethoden beim Erwerb von Lizenzen nach dem Auswertungszeitraum beibehalten.</span><span class="sxs-lookup"><span data-stu-id="71b6a-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="71b6a-109">Die zweite besteht darin, [Ihre Microsoft 365 Defender Testumgebung](setup-m365deval.md) für die Auswertung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="71b6a-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="71b6a-110">Da es möglicherweise nicht viele echte Signale vom Unternehmen gibt, sollten Sie sich dieser Warnung bewusst sein.</span><span class="sxs-lookup"><span data-stu-id="71b6a-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="71b6a-111">So aktivieren Sie E5-Testlizenzen, um Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71b6a-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="71b6a-112">Melden Sie sich bei Ihrem vorhandenen M365-Mandantenverwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="71b6a-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="71b6a-113">Wählen Sie im Navigationsmenü *"Dienste kaufen"* aus.</span><span class="sxs-lookup"><span data-stu-id="71b6a-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="71b6a-114">Scrollen Sie nach unten zum *Abschnitt Office 365,* und wählen Sie unter Office 365 E5 Lizenz die Schaltfläche "Details" aus.</span><span class="sxs-lookup"><span data-stu-id="71b6a-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Der Office 365 Abschnitt verfügt über eine Schaltfläche &quot;Details&quot;, auf die geklickt werden kann.":::

4. <span data-ttu-id="71b6a-116">Wählen Sie den *Kostenlosen Testlink starten* aus.</span><span class="sxs-lookup"><span data-stu-id="71b6a-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Klicken Sie auf &quot;Kostenlose Testversion starten&quot; (es gibt eine Gebühr von 35 USD).":::

5. <span data-ttu-id="71b6a-118">Bestätigen Sie Ihre Anforderung, und klicken Sie auf die Schaltfläche *"Jetzt testen".*</span><span class="sxs-lookup"><span data-stu-id="71b6a-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Im Bereich &quot;Auschecken, Bestellung bestätigen&quot; befindet sich die Schaltfläche &quot;Jetzt testen&quot; (für eine Office 365 E5 Testversion eines Monats für 25 Benutzer).":::

## <a name="next-steps"></a><span data-ttu-id="71b6a-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="71b6a-120">Next steps</span></span>
[<span data-ttu-id="71b6a-121">Aktivieren Microsoft 365 für Identität</span><span class="sxs-lookup"><span data-stu-id="71b6a-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="71b6a-122">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="71b6a-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>