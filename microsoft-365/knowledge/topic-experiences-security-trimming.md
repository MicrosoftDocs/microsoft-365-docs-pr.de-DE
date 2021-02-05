---
title: Sicherheitstrimmerung für Microsoft -Themen
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
description: Übersicht über die Verwendung von Sicherheitseinstellungen zum Anzeigen von Themen.
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107518"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="38ddf-103">Sicherheitstrimmerung für Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="38ddf-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="38ddf-104">Benutzer von "Themen" können keine Informationen in Themen anzeigen, die von ihren vorhandenen Office 365-Berechtigungen nicht angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="38ddf-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="38ddf-105">Alles, was einem Benutzer auf einer Themenseite angezeigt wird (z. B. SharePoint-Websites, Dokumente, Dateien), sind Informationen, die er bereits sehen darf.</span><span class="sxs-lookup"><span data-stu-id="38ddf-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="38ddf-106">In Themen werden keine änderungen an vorhandenen Berechtigungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="38ddf-107">Warum zwei Benutzer möglicherweise unterschiedliche Ansichten desselben Themas haben</span><span class="sxs-lookup"><span data-stu-id="38ddf-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="38ddf-108">Wenn ein Thema mithilfe von KI oder manueller Curation erstellt wird, kann es eine Beschreibung des Themas, alternative Namen, personen, die dem Thema zugeordnet sind, sowie Websites, Seiten und Dateien im Zusammenhang mit dem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="38ddf-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="38ddf-109">Wenn diese Informationen auf einer Themenseite angezeigt werden, werden zwei Benutzern, die dasselbe Thema anzeigen, die gleichen Informationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38ddf-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="38ddf-110">Wenn Benutzer 1 z. B. die Themenseite "Untere" aufruft, wird möglicherweise diese Ansicht der Themenseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38ddf-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Thema "1" für Benutzer 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="38ddf-112">Wenn Benutzer 2 jedoch auf derselben Seite des Themas "Untere" sucht, unterscheidet sich die Ansicht von Benutzer 1.</span><span class="sxs-lookup"><span data-stu-id="38ddf-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="38ddf-113">Benutzer 2 kann die *Dg-2000-Produktübersichtsdatei* im Abschnitt "Angeheftierte Dateien und Seiten" der Themenseite anzeigen, die für Benutzer 1 nicht angezeigt wird. </span><span class="sxs-lookup"><span data-stu-id="38ddf-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Thema "1" für Benutzer 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="38ddf-115">Der Unterschied, was Benutzern im gleichen Thema angezeigt wird, liegt daran, dass Benutzer möglicherweise nicht über die Office 365-Berechtigungen zum Anzeigen einer verwandten Website oder Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="38ddf-116">Unter "Themen" werden die Berechtigungen respektiert, die für Elemente in einem Thema festgelegt sind, und der Zugriff auf sie kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38ddf-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="38ddf-117">In unserem Beispiel kann Benutzer 1 die *Dg-2000-Produktübersichtsdatei* auf der Themenseite für Ihn nicht anzeigen, da Benutzer 1 nicht über Office 365-Berechtigungen zum Anzeigen der Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="38ddf-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="38ddf-118">Wenn ein Benutzer nicht in der Lage ist, genügend Informationen in einem Thema zu sehen, damit es nützlich ist, steht das Thema dem Benutzer nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="38ddf-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="38ddf-119">In diesem Fall wird dem Benutzer das hervorgehobene Thema nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38ddf-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="38ddf-120">Ein anderer Benutzer, der über Berechtigungen für weitere Informationen im Thema verfügt, damit er nützlich ist, kann das Thema sehen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="38ddf-121">Themenberechtigungen für Wissensmanager und Mitwirkende von Themen</span><span class="sxs-lookup"><span data-stu-id="38ddf-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="38ddf-122">Benutzer, denen Berechtigungen zum Verwalten von Themen zugewiesen sind – Wissensmanager – können nur Informationen anzeigen, für die sie in Themen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="38ddf-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="38ddf-123">Ebenso können Benutzer, die über Berechtigungen zum Erstellen und Bearbeiten von Themen verfügen – Thementeilnehmer – nur Informationen anzeigen, für die sie über Berechtigungen zum Anzeigen in Themen verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="38ddf-124">Ai im Vergleich zu manuell behandelten Themeninformationen</span><span class="sxs-lookup"><span data-stu-id="38ddf-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="38ddf-125">Themen können informationen enthalten, die von AI generiert werden, sowie Informationen, die von Themen mitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="38ddf-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="38ddf-126">Informationen in einem Thema, das von AI hinzugefügt wurde, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.</span><span class="sxs-lookup"><span data-stu-id="38ddf-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="38ddf-127">Informationen, die von einem Mitwirkenden oder Wissensmanager manuell hinzugefügt oder bearbeitet wurden, sind für jeden sichtbar, der das Thema sehen kann.</span><span class="sxs-lookup"><span data-stu-id="38ddf-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="38ddf-128">In der folgenden Tabelle wird beschrieben, was Benutzer – Themenanzeiger, Mitwirkende und Wissensmanager – basierend auf ihren Berechtigungen in einem bestimmten Thema sehen können.</span><span class="sxs-lookup"><span data-stu-id="38ddf-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="38ddf-129">Themaelement</span><span class="sxs-lookup"><span data-stu-id="38ddf-129">Topic item</span></span>|<span data-ttu-id="38ddf-130">Was Benutzer sehen können</span><span class="sxs-lookup"><span data-stu-id="38ddf-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="38ddf-131">Themaname</span><span class="sxs-lookup"><span data-stu-id="38ddf-131">Topic name</span></span>|<span data-ttu-id="38ddf-132">Benutzer können den Themennamen aller Themen im Themencenter sehen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="38ddf-133">Einige Themen sind möglicherweise nicht sichtbar, wenn sie eine geringe Relevanz für den Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="38ddf-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="38ddf-134">Themenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="38ddf-134">Topic description</span></span>|<span data-ttu-id="38ddf-135">Von AI generierte Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="38ddf-136">Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="38ddf-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="38ddf-137">Personen</span><span class="sxs-lookup"><span data-stu-id="38ddf-137">People</span></span>|<span data-ttu-id="38ddf-138">Angeheftierte Personen sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="38ddf-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="38ddf-139">Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="38ddf-140">Dateien</span><span class="sxs-lookup"><span data-stu-id="38ddf-140">Files</span></span>|<span data-ttu-id="38ddf-141">Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="38ddf-142">Seiten</span><span class="sxs-lookup"><span data-stu-id="38ddf-142">Pages</span></span>|<span data-ttu-id="38ddf-143">Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="38ddf-144">Websites</span><span class="sxs-lookup"><span data-stu-id="38ddf-144">Sites</span></span>|<span data-ttu-id="38ddf-145">Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.</span><span class="sxs-lookup"><span data-stu-id="38ddf-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="38ddf-146">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="38ddf-146">See also</span></span>

