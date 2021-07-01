---
title: Planen von Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie die Planung für Microsoft Viva Topics planen
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229539"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="52775-103">Planen von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="52775-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="52775-104">Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="52775-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="52775-105">Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und sie über die richtigen Berechtigungen zum Nutzen und Beitragen von Wissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="52775-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="52775-106">In diesem Artikel werden die folgenden Planungsentscheidungen behandelt:</span><span class="sxs-lookup"><span data-stu-id="52775-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="52775-107">Welche SharePoint Websites sie für Themen durchforsten möchten</span><span class="sxs-lookup"><span data-stu-id="52775-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="52775-108">Welche Themen sie ggf. von der Themenerfahrung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="52775-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="52775-109">Benutzer, für die Sie Themen sichtbar machen möchten</span><span class="sxs-lookup"><span data-stu-id="52775-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="52775-110">Welche Benutzer Sie Berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="52775-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="52775-111">Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="52775-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="52775-112">Welchen Namen Sie Ihrem Themencenter geben möchten</span><span class="sxs-lookup"><span data-stu-id="52775-112">What name you want to give your topic center</span></span>

<span data-ttu-id="52775-113">Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und Themenerfahrungen gewähren Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben.</span><span class="sxs-lookup"><span data-stu-id="52775-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="52775-114">Wir empfehlen Ihnen, auch [die Sicherheit und den Datenschutz](topic-experiences-security-privacy.md) von Microsoft Viva Topics im Rahmen Ihres Planungsprozesses zu lesen.</span><span class="sxs-lookup"><span data-stu-id="52775-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="52775-115">Um mehr über die KI-Technologie hinter Viva Topics zu erfahren, lesen Sie ["Viva" in Microsoft Viva Topics: von Big Data bis hin zu großem Wissen.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="52775-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="52775-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52775-116">Requirements</span></span>

<span data-ttu-id="52775-117">Sie müssen [Viva Topics abonniert](https://www.microsoft.com/microsoft-viva/topics) haben und ein globaler Administrator oder SharePoint Administrator sein, um auf die Microsoft 365 Admin Center zugreifen und Topics einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="52775-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="52775-118">Alle Benutzer, die Topics verwenden möchten, benötigen eine Lizenz für **Themenerfahrungen.**</span><span class="sxs-lookup"><span data-stu-id="52775-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="52775-119">Das Zuweisen von Lizenzen wird in ["Einrichten von Microsoft Viva Topics"](set-up-topic-experiences.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="52775-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="52775-120">Themensuche</span><span class="sxs-lookup"><span data-stu-id="52775-120">Topic discovery</span></span>

<span data-ttu-id="52775-121">Die Einstellungen für die Themensuche geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52775-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="52775-122">Dazu gehören sowohl klassische und moderne Websites als auch Websites, die Microsoft Teams und Microsoft 365-Gruppen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="52775-122">This includes both classic and modern sites, as well as sites associated with Microsoft Teams and Microsoft 365 Groups.</span></span> <span data-ttu-id="52775-123">OneDrive Websites sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="52775-123">OneDrive sites are not included.</span></span>

<span data-ttu-id="52775-124">Sie können wählen, ob Sie alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="52775-124">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="52775-125">Es wird empfohlen, dass Sie alle Websites auswählen, damit Themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.</span><span class="sxs-lookup"><span data-stu-id="52775-125">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="52775-126">Wenn Sie Topics einrichten, können Sie unter folgenden Optionen wählen:</span><span class="sxs-lookup"><span data-stu-id="52775-126">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="52775-127">**Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="52775-127">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="52775-128">Dies schließt aktuelle und zukünftige Websites ein.</span><span class="sxs-lookup"><span data-stu-id="52775-128">This includes current and future sites.</span></span>
- <span data-ttu-id="52775-129">**Alle, mit Ausnahme von ausgewählten Websites**: Alle Websites mit Ausnahme der von Ihnen angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="52775-129">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="52775-130">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="52775-130">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="52775-131">**Nur ausgewählte Websites:** Nur die von Ihnen angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="52775-131">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="52775-132">Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.</span><span class="sxs-lookup"><span data-stu-id="52775-132">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="52775-133">**Keine Websites**: Schließen Sie keine SharePoint-Websites ein.</span><span class="sxs-lookup"><span data-stu-id="52775-133">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="52775-134">Wenn Sie entweder **"Alle", mit Ausnahme ausgewählter Websites** oder **"Nur ausgewählte Websites",** auswählen, können Sie eine .csv Datei mit einer Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="52775-134">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="52775-135">Diese Optionen sind nützlich, wenn Sie ein Pilotprojekt durchführen und eine begrenzte Anzahl von Websites zum Starten einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="52775-135">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="52775-136">Sie können die .csv Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="52775-136">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="52775-137">Es wird nicht empfohlen, **"Keine Websites"** auszuwählen, da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="52775-137">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="52775-138">Sie können diese Option jedoch auswählen, wenn Sie Topics einrichten und später Websites hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="52775-138">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="52775-139">Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um anzufordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Themensuche entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="52775-139">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="52775-140">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="52775-140">Multi-geo</span></span>

<span data-ttu-id="52775-141">Wenn Ihre Organisation [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)bereitgestellt hat, wird das Themencenter am zentralen Standort bereitgestellt, und nur SharePoint Standorte am zentralen Standort stehen als Quellen für Themen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="52775-141">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="52775-142">(Wenn Sie **alle Websites** auswählen, verwendet Viva Topics alle Websites am zentralen Ort.)</span><span class="sxs-lookup"><span data-stu-id="52775-142">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="52775-143">Die gesamte Verarbeitung und Speicherung von Inhalten erfolgt am zentralen Ort.</span><span class="sxs-lookup"><span data-stu-id="52775-143">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="52775-144">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="52775-144">User permissions</span></span>

<span data-ttu-id="52775-145">Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.</span><span class="sxs-lookup"><span data-stu-id="52775-145">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="52775-146">Derzeit unterstützt Viva Topics nicht die Bereitstellung von Lizenzen oder Benutzerberechtigungen für Gastbenutzer (externe).</span><span class="sxs-lookup"><span data-stu-id="52775-146">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="52775-147">*Themen verwalten*</span><span class="sxs-lookup"><span data-stu-id="52775-147">*Manage topics*</span></span>

<span data-ttu-id="52775-148">Wissensmanager überwachen die Qualität von Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="52775-148">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="52775-149">Sie können Themen bestätigen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="52775-149">They can confirm and reject topics.</span></span>

<span data-ttu-id="52775-150">Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe zu erstellen (oder eine vorhandene zu verwenden), die die Personen enthält, die Wissensmanager sein sollen.</span><span class="sxs-lookup"><span data-stu-id="52775-150">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="52775-151">Sie können diese Sicherheitsgruppe während des Setupprozesses angeben.</span><span class="sxs-lookup"><span data-stu-id="52775-151">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="52775-152">*Erstellen und Bearbeiten von Themen*</span><span class="sxs-lookup"><span data-stu-id="52775-152">*Create and edit topics*</span></span>

<span data-ttu-id="52775-153">Themenmitwirkende sind die Experten und Fachexperten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="52775-153">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="52775-154">Sie können Themen erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="52775-154">They can create and edit topics.</span></span> 

<span data-ttu-id="52775-155">Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da Themen am besten funktionieren, wenn alle Benutzer Informationen freigeben können.</span><span class="sxs-lookup"><span data-stu-id="52775-155">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="52775-156">Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für sie, und geben Sie diese während des Setupprozesses an.</span><span class="sxs-lookup"><span data-stu-id="52775-156">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="52775-157">Sie können festlegen, dass niemand an Themen mitwirken darf, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="52775-157">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="52775-158">Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="52775-158">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="52775-159">*Betrachter von Topics*</span><span class="sxs-lookup"><span data-stu-id="52775-159">*Topic viewers*</span></span>

<span data-ttu-id="52775-160">Themenbetrachter können Informationen auf Themenseiten, in Suchergebnissen und wenn Themen im Inhalt hervorgehoben werden, z. B. SharePoint Seiten, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52775-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="52775-161">Benutzer können erkannte Themen nur sehen, wenn sie Zugriff auf die Dateien und Seiten haben, auf denen das Thema entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="52775-161">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="52775-162">Beim Einrichten von Themenviewern können Sie aus folgenden Möglichkeiten wählen:</span><span class="sxs-lookup"><span data-stu-id="52775-162">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="52775-163">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="52775-163">**Everyone in my organization**</span></span>
- <span data-ttu-id="52775-164">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="52775-164">**Only selected people or security groups**</span></span>
- <span data-ttu-id="52775-165">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="52775-165">**No one**</span></span>

<span data-ttu-id="52775-166">Wir empfehlen **jeder in meiner Organisation,** aber wenn Sie ein Pilotprojekt durchführen, möchten Sie möglicherweise nur ausgewählte Personen oder Sicherheitsgruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="52775-166">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="52775-167">Sie können auch **"Niemand"** auswählen, wenn Sie "Topics" einrichten möchten, aber noch keine Themen anzeigen dürfen.</span><span class="sxs-lookup"><span data-stu-id="52775-167">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="52775-168">(Wissensmanager haben weiterhin Zugriff, damit sie die Themen anzeigen und bei der Entscheidung helfen können, Themen allgemein verfügbar zu machen.)</span><span class="sxs-lookup"><span data-stu-id="52775-168">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="52775-169">Wissensregeln</span><span class="sxs-lookup"><span data-stu-id="52775-169">Knowledge rules</span></span>

<span data-ttu-id="52775-170">Als Administrator können Sie bestimmte Themen aus der Themenerfahrung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="52775-170">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="52775-171">Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52775-171">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="52775-172">Während Wissensmanager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar.</span><span class="sxs-lookup"><span data-stu-id="52775-172">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="52775-173">(Wissensmanager können auch Themen im Themencenter nach der Ermittlung entfernen.)</span><span class="sxs-lookup"><span data-stu-id="52775-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="52775-174">Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer .csv-Datei hinzufügen und die Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="52775-174">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="52775-175">Sie können dies während des Setups oder später tun.</span><span class="sxs-lookup"><span data-stu-id="52775-175">You can do this during setup or later.</span></span>

<span data-ttu-id="52775-176">Die .csv Datei muss die folgenden Parameter enthalten:</span><span class="sxs-lookup"><span data-stu-id="52775-176">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="52775-177">**Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="52775-177">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="52775-178">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="52775-178">There are two ways to do this:</span></span>
- <span data-ttu-id="52775-179">**MatchType-Exact/Partial:** Geben Sie an, ob der eingegebene Name ein *exakter* oder *teilweiser* Übereinstimmungstyp war.</span><span class="sxs-lookup"><span data-stu-id="52775-179">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="52775-180">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (z. B. *Contoso* oder *ATL).*</span><span class="sxs-lookup"><span data-stu-id="52775-180">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="52775-181">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="52775-181">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="52775-182">Beispielsweise schließt *Arc* alle Themen mit dem Wort *Bogen* aus, z. B. *Arc Circle,* *Arc Arc-* oder *Training Arc.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. *Architektur,* nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="52775-182">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="52775-183">**Steht für (optional)**: (auch bekannt als *Erweiterung)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="52775-183">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Ausschließen von Themen in csv-Vorlage](../media/exclude-topics-csv.png) 

<span data-ttu-id="52775-185">Sie können die csv-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="52775-185">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="52775-186">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="52775-186">Administration</span></span>

<span data-ttu-id="52775-187">Wenn Sie Topics im Rahmen des Setupprozesses einrichten, wird automatisch ein Themencenter erstellt.</span><span class="sxs-lookup"><span data-stu-id="52775-187">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="52775-188">Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll.</span><span class="sxs-lookup"><span data-stu-id="52775-188">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="52775-189">Sie können sowohl den Namen als auch die URL im Rahmen des Setupprozesses festlegen und den Namen (aber nicht die URL) später im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="52775-189">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="52775-190">Sie können nur ein Themencenter haben.</span><span class="sxs-lookup"><span data-stu-id="52775-190">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="52775-191">Prüfliste zum Einrichten</span><span class="sxs-lookup"><span data-stu-id="52775-191">Setup checklist</span></span>

<span data-ttu-id="52775-192">Wenn Sie Themenoberflächen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchlaufen:</span><span class="sxs-lookup"><span data-stu-id="52775-192">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="52775-193">Liste der ein- oder auszuschließenden Websites, wenn nicht alle Websites für die Themenentdeckung eingeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="52775-193">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="52775-194">Sicherheitsgruppe für Themenbetrachter, wenn nicht alle Benutzer Themen anzeigen können</span><span class="sxs-lookup"><span data-stu-id="52775-194">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="52775-195">Sicherheitsgruppe für Themenmitwirkende, wenn nicht alle Benutzer Themen erstellen und bearbeiten können</span><span class="sxs-lookup"><span data-stu-id="52775-195">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="52775-196">Sicherheitsgruppe für Themenwissensverwalter, wenn nicht alle Benutzer Themen verwalten können</span><span class="sxs-lookup"><span data-stu-id="52775-196">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="52775-197">Liste vertraulicher Themen, die von der Themensuche ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="52775-197">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="52775-198">Ein Name für Ihre Themencenterwebsite</span><span class="sxs-lookup"><span data-stu-id="52775-198">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="52775-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52775-199">See also</span></span>

[<span data-ttu-id="52775-200">Topic Experiences einrichten</span><span class="sxs-lookup"><span data-stu-id="52775-200">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="52775-201">Verwalten der Themensuche in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52775-201">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="52775-202">Verwalten der Themensichtbarkeit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52775-202">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="52775-203">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52775-203">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="52775-204">Ändern des Namens des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52775-204">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
