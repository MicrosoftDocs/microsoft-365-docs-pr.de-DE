---
title: Verbinden mit Microsoft 365 über PowerShell
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
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Stellen Sie eine Verbindung mit Ihrem Microsoft 365-Mandanten mithilfe von PowerShell für Microsoft 365 her, um Aufgaben des Admin Centers über die Befehlszeile auszuführen.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690638"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Verbinden mit Microsoft 365 über PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Mit PowerShell für Microsoft 365 können Sie Ihre Microsoft 365-Einstellungen über die Befehlszeile verwalten. Das Herstellen einer Verbindung mit PowerShell ist ein einfacher Vorgang, bei dem Sie die erforderliche Software installieren und dann eine Verbindung mit Ihrer Microsoft 365-Organisation herstellen. 

Es gibt zwei Versionen des PowerShell-Moduls, mit denen Sie die Verbindung zu Microsoft 365 herstellen sowie Benutzerkonten, Gruppen und Lizenzen verwalten können:

- Azure Active Directory PowerShell für Graph (Cmdlets enthalten **AzureAD** in ihrem Namen)
- Microsoft Azure Active Directory-Modul für Windows PowerShell (Cmdlets enthalten **MSol** in ihrem Namen) 

Zum Zeitpunkt des Erscheinens dieses Artikels ersetzt das Azure Active Directory PowerShell für Graph-Modul nicht vollständig die Funktionen in den Cmdlets des Microsoft Azure Active Directory-Moduls für Windows PowerShell für Benutzer-, Gruppen- und Lizenzverwaltung. In einigen Fällen müssen Sie beide Versionen verwenden. Sie können problemlos beide Versionen auf demselben Computer installieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Sie können folgende Versionen von Windows verwenden:
    
  - Windows 10, Windows 8.1, Windows 8 oder Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 SP1

    > [!NOTE]
    > Für das Azure Active Directory PowerShell für Graph-Modul müssen Sie PowerShell 5.1 oder höher verwenden. Für das Microsoft Azure Active Directory-Modul für Windows PowerShell müssen Sie PowerShell 5.1 oder höher bis zu PowerShell 6 verwenden. PowerShell 7 können Sie nicht verwenden. Für Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 SP1 laden Sie [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) herunter. und installieren Sie es. 
    
    > [!NOTE]
    > Verwenden Sie eine 64-Bit-Version von Windows. Die Unterstützung für die 32-Bit-Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell wurde im Oktober 2014 eingestellt.
    
Diese Verfahren sind für Benutzer vorgesehen, die Mitglieder einer Microsoft 365-Administratorrolle sind. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul

Befehle im Azure Active Directory PowerShell für Graph-Modul haben **AzureAD** in ihrem Cmdlet-Namen. Sie können das [Azure Active Directory PowerShell für Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)-Modul oder [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1) installieren.

Führen Sie bei Verfahren, die die neuen Cmdlets im Azure Active Directory PowerShell für Graph-Modul benötigen, die nachstehenden Schritte zum Installieren des Moduls und Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement aus.

>[!Note]
>Informationen zur Unterstützung für verschiedene Versionen von Microsoft Windows finden Sie unter [Azure Active Directory PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).
>

### <a name="step-1-install-required-software"></a>Schritt 1: Installieren der erforderlichen Software

Diese Schritte sind auf Ihrem Computer nur einmal erforderlich, nicht jedes Mal, wenn Sie eine Verbindung herstellen. Allerdings müssen Sie wahrscheinlich in regelmäßigen Abständen neuere Versionen der Software installieren.
  
1. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).
    
2. Führen Sie im Befehlsfenster **Administrator: Windows PowerShell** den folgenden Befehl aus:
    
  ```powershell
  Install-Module -Name AzureAD
  ```

Falls Sie gefragt werden, ob Sie ein Modul aus einem nicht vertrauenswürdigen Repository installieren möchten: Geben Sie **Y** ein, und drücken Sie die EINGABETASTE.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement

Wenn Sie eine Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) herstellen möchten, führen Sie einen dieser Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).

| Office 365-Cloud | Befehl |
|:-------|:-----|
| Office 365 weltweit (+GCC) | `Connect-AzureAD` |
| Office 365, betrieben von 21Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Deutschland | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Geben Sie im Dialogfeld**Anmelden bei Ihrem Konto** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und klicken Sie dann auf **OK**.

Wenn Sie MFA verwenden, befolgen Sie die Anweisungen in den zusätzlichen Dialogfeldern, um weitere Authentifizierungsinformationen, z. B. einen Überprüfungscode, bereitzustellen.

