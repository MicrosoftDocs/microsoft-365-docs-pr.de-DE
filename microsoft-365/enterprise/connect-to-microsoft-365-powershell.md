---
title: Verbinden mit Microsoft 365 über PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Stellen Sie eine Verbindung mit Ihrem Microsoft 365-Mandanten mithilfe von PowerShell für Microsoft 365 her, um Admin Center-Aufgaben über die Befehlszeile auszuführen.
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053059"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Verbinden mit Microsoft 365 über PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Mit PowerShell für Microsoft 365 können Sie Ihre Microsoft 365-Einstellungen über die Befehlszeile verwalten. Um eine Verbindung mit PowerShell herzustellen, installieren Sie einfach die erforderliche Software, und stellen Sie eine Verbindung mit Ihrer Microsoft 365-Organisation her.

Es gibt zwei Versionen des PowerShell-Moduls, mit denen Sie die Verbindung zu Microsoft 365 herstellen und Benutzerkonten, Gruppen und Lizenzen verwalten können:

- Azure Active Directory-PowerShell für Graph, dessen Cmdlets *AzureAD* in ihrem Namen enthalten
- Microsoft Azure Active Directory-Modul für Windows PowerShell, dessen Cmdlets *MSol* in ihrem Namen enthalten

Zurzeit ersetzt das Modul „Azure Active Directory-PowerShell für Graph“ die Funktionen des Moduls „Microsoft Azure Active Directory-Modul für Windows PowerShell“ für Benutzer-, Gruppen- und Lizenzverwaltung nicht vollständig. In einigen Fällen müssen Sie beide Versionen verwenden. Sie können problemlos beide Versionen auf demselben Computer installieren.

>[!Note]
>Sie können sich auch über das Microsoft 365 Admin Center mit [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) verbinden.
>


## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?


**Betriebssystem**

Sie müssen eine 64-Bit-Version von Windows verwenden. Die Unterstützung für die 32-Bit-Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell wurde 2014 eingestellt.

Sie können folgende Versionen von Windows verwenden:
    
  - Windows 10, Windows 8.1, Windows 8 oder Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 SP1

>[!Note]
>Für Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 SP1 laden Sie [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) herunter. und installieren Sie es.

**PowerShell**

- Für das Azure Active Directory PowerShell für Graph-Modul müssen Sie PowerShell 5.1 oder höher verwenden.

- Für das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul müssen Sie PowerShell 5.1 oder höher bis zu PowerShell 6 verwenden. PowerShell 7 kann nicht verwendet werden.
       
>[!Note]
>Diese Verfahren sind für Benutzer vorgesehen, die Mitglieder einer Microsoft 365-Administratorrolle sind. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul

Befehle im Azure Active Directory PowerShell für Graph-Modul haben *AzureAD* in ihrem Cmdlet-Namen. Sie können das [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2)-Modul oder [Azure PowerShell](/powershell/azure/install-az-ps) installieren.

Führen Sie bei Verfahren, die die neuen Cmdlets im Azure Active Directory PowerShell für Graph-Modul erfordern, die nachstehenden Schritte zum Installieren des Moduls und Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement aus.

> [!Note]
> Informationen zur Unterstützung für verschiedene Versionen von Windows finden Sie unter [Azure Active Directory PowerShell für Graph-Modul](/powershell/azure/active-directory/install-adv2).

### <a name="step-1-install-the-required-software"></a>Schritt 1: Installieren der erforderlichen Software

Diese Schritte sind nur einmal auf Ihrem Computer erforderlich. Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.
  
1. Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).
    
2. Führen Sie den folgenden Befehl aus:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert. Bei der ersten Verwendung der PSGallery wird die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antworten Sie mit **Ja** oder **Ja für alle**, um mit der Installation fortzufahren.


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement

Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure Active Directory (Azure AD) herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).

| Office 365-Cloud | Befehl |
|:-------|:-----|
| Office 365 weltweit (+GCC) | `Connect-AzureAD` |
| Office 365, betrieben von 21Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Deutschland | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.

Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.

Nach dem Herstellen der Verbindung können Sie die Cmdlets für das [Azure Active Directory PowerShell für Graph-Modul](/powershell/module/azuread) verwenden.

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Herstellen einer Verbindung mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell

>[!Note]
>Die Cmdlets im Microsoft Azure Active Directory-Modul für Windows PowerShell weisen *Msol* in ihrem Namen auf.

Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell 7 und höher nicht unterstützt. Für PowerShell 7 oder höher müssen Sie das Azure Active Directory PowerShell für Graph-Modul oder Azure PowerShell verwenden.

Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt. Führen Sie diese Cmdlets über Windows PowerShell aus.
    
