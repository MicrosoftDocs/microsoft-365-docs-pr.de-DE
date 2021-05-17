---
title: Planen von Microsoft Viva-Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informationen zum Planen von Plan for Microsoft Viva Topics
ms.openlocfilehash: d64e4b341fe96d7aa3636f58bffe3dd8f388838e
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957539"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="e8b75-103">Planen von Microsoft Viva-Themen</span><span class="sxs-lookup"><span data-stu-id="e8b75-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="e8b75-104">Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e8b75-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="e8b75-105">Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und dass sie über die richtigen Berechtigungen zum Nutzen und Zum Beitragen von Wissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="e8b75-106">In diesem Artikel werden die folgenden Planungsentscheidungen untersucht:</span><span class="sxs-lookup"><span data-stu-id="e8b75-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="e8b75-107">Welche SharePoint Sie nach Themen durchforsten möchten</span><span class="sxs-lookup"><span data-stu-id="e8b75-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="e8b75-108">Welche Themen Sie von den Themenerfahrungen ausschließen möchten, falls dies der Fall ist</span><span class="sxs-lookup"><span data-stu-id="e8b75-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="e8b75-109">Für welche Benutzer Sie Themen sichtbar machen möchten</span><span class="sxs-lookup"><span data-stu-id="e8b75-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="e8b75-110">Welche Benutzer Sie berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="e8b75-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="e8b75-111">Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="e8b75-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="e8b75-112">Welchen Namen möchten Sie Ihrem Themencenter geben?</span><span class="sxs-lookup"><span data-stu-id="e8b75-112">What name you want to give your topic center</span></span>

<span data-ttu-id="e8b75-113">Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und die Themenerfahrung gewährt Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben.</span><span class="sxs-lookup"><span data-stu-id="e8b75-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="e8b75-114">Es wird empfohlen, im Rahmen Ihres Planungsprozesses auch Die Sicherheit und den Datenschutz von [Microsoft Viva Topics](topic-experiences-security-privacy.md) zu lesen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8b75-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8b75-115">Requirements</span></span>

