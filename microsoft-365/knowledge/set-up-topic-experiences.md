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
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929444"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="38a92-103">Einrichten von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="38a92-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="38a92-104">Sie können das Microsoft 365 Admin Center zum Einrichten und Konfigurieren von [Themen verwenden.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="38a92-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="38a92-105">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="38a92-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="38a92-106">Lesen Sie unbedingt [Plan for Microsoft Viva Topics,](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="38a92-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="38a92-107">Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="38a92-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="38a92-108">Wenn Sie SharePoint so konfiguriert haben, [dass verwaltete](/sharepoint/control-access-from-unmanaged-devices)Geräte erforderlich sind, müssen Sie Themen auf einem verwalteten Gerät einrichten.</span><span class="sxs-lookup"><span data-stu-id="38a92-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="38a92-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="38a92-109">Video demonstration</span></span>

<span data-ttu-id="38a92-110">Dieses Video zeigt den Prozess zum Einrichten von Themen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38a92-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="38a92-111">Einrichten von Themen</span><span class="sxs-lookup"><span data-stu-id="38a92-111">Set up Topics</span></span>

<span data-ttu-id="38a92-112">So richten Sie Themen ein</span><span class="sxs-lookup"><span data-stu-id="38a92-112">To set up Topics</span></span>

1. <span data-ttu-id="38a92-113">Wählen Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com) **Setup** aus, und zeigen Sie dann den Abschnitt Dateien **und Inhalte** an.</span><span class="sxs-lookup"><span data-stu-id="38a92-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="38a92-114">Klicken Sie **im Abschnitt** Dateien und Inhalte auf Personen mit Wissen **verbinden.**</span><span class="sxs-lookup"><span data-stu-id="38a92-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Verbinden von Personen mit Wissen](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="38a92-116">Klicken Sie **auf der Seite Personen mit Wissen verbinden** auf Erste **Schritte,** um Sie durch den Einrichtungsprozess zu gehen.</span><span class="sxs-lookup"><span data-stu-id="38a92-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Erste Schritte](../media/k-get-started.png) 

4. <span data-ttu-id="38a92-118">Auf der **Seite Auswählen, wie Themen von "Themen" zu** finden sind, konfigurieren Sie die Themenermittlung.</span><span class="sxs-lookup"><span data-stu-id="38a92-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="38a92-119">Wählen Sie **im Abschnitt SharePoint-Themenquellen** auswählen aus, welche SharePoint-Websites während der Suche als Quellen für Ihre Themen durchforstet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="38a92-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="38a92-120">Wählen Sie zwischen:</span><span class="sxs-lookup"><span data-stu-id="38a92-120">Choose from:</span></span>
    - <span data-ttu-id="38a92-121">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="38a92-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="38a92-122">Dies umfasst aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="38a92-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="38a92-123">**Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="38a92-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="38a92-124">Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="38a92-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="38a92-125">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="38a92-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="38a92-126">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="38a92-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="38a92-127">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="38a92-127">You can also upload a list of sites.</span></span> <span data-ttu-id="38a92-128">Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="38a92-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="38a92-129">**Keine Websites**: Keine SharePoint-Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="38a92-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Auswählen des Suchens von Themen](../media/ksetup1.png) 
   
