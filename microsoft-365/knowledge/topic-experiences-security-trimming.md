---
title: Thema Experiences Security Trimming (Preview)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Übersicht über die Verwendung von Sicherheit zum Anzeigen von Themen.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698950"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="c93c7-103">Thema Experiences Security Trimming (Preview)</span><span class="sxs-lookup"><span data-stu-id="c93c7-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c93c7-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="c93c7-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c93c7-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c93c7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c93c7-106">Thema Erlebnisse Benutzer können keine Informationen in Themen anzeigen, die durch die vorhandenen Office 365 Berechtigungen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="c93c7-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="c93c7-107">Alle Elemente, die ein Benutzer auf einer Themen Seite sieht (beispielsweise SharePoint-Websites, Dokumente, Dateien), werden Informationen, die er bereits sehen darf.</span><span class="sxs-lookup"><span data-stu-id="c93c7-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="c93c7-108">In den Themen Erfahrungen werden keine Änderungen an vorhandenen Berechtigungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="c93c7-109">Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben</span><span class="sxs-lookup"><span data-stu-id="c93c7-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="c93c7-110">Wenn ein Thema über AI oder manuelle Kuration erstellt wird, kann es eine Beschreibung des Themas, Alternative Namen, Personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="c93c7-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="c93c7-111">Wenn diese Informationen auf einer Themen Seite angezeigt werden, ist es möglich, dass zwei Benutzer, die dasselbe Thema anzeigen, nicht dieselben Informationen sehen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="c93c7-112">Wenn beispielsweise der Benutzer 1 die Neptun-Themen Seite anzeigt, können diese möglicherweise angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c93c7-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Neptun-Thema für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="c93c7-114">Wenn Benutzer 2 jedoch dieselbe Neptun-Themen Seite betrachtet, unterscheidet sich Ihre Ansicht von Benutzer 1.</span><span class="sxs-lookup"><span data-stu-id="c93c7-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="c93c7-115">Benutzer 2 kann die Produkt Übersichtsdatei der *GD-2000* im Abschnitt **fixierte Dateien und Seiten** der Seite Thema anzeigen, die nicht für Benutzer 1 angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c93c7-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Neptun-Thema für Benutzer 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="c93c7-117">Der Unterschied, was Benutzer im selben Thema sehen können, liegt daran, dass Benutzer möglicherweise nicht über die Office 365 Berechtigungen zum Anzeigen einer verwandten Website oder Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="c93c7-118">Thema Experiences respektiert die Berechtigungen, die für Elemente in einem Thema festgelegt sind, und kann den Zugriff darauf nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c93c7-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="c93c7-119">In unserem Beispiel kann Benutzer 1 die Produkt Übersichtsdatei der *GD-2000* nicht in ihrer Themen Seite für Neptun anzeigen, da Benutzer 1 nicht über Office 365 Berechtigungen zum Anzeigen der Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="c93c7-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="c93c7-120">Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema anzuzeigen, damit es nützlich ist, ist das Thema für den Benutzer nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c93c7-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="c93c7-121">In dieser Instanz wird dem Benutzer das markierte Thema nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c93c7-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="c93c7-122">Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er hilfreich ist, kann das Thema jedoch sehen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="c93c7-123">Thema Berechtigungen für Knowledge Manager und Thema Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="c93c7-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="c93c7-124">Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, für die Sie Berechtigungen zum Anzeigen von Themen haben.</span><span class="sxs-lookup"><span data-stu-id="c93c7-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="c93c7-125">Auf ähnliche Weise können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Thema Mitwirkende – nur Informationen anzeigen, für die Sie Berechtigungen zum Anzeigen von Themen haben.</span><span class="sxs-lookup"><span data-stu-id="c93c7-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="c93c7-126">AI versus manuell kuratierte Themen Informationen</span><span class="sxs-lookup"><span data-stu-id="c93c7-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="c93c7-127">Themen können Informationen enthalten, die von AI generiert werden, sowie Informationen, die von Mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="c93c7-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="c93c7-128">Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.</span><span class="sxs-lookup"><span data-stu-id="c93c7-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="c93c7-129">Informationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für alle sichtbar, die das Thema sehen können.</span><span class="sxs-lookup"><span data-stu-id="c93c7-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="c93c7-130">In der folgenden Tabelle wird beschrieben, was Benutzer – Thema Betrachter, Mitwirkende und Wissensmanager – in einem bestimmten Thema basierend auf Ihren Berechtigungen sehen können.</span><span class="sxs-lookup"><span data-stu-id="c93c7-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="c93c7-131">Thema-Element</span><span class="sxs-lookup"><span data-stu-id="c93c7-131">Topic item</span></span>|<span data-ttu-id="c93c7-132">Was Benutzer sehen können</span><span class="sxs-lookup"><span data-stu-id="c93c7-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="c93c7-133">Name des Themas</span><span class="sxs-lookup"><span data-stu-id="c93c7-133">Topic name</span></span>|<span data-ttu-id="c93c7-134">Benutzer können den Thema Namen aller Themen im Thema Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="c93c7-135">Einige Themen sind möglicherweise nicht sichtbar, wenn Sie eine geringe Relevanz für den Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="c93c7-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="c93c7-136">Beschreibung des Themas</span><span class="sxs-lookup"><span data-stu-id="c93c7-136">Topic description</span></span>|<span data-ttu-id="c93c7-137">Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="c93c7-138">Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c93c7-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="c93c7-139">Personen</span><span class="sxs-lookup"><span data-stu-id="c93c7-139">People</span></span>|<span data-ttu-id="c93c7-140">Angeheftete Personen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c93c7-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="c93c7-141">Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c93c7-142">Dateien</span><span class="sxs-lookup"><span data-stu-id="c93c7-142">Files</span></span>|<span data-ttu-id="c93c7-143">Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c93c7-144">Seiten</span><span class="sxs-lookup"><span data-stu-id="c93c7-144">Pages</span></span>|<span data-ttu-id="c93c7-145">Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c93c7-146">Websites</span><span class="sxs-lookup"><span data-stu-id="c93c7-146">Sites</span></span>|<span data-ttu-id="c93c7-147">Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c93c7-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="c93c7-148">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c93c7-148">See also</span></span>

