---
title: Informationen zu Datensätzen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr über Datensätze, um Sie beim Implementieren einer Datensatzverwaltungslösung in Microsoft 365 zu unterstützen.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685441"
---
# <a name="learn-about-records"></a><span data-ttu-id="66cbd-103">Informationen zu Datensätzen</span><span class="sxs-lookup"><span data-stu-id="66cbd-103">Learn about records</span></span>

><span data-ttu-id="66cbd-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="66cbd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="66cbd-105">Die Verwaltung von Datensätzen in Microsoft 365 hilft Ihrer Organisation bei der Einhaltung von Unternehmensrichtlinien und gesetzlichen oder regulatorischer Verpflichtungen bei gleichzeitiger Verringerung der Risiken und der gesetzlichen Haftung.</span><span class="sxs-lookup"><span data-stu-id="66cbd-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="66cbd-106">Wenn Inhalt als Datensatz markiert ist:</span><span class="sxs-lookup"><span data-stu-id="66cbd-106">When content is marked as a record:</span></span>

- <span data-ttu-id="66cbd-107">Die Elemente werden hinsichtlich der [zulässigen oder blockierten Aktionen](#compare-restrictions-for-what-actions-are-allowed-or-blocked) eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="66cbd-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="66cbd-108">Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.</span><span class="sxs-lookup"><span data-stu-id="66cbd-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="66cbd-109">Sie haben einen Verfügungsnachweis, wenn die Elemente am Ende ihrer Aufbewahrungsfrist gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="66cbd-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="66cbd-110">Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="66cbd-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="66cbd-111">Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.</span><span class="sxs-lookup"><span data-stu-id="66cbd-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="66cbd-112">Durch die Verwendung von Aufbewahrungsbezeichnungen zum Markieren von Inhalten als Datensätze können Sie eine einzige und konsistente Strategie für die Verwaltung von Datensätzen in Ihrer Microsoft 365-Umgebung implementieren.</span><span class="sxs-lookup"><span data-stu-id="66cbd-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="66cbd-113">Vergleichen Sie die Einschränkungen für die zulässigen oder blockierten Aktionen</span><span class="sxs-lookup"><span data-stu-id="66cbd-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="66cbd-114">Verwenden Sie die folgende Tabelle, um zu ermitteln, welche Einschränkungen für den Inhalt durch das Anwenden einer Standardaufbewahrungsbezeichnung und von Aufbewahrungsbezeichnungen, die den Inhalt als Datensatz kennzeichnen, gelten.</span><span class="sxs-lookup"><span data-stu-id="66cbd-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="66cbd-115">Eine Standardaufbewahrungsbezeichnung kann Daten speichern, ohne den Inhalt als Datensatz zu markieren.</span><span class="sxs-lookup"><span data-stu-id="66cbd-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="66cbd-116">Der Vollständigkeit halber enthält die Tabelle Spalten für einen gesperrten und entsperrten Datensatz, die für SharePoint und OneDrive gelten, jedoch nicht für Exchange.</span><span class="sxs-lookup"><span data-stu-id="66cbd-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="66cbd-117">Die Möglichkeit zum Sperren und Entsperren eines Datensatzes verwendet die [Datensatzversionsverwaltung](record-versioning.md), die für Exchange-Elemente nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="66cbd-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="66cbd-118">Für alle Exchange-Elemente, die als Datensatz markiert sind, ist das Verhalten der Spalte **Datensatz gesperrt** und der Spalte **Datensatz entsperrt** nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="66cbd-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="66cbd-119">Aktion</span><span class="sxs-lookup"><span data-stu-id="66cbd-119">Action</span></span>| <span data-ttu-id="66cbd-120">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="66cbd-120">Retention label</span></span> |<span data-ttu-id="66cbd-121">Datensatz – gesperrt</span><span class="sxs-lookup"><span data-stu-id="66cbd-121">Record - locked</span></span>| <span data-ttu-id="66cbd-122">Datensatz – entsperrt</span><span class="sxs-lookup"><span data-stu-id="66cbd-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66cbd-123">Inhalt bearbeiten</span><span class="sxs-lookup"><span data-stu-id="66cbd-123">Edit contents</span></span>|<span data-ttu-id="66cbd-124">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-124">Allowed</span></span> | <span data-ttu-id="66cbd-125">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="66cbd-125">**Blocked**</span></span> | <span data-ttu-id="66cbd-126">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-126">Allowed</span></span>|
|<span data-ttu-id="66cbd-127">Bearbeiten Sie Eigenschaften, einschließlich Umbenennen</span><span class="sxs-lookup"><span data-stu-id="66cbd-127">Edit properties, including rename</span></span>|<span data-ttu-id="66cbd-128">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-128">Allowed</span></span> |<span data-ttu-id="66cbd-129">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-129">Allowed</span></span> | <span data-ttu-id="66cbd-130">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-130">Allowed</span></span>|
|<span data-ttu-id="66cbd-131">Löschen</span><span class="sxs-lookup"><span data-stu-id="66cbd-131">Delete</span></span>|<span data-ttu-id="66cbd-132">Zulässig <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="66cbd-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="66cbd-133">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="66cbd-133">**Blocked**</span></span> | <span data-ttu-id="66cbd-134">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="66cbd-134">**Blocked**</span></span>|
|<span data-ttu-id="66cbd-135">Kopie</span><span class="sxs-lookup"><span data-stu-id="66cbd-135">Copy</span></span>|<span data-ttu-id="66cbd-136">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-136">Allowed</span></span> |<span data-ttu-id="66cbd-137">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-137">Allowed</span></span> | <span data-ttu-id="66cbd-138">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-138">Allowed</span></span>|
|<span data-ttu-id="66cbd-139">Innerhalb eines Containers bewegen<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="66cbd-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="66cbd-140">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-140">Allowed</span></span> |<span data-ttu-id="66cbd-141">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-141">Allowed</span></span> | <span data-ttu-id="66cbd-142">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-142">Allowed</span></span>|
|<span data-ttu-id="66cbd-143">Über Container hinweg bewegen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="66cbd-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="66cbd-144">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-144">Allowed</span></span> |<span data-ttu-id="66cbd-145">Zulässig, wenn nie entsperrt</span><span class="sxs-lookup"><span data-stu-id="66cbd-145">Allowed if never unlocked</span></span> | <span data-ttu-id="66cbd-146">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-146">Allowed</span></span>|
|<span data-ttu-id="66cbd-147">Öffnen/Lesen</span><span class="sxs-lookup"><span data-stu-id="66cbd-147">Open/Read</span></span>|<span data-ttu-id="66cbd-148">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-148">Allowed</span></span> |<span data-ttu-id="66cbd-149">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-149">Allowed</span></span> | <span data-ttu-id="66cbd-150">Allowed</span><span class="sxs-lookup"><span data-stu-id="66cbd-150">Allowed</span></span>|
|<span data-ttu-id="66cbd-151">Ändern der Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="66cbd-151">Change label</span></span>|<span data-ttu-id="66cbd-152">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-152">Allowed</span></span> |<span data-ttu-id="66cbd-153">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="66cbd-153">Allowed - container admin only</span></span> | <span data-ttu-id="66cbd-154">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="66cbd-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="66cbd-155">Bezeichnung entfernen</span><span class="sxs-lookup"><span data-stu-id="66cbd-155">Remove label</span></span>|<span data-ttu-id="66cbd-156">Zulässig</span><span class="sxs-lookup"><span data-stu-id="66cbd-156">Allowed</span></span> |<span data-ttu-id="66cbd-157">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="66cbd-157">Allowed - container admin only</span></span> | <span data-ttu-id="66cbd-158">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="66cbd-158">Allowed - container admin only</span></span>|

<span data-ttu-id="66cbd-159">Fußnoten:</span><span class="sxs-lookup"><span data-stu-id="66cbd-159">Footnotes:</span></span>

<span data-ttu-id="66cbd-160"><sup>1</sup> Unterstützt von OneDrive und Exchange durch Aufbewahren einer Kopie an einem gesicherten Ort, jedoch blockiert von SharePoint.</span><span class="sxs-lookup"><span data-stu-id="66cbd-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="66cbd-161">Nachricht, die ein Benutzer sieht, wenn er versucht, ein beschriftetes Dokument in SharePoint zu löschen:</span><span class="sxs-lookup"><span data-stu-id="66cbd-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="66cbd-163"><sup>2</sup> Zu den Containern gehören SharePoint-Dokumentbibliotheken und Exchange-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="66cbd-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="66cbd-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="66cbd-164">Next steps</span></span>

<span data-ttu-id="66cbd-165">Wenn Sie noch keine Aufbewahrungsbezeichnungen für die Datensatzverwaltung besitzen, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="66cbd-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="66cbd-166">Mehr zu Inhalte als Datensatz markieren finden Sie unter [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="66cbd-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
