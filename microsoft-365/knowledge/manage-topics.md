---
title: Verwalten von Themen im Themencenter in Microsoft Topics
description: Verwalten von Themen im Themencenter.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107186"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="da9ee-103">Verwalten von Themen im Themencenter</span><span class="sxs-lookup"><span data-stu-id="da9ee-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="da9ee-104">Im Themencenter "Aktuelle Themen" kann  ein Knowledge Manager die Seite "Themen verwalten" anzeigen, um Themen zu überprüfen, die in den Von Ihrem Wissensadministrator angegebenen Speicherorten für die SharePoint-Quelle identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="da9ee-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Themencenter](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="da9ee-106">Knowledge Manager unterstützen Sie dabei, ermittelte Themen durch den Themenlebenszyklus zu führen, in dem folgende Themen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="da9ee-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="da9ee-107">Vorgeschlagen: Ein Thema wurde von AI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="da9ee-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="da9ee-108">Bestätigt: Ein Thema, das von AI vorgeschlagen wurde, wird überprüft.</span><span class="sxs-lookup"><span data-stu-id="da9ee-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="da9ee-109">Die Überprüfung erfolgt durch Bestätigung durch einen Knowledge Manager.</span><span class="sxs-lookup"><span data-stu-id="da9ee-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="da9ee-110">Darüber hinaus kann ein Thema bestätigt werden, wenn mindestens zwei Benutzer über die Feedbackfrage auf der Themenkarte positives Feedback geben.</span><span class="sxs-lookup"><span data-stu-id="da9ee-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="da9ee-111">Veröffentlicht: Ein bestätigtes Thema, das behandelt wurde: Es wurden manuelle Änderungen vorgenommen, um die Qualität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="da9ee-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="da9ee-112">Entfernt: Ein Thema wird von einem Knowledge Manager abgelehnt und ist für Die Besucher nicht mehr sichtbar.</span><span class="sxs-lookup"><span data-stu-id="da9ee-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="da9ee-113">Das Thema kann in einem beliebigen Status sein, wenn es entfernt wird (vorgeschlagen, bestätigt oder veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="da9ee-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="da9ee-114">Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den behandelten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="da9ee-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Diagramm "Themenlebenszyklus"](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="da9ee-116">Auf der Seite "Themen verwalten" kann jeder Knowledge Manager nur Themen anzeigen, in denen er Zugriff auf die Dateien und Seiten des Themas hat.</span><span class="sxs-lookup"><span data-stu-id="da9ee-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="da9ee-117">Dies wird in den Themen wider, die unter den Registerkarten "Vorgeschlagen", "Bestätigt", "Entfernt" und "Veröffentlicht" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="da9ee-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="da9ee-118">Die Themenanzahl zeigt jedoch die Gesamtanzahl in der Organisation an.</span><span class="sxs-lookup"><span data-stu-id="da9ee-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="da9ee-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da9ee-119">Requirements</span></span>

<span data-ttu-id="da9ee-120">Um Themen im Themencenter zu verwalten, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="da9ee-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="da9ee-121">Sie verfügen über eine Lizenz für "Topics".</span><span class="sxs-lookup"><span data-stu-id="da9ee-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="da9ee-122">Die Berechtigung [**"Wer kann Themen verwalten"**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) haben.</span><span class="sxs-lookup"><span data-stu-id="da9ee-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="da9ee-123">Wissensadministratoren können Benutzern diese Berechtigung in den Themen "Themen" erteilen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="da9ee-124">Die Seite "Themen verwalten" kann nur dann im Themencenter angezeigt werden, wenn Sie über die Berechtigung "Wer kann Themen **verwalten"** verfügt.</span><span class="sxs-lookup"><span data-stu-id="da9ee-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="da9ee-125">Im Themencenter kann ein Knowledge Manager Themen überprüfen, die an den von Ihnen angegebenen SharePoint-Quellstandorten identifiziert wurden, und diese entweder bestätigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="da9ee-126">Ein Wissensmanager kann auch neue Themenseiten erstellen und veröffentlichen, wenn diese bei der Themenermittlung nicht gefunden wurden, oder vorhandene bearbeiten, wenn sie aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="da9ee-127">Überprüfen der vorgeschlagenen Themen</span><span class="sxs-lookup"><span data-stu-id="da9ee-127">Review suggested topics</span></span>

<span data-ttu-id="da9ee-128">Auf der Seite "Themen im Themencenter verwalten" werden Themen, die in den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden, auf der Registerkarte **"Vorgeschlagen"** aufgeführt. Bei Bedarf kann ein Knowledge Manager nicht bestätigte Themen überprüfen und diese bestätigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Vorgeschlagene Themen](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="da9ee-130">So überprüfen Sie ein vorgeschlagenes Thema:</span><span class="sxs-lookup"><span data-stu-id="da9ee-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="da9ee-131">Wählen Sie auf der Seite "Themen **verwalten"** die Registerkarte **"Vorgeschlagen"** aus, und wählen Sie das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="da9ee-132">Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="da9ee-133">Wenn Sie alle Bearbeitungen veröffentlichen, wird dieses Thema auf die Registerkarte **"Veröffentlicht"** verschieben.</span><span class="sxs-lookup"><span data-stu-id="da9ee-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="da9ee-134">Wechseln Sie nach der Überprüfung des Themas zurück zur Seite "Themen verwalten".</span><span class="sxs-lookup"><span data-stu-id="da9ee-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="da9ee-135">Für das ausgewählte Thema können Sie:</span><span class="sxs-lookup"><span data-stu-id="da9ee-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="da9ee-136">Aktivieren Sie das Kontrollkästchen, um das Thema zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="da9ee-137">Wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="da9ee-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="da9ee-138">Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und nun in der Liste **"Bestätigt"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da9ee-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="da9ee-139">Abgelehnte Themen werden aus der Liste **"Vorgeschlagen"** entfernt und nun auf der Registerkarte **"Entfernt"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da9ee-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="da9ee-140">Qualitätsergebnis</span><span class="sxs-lookup"><span data-stu-id="da9ee-140">Quality score</span></span>

<span data-ttu-id="da9ee-141">Jedem Thema, das auf der Seite "Vorgeschlagene Themen" angezeigt wird, ist eine <b>Qualitätsergebnis</b> zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="da9ee-142">Die Qualitätsergebnis ist eine Spiegelung der Informationsmenge, die dem durchschnittlichen Benutzer für die Informationen zu diesem Thema angezeigt wird, und dabei berücksichtigen, dass jedem Benutzer aufgrund der Berechtigungen, die er für die Informationen in einem Thema hat, möglicherweise mehr oder weniger Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="da9ee-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="da9ee-143">Die Qualitätsergebnis kann helfen, Einblicke in die Themen mit den meisten Informationen zu erhalten, und kann hilfreich sein, um Themen zu finden, die möglicherweise manuell bearbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="da9ee-144">Beispielsweise kann ein Thema mit einer niedrigeren Qualitätssentwertung das Ergebnis sein, dass einige Benutzer keine SharePoint-Berechtigungen für relevante Dateien oder Websites haben, die ai in das Thema eingeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="da9ee-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="da9ee-145">Ein Mitwirkender könnte dann das Thema bearbeiten, um die Informationen (falls angemessen) zu enthalten, die dann für alle Benutzer angezeigt werden können, die das Thema anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="da9ee-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="da9ee-146">Die Qualität kann zwischen 1 und 100 liegen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="da9ee-147">Ein neu gefundenes Thema hat eine Qualitätsnote von 0, bis zwei oder mehr Benutzer es angezeigt haben.</span><span class="sxs-lookup"><span data-stu-id="da9ee-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="da9ee-148">Die Qualität der einzelnen Benutzer wird durch eine Reihe von Faktoren bestimmt, z. B. durch die Menge der Inhalte, die für den bestimmten Benutzer angezeigt werden. Dies wird durch die Berechtigungen des Benutzers gesteuert, da auf jeder Themenseite Sicherheitstrimmer für von AI generierte Inhalte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="da9ee-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="da9ee-149">Die auf der Registerkarte "Vorgeschlagene Themen" angezeigte Qualitätsergebnis ist ein Durchschnittswert der einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="da9ee-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="da9ee-150">Impressionen</span><span class="sxs-lookup"><span data-stu-id="da9ee-150">Impressions</span></span>

<span data-ttu-id="da9ee-151">In <b>der</b> Spalte "Anzeigen" wird angezeigt, wie oft ein Thema endbenutzern angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="da9ee-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="da9ee-152">Dazu gehören Ansichten über Themenkarten in der Suche, über Themenhighlights und über Themencenteransichten.</span><span class="sxs-lookup"><span data-stu-id="da9ee-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="da9ee-153">Das Click-Through-Thema in diesen Themen wird nicht dargestellt, aber das Thema wurde angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da9ee-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="da9ee-154">Die Spalte "Impressionen" wird für Themen auf den Registerkarten "Vorgeschlagen", "Bestätigt", "Veröffentlicht" und "Entfernt" auf der Seite "Themen verwalten" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da9ee-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="da9ee-155">Bestätigte Themen</span><span class="sxs-lookup"><span data-stu-id="da9ee-155">Confirmed topics</span></span>

<span data-ttu-id="da9ee-156">Auf der Seite "Themen verwalten" werden Themen, die an den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden und von einem  Knowledge Manager bestätigt wurden oder von zwei oder mehr Personen über den Kartenfeedbackmechanismus bestätigt wurden, auf der Registerkarte "Bestätigt" aufgeführt. Bei Bedarf kann ein Benutzer mit Berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="da9ee-157">So überprüfen Sie ein bestätigtes Thema:</span><span class="sxs-lookup"><span data-stu-id="da9ee-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="da9ee-158">Wählen Sie **auf der** Registerkarte "Bestätigt" das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="da9ee-159">Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="da9ee-160">Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="da9ee-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="da9ee-161">Wechseln Sie dazu zum ausgewählten Thema in der Liste "Bestätigt", und wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="da9ee-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="da9ee-162">Veröffentlichte Themen</span><span class="sxs-lookup"><span data-stu-id="da9ee-162">Published topics</span></span>
<span data-ttu-id="da9ee-163">Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen.</span><span class="sxs-lookup"><span data-stu-id="da9ee-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="da9ee-164">Hier werden auch manuell erstellte Themen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="da9ee-164">Manually created topics are listed here as well.</span></span>

   ![Verwalten von Themen](../media/knowledge-management/manage-topics-new.png) </br> 




