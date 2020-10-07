---
title: Planen der Organisations-und Lebenszyklus-Steuerung für Microsoft 365-Gruppen und Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean about Lifecycle Governance-Optionen für Tools für die Zusammenarbeit in Microsoft 365
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377187"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="d76a3-103">Planen der Organisations-und Lebenszyklus-Steuerung für Microsoft 365-Gruppen und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d76a3-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="d76a3-104">Microsoft 365 Groups verfügt über eine umfangreiche Reihe von Tools zum Implementieren der Steuerungsfunktionen, die Ihre Organisation benötigt.</span><span class="sxs-lookup"><span data-stu-id="d76a3-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="d76a3-105">Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="d76a3-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="d76a3-106">Steuern der Benutzer, die Microsoft 365-Gruppen erstellen können</span><span class="sxs-lookup"><span data-stu-id="d76a3-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="d76a3-107">Gruppen können von Endbenutzern aus mehreren Endpunkten einschließlich Outlook, SharePoint, Teams und anderen Umgebungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![Bildbeschreibung](../media/04.png)

<span data-ttu-id="d76a3-109">Self-Service wird dringend empfohlen, um Gruppenbesitzer zu bevollmächtigen und Benutzern zu helfen, ihre Arbeit leichter erledigen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="d76a3-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="d76a3-110">Das Einschränken der Gruppen-und TEAMERSTELLUNG kann die Produktivität der Benutzer verlangsamen, da viele Microsoft 365-Dienste die Erstellung von Gruppen für den Dienst erfordern.</span><span class="sxs-lookup"><span data-stu-id="d76a3-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="d76a3-111">Die folgenden Steuerungsoptionen für die Gruppenerstellung sollten beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="d76a3-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="d76a3-112">Verwenden Sie zum Begrenzen der Gruppen Zersiedelung Gruppen [Ablaufrichtlinien](microsoft-365-groups-expiration-policy.md) , um Gruppen automatisch zu löschen, die nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="d76a3-113">Beschränken Sie die Gruppenerstellung auf Mitglieder einer [Sicherheitsgruppe mit einer dynamischen Mitgliedschaft](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) , die beispielsweise alle Vollzeitmitarbeiter enthält.</span><span class="sxs-lookup"><span data-stu-id="d76a3-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="d76a3-114">Beschränken Sie die Gruppenerstellung auf eine Sicherheitsgruppe, und fordern Sie die Benutzer auf, Schulungen in den Gruppen Nutzungsrichtlinien Ihrer Organisation durchzuführen, um Mitglieder der Sicherheitsgruppe zu werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="d76a3-115">Wenn Sie einschränken möchten, wer Gruppen erstellen kann, finden Sie weitere Informationen zum Konfigurieren dieses Themas unter [Manage who can create Microsoft 365 Groups](manage-creation-of-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="d76a3-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="d76a3-116">Löschen, wiederherstellen und Archivieren von Gruppen</span><span class="sxs-lookup"><span data-stu-id="d76a3-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="d76a3-117">Wenn eine Microsoft 365-Gruppe gelöscht wird, wird Sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="d76a3-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="d76a3-118">Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="d76a3-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d76a3-119">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d76a3-120">Wenn Aufbewahrungsrichtlinien vorhanden sind, um Chat, Dateien oder e-Mail beizubehalten, werden diese Elemente nach dem Löschen der Gruppe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d76a3-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="d76a3-121">Weitere Informationen finden Sie unter [erfahren Sie mehr über Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .</span><span class="sxs-lookup"><span data-stu-id="d76a3-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="d76a3-122">Wenn Sie eine Gruppe löschen, aber den Inhalt von einem oder mehreren der Gruppen verbundenen Dienste beibehalten möchten, finden Sie weitere Informationen unter [Archivieren von Gruppen, Teams und jammern](end-life-cycle-groups-teams-sites-yammer.md) .</span><span class="sxs-lookup"><span data-stu-id="d76a3-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="d76a3-123">Gruppenbenennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d76a3-123">Group naming policy</span></span>

<span data-ttu-id="d76a3-124">Mithilfe einer Benennungsrichtlinie für Gruppen können Sie Gruppen auf zwei Arten steuern:</span><span class="sxs-lookup"><span data-stu-id="d76a3-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="d76a3-125">Eine Namensrichtlinie für Präfix/Suffix kann verwendet werden, um feste Zeichenfolgen oder Azure AD Attribute am Anfang oder Ende eines Gruppennamens und der zugehörigen e-Mail-Adresse zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="d76a3-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="d76a3-126">Auf diese Weise können Sie sicherstellen, dass z. b. Abteilungsnamen oder Regionen in Gruppennamen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="d76a3-127">Eine Richtlinie für blockierte Wörter kann sicherstellen, dass bestimmte Wörter wie die Namen von Führungskräften nicht in Gruppennamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="d76a3-128">Benennungsrichtlinien werden angewendet, wenn Gruppen von einem der Gruppen verbundenen Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="d76a3-129">Wenn Sie sich für die Verwendung von Benennungsrichtlinien für Gruppen entscheiden, lesen Sie die [Benennungsrichtlinie für Microsoft 365-Gruppen](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d76a3-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="d76a3-130">Gruppenablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d76a3-130">Group expiration policy</span></span>

<span data-ttu-id="d76a3-131">Sie können einen Ablaufzeitraum angeben, und jede Gruppe, die das Ende dieses Zeitraums erreicht und nicht erneuert wird, wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d76a3-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="d76a3-132">Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung.</span><span class="sxs-lookup"><span data-stu-id="d76a3-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="d76a3-133">Nachdem Sie Gruppen so festgelegt haben, dass Sie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="d76a3-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="d76a3-134">Besitzer der Gruppe werden benachrichtigt, um die Gruppe zu erneuern, wenn sich der Ablauf nähert.</span><span class="sxs-lookup"><span data-stu-id="d76a3-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="d76a3-135">Aktive Gruppen werden automatisch erneuert.</span><span class="sxs-lookup"><span data-stu-id="d76a3-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="d76a3-136">Eine Gruppe, die nicht erneuert wird, wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d76a3-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="d76a3-137">Jede gelöschte Gruppe kann innerhalb von 30 Tagen von den Gruppenbesitzern oder dem Administrator wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="d76a3-138">Ablaufrichtlinien sind eine gute Möglichkeit zum Begrenzen der Gruppen Zersplitterung, indem sichergestellt wird, dass nicht mehr verwendete Gruppen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="d76a3-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="d76a3-139">Wenn Sie eine Gruppen Ablaufrichtlinie erstellen möchten, finden Sie weitere Informationen unter [Microsoft 365 Group-Ablaufrichtlinie](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d76a3-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
