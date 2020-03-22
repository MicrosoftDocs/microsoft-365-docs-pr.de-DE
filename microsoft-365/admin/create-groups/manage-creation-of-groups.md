---
title: Verwalten von Personen, die Office 365-Gruppen erstellen können
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Erfahren Sie, wie Sie steuern können, welche Benutzer Office 365-Gruppen erstellen können.
ms.openlocfilehash: 0da8aded4b7a55975a9327cc4f29ff8679b3ccf2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894551"
---
# <a name="manage-who-can-create-office-365-groups"></a>Verwalten von Personen, die Office 365-Gruppen erstellen können

  
Weil es für Benutzer so einfach ist, Office 365-Gruppen selbst zu erstellen, werden Sie vermutlich nicht mit Bitten überflutet, diese Gruppen im Auftrag anderer Personen zu erstellen. Je nach Ihrem Unternehmen möchten Sie jedoch steuern, welche Personen die Möglichkeit zum Erstellen von Gruppen haben sollen.
  
In diesem Artikel wird erklärt, wie Sie die Möglichkeit zum Erstellen von Gruppen in allen Office 365 Diensten deaktivieren können, die Gruppen verwenden, einschließlich:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Planner
    
- PowerBI

- Roadmap
    
Sie können die Erstellung von Office 365-Gruppen auf die Mitglieder einer bestimmten Sicherheitsgruppe beschränken. Um dies zu konfigurieren, verwenden Sie Windows PowerShell. Dieser Artikel führt Sie durch die erforderlichen Schritte.
  
Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können. Globale Office 365-Administratoren können über beliebige Instrumente Gruppen erstellen, z. B. über das Microsoft 365 Admin Center, Planner, Microsoft Teams, Exchange und SharePoint Online. Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.
        
  - Exchange-Administrator: Exchange Admin Center, Azure AD
    
  - Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
    
  - Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
    
  - Verzeichnisautoren: Azure AD

  - SharePoint-Administrator: SharePoint Admin Center, Azure AD
  
  - Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD
  
  - Benutzerverwaltungsadministrator: Microsoft 365 Admin Center, Yammer, Azure AD
     
Wenn Sie Mitglied einer dieser Rollen sind, können Sie Office 365-Gruppen für Benutzer mit eingeschränktem Zugriff erstellen und anschließend den Benutzer als Besitzer der Gruppe zuweisen. Benutzer mit dieser Rolle können in Yammer verbundene Gruppen erstellen, und zwar unabhängig von PowerShell-Einstellungen, die eine Erstellung verhindern sollten.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:

- Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert
- Die Mitglieder der Sicherheitsgruppe, die Gruppen erstellen dürfen

Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:

- Personen, die Mitglieder von Office 365-Gruppen sind und keine Möglichkeit haben, andere Gruppen zu erstellen.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a>Schritt 1: Erstellen einer Sicherheitsgruppe für Benutzer, die Office 365-Gruppen erstellen müssen

Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Sicherheitsgruppe verwendet werden. Sie können jedoch andere Sicherheitsgruppen als Mitglieder dieser Gruppe schachteln. Beispiel: Die Gruppe namens "Gruppenerstellung zulassen" ist die designierte Sicherheitsgruppe, und die Gruppen namens "Microsoft Planner-Benutzer" und "Exchange Online-Benutzer" sind Mitglieder dieser Gruppe.

Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.

> [!IMPORTANT]
> Achten Sie darauf, mithilfe einer **Sicherheitsgruppe** einzuschränken, wer Gruppen erstellen kann. Wenn Sie versuchen, eine Office 365 Gruppe zu verwenden, können Mitglieder keine Gruppe aus SharePoint erstellen, da Sie nach einer Sicherheitsgruppe sucht. 
    
1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.

2. Klicken Sie auf **Gruppe hinzufügen**.

3. Wählen Sie als Gruppentyp die Option **Sicherheit** aus. Vergessen Sie nicht den Namen der Gruppe! Sie benötigen ihn später noch.
  
4. Schließen Sie die Einrichtung der Sicherheitsgruppe ab, und fügen Sie Personen oder andere Sicherheitsgruppen hinzu, die in Ihrer Organisation Gruppen erstellen können sollen.
    
Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Schritt 2: Ausführen von PowerShell-Befehlen

Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

- Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.

- Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.



Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersetzen Sie *\<SecurityGroupName\>* durch den Namen der Sicherheitsgruppe, die Sie erstellt haben. Zum Beispiel:

`$GroupName = "Group Creators"`

Speichern Sie die Datei als "GroupCreators.ps1". 

Gehen Sie im PowerShell-Fenster zu dem Speicherort, an dem Sie die Datei gespeichert haben (geben Sie "CD <FileLocation>" ein).

Führen Sie das Skript aus, indem Sie Folgendes eingeben:

`.\GroupCreators.ps1`

und [melden sich bei der entsprechenden Aufforderung mit Ihrem Administratorkonto an](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription).

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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

![So sehen Ihre Einstellungen aus, wenn Sie fertig sind.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Wenn Sie später die verwendete Sicherheitsgruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Sicherheitsgruppe erneut ausführen.

Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.
    
## <a name="step-4-verify-that-it-works"></a>Schritt 4: Überprüfen, ob alles ordnungsgemäß funktioniert

1. Melden Sie sich bei Office 365 mit dem Benutzerkonto einer Person an, der es NICHT möglich sein sollte, Gruppen zu erstellen. Also einer Person, die nicht Mitglied der von Ihnen erstellten Sicherheitsgruppe oder ein Administrator ist.
    
2. Wählen Sie die Kachel **Planner** aus. 
    
3. Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen. 
  
4. Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.

Wiederholen Sie den Vorgang mit einem Mitglied der Sicherheitsgruppe.

> [!NOTE]
> Sollte es Mitgliedern der Sicherheitsgruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](https://go.microsoft.com/fwlink/?linkid=852135) daran gehindert werden.
    
## <a name="related-articles"></a>Verwandte Artikel

[Erste Schritte mit Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
