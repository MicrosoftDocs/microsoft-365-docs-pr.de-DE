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
ms.openlocfilehash: 4a9343ddfe07bbc4bf535759a39268915fd83ca1
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352242"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="e1201-103">Erstellen, Veröffentlichen und automatisches Anwenden von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="e1201-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e1201-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e1201-105">Verwenden Sie die folgenden Informationen, um [Aufbewahrungsbezeichnungen](labels.md) zu erstellen und diese dann automatisch auf Dokumente und E-Mails anzuwenden, oder um sie zu veröffentlichen, damit sie von den Benutzern manuell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e1201-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="e1201-106">Aufbewahrungsbezeichnungen helfen Ihnen bei der Aufbewahrung wichtiger Elemente und bei der Löschung alles anderen.</span><span class="sxs-lookup"><span data-stu-id="e1201-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="e1201-107">Sie werden auch als Teil einer [Datensatzverwaltungslösung](records-management.md) für Ihre Microsoft 365-Daten verwendet, um ein Element als Datensatz zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e1201-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="e1201-108">Wo Sie Ihre Aufbewahrungsbezeichnungen erstellen und konfigurieren, hängt davon ab, ob Sie die Datensatzverwaltung verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e1201-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="e1201-109">Es werden Anweisungen für beide Szenarios bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e1201-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e1201-110">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e1201-110">Before you begin</span></span>

<span data-ttu-id="e1201-111">Die Mitglieder Ihres Complianceteams, die Aufbewahrungsbezeichnungen erstellen sollen, benötigen Berechtigungen für das Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e1201-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e1201-112">Standardmäßig hat Ihr Mandantenadministrator Zugriff auf diesen Speicherort und kann anderen Personen den Zugriff auf das Security &amp; Compliance Center gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Zu diesem Zweck wird empfohlen, dass Sie zur Seite **Berechtigungen** des Security &amp; Compliance Centers gehen, die Rollengruppe **Compliance-Administrator** bearbeiten und dieser Rollengruppe Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1201-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="e1201-113">Weitere Informationen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1201-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="e1201-p104">Diese Berechtigungen sind nur erforderlich, um Aufbewahrungsbezeichnungen und eine Aufbewahrungsrichtlinie zu erstellen und anzuwenden. Für die Durchsetzung von Richtlinien ist kein Zugriff auf Inhalte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1201-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="e1201-116">Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="e1201-117">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="e1201-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="e1201-118">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-118">If you are using records management:</span></span>
        - <span data-ttu-id="e1201-119">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**</span><span class="sxs-lookup"><span data-stu-id="e1201-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="e1201-120">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-120">If you are not using records management:</span></span>
       - <span data-ttu-id="e1201-121">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**</span><span class="sxs-lookup"><span data-stu-id="e1201-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="e1201-122">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="e1201-122">Don't immediately see your option?</span></span> <span data-ttu-id="e1201-123">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1201-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="e1201-124">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1201-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="e1201-125">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="e1201-126">Informationen zu den Dateiplanbeschreibungen finden Sie unter [Übersicht über den Dateiplan-Manager.](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e1201-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="e1201-127">Wenn Sie mithilfe der Aufbewahrungsbezeichnung Inhalt als Datensatz deklarieren möchten, aktivieren Sie das Kontrollkästchen **Bezeichnung zum Klassifizieren von Inhalt als Datensatz verwenden**.</span><span class="sxs-lookup"><span data-stu-id="e1201-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="e1201-128">Wiederholen Sie diese Schritte, um weitere Bezeichnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1201-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="e1201-129">Um eine vorhandene Bezeichnung zu bearbeiten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e1201-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="e1201-130">Damit wird derselbe Assistent gestartet, der es Ihnen ermöglicht, die Beschreibungen und Einstellungen für Bezeichnungen in Schritt 2 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e1201-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="e1201-131">Veröffentlichen von Aufbewahrungsbezeichnungen durch die Erstellung einer Aufbewahrungsbezeichnungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e1201-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="e1201-132">Veröffentlichen Sie Aufbewahrungsbezeichnungen, damit sie von Benutzern manuell angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e1201-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="e1201-133">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="e1201-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="e1201-134">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-134">If you are using records management:</span></span>
        - <span data-ttu-id="e1201-135">**Lösungen** > **Datensatzverwaltung** > > Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="e1201-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="e1201-136">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-136">If you are not using records management:</span></span>
        - <span data-ttu-id="e1201-137">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="e1201-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="e1201-138">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="e1201-138">Don't immediately see your option?</span></span> <span data-ttu-id="e1201-139">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1201-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="e1201-140">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1201-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="e1201-141">Informationen zum Konfigurieren der Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](#retention-labels-and-locations) auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="e1201-141">For information about configuring the locations, see the [Retention labels and locations](#retention-labels-and-locations) section on this page.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="e1201-142">Aufbewahrungsbezeichnungen automatisch anwenden</span><span class="sxs-lookup"><span data-stu-id="e1201-142">Auto-apply a retention label</span></span>

