---
title: Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung
description: Verwenden des Info-Centers zum Verwalten von Aktionen im Zusammenhang mit automatisierten Untersuchungen und Reaktionen
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 725d22629d2c81a0edf8f329602214afddde6511
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633923"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="1411a-104">Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="1411a-104">Approve or reject pending actions following an automated investigation</span></span>

<span data-ttu-id="1411a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1411a-105">**Applies to:**</span></span>
- <span data-ttu-id="1411a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1411a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1411a-107">Wenn eine automatisierte Untersuchung ausgeführt wird, kann dies zu einer oder mehreren empfohlenen [Abhilfemaßnahmen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) führen, für die eine Genehmigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1411a-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="1411a-108">So kann beispielsweise ein Cluster von E-Mail-Nachrichten gelöscht oder eine in Quarantäne befindliche Datei entfernt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1411a-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="1411a-109">Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="1411a-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="1411a-110">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="1411a-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="1411a-111">Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Funktionen in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="1411a-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="1411a-112">Ausstehende Aktionen können mithilfe des [Aktions Centers](#review-a-pending-action-in-the-action-center) oder der [Ansicht Details der Untersuchung](#review-a-pending-action-in-the-investigation-details-view)überprüft und genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="1411a-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="1411a-113">Sie müssen über [geeignete Berechtigungen verfügen](mtp-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können.</span><span class="sxs-lookup"><span data-stu-id="1411a-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="1411a-114">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="1411a-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="1411a-115">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="1411a-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="1411a-116">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="1411a-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="1411a-117">Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="1411a-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="1411a-118">Wenn Sie ein Element in der Spalte **Nummer der Untersuchung** auswählen, wird die Seite mit den Untersuchungsdetails geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1411a-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="1411a-119">Dort können Sie die Ergebnisse der Untersuchung anzeigen und dann die empfohlenen Aktionen genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="1411a-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="1411a-120">Wenn Sie eine Zeile in der Liste auswählen, wird ein Flyout geöffnet, in dem Informationen zu dem betreffenden Element angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1411a-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="1411a-122">Verwenden Sie die Links, um eine zugeordnete Warnung oder eine Untersuchung anzuzeigen, und genehmigen Sie die jeweilige Aktion oder lehnen Sie diese ab.</span><span class="sxs-lookup"><span data-stu-id="1411a-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="1411a-123">Überprüfen einer ausstehenden Aktion in der Untersuchungsdetailansicht</span><span class="sxs-lookup"><span data-stu-id="1411a-123">Review a pending action in the investigation details view</span></span>

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="1411a-125">Wählen Sie auf der Seite [Untersuchungsdetails](mtp-autoir-results.md) die Option **Ausstehende Aktionen** (oder **Aktionen**) aus. Hier sind die Elemente aufgelistet, für die eine Genehmigung aussteht.</span><span class="sxs-lookup"><span data-stu-id="1411a-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="1411a-126">Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Genehmigen** oder **Ablehnen**aus.</span><span class="sxs-lookup"><span data-stu-id="1411a-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1411a-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1411a-127">Next steps</span></span>

- <span data-ttu-id="1411a-128">Erfahren Sie mehr über das [Info-Center](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="1411a-128">[Learn more about the Action center](mtp-action-center.md)</span></span>

- <span data-ttu-id="1411a-129">Erfahren Sie mehr über [Vorfälle](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1411a-129">[Learn more about incidents](incidents-overview.md)</span></span>

- <span data-ttu-id="1411a-130">Erfahren Sie mehr zum Thema [Suche](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1411a-130">[Learn about hunting](advanced-hunting-overview.md)</span></span>
