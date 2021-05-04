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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114007"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="2fae0-103">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="2fae0-103">Get started with activity explorer</span></span>

<span data-ttu-id="2fae0-104">Die [](data-classification-overview.md) Datenklassifizierungsübersicht und die Registerkarten des [Inhalts-Explorers](data-classification-content-explorer.md) bieten Ihnen Einen Überblick darüber, welche Inhalte erkannt und gekennzeichnet wurden und wo sich dieser Inhalt befindet.</span><span class="sxs-lookup"><span data-stu-id="2fae0-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="2fae0-105">Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht.</span><span class="sxs-lookup"><span data-stu-id="2fae0-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="2fae0-106">Der Aktivitäts-Explorer bietet eine verlaufshistorische Ansicht der Aktivitäten in Ihren beschriftet inhalten.</span><span class="sxs-lookup"><span data-stu-id="2fae0-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="2fae0-107">Die Aktivitätsinformationen werden aus Microsoft 365 einheitlichen Überwachungsprotokollen gesammelt, transformiert und in der Benutzeroberfläche des Aktivitäts-Explorers verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="2fae0-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="2fae0-109">Es stehen über 30 verschiedene Filter zur Verfügung, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="2fae0-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="2fae0-110">Zeitraum:</span><span class="sxs-lookup"><span data-stu-id="2fae0-110">date range</span></span>
- <span data-ttu-id="2fae0-111">Aktivitätstyp</span><span class="sxs-lookup"><span data-stu-id="2fae0-111">activity type</span></span>
- <span data-ttu-id="2fae0-112">Speicherort</span><span class="sxs-lookup"><span data-stu-id="2fae0-112">location</span></span>
- <span data-ttu-id="2fae0-113">Benutzer</span><span class="sxs-lookup"><span data-stu-id="2fae0-113">user</span></span>
- <span data-ttu-id="2fae0-114">Vertraulichkeitsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="2fae0-114">sensitivity label</span></span>
- <span data-ttu-id="2fae0-115">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="2fae0-115">retention label</span></span>
- <span data-ttu-id="2fae0-116">Dateipfad</span><span class="sxs-lookup"><span data-stu-id="2fae0-116">file path</span></span>
- <span data-ttu-id="2fae0-117">DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="2fae0-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="2fae0-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2fae0-118">Prerequisites</span></span>

<span data-ttu-id="2fae0-119">Jedem Konto, das auf die Datenklassifizierung zugreift und sie verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="2fae0-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="2fae0-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2fae0-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="2fae0-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2fae0-121">Office 365 (E5)</span></span>
- <span data-ttu-id="2fae0-122">Advanced Compliance (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="2fae0-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="2fae0-123">Advanced Threat Intelligence (E5)-Add-on</span><span class="sxs-lookup"><span data-stu-id="2fae0-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="2fae0-124">Microsoft 365 E5/A5 Info Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="2fae0-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="2fae0-125">Microsoft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="2fae0-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="2fae0-126">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2fae0-126">Permissions</span></span>

 <span data-ttu-id="2fae0-127">Um Zugriff auf die Registerkarte Aktivitäts-Explorer zu erhalten, muss einem Konto explizit die Mitgliedschaft in einer dieser Rollengruppen zugewiesen oder der Rolle explizit erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="2fae0-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="2fae0-128">**Microsoft 365-Rollengruppen**</span><span class="sxs-lookup"><span data-stu-id="2fae0-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="2fae0-129">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-129">Global administrator</span></span>
- <span data-ttu-id="2fae0-130">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-130">Compliance administrator</span></span>
- <span data-ttu-id="2fae0-131">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-131">Security administrator</span></span>
- <span data-ttu-id="2fae0-132">Compliancedatenadministrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-132">Compliance data administrator</span></span>

<span data-ttu-id="2fae0-133">**Microsoft 365 Rollen**</span><span class="sxs-lookup"><span data-stu-id="2fae0-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="2fae0-134">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-134">Compliance administrator</span></span>
- <span data-ttu-id="2fae0-135">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="2fae0-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="2fae0-136">Aktivitätstypen</span><span class="sxs-lookup"><span data-stu-id="2fae0-136">Activity types</span></span>

<span data-ttu-id="2fae0-137">Der Aktivitäts-Explorer sammelt Aktivitätsinformationen aus den Überwachungsprotokollen für mehrere Quellen von Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="2fae0-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="2fae0-138">Ausführlichere Informationen dazu, welche Bezeichnungsaktivität es in den Aktivitäts-Explorer ermöglicht, finden Sie unter [Bezeichnungsereignisse, die im Aktivitäts-Explorer verfügbar sind.](data-classification-activity-explorer-available-events.md)</span><span class="sxs-lookup"><span data-stu-id="2fae0-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="2fae0-139">**Vertraulichkeitsbezeichnungsaktivitäten** und Aufbewahrungsbezeichnungsaktivitäten aus Office systemeigenen Anwendungen, Azure Information Protection-Add-Ins, SharePoint Online, Exchange Online (nur Vertraulichkeitsbezeichnungen) und OneDrive. </span><span class="sxs-lookup"><span data-stu-id="2fae0-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="2fae0-140">Einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2fae0-140">Some examples are:</span></span>

- <span data-ttu-id="2fae0-141">Bezeichnung angewendet</span><span class="sxs-lookup"><span data-stu-id="2fae0-141">label applied</span></span>
- <span data-ttu-id="2fae0-142">Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)</span><span class="sxs-lookup"><span data-stu-id="2fae0-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="2fae0-143">Simulation der automatischen Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="2fae0-143">auto-labeling simulation</span></span>
- <span data-ttu-id="2fae0-144">Datei lesen</span><span class="sxs-lookup"><span data-stu-id="2fae0-144">file read</span></span> 

