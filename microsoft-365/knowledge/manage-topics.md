---
title: 'Verwalten von Themen im Themen Center in Thema Experiences (Preview) '
description: 'Gewusst wie: Verwalten von Themen im Thema Center.'
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 92cf9c860ddbf199c70a7c2d89a7daba3dfe0fe7
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731327"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="6cae1-103">Verwalten von Themen im Themen Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6cae1-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="6cae1-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="6cae1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="6cae1-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="6cae1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="6cae1-106">Im Themen Center kann ein Wissensmanager die Seite " **Themen verwalten** " anzeigen, um Themen zu überprüfen, die in SharePoint-Quellspeicherorten identifiziert wurden, wie von Ihrem Wissens Administrator angegeben.</span><span class="sxs-lookup"><span data-stu-id="6cae1-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Themen Center](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="6cae1-108">Wissensmanager helfen bei der Durchführung von entdeckten Themen im Thema Lifecycle, in dem Themen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="6cae1-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="6cae1-109">Vorgeschlagen: ein Thema wurde von AI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften, um den Schwellenwert für das Thema zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="6cae1-110">Bestätigt: ein Thema, das von AI vorgeschlagen wurde, wird validiert.</span><span class="sxs-lookup"><span data-stu-id="6cae1-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="6cae1-111">Die Überprüfung erfolgt durch Bestätigung eines Wissens Administrators. Darüber hinaus kann ein Thema bestätigt werden, wenn mindestens zwei Benutzer über das Thema Feedback positives Feedback erhalten, dass das Thema gültig ist.</span><span class="sxs-lookup"><span data-stu-id="6cae1-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="6cae1-112">Entfernt: ein Thema wird von einem Wissens Administrator abgelehnt und wird für die Betrachter nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cae1-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="6cae1-113">Das Thema kann in einem beliebigen Zustand sein, wenn es entfernt wird (vorgeschlagen oder bestätigt).</span><span class="sxs-lookup"><span data-stu-id="6cae1-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="6cae1-114">Veröffentlicht: ein bestätigtes Thema, das manuell aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6cae1-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Topic-Lebenszyklusdiagramm](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="6cae1-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6cae1-116">Requirements</span></span>

<span data-ttu-id="6cae1-117">Um Themen im Themen Center zu verwalten, müssen Sie folgende Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="6cae1-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="6cae1-118">Lassen Sie sich eine Lizenz für ein Thema erleben.</span><span class="sxs-lookup"><span data-stu-id="6cae1-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="6cae1-119">Verfügen über Berechtigungen für [**die Benutzer, die Themen verwalten können**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="6cae1-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="6cae1-120">Wissens-Admins können Benutzern diese Berechtigung im Thema Berechtigungseinstellungen für das Knowledge Network erteilen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="6cae1-121">Sie können die Seite "Themen verwalten" im Thema Center nur dann anzeigen, wenn Sie über die Berechtigung " **Who Can Manage topics** " verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="6cae1-122">Im Themen Center kann ein Wissensmanager Themen überprüfen, die in den von Ihnen angegebenen SharePoint-Quell Standorten identifiziert wurden, und Sie können diese entweder bestätigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="6cae1-123">Ein Knowledge Manager kann auch neue Themenseiten erstellen und veröffentlichen, wenn diese nicht in der Themen Erkennung gefunden wurden, oder vorhandene bearbeiten, wenn Sie aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="6cae1-124">Überprüfen der vorgeschlagenen Themen</span><span class="sxs-lookup"><span data-stu-id="6cae1-124">Review suggested topics</span></span>

<span data-ttu-id="6cae1-125">Auf der Seite Themen Center Manage topics werden Themen, die in den angegebenen SharePoint-Quell Standorten ermittelt wurden, auf der Registerkarte **vorgeschlagen** aufgeführt. Ein Knowledge Manager kann unbestätigte Themen überprüfen und beschließen, diese zu bestätigen oder abzulehnen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="6cae1-126">So überprüfen Sie ein vorgeschlagenes Thema:</span><span class="sxs-lookup"><span data-stu-id="6cae1-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="6cae1-127">Wählen Sie auf der Seite **Themen verwalten** die Registerkarte **vorgeschlagen** aus, und wählen Sie das Thema aus, um die Themen Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="6cae1-128">Lesen Sie auf der Seite Thema die Seite Thema, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="6cae1-129">Nachdem Sie das Thema überprüft haben, kehren Sie zur Seite Themen verwalten zurück.</span><span class="sxs-lookup"><span data-stu-id="6cae1-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="6cae1-130">Für das ausgewählte Thema können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="6cae1-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="6cae1-131">Aktivieren Sie das Kontrollkästchen, um das Thema zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="6cae1-132">Wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cae1-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="6cae1-133">Bestätigte Themen werden aus der Liste **vorgeschlagen** entfernt und werden nun in der Liste **bestätigt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cae1-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="6cae1-134">Abgelehnte Themen werden aus der Liste **vorgeschlagen** entfernt und werden nun auf der Registerkarte **entfernt** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cae1-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="6cae1-135">Bestätigte Themen</span><span class="sxs-lookup"><span data-stu-id="6cae1-135">Confirmed topics</span></span>

<span data-ttu-id="6cae1-136">Auf der Seite "Themen verwalten" werden Themen, die in den angegebenen SharePoint-Quellspeicherorten ermittelt wurden und von einem Knowledge Manager oder einer von zwei oder mehr Personen über den Kartenfeedback Mechanismus bestätigten "Crowd-sourced" bestätigt wurden, auf der Registerkarte " **bestätigt** " aufgeführt. Bei Bedarf kann ein Benutzer mit Berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und auswählen, Sie abzulehnen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="6cae1-137">So überprüfen Sie ein bestätigtes Thema:</span><span class="sxs-lookup"><span data-stu-id="6cae1-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="6cae1-138">Wählen Sie auf der Registerkarte **bestätigt** das Thema aus, um die Themen Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="6cae1-139">Lesen Sie auf der Seite Thema die Seite Thema, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="6cae1-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="6cae1-140">Beachten Sie, dass Sie trotzdem ein bestätigtes Thema ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="6cae1-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="6cae1-141">Wechseln Sie dazu zu dem ausgewählten Thema in der Liste bestätigt, und wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cae1-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="6cae1-142">Veröffentlichte Themen</span><span class="sxs-lookup"><span data-stu-id="6cae1-142">Published topics</span></span>
<span data-ttu-id="6cae1-143">Veröffentlichte Themen wurden bearbeitet, sodass jeder Person, die auf die Seite stößt, immer bestimmte Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6cae1-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="6cae1-144">Manuell erstellte Themen werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6cae1-144">Manually created topics are listed here.</span></span>