<span data-ttu-id="e1201-143">Richten Sie eine Aufbewahrungsbezeichnung so ein, dass sie basierend auf den von Ihnen festgelegten Bedingungen automatisch angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1201-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="e1201-144">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="e1201-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="e1201-145">Wenn Sie die Datensatzverwaltung verwenden: **Informationsgovernance**:</span><span class="sxs-lookup"><span data-stu-id="e1201-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="e1201-146">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="e1201-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="e1201-147">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="e1201-147">If you are not using records management:</span></span>
        - <span data-ttu-id="e1201-148">**Lösungen** > **Informationgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnung automatisch anwenden**</span><span class="sxs-lookup"><span data-stu-id="e1201-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="e1201-149">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="e1201-149">Don't immediately see your option?</span></span> <span data-ttu-id="e1201-150">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1201-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="e1201-151">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1201-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="e1201-152">Informationen zum Konfigurieren der Bedingungen, die zur automatischen Anwendung der Aufbewahrungsbezeichnung führen, finden Sie im Abschnitt [Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen](#configuring-conditions-for-auto-apply-retention-labels) auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="e1201-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="e1201-153">Informationen zum Konfigurieren der Speicherorte finden Sie im nächsten Abschnitt auf dieser Seite, [Aufbewahrungsbezeichnungen und -speicherorte](#retention-labels-and-locations).</span><span class="sxs-lookup"><span data-stu-id="e1201-153">For information about configuring the locations, see the next section on this page, [Retention labels and locations](#retention-labels-and-locations).</span></span>

## <a name="retention-labels-and-locations"></a><span data-ttu-id="e1201-154">Aufbewahrungsbezeichnungen und -speicherorte</span><span class="sxs-lookup"><span data-stu-id="e1201-154">Retention labels and locations</span></span>

<span data-ttu-id="e1201-155">Verschiedene Arten von Aufbewahrungsbezeichnungen können an verschiedenen Speicherorten veröffentlicht werden, je nach Funktion der Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="e1201-155">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="e1201-156">**Wenn für die Aufbewahrungsbezeichnung Folgendes gilt:**</span><span class="sxs-lookup"><span data-stu-id="e1201-156">**If the retention label is…**</span></span>|<span data-ttu-id="e1201-157">**So kann die Bezeichnungsrichtlinie angewendet werden auf...**</span><span class="sxs-lookup"><span data-stu-id="e1201-157">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1201-158">für Endbenutzer veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="e1201-158">Published to end users</span></span>  <br/> |<span data-ttu-id="e1201-159">Gruppen in Exchange, SharePoint, OneDrive, Office 365</span><span class="sxs-lookup"><span data-stu-id="e1201-159">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="e1201-160">basierend auf Typen vertraulicher Informationen automatisch angewendet</span><span class="sxs-lookup"><span data-stu-id="e1201-160">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="e1201-161">Exchange (nur alle Postfächer), SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1201-161">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="e1201-162">basieren auf einer Abfrage automatisch angewendet</span><span class="sxs-lookup"><span data-stu-id="e1201-162">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="e1201-163">Gruppen in Exchange, SharePoint, OneDrive, Office 365</span><span class="sxs-lookup"><span data-stu-id="e1201-163">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="e1201-164">In Exchange werden automatisch angewendete Bezeichnungen (sowohl für Abfragen als auch für vertrauliche Informationstypen) nur auf neu gesendete Nachrichten (in Übertragung begriffene Daten) angewendet, und nicht auf alle Elemente, die sich derzeit im Postfach befinden (ruhende Daten).</span><span class="sxs-lookup"><span data-stu-id="e1201-164">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="e1201-165">Außerdem können automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationstypen nur auf alle Postfächer angewendet werden; Sie können keine bestimmten Postfächer dafür auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1201-165">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="e1201-166">Öffentliche Ordner in Exchange und Skype unterstützen keine Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="e1201-166">Exchange public folders and Skype do not support retention labels.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="e1201-167">Konfigurieren der Bedingungen für automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-167">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="e1201-168">Aufbewahrungsbezeichnungen können automatisch auf Inhalte angewendet werden, wenn diese folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="e1201-168">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="e1201-169">Der Inhalt enthält bestimmte vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="e1201-169">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="e1201-170">Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e1201-170">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="e1201-171">Eine Übereinstimmung für trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="e1201-171">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Seite "Bedingung auswählen" für automatisch angewendete Bezeichnungen](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="e1201-173">Es kann bis zu sieben Tage dauern, bis die automatisch angewendeten Aufbewahrungsbezeichnungen für alle Inhalte, die den von Ihnen konfigurierten Bedingungen entsprechen, wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e1201-173">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="e1201-174">Automatisches Anwenden von Bezeichnungen auf Inhalte mit bestimmten Typen von vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="e1201-174">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="e1201-175">Wenn Sie automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationen erstellen, wird dieselbe Liste von Richtlinienvorlagen wie beim Erstellen einer DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1201-175">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="e1201-176">Jede Richtlinienvorlage ist für die Suche nach bestimmten Typen vertraulicher Informationen vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e1201-176">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="e1201-177">Die hier wiedergegebene Vorlage sucht beispielsweise nach US-amerikanischen Steuernummern für Privatpersonen (ITIN), Sozialversicherungsnummern (SSN) und Reisepassnummern.</span><span class="sxs-lookup"><span data-stu-id="e1201-177">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="e1201-178">Weitere Informationen zu DLP finden Sie unter [Übersicht über Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e1201-178">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Richtlinienvorlagen für Arten von vertraulichen Informationen](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="e1201-p112">Nach der Auswahl einer Richtlinienvorlage können Sie alle Arten von vertraulichen Informationen hinzufügen oder entfernen, und Sie können die Instanzenanzahl ändern und die Genauigkeit abgleichen. Im hier gezeigten Beispiel wird eine Aufbewahrungsbezeichnung nur dann automatisch angewendet, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="e1201-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="e1201-p113">Der Inhalt besteht aus 1 bis 9 Instanzen einer der drei folgenden Typen von vertraulichen Informationen. Sie können den **max**-Wert löschen, sodass er sich in **any** ändert.</span><span class="sxs-lookup"><span data-stu-id="e1201-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="e1201-p114">Der Typ der vertraulichen Informationen, der erkannt wird, hat eine Übereinstimmungsgenauigkeit (oder Vertrauensstufe) von mindestens 75. Viele Typen vertraulicher Informationen werden mit mehreren Mustern definiert, wobei ein Muster mit einer höheren Übereinstimmungsgenauigkeit mehr Nachweise (z. B. Stichwörter, Datumsangaben oder Adressen) erfordert, während ein Muster mit einer niedrigeren Übereinstimmungsgenauigkeit weniger Nachweise erfordert. Einfach ausgedrückt: Je niedriger die **min**-Übereinstimmungsgenauigkeit, desto einfacher ist es für den Inhalt, die Bedingung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e1201-p114">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="e1201-187">Weitere Informationen zu diesen Optionen finden Sie unter [Optimieren von Regeln, um die Übereinstimmung zu vereinfachen oder zu erschweren](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="e1201-187">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Optionen zum Identifizieren von Typen vertraulicher Informationen](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="e1201-189">Automatisches Anwenden von Bezeichnungen auf Inhalte mit Stichwörtern oder durchsuchbare Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e1201-189">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="e1201-p115">Sie können automatische Bezeichnungen auf Inhalte anwenden, die bestimmte Kriterien erfüllen. Die derzeit verfügbaren Bedingungen unterstützen das Anwenden einer Bezeichnung auf Inhalte, die bestimmte Wörter, Ausdrücke oder durchsuchbare Eigenschaften enthalten. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie UND, ODER und NICHT verfeinern.</span><span class="sxs-lookup"><span data-stu-id="e1201-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="e1201-193">Weitere Informationen zur Abfragesyntax finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e1201-193">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="e1201-194">Syntaxreferenz für die Keyword Query Language (KQL)</span><span class="sxs-lookup"><span data-stu-id="e1201-194">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="e1201-p116">Abfragebasierte Bezeichnungen verwenden den Suchindex zum Identifizieren von Inhalten. Weitere Informationen zu gültigen durchsuchbaren Eigenschaften finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e1201-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="e1201-197">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="e1201-197">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="e1201-198">Übersicht über durchforstete und verwaltete Eigenschaften in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="e1201-198">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="e1201-199">Beispiele für Abfragen:</span><span class="sxs-lookup"><span data-stu-id="e1201-199">Examples queries:</span></span>

- <span data-ttu-id="e1201-200">Exchange</span><span class="sxs-lookup"><span data-stu-id="e1201-200">Exchange</span></span>
    - <span data-ttu-id="e1201-201">Betreff: „Vierteljährliche Finanzdaten“</span><span class="sxs-lookup"><span data-stu-id="e1201-201">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="e1201-202">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="e1201-202">recipients:garthf</span></span><!--nolink--><span data-ttu-id="e1201-203">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e1201-203">@contoso.com</span></span>
- <span data-ttu-id="e1201-204">SharePoint und OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1201-204">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="e1201-205">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="e1201-205">contenttype:contract</span></span>
    - <span data-ttu-id="e1201-206">site:https</span><span class="sxs-lookup"><span data-stu-id="e1201-206">site:https</span></span><!--nolink--><span data-ttu-id="e1201-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="e1201-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Abfrage-Editor](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="e1201-209">Automatisches Anwenden von Bezeichnungen auf Inhalte mithilfe von trainierbare Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="e1201-209">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="e1201-210">Wenn Sie die Option für eine trainierbare Klassifizierung auswählen, können Sie eine der integrierten Klassifizierungen oder eine benutzerdefinierte Klassifizierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1201-210">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="e1201-211">Zu den integrierten Klassifizierungen gehören **Lebensläufe**, **Quellcode**, **Gezielte Belästigung**, **Vulgäre Ausdrücke** und **Drohungen**:</span><span class="sxs-lookup"><span data-stu-id="e1201-211">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Trainierbare Klassifizierung auswählen](../media/retention-label-classifers.png)

<span data-ttu-id="e1201-213">Wenn Sie eine Bezeichnung mithilfe dieser Option automatisch anwenden möchten, müssen SharePoint Online-Websites und -Postfächer mindestens 10 MB Daten umfassen.</span><span class="sxs-lookup"><span data-stu-id="e1201-213">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="e1201-214">Weitere Informationen zu trainierbaren Klassifizierungen finden Sie unter [Erste Schritte mit trainierbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="e1201-214">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="e1201-215">Eine Beispielkonfiguration finden Sie unter [Vorbereiten und Verwenden einer eingebauten Klassifizierung](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="e1201-215">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="e1201-216">Wie lange es dauert, bis Aufbewahrungsbezeichnungen wirksam werden</span><span class="sxs-lookup"><span data-stu-id="e1201-216">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="e1201-217">Wenn Sie Aufbewahrungsbezeichnungen veröffentlichen oder automatisch anwenden, werden sie nicht sofort wirksam:</span><span class="sxs-lookup"><span data-stu-id="e1201-217">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="e1201-218">Zuerst muss die Bezeichnungsrichtlinie aus dem Admin Center mit den Standorten der Richtlinie synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1201-218">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="e1201-219">Dann dauert es u. U. etwas, bis der jeweilige Ort den Endbenutzern veröffentlichte Aufbewahrungsbezeichnungen zur Verfügung stellt oder Bezeichnungen automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1201-219">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="e1201-220">Die jeweilige Dauer ist vom Ort und der Art der Aufbewahrungsbezeichnung abhängig.</span><span class="sxs-lookup"><span data-stu-id="e1201-220">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="e1201-221">Veröffentlichte Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-221">Published retention labels</span></span>

<span data-ttu-id="e1201-p119">Wenn Sie Aufbewahrungsbezeichnungen auf SharePoint oder OneDrive veröffentlichen, kann es bis zu einem Tag dauern, bevor diese Aufbewahrungsbezeichnungen den Endbenutzern angezeigt werden. Darüber hinaus kann es, wenn Sie Aufbewahrungsbezeichnungen auf Exchange veröffentlichen, bis zu sieben Tage dauern, bevor sie den Endbenutzern zur Verfügung stehen. Außerdem muss das Postfach mindestens 10 MB Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1201-p119">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Diagramm, wann manuelle Bezeichnungen wirksam werden](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="e1201-225">Automatisch angewendete Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-225">Auto-apply retention labels</span></span>

<span data-ttu-id="e1201-226">Wenn Sie Aufbewahrungsbezeichnungen automatisch auf Inhalte anwenden, die bestimmte Bedingungen erfüllen, kann es bis zu sieben Tage dauern, bevor die Aufbewahrungsbezeichnungen auf alle vorhandenen Inhalte angewendet werden, die diesen Kriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e1201-226">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagramm, wann automatisch angewendete Bezeichnungen wirksam werden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="e1201-228">So überprüfen Sie den Status der in Exchange veröffentlichten Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1201-228">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="e1201-p120">In Exchange Online werden Aufbewahrungsbezeichnungen Endbenutzern anhand eines Prozesses bereitgestellt, die alle sieben Tage ausgeführt wird. Mit PowerShell können Sie sehen, wann dieser Prozess zuletzt ausgeführt wurde, und so ermitteln, wann er erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1201-p120">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="e1201-231">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="e1201-231">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="e1201-232">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="e1201-232">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="e1201-233">In den Ergebnissen zeigt die Eigenschaft `ELCLastSuccessTimeStamp` (UTC), wann das System zuletzt Ihr Postfach verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="e1201-233">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="e1201-234">Wenn dies seit dem Zeitpunkt der Richtlinienerstellung nicht geschehen ist, werden die Bezeichnungen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1201-234">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="e1201-235">Um die Verarbeitung zu erzwingen, führen Sie `Start-ManagedFolderAssistant -Identity <user>` aus.</span><span class="sxs-lookup"><span data-stu-id="e1201-235">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="e1201-236">Wenn die Bezeichnungen nicht in Outlook im Web angezeigt werden und Sie denken, dass sie angezeigt werden sollten, müssen Sie den Cache des Browsers leeren (STRG + F5).</span><span class="sxs-lookup"><span data-stu-id="e1201-236">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="e1201-237">Aktualisieren von Aufbewahrungsbezeichnungen und der entsprechenden Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e1201-237">Updating retention labels and their policies</span></span>

<span data-ttu-id="e1201-238">Wenn Sie eine Aufbewahrungsbezeichnung, eine Aufbewahrungbezeichnungsrichtlinie oder eine Richtlinie für die automatische Anwendung bearbeiten, und diese Aufbewahrungsbezeichnung bereits auf Inhalte angewendet wird, werden die aktualisierten Einstellungen automatisch zusätzlich auf diese Inhalte sowie auf neu bezeichnete Inhalte angewendet.</span><span class="sxs-lookup"><span data-stu-id="e1201-238">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="e1201-239">Die PowerShell-Cmdlets für Aufbewahrungsbezeichnungen finden</span><span class="sxs-lookup"><span data-stu-id="e1201-239">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="e1201-240">So verwenden Sie die Cmdlets für Aufbewahrungsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="e1201-240">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="e1201-241">Herstellen einer Verbindung mit Office 365 Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1201-241">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="e1201-242">Verwenden Sie die folgenden Office 365 Security & Compliance Center-Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1201-242">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="e1201-243">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e1201-243">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="e1201-244">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e1201-244">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="e1201-245">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e1201-245">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="e1201-246">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e1201-246">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="e1201-247">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e1201-247">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="e1201-248">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e1201-248">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="e1201-249">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e1201-249">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="e1201-250">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e1201-250">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="e1201-251">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e1201-251">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="e1201-252">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e1201-252">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="e1201-253">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e1201-253">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="e1201-254">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e1201-254">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="e1201-255">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e1201-255">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="e1201-256">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e1201-256">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
