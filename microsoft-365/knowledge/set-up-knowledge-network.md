---
title: 'Einrichten der Wissensverwaltung (Vorschau) '
description: Einrichten der Wissensverwaltung
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612548"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="e6dae-103">Einrichten der Wissensverwaltung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="e6dae-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="e6dae-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="e6dae-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="e6dae-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e6dae-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="e6dae-106">Sie können das Microsoft 365 Admin Center verwenden, um die [Wissensverwaltung](knowledge-management-overview.md)einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e6dae-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="e6dae-107">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren des Wissensmanagements in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="e6dae-108">Beispielsweise müssen Sie Überlegungen zu den folgenden Aspekten treffen:</span><span class="sxs-lookup"><span data-stu-id="e6dae-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="e6dae-109">Die SharePoint-Websites, die Sie für Themen analysieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="e6dae-110">Die Benutzer, für die Sie Themen sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="e6dae-111">Die Benutzer, denen Sie Berechtigungen zum Verwalten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="e6dae-112">Die Benutzer, denen Sie Berechtigungen zum Erstellen oder Bearbeiten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="e6dae-113">Welchen Namen möchten Sie Ihrem Themen Center geben?</span><span class="sxs-lookup"><span data-stu-id="e6dae-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="e6dae-114">Möglicherweise ist es hilfreich, Sicherheitsgruppen zu erstellen, um Ihren Benutzern die Berechtigungen zu erteilen, die zum Anzeigen von Themen, zum Verwalten des Themas und zum Erstellen und Bearbeiten von Themen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e6dae-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="e6dae-115">Ein Administrator kann [Änderungen an den ausgewählten Einstellungen auch jederzeit nach dem Setup](manage-knowledge-network.md) über die Knowledge Management-Einstellungen im Microsoft 365 Admin Center vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6dae-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6dae-116">Requirements</span></span> 
<span data-ttu-id="e6dae-117">Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und organisatorische Wissens Aufgaben einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="e6dae-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="e6dae-118">Einrichten Ihres Wissensnetzwerks</span><span class="sxs-lookup"><span data-stu-id="e6dae-118">Set up your knowledge network</span></span>

