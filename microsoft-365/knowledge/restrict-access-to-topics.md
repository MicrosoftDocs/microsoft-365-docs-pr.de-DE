---
title: Einschränken des Zugriffs auf Themen
description: Vorgehensweise Ausschließen von Themen, damit diese nicht erkannt werden.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698960"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="b7d6e-103">Einschränken des Zugriffs auf Themen in Thema Erfahrungen</span><span class="sxs-lookup"><span data-stu-id="b7d6e-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="b7d6e-104">In Themenbereichen sollten die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht erkannt und für Ihre lizenzierten Benutzer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="b7d6e-105">Sie arbeiten beispielsweise an einem Projekt, für das Sie noch keine Informationen verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="b7d6e-106">Während Office 365 Berechtigungen für Websites, Dateien und andere Ressourcen verhindern, dass Benutzer in Themen vertrauliche Informationen von Benutzern anzeigen können, gibt es zusätzliche Schutzvorkehrungen, um zu verhindern, dass bestimmte Themen jemals erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="b7d6e-107">Während Knowledge-Administratoren die Einstellungen für das Wissensnetzwerk steuern, um zu verhindern, dass Themen entdeckt werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit Sie gemeinsam daran arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="b7d6e-108">In diesem Artikel wird beschrieben, wie Sie verhindern können, dass Themen über AI identifiziert oder in Ihrer Umgebung als zusätzliche Sicherheitsvorkehrungen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="b7d6e-109">Es ist wichtig zu beachten, dass die Benutzer in den Themen Erfahrungen keine Elemente in einem Thema anzeigen dürfen, auf die Sie über Office 365 Berechtigungen nicht zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="b7d6e-110">Selbst wenn ein Benutzer ein Thema, dessen Dateien, Websites und Seiten anzeigen kann, sind ihm keine Office 365 Berechtigungen zur Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="b7d6e-111">Stellen Sie sicher, dass die Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, sollten Sie die primäre Sicherheits Sicherung sein.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="b7d6e-112">Verhindern, dass Themen identifiziert werden</span><span class="sxs-lookup"><span data-stu-id="b7d6e-112">Prevent topics from being identified</span></span>

<span data-ttu-id="b7d6e-113">Der Wissens Administrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass er in der anfänglichen Indizierung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="b7d6e-114">Es gibt zwei Möglichkeiten, dies in den Einstellungen des Knowledge Network-Administrators im Microsoft 365 Admin Center zu tun.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="b7d6e-115">[Wählen Sie SharePoint-Websites aus, die von der Themen Ermittlung ausgeschlossen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)werden sollen: mit dieser Einstellung können Sie verhindern, dass bestimmte SharePoint-Websites für Themen gecrawlt werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="b7d6e-116">[Themen nach Namen ausschließen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="b7d6e-117">In den Einstellungen des Wissensnetzwerk Administrators kann ein Administrator eine Liste von Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="b7d6e-118">Sie können Themen ausschließen, die genaue oder partielle Übereinstimmungen mit einem Themen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="b7d6e-119">Verhindern, dass Themen von bestimmten Benutzern angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="b7d6e-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="b7d6e-120">Wissens Administratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="b7d6e-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="b7d6e-121">Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="b7d6e-122">In einer Pilotumgebung können Sie beispielsweise nur zulassen, dass eine kleine Gruppe von Benutzern Themen anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="b7d6e-123">Entfernen von Themen aus der Ansicht</span><span class="sxs-lookup"><span data-stu-id="b7d6e-123">Remove topics from being viewed</span></span>

<span data-ttu-id="b7d6e-124">Wissensmanager können auswählen, [Themen zu entfernen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) , damit Benutzer Sie nicht mehr sehen können.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="b7d6e-125">Auf der Seite **Themen verwalten** im **Themen Center** können Knowledge Manager auswählen, bestimmte Themen abzulehnen, um zu verhindern, dass Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="b7d6e-126">Themen können entfernt werden, unabhängig davon, ob Sie den Status "vorgeschlagen" oder "bestätigt" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="b7d6e-127">Entfernte Themen können bei Bedarf später als sichtbare Themen wieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b7d6e-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b7d6e-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b7d6e-128">See also</span></span>



  






