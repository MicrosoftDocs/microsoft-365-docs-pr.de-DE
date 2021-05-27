---
title: Ändern von Benutzernamen und -E-Mail-Adressen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'Erfahren Sie, wie ein globaler Microsoft 365-Administrator die E-Mail-Adresse und den Anzeigenamen eines Benutzers ändern kann, wenn sich sein Name ändert. '
ms.openlocfilehash: 4f65bade32b2998f395c3b4eab7a1d2a2e5f3f33
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683115"
---
# <a name="change-a-user-name-and-email-address"></a>Ändern von Benutzernamen und -E-Mail-Adressen

Es kann vorkommen, dass Sie die E-Mail-Adresse und den Anzeigenamen einer Person ändern müssen, wie z. B. wenn diese heiratet und ihren Nachnamen ändert.

## <a name="watch-change-a-users-name-or-email-address"></a>Ansehen: Namen oder E-Mail-Adresse eines Benutzers ändern

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

Sie müssen [globaler Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können. 

## <a name="change-a-users-email-address"></a>Ändern der E-Mail-Adresse eines Benutzers

::: moniker range="o365-worldwide"
 
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

::: moniker-end

1. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **Benutzernamen verwalten** aus.
    
1. Geben Sie im ersten Feld den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen. 

1. Wählen Sie **Änderungen speichern** aus.

> [!IMPORTANT]
> Wenn Sie eine Fehlermeldung erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

## <a name="set-the-primary-email-address"></a>Die primäre E-Mail-Adresse festlegen.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.  

::: moniker-end
    
2. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **E-Mail-Alias-Adressen verwalten** aus.

3. Wählen Sie **Als primäre E-Mail-Adresse festlegen** für die E-Mail-Adresse aus, die Sie als primäre E-Mail-Adresse für diese Person festlegen möchten. 
    
   > [!IMPORTANT]
   > Die Option zum Festlegen der primären E-Mail-Adresse wird nicht angezeigt, wenn Sie Microsoft 365 bei GoDaddy oder einem anderen Partnerdienst mit einer Verwaltungskonsole erworben haben. Melden Sie sich stattdessen bei der Verwaltungskonsole von GoDaddy bzw. des Partners an, um den primären Alias festzulegen. 
   >  
   > Diese Option wird außerdem nur angezeigt, wenn Sie ein globaler Administrator sind. Wenn Sie die Option nicht sehen, verfügen Sie nicht über die Berechtigung, den Namen und die primäre E-Mail-Adresse eines Benutzers zu ändern.
  
4. Es wird eine große gelbe Warnmeldung angezeigt, dass Sie dabei sind, die Anmeldeinformationen der Person zu ändern. Wählen Sie **Speichern** und dann **Schließen** aus.
    
5. Übermitteln Sie der Person die folgenden Informationen:
 
   - Diese Änderung kann eine Weile dauern.
  
   - Der neue Benutzername. Dieser wird für die Anmeldung bei Microsoft 365 benötigt.
    
   - Wenn die Person Skype for Business Online verwendet, muss sie von ihr organisierte Skype for Business Online-Besprechungen erneut planen und ihre externen Kontakte auffordern, ihre Kontaktinformationen zu aktualisieren.

   - Wenn die Person OneDrive verwendet, wurde die URL zu diesem Speicherort geändert. Wenn sich OneNote-Notizbücher auf ihrem OneDrive befinden, müssen sie möglicherweise geschlossen und in OneNote erneut geöffnet werden. Wenn über OneDrive Dateien geteilt wurden, funktionieren die Links zu den Dateien möglicherweise nicht, und die Person kann diese wieder freigeben.    
  
   - Wenn auch das Kennwort geändert wurde, wird die Person aufgefordert, das neue Kennwort auf ihrem mobilen Gerät einzugeben. Andernfalls wird es nicht synchronisiert.
  
## <a name="change-a-users-display-name"></a>Ändern des Anzeigenamens eines Benutzers

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

::: moniker-end

2. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **Kontaktinformationen verwalten** aus.

3. Geben Sie im Feld **Anzeigename** einen neuen Namen für die Person ein, und wählen Sie dann **Speichern** aus.

   Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen, und versuchen Sie es noch einmal**“ erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

Es kann bis zu 24 Stunden dauern, bis diese Änderung in allen Diensten wirksam wird. Nachdem die Änderung wirksam geworden ist, muss sich die Person mit dem aktualisierten Benutzernamen bei Outlook, Skype for Business und SharePoint anmelden.
 
## <a name="resolve-error-messages"></a>Auflösen von Fehlermeldungen

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>„Es wurde kein Parameter gefunden, der dem Parameternamen ‚E-Mail-Adressen‘ entspricht“

Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parameternamen 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist. Der Setupvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut. Sollte das Problem weiterhin bestehen, rufen Sie den [Support](../../business-video/get-help-support.md) an und bitten Sie um eine vollständige Synchronisierung.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>„Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen und versuchen Sie es noch einmal“

Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen und versuchen Sie es noch einmal**“ erhalten, bedeutet dies, dass Sie kein globaler Administrator sind und nicht über die Berechtigung zum Ändern des Benutzernamens verfügen. Suchen Sie den globalen Administrator in Ihrem Unternehmen und bitten Sie ihn, die Änderung vorzunehmen.


## <a name="what-to-do-with-old-email-addresses"></a>Was mit alten E-Mail-Adressen zu tun ist

Die vorherige primäre E-Mail-Adresse einer Person wird als zusätzliche E-Mail-Adresse beibehalten. **Wir empfehlen dringend, dass Sie die alte E-Mail-Adresse nicht entfernen.**
  
Einige Personen senden möglicherweise weiterhin E-Mails an die alte E-Mail-Adresse. Das Löschen dieser Adresse kann zu NDR-Fehlern führen. Microsoft leitet die E-Mails automatisch an die neue Adresse weiter. Außerdem: Verwenden Sie keine alten SMTP-E-Mail-Adressen, und wenden Sie sie nicht auf neue Konten an. Dies kann ebenfalls zu NDR-Fehlern oder zur Zustellung an ein nicht vorgesehenes Postfach führen.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>Wie ist vorzugehen, wenn das Offline-Adressbuch des Benutzers nicht mit der globalen Adressliste synchronisiert wird?

Wenn eine Person Exchange Online verwendet oder ihr Konto mit der lokalen Exchange-Umgebung Ihrer Organisation verknüpft ist, wird bei Ihrem Versuch, einen Benutzernamen und die zugehörige E-Mail-Adresse zu ändern, möglicherweise die folgende Fehlermeldung angezeigt: „Dieser Benutzer ist mit Ihrem lokalen Active Directory synchronisiert. Bestimmte Details können nur in Ihrem lokalen Active Directory bearbeitet werden.“
  
Der Grund dafür ist die Microsoft Online Email Routing Address (MOERA). Die MOERA wird aus dem Attribut _userPrincipalName_ der Person in Active Directory erstellt und dem Cloudkonto während der Erstsynchronisierung automatisch zugewiesen. Sobald eine MOERA erstellt wurde, kann sie in Microsoft 365 nicht geändert oder entfernt werden. Sie können den Benutzernamen zwar anschließend in Active Directory ändern. Weil aber die MOERA unverändert bleibt, können Probleme auftreten, wenn Sie den gerade geänderten Namen in der globalen Adressliste anzeigen. 
  
Um dies zu beheben, melden Sie sich beim [Azure Active Directory-Modul für PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) mit Ihren Administratoranmeldeinformationen für Microsoft 365 an. Verwenden Sie die folgende Syntax: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Damit wird das Attribut **userPrincipalName** einer Person geändert, allerdings hat dies keine Auswirkungen auf deren Microsoft Online E-Mail Routing-Adresse (MOERA). Als bewährte Methode sollten Sie jedoch dafür sorgen, dass der Anmelde-UPN dieser Person mit ihrer primären SMTP-Adresse übereinstimmt. 
  
Wenn Sie erfahren möchten, wie ein Benutzername einer Person in Active Directory, in Windows Server 2003 und früher geändert wird, lesen Sie [Umbenennen eines Benutzerkontos](/previous-versions/windows/it-pro/windows-server-2003/cc772952(v=ws.10)).
  
## <a name="related-content"></a>Verwandte Inhalte

[Administratoren: Zurücksetzen eines Kennworts für ein oder mehrere Benutzer](reset-passwords.md) (Artikel)
[Hinzufügen einer weiteren E-Mail-Adresse für einen Benutzer](../email/add-another-email-alias-for-a-user.md) (Artikel)
[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) (Artikel)