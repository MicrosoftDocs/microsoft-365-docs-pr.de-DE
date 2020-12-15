---
title: Planen von Themen Erfahrungen in Microsoft 365
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
description: Informationen zum Planen von Themen Erfahrungen in Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668156"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a><span data-ttu-id="866aa-103">Planen von Themen Erfahrungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866aa-103">Plan topic experiences in Microsoft 365</span></span>

<span data-ttu-id="866aa-104">Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation erlebbar sind.</span><span class="sxs-lookup"><span data-stu-id="866aa-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="866aa-105">Ihre Planungsentscheidungen für Themenerfahrung stellt sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und Sie über die richtigen Berechtigungen zum Nutzen und zur Mitwirkung von Wissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="866aa-105">Your planning decisions for topic experiences ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="866aa-106">In diesem Artikel werden die folgenden Planungsentscheidungen untersucht:</span><span class="sxs-lookup"><span data-stu-id="866aa-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="866aa-107">Die SharePoint-Websites, die Sie nach Themen durchforsten möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-107">Which SharePoint sites you want to crawl for topics.</span></span>
- <span data-ttu-id="866aa-108">Welche Themen (falls vorhanden) von den Themen Erfahrungen ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="866aa-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="866aa-109">Die Benutzer, für die Sie Themen sichtbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-109">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="866aa-110">Die Benutzer, denen Sie Berechtigungen zum Verwalten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-110">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="866aa-111">Die Benutzer, denen Sie Berechtigungen zum Erstellen oder Bearbeiten von Themen im Themen Center erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-111">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="866aa-112">Welchen Namen möchten Sie Ihrem Themen Center geben?</span><span class="sxs-lookup"><span data-stu-id="866aa-112">What name you want to give your topic center.</span></span>

<span data-ttu-id="866aa-113">Die Sicherheit und der Datenschutz Ihrer Daten werden respektiert, und durch Themen Erfahrungen erhalten Benutzer keinen zusätzlichen Zugriff auf Dateien, für die Sie keine Rechte haben.</span><span class="sxs-lookup"><span data-stu-id="866aa-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="866aa-114">Es wird empfohlen, dass Sie auch im Rahmen Ihres Planungsprozesses die [Themen Sicherheit und Datenschutz](topic-experiences-security-privacy.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="866aa-114">We recommend you also read [Topic experiences security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="866aa-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="866aa-115">Requirements</span></span>

<span data-ttu-id="866aa-116">Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zuzugreifen und Themen Erfahrungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="866aa-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

