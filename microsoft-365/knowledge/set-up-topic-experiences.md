---
title: Einrichten von Themen Erfahrungen in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Einrichten von Themen Erfahrungen in Microsoft 365
ms.openlocfilehash: df4dccead4b627a215ec7ebd11932aa0f2b6ac08
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731367"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="30f8b-103">Einrichten von Themen Erfahrungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30f8b-103">Set up topic experiences in Microsoft 365</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LBp7]  

</br>

<span data-ttu-id="30f8b-104">Sie können das Microsoft 365 Admin Center verwenden, um [Themen Erfahrungen](topic-experiences-overview.md)einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="30f8b-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="30f8b-105">Es ist wichtig, die beste Möglichkeit zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="30f8b-106">Lesen Sie unbedingt [Plan Topic Experiences](plan-topic-experiences.md) , bevor Sie mit den Verfahren in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="30f8b-107">Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zuzugreifen und Themen Erfahrungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="30f8b-108">Topic Experiences einrichten</span><span class="sxs-lookup"><span data-stu-id="30f8b-108">Set up topic experiences</span></span>

<span data-ttu-id="30f8b-109">So richten Sie Themen Erfahrungen in Microsoft 365 ein</span><span class="sxs-lookup"><span data-stu-id="30f8b-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="30f8b-110">Wählen Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com) **Setup** aus, und zeigen Sie dann den Abschnitt **Dateien und Inhalt** an.</span><span class="sxs-lookup"><span data-stu-id="30f8b-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="30f8b-111">Klicken Sie im Abschnitt **Dateien und Inhalt** auf **Personen mit Wissen verbinden**.</span><span class="sxs-lookup"><span data-stu-id="30f8b-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Verbinden von Personen mit wissen](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="30f8b-113">Klicken Sie auf der Seite **zum Verbinden von Benutzern mit Informationen** auf **Erste Schritte** , um Sie durch den Setupprozess zu führen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Erste Schritte](../media/k-get-started.png) 

4. <span data-ttu-id="30f8b-115">Auf der Seite **Wählen Sie aus, wie das Wissensnetzwerk Themen finden kann** , konfigurieren Sie die Themen Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="30f8b-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="30f8b-116">Wählen Sie im Abschnitt **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="30f8b-117">Wählen Sie zwischen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-117">Choose from:</span></span>
    - <span data-ttu-id="30f8b-118">**Alle Websites**: alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="30f8b-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="30f8b-119">Dazu gehören aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="30f8b-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="30f8b-120">**Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="30f8b-121">Sie können auch eine Liste der Websites hochladen, von denen Sie die Ermittlung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="30f8b-122">In Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="30f8b-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="30f8b-123">**Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="30f8b-124">Sie können auch eine Liste der Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-124">You can also upload a list of sites.</span></span> <span data-ttu-id="30f8b-125">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="30f8b-126">**Keine Websites**: keine SharePoint-Websites einschließen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Auswählen der Suche nach Themen](../media/ksetup1.png) 
   
5. <span data-ttu-id="30f8b-128">Im Abschnitt **Themen nach Name ausschließen** können Sie Namen von Themen hinzufügen, die Sie von der Themen Ermittlung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="30f8b-129">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="30f8b-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="30f8b-130">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-130">The options are:</span></span>
    - <span data-ttu-id="30f8b-131">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="30f8b-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="30f8b-132">**Themen nach Namen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="30f8b-132">**Exclude topics by name**</span></span>

    ![Themen ausschließen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="30f8b-134">(Knowledge Manager können Themen im Themen Center nach der Ermittlung auch ausschließen.)</span><span class="sxs-lookup"><span data-stu-id="30f8b-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="30f8b-135">So schließen Sie Themen nach Namen aus</span><span class="sxs-lookup"><span data-stu-id="30f8b-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="30f8b-136">Wenn Sie Themen ausschließen müssen, nachdem Sie **Themen nach Namen ausschließen** ausgewählt haben, wählen Sie die CSV-Vorlage herunterladen aus, und aktualisieren Sie Sie mit der Liste der Themen, die Sie aus ihren Ermittlungsergebnissen ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Themen in CSV-Vorlage ausschließen](../media/exclude-topics-csv.png) 

    <span data-ttu-id="30f8b-138">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="30f8b-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="30f8b-139">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="30f8b-140">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="30f8b-141">Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL*).</span><span class="sxs-lookup"><span data-stu-id="30f8b-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="30f8b-142">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="30f8b-143">Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis*, *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur*, nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="30f8b-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="30f8b-144">**Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.</span><span class="sxs-lookup"><span data-stu-id="30f8b-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="30f8b-145">**MatchType-Exact/Partial**: Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.</span><span class="sxs-lookup"><span data-stu-id="30f8b-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="30f8b-146">Nachdem Sie die CSV-Datei abgeschlossen und gespeichert haben, wählen Sie **Durchsuchen** aus, um Sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="30f8b-147">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-147">Select **Next**.</span></span>

