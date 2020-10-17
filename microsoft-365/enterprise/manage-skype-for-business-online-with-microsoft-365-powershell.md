---
title: Verwalten von Skype for Business Online mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Verwenden Sie PowerShell für Microsoft 365 zum Verwalten von Skype for Business Online-Richtlinien, benutzerspezifischen Richtlinien und Besprechungseinstellungen.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477101"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Verwalten von Skype for Business Online mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Für die Verwaltung von Richtlinien sind Skype for Business Online-Administratoren verantwortlich. Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center machen können, andere können in PowerShell einfacher gemacht werden.

## <a name="before-you-start"></a>Vor der Bereitstellung

  > [!Note]
   > Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
   
Installieren Sie das [PowerShell-Modul von Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).


## <a name="connect-using-admin-credentials"></a>Verbinden mit Administratoranmeldeinformationen

1. Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort Ihres Administratorkontos ein, und wählen Sie dann **OK** aus.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Herstellung einer Verbindung mit einem Administratorkonto mit mehrstufiger Authentifizierung

1. Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Wenn Sie durch den Befehl **New-CsOnlineSession** dazu aufgefordert werden, geben Sie den Namen Ihres Skype for Business Online-Administratorkontos ein.

3. Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** Ihr Skype for Business Online-Administratorkennwort ein und wählen Sie dann **Anmelden**.

4. Folgen Sie den Anweisungen im Dialogfeld **Bei Ihrem Konto anmelden**, um zusätzliche Authentifizierungsinformationen anzugeben, z. B. einen Überprüfungscode, und wählen Sie dann **Bestätigen**.

Weitere Informationen finden Sie unter:
  
- [Verwalten von Skype for Business Online-Richtlinien mit PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Zuweisen von benutzerspezifischen Skype for Business Online-Richtlinien mit PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Referenzen zu Skype for Business PowerShell-Cmdlets](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
