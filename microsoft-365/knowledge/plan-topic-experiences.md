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
ms.openlocfilehash: 19baf8bdcfdd1fe38d64e3c2f259ace1ceab5a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925976"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="3219c-103">Planen von Microsoft Viva-Themen</span><span class="sxs-lookup"><span data-stu-id="3219c-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="3219c-104">Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3219c-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="3219c-105">Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und dass sie über die richtigen Berechtigungen zum Nutzen und Zum Beitragen von Wissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="3219c-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="3219c-106">In diesem Artikel werden die folgenden Planungsentscheidungen untersucht:</span><span class="sxs-lookup"><span data-stu-id="3219c-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="3219c-107">Welche SharePoint-Websites Sie nach Themen durchforsten möchten</span><span class="sxs-lookup"><span data-stu-id="3219c-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="3219c-108">Welche Themen Sie von den Themenerfahrungen ausschließen möchten, falls dies der Fall ist</span><span class="sxs-lookup"><span data-stu-id="3219c-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="3219c-109">Für welche Benutzer Sie Themen sichtbar machen möchten</span><span class="sxs-lookup"><span data-stu-id="3219c-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="3219c-110">Welche Benutzer Sie berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="3219c-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="3219c-111">Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="3219c-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="3219c-112">Welchen Namen möchten Sie Ihrem Themencenter geben?</span><span class="sxs-lookup"><span data-stu-id="3219c-112">What name you want to give your topic center</span></span>

<span data-ttu-id="3219c-113">Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und die Themenerfahrung gewährt Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben.</span><span class="sxs-lookup"><span data-stu-id="3219c-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="3219c-114">Es wird empfohlen, im Rahmen Ihres Planungsprozesses auch Die Sicherheit und den Datenschutz von [Microsoft Viva Topics](topic-experiences-security-privacy.md) zu lesen.</span><span class="sxs-lookup"><span data-stu-id="3219c-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="3219c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3219c-115">Requirements</span></span>

