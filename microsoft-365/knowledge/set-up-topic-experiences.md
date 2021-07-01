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
description: Erfahren Sie, wie Sie Microsoft Viva Topics einrichten
ms.openlocfilehash: 42f84b9b792907d7fe118e0b15c3767674ddf19b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229587"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="d4af8-103">Einrichten von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d4af8-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="d4af8-104">Sie können die Microsoft 365 Admin Center verwenden, um [Topics](topic-experiences-overview.md)einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d4af8-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="d4af8-105">Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="d4af8-106">Lesen Sie unbedingt ["Plan für Microsoft Viva Topics",](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="d4af8-107">Sie müssen [Viva Topics abonniert](https://www.microsoft.com/microsoft-viva/topics) haben und ein globaler Administrator oder SharePoint Administrator sein, um auf die Microsoft 365 Admin Center zugreifen und Topics einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="d4af8-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="d4af8-108">Wenn Sie SharePoint so konfiguriert haben, dass [verwaltete Geräte erforderlich](/sharepoint/control-access-from-unmanaged-devices)sind, müssen Sie Themen von einem verwalteten Gerät einrichten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d4af8-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="d4af8-109">Video demonstration</span></span>

<span data-ttu-id="d4af8-110">Dieses Video zeigt den Prozess zum Einrichten von Themen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4af8-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="d4af8-111">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="d4af8-111">Assign licenses</span></span>

<span data-ttu-id="d4af8-112">Sie müssen Lizenzen für die Benutzer zuweisen, die Topics verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="d4af8-113">Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und dem Themencenter sehen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="d4af8-114">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="d4af8-114">To assign licenses:</span></span>

1. <span data-ttu-id="d4af8-115">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d4af8-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="d4af8-116">Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **"Lizenzen und Apps".**</span><span class="sxs-lookup"><span data-stu-id="d4af8-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="d4af8-117">Wählen Sie unter **Lizenzen** **Viva Topics** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="d4af8-118">Stellen Sie unter **"Apps"** sicher, dass **Graph Connectors-Suche mit Index (Viva Topics)** und **Viva Topics** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="d4af8-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4af8-119">![Microsoft Viva Topics-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="d4af8-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="d4af8-120">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="d4af8-120">Click **Save changes**.</span></span>

<span data-ttu-id="d4af8-121">Es kann bis zu einer Stunde dauern, bis Benutzer zugriff auf Topics erhalten, nachdem die Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="d4af8-122">Einrichten von Themen</span><span class="sxs-lookup"><span data-stu-id="d4af8-122">Set up Topics</span></span>

> [!Note]
> <span data-ttu-id="d4af8-123">Wenn die Themensuche zum ersten Mal aktiviert ist, kann es bis zu zwei Wochen dauern, bis alle vorgeschlagenen Themen in der Ansicht "Themen verwalten" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-123">The first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="d4af8-124">Die Themensuche wird fortgesetzt, wenn neue Inhalte oder Aktualisierungen an Inhalten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-124">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="d4af8-125">Es ist normal, dass die Anzahl der vorgeschlagenen Themen in Ihrer Organisation Schwankungen aufweist, wenn Viva Topics neue Informationen auswertet.</span><span class="sxs-lookup"><span data-stu-id="d4af8-125">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

