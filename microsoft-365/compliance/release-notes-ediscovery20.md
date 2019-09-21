---
title: Anmerkungen zur Version für Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Dieser Artikel enthält die Anmerkungen zu dieser Version für Advanced eDiscovery.
ms.openlocfilehash: f3d26b1c84746581ccf32e1d4aada079fc21dfb3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082582"
---
# <a name="release-notes-for-advanced-ediscovery"></a><span data-ttu-id="57e2a-103">Anmerkungen zur Version für Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57e2a-103">Release notes for Advanced eDiscovery</span></span>

<span data-ttu-id="57e2a-104">Das Public Preview-Programm für Advanced eDiscovery ist die Möglichkeit, frühzeitig Zugriff auf die bevorstehenden Funktionen und Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="57e2a-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="57e2a-105">Um frühzeitig Zugriff auf die neuesten Funktionen zu erhalten, erstellen und verwenden Sie einfach einen erweiterten eDiscovery-Fall im Security #a0 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="57e2a-105">To get early access to the newest features, just create and use an Advanced eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="57e2a-106">Weitere Informationen finden Sie unter [Create a New Case](create-new-ediscovery-case.md).</span><span class="sxs-lookup"><span data-stu-id="57e2a-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="57e2a-107">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="57e2a-107">Known issues</span></span>

<span data-ttu-id="57e2a-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="57e2a-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="57e2a-109">Die Daten, die einem Formular entsprechen, das vor dem 31. Januar 2019 erstellt wurde, können nicht durchsucht werden, wenn das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57e2a-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="57e2a-110">Formulare, die nach diesem Datum erstellt wurden, stehen für die Suche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="57e2a-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="57e2a-111">Ein von einem Benutzer erstelltes Formular kann weiterhin Antworten erhalten, auch wenn der Benutzer, der das Formular erstellt hat, gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="57e2a-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="57e2a-112">Die entsprechenden Daten für diese Antworten (die nach dem Löschen des Depot Postfachs aufgetreten sind) sind jedoch nicht durchsuchbar, wenn Sie das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwenden.</span><span class="sxs-lookup"><span data-stu-id="57e2a-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span>
 
<span data-ttu-id="57e2a-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="57e2a-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="57e2a-114">Wenn ein Benutzer ein Sway unmittelbar vor dem Löschen des Benutzerkontos für den Besitzer dieses Sways bearbeitet, sind diese Änderungen möglicherweise nicht durchsuchbar, wenn das Such Tool in Advanced eDiscovery zum Durchsuchen von Depot Postfächern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57e2a-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="57e2a-115">Sway Blocks ändert sich in ein Sway, sobald ein Signal empfangen wird, dass das Konto gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="57e2a-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="57e2a-116">Es gibt jedoch eine kleine Chance, dass ein Sway bearbeitet werden kann, bevor dieses Signal empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="57e2a-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="57e2a-117">In dieser Version behobene Probleme</span><span class="sxs-lookup"><span data-stu-id="57e2a-117">Issues fixed in this release</span></span>

- <span data-ttu-id="57e2a-118">DCR: Ausnahmebehandlung für nicht indizierte Elemente und verwaiste Elemente</span><span class="sxs-lookup"><span data-stu-id="57e2a-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="57e2a-119">DCR: Benachrichtigungen halten</span><span class="sxs-lookup"><span data-stu-id="57e2a-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="57e2a-120">DCR: Verwalter in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57e2a-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="57e2a-121">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="57e2a-121">What’s new</span></span>

- <span data-ttu-id="57e2a-122">Neu **gestaltete Navigation im Security #a0 Compliance Center** – Advanced eDiscovery hat ein neues Aussehen und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="57e2a-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery has a new look and feel.</span></span> <span data-ttu-id="57e2a-123">Verwenden Sie Advanced eDiscovery, um einen größeren Teil Ihres Fall Workflows zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="57e2a-123">Use Advanced eDiscovery to manage more of your case workflow.</span></span>

- <span data-ttu-id="57e2a-124">**Case Management** – zusätzliche Unterstützung für neue Falltypen.</span><span class="sxs-lookup"><span data-stu-id="57e2a-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="57e2a-125">Sie können auch Ihre aktuellen und bevorzugten Fälle auswählen und speichern.</span><span class="sxs-lookup"><span data-stu-id="57e2a-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="57e2a-126">Verfolgen und Überwachen von Aktivitäten innerhalb und über mehrere Fälle mithilfe neuer Dashboards.</span><span class="sxs-lookup"><span data-stu-id="57e2a-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="57e2a-127">**Depotverwaltung** – hinzufügen und Entfernen von Benutzern als Datenverwalter in einem Fall.</span><span class="sxs-lookup"><span data-stu-id="57e2a-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="57e2a-128">**Exchange-, OneDrive-und** Microsoft Teams-Integration – fügen Sie einem Fall automatisch das aktuelle Postfach des Benutzers, das OneDrive für Unternehmen-Konto und die Microsoft Teams-Websites hinzu.</span><span class="sxs-lookup"><span data-stu-id="57e2a-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="57e2a-129">**Depotbank Communications** – senden und Verwalten von Benachrichtigungen über rechtliche Aufbewahrungsdaten im Namen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="57e2a-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="57e2a-130">**Depot Portal** – neues Portal für depotverwalter für den Zugriff auf Ihre aktiven Aufbewahrungs Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="57e2a-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="57e2a-131">**Deep Indexing** – erneutes durchforsten von teilweise indizierten Elementen bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="57e2a-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="57e2a-132">**Fehler** Korrektur – beheben oder Herunterladen von Verarbeitungsfehlern; Dies umfasst die Korrektur Unterstützung für große Dateitypen, kennwortgeschützte Dateien und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="57e2a-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="57e2a-133">**Verbesserungen bei der Suche** – erstellen Sie eine Suche, indem Sie Verwalter und/oder Standorte identifizieren.</span><span class="sxs-lookup"><span data-stu-id="57e2a-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="57e2a-134">**Überprüfen von Sätzen** – verwalten, nachverfolgen und Überwachen von statischen Dokumentensätzen.</span><span class="sxs-lookup"><span data-stu-id="57e2a-134">**Review sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="57e2a-135">**Review** – verwenden Sie eine systemeigene, Text-und Near-Native-Ansicht, um Dokumente zu überprüfen, die Ihrem Überprüfungs hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="57e2a-135">**Review** – Use a native, text, and near-native view to review documents added to your review set.</span></span>

- <span data-ttu-id="57e2a-136">**Redact, Tags und Anmerkungen** – Redact Text, wendet Tags an und macht bei der Überprüfung von Dokumenten Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="57e2a-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="57e2a-137">**Analyse-powered Review**– nutzen Sie die erweiterte eDiscovery-Analyse, um Ergebnisse innerhalb eines Überprüfungs Satzes zu suchen, zu suchen und zu cullieren.</span><span class="sxs-lookup"><span data-stu-id="57e2a-137">**Analytics-powered review**– Leverage Advanced eDiscovery analytics to find, search, and cull results within a review set.</span></span>

- <span data-ttu-id="57e2a-138">**Jobs** – Status der lang dauernden Prozesse nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="57e2a-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="57e2a-139">**Neue Überwachungsaktivitäten** – verfolgen und Anzeigen neuer Überwachungsaktivitäten für erweiterte eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="57e2a-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
