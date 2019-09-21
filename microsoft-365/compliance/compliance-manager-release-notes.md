---
title: Anmerkungen zur Microsoft Compliance-Manager-Version
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 815862616e1bdbf4b3be1d77de2a541ad703149f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081028"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="4ba23-104">Anmerkungen zur Version für Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4ba23-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="4ba23-105">Die Public Preview of Compliance Manager bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates.</span><span class="sxs-lookup"><span data-stu-id="4ba23-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="4ba23-106">Sie können das aktualisierte [Compliance-Manager-](https://servicetrust.microsoft.com/ComplianceManager) Tool im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) zum Nachverfolgen, zuweisen und Überprüfen von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ba23-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="4ba23-107">Neuerungen im Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4ba23-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="4ba23-108">**Integration in Microsoft Secure Score:** Compliance-Manager unterstützt die Integration mit [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) , indem Kunden verwaltete Aktionen mit mehr als 50 Secure Score-Aktionen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4ba23-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="4ba23-109">Wenn Sie eine zugeordnete Aktion in "Secure Score" abschließen, wird die entsprechende Compliance-Manager-Aktion automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4ba23-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="4ba23-110">**Importieren benutzerdefinierter Bewertungen:** Zusätzlich zu den integrierten Bewertungen unterstützt Compliance Manager jetzt das Importieren von benutzerdefinierten Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="4ba23-111">Sie können benutzerdefinierte Bewertungen für ein Produkt oder eine Dienstleistung sowie für alle Standards oder Verordnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="4ba23-112">**Actions-Elemente:** Aktionselemente sind jetzt einzelne Elemente, und viele umfassen die Telemetrie-Sammlung aus der Microsoft Secure Score Graph-API.</span><span class="sxs-lookup"><span data-stu-id="4ba23-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="4ba23-113">Wenn möglich, werden Empfehlungen zur technischen Aktion nun Links zur entsprechenden Konfigurationsseite im Office 365-Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="4ba23-114">**Mandantenverwaltung:** Neue Schnittstelle zum Verwalten neuer Datenelemente im Compliance-Manager (Preview):</span><span class="sxs-lookup"><span data-stu-id="4ba23-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="4ba23-115">**Dimensionen:** Anzeigen, hinzufügen und Anpassen von Metadaten für Vorlagen, BEWERTUNGEN und Aktionselemente, mit denen Sie benutzerdefinierte Pivots für Filter erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4ba23-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="4ba23-116">**Besitzer:** Geben Sie einen Besitzer für jedes Aktionselement an.</span><span class="sxs-lookup"><span data-stu-id="4ba23-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="4ba23-117">**Aktionen für Kunden:** Verwalten Sie die vollständige Liste der Aktionen, die in Compliance-Manager (Preview) enthalten sind, und aktivieren/deaktivieren Sie die Überwachung sicherer Bewertungen für Aktionselemente, die mit Secure Score integriert sind.</span><span class="sxs-lookup"><span data-stu-id="4ba23-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="4ba23-118">**Aktualisierte Kompatibilitätsbewertung**: die Methodik wurde geändert, um die Synchronisierung mit Microsoft Secure Score zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="4ba23-119">Das scoringsystem entfernt die von Microsoft verwalteten Steuergutschriften und konzentriert sich ausschließlich auf die Fertigstellung von von Kunden verwalteten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="4ba23-120">Bekannte Probleme im Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4ba23-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="4ba23-121">In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance-Manager behoben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="4ba23-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="4ba23-122">Kompatibilitätsbewertung</span><span class="sxs-lookup"><span data-stu-id="4ba23-122">Compliance Score</span></span>

- <span data-ttu-id="4ba23-123">Bei Aktionselementen, die als " **nicht im Bereich**" gekennzeichnet sind, wird die dem Aktionselement zugewiesene Bewertung nicht aus der Berechnung der Konformitätsbewertung ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="4ba23-124">Aktionselemente, die **nicht im Bereich** gekennzeichnet sind, verbessern nicht die Konformitätsbewertung.</span><span class="sxs-lookup"><span data-stu-id="4ba23-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="4ba23-125">Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="4ba23-125">Secure Score</span></span>

- <span data-ttu-id="4ba23-126">Sichere Ergebnis Ergebnisse sind für einige Aktionselemente in bestimmten Microsoft 365-und Office 365-Abonnements nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ba23-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="4ba23-127">Das sichere Ergebnis Ergebnis lautet in diesen Fällen "konnte nicht erkannt werden".</span><span class="sxs-lookup"><span data-stu-id="4ba23-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="4ba23-128">Manchmal werden sichere Ergebnis Ergebnisse für die entsprechenden Richtlinien und Aktionselemente nicht abgeschlossen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4ba23-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="4ba23-129">Von Microsoft verwaltete Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="4ba23-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="4ba23-130">Das Testdatum für von Microsoft verwaltete Steuerelemente wird nicht in der Benutzeroberfläche angezeigt, auch wenn diese in die Bewertung einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="4ba23-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="4ba23-131">Wenn Sie Informationen zum Test Datum anzeigen möchten, müssen Sie die Bewertung exportieren.</span><span class="sxs-lookup"><span data-stu-id="4ba23-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="4ba23-132">Anpassung</span><span class="sxs-lookup"><span data-stu-id="4ba23-132">Customization</span></span>

- <span data-ttu-id="4ba23-133">Durch das Hinzufügen von benutzerdefinierten Steuerelementen kann ein neues Steuerelement einer vorhandenen Steuerelement Familie hinzugefügt werden, es ist jedoch nicht möglich, eine neue Steuerelement Familie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="4ba23-134">In dieser Version wird das Verknüpfen von Aktionselementen oder das Hinzufügen von Aktionen Elementen oder Steuerelementen zu einer Bewertung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="4ba23-135">Wenn Sie eine benutzerdefinierte Aktion erstellen, können Sie Sie nicht bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="4ba23-136">Steuern von Familien, die in Bewertungen nicht angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="4ba23-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="4ba23-137">Wenn Sie eine Vorlage importieren, spiegeln alle auf dieser Vorlage basierenden Bewertungen alle Steuerelementfamilien wider, die Teil der Vorlage sind.</span><span class="sxs-lookup"><span data-stu-id="4ba23-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="4ba23-138">Wenn Sie der Vorlage jedoch neue Steuerelementfamilien hinzufügen, werden die Änderungen in vorhandenen Bewertungen nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="4ba23-139">Nur neue Bewertungen, die aus der aktualisierten Vorlage erstellt wurden, spiegeln die Änderungen wider.</span><span class="sxs-lookup"><span data-stu-id="4ba23-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="4ba23-140">Filter</span><span class="sxs-lookup"><span data-stu-id="4ba23-140">Filters</span></span>

- <span data-ttu-id="4ba23-141">Das Filtern von Aktionselementen oder Steuerelementen führt nicht konsistent zu korrekten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="4ba23-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="4ba23-142">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="4ba23-142">Templates</span></span>

- <span data-ttu-id="4ba23-143">Archivierte Vorlagen können bearbeitet werden, und Sie sollten nicht bearbeitbar sein.</span><span class="sxs-lookup"><span data-stu-id="4ba23-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="4ba23-144">Gesperrte Vorlagen ermöglichen eine Beurteilungs Erstellung, wenn Sie dies nicht tun sollten.</span><span class="sxs-lookup"><span data-stu-id="4ba23-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="4ba23-145">Das Sperren einer Vorlage soll verhindern, dass Sie zum Erstellen von Bewertungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4ba23-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="4ba23-146">Exportieren</span><span class="sxs-lookup"><span data-stu-id="4ba23-146">Export</span></span>

- <span data-ttu-id="4ba23-147">Der Vorlagenexport in JSON schlägt fehl, wenn der Vorlagenstatus auf " **importiert** " oder " **Ausstehende Genehmigung**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4ba23-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="4ba23-148">Unterstützte Browser</span><span class="sxs-lookup"><span data-stu-id="4ba23-148">Supported browsers</span></span>

- <span data-ttu-id="4ba23-149">Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="4ba23-150">Es gibt möglicherweise Fälle, in denen aktualisierte Daten erst angezeigt werden, wenn Ihr Browser aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4ba23-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="4ba23-151">Die Preview-Version von Microsoft Edge wird nicht unterstützt, aber es sind keine bekannten Probleme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4ba23-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="4ba23-152">Internet Explorer wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="4ba23-153">Sitzungstimeout</span><span class="sxs-lookup"><span data-stu-id="4ba23-153">Session timeout</span></span>

- <span data-ttu-id="4ba23-154">Wenn ein Timeout für eine Sitzung auftritt, wird möglicherweise der Fehler "etwas ging falsch" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="4ba23-155">Um zu beheben, gehen Sie zu [Compliance-Manager](https://servicetrust.microsoft.com/ComplianceManager) , und melden Sie sich erneut an.</span><span class="sxs-lookup"><span data-stu-id="4ba23-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="4ba23-156">Sprachunterstützung</span><span class="sxs-lookup"><span data-stu-id="4ba23-156">Language support</span></span>

- <span data-ttu-id="4ba23-157">Alle Sprachen werden für alle Webseiten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ba23-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="4ba23-158">Wenn Ihre lokale Sprache nicht unterstützt wird, zeigen Sie in US-Englisch an.</span><span class="sxs-lookup"><span data-stu-id="4ba23-158">If your local language is unsupported, view in US English.</span></span>