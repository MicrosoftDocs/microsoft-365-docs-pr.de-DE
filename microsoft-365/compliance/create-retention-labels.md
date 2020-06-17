---
title: Erstellen, Veröffentlichen und automatisches Anwenden von Aufbewahrungsbezeichnungen
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
description: Anweisungen zum Erstellen, Veröffentlichen und automatischen Anwenden von Aufbewahrungsbezeichnungen, um gewünschte Elemente aufzubewahren und anderes zu löschen, und um ein Element als Datensatz in Ihrer Office 365-Umgebung zu deklarieren.
ms.openlocfilehash: 035038c90179354e0497813326b1fdad01693bec
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761651"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="f596f-103">Erstellen, Veröffentlichen und automatisches Anwenden von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="f596f-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f596f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f596f-105">Verwenden Sie die folgenden Informationen, um [Aufbewahrungsbezeichnungen](labels.md) zu erstellen und diese dann automatisch auf Dokumente und E-Mails anzuwenden, oder um sie zu veröffentlichen, damit sie von den Benutzern manuell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f596f-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="f596f-106">Aufbewahrungsbezeichnungen helfen Ihnen bei der Aufbewahrung wichtiger Elemente und bei der Löschung alles anderen.</span><span class="sxs-lookup"><span data-stu-id="f596f-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="f596f-107">Sie werden auch als Teil einer [Datensatzverwaltungslösung](records-management.md) für Ihre Microsoft 365-Daten verwendet, um ein Element als Datensatz zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f596f-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="f596f-108">Wo Sie Ihre Aufbewahrungsbezeichnungen erstellen und konfigurieren, hängt davon ab, ob Sie die Datensatzverwaltung verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f596f-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="f596f-109">Es werden Anweisungen für beide Szenarios bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f596f-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f596f-110">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f596f-110">Before you begin</span></span>

<span data-ttu-id="f596f-111">Die Mitglieder Ihres Complianceteams, die Aufbewahrungsbezeichnungen erstellen sollen, benötigen Berechtigungen für das Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f596f-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f596f-112">Standardmäßig hat Ihr Mandantenadministrator Zugriff auf diesen Speicherort und kann anderen Personen den Zugriff auf das Security &amp; Compliance Center gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Zu diesem Zweck wird empfohlen, dass Sie zur Seite **Berechtigungen** des Security &amp; Compliance Centers gehen, die Rollengruppe **Compliance-Administrator** bearbeiten und dieser Rollengruppe Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f596f-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="f596f-113">Weitere Informationen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f596f-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="f596f-114">These permissions are required only to create and apply retention labels and a label policy.</span><span class="sxs-lookup"><span data-stu-id="f596f-114">These permissions are required only to create and apply retention labels and a label policy.</span></span> <span data-ttu-id="f596f-115">Policy enforcement does not require access to the content.</span><span class="sxs-lookup"><span data-stu-id="f596f-115">Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="f596f-116">Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="f596f-117">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="f596f-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="f596f-118">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-118">If you are using records management:</span></span>
        - <span data-ttu-id="f596f-119">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**</span><span class="sxs-lookup"><span data-stu-id="f596f-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="f596f-120">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-120">If you are not using records management:</span></span>
       - <span data-ttu-id="f596f-121">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**</span><span class="sxs-lookup"><span data-stu-id="f596f-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="f596f-122">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="f596f-122">Don't immediately see your option?</span></span> <span data-ttu-id="f596f-123">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="f596f-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="f596f-124">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f596f-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="f596f-125">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="f596f-126">Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f596f-126">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="f596f-127">Wenn Sie mithilfe der Aufbewahrungsbezeichnung Inhalt als Datensatz deklarieren möchten, aktivieren Sie das Kontrollkästchen **Bezeichnung zum Klassifizieren von Inhalt als Datensatz verwenden**.</span><span class="sxs-lookup"><span data-stu-id="f596f-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="f596f-128">Wiederholen Sie diese Schritte, um weitere Bezeichnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f596f-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="f596f-129">Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, wählen Sie sie aus, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den gleichen Assistenten zu starten, mit dem Sie die Beschreibungen der Bezeichnung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="f596f-129">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="f596f-130">Wählen Sie alternativ eine der verfügbaren **Bearbeitungsoptionen** aus, um direkt zur entsprechenden Seite zu wechseln und die Aktualisierung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f596f-130">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="f596f-131">Veröffentlichen von Aufbewahrungsbezeichnungen durch die Erstellung einer Aufbewahrungsbezeichnungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f596f-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="f596f-132">Veröffentlichen Sie Aufbewahrungsbezeichnungen, damit sie von Benutzern manuell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f596f-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="f596f-133">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="f596f-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="f596f-134">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-134">If you are using records management:</span></span>
        - <span data-ttu-id="f596f-135">**Lösungen** > **Datensatzverwaltung** > > Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="f596f-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="f596f-136">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-136">If you are not using records management:</span></span>
        - <span data-ttu-id="f596f-137">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="f596f-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="f596f-138">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="f596f-138">Don't immediately see your option?</span></span> <span data-ttu-id="f596f-139">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="f596f-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="f596f-140">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f596f-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="f596f-141">Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="f596f-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="f596f-142">Wenn Sie eine vorhandene Aufbewahrungsbezeichnungsrichtlinie bearbeiten möchten, wählen Sie sie aus, und wählen Sie dann **Richtlinie bearbeiten** aus, um den gleichen Assistenten zu starten, mit dem Sie die Richtlinienbeschreibung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="f596f-142">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="f596f-143">Wählen Sie alternativ eine der verfügbaren **Bearbeitungsoptionen** aus, um direkt zur entsprechenden Seite zu wechseln und die Aktualisierung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f596f-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="f596f-144">Aufbewahrungsbezeichnungen automatisch anwenden</span><span class="sxs-lookup"><span data-stu-id="f596f-144">Auto-apply a retention label</span></span>

