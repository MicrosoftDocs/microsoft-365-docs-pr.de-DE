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
ms.openlocfilehash: 7c13158d9ce2857c01cad60c77b6f27bce6d3b6b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107647"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a>Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Dieses Szenario wird für alle Aufbewahrungsbezeichnungskonfigurationen unterstützt, einschließlich der [regulatorischen Datensätze](records-management.md#records).

Verwenden Sie die folgenden Informationen, um [Aufbewahrungsbezeichnungen](retention.md) zu erstellen und zu veröffentlichen und anschließend auf Dokumente und E-Mails anzuwenden.

Aufbewahrungsbezeichnungen helfen Ihnen dabei, auf Elementebene (Dokument oder E-Mail) benötigte Inhalte beizubehalten und nicht benötigte Inhalte zu löschen. Sie werden auch als Teil einer [Datensatzverwaltungslösung](records-management.md) für Ihre Microsoft 365-Daten verwendet, um ein Element als Datensatz zu deklarieren.

Der Vorgang, mit dem Personen in Ihrer Organisation Aufbewahrungsbezeichnungen zur Verfügung gestellt werden, damit sie Inhalte klassifizieren können, besteht aus zwei Schritten: 

1. Erstellen der Aufbewahrungsbezeichnungen.

2. Veröffentlichen der Aufbewahrungsbezeichnungen mithilfe einer Richtlinie für Aufbewahrungsbezeichnungen.
  
