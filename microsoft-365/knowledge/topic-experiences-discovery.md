---
title: Verwalten der Themenermittlung in Microsoft -Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie die Themenermittlung in Microsoft Topics verwalten.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107759"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="4db63-103">Verwalten der Themenermittlung in Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="4db63-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="4db63-104">Sie können Die Themenermittlungseinstellungen im [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4db63-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="4db63-105">Sie müssen ein globaler Administrator oder ein SharePoint-Administrator sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4db63-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="4db63-106">So greifen Sie auf Die Themenverwaltungseinstellungen zu:</span><span class="sxs-lookup"><span data-stu-id="4db63-106">To access topics management settings:</span></span>

1. <span data-ttu-id="4db63-107">Klicken Sie im Microsoft 365 Admin Center auf **"Einstellungen"** und dann auf **"Organisationseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="4db63-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="4db63-108">Klicken Sie **auf der** Registerkarte "Dienste" auf **"Themenerfahrungen".**</span><span class="sxs-lookup"><span data-stu-id="4db63-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Verbinden von Personen mit Wissen](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="4db63-110">Wählen Sie die **Registerkarte "Themenermittlung"** aus. Informationen zu den einzelnen Einstellungen finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="4db63-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="4db63-112">Auswählen von SharePoint-Themenquellen</span><span class="sxs-lookup"><span data-stu-id="4db63-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="4db63-113">Sie können die SharePoint-Websites in Ihrer Organisation ändern, die nach Themen gecrawlt werden.</span><span class="sxs-lookup"><span data-stu-id="4db63-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="4db63-114">Wenn Sie eine bestimmte Liste von Websites ein- oder ausschließen möchten, können Sie die folgende .csv-Vorlage verwenden:</span><span class="sxs-lookup"><span data-stu-id="4db63-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="4db63-115">Wenn Sie Websites mithilfe der Websiteauswahl hinzufügen, werden sie der vorhandenen Liste der Websites hinzugefügt, die ein- oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4db63-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="4db63-116">Wenn Sie eine CSV-Datei hochladen, werden alle vorhandenen Listen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="4db63-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="4db63-117">Wenn Sie zuvor bestimmte Websites eingeschlossen oder ausgeschlossen haben, laden Sie die Liste als CSV-Datei herunter, nehmen Sie Änderungen vor, und laden Sie die neue Liste hoch.</span><span class="sxs-lookup"><span data-stu-id="4db63-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="4db63-118">So wählen Sie Websites für die Themenermittlung aus</span><span class="sxs-lookup"><span data-stu-id="4db63-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="4db63-119">Wählen Sie **auf der Registerkarte "Themenermittlung"** unter **"SharePoint-Themenquellen auswählen"** die Option **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="4db63-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="4db63-120">Wählen Sie **auf der Seite "SharePoint-Themenquellen** auswählen" aus, welche SharePoint-Websites während der Suche als Quellen für Ihre Themen durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="4db63-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4db63-121">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4db63-121">This includes:</span></span>
    - <span data-ttu-id="4db63-122">**Alle Websites:** Alle SharePoint-Websites in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4db63-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="4db63-123">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="4db63-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="4db63-124">**Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="4db63-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4db63-125">Sie können auch eine Liste der Websites hochladen, für die Sie die Suche abmelden möchten.</span><span class="sxs-lookup"><span data-stu-id="4db63-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="4db63-126">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="4db63-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="4db63-127">**Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten.</span><span class="sxs-lookup"><span data-stu-id="4db63-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4db63-128">Sie können auch eine Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="4db63-128">You can also upload a list of sites.</span></span> <span data-ttu-id="4db63-129">Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="4db63-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="4db63-130">**Keine Websites:** Themen werden nicht automatisch generiert oder mit SharePoint-Inhalten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4db63-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="4db63-131">Vorhandene Themen verbleiben im Themencenter.</span><span class="sxs-lookup"><span data-stu-id="4db63-131">Existing topics remain in the topic center.</span></span>

    ![Screenshot der Benutzeroberfläche für SharePoint-Themenquellen](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="4db63-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4db63-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="4db63-134">Ausschließen von Themen nach Namen</span><span class="sxs-lookup"><span data-stu-id="4db63-134">Exclude topics by name</span></span>

<span data-ttu-id="4db63-135">Sie können Themen von der Suche ausschließen, indem Sie eine Liste mithilfe einer CSV-Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="4db63-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="4db63-136">Wenn Sie zuvor Themen ausgeschlossen haben, können Sie die CSV herunterladen, Änderungen vornehmen und sie erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="4db63-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="4db63-137">Wählen Sie **auf der Registerkarte "Themenermittlung"** unter **"Themen ausschließen"** die Option **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="4db63-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="4db63-138">Klicken **Sie auf "Themen nach Namen ausschließen".**</span><span class="sxs-lookup"><span data-stu-id="4db63-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="4db63-139">Wenn Sie eine Liste erstellen müssen, laden Sie die .csv-Vorlage herunter, und fügen Sie die Themen hinzu, die Sie ausschließen möchten (siehe "Arbeiten mit der *CSV-Vorlage"* weiter unten).</span><span class="sxs-lookup"><span data-stu-id="4db63-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="4db63-140">Wenn die Datei bereit ist, klicken Sie auf **"Durchsuchen",** und laden Sie die Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="4db63-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="4db63-141">Wenn eine Liste vorhanden ist, können Sie die CSV herunterladen, die die Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="4db63-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="4db63-142">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4db63-142">Click **Save**.</span></span>

    ![Screenshot der Benutzeroberfläche "Themen ausschließen"](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="4db63-144">Arbeiten mit der .csv-Vorlage</span><span class="sxs-lookup"><span data-stu-id="4db63-144">Working with the .csv template</span></span>

<span data-ttu-id="4db63-145">Sie können die folgende CSV-Vorlage kopieren:</span><span class="sxs-lookup"><span data-stu-id="4db63-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="4db63-146">Geben Sie in der Csv-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="4db63-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="4db63-147">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="4db63-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4db63-148">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="4db63-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="4db63-149">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) verwenden.*</span><span class="sxs-lookup"><span data-stu-id="4db63-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="4db63-150">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4db63-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4db63-151">Der Bogen *schließt* z. B. alle Themen aus, *in* denen der Wortbogen enthalten ist, z. B. Bogenkreis,  *Arkusbogen* oder *Schulungsbogen.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="4db63-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="4db63-152">**Steht für (optional):** Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="4db63-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="4db63-153">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein *exakter* oder teilweiser *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="4db63-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="4db63-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db63-155">See also</span></span>

[<span data-ttu-id="4db63-156">Verwalten der Sichtbarkeit von Themen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4db63-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="4db63-157">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4db63-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="4db63-158">Ändern des Namens des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4db63-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
