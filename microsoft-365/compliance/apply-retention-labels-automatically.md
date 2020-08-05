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
description: Erstellen Sie Aufbewahrungsbezeichnungen und veröffentlichen Sie diese automatisch, damit Sie diese Bezeichnungen automatisch auf Inhalte anwenden können, die Sie beibehalten möchten und nicht benötigte Inhalte löschen können.
ms.openlocfilehash: a67be377e641cb6cc7395cd82f91a05b89c5ea7a
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560616"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="77fd4-103">Aufbewahrungsbezeichnungen automatisch anwenden, um Inhalte beizubehalten oder zu löschen</span><span class="sxs-lookup"><span data-stu-id="77fd4-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="77fd4-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="77fd4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="77fd4-105">Eines der leistungsstärksten Features von [Aufbewahrungsbezeichnungen](retention.md) ist die Möglichkeit, diese automatisch auf Inhalte anzuwenden, die bestimmte Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="77fd4-106">In diesem Fall müssen die Personen in Ihrer Organisation die Bezeichnungen nicht selber anwenden.</span><span class="sxs-lookup"><span data-stu-id="77fd4-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="77fd4-107">Das wird von Microsoft 365 erledigt.</span><span class="sxs-lookup"><span data-stu-id="77fd4-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="77fd4-108">Das automatische Anwenden von Aufbewahrungsbezeichnungen ist aus den folgenden Gründen besonders effektiv:</span><span class="sxs-lookup"><span data-stu-id="77fd4-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="77fd4-109">Sie müssen die Benutzer nicht schulen, damit sie alle Ihre Klassifizierungen kennen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="77fd4-110">Sie müssen sich nicht darauf verlassen, dass die Benutzer alle Inhalte richtig klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="77fd4-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="77fd4-111">Benutzer müssen nicht mehr über Governance-Richtlinien Bescheid wissen, sondern können sich stattdessen auf ihre Arbeit konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="77fd4-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="77fd4-112">Sie können Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, wenn diese Inhalte vertrauliche Informationen oder Schlüsselwörter aufweisen oder [trainierbaren Klassifizierungsmerkmalen](classifier-getting-started-with.md) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="77fd4-113">Folgende Prozesse können eine Aufbewahrungsbezeichnung entsprechend dieser Bedingungen automatisch anwenden:</span><span class="sxs-lookup"><span data-stu-id="77fd4-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagramm der Rollen und Aufgaben für automatisch angewendete Bezeichnungen](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="77fd4-115">Befolgen Sie für die beiden Administratorschritte die nachfolgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="77fd4-116">Automatische Richtlinien verwenden dienstseitige Bezeichnungen mit Bedingungen, um Aufbewahrungsbezeichnungen automatisch anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="77fd4-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="77fd4-117">Sie können eine Aufbewahrungsbezeichnung auch automatisch mit einer Bezeichnungsrichtlinie anwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="77fd4-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="77fd4-118">Wenden Sie eine Standardaufbewahrungsbezeichnung auf eine SharePoint-Bibliothek, einen Ordner oder eine Dokumentenmappe an, damit nicht beschriftete Inhalte in diesem Container automatisch gekennzeichnet werden</span><span class="sxs-lookup"><span data-stu-id="77fd4-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="77fd4-119">Automatisches Anwenden einer Aufbewahrungsbezeichnung auf E-Mails mithilfe von Regeln</span><span class="sxs-lookup"><span data-stu-id="77fd4-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="77fd4-120">Informationen zu diesen Szenarien finden Sie unter [Erstellen und Anwenden von Aufbewahrungsbezeichnungen in Apps](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="77fd4-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77fd4-121">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="77fd4-121">Before you begin</span></span>

<span data-ttu-id="77fd4-122">Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="77fd4-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="77fd4-123">Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="77fd4-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="77fd4-124">Aufbewahrungsbezeichnungen automatisch anwenden</span><span class="sxs-lookup"><span data-stu-id="77fd4-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="77fd4-125">Erstellen Sie zunächst Ihre Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="77fd4-125">First, create your retention label.</span></span> <span data-ttu-id="77fd4-126">Erstellen Sie anschließend eine automatische Richtlinie, um diese Bezeichnung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="77fd4-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="77fd4-127">Wenn Sie Ihre Aufbewahrungsbezeichnung bereits erstellt haben, wechseln Sie zu [Erstellen einer automatischen Richtlinie](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="77fd4-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="77fd4-128">Die Navigationsanweisungen sind davon abhängig, ob Sie die [Datensatzverwaltung](records-management.md)verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="77fd4-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="77fd4-129">Es werden Anweisungen für beide Szenarios bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="77fd4-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="77fd4-130">Schritt 1: Erstellen einer Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="77fd4-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="77fd4-131">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="77fd4-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="77fd4-132">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="77fd4-132">If you are using records management:</span></span>
        - <span data-ttu-id="77fd4-133">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**</span><span class="sxs-lookup"><span data-stu-id="77fd4-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="77fd4-134">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="77fd4-134">If you are not using records management:</span></span>
       - <span data-ttu-id="77fd4-135">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**</span><span class="sxs-lookup"><span data-stu-id="77fd4-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="77fd4-136">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="77fd4-136">Don't immediately see your option?</span></span> <span data-ttu-id="77fd4-137">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="77fd4-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="77fd4-138">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="77fd4-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="77fd4-139">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="77fd4-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="77fd4-140">Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="77fd4-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="77fd4-141">Wenn Sie mithilfe der Aufbewahrungsbezeichnung Inhalt als Datensatz deklarieren möchten, aktivieren Sie das Kontrollkästchen **Bezeichnung zum Klassifizieren von Inhalt als Datensatz verwenden**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="77fd4-142">Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, wählen Sie sie aus, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den gleichen Assistenten zu starten, mit dem Sie die Beschreibungen der Bezeichnung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="77fd4-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="77fd4-143">Wählen Sie alternativ eine der verfügbaren **Bearbeitungsoptionen** aus, um direkt zur entsprechenden Seite zu wechseln und die Aktualisierung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="77fd4-144">Schritt 2: Erstellen einer Richtlinie für die automatische Anwendung</span><span class="sxs-lookup"><span data-stu-id="77fd4-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="77fd4-145">Wenn Sie eine Richtlinie für die automatische Anwendung erstellen, wird eine gewählte Aufbewahrungsbezeichnung automatisch anhand festgelegter Bedingungen auf Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="77fd4-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="77fd4-146">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="77fd4-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="77fd4-147">Wenn Sie die Datensatzverwaltung verwenden: **Informationsgovernance**:</span><span class="sxs-lookup"><span data-stu-id="77fd4-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="77fd4-148">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="77fd4-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="77fd4-149">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="77fd4-149">If you are not using records management:</span></span>
        - <span data-ttu-id="77fd4-150">**Lösungen** > **Informationgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="77fd4-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="77fd4-151">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="77fd4-151">Don't immediately see your option?</span></span> <span data-ttu-id="77fd4-152">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="77fd4-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="77fd4-153">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="77fd4-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="77fd4-154">Informationen zum Konfigurieren der Bedingungen, die zur automatischen Anwendung der Aufbewahrungsbezeichnung führen, finden Sie im Abschnitt [Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen](#configuring-conditions-for-auto-apply-retention-labels) auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="77fd4-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="77fd4-155">Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="77fd4-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="77fd4-156">Wenn Sie eine vorhandene Richtlinie zum automatischen Anwenden von Bezeichnungen bearbeiten möchten, wählen Sie sie aus, und wählen Sie dann **Richtlinie bearbeiten** aus, um den gleichen Assistenten zu starten, mit dem Sie die Richtlinienbeschreibung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="77fd4-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="77fd4-157">Wählen Sie alternativ eine der verfügbaren **Bearbeitungsoptionen** aus, um direkt zur entsprechenden Seite zu wechseln und die Aktualisierung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="77fd4-158">Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="77fd4-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="77fd4-159">Aufbewahrungsbezeichnungen können automatisch auf Inhalte angewendet werden, wenn diese folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="77fd4-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="77fd4-160">Der Inhalt enthält bestimmte vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="77fd4-161">Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="77fd4-162">Eine Übereinstimmung für trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="77fd4-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="77fd4-163">Automatisches Anwenden von Bezeichnungen auf Inhalte mit bestimmten Typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="77fd4-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="77fd4-164">Wenn Sie automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationen erstellen, wird dieselbe Liste von Richtlinienvorlagen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77fd4-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="77fd4-165">Jede Richtlinienvorlage ist für die Suche nach bestimmten Typen vertraulicher Informationen vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="77fd4-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="77fd4-166">Die hier wiedergegebene Vorlage sucht beispielsweise nach US-amerikanischen Steuernummern für Privatpersonen (ITIN), Sozialversicherungsnummern (SSN) und Reisepassnummern.</span><span class="sxs-lookup"><span data-stu-id="77fd4-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="77fd4-167">Weitere Informationen zu DLP finden Sie unter [Übersicht über Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="77fd4-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Richtlinienvorlagen für Arten von vertraulichen Informationen](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="77fd4-p112">Nach der Auswahl einer Richtlinienvorlage können Sie alle Arten von vertraulichen Informationen hinzufügen oder entfernen, und Sie können die Instanzenanzahl ändern und die Genauigkeit abgleichen. Im hier gezeigten Beispiel wird eine Aufbewahrungsbezeichnung nur dann automatisch angewendet, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="77fd4-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="77fd4-p113">Der Inhalt besteht aus 1 bis 9 Instanzen einer der drei folgenden Typen von vertraulichen Informationen. Sie können den **max**-Wert löschen, sodass er sich in **any** ändert.</span><span class="sxs-lookup"><span data-stu-id="77fd4-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="77fd4-173">Der erkannte Typ vertraulicher Informationen hat eine Übereinstimmungsgenauigkeit (oder eine Zuverlässigkeitsstufe) von mindestens 75.</span><span class="sxs-lookup"><span data-stu-id="77fd4-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="77fd4-174">Viele vertrauliche Informationstypen werden mit mehreren Mustern definiert. Dabei erfordert ein Muster mit einer höheren Übereinstimmungsgenauigkeit mehr Nachweise, um gefunden zu werden (z. B. Stichwörter, Datumsangaben oder Adressen), während ein Muster mit einer niedrigeren Übereinstimmungsgenauigkeit weniger Nachweise erfordert. </span><span class="sxs-lookup"><span data-stu-id="77fd4-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="77fd4-175">Je niedriger die **minimale** Übereinstimmungsgenauigkeit, desto einfacher können Inhalte die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="77fd4-176">Weitere Informationen zu diesen Optionen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="77fd4-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Optionen zum Identifizieren von Typen vertraulicher Informationen](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="77fd4-178">Automatisches Anwenden von Bezeichnungen auf Inhalte mit Stichwörtern oder durchsuchbare Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77fd4-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="77fd4-p115">Sie können automatische Bezeichnungen auf Inhalte anwenden, die bestimmte Kriterien erfüllen. Die derzeit verfügbaren Bedingungen unterstützen das Anwenden einer Bezeichnung auf Inhalte, die bestimmte Wörter, Ausdrücke oder durchsuchbare Eigenschaften enthalten. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie UND, ODER und NICHT verfeinern.</span><span class="sxs-lookup"><span data-stu-id="77fd4-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="77fd4-182">Weitere Informationen zur Abfragesyntax finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="77fd4-182">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="77fd4-183">Syntaxreferenz für die Keyword Query Language (KQL)</span><span class="sxs-lookup"><span data-stu-id="77fd4-183">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="77fd4-p116">Abfragebasierte Bezeichnungen verwenden den Suchindex zum Identifizieren von Inhalten. Weitere Informationen zu gültigen durchsuchbaren Eigenschaften finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="77fd4-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="77fd4-186">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="77fd4-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="77fd4-187">Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="77fd4-187">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="77fd4-188">Beispiele für Abfragen:</span><span class="sxs-lookup"><span data-stu-id="77fd4-188">Examples queries:</span></span>

- <span data-ttu-id="77fd4-189">Exchange</span><span class="sxs-lookup"><span data-stu-id="77fd4-189">Exchange</span></span>
    - <span data-ttu-id="77fd4-190">Betreff: „Vierteljährliche Finanzdaten“</span><span class="sxs-lookup"><span data-stu-id="77fd4-190">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="77fd4-191">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="77fd4-191">recipients:garthf</span></span><!--nolink--><span data-ttu-id="77fd4-192">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77fd4-192">@contoso.com</span></span>
- <span data-ttu-id="77fd4-193">SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="77fd4-193">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="77fd4-194">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="77fd4-194">contenttype:contract</span></span>
    - <span data-ttu-id="77fd4-195">site:https</span><span class="sxs-lookup"><span data-stu-id="77fd4-195">site:https</span></span><!--nolink--><span data-ttu-id="77fd4-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="77fd4-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Abfrage-Editor](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="77fd4-198">Automatisches Anwenden von Bezeichnungen auf Inhalte mithilfe von trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="77fd4-198">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="77fd4-199">Wenn Sie die Option für eine trainierbare Klassifizierung auswählen, können Sie eine der integrierten Klassifizierungen oder eine benutzerdefinierte Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-199">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="77fd4-200">Zu den integrierten Klassifizierungen gehören **Lebensläufe**, **Quellcode**, **Gezielte Belästigung**, **Vulgäre Ausdrücke** und **Drohungen**:</span><span class="sxs-lookup"><span data-stu-id="77fd4-200">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Trainierbare Klassifizierung auswählen](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="77fd4-202">Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="77fd4-202">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="77fd4-203">Verwenden Sie diese integrierte Klassifizierung nicht mehr, und ändern Sie Ihre Geschäftsprozesse entsprechend, falls sie derzeit noch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77fd4-203">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="77fd4-204">Wir empfehlen stattdessen die Verwendung der integrierten Klassifizierungen **Gezielte Belästigung**, **Obszönitäten** und **Bedrohung**.</span><span class="sxs-lookup"><span data-stu-id="77fd4-204">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="77fd4-205">Wenn Sie eine Bezeichnung mithilfe dieser Option automatisch anwenden möchten, müssen SharePoint Online-Websites und -Postfächer mindestens 10 MB Daten umfassen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-205">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="77fd4-206">Weitere Informationen zu trainierbaren Klassifizierungen finden Sie unter [Erste Schritte mit trainierbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="77fd4-206">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="77fd4-207">Eine Beispielkonfiguration finden Sie unter [Vorbereiten und Verwenden einer eingebauten Klassifizierung](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="77fd4-207">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="77fd4-208">Wie lange es dauert, bis Aufbewahrungsbezeichnungen wirksam werden</span><span class="sxs-lookup"><span data-stu-id="77fd4-208">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="77fd4-209">Wenn Sie Aufbewahrungsbezeichnungen automatisch anwenden, kann es bis zu sieben Tage dauern, bevor die Aufbewahrungsbezeichnungen auf alle vorhandenen Inhalte angewendet werden, die diesen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77fd4-209">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramm, wann automatisch angewendete Bezeichnungen wirksam werden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="77fd4-211">Aktualisieren von Aufbewahrungsbezeichnungen und der entsprechenden Richtlinien</span><span class="sxs-lookup"><span data-stu-id="77fd4-211">Updating retention labels and their policies</span></span>

<span data-ttu-id="77fd4-212">Wenn Sie eine Aufbewahrungsbezeichnung oder eine Richtlinie für die automatische Anwendung bearbeiten, und die Aufbewahrungsbezeichnung bereits auf Inhalte angewendet wird, werden Ihre aktualisierten Einstellungen automatisch zusätzlich auf diese Inhalte sowie auf neu identifizierte Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="77fd4-212">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="77fd4-213">Einige Einstellungen können nicht geändert werden, nachdem die Bezeichnung oder Richtlinie erstellt und gespeichert wurde. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="77fd4-213">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="77fd4-214">Die Aufbewahrungseinstellungen außer dem Aufbewahrungszeitraum, es sei denn, Sie haben die Bezeichnung so konfiguriert, dass der Inhalt basierend auf dem Zeitpunkt der Erstellung beibehalten oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="77fd4-214">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="77fd4-215">Die Option zum Klassifizieren als Datensatz.</span><span class="sxs-lookup"><span data-stu-id="77fd4-215">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77fd4-216">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="77fd4-216">Next steps</span></span>

<span data-ttu-id="77fd4-217">Unter [Verwenden von Aufbewahrungsbezeichnungen zum Verwalten des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md) finden Sie ein Beispielszenario, in dem eine automatisch angewendete Richtlinie mit verwalteten Eigenschaften in SharePoint und die ereignisbasierte Aufbewahrung zum Starten des Aufbewahrungszeitraums verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77fd4-217">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>