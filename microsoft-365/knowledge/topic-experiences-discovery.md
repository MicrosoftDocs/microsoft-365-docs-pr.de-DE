---
title: Verwalten der Themensuche in Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie die Themenerkennung in Microsoft Viva Topics verwalten.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768974"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="14aea-103">Verwalten der Themensuche in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="14aea-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="14aea-104">Sie können die Themenermittlungseinstellungen im [Microsoft 365 verwalten.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="14aea-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="14aea-105">Sie müssen ein globaler Administrator oder ein SharePoint sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="14aea-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="14aea-106">So greifen Sie auf die Themenverwaltungseinstellungen zu:</span><span class="sxs-lookup"><span data-stu-id="14aea-106">To access topics management settings:</span></span>

1. <span data-ttu-id="14aea-107">Klicken Sie Microsoft 365 Admin Center **auf Einstellungen**, und dann auf **Organisationseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="14aea-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="14aea-108">Klicken Sie **auf der** Registerkarte Dienste auf **Themenerfahrungen**.</span><span class="sxs-lookup"><span data-stu-id="14aea-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Verbinden personen zum Wissen](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="14aea-110">Wählen Sie die **Registerkarte Themaermittlung** aus. Informationen zu den einzelnen Einstellungen finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="14aea-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="14aea-112">Auswählen SharePoint Themenquellen</span><span class="sxs-lookup"><span data-stu-id="14aea-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="14aea-113">Sie können die SharePoint in Ihrer Organisation ändern, die nach Themen durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="14aea-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="14aea-114">Wenn Sie eine bestimmte Liste von Websites hinzufügen oder ausschließen möchten, können Sie die folgende Vorlage .csv verwenden:</span><span class="sxs-lookup"><span data-stu-id="14aea-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="14aea-115">Wenn Sie Websites mithilfe der Websiteauswahl hinzufügen, werden diese zur vorhandenen Liste der Websites hinzugefügt, die ein- oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14aea-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="14aea-116">Wenn Sie eine CSV-Datei hochladen, werden alle vorhandenen Listen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="14aea-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="14aea-117">Wenn Sie zuvor bestimmte Websites eingeschlossen oder ausgeschlossen haben, laden Sie die Liste als .csv herunter, nehmen Änderungen vor und laden die neue Liste hoch.</span><span class="sxs-lookup"><span data-stu-id="14aea-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="14aea-118">So wählen Sie Websites für die Themenerkennung aus</span><span class="sxs-lookup"><span data-stu-id="14aea-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="14aea-119">Wählen Sie auf der Registerkarte **Themensuche** unter **SharePoint-Themenquellen auswählen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="14aea-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="14aea-120">Wählen Sie **auf SharePoint** Seite Quellen auswählen aus, SharePoint Websites während der Suche als Quellen für Ihre Themen durchforstet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14aea-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="14aea-121">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="14aea-121">This includes:</span></span>
    - <span data-ttu-id="14aea-122">**Alle Websites**: Alle SharePoint in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="14aea-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="14aea-123">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="14aea-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="14aea-124">**Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="14aea-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="14aea-125">Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="14aea-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="14aea-126">Zukünftig erstellte Websites werden als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="14aea-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="14aea-127">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="14aea-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="14aea-128">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="14aea-128">You can also upload a list of sites.</span></span> <span data-ttu-id="14aea-129">Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="14aea-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="14aea-130">**Keine Websites:** Themen werden nicht automatisch generiert oder mit inhalten SharePoint aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="14aea-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="14aea-131">Vorhandene Themen verbleiben im Themencenter.</span><span class="sxs-lookup"><span data-stu-id="14aea-131">Existing topics remain in the topic center.</span></span>

    ![Screenshot der SharePoint der Benutzeroberfläche von Themenquellen](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="14aea-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14aea-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="14aea-134">Ausschließen von Themen nach Name</span><span class="sxs-lookup"><span data-stu-id="14aea-134">Exclude topics by name</span></span>

<span data-ttu-id="14aea-135">Sie können Themen von der Suche ausschließen, indem Sie eine Liste mithilfe einer CSV-Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="14aea-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="14aea-136">Wenn Sie zuvor Themen ausgeschlossen haben, können Sie die CSV-Datei herunterladen, Änderungen vornehmen und sie erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="14aea-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="14aea-137">Wählen Sie auf der Registerkarte **Themensuche** unter **Themen ausschließen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="14aea-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="14aea-138">Klicken **Sie auf Themen nach Name ausschließen**.</span><span class="sxs-lookup"><span data-stu-id="14aea-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="14aea-139">Wenn Sie eine Liste erstellen müssen, laden Sie die Vorlage .csv herunter, und fügen Sie die Themen hinzu, die Sie ausschließen möchten (siehe Arbeiten mit .csv *Vorlage* unten).</span><span class="sxs-lookup"><span data-stu-id="14aea-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="14aea-140">Wenn die Datei bereit ist, klicken Sie auf **Durchsuchen** und laden Sie die Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="14aea-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="14aea-141">Wenn eine Liste vorhanden ist, können Sie die .csv liste herunterladen.</span><span class="sxs-lookup"><span data-stu-id="14aea-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="14aea-142">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14aea-142">Click **Save**.</span></span>

    ![Screenshot der Benutzeroberfläche für Ausgeschlossene Themen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="14aea-144">Arbeiten mit der .csv Vorlage</span><span class="sxs-lookup"><span data-stu-id="14aea-144">Working with the .csv template</span></span>

<span data-ttu-id="14aea-145">Sie können die folgende CSV-Vorlage kopieren:</span><span class="sxs-lookup"><span data-stu-id="14aea-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="14aea-146">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="14aea-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="14aea-147">**Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="14aea-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="14aea-148">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="14aea-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="14aea-149">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym ausschließen (z. B. *Contoso* oder *ATL*).</span><span class="sxs-lookup"><span data-stu-id="14aea-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="14aea-150">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="14aea-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="14aea-151">Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="14aea-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="14aea-152">**Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="14aea-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="14aea-153">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="14aea-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="14aea-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14aea-155">See also</span></span>

[<span data-ttu-id="14aea-156">Verwalten der Thementransparenz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14aea-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="14aea-157">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14aea-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="14aea-158">Ändern Sie den Namen des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14aea-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
