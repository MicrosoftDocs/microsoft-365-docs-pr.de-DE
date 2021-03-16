---
title: Verwalten von Personen, die Microsoft 365-Gruppen erstellen können
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
description: Erfahren Sie, wie Sie steuern können, welche Benutzer Microsoft 365-Gruppen erstellen können.
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819702"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Verwalten von Personen, die Microsoft 365-Gruppen erstellen können

Standardmäßig können alle Benutzer Microsoft 365-Gruppen erstellen. Dies ist der empfohlene Ansatz, weil er es den Benutzern ermöglicht, ohne Unterstützung durch die IT mit der Zusammenarbeit zu beginnen.

Wenn Sie in Ihrem Unternehmen einschränken müssen, wer Gruppen erstellen kann, verwenden Sie dazu die Verfahren in diesem Artikel. Wenn Sie einschränken, wer eine Gruppe erstellen kann, wirkt sich dies auf alle Dienste aus, die für den Zugriff auf Gruppen angewiesen sind, einschließlich:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassisch)
- Project für das Web / Roadmap

Sie können die Erstellung von Microsoft 365-Gruppen auf die Mitglieder einer bestimmten Microsoft 365-Gruppe oder Sicherheitsgruppe beschränken. Um dies zu konfigurieren, verwenden Sie Windows PowerShell. Dieser Artikel führt Sie durch die erforderlichen Schritte.

Durch die in diesem Artikel beschriebenen Schritte wird nicht verhindert, dass Mitglieder mit bestimmten Rollen Gruppen erstellen können. Globale Office 365-Administratoren können über beliebige Instrumente Gruppen erstellen, z. B. über das Microsoft 365 Admin Center, Planner, Microsoft Teams, Exchange und SharePoint Online. Benutzer mit anderen Rollen können Gruppen über begrenzte Instrumente erstellen, die nachstehend aufgelistet sind.

- Exchange-Administrator: Exchange Admin Center, Azure AD
- Partnersupport der Ebene 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Partnersupport der Ebene 2: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Verzeichnisautoren: Azure AD
- SharePoint-Administrator: SharePoint Admin Center, Azure AD
- Microsoft Teams-Dienstadministrator: Microsoft Teams Admin Center, Azure AD
- Benutzeradministrator: Microsoft 365 Admin Center, Azure AD

Wenn Sie Mitglied einer dieser Rollen sind, können Sie Microsoft 365-Gruppen für Benutzer mit eingeschränktem Zugriff erstellen und anschließend den Benutzer als Besitzer der Gruppe zuweisen.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Um verwalten zu können, wer Gruppen erstellt, benötigen die folgenden Personen ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:

- Der Administrator, der die Einstellungen für die Gruppenerstellung konfiguriert
- Die Mitglieder der Gruppe, die Gruppen erstellen dürfen

> [!NOTE]
> Weitere Details zum Zuweisen von Azure-Lizenzen finden Sie unter [Zuweisen oder Entfernen von Lizenzen im Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

Die folgenden Personen benötigen keine ihnen zugewiesene Azure AD Premium-Lizenzen oder Azure AD Basic EDU-Lizenzen:

- Personen, die Mitglieder von Microsoft 365-Gruppen sind und keine Möglichkeit haben, andere Gruppen zu erstellen.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Schritt 1: Erstellen einer Gruppe für Benutzer, die Microsoft 365-Gruppen erstellen müssen

Zum Steuern des Personenkreises, der Gruppen erstellen kann, kann in Ihrer Organisation nur eine Gruppe verwendet werden. Sie können jedoch andere Gruppen als Mitglieder dieser Gruppe schachteln.

Administratoren mit den oben aufgeführten Rollen müssen nicht Mitglieder dieser Gruppe sein: Sie behalten ihre Fähigkeit, Gruppen zu erstellen.

1. Wechseln Sie im Admin Center zur Seite [Gruppen](https://admin.microsoft.com/adminportal/home#/groups).

2. Klicken Sie auf **Gruppe hinzufügen**.

3. Wählen Sie den gewünschten Gruppentyp aus. Vergessen Sie nicht den Namen der Gruppe! Sie benötigen ihn später noch.

4. Schließen Sie die Einrichtung der Gruppe ab, indem Sie Personen oder andere Gruppen hinzufügen, denen Sie in Ihrer Organisation das Erstellen von Gruppen erlauben möchten.

Ausführliche Anleitungen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

## <a name="step-2-run-powershell-commands"></a>Schritt 2: Ausführen von PowerShell-Befehlen

Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

- Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.

- Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.

Kopieren Sie das folgende Skript in einen Text-Editor wie Editor oder [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersetzen Sie *\<GroupName\>* durch den Namen der Gruppe, die Sie erstellt haben. Zum Beispiel:

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

Wenn Sie später die verwendete Gruppe ändern möchten, können Sie das Skript mit dem Namen der neuen Gruppe erneut ausführen.

Wenn Sie die Einschränkung für die Gruppenerstellung deaktivieren und wieder allen Benutzern das Erstellen von Gruppen gestatten möchten, legen Sie $GroupName auf "" und $AllowGroupCreation auf "True" fest, und führen Sie das Skript erneut aus.

## <a name="step-3-verify-that-it-works"></a>Schritt 3: Überprüfen der ordnungsgemäßen Funktion

Es kann dreißig Minuten oder länger dauern, bis Änderungen wirksam werden. Sie können die neuen Einstellungen auf folgende Weise prüfen:

1. Melden Sie sich bei Microsoft 365 mit dem Benutzerkonto einer Person an, der es NICHT möglich sein sollte, Gruppen zu erstellen. Also einer Person, die nicht Mitglied der von Ihnen erstellten Gruppe oder ein Administrator ist.

2. Wählen Sie die Kachel **Planner** aus.

3. Wählen Sie in Planner in der linken Navigationsleiste **Neuer Plan** aus, um einen Plan zu erstellen.

4. Jetzt sollte eine Nachricht angezeigt werden, die besagt, dass die Erstellung von Plänen und Gruppen deaktiviert ist.

Wiederholen Sie den Vorgang mit einem Mitglied der Gruppe.

> [!NOTE]
> Sollte es Mitgliedern der Gruppe nicht möglich sein, Gruppen zu erstellen, überprüfen Sie, ob Sie nicht durch ihre [OWA-Postfachrichtlinie](https://go.microsoft.com/fwlink/?linkid=852135) daran gehindert werden.

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Erste Schritte mit Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Einrichten der Self-Service-Gruppenverwaltung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
