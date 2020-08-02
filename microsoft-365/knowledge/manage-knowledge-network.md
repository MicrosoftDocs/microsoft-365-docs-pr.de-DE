---
title: 'Verwalten Ihres Wissens Verwaltungsnetzwerks (Vorschau) '
description: Einrichten der Wissensverwaltung
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540118"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="f0135-103">Verwalten Ihres Wissens Verwaltungsnetzwerks (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f0135-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="f0135-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="f0135-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f0135-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f0135-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="f0135-106">Nachdem Sie das [Knowledge Management eingerichtet](set-up-knowledge-network.md)haben, kann ein Administrator zu jeder Zeit Anpassungen an Ihren Konfigurationseinstellungen über das Microsoft 365 Admin Center vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f0135-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f0135-107">Beispielsweise müssen Sie die Einstellungen für Folgendes anpassen:</span><span class="sxs-lookup"><span data-stu-id="f0135-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="f0135-108">Hinzufügen von neuen SharePoint-Quellen zu Minen Themen.</span><span class="sxs-lookup"><span data-stu-id="f0135-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="f0135-109">Ändern der Benutzer, die auf Themen zugreifen können</span><span class="sxs-lookup"><span data-stu-id="f0135-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="f0135-110">Ändern Sie, welche Benutzerberechtigungen für Aufgaben im Themen Center haben.</span><span class="sxs-lookup"><span data-stu-id="f0135-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="f0135-111">Ändern des Namens Ihres Themen Centers</span><span class="sxs-lookup"><span data-stu-id="f0135-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="f0135-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0135-112">Requirements</span></span> 
<span data-ttu-id="f0135-113">Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und organisatorische Wissens Aufgaben verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="f0135-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="f0135-114">So greifen Sie auf Wissens Verwaltungseinstellungen zu:</span><span class="sxs-lookup"><span data-stu-id="f0135-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="f0135-115">Wählen Sie im Microsoft 365 Admin Center die Option **Setup**aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.</span><span class="sxs-lookup"><span data-stu-id="f0135-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="f0135-116">Klicken Sie im Abschnitt **organisatorisches Wissen** auf **Personen mit Wissen verbinden**.</span><span class="sxs-lookup"><span data-stu-id="f0135-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Verbinden von Personen mit wissen](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="f0135-118">Wählen Sie auf der Seite mit den **Informationen zum Benutzer verbinden** die Option **Manage** aus, um den Bereich **Wissensnetzwerk Einstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f0135-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![Wissen-Netzwerk-Einstellungen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="f0135-120">Ändern, wie das Wissensnetzwerk Themen finden kann</span><span class="sxs-lookup"><span data-stu-id="f0135-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="f0135-121">Wählen Sie die Registerkarte **Thema Ermittlung** aus, wenn Sie Ihre Auswahlmöglichkeiten für SharePoint-Themen Quellen aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="f0135-122">Mit dieser Einstellung können Sie die SharePoint-Websites in Ihrem Mandanten auswählen, die durchforstet und für Themen abgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="f0135-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="f0135-123">Wählen Sie auf der Registerkarte **Thema Discovery** unter **SharePoint-Themen Quellen auswählen**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="f0135-124">Wählen Sie auf der Seite **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0135-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="f0135-125">Hierzu zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="f0135-125">This includes:</span></span></br>
    <span data-ttu-id="f0135-126">a.</span><span class="sxs-lookup"><span data-stu-id="f0135-126">a.</span></span> <span data-ttu-id="f0135-127">**Alle Websites**: alle SharePoint-Websites in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f0135-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="f0135-128">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="f0135-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="f0135-129">b.</span><span class="sxs-lookup"><span data-stu-id="f0135-129">b.</span></span> <span data-ttu-id="f0135-130">**Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="f0135-131">Sie können auch eine Liste der Websites hochladen, für die Sie die Ermittlung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="f0135-132">In der Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f0135-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="f0135-133">c.</span><span class="sxs-lookup"><span data-stu-id="f0135-133">c.</span></span> <span data-ttu-id="f0135-134">**Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="f0135-135">Sie können auch eine Liste der Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="f0135-135">You can also upload a list of sites.</span></span> <span data-ttu-id="f0135-136">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="f0135-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Auswählen der Suche nach Themen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="f0135-138">Wenn Sie über eine Reihe von Websites verfügen, die Sie ausschließen möchten (wenn Sie **Alle auswählen, außer ausgewählte Websites**) oder einbeziehen (wenn Sie **nur ausgewählte Websites**ausgewählt haben), können Sie eine CSV-Datei mit den Websitenamen und-URLs hochladen.</span><span class="sxs-lookup"><span data-stu-id="f0135-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="f0135-139">Sie können die Option **Download Site Template. CSV** auswählen, wenn Sie die CSV-Vorlagendatei verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="f0135-140">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="f0135-141">Ändern der Personen, die Themen in Ihrer Organisation anzeigen können</span><span class="sxs-lookup"><span data-stu-id="f0135-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="f0135-142">Wählen Sie die Registerkarte **Thema Ermittlung** aus, wenn Sie aktualisieren möchten, wer in Ihrer Organisation entdeckte Themen in Suchergebnissen sehen kann und wann Themen in Inhalten wie SharePoint-Seiten hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="f0135-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="f0135-143">Wählen Sie auf der Registerkarte **Thema Discovery** unter **wer Themen im Wissensnetzwerk anzeigen kann die**Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="f0135-144">Auf der Seite " **Wer kann Themen auf der Wissensnetzwerk Seite sehen** " wählen Sie aus, wer Zugriff auf Themen Details haben soll, wie beispielsweise hervorgehobene Themen, Themenkarten, Themen Antworten auf der Suche und Themenseiten.</span><span class="sxs-lookup"><span data-stu-id="f0135-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="f0135-145">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="f0135-145">You can select:</span></span></br>
    <span data-ttu-id="f0135-146">a.</span><span class="sxs-lookup"><span data-stu-id="f0135-146">a.</span></span> <span data-ttu-id="f0135-147">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="f0135-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f0135-148">b.</span><span class="sxs-lookup"><span data-stu-id="f0135-148">b.</span></span> <span data-ttu-id="f0135-149">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="f0135-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="f0135-150">c.</span><span class="sxs-lookup"><span data-stu-id="f0135-150">c.</span></span> <span data-ttu-id="f0135-151">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="f0135-151">**No one**</span></span></br>

    ![Wer Themen sehen kann](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="f0135-153">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="f0135-154">Während Sie mit dieser Einstellung einen beliebigen Benutzer in Ihrer Organisation auswählen können, können nur Benutzer, denen Lizenzen für Wissensmanagement zugewiesen sind, Themen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0135-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="f0135-155">Ändern der Berechtigungen für Aufgaben im Themen Center</span><span class="sxs-lookup"><span data-stu-id="f0135-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="f0135-156">Wählen Sie die Registerkarte **Thema Berechtigungen** aus, wenn Sie aktualisieren möchten, wer über Berechtigungen für Folgendes auf der Seite "Themen Center" verfügt:</span><span class="sxs-lookup"><span data-stu-id="f0135-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="f0135-157">Die Benutzer können Themen erstellen und bearbeiten: Erstellen Sie neue Themen, die während der Suche nicht gefunden wurden, oder bearbeiten Sie vorhandene Themenseiten Details.</span><span class="sxs-lookup"><span data-stu-id="f0135-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="f0135-158">Welche Benutzer Themen verwalten können: bestätigen oder ablehnen erkannter Themen.</span><span class="sxs-lookup"><span data-stu-id="f0135-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="f0135-159">So aktualisieren Sie die Benutzer, die Berechtigungen zum Erstellen und Bearbeiten von Themen haben:</span><span class="sxs-lookup"><span data-stu-id="f0135-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="f0135-160">Wählen Sie auf der Registerkarte **Thema Berechtigungen** unter **Wer kann Themen erstellen und bearbeiten**aus die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="f0135-161">Auf der Seite für die **Erstellung und Bearbeitung von Themen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="f0135-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="f0135-162">a.</span><span class="sxs-lookup"><span data-stu-id="f0135-162">a.</span></span> <span data-ttu-id="f0135-163">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="f0135-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f0135-164">b.</span><span class="sxs-lookup"><span data-stu-id="f0135-164">b.</span></span> <span data-ttu-id="f0135-165">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="f0135-165">**Only selected people or security groups**</span></span></br>

    ![Erstellen und Bearbeiten von Themen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="f0135-167">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-167">Select **Save**.</span></span></br>

<span data-ttu-id="f0135-168">So aktualisieren Sie, wer über Berechtigungen zum Verwalten von Themen verfügt:</span><span class="sxs-lookup"><span data-stu-id="f0135-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="f0135-169">Wählen Sie auf der Registerkarte **Thema Berechtigungen** unter **Benutzer können Themen verwalten die**Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="f0135-170">Auf der Seite **Themen, die Themen verwalten können** , können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="f0135-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="f0135-171">a.</span><span class="sxs-lookup"><span data-stu-id="f0135-171">a.</span></span> <span data-ttu-id="f0135-172">**Jeder in Ihrer Organisation**</span><span class="sxs-lookup"><span data-stu-id="f0135-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="f0135-173">b.</span><span class="sxs-lookup"><span data-stu-id="f0135-173">b.</span></span> <span data-ttu-id="f0135-174">**Ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="f0135-174">**Selected people or security groups**</span></span></br>

    ![Verwalten von Themen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="f0135-176">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="f0135-177">Aktualisieren des Namens des Themen Centers</span><span class="sxs-lookup"><span data-stu-id="f0135-177">Update your topic center name</span></span>

<span data-ttu-id="f0135-178">Wählen Sie die Registerkarte **Topic Center** aus, wenn Sie den Namen Ihres Themen Centers aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0135-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="f0135-179">Wählen Sie auf der Registerkarte **Themen Center** unter **Name des Themas**" **Bearbeiten**" aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="f0135-180">Geben Sie auf der Seite **Themen Center Namen bearbeiten** im Feld **Themen Center Name** den neuen Namen für Ihr Themen Center ein.</span><span class="sxs-lookup"><span data-stu-id="f0135-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="f0135-181">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f0135-181">Select **Save**</span></span>

    ![Bearbeiten des Themen Center namens](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="f0135-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0135-183">See also</span></span>



  