![Diagramm der Rollen und Aufgaben für Bezeichnungen](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

Führen Sie anhand der nachfolgenden Anweisungen die beiden Administratorschritte aus.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsbezeichnungen und deren Richtlinien. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-create-and-publish-retention-labels"></a>Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen

Erstellen Sie zunächst Ihre Aufbewahrungsbezeichnungen. Erstellen Sie dann eine Bezeichnungsrichtlinie, um die Bezeichnungen auf Apps anwenden zu können.

Wo Sie Ihre Aufbewahrungsbezeichnungen erstellen und konfigurieren, hängt davon ab, ob Sie die Datensatzverwaltung verwenden oder nicht. Es werden Anweisungen für beide Szenarios bereitgestellt.

### <a name="step-1-create-retention-labels"></a>Schritt 1: Erstellen der Aufbewahrungsbezeichnungen

1. Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:
    
    - Wenn Sie die Datensatzverwaltung verwenden:
        - **Lösungen** > **Datensatzverwaltung** >  Registerkarte **Dateiplan** > **+ Bezeichnung erstellen** > **Aufbewahrungsbezeichnung**
        
    - Wenn Sie die Datensatzverwaltung nicht verwenden:
       - **Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungen** > + **Bezeichnung erstellen**
    
    Sehen Sie nicht sofort die gewünschte Option? Wählen Sie zuerst **Alle anzeigen** aus. 

2. Folgen Sie den Anweisungen des Assistenten. Wenn Sie die Datensatzverwaltung verwenden:
    
    - Informationen zu den Dateiplanbeschreibungen finden Sie unter [Verwenden des Dateiplans zum Verwalten von Aufbewahrungsbezeichnungen](file-plan-manager.md).
    
    - Wenn Sie Datensätze mithilfe der Aufbewahrungsbezeichnung deklarieren möchten, wählen Sie **Elemente als Datensätze markieren** oder **Elemente als regulatorische Datensätze markieren** aus. Weitere Informationen finden Sie unter [Aufbewahrungsbezeichnungen zum Deklarieren von Datensätzen konfigurieren](declare-records.md#configuring-retention-labels-to-declare-records).

3. Nachdem Sie die Bezeichnung erstellt haben und die Optionen zum Veröffentlichen der Bezeichnung angezeigt werden, können Sie die Bezeichnung entweder automatisch anwenden oder einfach nur speichern: Wählen Sie **Bezeichnung vorerst nur speichern** und dann **Fertig** aus.

4. Wiederholen Sie diese Schritte, um weitere Bezeichnungen zu erstellen.

Wenn Sie eine vorhandene Bezeichnung bearbeiten möchten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten, mit dem Sie die Bezeichnungsbeschreibungen und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern können.

### <a name="step-2-publish-retention-labels"></a>Schritt 2: Veröffentlichen der Aufbewahrungsbezeichnungen

Veröffentlichen Sie Aufbewahrungsbezeichnungen, sodass sie von Benutzern in Apps wie SharePoint und Outlook angewendet werden können.

1. Navigieren Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) zu einem der folgenden Orte:
    
    - Wenn Sie die Datensatzverwaltung verwenden:
        - **Lösungen** > **Datensatzverwaltung** > > Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**
    
    - Wenn Sie die Datensatzverwaltung nicht verwenden:
        - **Lösungen** > **Informationsgovernance** >  Registerkarte **Bezeichnungsrichtlinien** > **Bezeichnungen veröffentlichen**
    
    Sehen Sie nicht sofort die gewünschte Option? Wählen Sie zuerst **Alle anzeigen** aus. 

2. Folgen Sie den Anweisungen des Assistenten.
    
    Informationen über die von Aufbewahrungsbezeichnungen unterstützten Speicherorte finden Sie unter [Aufbewahrungsbezeichnungen und -speicherorte](retention.md#retention-label-policies-and-locations). 

Um eine vorhandene Richtlinie für Aufbewahrungsbezeichnungen zu bearbeiten (der Richtlinientyp ist **Veröffentlichen**), markieren Sie sie, und wählen Sie dann die Option **Bearbeiten** aus, um den Assistenten zum Bearbeiten der Aufbewahrungsrichtlinie zu starten. Mit diesem Assistenten können Sie die Richtlinienbeschreibung und alle [zutreffenden Einstellungen](#updating-retention-labels-and-their-policies) aus Schritt 2 ändern.


## <a name="when-retention-labels-become-available-to-apply"></a>Wann stehen die Aufbewahrungsbezeichnungen zur Anwendung zur Verfügung

Wenn Sie Aufbewahrungsbezeichnungen in SharePoint oder OneDrive veröffentlichen, stehen diese Bezeichnungen den Endbenutzern in der Regel innerhalb eines Tages zur Verfügung. Es kann jedoch bis zu sieben Tage dauern. 

Wenn Sie Aufbewahrungsbezeichnungen in Exchange veröffentlichen, kann es bis zu sieben Tage dauern, bis diese Aufbewahrungsbezeichnungen den Endbenutzern angezeigt werden. Zusätzlich muss das Postfach mindestens 10 MB Datenvolumen aufweisen.

Zum Beispiel:
  
![Diagramm, wann manuelle Bezeichnungen wirksam werden](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

Wenn die Bezeichnungen nach sieben Tagen nicht erscheinen, überprüfen Sie den **Status** der Bezeichnungsrichtlinie, indem Sie sie auf der Seite **Richtlinien für Bezeichnungen** im Compliance Center auswählen. Wenn der Status **Aus (Fehler)** angezeigt wird und in den Details für die Standorte eine Meldung angezeigt wird, dass die Bereitstellung der Richtlinie (für SharePoint) oder der Versuch der Neuverteilung der Richtlinie (für OneDrive) länger als erwartet dauert, versuchen Sie, den PowerShell-Befehl [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) auszuführen, um die Richtlinienverteilung erneut zu versuchen:

1. [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Führen Sie den folgenden Befehl aus:
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>So überprüfen Sie den Status der in Exchange veröffentlichten Aufbewahrungsbezeichnungen

In Exchange Online werden Aufbewahrungsbezeichnungen für Endbenutzer über einen Prozess bereitgestellt, der alle sieben Tage ausgeführt wird. Wenn Sie PowerShell verwenden, können Sie sehen, wenn der Prozess zuletzt ausgeführt wurde und damit ermitteln, wann er erneut ausgeführt wird.
  
1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Führen Sie die folgenden Befehle aus:
    
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

After content is labeled, see the following information to understand when the applied label can be removed or changed: [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).

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

##### Applying a default retention label to an Outlook folder

You can apply retention labels to Outlook folders as a default label that can be inherited by messages in that folder. Right-click the folder, select **Properties**, the **Policy** tab, and select the retention label you want to use as that folder's default retention label.

When you use a a standard retention label as your default label for an Outlook folder:
  
- All unlabeled items in the folder have this retention label applied.

- The inheritance flows to any child folders and items inherit the label from their nearest folder.

- Items that are already labeled retain their retention label, unless it was applied by a different default label.

- If you change or remove the default retention label for the folder: Existing retention labels applied to items in that folder are also changed or removed only if those labels were applied by a default label.

- If you move an item with a default retention label from one folder to another folder with a different default retention label: The item gets the new default retention label.

- If you move an item with a default retention label from one folder to another folder with no default retention label: The old default retention label is removed.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with the desktop version of Outlook on the web, you can also apply retention labels to folders. Right-click the folder, select **Assign policy**, and change **Use parent folder policy** to the retention label you want to use as that folder's default retention label.

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)

For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Microsoft 365 Groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to letting people apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set. In this scenario, documents in that location can inherit your selected default retention label. Although the same label is applied, each document will be retained and deleted separately, according to the start of the retention period setting in the label. 
  
For a document library, the default label configuration is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library.
  
For example, if you have a retention label for marketing materials, and you know a specific document library contains only that type of content, you can make the **Marketing Materials** retention label the default label for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)

#### Label behavior when you use a default label for SharePoint

For standard retention labels that you apply as a default retention label to a library, folder, or document set:

- All new, unlabeled items in the container will have this retention label applied.

- For folders, the inheritance flows to any child folders and items inherit the label from their nearest folder.

- If you selected the option to apply the default label to existing items: Items that are already labeled retain their retention label, unless it was applied by a different default label.
    
- If you change the default retention label for the container: Existing retention labels applied to items in that container are changed only if you selected the option to apply the default label to existing items and those labels were applied by a default label.

- If you remove the default retention label for the container: Items retain their labels.
    
- If you move an item with a default retention label applied from one container to another container: The item keeps its existing default retention label, even if the new location has a different default retention label. Only if you then change the default label for this new location can the moved item inherit the default label from its current location.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)

Although the UI refers to retention policies, it's your retention labels that display here and can be selected, not your retention policies.

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention label and policy name, and the retention settings except the retention period. However, you can't change the retention period when the retention period is based on when items were labeled.
- The option to mark items as a record.

### Deleting retention labels

You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.

For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.

However, it can take up to two days for content explorer to show the items that are labeled. In this scenario, the retention label might be deleted without showing you the link to content explorer.

## Locking the policy to prevent changes

If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](./event-driven-retention.md#automate-events-by-using-a-rest-api)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)