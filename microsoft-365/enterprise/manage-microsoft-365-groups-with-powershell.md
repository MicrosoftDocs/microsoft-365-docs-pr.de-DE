---
title: Verwalten von Microsoft 365-Gruppen mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie allgemeine Verwaltungsaufgaben für Microsoft 365-Gruppen in PowerShell ausführen.
ms.openlocfilehash: c1aa551597644b7f41c3445a791ea27579464f7b
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277477"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Verwalten von Microsoft 365-Gruppen mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

In diesem Artikel werden die Schritte zum Ausführen häufiger Verwaltungsaufgaben für Gruppen in Microsoft PowerShell beschrieben. Zudem sind die PowerShell-Cmdlets für Gruppen aufgeführt. Informationen zum Verwalten von SharePoint-Websites finden Sie unter [Verwalten von SharePoint Online-Websites mithilfe von PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Link zu Ihren Microsoft 365-Gruppen-Nutzungsrichtlinien
<a name="BK_LinkToGuideLines"> </a>

Wenn Benutzer [eine Gruppe in Outlook erstellen oder bearbeiten](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), können Sie über einen Link auf die Nutzungsrichtlinien Ihrer Organisation verweisen. Angenommen, einem Gruppennamen muss ein spezielles Präfix oder Suffix hinzugefügt werden.

Verwenden Sie die Azure Active Directory (Azure AD) PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Microsoft 365-Gruppen zu richten. Lesen Sie [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?LinkID=827484), und führen Sie die Schritte unter **Erstellen von Einstellungen auf Verzeichnisebene** aus, um den Link zu den Nutzungsrichtlinien zu definieren. Nachdem Sie das AAD-Cmdlet ausgeführt haben, wird den Benutzern beim Erstellen oder Bearbeiten einer Gruppe in Outlook der Link zu Ihren Richtlinien angezeigt.

![Eine neue Gruppe mit Link zu Nutzungsrichtlinien erstellen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Auf "Gruppennutzungsrichtlinien" klicken, um die Office 365-Gruppenrichtlinien Ihrer Organisation anzuzeigen](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Zulassen, dass Benutzer als Microsoft 365-Gruppe senden
<a name="BK_LinkToGuideLines"> </a>

Wenn Sie möchten, dass Ihre Microsoft 365-Gruppen "Senden als" aktivieren, verwenden Sie die Cmdlets [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) und [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) , um dies zu konfigurieren. Nachdem Sie diese Einstellung aktiviert haben, können Benutzer von Microsoft 365 Gruppe Outlook oder Outlook im Internet verwenden, um e-Mails als Microsoft 365-Gruppe zu senden und zu beantworten. Benutzer können zur Gruppe wechseln, eine neue E-Mail erstellen und das Feld "Senden als" in die E-Mail-Adresse der Gruppe ändern.

([Sie können diesen Schritt auch im Exchange Admin Center ausführen](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).

Verwenden Sie das folgende Skript, *\<GroupAlias\>* und ersetzen Sie durch den Alias der Gruppe, die Sie aktualisieren möchten, und *\<UserAlias\>* mit dem Alias des Benutzers, dem Sie Berechtigungen erteilen möchten. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), um das Skript auszuführen.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Sobald das Cmdlet ausgeführt wurde, können Benutzer zu Outlook oder Outlook im Web wechseln und als Gruppe senden, indem sie die E-Mail-Adresse der Gruppe zum Feld **Von** hinzufügen.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Erstellen von Klassifizierungen für Microsoft 365-Gruppen in Ihrer Organisation

Sie können Sensitivitäts Bezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Microsoft 365-Gruppe erstellen. Wenn Sie Gruppen klassifizieren möchten, empfehlen wir die Verwendung von Sensitivitäts Bezeichnungen anstelle des vorherigen Gruppen Klassifizierungs Features. Informationen zur Verwendung von Sensitivitäts Bezeichnungen finden Sie unter [use Sensitivity Labels to Protect Content in Microsoft Teams, Microsoft 365 Groups und SharePoint Sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!IMPORTANT]
> Wenn Sie derzeit Klassifizierungs Bezeichnungen verwenden, stehen diese nicht mehr für Benutzer zur Verfügung, die Gruppen erstellen, sobald die Vertraulichkeits Bezeichnungen aktiviert sind.

Sie können weiterhin das vorherige Gruppen Klassifizierungs Feature verwenden. Sie können Klassifikationen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Microsoft 365-Gruppe erstellen. Beispielsweise können Sie den Benutzern gestatten, die Klassifizierungen "Standard", "Geheim" und "Streng geheim" für erstellte Gruppen festzulegen. Gruppenklassifizierungen sind nicht standardmäßig festgelegt, und Sie müssen diese erstellen, damit sie von den Benutzern festgelegt werden können. Verwenden Sie Azure Active Directory PowerShell, um Ihre Benutzer auf die Verwendungsrichtlinien Ihrer Organisation für Microsoft 365-Gruppen zu richten.

Sehen Sie sich [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) an, und führen Sie die Schritte in den **Erstellen von Einstellungen auf Verzeichnisebene** aus, um die Klassifizierung für Microsoft 365-Gruppen zu definieren.

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

Führen Sie nach dem oben genannten Azure Active Directory-Cmdlet zum Festlegen der Klassifizierung das Cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) aus, wenn Sie die Klassifizierung für eine bestimmte Gruppe festlegen möchten.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Sie können auch eine neue Gruppe mit einer Klassifizierung erstellen.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Weitere Informationen zur Verwendung von Exchange Online PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Sobald diese Einstellungen aktiviert sind, kann der Gruppenbesitzer eine Klassifizierung aus dem Dropdownmenü in Outlook im Web und Outlook auswählen und sie aus der Gruppenseite **Bearbeiten** speichern.

![Auswählen der Microsoft 365-Gruppen Klassifizierung](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Ausblenden von Microsoft 365-Gruppen aus der globalen Adressliste.
<a name="BKMK_CreateClassification"> </a>

Sie können angeben, ob eine Microsoft 365-Gruppe in der globalen Adressliste (GAL) und anderen Listen in Ihrer Organisation angezeigt wird. Wenn Sie beispielsweise eine Gruppe für juristische Abteilungen haben, die nicht in der Adressliste angezeigt werden soll, können Sie verhindern, dass die Gruppe in der GAL angezeigt wird. Führen Sie das Cmdlet Gruppe-Unified Group aus, um die Gruppe wie folgt aus der Adressliste auszublenden:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Zulassen, dass nur interne Benutzer Nachrichten an Microsoft 365-Gruppen senden
<a name="BKMK_CreateClassification"> </a>

Wenn Sie nicht möchten, dass Benutzer aus anderen Organisationen e-Mails an eine Microsoft 365-Gruppe senden, können Sie die Einstellungen für diese Gruppe ändern. So können nur interne Benutzer E-Mail-Nachrichten an Ihre Gruppe senden. Wenn ein externer Benutzer versucht, eine Nachricht an diese Gruppe zu senden, wird er abgelehnt.

Führen Sie das Cmdlet "Set-UnifiedGroup" wie folgt aus, um diese Einstellung zu aktualisieren:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Hinzufügen von e-Mail-Infos zu Microsoft 365-Gruppen
<a name="BKMK_CreateClassification"> </a>

Wenn ein Absender versucht, eine e-Mail an eine Microsoft 365-Gruppe zu senden, kann ihm ein QuickInfo-angezeigt werden.

Führen Sie das Cmdlet "Set-UnifiedGroup" aus, um eine E-Mail-Info zur Gruppe hinzuzufügen:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Neben einer E-Mail-Info können Sie auch "MailTipTranslations" festlegen, wodurch zusätzliche Sprachen für die E-Mail-Info festgelegt werden. Angenommen Sie, Sie möchten die spanische Übersetzung verwenden, dann führen Sie den folgenden Befehl aus:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Ändern des Anzeigenamens der Microsoft 365-Gruppe

Der Anzeigename gibt den Namen der Microsoft 365-Gruppe an. Sie können diesen Namen in Ihrem Exchange Admin Center oder Microsoft 365 Admin Center sehen. Sie können den Anzeigenamen der Gruppe bearbeiten oder einer vorhandenen Microsoft 365-Gruppe einen Anzeigenamen zuweisen, indem Sie den Befehl "Gruppe-Unifiedgroup" ausführen:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Ändern der Standardeinstellung von Microsoft 365-Gruppen für Outlook in "öffentlich" oder "Privat"
<a name="BKMK_CreateClassification"> </a>

Microsoft 365-Gruppen in Outlook werden standardmäßig als privat erstellt. Wenn Ihre Organisation Microsoft 365-Gruppen standardmäßig als Public (oder Back to private) erstellen möchte, verwenden Sie diese PowerShell-Cmdlet-Syntax:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

So legen Sie die Einstellung auf "Privat" fest:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

So überprüfen Sie die Einstellung:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Weitere Informationen hierzu finden Sie unter [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) und [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Groups-Cmdlets

Die folgenden Cmdlets können mit Microsoft 365-Gruppen verwendet werden.

|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Verwenden Sie dieses Cmdlet, um nach vorhandenen Microsoft 365-Gruppen zu suchen und um die Eigenschaften des Group-Objekts anzuzeigen.  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Aktualisieren der Eigenschaften einer bestimmten Microsoft 365-Gruppe  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Erstellen Sie eine neue Microsoft 365-Gruppe. Dieses Cmdlet stellt einen minimalen Satz von Parametern bereit. Um Werte für erweiterte Eigenschaften festzulegen, verwenden Sie nach dem Erstellen der neuen Gruppe "-Unifiedgroup".  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Löschen einer vorhandenen Microsoft 365-Gruppe  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Abrufen von Mitgliedschafts-und Besitzerinformationen für eine Microsoft 365-Gruppe  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Hinzufügen von Hunderten oder Tausenden von Benutzern oder neuen Besitzern zu einer vorhandenen Microsoft 365-Gruppe  <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Entfernen von Besitzern und Mitgliedern aus einer vorhandenen Microsoft 365-Gruppe  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Wird verwendet, um Informationen zu dem Benutzerfoto abzurufen, das mit einem Konto verbunden ist. Benutzerfotos werden in Active Directory gespeichert.  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Wird verwendet, um ein Benutzerfoto mit einem Konto zu verknüpfen. Benutzerfotos werden in Active Directory gespeichert.  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Entfernen des Fotos für eine Microsoft 365-Gruppe  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Verwalten von Personen, die Microsoft 365-Gruppen erstellen können](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Verwalten des Gastzugriffs auf Microsoft 365-Gruppen](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Ändern der statischen Gruppenmitgliedschaft in „Dynamisch“](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
