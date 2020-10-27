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
ms.openlocfilehash: 84db671b475a9dade039136380cef0bc5bde7282
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754703"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="a3782-103">Informationen zur Aufbewahrung für Yammer</span><span class="sxs-lookup"><span data-stu-id="a3782-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="a3782-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a3782-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a3782-105">Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Yammer beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="a3782-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="a3782-106">Informationen zu anderen Arbeitsbereichen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a3782-106">For other workloads, see:</span></span>

- [<span data-ttu-id="a3782-107">Informationen zur Aufbewahrung für SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="a3782-107">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="a3782-108">Informationen zur Aufbewahrung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3782-108">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="a3782-109">Informationen zur Aufbewahrung für Exchange</span><span class="sxs-lookup"><span data-stu-id="a3782-109">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="a3782-110">Lieferumfang für Aufbewahrung und Löschung</span><span class="sxs-lookup"><span data-stu-id="a3782-110">What's included for retention and deletion</span></span>

<span data-ttu-id="a3782-111">Die folgenden Yammer-Elemente können mithilfe von Aufbewahrungsrichtlinien für Yammer beibehalten oder gelöscht werden: Community-Nachrichten und private Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a3782-111">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="a3782-112">Reaktionen von anderen Personen in der Form von Emoticons sind in diesen Nachrichten nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="a3782-112">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="a3782-113">Funktionsweise einer Aufbewahrungsrichtlinie mit Yammer</span><span class="sxs-lookup"><span data-stu-id="a3782-113">How retention works with Yammer</span></span>

<span data-ttu-id="a3782-114">Sie können eine Aufbewahrungsrichtlinie zum Aufbewahren und Löschen von Communitynachrichten und privaten Nachrichten in Yammer verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3782-114">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="a3782-115">Private Nachrichten werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der in die Nachricht eingebunden ist, und Communitynachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für die Community gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a3782-115">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="a3782-116">Aufbewahrungsrichtlinien, die für Benutzer- oder Gruppenpostfächer konfiguriert sind, wirken sich nicht auf Yammer-Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="a3782-116">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="a3782-117">Obwohl Yammer-Nachrichten in Exchange gespeichert sind, werden diese Yammer-Daten nur von einer Aufbewahrungsrichtlinie eingeschlossen, die für die Speicherorte **Yammer-Communitynachrichten** und **Private Yammer-Nachrichten** konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a3782-117">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="a3782-118">Wenn eine aktive Aufbewahrungsrichtlinie, durch die Yammer-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Yammer-Daten aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="a3782-118">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="a3782-119">Wenn diese Yammer-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.</span><span class="sxs-lookup"><span data-stu-id="a3782-119">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="a3782-120">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, wertet ein Zeitgeberauftrag des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Yammer-Nachrichten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a3782-120">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="a3782-121">Die Ausführung des Zeitgeberauftrags dauert bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="a3782-121">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="a3782-122">Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner "SubstrateHolds" verschoben, einen versteckten Ordner, der sich in jedem Benutzer- oder Gruppenpostfach befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a3782-122">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="a3782-123">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie das Aufbewahren und dann Löschen, nur das Aufbewahren oder nur das Löschen vorsieht.</span><span class="sxs-lookup"><span data-stu-id="a3782-123">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="a3782-124">Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und dann Löschen dient:</span><span class="sxs-lookup"><span data-stu-id="a3782-124">When the retention policy is to retain and then delete:</span></span>

![Darstellung des Aufbewahrungsablaufs für Yammer-Nachrichten](../media/yammerretentionlifecycle.png)

<span data-ttu-id="a3782-126">Zu den zwei Pfaden im Diagramm:</span><span class="sxs-lookup"><span data-stu-id="a3782-126">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="a3782-127">**Wenn eine Yammer-Nachricht während des Aufbewahrungszeitraums vom Benutzer bearbeitet oder gelöscht wird** , wird die Originalnachricht sofort in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht).</span><span class="sxs-lookup"><span data-stu-id="a3782-127">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="a3782-128">Die Nachricht wird dort bis zum Ablauf des Aufbewahrungszeitraums gespeichert und dann sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a3782-128">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="a3782-129">**Wenn eine Yammer-Nachricht nicht gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung: Die Nachrichten werden nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="a3782-129">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="a3782-130">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="a3782-130">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="a3782-131">Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a3782-131">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3782-132">Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="a3782-132">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="a3782-133">Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="a3782-133">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="a3782-134">Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.</span><span class="sxs-lookup"><span data-stu-id="a3782-134">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="a3782-135">Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a3782-135">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="a3782-136">**Wenn Yammer-Nachricht bearbeitet oder gelöscht wird** : Eine Kopie der Originalnachricht wird sofort im Ordner "SubstrateHolds" erstellt und dort bis zum Ablauf des Aufbewahrungszeitraums aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="a3782-136">**If a Yammer message is edited or deleted** : A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="a3782-137">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a3782-137">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="a3782-138">**Wenn die Yammer-Nachricht nicht geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.</span><span class="sxs-lookup"><span data-stu-id="a3782-138">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="a3782-139">Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen</span><span class="sxs-lookup"><span data-stu-id="a3782-139">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="a3782-140">**Wenn die Yammer-Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird** : Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="a3782-140">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="a3782-141">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="a3782-141">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="a3782-142">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a3782-142">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="a3782-143">**Wenn die Yammer-Nachricht während des Zeitraums vom Benutzer gelöscht wird** , wird das Element sofort in den Ordner "SubstrateHolds" verschoben, wo es sofort endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="a3782-143">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="a3782-144">Nachrichten und externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="a3782-144">Messages and external users</span></span>

