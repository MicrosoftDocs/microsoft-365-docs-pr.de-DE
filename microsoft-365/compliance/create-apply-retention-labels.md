---
title: Erstellen von Aufbewahrungsbezeichnungen für die Anwendung in Apps, um Inhalte beizubehalten oder zu löschen
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
description: Anweisungen zum Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen, damit Sie diese in Apps auf Inhalte anwenden können, die Sie beibehalten möchten und nicht benötigte Inhalte löschen können.
ms.openlocfilehash: a9105b404dbeef0ff6ef247ce613f4257c3d3b2a
ms.sourcegitcommit: 095b1f52f2e73e8d44195916984efeb0908c2ad8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48755554"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a><span data-ttu-id="48e48-103">Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps</span><span class="sxs-lookup"><span data-stu-id="48e48-103">Create retention labels and apply them in apps</span></span>

><span data-ttu-id="48e48-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="48e48-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="48e48-105">Dieses Szenario wird für alle Aufbewahrungsbezeichnungskonfigurationen unterstützt, einschließlich der [regulatorischen Datensätze](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="48e48-105">This scenario is supported for all retention label configurations, including [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="48e48-106">Verwenden Sie die folgenden Informationen, um [Aufbewahrungsbezeichnungen](retention.md) zu erstellen und zu veröffentlichen und anschließend auf Dokumente und E-Mails anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="48e48-106">Use the following information to help you create and publish [retention labels](retention.md), and then apply them to documents and emails.</span></span>

<span data-ttu-id="48e48-107">Aufbewahrungsbezeichnungen helfen Ihnen dabei, auf Elementebene (Dokument oder E-Mail) benötigte Inhalte beizubehalten und nicht benötigte Inhalte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="48e48-107">Retention labels help you retain what you need and delete what you don't at the item level (document or email).</span></span> <span data-ttu-id="48e48-108">Sie werden auch als Teil einer [Datensatzverwaltungslösung](records-management.md) für Ihre Microsoft 365-Daten verwendet, um ein Element als Datensatz zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="48e48-108">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="48e48-109">Der Vorgang, mit dem Personen in Ihrer Organisation Aufbewahrungsbezeichnungen zur Verfügung gestellt werden, damit sie Inhalte klassifizieren können, besteht aus zwei Schritten:</span><span class="sxs-lookup"><span data-stu-id="48e48-109">Making retention labels available to people in your organization so that they can classify content is a two-step process:</span></span> 

1. <span data-ttu-id="48e48-110">Erstellen der Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="48e48-110">Create the retention labels.</span></span>

2. <span data-ttu-id="48e48-111">Veröffentlichen der Aufbewahrungsbezeichnungen mithilfe einer Richtlinie für Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="48e48-111">Publish the retention labels by using a retention label policy.</span></span>
  
![Diagramm der Rollen und Aufgaben für Bezeichnungen](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

<span data-ttu-id="48e48-113">Führen Sie anhand der nachfolgenden Anweisungen die beiden Administratorschritte aus.</span><span class="sxs-lookup"><span data-stu-id="48e48-113">Use the following instructions for the two admin steps.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="48e48-114">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="48e48-114">Before you begin</span></span>

<span data-ttu-id="48e48-115">Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="48e48-115">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="48e48-116">Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="48e48-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-create-and-publish-retention-labels"></a><span data-ttu-id="48e48-117">Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="48e48-117">How to create and publish retention labels</span></span>

<span data-ttu-id="48e48-118">Erstellen Sie zunächst Ihre Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="48e48-118">First, create your retention labels.</span></span> <span data-ttu-id="48e48-119">Erstellen Sie dann eine Bezeichnungsrichtlinie, um die Bezeichnungen auf Apps anwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="48e48-119">Then create a label policy to make the labels available to apply in apps.</span></span>

<span data-ttu-id="48e48-120">Wo Sie Ihre Aufbewahrungsbezeichnungen erstellen und konfigurieren, hängt davon ab, ob Sie die Datensatzverwaltung verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="48e48-120">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="48e48-121">Es werden Anweisungen für beide Szenarios bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48e48-121">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-retention-labels"></a><span data-ttu-id="48e48-122">Schritt 1: Erstellen der Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="48e48-122">Step 1: Create retention labels</span></span>

1. <span data-ttu-id="48e48-123">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="48e48-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="48e48-124">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="48e48-124">If you are using records management:</span></span>
        - <span data-ttu-id="48e48-125">**Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**</span><span class="sxs-lookup"><span data-stu-id="48e48-125">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="48e48-126">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="48e48-126">If you are not using records management:</span></span>
       - <span data-ttu-id="48e48-127">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**</span><span class="sxs-lookup"><span data-stu-id="48e48-127">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="48e48-128">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="48e48-128">Don't immediately see your option?</span></span> <span data-ttu-id="48e48-129">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="48e48-129">First select **Show all** .</span></span> 

2. <span data-ttu-id="48e48-130">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="48e48-130">Follow the prompts in the wizard.</span></span> <span data-ttu-id="48e48-131">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="48e48-131">If you are using records management:</span></span>
    
    - <span data-ttu-id="48e48-132">Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).</span><span class="sxs-lookup"><span data-stu-id="48e48-132">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="48e48-133">Wenn Sie Datensätze mithilfe der Aufbewahrungsbezeichnung deklarieren möchten, wählen Sie **Elemente als Datensätze markieren** oder **Elemente als regulatorische Datensätze markieren** aus.</span><span class="sxs-lookup"><span data-stu-id="48e48-133">To use the retention label to declare records, select **Mark items as records** , or **Mark items as regulatory records** .</span></span> <span data-ttu-id="48e48-134">Weitere Informationen finden Sie unter [Aufbewahrungsbezeichnungen zum Deklarieren von Datensätzen konfigurieren](declare-records.md#configuring-retention-labels-to-declare-records).</span><span class="sxs-lookup"><span data-stu-id="48e48-134">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="48e48-135">Nachdem Sie die Bezeichnung erstellt haben und die Optionen zum Veröffentlichen der Bezeichnung angezeigt werden, können Sie die Bezeichnung entweder automatisch anwenden oder einfach nur speichern: Wählen Sie **Bezeichnung vorerst nur speichern** und dann **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="48e48-135">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Just save the label for now** , and then select **Done** .</span></span>

4. <span data-ttu-id="48e48-136">Wiederholen Sie diese Schritte, um weitere Bezeichnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48e48-136">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="48e48-137">Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die Bezeichnungsbeschreibungen und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.</span><span class="sxs-lookup"><span data-stu-id="48e48-137">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-publish-retention-labels"></a><span data-ttu-id="48e48-138">Schritt 2: Veröffentlichen der Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="48e48-138">Step 2: Publish retention labels</span></span>

<span data-ttu-id="48e48-139">Veröffentlichen Sie Aufbewahrungsbezeichnungen, sodass sie von Benutzern in Apps wie SharePoint und Outlook angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="48e48-139">Publish retention labels so that they can be applied by users in apps, such as SharePoint and Outlook.</span></span>

1. <span data-ttu-id="48e48-140">Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:</span><span class="sxs-lookup"><span data-stu-id="48e48-140">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="48e48-141">Wenn Sie die Datensatzverwaltung verwenden:</span><span class="sxs-lookup"><span data-stu-id="48e48-141">If you are using records management:</span></span>
        - <span data-ttu-id="48e48-142">**Lösungen** > **Datensatzverwaltung** > > Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="48e48-142">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="48e48-143">Wenn Sie die Datensatzverwaltung nicht verwenden:</span><span class="sxs-lookup"><span data-stu-id="48e48-143">If you are not using records management:</span></span>
        - <span data-ttu-id="48e48-144">**Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="48e48-144">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="48e48-145">Sehen Sie nicht sofort die gewünschte Option?</span><span class="sxs-lookup"><span data-stu-id="48e48-145">Don't immediately see your option?</span></span> <span data-ttu-id="48e48-146">Wählen Sie zuerst **Alle anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="48e48-146">First select **Show all** .</span></span> 

2. <span data-ttu-id="48e48-147">Folgen Sie den Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="48e48-147">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="48e48-148">Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie im Abschnitt [Aufbewahrungsbezeichnungen und -speicherorte](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="48e48-148">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="48e48-149">Um eine vorhandene Richtlinie für Aufbewahrungsbezeichnungen zu bearbeiten (der Richtlinientyp ist **Veröffentlichen** ), markieren Sie sie, und wählen Sie dann die Option **Bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten.</span><span class="sxs-lookup"><span data-stu-id="48e48-149">To edit an existing retention label policy (the policy type is **Publish** ), select it, and then select the **Edit** option to start the Edit retention policy.</span></span> <span data-ttu-id="48e48-150">Mit diesem Assistenten können Sie die Richtlinienbeschreibung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern.</span><span class="sxs-lookup"><span data-stu-id="48e48-150">This wizard lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


## <a name="when-retention-labels-become-available-to-apply"></a><span data-ttu-id="48e48-151">Wann stehen die Aufbewahrungsbezeichnungen zur Anwendung zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="48e48-151">When retention labels become available to apply</span></span>

<span data-ttu-id="48e48-152">Wenn Sie Aufbewahrungsbezeichnungen in SharePoint oder OneDrive veröffentlichen, stehen diese Bezeichnungen den Endbenutzern in der Regel innerhalb eines Tages zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="48e48-152">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="48e48-153">Es kann jedoch bis zu sieben Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="48e48-153">However, allow up to seven days.</span></span> 

<span data-ttu-id="48e48-154">Wenn Sie Aufbewahrungsbezeichnungen in Exchange veröffentlichen, kann es bis zu sieben Tage dauern, bis diese Aufbewahrungsbezeichnungen den Endbenutzern angezeigt werden. Zusätzlich muss das Postfach mindestens 10 MB Datenvolumen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="48e48-154">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="48e48-155">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="48e48-155">For example:</span></span>
  
![Diagramm, wann manuelle Bezeichnungen wirksam werden](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

<span data-ttu-id="48e48-157">Wenn die Bezeichnungen nach sieben Tagen nicht erscheinen, überprüfen Sie den **Status** der Bezeichnungsrichtlinie, indem Sie sie auf der Seite **Richtlinien für Bezeichnungen** im Compliance Center auswählen.</span><span class="sxs-lookup"><span data-stu-id="48e48-157">If the labels don't appear after seven days, check the **Status** of the label policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="48e48-158">Wenn der Status **Aus (Fehler)** angezeigt wird und in den Details für die Standorte eine Meldung angezeigt wird, dass die Bereitstellung der Richtlinie (für SharePoint) oder der Versuch der Neuverteilung der Richtlinie (für OneDrive) länger als erwartet dauert, versuchen Sie, den PowerShell-Befehl [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) auszuführen, um die Richtlinienverteilung erneut zu versuchen:</span><span class="sxs-lookup"><span data-stu-id="48e48-158">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. [<span data-ttu-id="48e48-159">Herstellen einer Verbindung mit Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="48e48-159">Connect to Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="48e48-160">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="48e48-160">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="48e48-161">So überprüfen Sie den Status der in Exchange veröffentlichten Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="48e48-161">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="48e48-162">In Exchange Online werden Aufbewahrungsbezeichnungen für Endbenutzer über einen Prozess bereitgestellt, der alle sieben Tage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48e48-162">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="48e48-163">Wenn Sie PowerShell verwenden, können Sie sehen, wenn der Prozess zuletzt ausgeführt wurde und damit ermitteln, wann er erneut ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48e48-163">By using PowerShell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="48e48-164">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="48e48-164">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="48e48-165">Führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="48e48-165">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

In addition, when you use [SharePoint Syntex](../contentunderstanding/index.md) and publish retention labels to SharePoint locations, you can [apply a retention label to a document understanding model](../contentunderstanding/apply-a-retention-label-to-a-model.md) so that identified documents are automatically labeled.

### Manually apply retention labels 

End users, as well as administrators, can manually apply retention labels from the following locations:  

- Outlook and Outlook on the web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)
    
Use the following sections to understand how to apply retention labels. 

#### Applying retention labels in Outlook

To label an item in the Outlook desktop client, select the item. On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label. 
  
![Assign Policy button](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label. 

After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.
  
You can also apply retention labels to folders, in which case:
  
- All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page. 
    
- If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicitly assigned retention labels. 
    
- If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.
    
- If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with Outlook on the web, you can also apply retention labels to folders. 

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Office 365 groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location inherit the default retention label. Although the same label is applied, each document will be retained and deleted separately, according to the start of the retention period setting in the label. 
  
For a document library, the default label configuration is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library. 
  
For example, if you have a retention label for marketing materials, and you know a specific document library contains only that type of content, you can make the **Marketing Materials** retention label the default label for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
If you apply a default retention label to existing items in the library, folder, or document set:
  
- All items in the library, folder, or document set automatically get the same retention label, **except** for items that already have a retention label applied to them.
    
- If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items that were manually labeled.
    
- If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label. If the item does not have a label before moving, it will take on the default retention label of the new location.

**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations. When you move a new item into a location with a record label, that item is labeled a record. However, if you change the default retention label to a label that doesn't declare content as a record, that action does not remove the record label from the individual items; those items retain their record label. Only a site collection admin can explicitly remove or change the retention label of record items.

For more information about retention labels that declare content as a record, see [Records](records-management.md#records).

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)

Although the UI refers to retention policies, it's your retention labels that display here and can be selected, not your retention policies.

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](automate-event-driven-retention.md)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)
