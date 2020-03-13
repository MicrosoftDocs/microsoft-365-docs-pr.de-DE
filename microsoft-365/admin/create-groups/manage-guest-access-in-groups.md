---
title: Verwalten des Gastzugriffs in Office 365-Gruppen
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Hier erfahren Sie, wie Sie einer Office 365-Gruppe Gäste hinzufügen, Gastbenutzer anzeigen und PowerShell zum Steuern des Gastzugriffs verwenden.
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610612"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Verwalten des Gastzugriffs in Office 365-Gruppen

Standardmäßig ist der Gastzugriff für Office 365-Gruppen für Ihre Organisation aktiviert. Administratoren können steuern, ob sie den Gastzugriff für die ganze Organisation oder für einzelne Gruppen zulassen möchten.

Wenn diese Option aktiviert ist, können Gruppenmitglieder über Outlook im Web Gastbenutzer zu einer Office 365-Gruppe einladen. Einladungen werden zur Genehmigung an den Gruppenbesitzer gesendet.

> [!Note]
> Yammer Enterprise-Netzwerke, die sich im nativen Modus oder im [EU-Gebiet](https://go.microsoft.com/fwlink/?linkid=2107357) befinden, unterstützen keine Netzwerkgäste.
> Mit Office 365 verbundene Yammer-Gruppen unterstützen derzeit keinen Gastzugriff. Sie können aber in Ihrem Yammer-Netzwerk nicht verbundene, externe Gruppen erstellen. Entsprechende Anleitungen finden Sie unter [Erstellen und Verwalten von externen Gruppen in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx).

### <a name="edit-guest-information"></a>Bearbeiten von Gastinformationen

Nach der Genehmigung wird der Gastbenutzer dem Verzeichnis und der Gruppe hinzugefügt.

Der Gastzugriff in Gruppen wird häufig als Teil eines breiter gefächerten Szenarios verwendet, das SharePoint oder Teams umfasst. Diese Dienste besitzen ihre eigenen Einstellungen für die Gastfreigabe. Umfassende Anweisungen zum Einrichten der gemeinsamen Nutzung über Gruppen, SharePoint und Teams hinweg finden Sie unter:

- [Zusammenarbeit mit Gästen in einer Website](../../solutions/collaborate-in-site.md)
- [Zusammenarbeit mit Gästen in einem Team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Verwalten des Gastzugriffs von Gruppen

Wenn Sie den Gastzugriff in Gruppen aktivieren oder deaktivieren möchten, können Sie dies im Microsoft 365 Admin Center tun.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Dienste und Add-Ins</a>.

2. Wählen Sie **Office 365-Gruppen** aus.
  
3. Wählen Sie auf der Seite **Office 365-Gruppen** aus, ob Sie Personen außerhalb Ihrer Organisation Zugriff auf Gruppenressourcen gewähren oder zulassen möchten, dass Gruppenbesitzer Personen außerhalb Ihrer Organisation zu Gruppen hinzufügen.

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>Hinzufügen von Gästen zu einer Office 365-Gruppe über das Admin Center

Wenn der Gast bereits in Ihrem Verzeichnis vorhanden ist, können Sie ihn über das Microsoft 365 Admin Center zu Ihren Gruppen hinzufügen.
  
1. Wechseln Sie im Admin Center zur Seite **Gruppen** > **Gruppen**.
  
2. Wählen Sie die Gruppe aus, der Sie den Gast hinzufügen möchten, und wählen Sie auf der Registerkarte **Mitglieder** **Alle anzeigen und Mitglieder verwalten** aus. 
  
4. Wählen Sie **Mitglieder hinzufügen** und dann den Namen der Person, die Sie hinzufügen möchten.
    
5. Klicken Sie auf **Speichern**.

Wenn Sie einen Gast direkt zum Verzeichnis hinzufügen möchten, können Sie [Benutzer der Azure Active Directory-B2B-Zusammenarbeit im Azure-Portal hinzufügen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Wenn Sie die Informationen eines Gastes bearbeiten möchten, können Sie die [Profilinformationen eines Benutzers mithilfe von Azure Active Directory hinzufügen oder aktualisieren](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Blockieren von Gastbenutzern aus einer bestimmten Gruppe

Wenn Sie den Gastzugriff auf die meisten, aber nicht alle Gruppen zulassen möchten, können Sie den Gastzugriff für einzelne Gruppen mithilfe von Microsoft PowerShell sperren.

Sie müssen die Vorschau-Version von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) verwenden (Modulname **AzureADPreview**), um die Einstellung für den Gastzugriff auf Gruppenebene zu ändern:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

- Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.

- Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.

> [!NOTE]
> Sie müssen über globale Administratorrechte verfügen, um diese Befehle ausführen zu können. 

Führen Sie das folgende Skript aus und ändern Sie */<GroupName/>* auf den Namen der Gruppe, für den Sie Gastzugriff sperren möchten.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Zum Überprüfen Ihrer Einstellungen führen Sie diesen Befehl aus:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Die Überprüfung sieht wie folgt aus:
    
![Screenshot des PowerShell-Fensters, das anzeigt, dass der Gastgruppenzugriff auf falsch festgelegt wurde.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Zulassen oder Blockieren des Gastzugriffs basierend auf der Domäne

Sie können Gastbenutzer zulassen oder blockieren, die eine bestimmte Domäne verwenden. Nehmen wir z. B. an, dass Ihr Unternehmen (Contoso) über eine Partnerschaft mit einem anderen Unternehmen (Fabrikam) verfügt. Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, damit Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.

Weitere Informationen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Hinzufügen von Gästen zur globalen Adressliste

Standardmäßig sind Gastbenutzer in der globalen Adressliste von Exchange nicht sichtbar. Führen Sie die nachstehenden Schritte aus, um einen Gast in der globalen Adressliste anzuzeigen.

Suchen Sie die ObjectID des Gastbenutzers:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Führen Sie dann die folgenden Aktionen mit den entsprechenden Werten für Objekt-ID, Vorname, Nachname, Anzeigename und Telefonnummer aus.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Gruppenmitgliedschaften im Microsoft 365 Admin Center](add-or-remove-members-from-groups.md)
  
[Azure Active Directory Domain Services-Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
