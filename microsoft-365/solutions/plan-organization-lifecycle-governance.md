---
title: Planen der Organisations- und Lebenszyklussteuerung für Microsoft 365 gruppen und Microsoft Teams
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
recommendations: false
description: Lean about lifecycle governance options for collaboration tools in Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538819"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="3528c-103">Planen der Organisations- und Lebenszyklussteuerung für Microsoft 365 gruppen und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3528c-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="3528c-104">Microsoft 365 gruppen verfügt über eine reihe von Tools, um die Governancefunktionen zu implementieren, die Ihre Organisation benötigt.</span><span class="sxs-lookup"><span data-stu-id="3528c-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="3528c-105">Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="3528c-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="3528c-106">Steuern, wer benutzergruppen Microsoft 365 kann</span><span class="sxs-lookup"><span data-stu-id="3528c-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="3528c-107">Gruppen können von Endbenutzern aus mehreren Endpunkten erstellt werden, einschließlich Outlook, SharePoint, Teams und anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="3528c-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![Bildbeschreibung](../media/04.png)

<span data-ttu-id="3528c-109">Wir empfehlen dringend Self-Service, um Gruppenbesitzer zu unterstützen und Benutzern zu helfen, ihre Arbeit einfacher zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="3528c-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="3528c-110">Das Einschränken der Gruppen- und Teamerstellung kann die Produktivität der Benutzer beeinträchtigen, da viele Microsoft 365 erfordern, dass Gruppen erstellt werden, damit der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3528c-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="3528c-111">Berücksichtigen Sie die folgenden Steuerungsoptionen für die Gruppenerstellung:</span><span class="sxs-lookup"><span data-stu-id="3528c-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="3528c-112">Verwenden Sie zum Einschränken der Gruppensprawlung [Ablaufrichtlinien](microsoft-365-groups-expiration-policy.md) für Gruppen, um nicht verwendete Gruppen automatisch zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3528c-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="3528c-113">Beschränken Sie die Gruppenerstellung auf Mitglieder einer [Sicherheitsgruppe](/azure/active-directory/users-groups-roles/groups-create-rule) mit dynamischer Mitgliedschaft, die z. B. alle Vollzeitmitarbeiter enthält.</span><span class="sxs-lookup"><span data-stu-id="3528c-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="3528c-114">Beschränken Sie die Gruppenerstellung auf eine Sicherheitsgruppe, und fordern Sie, dass Benutzer Schulungen in den Gruppenverwendungsrichtlinien Ihrer Organisation abschließen müssen, um Mitglied der Sicherheitsgruppe zu werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="3528c-115">Wenn Sie einschränken möchten, wer Gruppen erstellen kann, finden Sie unter [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) weitere Informationen zur Konfiguration dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="3528c-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="3528c-116">Gruppenlöschen, Wiederherstellen und Archivierung</span><span class="sxs-lookup"><span data-stu-id="3528c-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="3528c-117">Wenn eine Microsoft 365 gelöscht wird, wird sie standardmäßig 30 Tage lang aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="3528c-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="3528c-118">Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="3528c-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="3528c-119">Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="3528c-120">Wenn Aufbewahrungsrichtlinien zum Beibehalten von Chats, Dateien oder E-Mails erstellt wurden, werden diese Elemente beibehalten, nachdem die Gruppe gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="3528c-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="3528c-121">Weitere [Informationen finden Sie unter Informationen](../compliance/retention.md) zu Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="3528c-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="3528c-122">Wenn Sie eine Gruppe löschen möchten, aber den Inhalt aus einem oder mehreren der mit einer Gruppe verbundenen Dienste beibehalten möchten, finden Sie weitere Informationen unter Archivieren von [Gruppen,](end-life-cycle-groups-teams-sites-yammer.md) Teams und Yammer Informationen.</span><span class="sxs-lookup"><span data-stu-id="3528c-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="3528c-123">Gruppenbenennungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3528c-123">Group naming policy</span></span>

<span data-ttu-id="3528c-124">Eine Gruppenbenennungsrichtlinie kann Ihnen dabei helfen, Gruppen auf zwei Arten zu steuern:</span><span class="sxs-lookup"><span data-stu-id="3528c-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="3528c-125">Eine Präfix-/Suffixbenennungsrichtlinie kann verwendet werden, um feste Zeichenfolgen oder Azure AD-Attribute am Anfang oder Ende eines Gruppennamens und der zugehörigen E-Mail-Adresse zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3528c-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="3528c-126">Auf diese Art können Sie sicherstellen, dass beispielsweise Abteilungsnamen oder Regionen in Gruppennamen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3528c-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="3528c-127">Eine Richtlinie für blockierte Wörter kann sicherstellen, dass bestimmte Wörter, z. B. die Namen von Führungskräften, nicht in Gruppennamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="3528c-128">Benennungsrichtlinien werden angewendet, wenn Gruppen aus einem der mit einer Gruppe verbundenen Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="3528c-129">Wenn Sie sich für die Verwendung von Benennungsrichtlinien für Gruppen entscheiden, lesen Sie [Microsoft 365 Namensrichtlinie für Gruppen](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3528c-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="3528c-130">Gruppenablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3528c-130">Group expiration policy</span></span>

<span data-ttu-id="3528c-131">Sie können einen Ablaufzeitraum angeben, und alle Gruppen, die das Ende dieses Zeitraums erreichen und nicht verlängert werden, werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3528c-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="3528c-132">Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung.</span><span class="sxs-lookup"><span data-stu-id="3528c-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="3528c-133">Sobald Sie festgelegt haben, dass Gruppen ablaufen:</span><span class="sxs-lookup"><span data-stu-id="3528c-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="3528c-134">Besitzer der Gruppe werden benachrichtigt, die Gruppe zu verlängern, sobald sich der Ablauf nähert.</span><span class="sxs-lookup"><span data-stu-id="3528c-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="3528c-135">Aktive Gruppen werden automatisch erneuert.</span><span class="sxs-lookup"><span data-stu-id="3528c-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="3528c-136">Alle nicht verlängerten Gruppen werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3528c-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="3528c-137">Alle gelöschten Gruppen können von den Gruppenbesitzern oder dem Administrator innerhalb von 30 Tagen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="3528c-138">Ablaufrichtlinien sind eine gute Möglichkeit, die Zersiedelung von Gruppen zu begrenzen, indem sichergestellt wird, dass nicht mehr verwendete Gruppen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3528c-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="3528c-139">Wenn Sie eine Gruppenablaufrichtlinie erstellen möchten, lesen Sie [Microsoft 365 Gruppenablaufrichtlinie](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3528c-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3528c-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3528c-140">Related topics</span></span>

[<span data-ttu-id="3528c-141">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="3528c-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="3528c-142">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="3528c-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="3528c-143">Entfernen eines ehemaligen Mitarbeiters und sicherer Daten</span><span class="sxs-lookup"><span data-stu-id="3528c-143">Remove a former employee and secure data</span></span>](/microsoft-365/admin/add-users/remove-former-employee)
