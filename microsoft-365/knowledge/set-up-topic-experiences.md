---
title: Einrichten von Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informationen zum Einrichten von Microsoft Viva Topics
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930221"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="9f7af-103">Einrichten von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9f7af-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="9f7af-104">Sie können das Microsoft 365 Admin Center zum Einrichten und Konfigurieren von [Themen verwenden.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9f7af-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="9f7af-105">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="9f7af-106">Lesen Sie unbedingt [Plan for Microsoft Viva Topics,](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="9f7af-107">Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="9f7af-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="9f7af-108">Wenn Sie die SharePoint für [verwaltete](/sharepoint/control-access-from-unmanaged-devices)Geräte konfiguriert haben, müssen Sie Themen auf einem verwalteten Gerät einrichten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="9f7af-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="9f7af-109">Video demonstration</span></span>

<span data-ttu-id="9f7af-110">Dieses Video zeigt den Prozess zum Einrichten von Themen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f7af-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="9f7af-111">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="9f7af-111">Assign licenses</span></span>

<span data-ttu-id="9f7af-112">Sie müssen lizenzen für die Benutzer zuweisen, die Themen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="9f7af-113">Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und dem Themencenter anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="9f7af-114">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="9f7af-114">To assign licenses:</span></span>

1. <span data-ttu-id="9f7af-115">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="9f7af-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="9f7af-116">Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **Lizenzen und Apps**.</span><span class="sxs-lookup"><span data-stu-id="9f7af-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="9f7af-117">Wählen **Sie unter Lizenzen** die Option Viva Topics **aus.**</span><span class="sxs-lookup"><span data-stu-id="9f7af-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="9f7af-118">Stellen **Sie unter Apps** sicher, Graph Connectors Search with Index **(Viva Topics)** und Viva **Topics** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="9f7af-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9f7af-119">![Microsoft Viva Topics-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="9f7af-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="9f7af-120">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="9f7af-120">Click **Save changes**.</span></span>

<span data-ttu-id="9f7af-121">Es kann bis zu einer Stunde dauern, bis Benutzer zugriff auf Themen erhalten, nachdem die Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="9f7af-122">Einrichten von Themen</span><span class="sxs-lookup"><span data-stu-id="9f7af-122">Set up Topics</span></span>

<span data-ttu-id="9f7af-123">So richten Sie Themen ein</span><span class="sxs-lookup"><span data-stu-id="9f7af-123">To set up Topics</span></span>

