---
title: Microsoft Viva Topics Security Trimming
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Übersicht über die Verwendung von Sicherheit zum Anzeigen von Themen.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939623"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="8ef14-103">Microsoft Viva Topics Security Trimming</span><span class="sxs-lookup"><span data-stu-id="8ef14-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="8ef14-104">Benutzer von "Viva Topics" können keine Informationen in Themen anzeigen, die ihre vorhandenen Office 365 verhindern, dass sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8ef14-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="8ef14-105">Alles, was einem Benutzer auf einer Themenseite angezeigt wird (z. B. SharePoint Websites, Dokumente, Dateien), sind Informationen, die er bereits sehen darf.</span><span class="sxs-lookup"><span data-stu-id="8ef14-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="8ef14-106">Bei "Viva Topics" werden keine Änderungen an vorhandenen Berechtigungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="8ef14-107">Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben</span><span class="sxs-lookup"><span data-stu-id="8ef14-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="8ef14-108">Wenn ein Thema über KI oder manuelle Kuration erstellt wird, kann es eine Beschreibung des Themas, alternative Namen, Personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ef14-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="8ef14-109">Wenn diese Informationen auf einer Themenseite angezeigt werden, kann es sein, dass zwei Benutzer, die dasselbe Thema anzeigen, die gleichen Informationen nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="8ef14-110">Wenn Benutzer 1 z. B. die Themenseite "Neptune" aufruft, wird möglicherweise diese Ansicht der Themenseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ef14-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Thema "Neptun" für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="8ef14-112">Wenn Benutzer 2 jedoch dieselbe Seite des Themas "Neptune" betrachtet, unterscheidet sich ihre Ansicht von Benutzer 1.</span><span class="sxs-lookup"><span data-stu-id="8ef14-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="8ef14-113">Benutzer 2 kann die *Dg-2000-Produktübersichtsdatei* im Abschnitt Angeheftet Dateien und Seiten der Themenseite anzeigen, die für Benutzer 1 nicht angezeigt wird. </span><span class="sxs-lookup"><span data-stu-id="8ef14-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Thema "2" für "2"](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="8ef14-115">Der Unterschied bei den Benutzern, die im gleichen Thema angezeigt werden, liegt daran, dass Benutzer möglicherweise nicht über die Office 365 zum Anzeigen einer verwandten Website oder Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="8ef14-116">Viva Topics respektiert die Berechtigungen, die für Elemente in einem Thema festgelegt sind, und kann den Zugriff darauf nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8ef14-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="8ef14-117">In unserem Beispiel kann Benutzer 1 die *DG-2000-Produktübersichtsdatei* nicht auf ihrer Themenseite für "Neptune" anzeigen, da Benutzer 1 nicht über Office 365 zum Anzeigen der Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="8ef14-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="8ef14-118">Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema zu sehen, damit es nützlich ist, steht das Thema dem Benutzer nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8ef14-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="8ef14-119">In diesem Fall wird dem Benutzer das hervorgehobene Thema nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ef14-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="8ef14-120">Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er nützlich ist, kann das Thema sehen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="8ef14-121">Themenberechtigungen für Wissensmanager und Mitwirkende von Themen</span><span class="sxs-lookup"><span data-stu-id="8ef14-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="8ef14-122">Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, die sie in Themen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="8ef14-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="8ef14-123">Ebenso können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Mitwirkende – nur Informationen anzeigen, die sie in Themen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="8ef14-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="8ef14-124">Informationen zu AI und manuell kuratierten Themen</span><span class="sxs-lookup"><span data-stu-id="8ef14-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="8ef14-125">Themen können informationen enthalten, die durch KI generiert werden, und Informationen, die von Themenwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8ef14-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="8ef14-126">Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf die Quellinhalte haben.</span><span class="sxs-lookup"><span data-stu-id="8ef14-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="8ef14-127">Themenbeschreibung und Personeninformationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für alle Personen sichtbar, die das Thema sehen können.</span><span class="sxs-lookup"><span data-stu-id="8ef14-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="8ef14-128">Dateien, Seiten und Websites sind nur für Benutzer sichtbar, die über Berechtigungen für die Quellinhalte verfügen, unabhängig davon, ob sie manuell von AI hinzugefügt oder hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="8ef14-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="8ef14-129">In der folgenden Tabelle wird beschrieben, was Benutzer – Themenbetrachter, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.</span><span class="sxs-lookup"><span data-stu-id="8ef14-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="8ef14-130">Themenelement</span><span class="sxs-lookup"><span data-stu-id="8ef14-130">Topic item</span></span>|<span data-ttu-id="8ef14-131">Anzeige für Benutzer</span><span class="sxs-lookup"><span data-stu-id="8ef14-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="8ef14-132">Themenname</span><span class="sxs-lookup"><span data-stu-id="8ef14-132">Topic name</span></span>|<span data-ttu-id="8ef14-133">Benutzer können den Themanamen von Themen im Themencenter sehen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="8ef14-134">Einige Themen sind möglicherweise nicht sichtbar, wenn Benutzer nicht über Berechtigungen für den Quellinhalt verfügen oder eine geringe Relevanz für den Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="8ef14-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="8ef14-135">Beschreibung des Themas</span><span class="sxs-lookup"><span data-stu-id="8ef14-135">Topic description</span></span>|<span data-ttu-id="8ef14-136">Von der KI generierten Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="8ef14-137">Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8ef14-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="8ef14-138">Personen</span><span class="sxs-lookup"><span data-stu-id="8ef14-138">People</span></span>|<span data-ttu-id="8ef14-139">Angeheftete Personen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8ef14-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="8ef14-140">Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8ef14-141">Dateien</span><span class="sxs-lookup"><span data-stu-id="8ef14-141">Files</span></span>|<span data-ttu-id="8ef14-142">Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8ef14-143">Seiten</span><span class="sxs-lookup"><span data-stu-id="8ef14-143">Pages</span></span>|<span data-ttu-id="8ef14-144">Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8ef14-145">Websites</span><span class="sxs-lookup"><span data-stu-id="8ef14-145">Sites</span></span>|<span data-ttu-id="8ef14-146">Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="8ef14-147">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8ef14-147">See also</span></span>