5. <span data-ttu-id="38a92-131">Im Abschnitt **Themen nach Name** ausschließen können Sie Namen von Themen hinzufügen, die Sie von der Themenermittlung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="38a92-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="38a92-132">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="38a92-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="38a92-133">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="38a92-133">The options are:</span></span>
    - <span data-ttu-id="38a92-134">**Keine Themen ausschließen**</span><span class="sxs-lookup"><span data-stu-id="38a92-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="38a92-135">**Ausschließen von Themen nach Namen**</span><span class="sxs-lookup"><span data-stu-id="38a92-135">**Exclude topics by name**</span></span>

    ![Ausschließen von Themen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="38a92-137">(Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)</span><span class="sxs-lookup"><span data-stu-id="38a92-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="38a92-138">So schließen Sie Themen nach Namen aus</span><span class="sxs-lookup"><span data-stu-id="38a92-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="38a92-139">Wenn Sie Themen ausschließen müssen, laden Sie nach auswahl von Themen nach Name ausschließen die CSV-Vorlage herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten. </span><span class="sxs-lookup"><span data-stu-id="38a92-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

    <span data-ttu-id="38a92-141">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="38a92-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="38a92-142">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="38a92-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="38a92-143">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="38a92-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="38a92-144">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*</span><span class="sxs-lookup"><span data-stu-id="38a92-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="38a92-145">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="38a92-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="38a92-146">Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="38a92-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="38a92-147">**Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="38a92-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="38a92-148">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="38a92-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="38a92-149">Nachdem Sie die CSV-Datei abgeschlossen und gespeichert haben, wählen Sie **Durchsuchen** aus, um sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="38a92-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="38a92-150">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="38a92-150">Select **Next**.</span></span>

6. <span data-ttu-id="38a92-151">Auf der **Seite Wer kann Themen sehen und wo kann** sie angezeigt werden, konfigurieren Sie die Sichtbarkeit des Themas.</span><span class="sxs-lookup"><span data-stu-id="38a92-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="38a92-152">In der **Einstellung Themen** anzeigen können wählen Sie aus, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="38a92-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="38a92-153">Sie können wählen:</span><span class="sxs-lookup"><span data-stu-id="38a92-153">You can select:</span></span>
    - <span data-ttu-id="38a92-154">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="38a92-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="38a92-155">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="38a92-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="38a92-156">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="38a92-156">**No one**</span></span>

    ![Wer Kann Themen sehen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="38a92-158">Mit dieser Einstellung können Sie zwar beliebige Benutzer in Ihrer Organisation auswählen, aber nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, können Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38a92-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="38a92-159">Auf der **Seite Berechtigungen für die Themenverwaltung** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="38a92-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="38a92-160">Im Abschnitt **Wer kann Themen erstellen und** bearbeiten, können Sie folgende Auswahl auswählen:</span><span class="sxs-lookup"><span data-stu-id="38a92-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="38a92-161">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="38a92-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="38a92-162">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="38a92-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="38a92-163">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="38a92-163">**No one**</span></span>

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. <span data-ttu-id="38a92-165">Im Abschnitt **Wer kann Themen verwalten,** können Sie folgende Option auswählen:</span><span class="sxs-lookup"><span data-stu-id="38a92-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="38a92-166">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="38a92-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="38a92-167">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="38a92-167">**Only selected people or security groups**</span></span>

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="38a92-169">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="38a92-169">Select **Next**.</span></span>

9. <span data-ttu-id="38a92-170">Auf der **Seite Themencenter erstellen** können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="38a92-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="38a92-171">Geben Sie **im Feld** Websitename einen Namen für Ihr Themencenter ein.</span><span class="sxs-lookup"><span data-stu-id="38a92-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="38a92-172">Optional können Sie eine kurze Beschreibung in das Feld **Beschreibung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="38a92-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="38a92-173">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="38a92-173">Select **Next**.</span></span>

   ![Erstellen von Knowledge Center](../media/ksetup4.png)  

10. <span data-ttu-id="38a92-175">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="38a92-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="38a92-176">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="38a92-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="38a92-177">Die **aktivierte Seite "Viva Topics"** wird angezeigt, um zu bestätigen, dass das System nun mit der Analyse der ausgewählten Websites für Themen beginnt und die Themencenterwebsite erstellt.</span><span class="sxs-lookup"><span data-stu-id="38a92-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="38a92-178">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="38a92-178">Select **Done**.</span></span>

12. <span data-ttu-id="38a92-179">Sie werden an Ihre Seite Personen mit Wissen verbinden **zurückgegeben.**</span><span class="sxs-lookup"><span data-stu-id="38a92-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="38a92-180">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="38a92-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Angewendete Einstellungen](../media/ksetup7.png)    

<span data-ttu-id="38a92-182">Beachten Sie, dass es bei der ersten Aktivierung der Themenermittlung bis zu zwei Wochen dauern kann, bis alle vorgeschlagenen Themen in der Ansicht Themen verwalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="38a92-182">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="38a92-183">Die Themenermittlung wird fortgesetzt, wenn neue Inhalte oder Aktualisierungen von Inhalten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="38a92-183">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="38a92-184">Es ist normal, dass es Schwankungen bei der Anzahl vorgeschlagener Themen in Ihrer Organisation gibt, wenn Neue Informationen von Viva Topics ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="38a92-184">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="38a92-185">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="38a92-185">Assign licenses</span></span>

<span data-ttu-id="38a92-186">Nachdem Sie die Themenerfahrung konfiguriert haben, müssen Sie den Benutzern, die Themen verwenden, Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="38a92-186">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="38a92-187">Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und dem Themencenter anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38a92-187">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="38a92-188">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="38a92-188">To assign licenses:</span></span>

1. <span data-ttu-id="38a92-189">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="38a92-189">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="38a92-190">Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **Lizenzen und Apps**.</span><span class="sxs-lookup"><span data-stu-id="38a92-190">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="38a92-191">Wählen **Sie unter Lizenzen** die Option Viva Topics **aus.**</span><span class="sxs-lookup"><span data-stu-id="38a92-191">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="38a92-192">Stellen **Sie unter Apps** sicher, dass Graph Connectors Search with Index **(Viva Topics)** und Viva **Topics** beide ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="38a92-192">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38a92-193">![Microsoft Viva Topics-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="38a92-193">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="38a92-194">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="38a92-194">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="38a92-195">Verwalten von Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="38a92-195">Manage topic experiences</span></span>

<span data-ttu-id="38a92-196">Nachdem Sie Themen eingerichtet haben, können Sie die Einstellungen ändern, die Sie beim Setup im [Microsoft 365 Admin Center ausgewählt haben.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="38a92-196">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="38a92-197">Sehen Sie sich die folgenden Verweise an:</span><span class="sxs-lookup"><span data-stu-id="38a92-197">See the following references:</span></span>

- [<span data-ttu-id="38a92-198">Verwalten der Themensuche in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="38a92-198">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="38a92-199">Verwalten der Sichtbarkeit von Themen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="38a92-199">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="38a92-200">Verwalten von Themenberechtigungen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="38a92-200">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="38a92-201">Ändern des Namens des Themencenters in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="38a92-201">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="38a92-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38a92-202">See also</span></span>

[<span data-ttu-id="38a92-203">Übersicht über Die Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="38a92-203">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
