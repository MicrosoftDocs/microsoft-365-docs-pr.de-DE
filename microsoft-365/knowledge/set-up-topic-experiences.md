---
title: 'Einrichten der Wissensverwaltung (Vorschau) '
description: Einrichten der Wissensverwaltung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989000"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="68171-103">Einrichten der Wissensverwaltung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="68171-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="68171-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="68171-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="68171-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="68171-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="68171-106">Sie können das Microsoft 365 Admin Center verwenden, um die [Wissensverwaltung](knowledge-management-overview.md)einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68171-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="68171-107">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren des Wissensmanagements in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="68171-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="68171-108">Beispielsweise müssen Sie Überlegungen zu den folgenden Aspekten treffen:</span><span class="sxs-lookup"><span data-stu-id="68171-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="68171-109">Die SharePoint-Websites, die Sie für Themen analysieren möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="68171-110">Die Benutzer, für die Sie Themen sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="68171-111">Die Benutzer, denen Sie Berechtigungen zum Verwalten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="68171-112">Die Benutzer, denen Sie Berechtigungen zum Erstellen oder Bearbeiten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="68171-113">Welchen Namen möchten Sie Ihrem Themen Center geben?</span><span class="sxs-lookup"><span data-stu-id="68171-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="68171-114">Möglicherweise ist es hilfreich, Sicherheitsgruppen zu erstellen, um Ihren Benutzern die Berechtigungen zu erteilen, die zum Anzeigen von Themen, zum Verwalten des Themas und zum Erstellen und Bearbeiten von Themen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="68171-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="68171-115">Ein Administrator kann [Änderungen an den ausgewählten Einstellungen auch jederzeit nach dem Setup](topic-experiences-discovery.md) über die Knowledge Management-Einstellungen im Microsoft 365 Admin Center vornehmen.</span><span class="sxs-lookup"><span data-stu-id="68171-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="68171-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68171-116">Requirements</span></span> 
<span data-ttu-id="68171-117">Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und organisatorische Wissens Aufgaben einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="68171-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="68171-118">Einrichten Ihres Wissensnetzwerks</span><span class="sxs-lookup"><span data-stu-id="68171-118">Set up your knowledge network</span></span>