### <a name="step-1-install-the-required-software"></a>Schritt 1: Installieren der erforderlichen Software

Diese Schritte sind nur einmal auf Ihrem Computer erforderlich. Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.
  
1.  Wenn Sie nicht Windows 10 ausführen, installieren Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten: [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).
    
2. Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:
    
   1. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).
   1.  Führen Sie den Befehl **Install-Module MSOnline** aus.
   1. Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.
   1. Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement

Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure AD herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).

| Office 365-Cloud | Befehl |
|:-------|:-----|
| Office 365 weltweit (+GCC) | `Connect-MsolService` |
| Office 365, betrieben von 21Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Deutschland | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.

Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.

### <a name="how-do-you-know-it-worked"></a>Woher wissen Sie, dass der Vorgang erfolgreich war?

Wenn Sie keine Fehlermeldung erhalten, wurde die Verbindung hergestellt. Führen Sie für einen schnellen Test ein Microsoft 365-Cmdlet aus, z. B.  **Get-MsolUser**, und sehen Sie sich die Ergebnisse an.
  
Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die folgenden Punkte:
  
- **Ein häufig auftretendes Problem ist ein falsches Kennwort**. Führen Sie [Schritt 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) erneut aus, und achten Sie dabei auf die korrekte Eingabe des Benutzernamens und des Kennworts.
    
- **Das Microsoft Azure Active Directory-Modul für Windows PowerShell setzt voraus, dass Microsoft .NET Framework 3.5.* x* auf Ihrem Computer aktiviert ist**. Es ist wahrscheinlich, dass auf Ihrem Computer eine neuere Version installiert ist (z. B. Version 4 oder 4.5.* x*). Die Abwärtskompatibilität mit älteren Versionen von .NET Framework kann jedoch aktiviert oder deaktiviert werden. Weitere Informationen finden Sie in den folgenden Artikeln:
    
  - Informationen zu Windows Server 2012 oder Windows Server 2012 R2 finden Sie unter [Aktivieren von .NET Framework 3.5 mithilfe des Assistenten zum Hinzufügen von Rollen und Features](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Informationen zu Windows 7 oder Windows Server 2008 R2 finden Sie unter[Das Azure Active Directory-Modul für Windows PowerShell kann nicht geöffnet werden](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Informationen zu Windows 10, Windows 8.1 und Windows 8 finden Sie unter [Installieren von .NET Framework 3.5 unter Windows 10, Windows 8.1 und Windows 8](/dotnet/framework/install/dotnet-35-windows-10).

  
- **Möglicherweise ist Ihre Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell veraltet.** Um dies zu überprüfen, führen Sie den folgenden Befehl in PowerShell für Microsoft 365 oder im Microsoft Azure Active Directory-Modul für Windows PowerShell aus:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Wenn die zurückgegebene Versionsnummer niedriger als *1.0.8070.2* ist, deinstallieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell, und führen Sie die Installation über den vorstehenden [Schritt 1](#step-1-install-the-required-software) durch.

- **Wenn Sie einen Verbindungsfehler erhalten**, finden Sie auf dieser Seite weitere Informationen: [Fehler "Connect-MsolService: Ausnahme vom Typ ausgelöst"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).
    
- **Wenn Sie einen "Get-Item: Pfad nicht gefunden"-Fehler erhalten**, führen Sie folgenden Befehl aus:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a>Mit Azure Cloud Shell verbinden

Wählen Sie das PowerShell-Fenstersymbol in der oberen rechten Ecke der Taskleiste aus, damit Sie sich vom Microsoft 365 Admin Center aus mit Azure Cloud Shell verbinden können. Wählen Sie im Bereich “**Willkommen bei Azure Cloud Shell**“ “**PowerShell**“ aus.

Sie benötigen ein aktives Azure-Abonnement für Ihre Organisation, das an Ihr Microsoft 365-Abonnement gebunden ist. Wenn Sie noch kein Abonnement haben, können Sie eins abschließen. Sobald Sie ein Azure-Abonnement haben, wird ein PowerShell-Fenster geöffnet, in dem Sie PowerShell-Befehle und -Skripts ausführen können.

Weitere Informationen finden Sie unter “[Azure Cloud Shell](/azure/cloud-shell/overview)“.

## <a name="see-also"></a>Siehe auch

- [Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Verbinden mit allen Microsoft 365-Diensten in einem einzigen Windows PowerShell-Fenster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
