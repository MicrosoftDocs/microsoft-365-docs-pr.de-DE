---
title: 'Verwalten von Themen im Themencenter in Themenerfahrungen (Vorschau) '
description: Verwalten von Themen im Themencenter.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 371ccc16e787b331f42026dec48e5e3113b2b172
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976191"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="95b1b-103">Verwalten von Themen im Themencenter (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="95b1b-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="95b1b-104">Der Inhalt dieses Artikels ist für Project Cortex Private Preview vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="95b1b-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="95b1b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="95b1b-106">Im Themencenter kann ein Knowledge  Manager die Seite "Themen verwalten" anzeigen, um Themen zu überprüfen, die in den Von Ihrem Wissensadministrator angegebenen Speicherorten für die SharePoint-Quelle identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="95b1b-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Themencenter](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="95b1b-108">Knowledge Manager unterstützen Sie dabei, ermittelte Themen durch den Themenlebenszyklus zu führen, in dem folgende Themen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="95b1b-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="95b1b-109">Vorgeschlagen: Ein Thema wurde von AI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften, um den Schwellenwert für das Thema zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="95b1b-110">Bestätigt: Ein Thema, das von AI vorgeschlagen wurde, wird überprüft.</span><span class="sxs-lookup"><span data-stu-id="95b1b-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="95b1b-111">Die Überprüfung erfolgt durch Bestätigung durch einen Wissensadministrator. Darüber hinaus kann ein Thema bestätigt werden, wenn mindestens zwei Benutzer positives Feedback durch Feedback zu Themen geben, dass das Thema gültig ist.</span><span class="sxs-lookup"><span data-stu-id="95b1b-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="95b1b-112">Entfernt: Ein Thema wird von einem Wissensadministrator abgelehnt und ist für Die Besucher nicht mehr sichtbar.</span><span class="sxs-lookup"><span data-stu-id="95b1b-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="95b1b-113">Das Thema kann einen beliebigen Status haben, wenn es entfernt (vorgeschlagen oder bestätigt) wird.</span><span class="sxs-lookup"><span data-stu-id="95b1b-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="95b1b-114">Veröffentlicht: Ein bestätigtes Thema, das manuell aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="95b1b-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Diagramm "Themenlebenszyklus"](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="95b1b-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95b1b-116">Requirements</span></span>

<span data-ttu-id="95b1b-117">Um Themen im Themencenter zu verwalten, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="95b1b-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="95b1b-118">Sie verfügen über eine Topic Experiences-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="95b1b-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="95b1b-119">Berechtigungen für die Personen, [**die Themen verwalten können.**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)</span><span class="sxs-lookup"><span data-stu-id="95b1b-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="95b1b-120">Wissensadministratoren können Benutzern diese Berechtigung in den Themeneinstellungen des Knowledge Network erteilen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="95b1b-121">Die Seite "Themen verwalten" kann nur dann im Themencenter angezeigt werden, wenn Sie über die Berechtigung "Wer kann Themen **verwalten"** verfügt.</span><span class="sxs-lookup"><span data-stu-id="95b1b-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="95b1b-122">Im Themencenter kann ein Knowledge Manager Themen überprüfen, die an den von Ihnen angegebenen SharePoint-Quellstandorten identifiziert wurden, und diese entweder bestätigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="95b1b-123">Ein Wissensmanager kann auch neue Themenseiten erstellen und veröffentlichen, wenn diese bei der Themenermittlung nicht gefunden wurden, oder vorhandene bearbeiten, wenn sie aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="95b1b-124">Überprüfen der vorgeschlagenen Themen</span><span class="sxs-lookup"><span data-stu-id="95b1b-124">Review suggested topics</span></span>

<span data-ttu-id="95b1b-125">Auf der Seite "Themen im Themencenter verwalten" werden Themen, die in den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden, auf der Registerkarte **"Vorgeschlagen"** aufgeführt. Ein Wissensmanager kann nicht bestätigte Themen überprüfen und diese bestätigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="95b1b-126">So überprüfen Sie ein vorgeschlagenes Thema:</span><span class="sxs-lookup"><span data-stu-id="95b1b-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="95b1b-127">Wählen Sie auf der Seite "Themen **verwalten"** die Registerkarte **"Vorgeschlagen"** aus, und wählen Sie das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="95b1b-128">Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="95b1b-129">Wechseln Sie nach der Überprüfung des Themas zurück zur Seite "Themen verwalten".</span><span class="sxs-lookup"><span data-stu-id="95b1b-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="95b1b-130">Für das ausgewählte Thema können Sie:</span><span class="sxs-lookup"><span data-stu-id="95b1b-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="95b1b-131">Aktivieren Sie das Kontrollkästchen, um das Thema zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="95b1b-132">Wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="95b1b-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="95b1b-133">Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und nun in der Liste **"Bestätigt"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95b1b-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="95b1b-134">Abgelehnte Themen werden aus der Liste **"Vorgeschlagen"** entfernt und nun auf der Registerkarte **"Entfernt"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95b1b-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="95b1b-135">Bestätigte Themen</span><span class="sxs-lookup"><span data-stu-id="95b1b-135">Confirmed topics</span></span>

<span data-ttu-id="95b1b-136">Auf der Seite "Themen verwalten" werden Themen, die an den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden und von einem  Knowledge Manager bestätigt wurden oder von zwei oder mehr Personen über den Kartenfeedbackmechanismus bestätigt wurden, auf der Registerkarte "Bestätigt" aufgeführt. Bei Bedarf kann ein Benutzer mit Berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="95b1b-137">So überprüfen Sie ein bestätigtes Thema:</span><span class="sxs-lookup"><span data-stu-id="95b1b-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="95b1b-138">Wählen Sie **auf der** Registerkarte "Bestätigt" das Thema aus, um die Themenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="95b1b-139">Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="95b1b-140">Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="95b1b-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="95b1b-141">Wechseln Sie dazu zum ausgewählten Thema in der Liste "Bestätigt", und wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="95b1b-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="95b1b-142">Veröffentlichte Themen</span><span class="sxs-lookup"><span data-stu-id="95b1b-142">Published topics</span></span>
<span data-ttu-id="95b1b-143">Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen.</span><span class="sxs-lookup"><span data-stu-id="95b1b-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="95b1b-144">Manuell erstellte Themen werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="95b1b-144">Manually created topics are listed here.</span></span>




