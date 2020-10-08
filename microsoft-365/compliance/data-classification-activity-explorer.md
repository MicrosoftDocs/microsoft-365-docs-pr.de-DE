---
title: Erste Schritte mit dem Aktivitäten-Explorer
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 0175f41ca3fbcfc685acf933cc0cd97af6aa61ad
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379202"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="f21b4-103">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="f21b4-103">Get started with activity explorer</span></span>

<span data-ttu-id="f21b4-104">Auf den Registerkarten „Übersicht über die Datenklassifizierung“ und „Inhalts-Explorer“ erfahren Sie, welche Inhalte gefunden und beschriftet wurden und wo sich diese Inhalte befinden.</span><span class="sxs-lookup"><span data-stu-id="f21b4-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="f21b4-105">Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht.</span><span class="sxs-lookup"><span data-stu-id="f21b4-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="f21b4-106">Der Aktivitäten-Explorer bietet eine Verlaufsanzeige.</span><span class="sxs-lookup"><span data-stu-id="f21b4-106">Activity explorer provides a historical view.</span></span>

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="f21b4-108">Es stehen über 30 verschiedene Filter zur Verfügung, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="f21b4-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="f21b4-109">Zeitraum:</span><span class="sxs-lookup"><span data-stu-id="f21b4-109">date range</span></span>
- <span data-ttu-id="f21b4-110">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="f21b4-110">activity type</span></span>
- <span data-ttu-id="f21b4-111">Speicherort</span><span class="sxs-lookup"><span data-stu-id="f21b4-111">location</span></span>
- <span data-ttu-id="f21b4-112">Benutzer</span><span class="sxs-lookup"><span data-stu-id="f21b4-112">user</span></span>
- <span data-ttu-id="f21b4-113">Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="f21b4-113">sensitivity label</span></span>
- <span data-ttu-id="f21b4-114">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="f21b4-114">retention label</span></span>
- <span data-ttu-id="f21b4-115">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="f21b4-115">file path</span></span>
- <span data-ttu-id="f21b4-116">DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f21b4-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="f21b4-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f21b4-117">Prerequisites</span></span>

<span data-ttu-id="f21b4-118">Jedem Konto, das auf die Datenklassifizierung zugreift und sie verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="f21b4-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="f21b4-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f21b4-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="f21b4-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f21b4-120">Office 365 (E5)</span></span>
- <span data-ttu-id="f21b4-121">Advanced Compliance (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="f21b4-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="f21b4-122">Advanced Threat Intelligence (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="f21b4-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="f21b4-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f21b4-123">Permissions</span></span>

 <span data-ttu-id="f21b4-124">Um Zugriff auf die Registerkarte „Aktivitäts-Explorer“ zu erhalten, muss einem Konto die Mitgliedschaft in einer dieser Rollen oder Rollengruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f21b4-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="f21b4-125">**Microsoft 365-Rollengruppen**</span><span class="sxs-lookup"><span data-stu-id="f21b4-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="f21b4-126">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="f21b4-126">Global administrator</span></span>
- <span data-ttu-id="f21b4-127">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="f21b4-127">Compliance administrator</span></span>
- <span data-ttu-id="f21b4-128">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="f21b4-128">Security administrator</span></span>
- <span data-ttu-id="f21b4-129">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="f21b4-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="f21b4-130">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="f21b4-130">Activity type</span></span>

<span data-ttu-id="f21b4-131">Microsoft 365 überwacht und berichtet über Arten von Aktivitäten in SharePoint Online und OneDrive, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="f21b4-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="f21b4-132">Bezeichnung angewendet</span><span class="sxs-lookup"><span data-stu-id="f21b4-132">label applied</span></span>
- <span data-ttu-id="f21b4-133">Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)</span><span class="sxs-lookup"><span data-stu-id="f21b4-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="f21b4-134">Simulation der automatischen Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="f21b4-134">auto-labeling simulation</span></span>

<span data-ttu-id="f21b4-135">Wenn Sie wissen, welche Aktionen mit Ihren vertraulichen beschrifteten Inhalten durchgeführt werden, können Sie feststellen, ob die von Ihnen bereits eingerichteten Steuerelemente, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), wirksam sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f21b4-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="f21b4-136">Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="f21b4-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="f21b4-137">Der Aktivitäts-Explorer überwacht derzeit keine Aufbewahrungsaktivitäten für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f21b4-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="f21b4-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f21b4-138">See also</span></span>
- [<span data-ttu-id="f21b4-139">Weitere Informationen zu Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f21b4-139">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f21b4-140">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f21b4-140">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="f21b4-141">Entitätsdefinitionen für Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="f21b4-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

