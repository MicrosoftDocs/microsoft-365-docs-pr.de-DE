---
title: Aufbewahrungsbezeichnungen automatisch anwenden, um Inhalte beizubehalten oder zu löschen
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
description: Erstellen Sie Aufbewahrungsbezeichnungen und Richtlinien für das automatische Anwenden von Bezeichnungen, damit Sie Bezeichnungen automatisch auf Inhalte anwenden können, die Sie beibehalten möchten, und nicht benötigte Inhalte löschen können.
ms.openlocfilehash: a79e7a96cc02957b0bac4dba31b24c5727f0483b
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751180"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="2cea9-103">Aufbewahrungsbezeichnungen automatisch anwenden, um Inhalte beizubehalten oder zu löschen</span><span class="sxs-lookup"><span data-stu-id="2cea9-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="2cea9-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="2cea9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="2cea9-105">Dieses Szenario wird für [regulatorische Datensätze](records-management.md#records) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="2cea9-106">Eines der leistungsstärksten Features von [Aufbewahrungsbezeichnungen](retention.md) ist die Möglichkeit, diese automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="2cea9-107">In diesem Fall müssen die Personen in Ihrer Organisation die Bezeichnungen nicht selber anwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="2cea9-108">Das wird von Microsoft 365 erledigt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="2cea9-109">Das automatische Anwenden von Aufbewahrungsbezeichnungen ist aus den folgenden Gründen besonders effektiv:</span><span class="sxs-lookup"><span data-stu-id="2cea9-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="2cea9-110">Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="2cea9-111">Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="2cea9-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="2cea9-112">Benutzer müssen nicht mehr über Governance-Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="2cea9-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="2cea9-113">Sie können Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, wenn diese Inhalte vertrauliche Informationen, Schlüsselwörter oder durchsuchbare Eigenschaften aufweisen oder [trainierbaren Klassifizierungsmerkmalen](classifier-get-started-with.md) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="2cea9-114">Verwenden Sie jetzt in der Vorschau durchsuchbare Eigenschaften, um [Aufnahmen von Teams-Besprechungen](#microsoft-teams-meeting-recordings) zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2cea9-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="2cea9-115">Folgende Prozesse können eine Aufbewahrungsbezeichnung entsprechend dieser Bedingungen automatisch anwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagramm der Rollen und Aufgaben für automatisch angewendete Bezeichnungen](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="2cea9-117">Befolgen Sie für die beiden Administratorschritte die nachfolgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="2cea9-118">Automatische Richtlinien verwenden dienstseitige Bezeichnungen mit Bedingungen, um Aufbewahrungsbezeichnungen automatisch anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="2cea9-119">Sie können eine Aufbewahrungsbezeichnung auch automatisch mit einer Bezeichnungsrichtlinie anwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="2cea9-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="2cea9-120">Anwenden einer Aufbewahrungsbezeichnung auf ein Dokumentverständnismodell in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="2cea9-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="2cea9-121">Anwenden einer Standard-Aufbewahrungsbezeichnung für SharePoint und Outlook</span><span class="sxs-lookup"><span data-stu-id="2cea9-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="2cea9-122">Anwenden einer Aufbewahrungsbezeichnung auf E-Mails mithilfe von Outlook-Regeln</span><span class="sxs-lookup"><span data-stu-id="2cea9-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="2cea9-123">Informationen zu diesen Szenarien finden Sie unter [Erstellen und Anwenden von Aufbewahrungsbezeichnungen in Apps](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2cea9-124">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="2cea9-124">Before you begin</span></span>

<span data-ttu-id="2cea9-125">Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="2cea9-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="2cea9-126">Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="2cea9-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="2cea9-127">Aufbewahrungsbezeichnungen automatisch anwenden</span><span class="sxs-lookup"><span data-stu-id="2cea9-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="2cea9-128">Erstellen Sie zunächst Ihre Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="2cea9-128">First, create your retention label.</span></span> <span data-ttu-id="2cea9-129">Erstellen Sie anschließend eine automatische Richtlinie, um diese Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="2cea9-130">Wenn Sie Ihre Aufbewahrungsbezeichnung bereits erstellt haben, wechseln Sie zu [Erstellen einer automatischen Richtlinie](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="2cea9-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="2cea9-131">Die Navigationsanweisungen sind davon abhängig, ob Sie die [Datensatzverwaltung](records-management.md)verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2cea9-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="2cea9-132">Es werden Anweisungen für beide Szenarios bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="2cea9-133">Schritt 1: Erstellen einer Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="2cea9-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="2cea9-134">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="2cea9-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="2cea9-135">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-135">If you are using records management:</span></span>
        - <span data-ttu-id="2cea9-136">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**</span><span class="sxs-lookup"><span data-stu-id="2cea9-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="2cea9-137">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-137">If you are not using records management:</span></span>
       - <span data-ttu-id="2cea9-138">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**</span><span class="sxs-lookup"><span data-stu-id="2cea9-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="2cea9-139">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="2cea9-139">Don't immediately see your option?</span></span> <span data-ttu-id="2cea9-140">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2cea9-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="2cea9-141">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2cea9-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="2cea9-142">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="2cea9-143">Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="2cea9-144">Wenn Sie Datensätze mithilfe der Aufbewahrungsbezeichnung deklarieren möchten, wählen Sie **Elemente als Datensätze markieren** oder **Elemente als regulatorische Datensätze markieren** aus.</span><span class="sxs-lookup"><span data-stu-id="2cea9-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="2cea9-145">Weitere Informationen finden Sie unter [Aufbewahrungsbezeichnungen zum Deklarieren von Datensätzen konfigurieren](declare-records.md#configuring-retention-labels-to-declare-records).</span><span class="sxs-lookup"><span data-stu-id="2cea9-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="2cea9-146">Nachdem Sie die Bezeichnung erstellt haben und Ihnen die Optionen zum Veröffentlichen der Bezeichnung, zum automatischen Anwenden der Bezeichnung oder zum Speichern der Bezeichnung angezeigt werden: Wählen Sie **Diese Bezeichnung automatisch auf einen bestimmten Inhaltstyp anwenden** und dann **Fertig** aus, um den Assistenten zum Erstellen automatischer Bezeichnungen zu starten, der Sie direkt zu Schritt 2 des folgenden Verfahrens führt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="2cea9-147">Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die Bezeichnungsbeschreibungen und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="2cea9-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="2cea9-148">Schritt 2: Erstellen einer Richtlinie für die automatische Anwendung</span><span class="sxs-lookup"><span data-stu-id="2cea9-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="2cea9-149">Wenn Sie eine Richtlinie für die automatische Anwendung erstellen, wird eine gewählte Aufbewahrungsbezeichnung automatisch anhand festgelegter Bedingungen auf Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="2cea9-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="2cea9-150">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="2cea9-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="2cea9-151">Wenn Sie die Datensatzverwaltung verwenden: **Informationsgovernance**:</span><span class="sxs-lookup"><span data-stu-id="2cea9-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="2cea9-152">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="2cea9-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="2cea9-153">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-153">If you are not using records management:</span></span>
        - <span data-ttu-id="2cea9-154">**Lösungen** > **Informationgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="2cea9-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="2cea9-155">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="2cea9-155">Don't immediately see your option?</span></span> <span data-ttu-id="2cea9-156">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2cea9-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="2cea9-157">Folgen Sie den Eingabeaufforderungen im Assistenten zum Erstellen automatischer Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="2cea9-158">Informationen zum Konfigurieren der Bedingungen, die zur automatischen Anwendung der Aufbewahrungsbezeichnung führen, finden Sie im Abschnitt [Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen](#configuring-conditions-for-auto-apply-retention-labels) auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="2cea9-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="2cea9-159">Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="2cea9-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="2cea9-160">Wenn Sie eine vorhandene Richtlinie zum automatischen Anwenden von Bezeichnungen bearbeiten möchten, wählen Sie sie aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die ausgewählte Aufbewahrungsrichtlinie und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="2cea9-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="2cea9-161">Nach der Bezeichnung von Inhalten mit Hilfe einer automatischen Bezeichnungsrichtlinie kann die angewendete Bezeichnung nicht automatisch entfernt oder geändert werden, indem der Inhalt oder die Richtlinie geändert oder eine neue automatische Bezeichnungsrichtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cea9-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="2cea9-162">Weitere Informationen finden Sie unter [Jeweils nur eine Aufbewahrungsbezeichnung](retention.md#only-one-retention-label-at-a-time).</span><span class="sxs-lookup"><span data-stu-id="2cea9-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="2cea9-163">Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="2cea9-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="2cea9-164">Aufbewahrungsbezeichnungen können automatisch auf Inhalte angewendet werden, wenn diese folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2cea9-164">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="2cea9-165">Der Inhalt enthält bestimmte vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-165">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="2cea9-166">Der Inhalt enthält bestimmte Stichwörter oder durchsuchbare Eigenschaften, die einer von Ihnen erstellten Abfrage entsprechen</span><span class="sxs-lookup"><span data-stu-id="2cea9-166">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="2cea9-167">Eine Übereinstimmung für trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="2cea9-167">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="2cea9-168">Automatisches Anwenden von Bezeichnungen auf Inhalte mit bestimmten Typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="2cea9-168">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="2cea9-169">Wenn Sie automatisch angewendete Richtlinien für Aufbewahrungsbezeichnungen für vertrauliche Informationen erstellen, wird dieselbe Liste von Richtlinienvorlagen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-169">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="2cea9-170">Jede Vorlage ist für die Suche nach bestimmten Typen vertraulicher Informationen vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2cea9-170">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="2cea9-171">Die hier gezeigte Vorlage sucht beispielsweise nach US ITIN-, SSN- und Reisepassnummern aus der **Datenschutz**-Kategorie und der Vorlage **USA – Daten mit persönlich identifizierbaren Informationen (PII)**:</span><span class="sxs-lookup"><span data-stu-id="2cea9-171">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data** template:</span></span>

![Richtlinienvorlagen für Arten von vertraulichen Informationen](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="2cea9-173">Weitere Informationen zu Typen vertraulicher Informationen finden Sie unter [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-173">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="2cea9-174">Nach der Auswahl einer Richtlinienvorlage können Sie beliebige Typen vertraulicher Informationen hinzufügen oder entfernen, und Sie können die Instanzenzahl und die Übereinstimmungsgenauigkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="2cea9-174">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="2cea9-175">Im folgenden Beispielscreenshot wird eine Aufbewahrungsbezeichnung nur dann automatisch angewendet, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2cea9-175">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="2cea9-176">Der erkannte Typ vertraulicher Informationen hat eine Übereinstimmungsgenauigkeit (oder eine Zuverlässigkeitsstufe) von mindestens 75.</span><span class="sxs-lookup"><span data-stu-id="2cea9-176">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="2cea9-177">Viele vertrauliche Informationstypen werden mit mehreren Mustern definiert. Dabei erfordert ein Muster mit einer höheren Übereinstimmungsgenauigkeit mehr Nachweise, um gefunden zu werden (z. B. Stichwörter, Datumsangaben oder Adressen), während ein Muster mit einer niedrigeren Übereinstimmungsgenauigkeit weniger Nachweise erfordert. </span><span class="sxs-lookup"><span data-stu-id="2cea9-177">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="2cea9-178">Je niedriger die **minimale** Übereinstimmungsgenauigkeit, desto einfacher können Inhalte die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-178">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="2cea9-179">Der Inhalt besteht aus zwischen einer und neun Instanzen von einem dieser drei vertraulichen Informationstypen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-179">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="2cea9-180">Sie können den **bis**-Wert löschen, sodass er in **Beliebig** geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2cea9-180">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="2cea9-181">Weitere Informationen zu diesen Optionen finden Sie in der folgenden Anleitung aus der DLP-Dokumentation [Optimieren von Regeln, um Übereinstimmungen zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="2cea9-181">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Optionen zum Identifizieren von Typen vertraulicher Informationen](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="2cea9-183">Folgendes ist bei der Verwendung von Typen vertraulicher Informationen zum automatischen Anwenden von Aufbewahrungsbezeichnungen zu beachten:</span><span class="sxs-lookup"><span data-stu-id="2cea9-183">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="2cea9-184">Neue und geänderte Elemente können automatisch mit Bezeichnungen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-184">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="2cea9-185">Automatisches Anwenden von Bezeichnungen auf Inhalte mit Stichwörtern oder durchsuchbare Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2cea9-185">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="2cea9-p115">Sie können automatische Bezeichnungen auf Inhalte mithilfe einer Abfrage anwenden, die bestimmte Wörter, Ausdrücke oder durchsuchbare Eigenschaften enthält. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie UND, ODER und NICHT verfeinern.</span><span class="sxs-lookup"><span data-stu-id="2cea9-p115">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Abfrage-Editor](../media/new-retention-query-editor.png)

<span data-ttu-id="2cea9-189">Weitere Informationen zur Abfragesyntax, bei der die Keyword Query Language (KQL) angewendet wird, finden Sie unter [Syntaxreferenz für die Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="2cea9-189">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="2cea9-190">Abfragebasierte Richtlinien für die automatische Anwendung verwenden den gleichen Suchindex wie die eDiscovery-Inhaltssuche, um Inhalte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2cea9-190">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="2cea9-191">Weitere Informationen zu den durchsuchbaren Eigenschaften, die Sie verwenden können, finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-191">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="2cea9-192">Folgendes muss berücksichtigt werden, wenn Sie Stichwörter oder durchsuchbare Eigenschaften verwenden, um Aufbewahrungsbezeichnungen automatisch anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-192">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="2cea9-193">Neue, geänderte und vorhandene Elemente werden für SharePoint, OneDrive und Exchange automatisch mit Bezeichnungen versehen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-193">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="2cea9-194">Für SharePoint werden durchforstete Eigenschaften und benutzerdefinierte Eigenschaften für diese KQL-Abfragen nicht unterstützt, und Sie dürfen nur vordefinierte verwaltete Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-194">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="2cea9-195">Sie können jedoch Zuordnungen auf Mandantenebene mit den vordefinierten verwalteten Eigenschaften verwenden, die standardmäßig als Einschränkungen aktiviert sind (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 und RefinableDouble00-09).</span><span class="sxs-lookup"><span data-stu-id="2cea9-195">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="2cea9-196">Weitere Informationen finden Sie unter [Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview). Anweisungen finden Sie unter [Erstellen einer neuen verwalteten Eigenschaft](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span><span class="sxs-lookup"><span data-stu-id="2cea9-196">For more information, see [Overview of crawled and managed properties in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="2cea9-197">Wenn Sie eine benutzerdefinierte Eigenschaft einer der Einschränkungseigenschaften zuordnen, warten Sie 24 Stunden, bevor Sie sie in Ihrer KQL-Abfrage für eine Aufbewahrungsbezeichnung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-197">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="2cea9-198">Verwaltete SharePoint-Eigenschaften können zwar durch die Verwendung von Aliasen umbenannt werden, Sie sollten diese aber nicht für KQL-Abfragen in Ihren Bezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-198">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="2cea9-199">Sie müssen immer den tatsächlichen Namen der verwalteten Eigenschaft angeben, z. B "RefinableString01".</span><span class="sxs-lookup"><span data-stu-id="2cea9-199">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="2cea9-200">Um nach Werten zu suchen, die Leerzeichen oder Sonderzeichen enthalten, schließen Sie den Suchbegriff in doppelte Anführungszeichen (`" "`) ein; z. B. `subject:"Financial Statements"`.</span><span class="sxs-lookup"><span data-stu-id="2cea9-200">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="2cea9-201">Verwenden Sie die Eigenschaft *DocumentLink* anstelle von *Path*, um ein Element auf der Grundlage seiner URL zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-201">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="2cea9-202">Suffixsuchen mit Platzhalter (z. B. `*cat`) oder Teilzeichenfolgensuchen mit Platzhalter (z. B. `*cat*`) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-202">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="2cea9-203">Präfixsuchen mit Platzhaltern (z. B. `cat*`) werden jedoch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2cea9-203">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="2cea9-204">Beachten Sie, dass teilweise indizierte Elemente dafür verantwortlich sein können, dass Elemente, die eigentlich mit Bezeichnungen versehen werden sollten, nicht bezeichnet werden, oder dass Elemente mit Bezeichnungen versehen werden, von denen Sie erwarten, dass sie von der Bezeichnung ausgeschlossen werden, wenn Sie den Operator NOT verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-204">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="2cea9-205">Weitere Informationen finden Sie unter [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-205">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="2cea9-206">Beispiele für Abfragen:</span><span class="sxs-lookup"><span data-stu-id="2cea9-206">Examples queries:</span></span>

| <span data-ttu-id="2cea9-207">Arbeitslast</span><span class="sxs-lookup"><span data-stu-id="2cea9-207">Workload</span></span> | <span data-ttu-id="2cea9-208">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cea9-208">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="2cea9-209">Exchange</span><span class="sxs-lookup"><span data-stu-id="2cea9-209">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="2cea9-210">Exchange</span><span class="sxs-lookup"><span data-stu-id="2cea9-210">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="2cea9-211">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cea9-211">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="2cea9-212">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cea9-212">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="2cea9-213">Exchange oder SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cea9-213">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="2cea9-214">Komplexerer Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2cea9-214">More complex examples:</span></span>

<span data-ttu-id="2cea9-215">Die folgende Abfrage für SharePoint identifiziert Word-Dokumente oder Excel-Kalkulationstabellen, wenn diese Dateien die Stichwörter **password**, **passwords** oder **pw** enthalten:</span><span class="sxs-lookup"><span data-stu-id="2cea9-215">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="2cea9-216">Die folgende Abfrage für Exchange identifiziert ein beliebiges Word-Dokument oder eine PDF-Datei, die das Wort **nda** oder den Ausdruck **non disclosure agreement** enthält, wenn diese Dokumente an eine E-Mail angefügt werden:</span><span class="sxs-lookup"><span data-stu-id="2cea9-216">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="2cea9-217">Die folgende Abfrage für SharePoint identifiziert Dokumente, die eine Kreditkartennummer enthalten:</span><span class="sxs-lookup"><span data-stu-id="2cea9-217">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="2cea9-218">Die folgende Abfrage enthält einige typische Stichwörter, die Ihnen dabei helfen sollen, Dokumente oder E-Mails mit rechtlichen Inhalten zu identifizieren:</span><span class="sxs-lookup"><span data-stu-id="2cea9-218">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="2cea9-219">Die folgende Abfrage enthält typische Stichwörter, die Ihnen dabei helfen sollen, Dokumente oder E-Mails mit Personaldaten zu identifizieren:</span><span class="sxs-lookup"><span data-stu-id="2cea9-219">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="2cea9-220">Beachten Sie, dass dieses letzte Beispiel die bewährte Methode verwendet, zwischen den Stichwörtern immer Operatoren anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2cea9-220">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="2cea9-221">Ein Leerzeichen zwischen Stichwörtern (oder zwei Eigenschaft:Wert-Ausdrücke) entspricht der Verwendung von AND.</span><span class="sxs-lookup"><span data-stu-id="2cea9-221">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="2cea9-222">Indem immer Operatoren hinzugefügt werden, ist es einfacher zu erkennen, dass diese Beispielabfrage nur Inhalte, die alle Stichwörter enthalten, und keine Inhalte, die nur einzelne der Stichwörter enthalten, identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2cea9-222">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="2cea9-223">Wenn Sie Inhalte identifizieren möchten, die einzelne der angegebenen Stichwörter enthalten, verwenden Sie OR anstelle von AND.</span><span class="sxs-lookup"><span data-stu-id="2cea9-223">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="2cea9-224">Wie dieses Beispiel verdeutlicht, lässt sich die Abfrage einfacher interpretieren, wenn die Operatoren immer angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="2cea9-224">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="2cea9-225">Aufnahmen von Microsoft Teams-Besprechungen</span><span class="sxs-lookup"><span data-stu-id="2cea9-225">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="2cea9-226">Die Möglichkeit zum Aufbewahren und Löschen von Teams-Besprechungsaufzeichnungen befindet sich in der Vorschau und funktioniert erst, nachdem die Aufzeichnungen auf OneDrive oder Microsoft Office SharePoint Online gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-226">The ability to retain and delete Teams meeting recordings is in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="2cea9-227">Weitere Informationen finden Sie unter [Verwenden von OneDrive for Business und SharePoint Online oder Stream für Besprechungsaufzeichnungen](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span><span class="sxs-lookup"><span data-stu-id="2cea9-227">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="2cea9-228">Wenn Sie Aufnahmen von Microsoft Teams-Besprechungen ermitteln möchten, die in den OneDrive-Konten von Benutzern oder in SharePoint gespeichert sind, geben Sie im **Stichwortabfrage-Editor** Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="2cea9-228">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="2cea9-229">Meistens werden die Besprechungsaufnahmen auf OneDrive gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2cea9-229">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="2cea9-230">Bei Kanalbesprechungen werden sie jedoch in SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2cea9-230">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="2cea9-231">Automatisches Anwenden von Bezeichnungen auf Inhalte mithilfe von trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="2cea9-231">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="2cea9-232">Wenn Sie die Option für eine trainierbare Klassifizierung auswählen, können Sie eine der integrierten Klassifizierungen oder eine benutzerdefinierte Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-232">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="2cea9-233">Zu den integrierten Klassifizierungen gehören **Lebensläufe**, **Quellcode**, **Gezielte Belästigung**, **Vulgäre Ausdrücke** und **Drohungen**:</span><span class="sxs-lookup"><span data-stu-id="2cea9-233">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Trainierbare Klassifizierung auswählen](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="2cea9-235">Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="2cea9-235">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="2cea9-236">Verwenden Sie diese integrierte Klassifizierung nicht mehr, und ändern Sie Ihre Geschäftsprozesse entsprechend, falls sie derzeit noch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cea9-236">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="2cea9-237">Wir empfehlen stattdessen die Verwendung der integrierten Klassifizierungen **Gezielte Belästigung**, **Obszönitäten** und **Bedrohung**.</span><span class="sxs-lookup"><span data-stu-id="2cea9-237">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="2cea9-238">Wenn Sie eine Bezeichnung mithilfe dieser Option automatisch anwenden möchten, müssen SharePoint-Websites und -Postfächer mindestens 10 MB Daten umfassen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-238">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="2cea9-239">Weitere Informationen über trainierbare Klassifizierer finden Sie unter [Weitere Informationen zu trainierbaren Klassifizierern (Vorschau)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-239">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="2cea9-240">Wenn Sie trainierbare Klassifizierungsmerkmale für Exchange verwenden, lesen Sie die kürzlich veröffentlichte [Anleitung zum Neutrainieren einer Klassifizierung im Inhaltsexplorer (Vorschau)](classifier-how-to-retrain-content-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-240">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="2cea9-241">Folgendes ist bei der Verwendung von trainierbaren Klassifizierungsmerkmalen zum automatischen Anwenden von Aufbewahrungsbezeichnungen zu beachten:</span><span class="sxs-lookup"><span data-stu-id="2cea9-241">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="2cea9-242">Neue und geänderte Elemente können automatisch mit Bezeichnungen versehen werden, genau wie vorhandene Elemente aus den letzten sechs Monaten.</span><span class="sxs-lookup"><span data-stu-id="2cea9-242">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="2cea9-243">Wie lange es dauert, bis Aufbewahrungsbezeichnungen wirksam werden</span><span class="sxs-lookup"><span data-stu-id="2cea9-243">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="2cea9-244">Wenn Sie Aufbewahrungsbezeichnungen automatisch anwenden, kann es bis zu sieben Tage dauern, bevor die Aufbewahrungsbezeichnungen auf alle vorhandenen Inhalte angewendet werden, die diesen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-244">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramm, wann automatisch angewendete Bezeichnungen wirksam werden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="2cea9-246">Wenn die erwarteten Bezeichnungen nach sieben Tagen nicht erscheinen, überprüfen Sie den **Status** der Richtlinie für die automatische Anwendung, indem Sie sie auf der Seite **Richtlinien für Bezeichnungen** im Compliance Center auswählen.</span><span class="sxs-lookup"><span data-stu-id="2cea9-246">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="2cea9-247">Wenn der Status **Aus (Fehler)** angezeigt wird und in den Details für die Standorte eine Meldung angezeigt wird, dass die Bereitstellung der Richtlinie (für SharePoint) oder der Versuch der Neuverteilung der Richtlinie (für OneDrive) länger als erwartet dauert, versuchen Sie, den PowerShell-Befehl [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) auszuführen, um die Richtlinienverteilung erneut zu versuchen:</span><span class="sxs-lookup"><span data-stu-id="2cea9-247">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="2cea9-248">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cea9-248">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="2cea9-249">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2cea9-249">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="2cea9-250">Aktualisieren von Aufbewahrungsbezeichnungen und der entsprechenden Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2cea9-250">Updating retention labels and their policies</span></span>

<span data-ttu-id="2cea9-251">Wenn Sie eine Aufbewahrungsbezeichnung oder eine Richtlinie für die automatische Anwendung bearbeiten, und die Aufbewahrungsbezeichnung bereits auf Inhalte angewendet wird, werden Ihre aktualisierten Einstellungen automatisch zusätzlich auf diese Inhalte sowie auf neu identifizierte Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="2cea9-251">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="2cea9-252">Einige Einstellungen können nicht geändert werden, nachdem die Bezeichnung oder Richtlinie erstellt und gespeichert wurde. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="2cea9-252">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="2cea9-253">Die Aufbewahrungsbezeichnung und der Name der Richtlinie sowie die Aufbewahrungseinstellungen mit Ausnahme des Aufbewahrungszeitraums.</span><span class="sxs-lookup"><span data-stu-id="2cea9-253">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="2cea9-254">Der Aufbewahrungszeitraum kann jedoch nicht geändert werden, wenn er auf dem Zeitpunkt basiert, zu dem die Bezeichnungen auf die Elemente angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="2cea9-254">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="2cea9-255">Die Option zum Markieren von Elementen als Datensatz.</span><span class="sxs-lookup"><span data-stu-id="2cea9-255">The option to mark items as a record.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="2cea9-256">Sperren der Richtlinie, um Änderungen vorzubeugen</span><span class="sxs-lookup"><span data-stu-id="2cea9-256">Locking the policy to prevent changes</span></span>

<span data-ttu-id="2cea9-257">Wenn Sie sicherstellen müssen, das niemand die Richtlinie deaktivieren, löschen oder weniger restriktiv machen kann, lesen Sie [Erhaltungssperre verwenden, um Änderungen an Aufbewahrungsrichtlinien und Richtlinien der Aufbewahrungsbezeichnung einzuschränken](retention-preservation-lock.md).</span><span class="sxs-lookup"><span data-stu-id="2cea9-257">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2cea9-258">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2cea9-258">Next steps</span></span>

<span data-ttu-id="2cea9-259">Unter [Verwenden von Aufbewahrungsbezeichnungen zum Verwalten des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md) finden Sie ein Beispielszenario, in dem eine automatisch angewendete Richtlinie für Aufbewahrungsbezeichnungen mit verwalteten Eigenschaften in SharePoint und die ereignisbasierte Aufbewahrung zum Starten des Aufbewahrungszeitraums verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cea9-259">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