<span data-ttu-id="3219c-116">Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="3219c-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="3219c-117">Alle Benutzer, die Themen verwenden möchten, benötigen eine **Topic Experiences-Lizenz.**</span><span class="sxs-lookup"><span data-stu-id="3219c-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="3219c-118">Zuweisen von Lizenzen finden Sie unter [Einrichten von Microsoft Viva Topics](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="3219c-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="3219c-119">Themasuche</span><span class="sxs-lookup"><span data-stu-id="3219c-119">Topic discovery</span></span>

<span data-ttu-id="3219c-120">Die Einstellungen für die Themenermittlung geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3219c-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="3219c-121">Sie können alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3219c-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="3219c-122">Es wird empfohlen, alle Websites zu wählen, damit themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.</span><span class="sxs-lookup"><span data-stu-id="3219c-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="3219c-123">Beim Einrichten von Themen können Sie aus den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="3219c-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="3219c-124">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="3219c-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="3219c-125">Dies umfasst aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="3219c-125">This includes current and future sites.</span></span>
- <span data-ttu-id="3219c-126">**Alle, mit Ausnahme ausgewählter Websites:** Alle Websites mit Ausnahme der angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="3219c-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="3219c-127">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="3219c-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="3219c-128">**Nur ausgewählte Websites:** Nur die angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="3219c-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="3219c-129">Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenerkennung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="3219c-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="3219c-130">**Keine Websites**: Keine SharePoint-Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="3219c-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="3219c-131">Wenn Sie entweder **Alle auswählen, mit** Ausnahme ausgewählter Websites oder **Nur** ausgewählte Websites, können Sie eine CSV-Datei mit einer Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="3219c-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="3219c-132">Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt erstellen und eine begrenzte Anzahl von Websites zum Starten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3219c-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="3219c-133">Sie können die CSV-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="3219c-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="3219c-134">Es wird nicht empfohlen, keine Websites **zu wählen,** da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3219c-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="3219c-135">Sie können diese Option jedoch auswählen, wenn Sie Themen einrichten und später Websites hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3219c-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="3219c-136">Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um zu fordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Themensuche entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3219c-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="3219c-137">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="3219c-137">Multi-geo</span></span>

<span data-ttu-id="3219c-138">Wenn Ihre Organisation [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)bereitgestellt hat, wird das Themencenter am zentralen Standort bereitgestellt, und nur SharePoint-Websites am zentralen Standort stehen als Quellen für Themen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3219c-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="3219c-139">(Wenn Sie Alle **Websites auswählen,** verwendet "Viva Topics" alle Websites am zentralen Standort.)</span><span class="sxs-lookup"><span data-stu-id="3219c-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="3219c-140">Die Verarbeitung und Speicherung von Inhalten erfolgt an zentraler Stelle.</span><span class="sxs-lookup"><span data-stu-id="3219c-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="3219c-141">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="3219c-141">User permissions</span></span>

<span data-ttu-id="3219c-142">Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.</span><span class="sxs-lookup"><span data-stu-id="3219c-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="3219c-143">*Themen verwalten*</span><span class="sxs-lookup"><span data-stu-id="3219c-143">*Manage topics*</span></span>

<span data-ttu-id="3219c-144">Wissensmanager überwachen die Qualität der Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="3219c-144">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="3219c-145">Sie können Themen bestätigen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="3219c-145">They can confirm and reject topics.</span></span>

<span data-ttu-id="3219c-146">Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe (oder eine vorhandene) zu erstellen, die die Personen enthält, die Sie als Wissensmanager verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3219c-146">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="3219c-147">Sie können diese Sicherheitsgruppe während des Setupvorgangs angeben.</span><span class="sxs-lookup"><span data-stu-id="3219c-147">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="3219c-148">*Erstellen und Bearbeiten von Themen*</span><span class="sxs-lookup"><span data-stu-id="3219c-148">*Create and edit topics*</span></span>

<span data-ttu-id="3219c-149">Mitwirkende sind die Experten für Themen und Experten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="3219c-149">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="3219c-150">Sie können Themen erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3219c-150">They can create and edit topics.</span></span> 

<span data-ttu-id="3219c-151">Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da die Themenerfahrungen am besten funktionieren, wenn alle Benutzer Informationen freigeben können.</span><span class="sxs-lookup"><span data-stu-id="3219c-151">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="3219c-152">Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für sie, und geben Sie sie während des Einrichtungsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="3219c-152">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="3219c-153">Sie können auswählen, dass niemand an Themen mit beitragen kann, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3219c-153">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="3219c-154">Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="3219c-154">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="3219c-155">*Themenbetrachter*</span><span class="sxs-lookup"><span data-stu-id="3219c-155">*Topic viewers*</span></span>

<span data-ttu-id="3219c-156">Themenbetrachter können Informationen auf Themenseiten, in Suchergebnissen und in Den Inhalten wie SharePoint-Seiten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3219c-156">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="3219c-157">Benutzer können nur dann ermittelte Themen sehen, wenn sie Zugriff auf die Dateien und Seiten haben, in denen das Thema entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="3219c-157">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="3219c-158">Beim Einrichten von Themenbetrachtern können Sie aus:</span><span class="sxs-lookup"><span data-stu-id="3219c-158">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="3219c-159">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="3219c-159">**Everyone in my organization**</span></span>
- <span data-ttu-id="3219c-160">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="3219c-160">**Only selected people or security groups**</span></span>
- <span data-ttu-id="3219c-161">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="3219c-161">**No one**</span></span>

<span data-ttu-id="3219c-162">Wir empfehlen **Jeder in meiner Organisation,** aber wenn Sie ein Pilotprojekt erstellen, sollten Sie möglicherweise nur ausgewählte Personen oder Sicherheitsgruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="3219c-162">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="3219c-163">Sie können auch Niemand **auswählen,** wenn Sie Themen einrichten möchten, aber noch keine Themen sehen können.</span><span class="sxs-lookup"><span data-stu-id="3219c-163">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="3219c-164">(Wissensmanager haben weiterhin Zugriff darauf, dass sie die Themen anzeigen und bei der Entscheidung helfen, Themen allgemein verfügbar zu machen.)</span><span class="sxs-lookup"><span data-stu-id="3219c-164">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="3219c-165">Wissensregeln</span><span class="sxs-lookup"><span data-stu-id="3219c-165">Knowledge rules</span></span>

<span data-ttu-id="3219c-166">Als Administrator können Sie bestimmte Themen von der Themenerfahrung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="3219c-166">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="3219c-167">Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3219c-167">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="3219c-168">Während Wissensmanager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar.</span><span class="sxs-lookup"><span data-stu-id="3219c-168">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="3219c-169">(Wissensmanager können nach der Ermittlung auch Themen im Themencenter entfernen.)</span><span class="sxs-lookup"><span data-stu-id="3219c-169">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="3219c-170">Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer CSV-Datei hinzufügen und die Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="3219c-170">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="3219c-171">Sie können dies während des Setups oder höher tun.</span><span class="sxs-lookup"><span data-stu-id="3219c-171">You can do this during setup or later.</span></span>

<span data-ttu-id="3219c-172">Die CSV-Datei muss die folgenden Parameter enthalten:</span><span class="sxs-lookup"><span data-stu-id="3219c-172">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="3219c-173">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="3219c-173">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="3219c-174">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="3219c-174">There are two ways to do this:</span></span>
- <span data-ttu-id="3219c-175">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="3219c-175">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="3219c-176">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*</span><span class="sxs-lookup"><span data-stu-id="3219c-176">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="3219c-177">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3219c-177">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="3219c-178">Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="3219c-178">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="3219c-179">**Steht für (optional)**: (Auch als Erweiterung *bezeichnet)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="3219c-179">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

<span data-ttu-id="3219c-181">Sie können die folgende CSV-Vorlage kopieren:</span><span class="sxs-lookup"><span data-stu-id="3219c-181">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="3219c-182">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3219c-182">Administration</span></span>

<span data-ttu-id="3219c-183">Wenn Sie Themen als Teil des Einrichtungsprozesses einrichten, wird automatisch ein Themencenter erstellt.</span><span class="sxs-lookup"><span data-stu-id="3219c-183">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="3219c-184">Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll.</span><span class="sxs-lookup"><span data-stu-id="3219c-184">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="3219c-185">Sie können sowohl den Namen als auch die URL im Rahmen des Einrichtungsprozesses festlegen und den Namen (jedoch nicht die URL) später im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="3219c-185">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3219c-186">Sie können nur ein Themencenter haben.</span><span class="sxs-lookup"><span data-stu-id="3219c-186">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="3219c-187">Prüfliste zum Einrichten</span><span class="sxs-lookup"><span data-stu-id="3219c-187">Setup checklist</span></span>

<span data-ttu-id="3219c-188">Wenn Sie Themenerfahrungen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchgehen:</span><span class="sxs-lookup"><span data-stu-id="3219c-188">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="3219c-189">Liste der Websites, die ein- oder ausgeschlossen werden, wenn nicht alle Websites für die Themenerkennung enthalten sind</span><span class="sxs-lookup"><span data-stu-id="3219c-189">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="3219c-190">Sicherheitsgruppe für Themenbetrachter, wenn nicht allen Benutzern das Anzeigen von Themen erlaubt wird</span><span class="sxs-lookup"><span data-stu-id="3219c-190">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="3219c-191">Sicherheitsgruppe für Mitwirkende von Themen, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen ermöglicht wird</span><span class="sxs-lookup"><span data-stu-id="3219c-191">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="3219c-192">Sicherheitsgruppe für Themenwissensmanager, wenn nicht allen Benutzern die Verwaltung von Themen ermöglicht wird</span><span class="sxs-lookup"><span data-stu-id="3219c-192">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="3219c-193">Liste der vertraulichen Themen, die von der Themenerkennung ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="3219c-193">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="3219c-194">Ein Name für Ihre Themencenterwebsite</span><span class="sxs-lookup"><span data-stu-id="3219c-194">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="3219c-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3219c-195">See also</span></span>

[<span data-ttu-id="3219c-196">Topic Experiences einrichten</span><span class="sxs-lookup"><span data-stu-id="3219c-196">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="3219c-197">Verwalten der Themenerkennung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3219c-197">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="3219c-198">Verwalten der Thementransparenz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3219c-198">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="3219c-199">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3219c-199">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="3219c-200">Ändern des Namens des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3219c-200">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