<span data-ttu-id="e8b75-116">Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="e8b75-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="e8b75-117">Alle Benutzer, die Themen verwenden möchten, benötigen eine **Topic Experiences-Lizenz.**</span><span class="sxs-lookup"><span data-stu-id="e8b75-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="e8b75-118">Zuweisen von Lizenzen finden Sie unter [Einrichten von Microsoft Viva Topics](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="e8b75-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="e8b75-119">Themasuche</span><span class="sxs-lookup"><span data-stu-id="e8b75-119">Topic discovery</span></span>

<span data-ttu-id="e8b75-120">Die Einstellungen für die Themensuche geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8b75-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="e8b75-121">Sie können wählen, ob Sie alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="e8b75-122">Es wird empfohlen, alle Websites zu wählen, damit themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.</span><span class="sxs-lookup"><span data-stu-id="e8b75-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="e8b75-123">Wenn Sie Topics einrichten, können Sie unter folgenden Optionen wählen:</span><span class="sxs-lookup"><span data-stu-id="e8b75-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="e8b75-124">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8b75-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="e8b75-125">Dies schließt aktuelle und zukünftige Websites ein.</span><span class="sxs-lookup"><span data-stu-id="e8b75-125">This includes current and future sites.</span></span>
- <span data-ttu-id="e8b75-126">**Alle, mit Ausnahme von ausgewählten Websites**: Alle Websites mit Ausnahme der von Ihnen angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="e8b75-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="e8b75-127">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="e8b75-128">**Nur ausgewählte Websites:** Nur die angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="e8b75-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="e8b75-129">Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="e8b75-130">**Keine Websites**: Schließen Sie keine SharePoint-Websites ein.</span><span class="sxs-lookup"><span data-stu-id="e8b75-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="e8b75-131">Wenn Sie entweder **Alle auswählen,** mit Ausnahme ausgewählter Websites oder **Nur** ausgewählte Websites, können Sie eine .csv mit einer Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="e8b75-132">Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt erstellen und eine begrenzte Anzahl von Websites zum Starten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="e8b75-133">Sie können die vorlage .csv kopieren:</span><span class="sxs-lookup"><span data-stu-id="e8b75-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="e8b75-134">Es wird nicht empfohlen, keine Websites **zu wählen,** da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8b75-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="e8b75-135">Sie können diese Option jedoch auswählen, wenn Sie Themen einrichten und später Websites hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="e8b75-136">Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um zu fordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Themensuche entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e8b75-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="e8b75-137">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="e8b75-137">Multi-geo</span></span>

<span data-ttu-id="e8b75-138">Wenn Ihre Organisation Microsoft 365 [Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)bereitgestellt hat, wird das Themencenter am zentralen Standort bereitgestellt, und nur SharePoint-Standorte am zentralen Standort stehen als Quellen für Themen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e8b75-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="e8b75-139">(Wenn Sie Alle **Websites auswählen,** verwendet "Viva Topics" alle Websites am zentralen Standort.)</span><span class="sxs-lookup"><span data-stu-id="e8b75-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="e8b75-140">Die Verarbeitung und Speicherung von Inhalten erfolgt an zentraler Stelle.</span><span class="sxs-lookup"><span data-stu-id="e8b75-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="e8b75-141">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="e8b75-141">User permissions</span></span>

<span data-ttu-id="e8b75-142">Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.</span><span class="sxs-lookup"><span data-stu-id="e8b75-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="e8b75-143">Derzeit unterstützt Viva Topics die Bereitstellung von Lizenzen oder Benutzerberechtigungen für Gastbenutzer (externe Benutzer) nicht.</span><span class="sxs-lookup"><span data-stu-id="e8b75-143">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="e8b75-144">*Themen verwalten*</span><span class="sxs-lookup"><span data-stu-id="e8b75-144">*Manage topics*</span></span>

<span data-ttu-id="e8b75-145">Wissensmanager überwachen die Qualität der Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8b75-145">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="e8b75-146">Sie können Themen bestätigen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-146">They can confirm and reject topics.</span></span>

<span data-ttu-id="e8b75-147">Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe (oder eine vorhandene) zu erstellen, die die Personen enthält, die Sie als Wissensmanager verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-147">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="e8b75-148">Sie können diese Sicherheitsgruppe während des Setupvorgangs angeben.</span><span class="sxs-lookup"><span data-stu-id="e8b75-148">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="e8b75-149">*Erstellen und Bearbeiten von Themen*</span><span class="sxs-lookup"><span data-stu-id="e8b75-149">*Create and edit topics*</span></span>

<span data-ttu-id="e8b75-150">Mitwirkende sind die Experten für Themen und Experten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8b75-150">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="e8b75-151">Sie können Themen erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-151">They can create and edit topics.</span></span> 

<span data-ttu-id="e8b75-152">Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da die Themenerfahrungen am besten funktionieren, wenn alle Benutzer Informationen freigeben können.</span><span class="sxs-lookup"><span data-stu-id="e8b75-152">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="e8b75-153">Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für sie, und geben Sie sie während des Einrichtungsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="e8b75-153">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="e8b75-154">Sie können auswählen, dass niemand an Themen mit beitragen kann, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-154">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="e8b75-155">Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-155">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="e8b75-156">*Betrachter von Topics*</span><span class="sxs-lookup"><span data-stu-id="e8b75-156">*Topic viewers*</span></span>

<span data-ttu-id="e8b75-157">Themenbetrachter können Informationen auf Themenseiten, in Suchergebnissen und wann Themen in den Inhalten hervorgehoben werden, z. B. SharePoint Seiten.</span><span class="sxs-lookup"><span data-stu-id="e8b75-157">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="e8b75-158">Benutzer können nur dann ermittelte Themen sehen, wenn sie Zugriff auf die Dateien und Seiten haben, in denen das Thema entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8b75-158">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="e8b75-159">Beim Einrichten von Themenbetrachtern können Sie aus:</span><span class="sxs-lookup"><span data-stu-id="e8b75-159">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="e8b75-160">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="e8b75-160">**Everyone in my organization**</span></span>
- <span data-ttu-id="e8b75-161">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="e8b75-161">**Only selected people or security groups**</span></span>
- <span data-ttu-id="e8b75-162">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="e8b75-162">**No one**</span></span>

<span data-ttu-id="e8b75-163">Wir empfehlen **Jeder in meiner Organisation,** aber wenn Sie ein Pilotprojekt erstellen, sollten Sie möglicherweise nur ausgewählte Personen oder Sicherheitsgruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-163">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="e8b75-164">Sie können auch Niemand **auswählen,** wenn Sie Themen einrichten möchten, aber noch keine Themen sehen können.</span><span class="sxs-lookup"><span data-stu-id="e8b75-164">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="e8b75-165">(Wissensmanager haben weiterhin Zugriff darauf, dass sie die Themen anzeigen und bei der Entscheidung helfen, Themen allgemein verfügbar zu machen.)</span><span class="sxs-lookup"><span data-stu-id="e8b75-165">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="e8b75-166">Wissensregeln</span><span class="sxs-lookup"><span data-stu-id="e8b75-166">Knowledge rules</span></span>

<span data-ttu-id="e8b75-167">Als Administrator können Sie bestimmte Themen von der Themenerfahrung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-167">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="e8b75-168">Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-168">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="e8b75-169">Während Wissensmanager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar.</span><span class="sxs-lookup"><span data-stu-id="e8b75-169">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="e8b75-170">(Wissensmanager können nach der Ermittlung auch Themen im Themencenter entfernen.)</span><span class="sxs-lookup"><span data-stu-id="e8b75-170">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="e8b75-171">Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer .csv hinzufügen und die Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="e8b75-171">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="e8b75-172">Sie können dies während des Setups oder höher tun.</span><span class="sxs-lookup"><span data-stu-id="e8b75-172">You can do this during setup or later.</span></span>

<span data-ttu-id="e8b75-173">Die .csv muss die folgenden Parameter enthalten:</span><span class="sxs-lookup"><span data-stu-id="e8b75-173">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="e8b75-174">**Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8b75-174">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="e8b75-175">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="e8b75-175">There are two ways to do this:</span></span>
- <span data-ttu-id="e8b75-176">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="e8b75-176">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="e8b75-177">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*</span><span class="sxs-lookup"><span data-stu-id="e8b75-177">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="e8b75-178">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e8b75-178">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="e8b75-179">Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="e8b75-179">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="e8b75-180">**Steht für (optional)**: (Auch als Erweiterung *bezeichnet)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="e8b75-180">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

<span data-ttu-id="e8b75-182">Sie können die folgende CSV-Vorlage kopieren:</span><span class="sxs-lookup"><span data-stu-id="e8b75-182">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="e8b75-183">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e8b75-183">Administration</span></span>

<span data-ttu-id="e8b75-184">Wenn Sie Themen als Teil des Einrichtungsprozesses einrichten, wird automatisch ein Themencenter erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8b75-184">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="e8b75-185">Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll.</span><span class="sxs-lookup"><span data-stu-id="e8b75-185">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="e8b75-186">Sie können sowohl den Namen als auch die URL im Rahmen des Setupprozesses festlegen und den Namen (jedoch nicht die URL) später im Microsoft 365 ändern.</span><span class="sxs-lookup"><span data-stu-id="e8b75-186">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e8b75-187">Sie können nur ein Themencenter haben.</span><span class="sxs-lookup"><span data-stu-id="e8b75-187">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="e8b75-188">Prüfliste zum Einrichten</span><span class="sxs-lookup"><span data-stu-id="e8b75-188">Setup checklist</span></span>

<span data-ttu-id="e8b75-189">Wenn Sie Themenerfahrungen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchgehen:</span><span class="sxs-lookup"><span data-stu-id="e8b75-189">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e8b75-190">Liste der ein- oder auszuschließenden Websites, wenn nicht alle Websites für die Themenentdeckung eingeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="e8b75-190">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="e8b75-191">Sicherheitsgruppe für Themenbetrachter, wenn nicht alle Benutzer Themen anzeigen können</span><span class="sxs-lookup"><span data-stu-id="e8b75-191">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="e8b75-192">Sicherheitsgruppe für Themenmitwirkende, wenn nicht alle Benutzer Themen erstellen und bearbeiten können</span><span class="sxs-lookup"><span data-stu-id="e8b75-192">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="e8b75-193">Sicherheitsgruppe für Themenwissensverwalter, wenn nicht alle Benutzer Themen verwalten können</span><span class="sxs-lookup"><span data-stu-id="e8b75-193">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="e8b75-194">Liste der vertraulichen Themen, die von der Themenerkennung ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="e8b75-194">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="e8b75-195">Ein Name für Ihre Themencenterwebsite</span><span class="sxs-lookup"><span data-stu-id="e8b75-195">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b75-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8b75-196">See also</span></span>

[<span data-ttu-id="e8b75-197">Topic Experiences einrichten</span><span class="sxs-lookup"><span data-stu-id="e8b75-197">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="e8b75-198">Verwalten der Themenerkennung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b75-198">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="e8b75-199">Verwalten der Thementransparenz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b75-199">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="e8b75-200">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b75-200">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="e8b75-201">Ändern Sie den Namen des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b75-201">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