Nach dem Herstellen der Verbindung können Sie die Cmdlets für das [Azure Active Directory PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) verwenden.
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Herstellen einer Verbindung mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell

Die Befehle im Microsoft Azure Active Directory-Modul für Windows PowerShell enthalten **Msol** in ihrem Cmdlet-Namen.

Das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen werden von PowerShell 7 und höher nicht unterstützt. Für PowerShell 7 oder höher müssen Sie das Azure Active Directory PowerShell für Graph-Modul oder Azure PowerShell verwenden.

PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen. 
    
### <a name="step-1-install-required-software"></a>Schritt 1: Installieren der erforderlichen Software

Diese Schritte sind auf Ihrem Computer nur einmal erforderlich, nicht jedes Mal, wenn Sie eine Verbindung herstellen. Allerdings müssen Sie wahrscheinlich in regelmäßigen Abständen neuere Versionen der Software installieren.
  
1.  Wenn Sie Windows 10 nicht ausführen, installieren Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten: [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:
    
  - Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).
  - Führen Sie den Befehl**Install-Module MSOnline** aus.
  - Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.
  - Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement

Wenn Sie eine Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) herstellen möchten, führen Sie einen dieser Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).

| Office 365-Cloud | Befehl |
|:-------|:-----|
| Office 365 weltweit (+GCC) | `Connect-MsolService` |
| Office 365, betrieben von 21Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Deutschland | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Geben Sie im Dialogfeld**Anmelden bei Ihrem Konto** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und klicken Sie dann auf **OK**.

Wenn Sie MFA verwenden, befolgen Sie die Anweisungen in den zusätzlichen Dialogfeldern, um weitere Authentifizierungsinformationen, z. B. einen Überprüfungscode, bereitzustellen.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein schneller Test ist die Ausführung eines Microsoft 365-Cmdlets, z. B. **Get-MsolUser**, und die Betrachtung der Ergebnisse.
  
Wenn Sie Fehlermeldungen erhalten, überprüfen Sie die folgenden Anforderungen:
  
- **Ein häufig auftretendes Problem ist ein falsches Kennwort**. Führen Sie Schritt 2 erneut aus, und achten Sie auf den Benutzernamen und das Kennwort, die Sie eingeben.
    
- **Das Microsoft Azure Active Directory-Modul für Windows PowerShell setzt voraus, dass das Feature Microsoft .NET Framework 3.5.* x* auf Ihrem Computer aktiviert ist**. Es ist wahrscheinlich, dass auf Ihrem Computer eine neuere Version installiert ist (z. B. 4 oder 4.5*x*), aber die Abwärtskompatibilität mit älteren Versionen von .NET Framework kann aktiviert oder deaktiviert werden. Weitere Informationen hierzu finden Sie in den folgenden Themen:
    
  - Informationen zu Windows Server 2012 oder Windows Server 2012 R2 finden Sie unter [Aktivieren von .NET Framework 3.5 mithilfe des Assistenten zum Hinzufügen von Rollen und Features](https://go.microsoft.com/fwlink/p/?LinkId=532368)
    
  - Informationen zu Windows 7 oder Windows Server 2008 R2 finden Sie unter[Das Azure Active Directory-Modul für Windows PowerShell kann nicht geöffnet werden](https://go.microsoft.com/fwlink/p/?LinkId=532370)

  - Informationen zu Windows 10, Windows 8.1 und Windows 8 finden Sie unter [Installieren von .NET Framework 3.5 unter Windows 10, Windows 8.1 und Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)

  
- **Möglicherweise ist Ihre Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell veraltet.** Um dies zu überprüfen, führen Sie den folgenden Befehl in PowerShell für Microsoft 365 oder im Microsoft Azure Active Directory-Modul für Windows PowerShell aus:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Wenn die zurückgegebene Versionsnummer niedriger als der Wert 1.0.8070.2 ist, deinstallieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell, und installieren Sie die neueste Version über den vorstehenden Schritt 1.

- **Wenn Sie einen Verbindungsfehler erhalten, finden Sie in diesem Thema weitere Informationen:** [Fehler "Connect-MsolService: Ausnahme vom Typ ausgelöst"](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Wenn Sie einen "Get-Item: Pfad nicht gefunden"-Fehler erhalten, verwenden Sie diesen Befehl:** 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a>Siehe auch

- [Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Verbinden mit allen Microsoft 365-Diensten in einem einzigen Windows PowerShell-Fenster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
