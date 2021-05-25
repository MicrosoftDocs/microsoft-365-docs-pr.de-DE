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
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651157"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="7d742-103">Verwalten von Themen im Themencenter in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="7d742-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="7d742-104">Im Themencenter "Viva Topics" kann  ein Wissensmanager die Seite Themen verwalten anzeigen, um Themen zu überprüfen, die in den Quellstandorten identifiziert wurden, wie von Ihrem Wissensadministrator angegeben.</span><span class="sxs-lookup"><span data-stu-id="7d742-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Topic Center](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="7d742-106">Themenphasen</span><span class="sxs-lookup"><span data-stu-id="7d742-106">Topic stages</span></span>

<span data-ttu-id="7d742-107">Wissensmanager helfen dabei, ermittelte Themen durch die verschiedenen Lebenszyklusphasen des Themas zu führen: **Vorgeschlagen**, **Bestätigt**, **Veröffentlicht** und **Entfernt**.</span><span class="sxs-lookup"><span data-stu-id="7d742-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Topic-Lifecycle-Diagramm](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="7d742-109">**Vorgeschlagen**: Ein Thema wurde von KI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7d742-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="7d742-110">(Diese werden in der Benutzeroberfläche **als vorgeschlagenes** Thema gekennzeichnet.)</span><span class="sxs-lookup"><span data-stu-id="7d742-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="7d742-111">**Bestätigt**: Ein Thema, das von AI erkannt und überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="7d742-111">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="7d742-112">Die Themenüberprüfung erfolgt, wenn eine der beiden:</span><span class="sxs-lookup"><span data-stu-id="7d742-112">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="7d742-113">Ein Knowledge Manager bestätigt ein Thema.</span><span class="sxs-lookup"><span data-stu-id="7d742-113">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="7d742-114">Ein Knowledge Manager [bestätigt ein Thema auf](manage-topics.md#confirmed-topics) der Seite Themen **verwalten.**</span><span class="sxs-lookup"><span data-stu-id="7d742-114">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="7d742-115">Mehrere Benutzer bestätigen ein Thema.</span><span class="sxs-lookup"><span data-stu-id="7d742-115">Multiple users confirm a topic.</span></span> <span data-ttu-id="7d742-116">Es muss ein Netz von zwei positiven Stimmen von Benutzern sein, die mit dem Feedbackmechanismus auf der Themenkarte abgestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="7d742-116">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="7d742-117">Wenn beispielsweise ein Benutzer für ein bestimmtes Thema positiv und ein Benutzer für ein bestimmtes Thema negativ stimmte, benötigen Sie noch zwei weitere positive Stimmen, damit das Thema bestätigt wird.</span><span class="sxs-lookup"><span data-stu-id="7d742-117">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="7d742-118">**Veröffentlicht**: Ein Thema, das kuratiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7d742-118">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="7d742-119">Manuelle Bearbeitungen wurden vorgenommen, um die Qualität zu verbessern, oder sie wurden von einem Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d742-119">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="7d742-120">**Entfernt:** Ein Thema, das abgelehnt wurde und für die Betrachter nicht mehr sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d742-120">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="7d742-121">Ein Thema kann in einem beliebigen Zustand entfernt werden (vorgeschlagen, bestätigt oder veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="7d742-121">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="7d742-122">Das Entfernen von Themen erfolgt, wenn eine der beiden:</span><span class="sxs-lookup"><span data-stu-id="7d742-122">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="7d742-123">Ein Knowledge Manager entfernt ein Thema.</span><span class="sxs-lookup"><span data-stu-id="7d742-123">A knowledge manager removes a topic.</span></span> <span data-ttu-id="7d742-124">Ein Knowledge Manager entfernt ein Thema auf der Seite **Themen** verwalten.</span><span class="sxs-lookup"><span data-stu-id="7d742-124">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="7d742-125">Mehrere Benutzer geben negative Stimmen mit dem Feedbackmechanismus auf der Themenkarte ab.</span><span class="sxs-lookup"><span data-stu-id="7d742-125">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="7d742-126">Damit ein Thema entfernt werden kann, muss ein Netz von zwei negativen Stimmen von Benutzern empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="7d742-126">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="7d742-127">Wenn beispielsweise ein Benutzer negativ und ein Benutzer für ein bestimmtes Thema positiv stimmte, benötigen Sie noch zwei negative Stimmen, damit das Thema entfernt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d742-127">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="7d742-128">Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den kuratierten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7d742-128">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="7d742-129">Auf der Seite Themen **verwalten** kann jeder Wissensmanager nur Themen anzeigen, in denen er Zugriff auf die zugrunde liegenden Dateien und Seiten hat, die mit dem Thema verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7d742-129">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="7d742-130">Diese Berechtigungstrimmerung wird in der Liste der Themen angezeigt, die auf den Registerkarten **Vorgeschlagen,** **Bestätigt,** Veröffentlicht **und** **Entfernt angezeigt** werden.</span><span class="sxs-lookup"><span data-stu-id="7d742-130">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="7d742-131">Die Anzahl der Themen zeigt jedoch unabhängig von berechtigungen die Gesamtzahlen in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="7d742-131">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d742-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d742-132">Requirements</span></span>

<span data-ttu-id="7d742-133">Zum Verwalten von Themen im Themencenter müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="7d742-133">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="7d742-134">Über eine Viva Topics-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="7d742-134">Have a Viva Topics license.</span></span>

- <span data-ttu-id="7d742-135">Verfügen Sie über [**Wer, die Themen verwalten**](./topic-experiences-user-permissions.md) können.</span><span class="sxs-lookup"><span data-stu-id="7d742-135">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="7d742-136">Wissensadministratoren können Benutzern diese Berechtigung in den Berechtigungseinstellungen von Viva Topics erteilen.</span><span class="sxs-lookup"><span data-stu-id="7d742-136">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="7d742-137">Sie können die Seite  Themen verwalten im Themencenter nur anzeigen, wenn Sie über die Berechtigung Wer **Themen verwalten** verfügen.</span><span class="sxs-lookup"><span data-stu-id="7d742-137">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="7d742-138">Im Themencenter kann ein Wissensmanager Themen überprüfen, die an den von Ihnen angegebenen Quellstandorten identifiziert wurden, und diese entweder bestätigen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="7d742-138">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="7d742-139">Ein Knowledge Manager kann auch neue Themenseiten erstellen und veröffentlichen, wenn sie nicht in der Themensuche gefunden wurden, oder vorhandene Bearbeiten, wenn sie aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7d742-139">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="7d742-140">Überprüfen der vorgeschlagenen Themen</span><span class="sxs-lookup"><span data-stu-id="7d742-140">Review suggested topics</span></span>

<span data-ttu-id="7d742-141">Auf der **Seite Themen verwalten** werden Themen, die in den angegebenen Quellstandorten SharePoint gefunden wurden, auf der Registerkarte **Vorgeschlagen** aufgeführt. Bei Bedarf kann ein Wissensmanager unbestätigte Themen überprüfen und diese bestätigen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="7d742-141">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Vorgeschlagene Themen](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="7d742-143">So überprüfen Sie ein vorgeschlagenes Thema:</span><span class="sxs-lookup"><span data-stu-id="7d742-143">To review a suggested topic:</span></span>

1. <span data-ttu-id="7d742-144">Wählen Sie **auf der Seite** Themen verwalten die Registerkarte Vorgeschlagen aus, und wählen Sie dann das Thema aus, um die Themenseite zu öffnen. </span><span class="sxs-lookup"><span data-stu-id="7d742-144">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="7d742-145">Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7d742-145">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="7d742-146">Wenn Sie alle Bearbeitungen veröffentlichen, wird dieses Thema auf die Registerkarte **Veröffentlicht** verschieben.</span><span class="sxs-lookup"><span data-stu-id="7d742-146">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="7d742-147">Nachdem Sie das Thema überprüft haben, wechseln Sie zurück zur Seite **Themen** verwalten.</span><span class="sxs-lookup"><span data-stu-id="7d742-147">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="7d742-148">Für das ausgewählte Thema können Sie folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="7d742-148">For the selected topic, you can:</span></span>

   - <span data-ttu-id="7d742-149">Das Kontrollkästchen aktivieren, um das Thema zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7d742-149">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="7d742-150">Wählen Sie **das x** aus, wenn Sie das Thema entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d742-150">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="7d742-151">Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und werden nun in der **Liste Bestätigt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d742-151">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="7d742-152">Entfernte Themen werden aus der **Vorgeschlagenen** Liste entfernt und werden nun auf der Registerkarte **Entfernt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d742-152">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="7d742-153">Qualitätsergebnis</span><span class="sxs-lookup"><span data-stu-id="7d742-153">Quality score</span></span>

<span data-ttu-id="7d742-154">Jedem Thema, das auf **der** Seite Vorgeschlagene Themen angezeigt wird, wird eine Qualitätsnote zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7d742-154">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="7d742-155">Die Qualitätskontrolle spiegelt die Informationsmenge wider, die dem durchschnittlichen Benutzer für die Informationen zu diesem Thema angezeigt wird, und dabei zu berücksichtigen, dass für jeden Benutzer aufgrund der Berechtigungen, die er möglicherweise für die Informationen in einem Thema hat, mehr oder weniger Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d742-155">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="7d742-156">Die Qualitätsnote kann einen Einblick in die Themen mit den meisten Informationen bieten und hilfreich sein, um Themen zu finden, die möglicherweise manuell bearbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7d742-156">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="7d742-157">Beispielsweise kann ein Thema mit einer niedrigeren Qualitätsnote das Ergebnis davon sein, dass einige Benutzer nicht über SharePoint Berechtigungen für relevante Dateien oder Websites verfügen, die AI in das Thema aufgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="7d742-157">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="7d742-158">Ein Mitwirkender kann dann das Thema bearbeiten, um die Informationen (falls zutreffend) aufzunehmen, die dann für alle Benutzer, die das Thema anzeigen können, sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="7d742-158">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="7d742-159">Eindrücke</span><span class="sxs-lookup"><span data-stu-id="7d742-159">Impressions</span></span>

<span data-ttu-id="7d742-160">In **der Spalte** Impressionen wird angezeigt, wie oft ein Thema endbenutzern angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d742-160">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="7d742-161">Dies umfasst Ansichten über Themenantwortkarten in der Suche und über Themenhighlights.</span><span class="sxs-lookup"><span data-stu-id="7d742-161">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="7d742-162">Es spiegelt nicht das Klicken auf diese Themen wider, sondern das Thema wurde angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d742-162">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="7d742-163">Die **Spalte Impressionen** wird für Themen auf den  Registerkarten **Vorgeschlagen,** **Bestätigt,** Veröffentlicht und Entfernt auf der Seite **Themen verwalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d742-163">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="7d742-164">Bestätigte Themen</span><span class="sxs-lookup"><span data-stu-id="7d742-164">Confirmed topics</span></span>

<span data-ttu-id="7d742-165">Auf  der Seite Themen verwalten werden Themen, die in Ihren angegebenen SharePoint-Quellstandorten entdeckt wurden und von einem Knowledge Manager oder "crowdsourced" bestätigt wurden, der von zwei oder mehr Personen (Ausgleich negativer Benutzerstimmen gegen positive Benutzerstimmen) durch den Kartenfeedbackmechanismus bestätigt wurde, auf der Registerkarte **Bestätigt** aufgeführt. Bei Bedarf kann ein Benutzer mit berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="7d742-165">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="7d742-166">So überprüfen Sie ein bestätigtes Thema:</span><span class="sxs-lookup"><span data-stu-id="7d742-166">To review a confirmed topic:</span></span>

1. <span data-ttu-id="7d742-167">Wählen Sie auf der Registerkarte **Bestätigt** das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7d742-167">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="7d742-168">Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7d742-168">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="7d742-169">Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="7d742-169">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="7d742-170">Wechseln Sie dazu auf der Registerkarte  Bestätigt zum ausgewählten Thema, und wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d742-170">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="7d742-171">Veröffentlichte Themen</span><span class="sxs-lookup"><span data-stu-id="7d742-171">Published topics</span></span>

<span data-ttu-id="7d742-172">Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen.</span><span class="sxs-lookup"><span data-stu-id="7d742-172">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="7d742-173">Auch manuell erstellte Themen werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d742-173">Manually created topics are listed here as well.</span></span>

   ![Verwalten von Themen](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a><span data-ttu-id="7d742-175">Dashboard für die Anzahl von Themen</span><span class="sxs-lookup"><span data-stu-id="7d742-175">Topic count dashboard</span></span>

<span data-ttu-id="7d742-176">In diesem Diagramm in der Dashboardansicht können Sie die Anzahl der Themen in Ihrem Themencenter für Themen von "Viva Topics" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d742-176">This chart in the dashboard view lets you see the number of topics in your Viva Topics topic center.</span></span> <span data-ttu-id="7d742-177">Das Diagramm zeigt die Themenanzahlen pro Themenlebenszyklusphase und zeigt auch, wie die Themenanzahl im Laufe der Zeit trendiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d742-177">The chart shows the topic counts per topic lifecycle stage and also shows how topic counts have trended over time.</span></span> <span data-ttu-id="7d742-178">Wissensmanager können die Rate, mit der neue Themen von AI entdeckt werden, und die Rate, mit der Themen vom Knowledge Manager oder von Benutzeraktionen bestätigt oder veröffentlicht werden, visuell überwachen.</span><span class="sxs-lookup"><span data-stu-id="7d742-178">Knowledge managers can visually monitor the rate at which new topics are being discovered by AI and the rate at which topics are getting confirmed or published by the knowledge manager or user actions.</span></span>

<span data-ttu-id="7d742-179">Wissensmanagern wird möglicherweise eine andere Anzahl von Themen  in der Liste der Themen auf der Seite Themen verwalten als im Dashboard angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d742-179">Knowledge managers might see a different count of topics represented in the list of topics on the **Manage topics** page than they see in the dashboard.</span></span> <span data-ttu-id="7d742-180">Dies liegt daran, dass ein Knowledge Manager möglicherweise nicht auf alle Themen zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="7d742-180">This is because a knowledge manager might not have access to all topics.</span></span> <span data-ttu-id="7d742-181">Die in der Dashboardansicht angezeigte Anzahl wird vor dem Anwenden der Berechtigungstrimmerung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d742-181">The count presented in the dashboard view is taken before applying permission-trimming.</span></span> 

   ![Screenshot des Dashboards für die Anzahl von Themen](../media/knowledge-management/topic-count-dashboard.png)