1. <span data-ttu-id="9f7af-124">Wählen Sie [Microsoft 365 Admin Center](https://admin.microsoft.com)setup aus, und zeigen Sie dann den Abschnitt Dateien und **Inhalte** an. </span><span class="sxs-lookup"><span data-stu-id="9f7af-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="9f7af-125">Klicken Sie **im Abschnitt** Dateien und Inhalt auf Verbinden personen **zum Wissen.**</span><span class="sxs-lookup"><span data-stu-id="9f7af-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Verbinden personen zum Wissen](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="9f7af-127">Klicken Sie **Verbinden Seite "Personen zu Wissen"** auf **Erste** Schritte, um Sie durch den Einrichtungsprozess zu gehen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Erste Schritte](../media/k-get-started.png) 

4. <span data-ttu-id="9f7af-129">Auf der **Seite Auswählen, wie Themen von "Themen" zu** finden sind, konfigurieren Sie die Themenermittlung.</span><span class="sxs-lookup"><span data-stu-id="9f7af-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="9f7af-130">Wählen Sie **im SharePoint** Auswählen von Themenquellen aus, SharePoint websites während der Suche als Quellen für Ihre Themen durchforstet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="9f7af-131">Wählen Sie zwischen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-131">Choose from:</span></span>
    - <span data-ttu-id="9f7af-132">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9f7af-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="9f7af-133">Dies schließt aktuelle und zukünftige Websites ein.</span><span class="sxs-lookup"><span data-stu-id="9f7af-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="9f7af-134">**Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="9f7af-135">Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="9f7af-136">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="9f7af-137">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="9f7af-138">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-138">You can also upload a list of sites.</span></span> <span data-ttu-id="9f7af-139">Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="9f7af-140">**Keine Websites**: Schließen Sie keine SharePoint-Websites ein.</span><span class="sxs-lookup"><span data-stu-id="9f7af-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Auswählen des Suchens von Themen](../media/ksetup1.png) 
   
5. <span data-ttu-id="9f7af-142">Im Abschnitt **Themen nach Name** ausschließen können Sie Namen von Themen hinzufügen, die Sie von der Themenermittlung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="9f7af-143">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="9f7af-144">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-144">The options are:</span></span>
    - <span data-ttu-id="9f7af-145">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="9f7af-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="9f7af-146">**Ausschließen von Themen nach Namen**</span><span class="sxs-lookup"><span data-stu-id="9f7af-146">**Exclude topics by name**</span></span>

    ![Ausschließen von Themen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="9f7af-148">(Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)</span><span class="sxs-lookup"><span data-stu-id="9f7af-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="9f7af-149">So schließen Sie Themen nach Namen aus</span><span class="sxs-lookup"><span data-stu-id="9f7af-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="9f7af-150">Wenn Sie Themen ausschließen müssen, laden Sie nach auswahl von Themen nach Name ausschließen die .csv-Vorlage herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten. </span><span class="sxs-lookup"><span data-stu-id="9f7af-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

    <span data-ttu-id="9f7af-152">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="9f7af-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="9f7af-153">**Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f7af-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="9f7af-154">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="9f7af-155">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*</span><span class="sxs-lookup"><span data-stu-id="9f7af-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="9f7af-156">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9f7af-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="9f7af-157">Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="9f7af-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="9f7af-158">**Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="9f7af-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="9f7af-159">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="9f7af-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="9f7af-160">Nachdem Sie ihre Datei abgeschlossen und .csv haben, wählen Sie **Durchsuchen** aus, um sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="9f7af-161">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9f7af-161">Select **Next**.</span></span>

6. <span data-ttu-id="9f7af-162">Auf der **Wer Themen angezeigt werden** und wo sie angezeigt werden können, konfigurieren Sie die Sichtbarkeit des Themas.</span><span class="sxs-lookup"><span data-stu-id="9f7af-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="9f7af-163">In der **Wer** themeneinstellung können Sie auswählen, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="9f7af-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="9f7af-164">Sie können wählen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-164">You can select:</span></span>
    - <span data-ttu-id="9f7af-165">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="9f7af-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9f7af-166">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="9f7af-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="9f7af-167">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="9f7af-167">**No one**</span></span>

    ![Wer können Themen sehen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="9f7af-169">Mit dieser Einstellung können Sie zwar beliebige Benutzer in Ihrer Organisation auswählen, aber nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, können Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="9f7af-170">Auf der **Seite Berechtigungen für die Themenverwaltung** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="9f7af-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="9f7af-171">Im Abschnitt **Wer Können Sie Themen erstellen und** bearbeiten, können Sie folgende Option auswählen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="9f7af-172">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="9f7af-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9f7af-173">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="9f7af-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="9f7af-174">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="9f7af-174">**No one**</span></span>

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. <span data-ttu-id="9f7af-176">Im Abschnitt **Wer Themen verwalten** können, können Sie folgende Option auswählen:</span><span class="sxs-lookup"><span data-stu-id="9f7af-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="9f7af-177">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="9f7af-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="9f7af-178">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="9f7af-178">**Only selected people or security groups**</span></span>

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="9f7af-180">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9f7af-180">Select **Next**.</span></span>

9. <span data-ttu-id="9f7af-181">Auf der **Seite Themencenter erstellen** können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="9f7af-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="9f7af-182">Geben Sie **im Feld** Websitename einen Namen für Ihr Themencenter ein.</span><span class="sxs-lookup"><span data-stu-id="9f7af-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="9f7af-183">Optional können Sie eine kurze Beschreibung in das Feld **Beschreibung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="9f7af-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="9f7af-184">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9f7af-184">Select **Next**.</span></span>

   ![Erstellen von Knowledge Center](../media/ksetup4.png)  

10. <span data-ttu-id="9f7af-186">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="9f7af-187">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9f7af-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="9f7af-188">Die **aktivierte Seite "Viva Topics"** wird angezeigt, um zu bestätigen, dass das System nun mit der Analyse der ausgewählten Websites für Themen beginnt und die Themencenterwebsite erstellt.</span><span class="sxs-lookup"><span data-stu-id="9f7af-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="9f7af-189">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="9f7af-189">Select **Done**.</span></span>

12. <span data-ttu-id="9f7af-190">Sie werden an Ihre Seite "Personen **Verbinden wissen"** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f7af-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="9f7af-191">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9f7af-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Einstellungen angewendet](../media/ksetup7.png)    

<span data-ttu-id="9f7af-193">Beachten Sie, dass es bei der ersten Aktivierung der Themenermittlung bis zu zwei Wochen dauern kann, bis alle vorgeschlagenen Themen in der Ansicht Themen verwalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="9f7af-194">Die Themenermittlung wird fortgesetzt, wenn neue Inhalte oder Aktualisierungen von Inhalten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="9f7af-195">Es ist normal, dass es Schwankungen bei der Anzahl vorgeschlagener Themen in Ihrer Organisation gibt, wenn Neue Informationen von Viva Topics ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="9f7af-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="9f7af-196">Verwalten von Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="9f7af-196">Manage topic experiences</span></span>

<span data-ttu-id="9f7af-197">Nachdem Sie Themen eingerichtet haben, können Sie die Einstellungen ändern, die Sie während des Setups im [Microsoft 365 admin center ausgewählt haben.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="9f7af-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="9f7af-198">Sehen Sie sich die folgenden Verweise an:</span><span class="sxs-lookup"><span data-stu-id="9f7af-198">See the following references:</span></span>

- [<span data-ttu-id="9f7af-199">Verwalten der Themensuche in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9f7af-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="9f7af-200">Verwalten der Sichtbarkeit von Themen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9f7af-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="9f7af-201">Verwalten von Themenberechtigungen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9f7af-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="9f7af-202">Ändern des Namens des Themencenters in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9f7af-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="9f7af-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f7af-203">See also</span></span>

[<span data-ttu-id="9f7af-204">Übersicht über Die Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="9f7af-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
