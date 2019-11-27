---
title: Verwenden des Datenklassifizierungsaktivitäten-Explorers
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268961"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="eb478-103">Anzeigen von Aktivitäten mit beschrifteten Inhalten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="eb478-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="eb478-104">Auf den Registerkarten „Übersicht über die Datenklassifizierung“ und „Inhalts-Explorer“ erfahren Sie, welche Inhalte gefunden und beschriftet wurden und wo sich diese Inhalte befinden.</span><span class="sxs-lookup"><span data-stu-id="eb478-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="eb478-105">Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht.</span><span class="sxs-lookup"><span data-stu-id="eb478-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="eb478-106">Der Aktivitäten-Explorer bietet eine Verlaufsanzeige.</span><span class="sxs-lookup"><span data-stu-id="eb478-106">Activity explorer provides a historical view.</span></span>

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="eb478-108">Sie können die Daten filtern nach:</span><span class="sxs-lookup"><span data-stu-id="eb478-108">You can filter the data by:</span></span>

- <span data-ttu-id="eb478-109">Zeitraum:</span><span class="sxs-lookup"><span data-stu-id="eb478-109">Date range</span></span>
- <span data-ttu-id="eb478-110">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="eb478-110">Activity type</span></span>
- <span data-ttu-id="eb478-111">Speicherort</span><span class="sxs-lookup"><span data-stu-id="eb478-111">location</span></span>
- <span data-ttu-id="eb478-112">Benutzer</span><span class="sxs-lookup"><span data-stu-id="eb478-112">user</span></span>
- <span data-ttu-id="eb478-113">Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="eb478-113">For sensitivity label usage:</span></span>
- <span data-ttu-id="eb478-114">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="eb478-114">Retention Label</span></span>


<span data-ttu-id="eb478-115">Sie können die Daten in einer Liste oder in einem Balkendiagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb478-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="activity-type"></a><span data-ttu-id="eb478-116">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="eb478-116">Activity type</span></span>

<span data-ttu-id="eb478-117">Microsoft 365 überwacht und berichtet über 12 Arten von Aktivitäten in SharePoint Online, OneDrive und Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="eb478-117">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="eb478-118">Endpunkte sind Benutzergeräte mit Windows 10.</span><span class="sxs-lookup"><span data-stu-id="eb478-118">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="eb478-119">Datei erstellt</span><span class="sxs-lookup"><span data-stu-id="eb478-119">File is created</span></span>
- <span data-ttu-id="eb478-120">Datei geändert</span><span class="sxs-lookup"><span data-stu-id="eb478-120">File modified</span></span>
- <span data-ttu-id="eb478-121">Datei umbenannt</span><span class="sxs-lookup"><span data-stu-id="eb478-121">File renamed</span></span>
- <span data-ttu-id="eb478-122">Datei in die Cloud kopiert</span><span class="sxs-lookup"><span data-stu-id="eb478-122">File copied to cloud</span></span>
- <span data-ttu-id="eb478-123">Zugriff auf Datei durch eine nicht zulässige App</span><span class="sxs-lookup"><span data-stu-id="eb478-123">File accessed by unallowed app</span></span>
- <span data-ttu-id="eb478-124">Datei gedruckt</span><span class="sxs-lookup"><span data-stu-id="eb478-124">File printed</span></span>
- <span data-ttu-id="eb478-125">Datei auf Wechselmedien kopiert</span><span class="sxs-lookup"><span data-stu-id="eb478-125">File copied to removable media</span></span>
- <span data-ttu-id="eb478-126">Datei auf die Netzwerkfreigabe kopiert</span><span class="sxs-lookup"><span data-stu-id="eb478-126">File copied to network share</span></span>
- <span data-ttu-id="eb478-127">Datei gelesen</span><span class="sxs-lookup"><span data-stu-id="eb478-127">File read</span></span>
- <span data-ttu-id="eb478-128">Datei in die Zwischenablage kopiert</span><span class="sxs-lookup"><span data-stu-id="eb478-128">file copied to clipboard</span></span>
- <span data-ttu-id="eb478-129">Bezeichnung angewendet</span><span class="sxs-lookup"><span data-stu-id="eb478-129">Label protection is applied</span></span>
- <span data-ttu-id="eb478-130">Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)</span><span class="sxs-lookup"><span data-stu-id="eb478-130">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="eb478-131">Wenn Sie wissen, welche Aktionen mit Ihren vertraulichen beschrifteten Inhalten durchgeführt werden, können Sie feststellen, ob die von Ihnen bereits eingerichteten Steuerelemente, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), wirksam sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="eb478-131">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="eb478-132">Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="eb478-132">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="eb478-133">Sobald Ihre Filter festgelegt sind, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="eb478-133">Once your filters are set, you can:</span></span>

- <span data-ttu-id="eb478-134">Zeigen Sie mit der Maus auf ein Segment des Balkendiagramms, um die Anzahl der Elemente anzuzeigen, die in diese Kategorie fallen ![Mauszeiger Aktivitäten-Explorer](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="eb478-134">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="eb478-135">Exportieren von Daten</span><span class="sxs-lookup"><span data-stu-id="eb478-135">The variable to export  the data to.</span></span>
- <span data-ttu-id="eb478-136">Wählen Sie ein beliebiges Element in der Liste aus und zeigen Sie die Details der Aktion im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="eb478-136">select any given item from the list and view the details of the action in the fly-out</span></span>

![Flyout für Details des Aktivitäten-Explorers](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="eb478-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb478-138">See also</span></span>
- [<span data-ttu-id="eb478-139">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="eb478-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="eb478-140">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="eb478-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="eb478-141">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="eb478-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="eb478-142">Übersicht über Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eb478-142">Overview of retention policies</span></span>](retention-policies.md)