<span data-ttu-id="a3782-145">Standardmäßig gilt eine Aufbewahrungsrichtlinie für private Yammer-Nachrichten für alle Benutzer in Ihrer Organisation, jedoch nicht für externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a3782-145">By default, a retention policy for Yammer private messages apply to all users in your organization, but not external users.</span></span> <span data-ttu-id="a3782-146">Sie können eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, indem Sie die Option **Benutzer auswählen** verwenden und die fraglichen Konten angeben.</span><span class="sxs-lookup"><span data-stu-id="a3782-146">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="a3782-147">Zurzeit werden Azure-B2B-Gastbenutzer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3782-147">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="a3782-148">Wenn ein Benutzer die Organisation verlässt</span><span class="sxs-lookup"><span data-stu-id="a3782-148">When a user leaves the organization</span></span> 

<span data-ttu-id="a3782-149">Wenn ein Benutzer Ihre Organisation verlässt und sein Microsoft 365-Konto gelöscht wird, werden seine privaten Yammer-Nachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a3782-149">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="a3782-150">Die Nachrichten unterliegen weiterhin jeder Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3782-150">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="a3782-151">Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a3782-151">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="a3782-152">Wenn der Benutzer Dateien in Yammer gespeichert hat, lesen Sie den [entsprechenden Abschnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a3782-152">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="a3782-153">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a3782-153">Limitations</span></span>

<span data-ttu-id="a3782-154">Yammer-Aufbewahrungsrichtlinien befinden sich derzeit in der Vorschau, und wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="a3782-154">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="a3782-155">Es gibt folgende Einschränkungen, die Sie bei der Aufbewahrung von Yammer-Community-Nachrichten und privaten Nachrichten beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="a3782-155">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="a3782-156">Wenn Sie **Benutzer auswählen** für den Speicherort **Private Yammer-Nachrichten** auswählen, werden möglicherweise Gäste und Nicht-Postfachbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3782-156">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="a3782-157">Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="a3782-157">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="a3782-158">Konfigurationsleitfaden</span><span class="sxs-lookup"><span data-stu-id="a3782-158">Configuration guidance</span></span>

<span data-ttu-id="a3782-159">Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="a3782-159">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="a3782-160">Wenn Sie startklar für die Erstellung einer Aufbewahrungsrichtlinie für Yammer sind, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a3782-160">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>
