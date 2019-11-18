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
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2019
ms.locfileid: "38686050"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="88397-104">Anmerkungen zur Version für Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="88397-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="88397-105">Die Public Preview of Compliance Manager bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates.</span><span class="sxs-lookup"><span data-stu-id="88397-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="88397-106">Sie können das aktualisierte [Compliance-Manager-](https://servicetrust.microsoft.com/ComplianceManager) Tool im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) zum Nachverfolgen, zuweisen und Überprüfen von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="88397-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="88397-107">Neuerungen im Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="88397-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="88397-108">**Rollenbasierter Zugriff auf den Compliance-Manager:** Die standardmäßige **Gastzugriffs** Rolle wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="88397-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="88397-109">Damit ein Benutzer auf den Compliance-Manager zugreifen kann, muss der globale Administrator [jedem Benutzer eine Berechtigung zuweisen](compliance-manager-overview.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="88397-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="88397-110">**Aktualisierte Kompatibilitätsbewertung**: das Kompatibilitäts Ergebnis enthält jetzt Ergebnisse für von Microsoft verwaltete Aktionen.</span><span class="sxs-lookup"><span data-stu-id="88397-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="88397-111">Ihre Punktzahl wird dadurch zunehmen.</span><span class="sxs-lookup"><span data-stu-id="88397-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="88397-112">**Actions-Elemente:** Aktionselemente sind jetzt einzelne Elemente, und viele umfassen die Telemetrie-Sammlung aus der Microsoft Secure Score Graph-API.</span><span class="sxs-lookup"><span data-stu-id="88397-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="88397-113">Wenn möglich, werden Empfehlungen zur technischen Aktion nun Links zur entsprechenden Konfigurationsseite im Office 365-Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88397-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="88397-114">**Mandantenverwaltung:** Neue Schnittstelle zum Verwalten neuer Datenelemente im Compliance-Manager (Preview):</span><span class="sxs-lookup"><span data-stu-id="88397-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="88397-115">**Dimensionen:** Anzeigen, hinzufügen und Anpassen von Metadaten für Vorlagen, BEWERTUNGEN und Aktionselemente, mit denen Sie benutzerdefinierte Pivots für Filter erstellen können.</span><span class="sxs-lookup"><span data-stu-id="88397-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="88397-116">**Besitzer:** Geben Sie einen Besitzer für jedes Aktionselement an.</span><span class="sxs-lookup"><span data-stu-id="88397-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="88397-117">**Aktionen für Kunden:** Verwalten Sie die vollständige Liste der Aktionen, die in Compliance-Manager (Preview) enthalten sind, und aktivieren/deaktivieren Sie die Überwachung sicherer Bewertungen für Aktionselemente, die mit Secure Score integriert sind.</span><span class="sxs-lookup"><span data-stu-id="88397-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="88397-118">Bekannte Probleme im Compliance-Manager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="88397-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="88397-119">In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance-Manager behoben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="88397-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="88397-120">Kompatibilitätsbewertung</span><span class="sxs-lookup"><span data-stu-id="88397-120">Compliance Score</span></span>

- <span data-ttu-id="88397-121">Bei Aktionselementen, die als " **nicht im Bereich**" gekennzeichnet sind, wird die dem Aktionselement zugewiesene Bewertung nicht aus der Berechnung der Konformitätsbewertung ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="88397-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the compliance score calculation.</span></span> <span data-ttu-id="88397-122">Aktionselemente, die **nicht im Bereich** gekennzeichnet sind, verbessern nicht die Konformitätsbewertung.</span><span class="sxs-lookup"><span data-stu-id="88397-122">Action Items marked **Not in Scope** do not increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="88397-123">Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="88397-123">Secure Score</span></span>

- <span data-ttu-id="88397-124">Sichere Ergebnis Ergebnisse sind für einige Aktionselemente in bestimmten Microsoft 365-und Office 365-Abonnements nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="88397-124">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="88397-125">In diesen Fällen konnte das sichere Ergebnis Ergebnis **nicht erkannt werden** .</span><span class="sxs-lookup"><span data-stu-id="88397-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="88397-126">Manchmal werden sichere Ergebnis Ergebnisse für die entsprechenden Richtlinien und Aktionselemente nicht abgeschlossen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="88397-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="88397-127">Für neue Mandanten ist die Sicherung der Bewertungs Aktualisierungen für alle Aktionen automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88397-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="88397-128">Der globale Administrator kann die Option für die kontinuierliche Aktualisierung sicherer Bewertungen auf aus festlegen, wodurch Updates für alle Aktionen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="88397-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
- <span data-ttu-id="88397-129">Wenn Secure Score Updates aktiviert sind, werden Aktionen aktiv durch Secure Score überwacht, obwohl das Test Datum der Aktion nicht aktualisiert wird, um die Überwachung widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="88397-129">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date will not be updated to reflect monitoring.</span></span>
- <span data-ttu-id="88397-130">Wenn neue Bewertungen erstellt werden, enthalten Scores automatisch von Microsoft verwaltete Steuerpunkte und die Integration sicherer Bewertungen.</span><span class="sxs-lookup"><span data-stu-id="88397-130">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="88397-131">Von Microsoft verwaltete Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="88397-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="88397-132">Das Testdatum für von Microsoft verwaltete Steuerelemente wird nicht in der Benutzeroberfläche angezeigt, auch wenn diese in die Bewertung einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="88397-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="88397-133">Wenn Sie Informationen zum Test Datum anzeigen möchten, müssen Sie die Bewertung exportieren.</span><span class="sxs-lookup"><span data-stu-id="88397-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="88397-134">Anpassung</span><span class="sxs-lookup"><span data-stu-id="88397-134">Customization</span></span>

- <span data-ttu-id="88397-135">Durch das Hinzufügen von benutzerdefinierten Steuerelementen kann ein neues Steuerelement einer vorhandenen Steuerelement Familie hinzugefügt werden, es ist jedoch nicht möglich, eine neue Steuerelement Familie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="88397-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="88397-136">In dieser Version wird das Verknüpfen von Aktionselementen oder das Hinzufügen von Aktionen Elementen oder Steuerelementen zu einer Bewertung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="88397-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="88397-137">Wenn Sie eine benutzerdefinierte Aktion erstellen, können Sie Sie nicht bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="88397-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="88397-138">Steuern von Familien, die in Bewertungen nicht angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="88397-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="88397-139">Wenn Sie eine Vorlage importieren, spiegeln alle auf dieser Vorlage basierenden Bewertungen alle Steuerelementfamilien wider, die Teil der Vorlage sind.</span><span class="sxs-lookup"><span data-stu-id="88397-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="88397-140">Wenn Sie der Vorlage jedoch neue Steuerelementfamilien hinzufügen, werden die Änderungen in vorhandenen Bewertungen nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="88397-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="88397-141">Nur neue Bewertungen, die aus der aktualisierten Vorlage erstellt wurden, spiegeln die Änderungen wider.</span><span class="sxs-lookup"><span data-stu-id="88397-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="88397-142">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88397-142">Templates</span></span>

- <span data-ttu-id="88397-143">Beim Erstellen einer Vorlage müssen Sie Dimensionen für **Produkt** und **Zertifizierung** einschließen, um sicherzustellen, dass Ihre Vorlage im Kompatibilitäts Bewertungsergebnis angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="88397-143">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="88397-144">Archivierte Vorlagen können bearbeitet werden, und Sie sollten nicht bearbeitbar sein.</span><span class="sxs-lookup"><span data-stu-id="88397-144">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="88397-145">Gesperrte Vorlagen ermöglichen eine Beurteilungs Erstellung, wenn Sie dies nicht tun sollten.</span><span class="sxs-lookup"><span data-stu-id="88397-145">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="88397-146">Das Sperren einer Vorlage soll verhindern, dass Sie zum Erstellen von Bewertungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88397-146">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="88397-147">Exportieren</span><span class="sxs-lookup"><span data-stu-id="88397-147">Export</span></span>

- <span data-ttu-id="88397-148">Der Vorlagenexport in JSON schlägt fehl, wenn der Vorlagenstatus auf " **importiert** " oder " **Ausstehende Genehmigung**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="88397-148">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="88397-149">Unterstützte Browser</span><span class="sxs-lookup"><span data-stu-id="88397-149">Supported browsers</span></span>

- <span data-ttu-id="88397-150">Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="88397-150">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="88397-151">Es gibt möglicherweise Fälle, in denen aktualisierte Daten erst angezeigt werden, wenn Ihr Browser aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="88397-151">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="88397-152">Die Preview-Version von Microsoft Edge wird nicht unterstützt, aber es sind keine bekannten Probleme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="88397-152">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="88397-153">Internet Explorer wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="88397-153">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="88397-154">Sitzungstimeout</span><span class="sxs-lookup"><span data-stu-id="88397-154">Session timeout</span></span>

- <span data-ttu-id="88397-155">Wenn ein Timeout für eine Sitzung auftritt, wird möglicherweise der Fehler "etwas ging falsch" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88397-155">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="88397-156">Um zu beheben, gehen Sie zu [Compliance-Manager](https://servicetrust.microsoft.com/ComplianceManager) , und melden Sie sich erneut an.</span><span class="sxs-lookup"><span data-stu-id="88397-156">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="88397-157">Sprachunterstützung</span><span class="sxs-lookup"><span data-stu-id="88397-157">Language support</span></span>

- <span data-ttu-id="88397-158">Alle Sprachen werden für alle Webseiten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="88397-158">All languages are not supported for all webpages.</span></span> <span data-ttu-id="88397-159">Wenn Ihre lokale Sprache nicht unterstützt wird, zeigen Sie in US-Englisch an.</span><span class="sxs-lookup"><span data-stu-id="88397-159">If your local language is unsupported, view in US English.</span></span>