<span data-ttu-id="e6dae-119">Das Einrichten Ihres Wissensnetzwerks führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="e6dae-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="e6dae-120">Thema Discovery: Auswählen von Themen Quellen und Themen, die von der Suche ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="e6dae-121">Thema Visibility: auswählen, wer Themen als Highlights anzeigen kann, in Such-und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="e6dae-122">Thema Permissions: Auswählen der Personen, die Themen erstellen, bearbeiten und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="e6dae-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="e6dae-123">Themen Center: Erstellen Ihres Themen Centers.</span><span class="sxs-lookup"><span data-stu-id="e6dae-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="e6dae-124">Überprüfung: überprüfen und Anwenden Ihrer Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="e6dae-125">So richten Sie Ihr Wissensnetzwerk ein:</span><span class="sxs-lookup"><span data-stu-id="e6dae-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="e6dae-126">Wählen Sie im Microsoft 365 Admin Center (admin.Microsoft.com) die Option **Setup**aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.</span><span class="sxs-lookup"><span data-stu-id="e6dae-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="e6dae-127">Klicken Sie im Abschnitt **organisatorisches Wissen** auf **Personen mit Wissen verbinden**.</span><span class="sxs-lookup"><span data-stu-id="e6dae-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Verbinden von Personen mit wissen](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="e6dae-129">Klicken Sie auf der Seite **zum Verbinden von Benutzern mit Informationen** auf **Erste Schritte** , um Sie durch den Setupprozess zu führen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Erste Schritte](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="e6dae-131">Auf der Seite **Wählen Sie aus, wie das Wissensnetzwerk Themen finden kann** , konfigurieren Sie die Themen Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="e6dae-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="e6dae-132">Wählen Sie im Abschnitt **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="e6dae-133">Hierzu zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="e6dae-133">This includes:</span></span></br>
    <span data-ttu-id="e6dae-134">a.</span><span class="sxs-lookup"><span data-stu-id="e6dae-134">a.</span></span> <span data-ttu-id="e6dae-135">**Alle Websites**: alle SharePoint-Websites in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="e6dae-136">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="e6dae-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="e6dae-137">b.</span><span class="sxs-lookup"><span data-stu-id="e6dae-137">b.</span></span> <span data-ttu-id="e6dae-138">**Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="e6dae-139">Sie können auch eine Liste der Websites hochladen, von denen Sie die Ermittlung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="e6dae-140">In Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6dae-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="e6dae-141">c.</span><span class="sxs-lookup"><span data-stu-id="e6dae-141">c.</span></span> <span data-ttu-id="e6dae-142">**Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="e6dae-143">Sie können auch eine Liste der Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-143">You can also upload a list of sites.</span></span> <span data-ttu-id="e6dae-144">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Auswählen der Suche nach Themen](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="e6dae-146">Im Abschnitt **Themen nach Name ausschließen** können Sie auswählen, dass Themen Namen eingeschlossen werden sollen, die nicht in den ermittelten Ergebnissen enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="e6dae-147">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Themen als Teil des Wissensnetzwerks einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="e6dae-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="e6dae-148">Zu den Optionen gehören:</span><span class="sxs-lookup"><span data-stu-id="e6dae-148">Your options include:</span></span></br>
    <span data-ttu-id="e6dae-149">a.</span><span class="sxs-lookup"><span data-stu-id="e6dae-149">a.</span></span> <span data-ttu-id="e6dae-150">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="e6dae-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="e6dae-151">b.</span><span class="sxs-lookup"><span data-stu-id="e6dae-151">b.</span></span> <span data-ttu-id="e6dae-152">**Thema ausschließen, das diese Begriffe enthält**: Wenn Sie Themen haben, die Sie Benutzern nicht als Teil des Wissensnetzwerks angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="e6dae-153">-Laden Sie die bereitgestellte Vorlage herunter.</span><span class="sxs-lookup"><span data-stu-id="e6dae-153">- Download the provided template.</span></span>
   <span data-ttu-id="e6dae-154">– Geben Sie die Namen der Themen ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="e6dae-155">Sie müssen den Übereinstimmungs als exakt oder partiell angeben.</span><span class="sxs-lookup"><span data-stu-id="e6dae-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="e6dae-156">Exakte Übereinstimmung bedeutet, dass Themen, die dem genauen Ausdruck entsprechen, ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e6dae-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="e6dae-157">Partielle Übereinstimmung ist strenger und bedeutet, dass Themen, die den Begriff enthalten, ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e6dae-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="e6dae-158">Wenn Sie beispielsweise *doc* als Namen des Themas eingeben, wird die *doc-Assembly* ausgeschlossen, wenn *docker* dies nicht tut.</span><span class="sxs-lookup"><span data-stu-id="e6dae-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="e6dae-159">Bei Themen Namen wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e6dae-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="e6dae-160">– Wählen Sie diese Option aus  **+**   , um die abgeschlossene CSV-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e6dae-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="e6dae-161">Wählen Sie dann **hochladen**aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-161">Then select **Upload**.</span></span> <span data-ttu-id="e6dae-162">Wenn Ihre Datei erfolgreich verarbeitet wurde, wird ein grünes Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6dae-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="e6dae-163">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="e6dae-164">Auf der Seite " **Wer kann Themen sehen" und "wo Sie diese anzeigen können** " Konfigurieren Sie die Sichtbarkeit des Themas.</span><span class="sxs-lookup"><span data-stu-id="e6dae-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="e6dae-165">In der Liste der Benutzer, die **Themen in der Wissensnetzwerk Einstellung anzeigen können** , wählen Sie aus, wer Zugriff auf Themen Details haben soll, wie beispielsweise hervorgehobene Themen, Themenkarten, Themen Antworten auf der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="e6dae-166">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6dae-166">You can select:</span></span></br>
    <span data-ttu-id="e6dae-167">a.</span><span class="sxs-lookup"><span data-stu-id="e6dae-167">a.</span></span> <span data-ttu-id="e6dae-168">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="e6dae-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="e6dae-169">b.</span><span class="sxs-lookup"><span data-stu-id="e6dae-169">b.</span></span> <span data-ttu-id="e6dae-170">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="e6dae-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="e6dae-171">c.</span><span class="sxs-lookup"><span data-stu-id="e6dae-171">c.</span></span> <span data-ttu-id="e6dae-172">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="e6dae-172">**No one**</span></span></br>

    ![Wer Themen sehen kann](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="e6dae-174">Während Sie mit dieser Einstellung einen beliebigen Benutzer in Ihrer Organisation auswählen können, können nur Benutzer, denen Lizenzen für Wissensmanagement zugewiesen sind, Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="e6dae-175">Wählen Sie auf der Seite **Berechtigungen für die Themen Verwaltung** aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="e6dae-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="e6dae-176">Im Abschnitt **who can create and Edit topics** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6dae-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="e6dae-177">a.</span><span class="sxs-lookup"><span data-stu-id="e6dae-177">a.</span></span> <span data-ttu-id="e6dae-178">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="e6dae-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="e6dae-179">b.</span><span class="sxs-lookup"><span data-stu-id="e6dae-179">b.</span></span> <span data-ttu-id="e6dae-180">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="e6dae-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="e6dae-181">Im Abschnitt **Verwalten von Themen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="e6dae-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="e6dae-182">a.</span><span class="sxs-lookup"><span data-stu-id="e6dae-182">a.</span></span> <span data-ttu-id="e6dae-183">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="e6dae-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="e6dae-184">b.</span><span class="sxs-lookup"><span data-stu-id="e6dae-184">b.</span></span> <span data-ttu-id="e6dae-185">**Ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="e6dae-185">**Selected people or security groups**</span></span></br>

    ![Berechtigungen für die Themen Verwaltung](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="e6dae-187">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="e6dae-188">Auf der Seite **Thema Center erstellen** können Sie Ihre Themen Center-Website erstellen, in der die Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="e6dae-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="e6dae-189">Geben Sie im Feld **Themen Center Name** einen Namen für Ihr Themen Center ein.</span><span class="sxs-lookup"><span data-stu-id="e6dae-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="e6dae-190">Sie können optional eine kurze Beschreibung in das Feld **Website Beschreibung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="e6dae-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="e6dae-191">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-191">Select **Next**.</span></span></br>

   ![Wissens Center erstellen](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="e6dae-193">Auf der Seite **überprüfen und fertig stellen** können Sie sich Ihre ausgewählte Einstellung ansehen und auswählen, dass Sie Änderungen vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="e6dae-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="e6dae-194">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Fertig stellen und überprüfen](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="e6dae-196">Die Seite **Wissensnetzwerk aktiviert** wird angezeigt und bestätigt, dass das System jetzt mit der Analyse der ausgewählten Websites für Themen beginnt und die Knowledge Center-Website erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6dae-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="e6dae-197">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="e6dae-197">Select **Done**.</span></span></br>

    ![Aktiviert](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="e6dae-199">Sie kehren zur Seite " **Personen an Wissen verbinden** " zurück.</span><span class="sxs-lookup"><span data-stu-id="e6dae-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="e6dae-200">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e6dae-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Angewendete Einstellungen](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="e6dae-202">Nach dem Setup kann ein Administrator jederzeit [Änderungen an den ausgewählten Wissens Verwaltungseinstellungen vornehmen](manage-knowledge-network.md) , indem er zu dieser Seite zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="e6dae-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="e6dae-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6dae-203">See also</span></span>



  






