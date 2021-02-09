---
title: Planen von Microsoft -Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie den Plan für Microsoft -Themen in Themen planen
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150478"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="0f2d2-103">Planen von Microsoft -Themen</span><span class="sxs-lookup"><span data-stu-id="0f2d2-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="0f2d2-104">Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="0f2d2-105">Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern Themen mit hoher Qualität angezeigt werden und dass sie über die richtigen Berechtigungen zum Nutzen und Zum Beitragen von Wissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="0f2d2-106">In diesem Artikel werden diese Planungsentscheidungen behandelt:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="0f2d2-107">Welche SharePoint-Websites sie nach Themen durchforsten möchten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="0f2d2-108">Welche Themen sie gegebenenfalls aus der Themenerfahrung ausschließen möchten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="0f2d2-109">Für welche Benutzer Sie Themen sichtbar machen möchten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="0f2d2-110">Welche Benutzer Sie berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="0f2d2-111">Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="0f2d2-112">Welchen Namen Möchten Sie Ihrem Themencenter geben?</span><span class="sxs-lookup"><span data-stu-id="0f2d2-112">What name you want to give your topic center</span></span>

<span data-ttu-id="0f2d2-113">Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und Themenerfahrungen gewähren Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="0f2d2-114">Es wird empfohlen, dass Sie im Rahmen Ihres Planungsprozesses auch die Themen "Sicherheit und Datenschutz in [Microsoft Topics"](topic-experiences-security-privacy.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f2d2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f2d2-115">Requirements</span></span>

<span data-ttu-id="0f2d2-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="0f2d2-117">Alle Benutzer, die Themen verwenden werden, benötigen **eine Topic Experiences-Lizenz.**</span><span class="sxs-lookup"><span data-stu-id="0f2d2-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="0f2d2-118">Das Zuweisen von Lizenzen wird in [den Themen zum Einrichten von Microsoft Topics behandelt.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="0f2d2-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="0f2d2-119">Themenermittlung</span><span class="sxs-lookup"><span data-stu-id="0f2d2-119">Topic discovery</span></span>

<span data-ttu-id="0f2d2-120">Die Themenerkennungseinstellungen geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="0f2d2-121">Sie können alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="0f2d2-122">Es wird empfohlen, alle Websites zu wählen, damit themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="0f2d2-123">Beim Einrichten von Themen können Sie aus den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="0f2d2-124">**Alle Websites:** Alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="0f2d2-125">Dazu gehören aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-125">This includes current and future sites.</span></span>
- <span data-ttu-id="0f2d2-126">**Alle, mit Ausnahme ausgewählter Websites:** Alle Websites mit Ausnahme der von Ihnen angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="0f2d2-127">Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="0f2d2-128">**Nur ausgewählte Websites:** Nur die von Ihnen angegebenen Websites.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="0f2d2-129">Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="0f2d2-130">**Keine Websites:** Keine SharePoint-Websites enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="0f2d2-131">Wenn Sie **"Alle" mit** Ausnahme ausgewählter Websites oder **"Nur** ausgewählte Websites" auswählen, können Sie eine .csv-Datei mit einer Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="0f2d2-132">Diese Optionen sind nützlich, wenn Sie ein Pilotprojekt machen und eine begrenzte Anzahl von Websites zum Starten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="0f2d2-133">Sie können die .csv-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="0f2d2-134">Es wird nicht empfohlen, "Keine Websites" zu wählen, da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden. </span><span class="sxs-lookup"><span data-stu-id="0f2d2-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="0f2d2-135">Sie können diese Option jedoch auswählen, wenn Sie Themen einrichten und später Websites hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="0f2d2-136">Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um an verlangen, dass einzelne Websites bei Bedarf aus der Themenermittlung in Ihrer Organisation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="0f2d2-137">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="0f2d2-137">User permissions</span></span>

<span data-ttu-id="0f2d2-138">Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="0f2d2-139">*Verwalten von Themen*</span><span class="sxs-lookup"><span data-stu-id="0f2d2-139">*Manage topics*</span></span>

<span data-ttu-id="0f2d2-140">Wissensmanager überwachen die Qualität von Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="0f2d2-141">Sie können Themen bestätigen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="0f2d2-142">Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe zu erstellen (oder eine vorhandene zu verwenden), die die Personen enthält, die Sie als Wissensmanager verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="0f2d2-143">Sie können diese Sicherheitsgruppe während des Setupvorgangs angeben.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="0f2d2-144">*Erstellen und Bearbeiten von Themen*</span><span class="sxs-lookup"><span data-stu-id="0f2d2-144">*Create and edit topics*</span></span>

<span data-ttu-id="0f2d2-145">Mitwirkende sind Experten und Fachexperten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="0f2d2-146">Sie können Themen erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-146">They can create and edit topics.</span></span> 

<span data-ttu-id="0f2d2-147">Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da die Themenerfahrung am besten funktioniert, wenn alle Benutzer Informationen gemeinsam verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="0f2d2-148">Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für diese Personen, und geben Sie sie während des Setupprozesses an.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="0f2d2-149">Sie können festlegen, dass niemand an Themen mit beitragen darf, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="0f2d2-150">Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="0f2d2-151">*Themenanzeigen*</span><span class="sxs-lookup"><span data-stu-id="0f2d2-151">*Topic viewers*</span></span>

<span data-ttu-id="0f2d2-152">Themenanzeigen können Informationen auf Themenseiten, in Suchergebnissen und bei hervorgehobenen Themen in Inhalten wie SharePoint-Seiten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="0f2d2-153">Benutzer können ermittelte Themen nur sehen, wenn sie Zugriff auf die Dateien und Seiten haben, auf denen das Thema gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="0f2d2-154">Beim Einrichten von Themenanzeigen haben Sie die Wahl zwischen:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="0f2d2-155">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="0f2d2-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="0f2d2-156">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="0f2d2-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="0f2d2-157">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="0f2d2-157">**No one**</span></span>

<span data-ttu-id="0f2d2-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="0f2d2-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="0f2d2-160">(Wissensmanager haben weiterhin Zugriff, um ihnen das Anzeigen der Themen und Hilfe bei der Entscheidung zu ermöglichen, Themen allgemein verfügbar zu machen.)</span><span class="sxs-lookup"><span data-stu-id="0f2d2-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="0f2d2-161">Wissensregeln</span><span class="sxs-lookup"><span data-stu-id="0f2d2-161">Knowledge rules</span></span>

<span data-ttu-id="0f2d2-162">Als Administrator können Sie bestimmte Themen aus der Themenerfahrung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="0f2d2-163">Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="0f2d2-164">Während Knowledge Manager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="0f2d2-165">(Wissensmanager können nach der Ermittlung auch Themen im Themencenter entfernen.)</span><span class="sxs-lookup"><span data-stu-id="0f2d2-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="0f2d2-166">Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer CSV-Datei hinzufügen und die Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="0f2d2-167">Sie können dies während des Setups oder höher tun.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-167">You can do this during setup or later.</span></span>

<span data-ttu-id="0f2d2-168">Die .csv-Datei muss die folgenden Parameter enthalten:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="0f2d2-169">**Name:** Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0f2d2-170">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-170">There are two ways to do this:</span></span>
- <span data-ttu-id="0f2d2-171">**MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein *exakter* oder teilweiser *Übereinstimmungstyp* war.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="0f2d2-172">Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) verwenden.*</span><span class="sxs-lookup"><span data-stu-id="0f2d2-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="0f2d2-173">Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0f2d2-174">Der Bogen *schließt* z. B. alle Themen aus, *in* denen der Wortbogen enthalten ist, z. B. Bogenkreis,  *Arkusbogen* oder *Schulungsbogen.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*</span><span class="sxs-lookup"><span data-stu-id="0f2d2-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="0f2d2-175">**Steht für (optional)**: (auch als Erweiterung *bezeichnet)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

<span data-ttu-id="0f2d2-177">Sie können die folgende CSV-Vorlage kopieren:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="0f2d2-178">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="0f2d2-178">Administration</span></span>

<span data-ttu-id="0f2d2-179">Wenn Sie Themen im Rahmen des Einrichtungsprozesses einrichten, wird automatisch ein Themencenter erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="0f2d2-180">Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="0f2d2-181">Sie können den Namen und die URL im Rahmen des Setupprozesses festlegen und den Namen (jedoch nicht die URL) später im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0f2d2-182">Sie können nur ein Themencenter haben.</span><span class="sxs-lookup"><span data-stu-id="0f2d2-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="0f2d2-183">Prüfliste für das Setup</span><span class="sxs-lookup"><span data-stu-id="0f2d2-183">Setup checklist</span></span>

<span data-ttu-id="0f2d2-184">Wenn Sie Themenerfahrungen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchgehen:</span><span class="sxs-lookup"><span data-stu-id="0f2d2-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0f2d2-185">Liste der Websites, die ein- oder ausgeschlossen werden, wenn nicht alle Websites für die Themenermittlung enthalten sind</span><span class="sxs-lookup"><span data-stu-id="0f2d2-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="0f2d2-186">Sicherheitsgruppe für Themenanzeigen, wenn nicht allen Benutzern das Anzeigen von Themen erlaubt wird</span><span class="sxs-lookup"><span data-stu-id="0f2d2-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="0f2d2-187">Sicherheitsgruppe für Mitwirkende von Themen, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen erlaubt wird</span><span class="sxs-lookup"><span data-stu-id="0f2d2-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="0f2d2-188">Sicherheitsgruppe für Wissensmanager von Themen, wenn nicht allen Benutzern die Verwaltung von Themen erlaubt wird</span><span class="sxs-lookup"><span data-stu-id="0f2d2-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="0f2d2-189">Liste der vertraulichen Themen, die von der Themenermittlung ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="0f2d2-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="0f2d2-190">Ein Name für Ihre Themencenterwebsite</span><span class="sxs-lookup"><span data-stu-id="0f2d2-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="0f2d2-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f2d2-191">See also</span></span>

[<span data-ttu-id="0f2d2-192">Topic Experiences einrichten</span><span class="sxs-lookup"><span data-stu-id="0f2d2-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="0f2d2-193">Verwalten der Themenermittlung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2d2-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="0f2d2-194">Verwalten der Sichtbarkeit von Themen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2d2-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="0f2d2-195">Verwalten von Themenberechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2d2-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="0f2d2-196">Ändern des Namens des Themencenters in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f2d2-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