<span data-ttu-id="d4af8-126">So richten Sie Themen ein</span><span class="sxs-lookup"><span data-stu-id="d4af8-126">To set up Topics</span></span>
1. <span data-ttu-id="d4af8-127">Wählen Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com) **setup** aus, und zeigen Sie dann den Abschnitt **"Dateien und Inhalt"** an.</span><span class="sxs-lookup"><span data-stu-id="d4af8-127">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="d4af8-128">Klicken Sie im Abschnitt **"Dateien und Inhalt"** auf **Verbinden Personen wissen.**</span><span class="sxs-lookup"><span data-stu-id="d4af8-128">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Verbinden Von Personen zu Wissen](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="d4af8-130">Klicken Sie auf der **Seite Verbinden Personen zu Wissen** auf **"Erste Schritte",** um Sie durch den Einrichtungsprozess zu führen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-130">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Erste Schritte](../media/k-get-started.png) 

4. <span data-ttu-id="d4af8-132">Auf der Seite **"Auswählen, wie Viva Topics Themen finden kann"** konfigurieren Sie die Themensuche.</span><span class="sxs-lookup"><span data-stu-id="d4af8-132">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="d4af8-133">Wählen Sie im Abschnitt **"SharePoint Themenquellen auswählen"** aus, welche SharePoint Websites während der Suche als Quellen für Ihre Themen durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-133">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="d4af8-134">Wählen Sie zwischen:</span><span class="sxs-lookup"><span data-stu-id="d4af8-134">Choose from:</span></span>
    - <span data-ttu-id="d4af8-135">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d4af8-135">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="d4af8-136">Dies schließt aktuelle und zukünftige Websites ein.</span><span class="sxs-lookup"><span data-stu-id="d4af8-136">This includes current and future sites.</span></span>
    - <span data-ttu-id="d4af8-137">**Alle, außer ausgewählten Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-137">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="d4af8-138">Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-138">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="d4af8-139">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-139">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="d4af8-140">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-140">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="d4af8-141">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-141">You can also upload a list of sites.</span></span> <span data-ttu-id="d4af8-142">Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-142">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="d4af8-143">**Keine Websites**: Schließen Sie keine SharePoint-Websites ein.</span><span class="sxs-lookup"><span data-stu-id="d4af8-143">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Auswählen, wie Themen gesucht werden sollen](../media/ksetup1.png) 
   
