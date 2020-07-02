---
title: Ändern von Benutzernamen und -E-Mail-Adressen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: 'Erfahren Sie, wie ein globaler Administrator die E-Mail-Adresse und den Anzeigenamen eines Benutzers ändern kann. '
ms.openlocfilehash: 0c94114a50ce369ffb809e8f41060994f635a36c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936527"
---
# <a name="change-a-user-name-and-email-address"></a>Ändern von Benutzernamen und -E-Mail-Adressen

Es kann vorkommen, dass Sie die E-Mail-Adresse und den Anzeigenamen einer Person ändern müssen, wie z. B. wenn diese heiratet und ihren Nachnamen ändert.

Sehen Sie sich ein kurzes Video zum Ändern der E-Mail-Adresse eines Benutzers an. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.

## <a name="change-a-users-email-address"></a>Ändern der E-Mail-Adresse eines Benutzers

Sie müssen [globaler Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können. 

::: moniker range="o365-worldwide"
 
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **Benutzernamen verwalten** aus.
    
3. Geben Sie im ersten Feld den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, wählen Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste aus. 

4. Wählen Sie **Änderungen speichern** aus.

   
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Benutzername/E-Mail-** **Bearbeiten** aus.

3. Geben Sie im ersten Feld den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.

4. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Benutzername/E-Mail-** **Bearbeiten** aus.

3. Geben Sie im ersten Feld den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Office 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen.

4. Klicken Sie auf **Speichern**.

::: moniker-end

**WICHTIG**: Wenn Sie eine Fehlermeldung erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

## <a name="set-the-primary-email-address"></a>Die primäre E-Mail-Adresse festlegen.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **E-Mail-Alias-Adressen verwalten** aus.

3. Wählen Sie **Als primäre E-Mail-Adresse festlegen** für die E-Mail-Adresse aus, die Sie als primäre E-Mail-Adresse für diese Person festlegen möchten. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Diese Option wird außerdem nur angezeigt, wenn Sie ein globaler Administrator sind. Wenn Sie die Option nicht sehen, verfügen Sie nicht über die Berechtigung, den Namen und die primäre E-Mail-Adresse eines Benutzers zu ändern.
  
4. Es wird eine große gelbe Warnmeldung angezeigt, dass Sie dabei sind, die Anmeldeinformationen der Person zu ändern. Wählen Sie **Speichern** und dann **Schließen** aus.
    
5. Übermitteln Sie der Person die folgenden Informationen:
 
  - Diese Änderung kann eine Weile dauern.
  
  - Their new username. They'll need it to sign in to Microsoft 365.
    
  - Wenn die Person Skype for Business Online verwendet, muss sie von ihr organisierte Skype for Business Online-Besprechungen erneut planen und ihre externen Kontakte auffordern, ihre Kontaktinformationen zu aktualisieren.

  - Wenn die Person OneDrive verwendet, wurde die URL zu diesem Speicherort geändert. Wenn sich OneNote-Notizbücher auf ihrem OneDrive befinden, müssen sie möglicherweise geschlossen und in OneNote erneut geöffnet werden. Wenn über OneDrive Dateien geteilt wurden, funktionieren die Links zu den Dateien möglicherweise nicht, und die Person kann diese wieder freigeben.    
  
  - Wenn auch das Kennwort geändert wurde, wird die Person aufgefordert, das neue Kennwort auf ihrem mobilen Gerät einzugeben. Andernfalls wird es nicht synchronisiert.
  
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Benutzername/E-Mail-** **Bearbeiten** aus.

3. Wählen Sie **Als primäre E-Mail-Adresse festlegen** für die E-Mail-Adresse aus, die Sie als primäre E-Mail-Adresse für diese Person festlegen möchten. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Diese Option wird außerdem nur angezeigt, wenn Sie ein globaler Administrator sind. Wenn Sie die Option nicht sehen, verfügen Sie nicht über die Berechtigung, den Namen und die primäre E-Mail-Adresse eines Benutzers zu ändern.
  
4. Es wird eine große gelbe Warnmeldung angezeigt, dass Sie dabei sind, die Anmeldeinformationen der Person zu ändern. Wählen Sie **Speichern** und dann **Schließen** aus.
    
5. Teilen Sie der Person die folgenden Informationen mit:
 
  - Es kann einige Zeit dauern, bis diese Änderung wirksam wird.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Wenn die Person Skype for Business Online verwendet, muss sie eventuelle von ihr organisierte Skype for Business Online-Besprechungen erneut planen und ihre externen Kontakte auffordern, die alten Kontaktinformationen zu aktualisieren.

  - Wenn Sie OneDrive verwenden, teilen Sie der Person mit, dass die URL zu diesem Speicherort geändert wurde. Wenn sie OneNote-Notizbücher auf ihrem OneDrive hat, müssen sie diese möglicherweise in OneNote schließen und erneut öffnen. Wenn sie über ihr OneDrive Dateien freigegeben hat, funktionieren die Links zu den Dateien möglicherweise nicht, und der Benutzer kann diese wieder freigeben.    
  
  - Wenn auch das Kennwort geändert wurde, wird die Person aufgefordert, das neue Kennwort auf ihrem mobilen Gerät einzugeben. Andernfalls wird es nicht synchronisiert.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Benutzername/E-Mail-** **Bearbeiten** aus.

3. Wählen Sie **Als primäre E-Mail-Adresse festlegen** für die E-Mail-Adresse aus, die Sie als primäre E-Mail-Adresse für diese Person festlegen möchten. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Diese Option wird außerdem nur angezeigt, wenn Sie ein globaler Administrator sind. Wenn Sie die Option nicht sehen, verfügen Sie nicht über die Berechtigung, den Namen und die primäre E-Mail-Adresse eines Benutzers zu ändern.
  
4. Es wird eine große gelbe Warnmeldung angezeigt, dass Sie dabei sind, die Anmeldeinformationen der Person zu ändern. Wählen Sie **Speichern** und dann **Schließen** aus.
    
5. Teilen Sie der Person die folgenden Informationen mit:
 
  - Es kann einige Zeit dauern, bis diese Änderung wirksam wird.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Wenn die Person Skype for Business Online verwendet, muss sie eventuelle von ihr organisierte Skype for Business Online-Besprechungen erneut planen und ihre externen Kontakte auffordern, die alten Kontaktinformationen zu aktualisieren.

  - Wenn Sie OneDrive verwenden, teilen Sie der Person mit, dass die URL zu diesem Speicherort geändert wurde. Wenn sie OneNote-Notizbücher auf ihrem OneDrive hat, müssen sie diese möglicherweise in OneNote schließen und erneut öffnen. Wenn sie über ihr OneDrive Dateien freigegeben hat, funktionieren die Links zu den Dateien möglicherweise nicht, und der Benutzer kann diese wieder freigeben.    
  
  - Wenn auch das Kennwort geändert wurde, wird die Person aufgefordert, das neue Kennwort auf ihrem mobilen Gerät einzugeben. Andernfalls wird es nicht synchronisiert.

::: moniker-end
  
## <a name="change-a-users-display-name"></a>Ändern des Anzeigenamens eines Benutzers

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Benutzers aus, und wählen Sie dann in der Registerkarte **Konto** **Kontaktinformationen verwalten** aus.

3. Geben Sie im Feld **Anzeigename** einen neuen Namen für die Person ein, und wählen Sie dann **Speichern** aus.

    Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen, und versuchen Sie es noch einmal**“ erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Kontaktinformationen****Bearbeiten** aus.

3. Geben Sie im Feld **Anzeigename** einen neuen Namen für die Person ein und wählen Sie dann **Speichern** aus.

    Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen, und versuchen Sie es noch einmal**“ erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie den Benutzer aus. Wählen Sie im Bereich „Flyout“ neben **Kontaktinformationen****Bearbeiten** aus.

3. Geben Sie im Feld **Anzeigename** einen neuen Namen für die Person ein und wählen Sie dann **Speichern** aus.

    Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen, und versuchen Sie es noch einmal**“ erhalten, sehen Sie unter [Fehlermeldungen lösen](#resolve-error-messages) nach.

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>Auflösen von Fehlermeldungen

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>„Es wurde kein Parameter gefunden, der dem Parameternamen ‚E-Mail-Adressen‘ entspricht“

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call [support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) and ask them to do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>„Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen und versuchen Sie es noch einmal“

Wenn Sie die Fehlermeldung „**Der Benutzer konnte leider nicht bearbeitet werden. Überprüfen Sie die Benutzerinformationen und versuchen Sie es noch einmal**“ erhalten, bedeutet dies, dass Sie kein globaler Administrator sind und nicht über die Berechtigung zum Ändern des Benutzernamens verfügen. Suchen Sie den globalen Administrator in Ihrem Unternehmen und bitten Sie ihn, die Änderung vorzunehmen.


## <a name="what-to-do-with-old-email-addresses"></a>Was mit alten E-Mail-Adressen zu tun ist

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people might continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft automatically routes it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>Wie ist vorzugehen, wenn das Offline-Adressbuch des Benutzers nicht mit der globalen Adressliste synchronisiert wird?

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you might see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it doesn't change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
Um dies zu beheben, melden Sie sich beim [Azure Active Directory-Modul für PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) mit Ihren Administratoranmeldeinformationen für Microsoft 365 an. Verwenden Sie die folgende Syntax: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Damit wird das Attribut **userPrincipalName** einer Person geändert, allerdings hat dies keine Auswirkungen auf deren Microsoft Online E-Mail Routing-Adresse (MOERA). Als bewährte Methode sollten Sie jedoch dafür sorgen, dass der Anmelde-UPN dieser Person mit ihrer primären SMTP-Adresse übereinstimmt. 
  
Wenn Sie erfahren möchten, wie ein Benutzername einer Person in Active Directory, in Windows Server 2003 und früher geändert wird, lesen Sie [Umbenennen eines Benutzerkontos](https://go.microsoft.com/fwlink/?LinkId=809091).
  
## <a name="related-articles"></a>Verwandte Artikel

[Administratoren: Zurücksetzen eines Kennworts für ein oder mehrere Benutzer](reset-passwords.md)
  
[Hinzufügen einer weiteren E-Mail-Adresse für einen Benutzer](../email/add-another-email-alias-for-a-user.md)
