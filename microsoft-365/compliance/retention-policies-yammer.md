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
ms.openlocfilehash: ce3e298d5d0a034b30865e9fa1278325ce25c1e6
ms.sourcegitcommit: 27cb4591e08f62ba0a08d6dcf224bf2039034fe5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2021
ms.locfileid: "49883704"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="10952-103">Informationen zur Aufbewahrung für Yammer</span><span class="sxs-lookup"><span data-stu-id="10952-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="10952-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="10952-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="10952-105">Dieses Feature befindet sich in Vorschau und ist noch nicht für alle Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10952-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="10952-106">Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Yammer beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="10952-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="10952-107">Informationen zu anderen Arbeitsbereichen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="10952-107">For other workloads, see:</span></span>

- [<span data-ttu-id="10952-108">Informationen zur Aufbewahrung für SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="10952-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="10952-109">Informationen zur Aufbewahrung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10952-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="10952-110">Informationen zur Aufbewahrung für Exchange</span><span class="sxs-lookup"><span data-stu-id="10952-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="10952-111">Lieferumfang für Aufbewahrung und Löschung</span><span class="sxs-lookup"><span data-stu-id="10952-111">What's included for retention and deletion</span></span>

<span data-ttu-id="10952-112">Die folgenden Yammer-Elemente können mithilfe von Aufbewahrungsrichtlinien für Yammer beibehalten oder gelöscht werden: Community-Nachrichten und private Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="10952-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="10952-113">Reaktionen von anderen Personen in der Form von Emoticons sind in diesen Nachrichten nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="10952-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="10952-114">Funktionsweise einer Aufbewahrungsrichtlinie mit Yammer</span><span class="sxs-lookup"><span data-stu-id="10952-114">How retention works with Yammer</span></span>

<span data-ttu-id="10952-115">Sie können eine Aufbewahrungsrichtlinie zum Aufbewahren und Löschen von Communitynachrichten und privaten Nachrichten in Yammer verwenden.</span><span class="sxs-lookup"><span data-stu-id="10952-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="10952-116">Private Nachrichten werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der in die Nachricht eingebunden ist, und Communitynachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für die Community gespeichert.</span><span class="sxs-lookup"><span data-stu-id="10952-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="10952-117">Aufbewahrungsrichtlinien, die für Benutzer- oder Gruppenpostfächer konfiguriert sind, wirken sich nicht auf Yammer-Nachrichten aus.</span><span class="sxs-lookup"><span data-stu-id="10952-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="10952-118">Obwohl Yammer-Nachrichten in Exchange gespeichert sind, werden diese Yammer-Daten nur von einer Aufbewahrungsrichtlinie eingeschlossen, die für die Speicherorte **Yammer-Communitynachrichten** und **Private Yammer-Nachrichten** konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="10952-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="10952-119">Wenn eine aktive Aufbewahrungsrichtlinie, durch die Yammer-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Yammer-Daten aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="10952-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="10952-120">Wenn diese Yammer-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.</span><span class="sxs-lookup"><span data-stu-id="10952-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="10952-121">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, wertet ein Zeitgeberauftrag des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Yammer-Nachrichten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="10952-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="10952-122">Die Ausführung des Zeitgeberauftrags dauert bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="10952-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="10952-123">Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner "SubstrateHolds" verschoben, einen versteckten Ordner, der sich in jedem Benutzer- oder Gruppenpostfach befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="10952-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="10952-124">Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie das Aufbewahren und dann Löschen, nur das Aufbewahren oder nur das Löschen vorsieht.</span><span class="sxs-lookup"><span data-stu-id="10952-124">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="10952-125">Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und dann Löschen dient:</span><span class="sxs-lookup"><span data-stu-id="10952-125">When the retention policy is to retain and then delete:</span></span>

![Darstellung des Aufbewahrungsablaufs für Yammer-Nachrichten](../media/yammerretentionlifecycle.png)

<span data-ttu-id="10952-127">Zu den zwei Pfaden im Diagramm:</span><span class="sxs-lookup"><span data-stu-id="10952-127">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="10952-128">**Wenn eine Yammer-Nachricht während des Aufbewahrungszeitraums vom Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht sofort in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht).</span><span class="sxs-lookup"><span data-stu-id="10952-128">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="10952-129">Die Nachricht wird dort bis zum Ablauf des Aufbewahrungszeitraums gespeichert und dann sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10952-129">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="10952-130">**Wenn eine Yammer-Nachricht nicht gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung: Die Nachrichten werden nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="10952-130">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="10952-131">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="10952-131">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="10952-132">Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie sofort endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10952-132">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="10952-133">Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="10952-133">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="10952-134">Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="10952-134">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="10952-135">Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.</span><span class="sxs-lookup"><span data-stu-id="10952-135">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="10952-136">Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="10952-136">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="10952-137">**Wenn Yammer-Nachricht bearbeitet oder gelöscht wird**: Eine Kopie der Originalnachricht wird sofort im Ordner "SubstrateHolds" erstellt und dort bis zum Ablauf des Aufbewahrungszeitraums aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="10952-137">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="10952-138">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10952-138">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="10952-139">**Wenn die Yammer-Nachricht nicht geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.</span><span class="sxs-lookup"><span data-stu-id="10952-139">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="10952-140">Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen</span><span class="sxs-lookup"><span data-stu-id="10952-140">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="10952-141">**Wenn die Yammer-Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben.</span><span class="sxs-lookup"><span data-stu-id="10952-141">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="10952-142">Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="10952-142">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="10952-143">Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10952-143">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="10952-144">**Wenn die Yammer-Nachricht während des Zeitraums vom Benutzer gelöscht wird**, wird das Element sofort in den Ordner "SubstrateHolds" verschoben, wo es sofort endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="10952-144">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="10952-145">Nachrichten und externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="10952-145">Messages and external users</span></span>

