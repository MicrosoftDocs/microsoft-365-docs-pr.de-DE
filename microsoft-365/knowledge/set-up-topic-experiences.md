---
title: Einrichten von Microsoft -Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Hier erfahren Sie, wie Sie Microsoft -Themen einrichten
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150500"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="52384-103">Einrichten von Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="52384-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="52384-104">Sie können das Microsoft 365 Admin Center zum Einrichten und Konfigurieren von Themen [verwenden.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="52384-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="52384-105">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="52384-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="52384-106">Lesen Sie unbedingt ["Planen von Microsoft -Themen",](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="52384-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="52384-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span><span class="sxs-lookup"><span data-stu-id="52384-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="52384-108">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="52384-108">Video demonstration</span></span>

<span data-ttu-id="52384-109">In diesem Video wird der Prozess zum Einrichten von Themen in Microsoft 365 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="52384-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="52384-110">Einrichten von Themen</span><span class="sxs-lookup"><span data-stu-id="52384-110">Set up Topics</span></span>

<span data-ttu-id="52384-111">So richten Sie Themen ein</span><span class="sxs-lookup"><span data-stu-id="52384-111">To set up Topics</span></span>

1. <span data-ttu-id="52384-112">Wählen Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com) **"Setup"** aus, und zeigen Sie dann den Abschnitt **"Dateien und Inhalt"** an.</span><span class="sxs-lookup"><span data-stu-id="52384-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="52384-113">Klicken Sie **im Abschnitt "Dateien und Inhalte"** **auf "Personen mit Wissen verbinden".**</span><span class="sxs-lookup"><span data-stu-id="52384-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Verbinden von Personen mit Wissen](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="52384-115">Klicken Sie **auf der Seite "Personen mit Wissen verbinden"** auf **"Erste** Schritte", um Sie durch den Einrichtungsprozess zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52384-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Erste Schritte](../media/k-get-started.png) 

4. <span data-ttu-id="52384-117">Auf der **Seite "Auswählen, wie Themen unter "Themen" zu** finden sind, konfigurieren Sie die Themenermittlung.</span><span class="sxs-lookup"><span data-stu-id="52384-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="52384-118">Wählen Sie **im Abschnitt "SharePoint-Themenquellen** auswählen" aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="52384-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="52384-119">Wählen Sie zwischen:</span><span class="sxs-lookup"><span data-stu-id="52384-119">Choose from:</span></span>
    - <span data-ttu-id="52384-120">**Alle Websites:** Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="52384-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="52384-121">Dazu gehören aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="52384-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="52384-122">**Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="52384-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="52384-123">Sie können auch eine Liste der Websites hochladen, für die Sie die Suche abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="52384-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="52384-124">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="52384-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="52384-125">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="52384-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="52384-126">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="52384-126">You can also upload a list of sites.</span></span> <span data-ttu-id="52384-127">Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="52384-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="52384-128">**Keine Websites:** Keine SharePoint-Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="52384-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Auswählen der Themensuche](../media/ksetup1.png) 
   