<span data-ttu-id="f596f-145">Richten Sie eine Aufbewahrungsbezeichnung so ein, dass sie basierend auf den von Ihnen festgelegten Bedingungen automatisch angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f596f-145">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="f596f-146">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="f596f-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="f596f-147">Wenn Sie die Datensatzverwaltung verwenden: **Informationsgovernance**:</span><span class="sxs-lookup"><span data-stu-id="f596f-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="f596f-148">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="f596f-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="f596f-149">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="f596f-149">If you are not using records management:</span></span>
        - <span data-ttu-id="f596f-150">**Lösungen** > **Informationgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="f596f-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="f596f-151">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="f596f-151">Don't immediately see your option?</span></span> <span data-ttu-id="f596f-152">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="f596f-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="f596f-153">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f596f-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="f596f-154">Informationen zum Konfigurieren der Bedingungen, die zur automatischen Anwendung der Aufbewahrungsbezeichnung führen, finden Sie im Abschnitt [Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen](#configuring-conditions-for-auto-apply-retention-labels) auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="f596f-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="f596f-155">Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="f596f-155">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="f596f-156">Wenn Sie eine vorhandene Richtlinie zum automatischen Anwenden von Bezeichnungen bearbeiten möchten, wählen Sie sie aus, und wählen Sie dann **Richtlinie bearbeiten** aus, um den gleichen Assistenten zu starten, mit dem Sie die Richtlinienbeschreibung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="f596f-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="f596f-157">Wählen Sie alternativ eine der verfügbaren **Bearbeitungsoptionen** aus, um direkt zur entsprechenden Seite zu wechseln und die Aktualisierung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f596f-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="f596f-158">Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="f596f-159">Aufbewahrungsbezeichnungen können automatisch auf Inhalte angewendet werden, wenn diese folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="f596f-159">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="f596f-160">Der Inhalt enthält bestimmte vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="f596f-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="f596f-161">Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f596f-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="f596f-162">Eine Übereinstimmung für trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="f596f-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Seite "Bedingung auswählen" für automatisch angewendete Bezeichnungen](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="f596f-164">Es kann bis zu sieben Tage dauern, bis die automatisch angewendeten Aufbewahrungsbezeichnungen für alle Inhalte, die den von Ihnen konfigurierten Bedingungen entsprechen, wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="f596f-164">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="f596f-165">Automatisches Anwenden von Bezeichnungen auf Inhalte mit bestimmten Typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="f596f-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="f596f-166">Wenn Sie automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationen erstellen, wird dieselbe Liste von Richtlinienvorlagen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f596f-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="f596f-167">Jede Richtlinienvorlage ist für die Suche nach bestimmten Typen vertraulicher Informationen vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f596f-167">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="f596f-168">Die hier wiedergegebene Vorlage sucht beispielsweise nach US-amerikanischen Steuernummern für Privatpersonen (ITIN), Sozialversicherungsnummern (SSN) und Reisepassnummern.</span><span class="sxs-lookup"><span data-stu-id="f596f-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="f596f-169">Weitere Informationen zu DLP finden Sie unter [Übersicht über Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f596f-169">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Richtlinienvorlagen für Arten von vertraulichen Informationen](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="f596f-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span><span class="sxs-lookup"><span data-stu-id="f596f-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="f596f-172">In the example shown here, a retention label will be auto-applied only when:</span><span class="sxs-lookup"><span data-stu-id="f596f-172">In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="f596f-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="f596f-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="f596f-174">You can delete the **max** value so that it changes to **any**.</span><span class="sxs-lookup"><span data-stu-id="f596f-174">You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="f596f-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span><span class="sxs-lookup"><span data-stu-id="f596f-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="f596f-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span><span class="sxs-lookup"><span data-stu-id="f596f-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="f596f-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span><span class="sxs-lookup"><span data-stu-id="f596f-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="f596f-178">Weitere Informationen zu diesen Optionen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="f596f-178">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Optionen zum Identifizieren von Typen vertraulicher Informationen](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="f596f-180">Automatisches Anwenden von Bezeichnungen auf Inhalte mit Stichwörtern oder durchsuchbare Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f596f-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="f596f-181">You can auto-apply labels to content that satisfies certain conditions.</span><span class="sxs-lookup"><span data-stu-id="f596f-181">You can auto-apply labels to content that satisfies certain conditions.</span></span> <span data-ttu-id="f596f-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span><span class="sxs-lookup"><span data-stu-id="f596f-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span></span> <span data-ttu-id="f596f-183">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="f596f-183">You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="f596f-184">Weitere Informationen zur Abfragesyntax finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="f596f-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="f596f-185">Syntaxreferenz für die Keyword Query Language (KQL)</span><span class="sxs-lookup"><span data-stu-id="f596f-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="f596f-186">Query-based labels use the search index to identify content.</span><span class="sxs-lookup"><span data-stu-id="f596f-186">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="f596f-187">For more information on valid searchable properties, see:</span><span class="sxs-lookup"><span data-stu-id="f596f-187">For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="f596f-188">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="f596f-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="f596f-189">Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="f596f-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="f596f-190">Beispiele für Abfragen:</span><span class="sxs-lookup"><span data-stu-id="f596f-190">Examples queries:</span></span>

- <span data-ttu-id="f596f-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="f596f-191">Exchange</span></span>
    - <span data-ttu-id="f596f-192">Betreff: „Vierteljährliche Finanzdaten“</span><span class="sxs-lookup"><span data-stu-id="f596f-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="f596f-193">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="f596f-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="f596f-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f596f-194">@contoso.com</span></span>
- <span data-ttu-id="f596f-195">SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="f596f-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="f596f-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="f596f-196">contenttype:contract</span></span>
    - <span data-ttu-id="f596f-197">site:https</span><span class="sxs-lookup"><span data-stu-id="f596f-197">site:https</span></span><!--nolink--><span data-ttu-id="f596f-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="f596f-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Abfrage-Editor](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="f596f-200">Automatisches Anwenden von Bezeichnungen auf Inhalte mithilfe von trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="f596f-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="f596f-201">Wenn Sie die Option für eine trainierbare Klassifizierung auswählen, können Sie eine der integrierten Klassifizierungen oder eine benutzerdefinierte Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="f596f-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="f596f-202">Zu den integrierten Klassifizierungen gehören **Lebensläufe**, **Quellcode**, **Gezielte Belästigung**, **Vulgäre Ausdrücke** und **Drohungen**:</span><span class="sxs-lookup"><span data-stu-id="f596f-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Trainierbare Klassifizierung auswählen](../media/retention-label-classifers.png)

<span data-ttu-id="f596f-204">Wenn Sie eine Bezeichnung mithilfe dieser Option automatisch anwenden möchten, müssen SharePoint Online-Websites und -Postfächer mindestens 10 MB Daten umfassen.</span><span class="sxs-lookup"><span data-stu-id="f596f-204">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="f596f-205">Weitere Informationen zu trainierbaren Klassifizierungen finden Sie unter [Erste Schritte mit trainierbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="f596f-205">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="f596f-206">Eine Beispielkonfiguration finden Sie unter [Vorbereiten und Verwenden einer eingebauten Klassifizierung](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="f596f-206">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="f596f-207">Wie lange es dauert, bis Aufbewahrungsbezeichnungen wirksam werden</span><span class="sxs-lookup"><span data-stu-id="f596f-207">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="f596f-208">Wenn Sie Aufbewahrungsbezeichnungen veröffentlichen oder automatisch anwenden, werden sie nicht sofort wirksam:</span><span class="sxs-lookup"><span data-stu-id="f596f-208">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="f596f-209">Zuerst muss die Bezeichnungsrichtlinie aus dem Admin Center mit den Standorten der Richtlinie synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f596f-209">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="f596f-210">Dann dauert es u. U. etwas, bis der jeweilige Ort den Endbenutzern veröffentlichte Aufbewahrungsbezeichnungen zur Verfügung stellt oder Bezeichnungen automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f596f-210">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="f596f-211">Die jeweilige Dauer ist vom Ort und der Art der Aufbewahrungsbezeichnung abhängig.</span><span class="sxs-lookup"><span data-stu-id="f596f-211">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="f596f-212">Veröffentlichte Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-212">Published retention labels</span></span>

<span data-ttu-id="f596f-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span><span class="sxs-lookup"><span data-stu-id="f596f-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="f596f-214">However, allow up to seven days.</span><span class="sxs-lookup"><span data-stu-id="f596f-214">However, allow up to seven days.</span></span> <span data-ttu-id="f596f-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span><span class="sxs-lookup"><span data-stu-id="f596f-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="f596f-216">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f596f-216">For example:</span></span>
  
![Diagramm, wann manuelle Bezeichnungen wirksam werden](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="f596f-218">Automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-218">Auto-apply retention labels</span></span>

<span data-ttu-id="f596f-219">Wenn Sie Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, die bestimmte Bedingungen erfüllen, kann es bis zu sieben Tage dauern, bevor die Aufbewahrungsbezeichnungen auf alle vorhandenen Inhalte angewendet werden, die diesen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f596f-219">If you auto-apply retention labels to content matching specific conditions, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramm, wann automatisch angewendete Bezeichnungen wirksam werden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="f596f-221">So überprüfen Sie den Status der in Exchange veröffentlichten Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f596f-221">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="f596f-222">In Exchange Online werden Aufbewahrungsbezeichnungen für Endbenutzer über einen Prozess bereitgestellt, der alle sieben Tage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f596f-222">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="f596f-223">Wenn Sie Powershell verwenden, können Sie sehen, wenn der Prozess zuletzt ausgeführt wurde und damit ermitteln, wann er erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f596f-223">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="f596f-224">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="f596f-224">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="f596f-225">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f596f-225">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## Updating retention labels and their policies

When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Find the PowerShell cmdlets for retention labels

To use the retention label cmdlets:
  
1. [Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use these Office 365 Security & Compliance Center cmdlets:
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