<span data-ttu-id="10952-146">Standardmäßig gilt eine Aufbewahrungsrichtlinie für private Yammer-Nachrichten für alle Benutzer in Ihrer Organisation, jedoch nicht für externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="10952-146">By default, a retention policy for Yammer private messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="10952-147">Sie können eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, indem Sie die Option **Benutzer auswählen** verwenden und die fraglichen Konten angeben.</span><span class="sxs-lookup"><span data-stu-id="10952-147">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="10952-148">Zurzeit werden Azure-B2B-Gastbenutzer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10952-148">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="10952-149">Wenn ein Benutzer die Organisation verlässt</span><span class="sxs-lookup"><span data-stu-id="10952-149">When a user leaves the organization</span></span> 

<span data-ttu-id="10952-150">Wenn ein Benutzer Ihre Organisation verlässt und sein Microsoft 365-Konto gelöscht wird, werden seine privaten Yammer-Nachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="10952-150">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="10952-151">Die Nachrichten unterliegen weiterhin jeder Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10952-151">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="10952-152">Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="10952-152">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="10952-153">Wenn der Benutzer Dateien in Yammer gespeichert hat, lesen Sie den [entsprechenden Abschnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.</span><span class="sxs-lookup"><span data-stu-id="10952-153">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="10952-154">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="10952-154">Limitations</span></span>

<span data-ttu-id="10952-155">Yammer-Aufbewahrungsrichtlinien befinden sich derzeit in der Vorschau, und wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="10952-155">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="10952-156">Es gibt folgende Einschränkungen, die Sie bei der Aufbewahrung von Yammer-Community-Nachrichten und privaten Nachrichten beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="10952-156">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="10952-157">Wenn Sie **Benutzer auswählen** für den Speicherort **Private Yammer-Nachrichten** auswählen, werden möglicherweise Gäste und Nicht-Postfachbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10952-157">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="10952-158">Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.</span><span class="sxs-lookup"><span data-stu-id="10952-158">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="10952-159">Konfigurationsleitfaden</span><span class="sxs-lookup"><span data-stu-id="10952-159">Configuration guidance</span></span>

<span data-ttu-id="10952-160">Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="10952-160">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="10952-161">Wenn Sie startklar für die Erstellung einer Aufbewahrungsrichtlinie für Yammer sind, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="10952-161">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>
