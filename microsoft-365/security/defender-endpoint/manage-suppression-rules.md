---
title: Verwalten von Unterdrückungsregeln für Microsoft Defender for Endpoint
description: Möglicherweise müssen Sie verhindern, dass Warnungen im Portal angezeigt werden, indem Sie Unterdrückungsregeln verwenden. Erfahren Sie, wie Sie Ihre Unterdrückungsregeln in Microsoft Defender for Endpoint verwalten.
keywords: Verwalten von Unterdrückung, Regeln, Regelname, Bereich, Aktion, Warnungen, Aktivieren, Deaktivieren
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862127"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="eb8e8-105">Verwalten von Unterdrückungsregeln</span><span class="sxs-lookup"><span data-stu-id="eb8e8-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eb8e8-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eb8e8-106">**Applies to:**</span></span>
- [<span data-ttu-id="eb8e8-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eb8e8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb8e8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb8e8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eb8e8-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="eb8e8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eb8e8-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="eb8e8-111">Es kann Szenarien gibt, in denen Sie das Anzeigen von Warnungen im Portal unterdrücken müssen.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="eb8e8-112">Sie können Unterdrückungsregeln für bestimmte Warnungen erstellen, die als harmlos bekannt sind, z. B. bekannte Tools oder Prozesse in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="eb8e8-113">Weitere Informationen zum Unterdrücken von Warnungen finden Sie unter [Suppress alerts](manage-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="eb8e8-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="eb8e8-114">Sie können eine Liste aller Unterdrückungsregeln anzeigen und an einem ort verwalten.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="eb8e8-115">Sie können auch eine Warnungsunterdrückungsregel aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="eb8e8-116">Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.**</span><span class="sxs-lookup"><span data-stu-id="eb8e8-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="eb8e8-117">Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="eb8e8-118">Wählen Sie eine Regel aus, indem Sie auf das Kontrollkästchen neben dem Regelnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="eb8e8-119">Klicken **Sie auf Regel aktivieren,** Regel **bearbeiten** oder  **Regel löschen**.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="eb8e8-120">Wenn Sie Änderungen an einer Regel vornehmen, können Sie Warnungen veröffentlichen, die bereits unterdrückt wurden, unabhängig davon, ob diese Warnungen den neuen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="eb8e8-121">Anzeigen von Details einer Unterdrückungsregel</span><span class="sxs-lookup"><span data-stu-id="eb8e8-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="eb8e8-122">Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.**</span><span class="sxs-lookup"><span data-stu-id="eb8e8-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="eb8e8-123">Die Liste der Unterdrückungsregeln, die Benutzer in Ihrer Organisation erstellt haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="eb8e8-124">Klicken Sie auf einen Regelnamen.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-124">Click on a rule name.</span></span> <span data-ttu-id="eb8e8-125">Details der Regel werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-125">Details of the rule is displayed.</span></span> <span data-ttu-id="eb8e8-126">Ihnen werden die Regeldetails angezeigt, z. B. Status, Bereich, Aktion, Anzahl der übereinstimmenden Warnungen, erstellt von und Datum, an dem die Regel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="eb8e8-127">Sie können auch zugeordnete Warnungen und die Regelbedingungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb8e8-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb8e8-128">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="eb8e8-128">Related topics</span></span>

- [<span data-ttu-id="eb8e8-129">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="eb8e8-129">Manage alerts</span></span>](manage-alerts.md)