6. <span data-ttu-id="30f8b-148">Auf der Seite " **Wer kann Themen sehen" und "wo können Sie diese sehen** " wird die Sichtbarkeit des Themas konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="30f8b-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="30f8b-149">In der Liste der Benutzer, die **Themen in der Wissensnetzwerk Einstellung anzeigen können** , wählen Sie aus, wer Zugriff auf Themen Details haben soll, wie beispielsweise hervorgehobene Themen, Themenkarten, Themen Antworten auf der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="30f8b-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="30f8b-150">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-150">You can select:</span></span>
    - <span data-ttu-id="30f8b-151">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="30f8b-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="30f8b-152">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="30f8b-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="30f8b-153">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="30f8b-153">**No one**</span></span>

    ![Wer Themen sehen kann](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="30f8b-155">Während diese Einstellung es Ihnen ermöglicht, einen beliebigen Benutzer in Ihrer Organisation auszuwählen, können nur Benutzer, denen die Lizenzen für ein Themen Erlebnis zugewiesen sind, Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="30f8b-156">Wählen Sie auf der Seite **Berechtigungen für die Themen Verwaltung** aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="30f8b-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="30f8b-157">Im Abschnitt **who can create and Edit topics** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="30f8b-158">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="30f8b-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="30f8b-159">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="30f8b-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="30f8b-160">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="30f8b-160">**No one**</span></span>

    ![Berechtigungen für die Thema Verwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. <span data-ttu-id="30f8b-162">Im Abschnitt **Verwalten von Themen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="30f8b-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="30f8b-163">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="30f8b-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="30f8b-164">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="30f8b-164">**Only selected people or security groups**</span></span>

    ![Berechtigungen für die Themen Verwaltung](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="30f8b-166">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-166">Select **Next**.</span></span>

9. <span data-ttu-id="30f8b-167">Auf der Seite **Thema Center erstellen** können Sie Ihre Themen Center-Website erstellen, in der die Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="30f8b-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="30f8b-168">Geben Sie im Feld **Websitename** einen Namen für Ihr Themen Center ein.</span><span class="sxs-lookup"><span data-stu-id="30f8b-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="30f8b-169">Sie können optional eine kurze Beschreibung in das Feld **Beschreibung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="30f8b-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="30f8b-170">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-170">Select **Next**.</span></span>

   ![Wissens Center erstellen](../media/ksetup4.png)  

10. <span data-ttu-id="30f8b-172">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="30f8b-173">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="30f8b-174">Die Seite **Wissensnetzwerk aktiviert** wird angezeigt und bestätigt, dass das System jetzt mit der Analyse der ausgewählten Websites für Themen beginnt und die Knowledge Center-Website erstellt.</span><span class="sxs-lookup"><span data-stu-id="30f8b-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="30f8b-175">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-175">Select **Done**.</span></span>

12. <span data-ttu-id="30f8b-176">Sie kehren zur Seite " **Personen an Wissen verbinden** " zurück.</span><span class="sxs-lookup"><span data-stu-id="30f8b-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="30f8b-177">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Angewendete Einstellungen](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="30f8b-179">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="30f8b-179">Assign licenses</span></span>

<span data-ttu-id="30f8b-180">Nachdem Sie Themen Erfahrungen konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die Themen Erfahrungen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="30f8b-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="30f8b-181">Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und das Themen Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="30f8b-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="30f8b-182">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="30f8b-182">To assign licenses:</span></span>

1. <span data-ttu-id="30f8b-183">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="30f8b-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="30f8b-184">Wählen Sie die Benutzer aus, denen Sie eine Lizenz zuweisen möchten, und klicken Sie dann auf **Produktlizenzen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="30f8b-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="30f8b-185">Wählen Sie **Weitere zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="30f8b-186">Wählen Sie unter **Lizenzen** die Option **Themen Erfahrungen** aus.</span><span class="sxs-lookup"><span data-stu-id="30f8b-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="30f8b-187">Stellen Sie sicher, dass unter **apps** die Option **Graph Connectors Search with Index** and **Topic Experiences** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="30f8b-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30f8b-188">![SharePoint Syntex-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="30f8b-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="30f8b-189">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="30f8b-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="30f8b-190">Verwalten von Themen Erfahrungen</span><span class="sxs-lookup"><span data-stu-id="30f8b-190">Manage topic experiences</span></span>

<span data-ttu-id="30f8b-191">Nachdem Sie Themen Erfahrungen eingerichtet haben, können Sie die Einstellungen ändern, die Sie während des Setups im [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="30f8b-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="30f8b-192">Siehe die folgenden Verweise:</span><span class="sxs-lookup"><span data-stu-id="30f8b-192">See the following references:</span></span>

- [<span data-ttu-id="30f8b-193">Verwalten der Themen Ermittlung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30f8b-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="30f8b-194">Verwalten der Themen Sichtbarkeit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30f8b-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="30f8b-195">Verwalten von Themen Berechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30f8b-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="30f8b-196">Ändern des Namens des Themen Centers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30f8b-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="30f8b-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30f8b-197">See also</span></span>

[<span data-ttu-id="30f8b-198">Übersicht über Themen Erlebnisse</span><span class="sxs-lookup"><span data-stu-id="30f8b-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