<span data-ttu-id="2fae0-145">**Azure Information Protection (AIP)-Scanner und AIP-Clients**</span><span class="sxs-lookup"><span data-stu-id="2fae0-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="2fae0-146">Angewendeter Schutz</span><span class="sxs-lookup"><span data-stu-id="2fae0-146">protection applied</span></span>
- <span data-ttu-id="2fae0-147">Schutz geändert</span><span class="sxs-lookup"><span data-stu-id="2fae0-147">protection changed</span></span>
- <span data-ttu-id="2fae0-148">Schutz entfernt</span><span class="sxs-lookup"><span data-stu-id="2fae0-148">protection removed</span></span>
- <span data-ttu-id="2fae0-149">Ermittelte Dateien</span><span class="sxs-lookup"><span data-stu-id="2fae0-149">files discovered</span></span> 

<span data-ttu-id="2fae0-150">Der Aktivitäts-Explorer sammelt außerdem **Ereignisse** aus Exchange Online, SharePoint Online, OneDrive, Teams Chat und Kanal (Vorschau), lokalen SharePoint-Ordnern und Bibliotheken sowie lokalen Dateifreigaben und Windows 10-Geräten über **DLP (Endpoint Data Loss Prevention).**</span><span class="sxs-lookup"><span data-stu-id="2fae0-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="2fae0-151">Einige Beispielereignisse von Windows 10 sind Datei:</span><span class="sxs-lookup"><span data-stu-id="2fae0-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="2fae0-152">Löschvorgänge</span><span class="sxs-lookup"><span data-stu-id="2fae0-152">deletions</span></span>
- <span data-ttu-id="2fae0-153">creations</span><span class="sxs-lookup"><span data-stu-id="2fae0-153">creations</span></span>
- <span data-ttu-id="2fae0-154">in die Zwischenablage kopiert</span><span class="sxs-lookup"><span data-stu-id="2fae0-154">copied to clipboard</span></span>
- <span data-ttu-id="2fae0-155">geändert</span><span class="sxs-lookup"><span data-stu-id="2fae0-155">modified</span></span>
- <span data-ttu-id="2fae0-156">Lesen</span><span class="sxs-lookup"><span data-stu-id="2fae0-156">read</span></span>
- <span data-ttu-id="2fae0-157">gedruckt</span><span class="sxs-lookup"><span data-stu-id="2fae0-157">printed</span></span>
- <span data-ttu-id="2fae0-158">umbenannt</span><span class="sxs-lookup"><span data-stu-id="2fae0-158">renamed</span></span>
- <span data-ttu-id="2fae0-159">in die Netzwerkfreigabe kopiert</span><span class="sxs-lookup"><span data-stu-id="2fae0-159">copied to network share</span></span>
- <span data-ttu-id="2fae0-160">Zugriff durch nicht zugelassene App</span><span class="sxs-lookup"><span data-stu-id="2fae0-160">accessed by unallowed app</span></span> 

<span data-ttu-id="2fae0-161">Der Wert des Verständnisses, welche Aktionen mit Ihren vertraulich gekennzeichneten Inhalten ergriffen werden, ist, dass Sie sehen können, ob die steuerelemente, die Sie bereits ergriffen haben, z. B. verhinderung von Datenverlusten wirksam sind oder nicht. [](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="2fae0-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="2fae0-162">Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="2fae0-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="2fae0-163">Der Aktivitäts-Explorer überwacht derzeit keine Aufbewahrungsaktivitäten für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2fae0-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fae0-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fae0-164">See also</span></span>

- [<span data-ttu-id="2fae0-165">Weitere Informationen zu Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="2fae0-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="2fae0-166">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="2fae0-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="2fae0-167">Informationen zu Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="2fae0-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="2fae0-168">Informationen zur Datenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="2fae0-168">Learn about data classification</span></span>](data-classification-overview.md)