<span data-ttu-id="866aa-117">Für alle Benutzer, die Themen Erfahrungen verwenden möchten, ist eine Lizenz für das **Thema Experiences** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="866aa-117">All users who are going to use topic experiences require a **Topic Experiences** license.</span></span> <span data-ttu-id="866aa-118">Das Zuweisen von Lizenzen wird in " [Einrichten von Themen Erfahrungen](set-up-topic-experiences.md)" behandelt.</span><span class="sxs-lookup"><span data-stu-id="866aa-118">Assigning licenses is covered in [Set up topic experiences](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="866aa-119">Thema Ermittlung</span><span class="sxs-lookup"><span data-stu-id="866aa-119">Topic discovery</span></span>

<span data-ttu-id="866aa-120">Die Themen Ermittlungs Einstellungen geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="866aa-121">Sie können auswählen, ob alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="866aa-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="866aa-122">Es wird empfohlen, dass Sie alle Websites auswählen, sodass mit dem Thema Erfahrungen eine große Anzahl von guten Themen für Ihre Benutzer ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="866aa-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="866aa-123">Wenn Sie Themen Erfahrungen einrichten, können Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="866aa-123">When you set up topic experiences, you can choose from the following options:</span></span>

- <span data-ttu-id="866aa-124">**Alle Websites**: alle SharePoint-Websites in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="866aa-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="866aa-125">Dazu gehören aktuelle und zukünftige Websites.</span><span class="sxs-lookup"><span data-stu-id="866aa-125">This includes current and future sites.</span></span>
- <span data-ttu-id="866aa-126">**Alle, außer ausgewählte Websites**: alle Websites mit Ausnahme der von Ihnen angegebenen.</span><span class="sxs-lookup"><span data-stu-id="866aa-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="866aa-127">In Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="866aa-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="866aa-128">**Nur ausgewählte Websites**: nur die Websites, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="866aa-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="866aa-129">In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="866aa-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="866aa-130">**Keine Websites**: keine SharePoint-Websites einschließen.</span><span class="sxs-lookup"><span data-stu-id="866aa-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="866aa-131">Wenn Sie entweder **alle, außer ausgewählte Websites** oder **nur ausgewählte Websites** auswählen, können Sie eine CSV-Datei mit einer Liste von Websites hochladen.</span><span class="sxs-lookup"><span data-stu-id="866aa-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="866aa-132">Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt ausführen und eine beschränkte Anzahl von Websites für den Start einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="866aa-133">Sie können die CSV-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="866aa-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="866aa-134">Es wird nicht empfohlen, **keine Websites** auszuwählen, da verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="866aa-135">Sie können diese Option jedoch auswählen, wenn Sie Themen Erfahrungen einrichten und dann später Websites hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-135">However, you can choose this option if you want to set up topic experiences and then add sites later.</span></span>

<span data-ttu-id="866aa-136">Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um zu fordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Thema Ermittlung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="866aa-137">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="866aa-137">User permissions</span></span>

<span data-ttu-id="866aa-138">Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was Sie tun können.</span><span class="sxs-lookup"><span data-stu-id="866aa-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="866aa-139">*Verwalten von Themen*</span><span class="sxs-lookup"><span data-stu-id="866aa-139">*Manage topics*</span></span>

<span data-ttu-id="866aa-140">Wissensmanager überwachen die Qualität der Informationen, ihre Strukturierung und andere bewährte Methoden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="866aa-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="866aa-141">Sie können Themen bestätigen und ablehnen.</span><span class="sxs-lookup"><span data-stu-id="866aa-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="866aa-142">Während Sie einzelne Themen Manager angeben können, wird empfohlen, dass Sie eine Sicherheitsgruppe erstellen (oder eine vorhandene verwenden), die die Personen enthält, die Sie als Wissens Verwalter bezeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="866aa-143">Sie können diese Sicherheitsgruppe während des Installationsvorgangs angeben.</span><span class="sxs-lookup"><span data-stu-id="866aa-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="866aa-144">*Erstellen und Bearbeiten von Themen*</span><span class="sxs-lookup"><span data-stu-id="866aa-144">*Create and edit topics*</span></span>

<span data-ttu-id="866aa-145">Thema Mitwirkende sind die Champions und Fachexperten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="866aa-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="866aa-146">Sie können Themen erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="866aa-146">They can create and edit topics.</span></span> 

<span data-ttu-id="866aa-147">Es wird empfohlen, dass Sie allen in Ihrer Organisation das Erstellen und Bearbeiten von Themen erlauben, da Themen Erfahrungen am besten funktionieren, wenn alle Benutzerinformationen freigeben können.</span><span class="sxs-lookup"><span data-stu-id="866aa-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="866aa-148">Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie für diese eine Sicherheitsgruppe, und geben Sie Sie während des Installationsvorgangs an.</span><span class="sxs-lookup"><span data-stu-id="866aa-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="866aa-149">Sie können festlegen, dass niemand Beiträge zu Themen leisten darf, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="866aa-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="866aa-150">Die Knowledge Manager können weiterhin Themen bearbeiten und erstellen.</span><span class="sxs-lookup"><span data-stu-id="866aa-150">Knowledge managers will still be able to edit and create topics.</span></span>

<span data-ttu-id="866aa-151">*Themen Betrachter*</span><span class="sxs-lookup"><span data-stu-id="866aa-151">*Topic viewers*</span></span>

<span data-ttu-id="866aa-152">Thema Betrachter können Informationen zu Themenseiten, in Suchergebnissen und wenn Themen im Inhalt wie SharePoint-Seiten hervorgehoben werden, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="866aa-153">Benutzer können nur entdeckte Themen anzeigen, wenn Sie Zugriff auf die Dateien und Seiten haben, in denen das Thema entdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="866aa-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="866aa-154">Beim Einrichten von Themen Ansichten stehen Ihnen folgende Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="866aa-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="866aa-155">**Jeder in meiner Organisation**</span><span class="sxs-lookup"><span data-stu-id="866aa-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="866aa-156">**Nur ausgewählte Personen oder Sicherheitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="866aa-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="866aa-157">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="866aa-157">**No one**</span></span>

<span data-ttu-id="866aa-158">Wir empfehlen **alle Mitarbeiter in meiner Organisation**, aber wenn Sie ein Pilotprojekt ausführen, können Sie nur ausgewählte Personen oder Sicherheitsgruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="866aa-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="866aa-159">Sie können auch **keines** auswählen, wenn Sie Themen Erfahrungen einrichten möchten, aber nicht zulassen, dass Personen noch angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-159">You can also choose **No one** if you want to set up topic experiences, but not allow people to see topics yet.</span></span> <span data-ttu-id="866aa-160">(Knowledge Manager haben weiterhin Zugriff, um die Themen anzeigen zu lassen und die Entscheidung zu unterstützen, Themen Erfahrungen allgemein verfügbar zu machen.)</span><span class="sxs-lookup"><span data-stu-id="866aa-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make topic experiences broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="866aa-161">Wissens Regeln</span><span class="sxs-lookup"><span data-stu-id="866aa-161">Knowledge rules</span></span>

<span data-ttu-id="866aa-162">Als Administrator können Sie bestimmte Themen aus thematischen Erfahrungen ausschließen.</span><span class="sxs-lookup"><span data-stu-id="866aa-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="866aa-163">Dies ist hilfreich, wenn Sie verhindern möchten, dass vertrauliche Daten in Themen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="866aa-164">Während Knowledge Manager Themen im Themen Center ausschließen können, sind die vom Administrator ausgegrenzten Themen auch für Wissensmanager nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="866aa-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="866aa-165">(Knowledge Manager können auch Themen im Themen Center nach der Ermittlung entfernen.)</span><span class="sxs-lookup"><span data-stu-id="866aa-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="866aa-166">Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie Sie zu einer CSV-Datei hinzufügen und die Datei hochladen.</span><span class="sxs-lookup"><span data-stu-id="866aa-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="866aa-167">Dies können Sie während der Installation oder später tun.</span><span class="sxs-lookup"><span data-stu-id="866aa-167">You can do this during setup or later.</span></span>

<span data-ttu-id="866aa-168">Die CSV-Datei muss die folgenden Parameter enthalten:</span><span class="sxs-lookup"><span data-stu-id="866aa-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="866aa-169">**Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="866aa-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="866aa-170">Sie können auf zwei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="866aa-170">There are two ways to do this:</span></span>
- <span data-ttu-id="866aa-171">**MatchType-Exact/Partial**: Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.</span><span class="sxs-lookup"><span data-stu-id="866aa-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="866aa-172">Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL*).</span><span class="sxs-lookup"><span data-stu-id="866aa-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="866aa-173">Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="866aa-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="866aa-174">Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis*, *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur*, nicht ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="866aa-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="866aa-175">**Steht für (optional)**: (wird auch als *Erweiterung* bezeichnet) Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.</span><span class="sxs-lookup"><span data-stu-id="866aa-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Themen in CSV-Vorlage ausschließen](../media/exclude-topics-csv.png) 

<span data-ttu-id="866aa-177">Sie können die CSV-Vorlage unten kopieren:</span><span class="sxs-lookup"><span data-stu-id="866aa-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="866aa-178">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="866aa-178">Administration</span></span>

<span data-ttu-id="866aa-179">Wenn Sie im Rahmen des Installationsvorgangs Themen Erfahrungen einrichten, wird automatisch ein Themen Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="866aa-179">When you set up topic experiences, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="866aa-180">Überlegen Sie, was Sie dem Themen Center nennen möchten und wie die URL sein soll.</span><span class="sxs-lookup"><span data-stu-id="866aa-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="866aa-181">Sie können den Namen und die URL als Teil des Installationsvorgangs festlegen, und Sie können den Namen (aber nicht die URL) später im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="866aa-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="866aa-182">Sie können nur ein Themen Center haben.</span><span class="sxs-lookup"><span data-stu-id="866aa-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="866aa-183">Prüfliste für Setup</span><span class="sxs-lookup"><span data-stu-id="866aa-183">Setup checklist</span></span>

<span data-ttu-id="866aa-184">Wenn Sie Themen Erfahrungen einrichten, benötigen Sie die folgenden Elemente, wenn Sie den Setup-Assistenten durchgehen:</span><span class="sxs-lookup"><span data-stu-id="866aa-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="866aa-185">Liste der einzuschließenden oder auszuschließenden Websites, wenn nicht alle Websites für die Themen Ermittlung eingeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="866aa-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="866aa-186">Sicherheitsgruppe für Themen Betrachter, wenn nicht allen Benutzern das Anzeigen von Themen gestattet wird</span><span class="sxs-lookup"><span data-stu-id="866aa-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="866aa-187">Sicherheitsgruppe für Thema Mitwirkende, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen gestattet wird</span><span class="sxs-lookup"><span data-stu-id="866aa-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="866aa-188">Sicherheitsgruppe für Thema Wissensmanager, wenn nicht allen Benutzern das Verwalten von Themen gestattet wird</span><span class="sxs-lookup"><span data-stu-id="866aa-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="866aa-189">Liste der vertraulichen Themen, die von der Thema Ermittlung ausgeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="866aa-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="866aa-190">Ein Name für Ihre Themen Center-Website</span><span class="sxs-lookup"><span data-stu-id="866aa-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="866aa-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="866aa-191">See also</span></span>

[<span data-ttu-id="866aa-192">Einrichten von Themen Erfahrungen</span><span class="sxs-lookup"><span data-stu-id="866aa-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="866aa-193">Verwalten der Themen Ermittlung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866aa-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="866aa-194">Verwalten der Themen Sichtbarkeit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866aa-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="866aa-195">Verwalten von Themen Berechtigungen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866aa-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="866aa-196">Ändern des Namens des Themen Centers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="866aa-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