<span data-ttu-id="68171-119">Das Einrichten Ihres Wissensnetzwerks führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="68171-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="68171-120">Thema Discovery: Auswählen von Themen Quellen und Themen, die von der Suche ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68171-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="68171-121">Thema Visibility: auswählen, wer Themen als Highlights anzeigen kann, in Such-und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="68171-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="68171-122">Thema Permissions: Auswählen der Personen, die Themen erstellen, bearbeiten und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="68171-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="68171-123">Themen Center: Erstellen Ihres Themen Centers.</span><span class="sxs-lookup"><span data-stu-id="68171-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="68171-124">Überprüfung: überprüfen und Anwenden Ihrer Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="68171-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="68171-125">So richten Sie Ihr Wissensnetzwerk ein:</span><span class="sxs-lookup"><span data-stu-id="68171-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="68171-126">Wählen Sie im Microsoft 365 Admin Center (admin.Microsoft.com) die Option **Setup** aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.</span><span class="sxs-lookup"><span data-stu-id="68171-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="68171-127">Klicken Sie im Abschnitt **organisatorisches Wissen** auf **Personen mit Wissen verbinden**.</span><span class="sxs-lookup"><span data-stu-id="68171-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Verbinden von Personen mit wissen](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="68171-129">Klicken Sie auf der Seite **zum Verbinden von Benutzern mit Informationen** auf **Erste Schritte** , um Sie durch den Setupprozess zu führen.</span><span class="sxs-lookup"><span data-stu-id="68171-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Erste Schritte](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="68171-131">Auf der Seite **Wählen Sie aus, wie das Wissensnetzwerk Themen finden kann** , konfigurieren Sie die Themen Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="68171-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="68171-132">Wählen Sie im Abschnitt **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68171-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="68171-133">Hierzu zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="68171-133">This includes:</span></span></br>
    <span data-ttu-id="68171-134">a.</span><span class="sxs-lookup"><span data-stu-id="68171-134">a.</span></span> <span data-ttu-id="68171-135">**Alle Websites** : alle SharePoint-Websites in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="68171-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="68171-136">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="68171-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="68171-137">b.</span><span class="sxs-lookup"><span data-stu-id="68171-137">b.</span></span> <span data-ttu-id="68171-138">**Alle, außer ausgewählte Websites** : Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="68171-139">Sie können auch eine Liste der Websites hochladen, von denen Sie die Ermittlung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="68171-140">In Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68171-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="68171-141">c.</span><span class="sxs-lookup"><span data-stu-id="68171-141">c.</span></span> <span data-ttu-id="68171-142">**Nur ausgewählte Websites** : Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="68171-143">Sie können auch eine Liste der Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="68171-143">You can also upload a list of sites.</span></span> <span data-ttu-id="68171-144">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="68171-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Auswählen der Suche nach Themen](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="68171-146">Im Abschnitt **Themen nach Name ausschließen** können Sie auswählen, dass Themen Namen eingeschlossen werden sollen, die nicht in den ermittelten Ergebnissen enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="68171-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="68171-147">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Themen als Teil des Wissensnetzwerks einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="68171-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="68171-148">Zu den Optionen gehören:</span><span class="sxs-lookup"><span data-stu-id="68171-148">Your options include:</span></span></br>
    <span data-ttu-id="68171-149">a.</span><span class="sxs-lookup"><span data-stu-id="68171-149">a.</span></span> <span data-ttu-id="68171-150">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="68171-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="68171-151">b.</span><span class="sxs-lookup"><span data-stu-id="68171-151">b.</span></span> <span data-ttu-id="68171-152">**Themen nach Namen ausschließen** : Wenn Sie Themen haben, die den Benutzern nicht als Teil des Wissensnetzwerks angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68171-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Themen ausschließen](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="68171-154">So schließen Sie Themen nach Namen aus</span><span class="sxs-lookup"><span data-stu-id="68171-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="68171-155">Wenn Sie Themen ausschließen müssen, wählen Sie nach dem auswählen **von Themen nach Namen ausschließen** **die Option CSV-Vorlage herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="68171-156">Verwenden Sie die Excel. CSV-Vorlage, um eine Liste von Themen einzuschließen, die von den Ermittlungsergebnissen ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68171-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Themen in CSV-Vorlage ausschließen](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="68171-158">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="68171-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="68171-159">**Name** : Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="68171-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="68171-160">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="68171-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="68171-161">Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL* ).</span><span class="sxs-lookup"><span data-stu-id="68171-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="68171-162">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="68171-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="68171-163">Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis* , *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur* , nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="68171-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="68171-164">**Expansion (optional)** : Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.</span><span class="sxs-lookup"><span data-stu-id="68171-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="68171-165">**MatchType-Exact/Partial** : Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.</span><span class="sxs-lookup"><span data-stu-id="68171-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="68171-166">Nachdem Sie die CSV-Vorlagendatei abgeschlossen und gespeichert haben, wählen Sie **Durchsuchen** aus, um Sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="68171-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="68171-167">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="68171-168">Auf der Seite " **Wer kann Themen sehen" und "wo Sie diese anzeigen können** " Konfigurieren Sie die Sichtbarkeit des Themas.</span><span class="sxs-lookup"><span data-stu-id="68171-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="68171-169">In der Liste der Benutzer, die **Themen in der Wissensnetzwerk Einstellung anzeigen können** , wählen Sie aus, wer Zugriff auf Themen Details haben soll, wie beispielsweise hervorgehobene Themen, Themenkarten, Themen Antworten auf der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="68171-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="68171-170">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="68171-170">You can select:</span></span></br>
    <span data-ttu-id="68171-171">a.</span><span class="sxs-lookup"><span data-stu-id="68171-171">a.</span></span> <span data-ttu-id="68171-172">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="68171-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="68171-173">b.</span><span class="sxs-lookup"><span data-stu-id="68171-173">b.</span></span> <span data-ttu-id="68171-174">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="68171-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="68171-175">c.</span><span class="sxs-lookup"><span data-stu-id="68171-175">c.</span></span> <span data-ttu-id="68171-176">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="68171-176">**No one**</span></span></br>

    ![Wer Themen sehen kann](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="68171-178">Während Sie mit dieser Einstellung einen beliebigen Benutzer in Ihrer Organisation auswählen können, können nur Benutzer, denen Lizenzen für Wissensmanagement zugewiesen sind, Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="68171-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="68171-179">Wählen Sie auf der Seite **Berechtigungen für die Themen Verwaltung** aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="68171-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="68171-180">Im Abschnitt **who can create and Edit topics** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="68171-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="68171-181">a.</span><span class="sxs-lookup"><span data-stu-id="68171-181">a.</span></span> <span data-ttu-id="68171-182">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="68171-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="68171-183">b.</span><span class="sxs-lookup"><span data-stu-id="68171-183">b.</span></span> <span data-ttu-id="68171-184">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="68171-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="68171-185">Im Abschnitt **Verwalten von Themen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="68171-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="68171-186">a.</span><span class="sxs-lookup"><span data-stu-id="68171-186">a.</span></span> <span data-ttu-id="68171-187">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="68171-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="68171-188">b.</span><span class="sxs-lookup"><span data-stu-id="68171-188">b.</span></span> <span data-ttu-id="68171-189">**Ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="68171-189">**Selected people or security groups**</span></span></br>

    ![Berechtigungen für die Themen Verwaltung](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="68171-191">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="68171-192">Auf der Seite **Thema Center erstellen** können Sie Ihre Themen Center-Website erstellen, in der die Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="68171-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="68171-193">Geben Sie im Feld **Themen Center Name** einen Namen für Ihr Themen Center ein.</span><span class="sxs-lookup"><span data-stu-id="68171-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="68171-194">Sie können optional eine kurze Beschreibung in das Feld **Website Beschreibung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="68171-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="68171-195">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-195">Select **Next**.</span></span></br>

   ![Wissens Center erstellen](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="68171-197">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="68171-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="68171-198">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Fertig stellen und überprüfen](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="68171-200">Die Seite **Wissensnetzwerk aktiviert** wird angezeigt und bestätigt, dass das System jetzt mit der Analyse der ausgewählten Websites für Themen beginnt und die Knowledge Center-Website erstellt.</span><span class="sxs-lookup"><span data-stu-id="68171-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="68171-201">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="68171-201">Select **Done**.</span></span></br>

    ![Aktiviert](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="68171-203">Sie kehren zur Seite " **Personen an Wissen verbinden** " zurück.</span><span class="sxs-lookup"><span data-stu-id="68171-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="68171-204">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="68171-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Angewendete Einstellungen](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="68171-206">Nach dem Setup kann ein Administrator jederzeit [Änderungen an den ausgewählten Wissens Verwaltungseinstellungen vornehmen](topic-experiences-discovery.md) , indem er zu dieser Seite zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="68171-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="68171-207">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="68171-207">See also</span></span>



  






