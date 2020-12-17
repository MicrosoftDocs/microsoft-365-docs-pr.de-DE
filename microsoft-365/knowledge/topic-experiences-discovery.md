---
title: Verwalten der Themen Ermittlung in Microsoft 365
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
description: Erfahren Sie, wie Sie die Themen Ermittlung in Microsoft 365 verwalten.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698543"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a><span data-ttu-id="70cf6-103">Verwalten der Themen Ermittlung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70cf6-103">Manage topic discovery in Microsoft 365</span></span>

<span data-ttu-id="70cf6-104">Sie können Themen Ermittlungs Einstellungen im [Microsoft 365 Admin Center](https://admin.microsoft.com)verwalten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="70cf6-105">Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="70cf6-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="70cf6-106">So greifen Sie auf Themen Verwaltungseinstellungen zu:</span><span class="sxs-lookup"><span data-stu-id="70cf6-106">To access topics management settings:</span></span>

1. <span data-ttu-id="70cf6-107">Klicken Sie im Microsoft 365 Admin Center auf **Einstellungen** und dann auf **org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="70cf6-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="70cf6-108">Klicken Sie auf der Registerkarte **Dienste** auf **Wissensnetzwerk**.</span><span class="sxs-lookup"><span data-stu-id="70cf6-108">On the **Services** tab, click **Knowledge network**.</span></span>

    ![Verbinden von Personen mit wissen](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="70cf6-110">Wählen Sie die Registerkarte **Thema Discovery** aus. In den folgenden Abschnitten finden Sie Informationen zu den einzelnen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![Wissen-Netzwerk-Einstellungen](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="70cf6-112">Auswählen von SharePoint-Themen Quellen</span><span class="sxs-lookup"><span data-stu-id="70cf6-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="70cf6-113">Sie können die SharePoint-Websites in Ihrer Organisation ändern, die nach Themen durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="70cf6-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="70cf6-114">Wenn Sie eine bestimmte Liste von Websites einschließen oder ausschließen möchten, können Sie die folgende CSV-Vorlage verwenden:</span><span class="sxs-lookup"><span data-stu-id="70cf6-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="70cf6-115">Wenn Sie Websites mithilfe der Websiteauswahl hinzufügen, werden Sie der vorhandenen Liste der einzuschließenden oder auszuschließenden Websites hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="70cf6-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="70cf6-116">Wenn Sie eine CSV-Datei hochladen, werden alle vorhandenen Listen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="70cf6-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="70cf6-117">Wenn Sie zuvor bestimmte Websites einbezogen oder ausgeschlossen haben, können Sie die Liste als CSV-Datei herunterladen, Änderungen vornehmen und die neue Liste hochladen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="70cf6-118">So wählen Sie Websites für die Themen Ermittlung aus</span><span class="sxs-lookup"><span data-stu-id="70cf6-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="70cf6-119">Wählen Sie auf der Registerkarte **Thema Discovery** unter **SharePoint-Themen Quellen auswählen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="70cf6-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="70cf6-120">Wählen Sie auf der Seite **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="70cf6-121">Hierzu zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="70cf6-121">This includes:</span></span>
    - <span data-ttu-id="70cf6-122">**Alle Websites**: alle SharePoint-Websites in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="70cf6-123">Dadurch werden aktuelle und zukünftige Websites erfasst.</span><span class="sxs-lookup"><span data-stu-id="70cf6-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="70cf6-124">**Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="70cf6-125">Sie können auch eine Liste der Websites hochladen, für die Sie die Ermittlung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="70cf6-126">In der Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="70cf6-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="70cf6-127">**Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="70cf6-128">Sie können auch eine Liste der Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-128">You can also upload a list of sites.</span></span> <span data-ttu-id="70cf6-129">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="70cf6-130">**Keine Websites**: Themen werden nicht automatisch generiert oder mit SharePoint-Inhalten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="70cf6-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="70cf6-131">Vorhandene Themen verbleiben im Themen Center.</span><span class="sxs-lookup"><span data-stu-id="70cf6-131">Existing topics remain in the topic center.</span></span>

    ![Screenshot der SharePoint-Themen Quellen-Benutzeroberfläche](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="70cf6-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="70cf6-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="70cf6-134">Themen nach Namen ausschließen</span><span class="sxs-lookup"><span data-stu-id="70cf6-134">Exclude topics by name</span></span>

<span data-ttu-id="70cf6-135">Sie können Themen aus der Ermittlung ausschließen, indem Sie eine Liste mithilfe einer CSV-Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="70cf6-136">Wenn Sie Themen zuvor ausgeschlossen haben, können Sie die CSV-Datei herunterladen, Änderungen vornehmen und erneut hochladen.</span><span class="sxs-lookup"><span data-stu-id="70cf6-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="70cf6-137">Wählen Sie auf der Registerkarte **Thema Discovery** unter **Themen ausschließen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="70cf6-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="70cf6-138">Klicken Sie auf **Themen nach Namen ausschließen**.</span><span class="sxs-lookup"><span data-stu-id="70cf6-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="70cf6-139">Wenn Sie eine Liste erstellen möchten, laden Sie die CSV-Vorlage herunter, und fügen Sie die auszuschließenden Themen hinzu (siehe *Arbeiten mit der CSV-Vorlage* unten).</span><span class="sxs-lookup"><span data-stu-id="70cf6-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="70cf6-140">Wenn die Datei verfügbar ist, klicken Sie auf **Durchsuchen** , und laden Sie die Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="70cf6-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="70cf6-141">Wenn eine Liste vorhanden ist, können Sie die CSV-Datei herunterladen, die die Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="70cf6-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="70cf6-142">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="70cf6-142">Click **Save**.</span></span>

    ![Screenshot der Benutzeroberfläche zum Ausschließen von Themen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="70cf6-144">Arbeiten mit der CSV-Vorlage</span><span class="sxs-lookup"><span data-stu-id="70cf6-144">Working with the .csv template</span></span>

<span data-ttu-id="70cf6-145">Sie können die CSV-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="70cf6-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="70cf6-146">Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:</span><span class="sxs-lookup"><span data-stu-id="70cf6-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="70cf6-147">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="70cf6-148">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="70cf6-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="70cf6-149">Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL*).</span><span class="sxs-lookup"><span data-stu-id="70cf6-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="70cf6-150">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="70cf6-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="70cf6-151">Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis*, *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur*, nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="70cf6-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="70cf6-152">**Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.</span><span class="sxs-lookup"><span data-stu-id="70cf6-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="70cf6-153">**MatchType-Exact/Partial**: Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.</span><span class="sxs-lookup"><span data-stu-id="70cf6-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Themen in CSV-Vorlage ausschließen](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="70cf6-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70cf6-155">See also</span></span>

[<span data-ttu-id="70cf6-156">Verwalten der Themen Sichtbarkeit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70cf6-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="70cf6-157">Verwalten von Themen Berechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70cf6-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="70cf6-158">Ändern des Namens des Themen Centers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70cf6-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
