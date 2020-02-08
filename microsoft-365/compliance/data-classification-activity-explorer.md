---
title: Verwenden des Datenklassifizierungsaktivitäten-Explorers
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 8af23cac590eb226890979719f938b8e79099bb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595472"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="f4aa8-103">Anzeigen von Aktivitäten mit beschrifteten Inhalten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f4aa8-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="f4aa8-104">Auf den Registerkarten „Übersicht über die Datenklassifizierung“ und „Inhalts-Explorer“ erfahren Sie, welche Inhalte gefunden und beschriftet wurden und wo sich diese Inhalte befinden.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="f4aa8-105">Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="f4aa8-106">Der Aktivitäten-Explorer bietet eine Verlaufsanzeige.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-106">Activity explorer provides a historical view.</span></span>

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="f4aa8-108">Sie können die Daten filtern nach:</span><span class="sxs-lookup"><span data-stu-id="f4aa8-108">You can filter the data by:</span></span>

- <span data-ttu-id="f4aa8-109">Zeitraum:</span><span class="sxs-lookup"><span data-stu-id="f4aa8-109">date range</span></span>
- <span data-ttu-id="f4aa8-110">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="f4aa8-110">activity type</span></span>
- <span data-ttu-id="f4aa8-111">Speicherort</span><span class="sxs-lookup"><span data-stu-id="f4aa8-111">location</span></span>
- <span data-ttu-id="f4aa8-112">Benutzer</span><span class="sxs-lookup"><span data-stu-id="f4aa8-112">user</span></span>
- <span data-ttu-id="f4aa8-113">Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="f4aa8-113">sensitivity label</span></span>
- <span data-ttu-id="f4aa8-114">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="f4aa8-114">retention label</span></span>


<span data-ttu-id="f4aa8-115">Sie können die Daten in einer Liste oder in einem Balkendiagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4aa8-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f4aa8-116">Prerequisites</span></span>

<span data-ttu-id="f4aa8-117">Jedem Konto, das auf den Aktivitäten-Explorer zugreift und diesen verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="f4aa8-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="f4aa8-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f4aa8-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="f4aa8-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f4aa8-119">Office 365 (E5)</span></span>
- <span data-ttu-id="f4aa8-120">Advanced Compliance (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="f4aa8-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="f4aa8-121">Advanced Threat Intelligence (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="f4aa8-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="f4aa8-122">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="f4aa8-122">Activity type</span></span>

<span data-ttu-id="f4aa8-123">Microsoft 365 überwacht und berichtet über 12 Arten von Aktivitäten in SharePoint Online, OneDrive und Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="f4aa8-124">Endpunkte sind Benutzergeräte mit Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="f4aa8-125">Datei erstellt</span><span class="sxs-lookup"><span data-stu-id="f4aa8-125">File created</span></span>
- <span data-ttu-id="f4aa8-126">Datei geändert</span><span class="sxs-lookup"><span data-stu-id="f4aa8-126">File modified</span></span>
- <span data-ttu-id="f4aa8-127">Datei umbenannt</span><span class="sxs-lookup"><span data-stu-id="f4aa8-127">File renamed</span></span>
- <span data-ttu-id="f4aa8-128">Datei in die Cloud kopiert</span><span class="sxs-lookup"><span data-stu-id="f4aa8-128">File copied to cloud</span></span>
- <span data-ttu-id="f4aa8-129">Zugriff auf Datei durch eine nicht zulässige App</span><span class="sxs-lookup"><span data-stu-id="f4aa8-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="f4aa8-130">Datei gedruckt</span><span class="sxs-lookup"><span data-stu-id="f4aa8-130">File printed</span></span>
- <span data-ttu-id="f4aa8-131">Datei auf Wechselmedien kopiert</span><span class="sxs-lookup"><span data-stu-id="f4aa8-131">File copied to removable media</span></span>
- <span data-ttu-id="f4aa8-132">Datei auf die Netzwerkfreigabe kopiert</span><span class="sxs-lookup"><span data-stu-id="f4aa8-132">File copied to network share</span></span>
- <span data-ttu-id="f4aa8-133">Datei gelesen</span><span class="sxs-lookup"><span data-stu-id="f4aa8-133">File read</span></span>
- <span data-ttu-id="f4aa8-134">Datei in die Zwischenablage kopiert</span><span class="sxs-lookup"><span data-stu-id="f4aa8-134">file copied to clipboard</span></span>
- <span data-ttu-id="f4aa8-135">Bezeichnung angewendet</span><span class="sxs-lookup"><span data-stu-id="f4aa8-135">Label applied</span></span>
- <span data-ttu-id="f4aa8-136">Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)</span><span class="sxs-lookup"><span data-stu-id="f4aa8-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="f4aa8-137">Wenn Sie wissen, welche Aktionen mit Ihren vertraulichen beschrifteten Inhalten durchgeführt werden, können Sie feststellen, ob die von Ihnen bereits eingerichteten Steuerelemente, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), wirksam sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="f4aa8-138">Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="f4aa8-139">Sobald Ihre Filter festgelegt sind, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f4aa8-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="f4aa8-140">Zeigen Sie mit der Maus auf ein Segment des Balkendiagramms, um die Anzahl der Elemente anzuzeigen, die in diese Kategorie fallen ![Mauszeiger Aktivitäten-Explorer](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="f4aa8-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="f4aa8-141">Exportieren von Daten</span><span class="sxs-lookup"><span data-stu-id="f4aa8-141">export the data</span></span>
- <span data-ttu-id="f4aa8-142">Wählen Sie ein beliebiges Element in der Liste aus und zeigen Sie die Details der Aktion im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="f4aa8-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![Flyout für Details des Aktivitäten-Explorers](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="f4aa8-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4aa8-144">See also</span></span>
- [<span data-ttu-id="f4aa8-145">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f4aa8-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f4aa8-146">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f4aa8-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="f4aa8-147">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="f4aa8-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="f4aa8-148">Übersicht über Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f4aa8-148">Overview of retention policies</span></span>](retention-policies.md)