5. <span data-ttu-id="d4af8-145">Im Abschnitt **"Themen nach Namen ausschließen"** können Sie Namen von Themen hinzufügen, die Sie von der Themensuche ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-145">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="d4af8-146">Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-146">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="d4af8-147">Mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="d4af8-147">The options are:</span></span>
    - <span data-ttu-id="d4af8-148">**Themen nicht ausschließen**</span><span class="sxs-lookup"><span data-stu-id="d4af8-148">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="d4af8-149">**Ausschließen von Themen nach Name**</span><span class="sxs-lookup"><span data-stu-id="d4af8-149">**Exclude topics by name**</span></span>

    ![Themen ausschließen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="d4af8-151">(Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)</span><span class="sxs-lookup"><span data-stu-id="d4af8-151">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="d4af8-152">Ausschließen von Themen nach Namen</span><span class="sxs-lookup"><span data-stu-id="d4af8-152">How to exclude topics by name</span></span>    

    <span data-ttu-id="d4af8-153">Wenn Sie Themen ausschließen müssen, laden Sie nach dem Auswählen **von "Themen ausschließen" anhand des Namens** die vorlage .csv herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-153">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Ausschließen von Themen in csv-Vorlage](../media/exclude-topics-csv.png) 

    <span data-ttu-id="d4af8-155">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="d4af8-155">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="d4af8-156">**Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4af8-156">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="d4af8-157">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="d4af8-157">There are two ways to do this:</span></span>
        - <span data-ttu-id="d4af8-158">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (z. B. *Contoso* oder *ATL).*</span><span class="sxs-lookup"><span data-stu-id="d4af8-158">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="d4af8-159">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-159">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="d4af8-160">Beispielsweise schließt *Arc* alle Themen mit dem Wort *Bogen* aus, z. B. *Arc Circle,* *Arc Arc-* oder *Training Arc.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. *Architektur,* nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d4af8-160">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="d4af8-161">**Steht für (optional):** Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="d4af8-161">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="d4af8-162">**MatchType-Exact/Partial:** Geben Sie an, ob der eingegebene Name ein *exakter* oder *teilweiser* Übereinstimmungstyp war.</span><span class="sxs-lookup"><span data-stu-id="d4af8-162">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="d4af8-163">Nachdem Sie Die .csv-Datei abgeschlossen und gespeichert haben, wählen Sie **"Durchsuchen"** aus, um sie zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-163">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="d4af8-164">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-164">Select **Next**.</span></span>

6. <span data-ttu-id="d4af8-165">Auf der **Wer Themen anzeigen können und wo diese angezeigt** werden, konfigurieren Sie die Themensichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d4af8-165">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="d4af8-166">In der Wer die **Themeneinstellung anzeigen können,** wählen Sie aus, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-166">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="d4af8-167">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="d4af8-167">You can select:</span></span>
    - <span data-ttu-id="d4af8-168">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="d4af8-168">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d4af8-169">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="d4af8-169">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d4af8-170">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="d4af8-170">**No one**</span></span>

    ![Wer können Themen anzeigen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="d4af8-172">Mit dieser Einstellung können Sie zwar einen beliebigen Benutzer in Ihrer Organisation auswählen, aber nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, können Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-172">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="d4af8-173">Auf der Seite **"Berechtigungen für die Themenverwaltung"** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="d4af8-173">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="d4af8-174">In the **Wer can create and edit topics** section, you can select:</span><span class="sxs-lookup"><span data-stu-id="d4af8-174">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="d4af8-175">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="d4af8-175">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d4af8-176">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="d4af8-176">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="d4af8-177">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="d4af8-177">**No one**</span></span>

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. <span data-ttu-id="d4af8-179">In the **Wer can manage topics** section, you can select:</span><span class="sxs-lookup"><span data-stu-id="d4af8-179">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="d4af8-180">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="d4af8-180">**Everyone in my organization**</span></span>
    - <span data-ttu-id="d4af8-181">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="d4af8-181">**Only selected people or security groups**</span></span>

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="d4af8-183">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-183">Select **Next**.</span></span>

9. <span data-ttu-id="d4af8-184">Auf der Seite **"Themencenter** erstellen" können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="d4af8-184">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="d4af8-185">Geben Sie im **Feld "Websitename"** einen Namen für Ihr Themencenter ein.</span><span class="sxs-lookup"><span data-stu-id="d4af8-185">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="d4af8-186">Sie können auf das Stiftsymbol klicken, wenn Sie die URL ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d4af8-186">You can click the pencil icon if you want to change the URL.</span></span> <span data-ttu-id="d4af8-187">Geben Sie optional eine kurze Beschreibung in das **Feld Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="d4af8-187">Optionally, type a short description in the **Description** box.</span></span> 

   > [!Important]
   > <span data-ttu-id="d4af8-188">Sie können den Websitenamen später ändern, aber sie können die URL nach Abschluss des Assistenten nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="d4af8-188">You can change the site name later, but you can't change the URL after you complete the wizard.</span></span>

   <span data-ttu-id="d4af8-189">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-189">Select **Next**.</span></span>

   ![Erstellen des Wissenscenters](../media/ksetup4.png)  

10. <span data-ttu-id="d4af8-191">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-191">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="d4af8-192">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-192">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="d4af8-193">Die **aktivierte** Viva Topics-Seite wird angezeigt und bestätigt, dass das System nun mit der Analyse Ihrer ausgewählten Websites für Themen und dem Erstellen der Themencenterwebsite beginnt.</span><span class="sxs-lookup"><span data-stu-id="d4af8-193">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="d4af8-194">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="d4af8-194">Select **Done**.</span></span>

12. <span data-ttu-id="d4af8-195">Sie werden zu Ihrer **Verbinden Seite "Personen zu Wissen"** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d4af8-195">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="d4af8-196">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d4af8-196">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![angewendete Einstellungen](../media/ksetup7.png)    

## <a name="manage-topic-experiences"></a><span data-ttu-id="d4af8-198">Verwalten von Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="d4af8-198">Manage topic experiences</span></span>

<span data-ttu-id="d4af8-199">Nachdem Sie Topics eingerichtet haben, können Sie die Einstellungen ändern, die Sie während der Einrichtung im [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="d4af8-199">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="d4af8-200">Sehen Sie sich die folgenden Verweise an:</span><span class="sxs-lookup"><span data-stu-id="d4af8-200">See the following references:</span></span>

- [<span data-ttu-id="d4af8-201">Verwalten der Themensuche in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d4af8-201">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="d4af8-202">Verwalten der Sichtbarkeit von Themen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d4af8-202">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="d4af8-203">Verwalten von Themenberechtigungen in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d4af8-203">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="d4af8-204">Ändern des Namens des Themencenters in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="d4af8-204">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="d4af8-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4af8-205">See also</span></span>

[<span data-ttu-id="d4af8-206">Übersicht über Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="d4af8-206">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