5. <span data-ttu-id="52384-130">Im Abschnitt **"Themen nach Namen** ausschließen" können Sie Namen von Themen hinzufügen, die sie aus der Themenermittlung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="52384-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="52384-131">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="52384-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="52384-132">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="52384-132">The options are:</span></span>
    - <span data-ttu-id="52384-133">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="52384-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="52384-134">**Ausschließen von Themen nach Namen**</span><span class="sxs-lookup"><span data-stu-id="52384-134">**Exclude topics by name**</span></span>

    ![Ausschließen von Themen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="52384-136">(Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)</span><span class="sxs-lookup"><span data-stu-id="52384-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="52384-137">Ausschließen von Themen nach Namen</span><span class="sxs-lookup"><span data-stu-id="52384-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="52384-138">Wenn Sie Themen ausschließen müssen, laden Sie nach auswahl von "Themen nach Namen ausschließen" die CSV-Vorlage herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten. </span><span class="sxs-lookup"><span data-stu-id="52384-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

    <span data-ttu-id="52384-140">Geben Sie in der Csv-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="52384-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="52384-141">**Name:** Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="52384-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="52384-142">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="52384-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="52384-143">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) verwenden.*</span><span class="sxs-lookup"><span data-stu-id="52384-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="52384-144">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="52384-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="52384-145">Der Bogen *schließt* z. B. alle Themen aus, *in* denen der Wortbogen enthalten ist, z. B. Bogenkreis,  *Arkusbogen* oder *Schulungsbogen.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="52384-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="52384-146">**Steht für (optional):** Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="52384-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="52384-147">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein *exakter* oder teilweiser *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="52384-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="52384-148">Nachdem Sie die CSV-Datei abgeschlossen und gespeichert haben, wählen Sie **"Durchsuchen"** aus, um sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="52384-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="52384-149">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="52384-149">Select **Next**.</span></span>

6. <span data-ttu-id="52384-150">Auf der **Seite "Wer kann Themen anzeigen** und wo kann er sie sehen" konfigurieren Sie die Sichtbarkeit des Themas.</span><span class="sxs-lookup"><span data-stu-id="52384-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="52384-151">In der **Einstellung "Wer** kann Themen anzeigen" wählen Sie aus, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="52384-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="52384-152">Sie können dies auswählen:</span><span class="sxs-lookup"><span data-stu-id="52384-152">You can select:</span></span>
    - <span data-ttu-id="52384-153">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="52384-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="52384-154">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="52384-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="52384-155">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="52384-155">**No one**</span></span>

    ![Wer kann Themen sehen?](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="52384-157">Während Sie mit dieser Einstellung beliebige Benutzer in Ihrer Organisation auswählen können, können nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52384-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="52384-158">Auf der **Seite "Berechtigungen für die Themenverwaltung"** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="52384-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="52384-159">Im Abschnitt **"Wer kann Themen erstellen und** bearbeiten" können Sie folgende Einstellungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="52384-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="52384-160">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="52384-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="52384-161">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="52384-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="52384-162">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="52384-162">**No one**</span></span>

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. <span data-ttu-id="52384-164">Im Abschnitt **"Wer kann Themen verwalten"** können Sie folgende Auswählen:</span><span class="sxs-lookup"><span data-stu-id="52384-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="52384-165">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="52384-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="52384-166">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="52384-166">**Only selected people or security groups**</span></span>

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="52384-168">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="52384-168">Select **Next**.</span></span>

9. <span data-ttu-id="52384-169">Auf der **Seite "Themencenter erstellen"** können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="52384-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="52384-170">Geben Sie **im Feld "Websitename"** einen Namen für Ihr Themencenter ein.</span><span class="sxs-lookup"><span data-stu-id="52384-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="52384-171">Optional können Sie eine kurze Beschreibung in das Feld **"Beschreibung"** eingeben.</span><span class="sxs-lookup"><span data-stu-id="52384-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="52384-172">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="52384-172">Select **Next**.</span></span>

   ![Erstellen des Knowledge Centers](../media/ksetup4.png)  

10. <span data-ttu-id="52384-174">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="52384-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="52384-175">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="52384-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="52384-176">Die **aktivierte Seite "Aktuelle** Themen" wird angezeigt, um zu bestätigen, dass das System nun mit der Analyse der ausgewählten Websites für Themen und dem Erstellen der Themencenterwebsite beginnt.</span><span class="sxs-lookup"><span data-stu-id="52384-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="52384-177">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="52384-177">Select **Done**.</span></span>

12. <span data-ttu-id="52384-178">Sie werden zu Ihrer Seite "Personen mit Wissen **verbinden"** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52384-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="52384-179">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="52384-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Angewendete Einstellungen](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="52384-181">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="52384-181">Assign licenses</span></span>

<span data-ttu-id="52384-182">Nachdem Sie die Themenerfahrungen konfiguriert haben, müssen Sie lizenzen für die Benutzer zuweisen, die Themen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="52384-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="52384-183">Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und das Themencenter anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52384-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="52384-184">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="52384-184">To assign licenses:</span></span>

1. <span data-ttu-id="52384-185">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="52384-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="52384-186">Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **"Lizenzen und Apps".**</span><span class="sxs-lookup"><span data-stu-id="52384-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="52384-187">Stellen **Sie unter "Apps"** sicher, dass die Graph **Connectors search with Index** and Topic **Experiences** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="52384-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="52384-188">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="52384-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="52384-189">Verwalten von Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="52384-189">Manage topic experiences</span></span>

<span data-ttu-id="52384-190">Nachdem Sie Themen eingerichtet haben, können Sie die Einstellungen ändern, die Sie während des Setups im [Microsoft 365 Admin Center ausgewählt haben.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="52384-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="52384-191">Weitere Informationen finden Sie in den folgenden Referenzen:</span><span class="sxs-lookup"><span data-stu-id="52384-191">See the following references:</span></span>

- [<span data-ttu-id="52384-192">Verwalten der Themenermittlung in Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="52384-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="52384-193">Verwalten der Sichtbarkeit von Themen in Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="52384-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="52384-194">Verwalten von Themenberechtigungen in Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="52384-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="52384-195">Ändern des Namens des Themencenters in Microsoft Topics</span><span class="sxs-lookup"><span data-stu-id="52384-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="52384-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52384-196">See also</span></span>

[<span data-ttu-id="52384-197">Übersicht über die Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="52384-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
