---
title: Verwalten von Microsoft 365-Gruppen mit PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: In diesem Artikel erfahren Sie, wie Sie allgemeine Verwaltungsaufgaben für Microsoft 365 in PowerShell ausführen.
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911050"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Verwalten von Microsoft 365-Gruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

In diesem Artikel werden die Schritte zum Ausführen häufiger Verwaltungsaufgaben für Gruppen in Microsoft PowerShell beschrieben. Zudem sind die PowerShell-Cmdlets für Gruppen aufgeführt. Informationen zum Verwalten von SharePoint-Websites finden Sie unter [Verwalten von SharePoint Online-Websites mithilfe von PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Link zu ihren Microsoft 365 Gruppennutzungsrichtlinien
<a name="BK_LinkToGuideLines"> </a>

Wenn Benutzer [eine Gruppe in Outlook erstellen oder bearbeiten](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), können Sie über einen Link auf die Nutzungsrichtlinien Ihrer Organisation verweisen. Angenommen, einem Gruppennamen muss ein spezielles Präfix oder Suffix hinzugefügt werden.

Verwenden Sie Azure Active Directory (Azure AD) PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Microsoft 365 verweisen. Lesen Sie [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](/azure/active-directory/enterprise-users/groups-settings-cmdlets), und führen Sie die Schritte unter **Erstellen von Einstellungen auf Verzeichnisebene** aus, um den Link zu den Nutzungsrichtlinien zu definieren. Nachdem Sie das AAD-Cmdlet ausgeführt haben, wird den Benutzern beim Erstellen oder Bearbeiten einer Gruppe in Outlook der Link zu Ihren Richtlinien angezeigt.

![Eine neue Gruppe mit Link zu Nutzungsrichtlinien erstellen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Auf "Gruppennutzungsrichtlinien" klicken, um die Office 365-Gruppenrichtlinien Ihrer Organisation anzuzeigen](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Zulassen, dass Benutzer als Microsoft 365 senden
<a name="BK_LinkToGuideLines"> </a>

Wenn Sie ihre Gruppen Microsoft 365 "Senden als" aktivieren möchten, verwenden Sie die [Cmdlets Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) und [Get-RecipientPermission,](/powershell/module/exchange/get-recipientpermission) um dies zu konfigurieren. Nachdem Sie diese Einstellung aktiviert haben, Microsoft 365 Gruppenbenutzer Outlook oder Outlook im Web zum Senden und Beantworten von E-Mails als Microsoft 365 verwenden. Benutzer können zur Gruppe wechseln, eine neue E-Mail erstellen und das Feld "Senden als" in die E-Mail-Adresse der Gruppe ändern.

([Sie können diesen Schritt auch im Exchange Admin Center ausführen](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).

Verwenden Sie das folgende Skript, indem Sie durch den Alias der Gruppe ersetzen, die Sie aktualisieren möchten, und durch den Alias des Benutzers, dem Sie *\<GroupAlias\>* *\<UserAlias\>* Berechtigungen erteilen möchten. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell), um das Skript auszuführen.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Sobald das Cmdlet ausgeführt wurde, können Benutzer zu Outlook oder Outlook im Web wechseln und als Gruppe senden, indem sie die E-Mail-Adresse der Gruppe zum Feld **Von** hinzufügen.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Erstellen von Klassifizierungen Microsoft 365 Gruppen in Ihrer Organisation

Sie können Vertraulichkeitsbezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365 erstellen. Wenn Sie Gruppen klassifizieren möchten, empfehlen wir die Verwendung von Vertraulichkeitsbezeichnungen anstelle des vorherigen Gruppenklassifizierungsfeatures. Informationen zum Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams,](../compliance/sensitivity-labels-teams-groups-sites.md)Microsoft 365 gruppen und SharePoint Websites .

> [!IMPORTANT]
> Wenn Sie derzeit Klassifizierungsbezeichnungen verwenden, stehen sie Benutzern, die Gruppen erstellen, nach aktivierung von Vertraulichkeitsbezeichnungen nicht mehr zur Verfügung.

Sie können weiterhin die vorherige Gruppenklassifizierungsfunktion verwenden. Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365 erstellen. Beispielsweise können Sie den Benutzern gestatten, die Klassifizierungen "Standard", "Geheim" und "Streng geheim" für erstellte Gruppen festzulegen. Gruppenklassifizierungen sind nicht standardmäßig festgelegt, und Sie müssen diese erstellen, damit sie von den Benutzern festgelegt werden können. Verwenden Azure Active Directory PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Gruppen Microsoft 365 verweisen.

Lesen Sie [Azure Active Directory Cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) zum Konfigurieren von Gruppeneinstellungen, und führen Sie die Schritte unter **Erstellen** von Einstellungen auf Verzeichnisebene aus, um die Klassifizierung für gruppen Microsoft 365 definieren.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Mit dem settings-Attribut *ClassificationDescriptions* können Sie jeder Klassifizierung eine Beschreibung zuordnen.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

wobei die Klassifizierung mit den Zeichenfolgen in der ClassificationList übereinstimmt.

Beispiel:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Führen Sie nach dem oben genannten Azure Active Directory-Cmdlet zum Festlegen der Klassifizierung das Cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) aus, wenn Sie die Klassifizierung für eine bestimmte Gruppe festlegen möchten.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Sie können auch eine neue Gruppe mit einer Klassifizierung erstellen.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Weitere Informationen zur Verwendung von Exchange Online PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Sobald diese Einstellungen aktiviert sind, kann der Gruppenbesitzer eine Klassifizierung aus dem Dropdownmenü in Outlook im Web und Outlook auswählen und sie aus der Gruppenseite **Bearbeiten** speichern.

