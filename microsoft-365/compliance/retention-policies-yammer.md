---
title: Informationen zur Aufbewahrung für Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie Näheres über Aufbewahrungsrichtlinien, die für Yammer gelten.
ms.openlocfilehash: d4988eee419a38497d4fa35cdb3e2f7fec103688
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052927"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="c97ec-103">Informationen zur Aufbewahrung für Yammer</span><span class="sxs-lookup"><span data-stu-id="c97ec-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="c97ec-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="c97ec-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="c97ec-105">Dieses Feature ist derzeit in der Vorschau und kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c97ec-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="c97ec-106">Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Yammer beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="c97ec-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="c97ec-107">Informationen zu anderen Arbeitsbereichen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c97ec-107">For other workloads, see:</span></span>

- [<span data-ttu-id="c97ec-108">Informationen zur Aufbewahrung für SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="c97ec-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="c97ec-109">Informationen zur Aufbewahrung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c97ec-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="c97ec-110">Informationen zur Aufbewahrung für Exchange</span><span class="sxs-lookup"><span data-stu-id="c97ec-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="c97ec-111">Lieferumfang für Aufbewahrung und Löschung</span><span class="sxs-lookup"><span data-stu-id="c97ec-111">What's included for retention and deletion</span></span>

<span data-ttu-id="c97ec-112">Die folgenden Yammer-Elemente können mithilfe von Aufbewahrungsrichtlinien für Yammer beibehalten oder gelöscht werden: Community-Nachrichten und private Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c97ec-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="c97ec-113">Reaktionen von anderen Personen in der Form von Emoticons sind in diesen Nachrichten nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="c97ec-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="c97ec-114">Funktionsweise einer Aufbewahrungsrichtlinie mit Yammer</span><span class="sxs-lookup"><span data-stu-id="c97ec-114">How retention works with Yammer</span></span>

<span data-ttu-id="c97ec-115">Sie können eine Aufbewahrungsrichtlinie zum Aufbewahren und Löschen von Communitynachrichten und privaten Nachrichten in Yammer verwenden.</span><span class="sxs-lookup"><span data-stu-id="c97ec-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="c97ec-116">Private Nachrichten werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der in die Nachricht eingebunden ist, und Communitynachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für die Community gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c97ec-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="c97ec-117">Aufbewahrungsrichtlinien, die für Benutzer- oder Gruppenpostfächer konfiguriert sind, wirken sich nicht auf Yammer-Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="c97ec-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="c97ec-118">Obwohl Yammer-Nachrichten in Exchange gespeichert sind, sind diese Yammer-Daten nur in einer Aufbewahrungsrichtlinie enthalten, die für die Speicherorte von **Yammer-Communitynachrichten** und **Benutzernachrichten in Yammer** konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c97ec-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="c97ec-119">Wenn eine aktive Aufbewahrungsrichtlinie, durch die Yammer-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Yammer-Daten aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="c97ec-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="c97ec-120">Wenn diese Yammer-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.</span><span class="sxs-lookup"><span data-stu-id="c97ec-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="c97ec-121">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, wertet ein Zeitgeberauftrag des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Yammer-Nachrichten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c97ec-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="c97ec-122">Die Ausführung des Zeitgeberauftrags dauert bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="c97ec-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="c97ec-123">Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner "SubstrateHolds" verschoben, einen versteckten Ordner, der sich in jedem Benutzer- oder Gruppenpostfach befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c97ec-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="c97ec-124">Aufgrund des [ ersten Aufbewahrungsprinzips](retention.md#the-principles-of-retention-or-what-takes-precedence) wird die endgültige Löschung immer ausgesetzt, wenn dasselbe Element aufgrund von einer anderen Aufbewahrungsrichtlinie aufbewahrt werden muss oder sich aus rechtlichen oder juristischen Gründen in eDiscovery-Aufbewahrungspflichten befindet.</span><span class="sxs-lookup"><span data-stu-id="c97ec-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="c97ec-125">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie das Aufbewahren und dann Löschen, nur das Aufbewahren oder nur das Löschen vorsieht.</span><span class="sxs-lookup"><span data-stu-id="c97ec-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="c97ec-126">Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und dann Löschen dient:</span><span class="sxs-lookup"><span data-stu-id="c97ec-126">When the retention policy is to retain and then delete:</span></span>

![Darstellung des Aufbewahrungsablaufs für Yammer-Nachrichten](../media/yammerretentionlifecycle.png)

<span data-ttu-id="c97ec-128">Zu den zwei Pfaden im Diagramm:</span><span class="sxs-lookup"><span data-stu-id="c97ec-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="c97ec-129">**Wenn eine Yammer-Nachricht während des Aufbewahrungszeitraums vom Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht sofort in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht).</span><span class="sxs-lookup"><span data-stu-id="c97ec-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="c97ec-130">Die Nachricht wird dort bis zum Ablauf des Aufbewahrungszeitraums gespeichert und dann sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c97ec-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="c97ec-131">**Wenn eine Yammer-Nachricht nicht gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung: Die Nachrichten werden nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="c97ec-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="c97ec-132">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="c97ec-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="c97ec-133">Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c97ec-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="c97ec-134">Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="c97ec-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="c97ec-135">Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="c97ec-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="c97ec-136">Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.</span><span class="sxs-lookup"><span data-stu-id="c97ec-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="c97ec-137">Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c97ec-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="c97ec-138">**Wenn Yammer-Nachricht bearbeitet oder gelöscht wird**: Eine Kopie der Originalnachricht wird sofort im Ordner "SubstrateHolds" erstellt und dort bis zum Ablauf des Aufbewahrungszeitraums aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="c97ec-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="c97ec-139">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c97ec-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="c97ec-140">**Wenn die Yammer-Nachricht nicht geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.</span><span class="sxs-lookup"><span data-stu-id="c97ec-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="c97ec-141">Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen</span><span class="sxs-lookup"><span data-stu-id="c97ec-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="c97ec-142">**Wenn die Yammer-Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="c97ec-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="c97ec-143">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="c97ec-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="c97ec-144">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c97ec-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="c97ec-145">**Wenn die Yammer-Nachricht während des Zeitraums vom Benutzer gelöscht wird**, wird das Element sofort in den Ordner "SubstrateHolds" verschoben, wo es sofort endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="c97ec-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="c97ec-146">Nachrichten und externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="c97ec-146">Messages and external users</span></span>

<span data-ttu-id="c97ec-147">Standardmäßig gilt eine Aufbewahrungsrichtlinie für Benutzernachrichten in Yammer für alle Benutzer in Ihrer Organisation, jedoch nicht für externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c97ec-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="c97ec-148">Sie können eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, indem Sie die Option **Benutzer auswählen** verwenden und die fraglichen Konten angeben.</span><span class="sxs-lookup"><span data-stu-id="c97ec-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="c97ec-149">Zurzeit werden Azure-B2B-Gastbenutzer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c97ec-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="c97ec-150">Wenn ein Benutzer die Organisation verlässt</span><span class="sxs-lookup"><span data-stu-id="c97ec-150">When a user leaves the organization</span></span> 

<span data-ttu-id="c97ec-151">Wenn ein Benutzer Ihre Organisation verlässt und sein Microsoft 365-Konto gelöscht wird, werden seine Benutzernachrichten in Yammer, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c97ec-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="c97ec-152">Die Nachrichten unterliegen weiterhin jeder Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c97ec-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="c97ec-153">Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c97ec-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="c97ec-154">Wenn der Benutzer Dateien in Yammer gespeichert hat, lesen Sie den [entsprechenden Abschnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c97ec-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="c97ec-155">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c97ec-155">Limitations</span></span>

<span data-ttu-id="c97ec-156">Yammer-Aufbewahrungsrichtlinien befinden sich derzeit in der Vorschau, und wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c97ec-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="c97ec-157">Es gibt folgende Einschränkungen, die Sie bei der Aufbewahrung von Yammer-Community-Nachrichten und privaten Nachrichten beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="c97ec-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="c97ec-158">Wenn Sie **Benutzer auswählen** für den Speicherort **Benutzernachrichten in Yammer** auswählen, werden möglicherweise Gäste und Nicht-Postfachbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c97ec-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="c97ec-159">Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="c97ec-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="c97ec-160">Konfigurationsleitfaden</span><span class="sxs-lookup"><span data-stu-id="c97ec-160">Configuration guidance</span></span>

<span data-ttu-id="c97ec-161">Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="c97ec-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="c97ec-162">Wenn Sie startklar für die Erstellung einer Aufbewahrungsrichtlinie für Yammer sind, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c97ec-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>