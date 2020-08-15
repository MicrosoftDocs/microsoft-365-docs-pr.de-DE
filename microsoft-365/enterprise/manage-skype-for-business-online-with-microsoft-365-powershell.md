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
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365 zum Verwalten von Skype for Business Online-Richtlinien, benutzerspezifischen Richtlinien und Besprechungseinstellungen.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690739"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Verwalten von Skype for Business Online mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Eine der Hauptaufgaben eines jeden Skype for Business Online-Administrators ist die Verwaltung von Richtlinien. Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center durchführen können, können andere Aufgaben in PowerShell wesentlich schneller und einfacher durchgeführt werden. 

## <a name="before-you-start"></a>Vor der Bereitstellung

Laden Sie das [Connector-Modul für Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366) herunter, installieren Sie es, und starten Sie Ihren Computer dann neu.


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a>Stellen Sie eine Verbindung unter Angabe des Namens und Kennworts Ihres Skype for Business Online-Administratorkontos her.

1. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort für Ihr Skype for Business Online-Administratorkonto ein, und klicken Sie dann auf **OK**.


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a>Stellen Sie eine Verbindung unter Verwendung Ihres Skype for Business Online-Administratorkontos mit mehrstufiger Authentifizierung her.

1. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Wenn Sie durch den Befehl **New-CsOnlineSession** dazu aufgefordert werden, geben Sie den Namen Ihres Skype for Business Online-Administratorkontos ein.

3. Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** Ihr Skype for Business Online-Administratorkennwort ein und klicken Sie dann auf **Anmelden**.

4. Folgen Sie den Anweisungen im Dialogfeld **Bei Ihrem Konto anmelden**, um zusätzliche Authentifizierungsinformationen anzugeben, z. B. einen Überprüfungscode, und klicken Sie dann auf **Bestätigen**.

Weitere Informationen hierzu finden Sie in den folgenden Themen:
  
- [Verwalten von Skype for Business Online-Richtlinien mit PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Zuweisen von benutzerspezifischen Skype for Business Online-Richtlinien mit PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Referenzen zu Skype for Business PowerShell-Cmdlets](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

