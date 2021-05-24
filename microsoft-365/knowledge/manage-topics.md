---
title: Verwalten von Themen im Themencenter in Microsoft Viva Topics
description: Verwalten von Themen im Themencenter.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: ba8f27c90f9c84729a10f461e85b2e1441b49549
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625401"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="47b71-103">Verwalten von Themen im Themencenter in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="47b71-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="47b71-104">Im Themencenter "Viva Topics" kann  ein Wissensmanager die Seite Themen verwalten anzeigen, um Themen zu überprüfen, die in den Quellstandorten identifiziert wurden, wie von Ihrem Wissensadministrator angegeben.</span><span class="sxs-lookup"><span data-stu-id="47b71-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Topic Center](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="47b71-106">Themenphasen</span><span class="sxs-lookup"><span data-stu-id="47b71-106">Topic stages</span></span>

<span data-ttu-id="47b71-107">Wissensmanager helfen dabei, ermittelte Themen durch die verschiedenen Lebenszyklusphasen des Themas zu führen: **Vorgeschlagen**, **Bestätigt**, **Veröffentlicht** und **Entfernt**.</span><span class="sxs-lookup"><span data-stu-id="47b71-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Topic-Lifecycle-Diagramm](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="47b71-109">**Vorgeschlagen**: Ein Thema wurde von KI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="47b71-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="47b71-110">(Diese werden in der Benutzeroberfläche **als vorgeschlagenes** Thema gekennzeichnet.)</span><span class="sxs-lookup"><span data-stu-id="47b71-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="47b71-111">**Bestätigt**: Ein Thema, das von AI erkannt und überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="47b71-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="47b71-112">Die Themenüberprüfung erfolgt, wenn eine der beiden:</span><span class="sxs-lookup"><span data-stu-id="47b71-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="47b71-113">Ein Knowledge Manager bestätigt ein Thema.</span><span class="sxs-lookup"><span data-stu-id="47b71-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="47b71-114">Ein Knowledge Manager [bestätigt ein Thema auf](manage-topics.md#confirmed-topics) der Seite Themen **verwalten.**</span><span class="sxs-lookup"><span data-stu-id="47b71-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="47b71-115">Mehrere Benutzer bestätigen ein Thema.</span><span class="sxs-lookup"><span data-stu-id="47b71-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="47b71-116">Es muss ein Netz von zwei positiven Stimmen von Benutzern sein, die mit dem Feedbackmechanismus auf der Themenkarte abgestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="47b71-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="47b71-117">Wenn beispielsweise ein Benutzer für ein bestimmtes Thema positiv und ein Benutzer für ein bestimmtes Thema negativ stimmte, benötigen Sie noch zwei weitere positive Stimmen, damit das Thema bestätigt wird.</span><span class="sxs-lookup"><span data-stu-id="47b71-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="47b71-118">**Veröffentlicht**: Ein Thema, das kuratiert wurde.</span><span class="sxs-lookup"><span data-stu-id="47b71-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="47b71-119">Manuelle Bearbeitungen wurden vorgenommen, um die Qualität zu verbessern, oder sie wurden von einem Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="47b71-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="47b71-120">**Entfernt:** Ein Thema, das abgelehnt wurde und für die Betrachter nicht mehr sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="47b71-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="47b71-121">Ein Thema kann in einem beliebigen Zustand entfernt werden (vorgeschlagen, bestätigt oder veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="47b71-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="47b71-122">Das Entfernen von Themen erfolgt, wenn eine der beiden:</span><span class="sxs-lookup"><span data-stu-id="47b71-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="47b71-123">Ein Knowledge Manager entfernt ein Thema.</span><span class="sxs-lookup"><span data-stu-id="47b71-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="47b71-124">Ein Knowledge Manager entfernt ein Thema auf der Seite **Themen** verwalten.</span><span class="sxs-lookup"><span data-stu-id="47b71-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="47b71-125">Mehrere Benutzer geben negative Stimmen mit dem Feedbackmechanismus auf der Themenkarte ab.</span><span class="sxs-lookup"><span data-stu-id="47b71-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="47b71-126">Damit ein Thema entfernt werden kann, muss ein Netz von zwei negativen Stimmen von Benutzern empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="47b71-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="47b71-127">Wenn beispielsweise ein Benutzer negativ und ein Benutzer für ein bestimmtes Thema positiv stimmte, benötigen Sie noch zwei negative Stimmen, damit das Thema entfernt werden kann.</span><span class="sxs-lookup"><span data-stu-id="47b71-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="47b71-128">Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den kuratierten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="47b71-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="47b71-129">Auf der Seite Themen **verwalten** kann jeder Wissensmanager nur Themen anzeigen, in denen er Zugriff auf die zugrunde liegenden Dateien und Seiten hat, die mit dem Thema verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="47b71-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="47b71-130">Diese Berechtigungstrimmerung wird in der Liste der Themen angezeigt, die auf den Registerkarten **Vorgeschlagen,** **Bestätigt,** Veröffentlicht **und** **Entfernt angezeigt** werden.</span><span class="sxs-lookup"><span data-stu-id="47b71-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="47b71-131">Die Anzahl der Themen zeigt jedoch unabhängig von berechtigungen die Gesamtzahlen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="47b71-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="47b71-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47b71-132">Requirements</span></span>

<span data-ttu-id="47b71-133">Zum Verwalten von Themen im Themencenter müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="47b71-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="47b71-134">Über eine Viva Topics-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="47b71-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="47b71-135">Verfügen Sie über [**Wer, die Themen verwalten**](./topic-experiences-user-permissions.md) können.</span><span class="sxs-lookup"><span data-stu-id="47b71-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="47b71-136">Wissensadministratoren können Benutzern diese Berechtigung in den Berechtigungseinstellungen von Viva Topics erteilen.</span><span class="sxs-lookup"><span data-stu-id="47b71-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="47b71-137">Sie können die Seite  Themen verwalten im Themencenter nur anzeigen, wenn Sie über die Berechtigung Wer **Themen verwalten** verfügen.</span><span class="sxs-lookup"><span data-stu-id="47b71-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="47b71-138">Im Themencenter kann ein Wissensmanager Themen überprüfen, die an den von Ihnen angegebenen Quellstandorten identifiziert wurden, und diese entweder bestätigen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="47b71-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="47b71-139">Ein Knowledge Manager kann auch neue Themenseiten erstellen und veröffentlichen, wenn sie nicht in der Themensuche gefunden wurden, oder vorhandene Bearbeiten, wenn sie aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="47b71-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="47b71-140">Überprüfen der vorgeschlagenen Themen</span><span class="sxs-lookup"><span data-stu-id="47b71-140">Review suggested topics</span></span>

<span data-ttu-id="47b71-141">Auf der **Seite Themen verwalten** werden Themen, die in den angegebenen Quellstandorten SharePoint gefunden wurden, auf der Registerkarte **Vorgeschlagen** aufgeführt. Bei Bedarf kann ein Wissensmanager unbestätigte Themen überprüfen und diese bestätigen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="47b71-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Vorgeschlagene Themen](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="47b71-143">So überprüfen Sie ein vorgeschlagenes Thema:</span><span class="sxs-lookup"><span data-stu-id="47b71-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="47b71-144">Wählen Sie **auf der Seite** Themen verwalten die Registerkarte Vorgeschlagen aus, und wählen Sie dann das Thema aus, um die Themenseite zu öffnen. </span><span class="sxs-lookup"><span data-stu-id="47b71-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="47b71-145">Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="47b71-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="47b71-146">Wenn Sie alle Bearbeitungen veröffentlichen, wird dieses Thema auf die Registerkarte **Veröffentlicht** verschieben.</span><span class="sxs-lookup"><span data-stu-id="47b71-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="47b71-147">Nachdem Sie das Thema überprüft haben, wechseln Sie zurück zur Seite **Themen** verwalten.</span><span class="sxs-lookup"><span data-stu-id="47b71-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="47b71-148">Für das ausgewählte Thema können Sie:</span><span class="sxs-lookup"><span data-stu-id="47b71-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="47b71-149">Aktivieren Sie das Häkchen, um das Thema zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="47b71-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="47b71-150">Wählen Sie **das x** aus, wenn Sie das Thema entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="47b71-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="47b71-151">Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und werden nun in der **Liste Bestätigt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47b71-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="47b71-152">Entfernte Themen werden aus der **Vorgeschlagenen** Liste entfernt und werden nun auf der Registerkarte **Entfernt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47b71-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="47b71-153">Qualitätsergebnis</span><span class="sxs-lookup"><span data-stu-id="47b71-153">Quality score</span></span>

<span data-ttu-id="47b71-154">Jedem Thema, das auf **der** Seite Vorgeschlagene Themen angezeigt wird, wird eine Qualitätsnote zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="47b71-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="47b71-155">Die Qualitätskontrolle spiegelt die Informationsmenge wider, die dem durchschnittlichen Benutzer für die Informationen zu diesem Thema angezeigt wird, und dabei zu berücksichtigen, dass für jeden Benutzer aufgrund der Berechtigungen, die er möglicherweise für die Informationen in einem Thema hat, mehr oder weniger Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="47b71-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="47b71-156">Die Qualitätsnote kann einen Einblick in die Themen mit den meisten Informationen bieten und hilfreich sein, um Themen zu finden, die möglicherweise manuell bearbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="47b71-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="47b71-157">Beispielsweise kann ein Thema mit einer niedrigeren Qualitätsnote das Ergebnis davon sein, dass einige Benutzer nicht über SharePoint Berechtigungen für relevante Dateien oder Websites verfügen, die AI in das Thema aufgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="47b71-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="47b71-158">Ein Mitwirkender kann dann das Thema bearbeiten, um die Informationen (falls zutreffend) aufzunehmen, die dann für alle Benutzer, die das Thema anzeigen können, sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="47b71-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="47b71-159">Eindrücke</span><span class="sxs-lookup"><span data-stu-id="47b71-159">Impressions</span></span>

<span data-ttu-id="47b71-160">In **der Spalte** Impressionen wird angezeigt, wie oft ein Thema endbenutzern angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="47b71-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="47b71-161">Dies umfasst Ansichten über Themenantwortkarten in der Suche und über Themenhighlights.</span><span class="sxs-lookup"><span data-stu-id="47b71-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="47b71-162">Es spiegelt nicht das Klicken auf diese Themen wider, sondern das Thema wurde angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47b71-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="47b71-163">Die **Spalte Impressionen** wird für Themen auf den  Registerkarten **Vorgeschlagen,** **Bestätigt,** Veröffentlicht und Entfernt auf der Seite **Themen verwalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47b71-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="47b71-164">Bestätigte Themen</span><span class="sxs-lookup"><span data-stu-id="47b71-164">Confirmed topics</span></span>

<span data-ttu-id="47b71-165">Auf  der Seite Themen verwalten werden Themen, die in Ihren angegebenen SharePoint-Quellstandorten entdeckt wurden und von einem Knowledge Manager oder "crowdsourced" bestätigt wurden, der von zwei oder mehr Personen (Ausgleich negativer Benutzerstimmen gegen positive Benutzerstimmen) durch den Kartenfeedbackmechanismus bestätigt wurde, auf der Registerkarte **Bestätigt** aufgeführt. Bei Bedarf kann ein Benutzer mit berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="47b71-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="47b71-166">So überprüfen Sie ein bestätigtes Thema:</span><span class="sxs-lookup"><span data-stu-id="47b71-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="47b71-167">Wählen Sie auf der Registerkarte **Bestätigt** das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="47b71-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="47b71-168">Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="47b71-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="47b71-169">Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="47b71-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="47b71-170">Wechseln Sie dazu auf der Registerkarte  Bestätigt zum ausgewählten Thema, und wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="47b71-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="47b71-171">Veröffentlichte Themen</span><span class="sxs-lookup"><span data-stu-id="47b71-171">Published topics</span></span>

<span data-ttu-id="47b71-172">Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen.</span><span class="sxs-lookup"><span data-stu-id="47b71-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="47b71-173">Auch manuell erstellte Themen werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="47b71-173">Manually created topics are listed here as well.</span></span>

   ![Verwalten von Themen](../media/knowledge-management/manage-topics-new.png)
