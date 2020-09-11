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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430034"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Verwalten von Skype for Business Online mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Für die Verwaltung von Richtlinien sind Skype for Business Online-Administratoren verantwortlich. Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center machen können, andere können in PowerShell einfacher gemacht werden.

## <a name="before-you-start"></a>Vor der Bereitstellung

Laden Sie das [Windows PowerShell Modul für Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366) herunter, installieren Sie es, und starten Sie Ihren Computer dann neu.


## <a name="connect-using-skype-for-business-online-admin-credentials"></a>Herstellung einer Verbindung mit Skype for Business Online-Administratoranmeldeinformationen

1. Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort für Ihr Skype for Business Online-Administratorkonto ein und wählen Sie dann **OK**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Herstellung einer Verbindung mit einem Administratorkonto mit mehrstufiger Authentifizierung

1. Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:

   ```powershell
   Import-Module SkypeOnlineConnector
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
