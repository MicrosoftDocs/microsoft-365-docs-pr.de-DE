---
title: Verhindern, dass Gäste einer bestimmten Gruppe hinzugefügt werden
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Erfahren Sie, wie Sie verhindern, dass Gäste zu einer bestimmten Gruppe hinzugefügt werden
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907940"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Verhindern, dass Gäste einer bestimmten Microsoft 365-Gruppe oder einem Microsoft Teams-Team hinzugefügt werden

Wenn Sie den Gastzugriff auf die meisten Gruppen und Teams zulassen möchten, aber über einiges verfügen möchten, an dem Sie den Gastzugriff verhindern möchten, können Sie den Gastzugriff für einzelne Gruppen und Teams blockieren. (Das Blockieren des Gastzugriffs auf ein Team erfolgt durch Blockieren des Gastzugriffs auf die zugeordnete Gruppe.) Dadurch wird verhindert, dass neue Gäste hinzugefügt werden, gäste, die sich bereits in der Gruppe oder im Team befinden, werden jedoch nicht entfernt.

Wenn Sie Vertraulichkeitsbezeichnungen in Ihrer Organisation verwenden, wird empfohlen, sie zu verwenden, um den Gastzugriff pro Gruppe zu steuern. Informationen dazu finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites.](../compliance/sensitivity-labels-teams-groups-sites.md) Dies ist der empfohlene Ansatz.

## <a name="change-group-settings-using-microsoft-powershell"></a>Ändern von Gruppeneinstellungen mithilfe von Microsoft PowerShell

Sie können auch verhindern, dass neue Gäste zu einzelnen Gruppen mit PowerShell hinzu kommen. (Denken Sie daran, dass die zugeordnete SharePoint-Website des Teams [über separate Gastfreigabesteuerelemente verfügt.)](/sharepoint/change-external-sharing-site)

Sie müssen die Vorschauversion von [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2) (Modulname **AzureADPreview**) verwenden, um die Gastzugriffseinstellung auf Gruppenebene zu ändern:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

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
    
![Screenshot des PowerShell-Fensters, das anzeigt, dass der Gastgruppenzugriff auf falsch festgelegt wurde.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Zulassen oder Blockieren des Gastzugriffs basierend auf der Domäne

Sie können Gäste zulassen oder blockieren, die eine bestimmte Domäne verwenden. Nehmen wir z. B. an, dass Ihr Unternehmen (Contoso) über eine Partnerschaft mit einem anderen Unternehmen (Fabrikam) verfügt. Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, damit Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.

Weitere Informationen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Hinzufügen von Gästen zur globalen Adressliste

Standardmäßig sind Gastbenutzer in der globalen Adressliste von Exchange nicht sichtbar. Führen Sie die nachstehenden Schritte aus, um einen Gast in der globalen Adressliste anzuzeigen.

Suchen Sie die ObjectID des Gasts, indem Sie:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Führen Sie dann die folgenden Aktionen mit den entsprechenden Werten für Objekt-ID, Vorname, Nachname, Anzeigename und Telefonnummer aus.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Verwalten von Gruppenmitgliedschaften im Microsoft 365 Admin Center](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory Domain Services-Zugriffsüberprüfungen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)