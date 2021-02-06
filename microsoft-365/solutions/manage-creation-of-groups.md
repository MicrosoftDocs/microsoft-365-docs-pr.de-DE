---
title: Verwalten, wer Microsoft 365-Gruppen erstellen kann
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Erfahren Sie, wie Sie steuern, welche Benutzer Microsoft 365-Gruppen erstellen können.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122384"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Verwalten, wer Microsoft 365-Gruppen erstellen kann

Standardmäßig können alle Benutzer Microsoft 365-Gruppen erstellen. Dies ist der empfohlene Ansatz, da benutzer mit der Zusammenarbeit beginnen können, ohne unterstützung von der IT zu benötigen.

Wenn Für Ihr Unternehmen die Einschränkung erforderlich ist, wer Gruppen erstellen kann, können Sie dazu die Verfahren in diesem Artikel verwenden. Wenn Sie einschränken, wer eine Gruppe erstellen kann, wirkt sich dies auf alle Dienste aus, die für den Zugriff auf Gruppen angewiesen sind, einschließlich:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassisch)
- Projekt für das Web/Roadmap

Sie können die Erstellung von Microsoft 365-Gruppen auf die Mitglieder einer bestimmten Microsoft 365-Gruppe oder Sicherheitsgruppe beschränken. Um dies zu konfigurieren, verwenden Sie Windows PowerShell. Dieser Artikel führt Sie durch die erforderlichen Schritte.

Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können. Globale Office 365-Administratoren können über beliebige Instrumente Gruppen erstellen, z. B. über das Microsoft 365 Admin Center, Planner, Microsoft Teams, Exchange und SharePoint Online. Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.

- Exchange-Administrator: Exchange Admin Center, Azure AD
- Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Verzeichnisautoren: Azure AD
- SharePoint-Administrator: SharePoint Admin Center, Azure AD
- Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD
- Benutzerverwaltungsadministrator: Microsoft 365 Admin Center, Yammer, Azure AD

Wenn Sie Mitglied einer dieser Rollen sind, können Sie Microsoft 365-Gruppen für eingeschränkte Benutzer erstellen und den Benutzer dann als Besitzer der Gruppe zuweisen.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Um zu verwalten, wer Gruppen erstellt, benötigen die folgenden Personen Azure AD Premium- oder Azure AD Basic EDU-Lizenzen, die ihnen zugewiesen sind:

- Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert
- Die Mitglieder der Gruppe, die Gruppen erstellen dürfen

> [!NOTE]
> Weitere [Informationen zum Zuweisen von Azure-Lizenzen](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) finden Sie unter "Zuweisen oder Entfernen von Lizenzen im Azure Active Directory-Portal".

Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:

- Personen, die Mitglieder von Microsoft 365-Gruppen sind und nicht in der Lage sind, andere Gruppen zu erstellen.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Schritt 1: Erstellen einer Gruppe für Benutzer, die Microsoft 365-Gruppen erstellen müssen

Es kann nur eine Gruppe in Ihrer Organisation verwendet werden, um zu steuern, wer Gruppen erstellen kann. Sie können jedoch andere Gruppen als Mitglieder dieser Gruppe schachteln.

Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.

1. Wechseln Sie im Admin Center zur Seite ["Gruppen".](https://admin.microsoft.com/adminportal/home#/groups)

2. Klicken Sie auf **Gruppe hinzufügen**.

3. Wählen Sie den Gruppentyp aus, den Sie verwenden möchten. Vergessen Sie nicht den Namen der Gruppe! Sie benötigen ihn später noch.

4. Schließen Sie die Einrichtung der Gruppe ab, und fügen Sie Personen oder andere Gruppen hinzu, die In der Lage sein sollen, Gruppen in Ihrer Organisation zu erstellen.

Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

## <a name="step-2-run-powershell-commands"></a>Schritt 2: Ausführen von PowerShell-Befehlen

Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

- Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.

- Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.

Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersetzen *\<GroupName\>* Sie dies durch den Namen der Gruppe, die Sie erstellt haben. Zum Beispiel:

`$GroupName = "Group Creators"`

Speichern Sie die Datei als "GroupCreators.ps1".

Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).

Führen Sie das Skript aus, indem Sie Folgendes eingeben:

`.\GroupCreators.ps1`

und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription).

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

Die letzte Zeile des Skripts enthält die aktualisierten Einstellungen:

![So sehen Ihre Einstellungen aus, wenn Sie fertig sind.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Wenn Sie zukünftig ändern möchten, welche Gruppe verwendet wird, können Sie das Skript mit dem Namen der neuen Gruppe erneut ausführen.

Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.

## <a name="step-3-verify-that-it-works"></a>Schritt 3: Überprüfen der ordnungsgemäßen Funktion

Es kann 30 Minuten oder mehr dauern, bis Änderungen wirksam werden. Sie können die neuen Einstellungen wie folgt überprüfen:

1. Melden Sie sich bei Microsoft 365 mit einem Benutzerkonto einer Person an, die nicht in der Lage sein sollte, Gruppen zu erstellen. Das heißt, sie sind kein Mitglied der gruppe, die Sie erstellt haben, oder ein Administrator.

2. Wählen Sie die Kachel **Planner** aus.

3. Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.

4. Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.

Versuchen Sie es erneut mit einem Mitglied der Gruppe.

> [!NOTE]
> Wenn Mitglieder der Gruppe keine Gruppen erstellen können, überprüfen Sie, ob sie nicht über ihre [OWA-Postfachrichtlinie blockiert werden.](https://go.microsoft.com/fwlink/?linkid=852135)

## <a name="related-topics"></a>Verwandte Themen

[Steuerungsplanung für die Zusammenarbeit – Schritt für Schritt](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Steuerungsplans für die Zusammenarbeit](collaboration-governance-first.md)

[Erste Schritte mit Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
