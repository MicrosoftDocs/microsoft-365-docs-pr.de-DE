---
title: Einschränken des Zugriffs auf Themen
description: So schließen Sie Themen aus, um zu verhindern, dass sie gefunden werden.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976145"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="9550f-103">Einschränken des Zugriffs auf Themen in Themenerfahrungen</span><span class="sxs-lookup"><span data-stu-id="9550f-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="9550f-104">In den Themenerfahrungen möchten Die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht ermittelt und für Ihre lizenzierten Benutzer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="9550f-105">Sie arbeiten beispielsweise an einem Projekt, zu dem Sie noch keine Informationen verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9550f-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="9550f-106">Während Office 365-Berechtigungen für Websites, Dateien und andere Ressourcen Verhindern, dass Benutzer von Themenerfahrungen vertrauliche Informationen in Themen anzeigen, gibt es zusätzliche Sicherheitsvorkehrungen, um zu verhindern, dass bestimmte Themen jemals gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="9550f-107">Während Wissensadministratoren die Einstellungen des Wissensnetzwerks steuern, um zu verhindern, dass Themen gefunden werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit sie gemeinsam daran arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="9550f-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="9550f-108">In diesem Artikel werden Möglichkeiten beschrieben, wie Sie verhindern können, dass Themen über KI identifiziert oder in Ihrer Umgebung als zusätzliche Sicherheitsvorkehrungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="9550f-109">Es ist wichtig zu beachten, dass Benutzer in den Themenerfahrungen nichts in einem Thema anzeigen dürfen, auf das sie nicht über Office 365-Berechtigungen zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="9550f-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="9550f-110">Auch wenn ein Benutzer ein Thema anzeigen kann, sind seine Dateien, Websites und Seiten, für die er keine Office 365-Berechtigungen zum Anzeigen hat, für sie nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9550f-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="9550f-111">Stellen Sie sicher, dass Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, damit die Sicherheit gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="9550f-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="9550f-112">Verhindern, dass Themen identifiziert werden</span><span class="sxs-lookup"><span data-stu-id="9550f-112">Prevent topics from being identified</span></span>

<span data-ttu-id="9550f-113">Der Wissensadministrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass sie bei der anfänglichen Indizierung gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="9550f-114">Es gibt zwei Möglichkeiten, dies in den Administratoreinstellungen des Knowledge Network im Microsoft 365 Admin Center zu tun.</span><span class="sxs-lookup"><span data-stu-id="9550f-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="9550f-115">[Auswählen von SharePoint-Websites, die von der](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)Themenermittlung ausgeschlossen werden: Sie können diese Einstellung verwenden, um zu verhindern, dass bestimmte SharePoint-Websites nach Themen gecrawlt werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="9550f-116">[Themen nach Namen ausschließen:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="9550f-117">In den Administratoreinstellungen des Knowledge Network kann ein Administrator eine Liste von Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9550f-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="9550f-118">Sie können Themen ausschließen, die genaue oder teilweise Übereinstimmungen mit einem Themennamen haben.</span><span class="sxs-lookup"><span data-stu-id="9550f-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="9550f-119">Verhindern, dass Themen von bestimmten Benutzern angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="9550f-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="9550f-120">Wissensadministratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="9550f-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="9550f-121">Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9550f-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="9550f-122">In einer Pilotumgebung können Sie beispielsweise nur einer kleinen Gruppe von Benutzern erlauben, Themen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="9550f-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="9550f-123">Entfernen von Themen aus der Anzeige</span><span class="sxs-lookup"><span data-stu-id="9550f-123">Remove topics from being viewed</span></span>

<span data-ttu-id="9550f-124">Wissensmanager können Themen [entfernen,](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) damit Benutzer sie nicht mehr sehen können.</span><span class="sxs-lookup"><span data-stu-id="9550f-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="9550f-125">Auf der **Seite "Themen verwalten"** im **Themencenter** können Knowledge Manager bestimmte Themen ablehnen, um zu verhindern, dass sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="9550f-126">Themen können unabhängig davon entfernt werden, ob sie sich in einem vorgeschlagenen oder bestätigten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="9550f-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="9550f-127">Entfernte Themen können später bei Bedarf wieder als angezeigte Themen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9550f-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="9550f-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9550f-128">See also</span></span>



  