![Auswählen Microsoft 365 Gruppenklassifikation](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ausblenden Microsoft 365 Gruppen aus der globalen Adressliste.
<a name="BKMK_CreateClassification"> </a>

Sie können angeben, ob Microsoft 365 gruppe in der globalen Adressliste (GAL) und anderen Listen in Ihrer Organisation angezeigt wird. Wenn Sie beispielsweise über eine Rechtsabteilungsgruppe verfügen, die nicht in der Adressliste angezeigt werden soll, können Sie verhindern, dass diese Gruppe in der GAL angezeigt wird. Führen Sie Set-Unified Gruppen-Cmdlet aus, um die Gruppe in der Adressliste wie dies auszublenden:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Nur interne Benutzer dürfen Nachrichten an gruppeninterne Microsoft 365 senden
<a name="BKMK_CreateClassification"> </a>

Wenn Sie nicht möchten, dass Benutzer aus anderen Organisationen E-Mails an eine Microsoft 365 senden, können Sie die Einstellungen für diese Gruppe ändern. So können nur interne Benutzer E-Mail-Nachrichten an Ihre Gruppe senden. Wenn ein externer Benutzer versucht, eine Nachricht an diese Gruppe zu senden, wird sie abgelehnt.

Führen Sie das Cmdlet "Set-UnifiedGroup" wie folgt aus, um diese Einstellung zu aktualisieren:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Hinzufügen von E-Mail-Microsoft 365 gruppen
<a name="BKMK_CreateClassification"> </a>

Wenn ein Absender versucht, eine E-Mail an eine Microsoft 365 zu senden, kann eine E-Mail-Tip angezeigt werden.

Führen Sie das Cmdlet "Set-UnifiedGroup" aus, um eine E-Mail-Info zur Gruppe hinzuzufügen:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Neben einer E-Mail-Info können Sie auch "MailTipTranslations" festlegen, wodurch zusätzliche Sprachen für die E-Mail-Info festgelegt werden. Angenommen Sie, Sie möchten die spanische Übersetzung verwenden, dann führen Sie den folgenden Befehl aus:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Ändern des Anzeigenamens der Microsoft 365 Gruppe

Der Anzeigename gibt den Namen der gruppe Microsoft 365 an. Dieser Name wird in Ihrem Exchange Admin Center oder im Microsoft 365 angezeigt. Sie können den Anzeigenamen der Gruppe bearbeiten oder einer vorhandenen Microsoft 365 gruppe einen Anzeigenamen zuweisen, indem Sie den befehl Set-UnifiedGroup ausführen:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Ändern der Standardeinstellung Microsoft 365 Gruppen für Outlook in Öffentlich oder Privat
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 Gruppen in Outlook werden standardmäßig als Privat erstellt. Wenn Ihre Organisation Microsoft 365 Gruppen standardmäßig als öffentlich (oder zurück zu Privat) erstellen möchten, verwenden Sie diese PowerShell-Cmdletsyntax:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

So legen Sie die Einstellung auf "Privat" fest:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

So überprüfen Sie die Einstellung:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Weitere Informationen hierzu finden Sie unter [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) und [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Gruppen-Cmdlets

Die folgenden Cmdlets können mit gruppen Microsoft 365 werden.

|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Verwenden Sie dieses Cmdlet, um vorhandene Gruppen Microsoft 365 und zum Anzeigen von Eigenschaften des Gruppenobjekts zu suchen.  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Aktualisieren der Eigenschaften einer bestimmten Microsoft 365 Gruppe  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Erstellen Sie eine neue Microsoft 365 Gruppe. Dieses Cmdlet bietet einen minimalen Satz von Parametern. Verwenden Sie zum Festlegen von Werten für erweiterte Eigenschaften Set-UnifiedGroup nach dem Erstellen der neuen Gruppe.  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Löschen einer vorhandenen Microsoft 365 Gruppe  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Abrufen von Mitgliedschafts- und Besitzerinformationen für eine Microsoft 365 Gruppe  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Hinzufügen von Mitgliedern, Besitzern und Abonnenten zu einer vorhandenen Microsoft 365 Gruppe <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Entfernen von Besitzern und Mitgliedern aus einer vorhandenen Microsoft 365 Gruppe  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Wird verwendet, um Informationen zu dem Benutzerfoto abzurufen, das mit einem Konto verbunden ist. Benutzerfotos werden in Active Directory gespeichert.  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Wird verwendet, um ein Benutzerfoto mit einem Konto zu verknüpfen. Benutzerfotos werden in Active Directory gespeichert.  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Entfernen des Fotos für eine Microsoft 365 Gruppe  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen](/office365/admin/manage/upgrade-distribution-lists)

[Verwalten von Personen, die Microsoft 365-Gruppen erstellen können](/office365/admin/create-groups/manage-creation-of-groups)

[Verwalten des Gastzugriffs auf Microsoft 365 Gruppen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Ändern der statischen Gruppenmitgliedschaft in „Dynamisch“](/azure/active-directory/users-groups-roles/groups-change-type)