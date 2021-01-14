---
title: Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Zusammenfassung: Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster.'
ms.openlocfilehash: 4266b4f216b4c9df48f0c19d1d2123269eb32cae
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849593"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster

Wenn Sie Microsoft 365 mithilfe von PowerShell verwalten, können mehrere PowerShell-Sitzungen zur gleichen Zeit geöffnet werden. Möglicherweise verwenden Sie unterschiedliche PowerShell-Fenster zum Verwalten von Benutzerkonten, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams und des Security &amp; Compliance Centers.
  
Dieses Szenario ist für das Verwalten von Microsoft 365 nicht optimal, da es nicht möglich ist, Daten zwischen diesen Fenstern für eine dienstübergreifende Verwaltung auszutauschen. In diesem Artikel wird die Verwendung einer einzelnen Instanz von PowerShell beschrieben, von der aus Sie Microsoft 365-Konten, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams und das Security &amp; Compliance Center verwalten können.

>[!Note]
>Dieser Artikel enthält derzeit nur die Befehle zum Herstellen der Verbindung mit der Worldwide-Cloud (+GCC). In Hinweisen werden Links zu Artikeln mit Informationen über die Verbindung zu den anderen Microsoft 365-Clouds bereitgestellt.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie Microsoft 365 von einer einzigen Instanz von PowerShell aus verwalten können, beachten Sie die folgenden Voraussetzungen:
  
- Das Microsoft 365-Geschäfts-, Schul- oder Unikonto, das Sie verwenden, muss über eine Microsoft 365-Administratorrolle verfügen. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Das ist eine Voraussetzung für PowerShell für Microsoft 365, aber nicht unbedingt für andere Microsoft 365-Dienste.
    
- Sie können folgende 64-Bit-Versionen von Windows verwenden:
    
  - Windows 10
    
  - Windows 8.1 oder Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 oder Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Sie müssen Microsoft .NET Framework 4.5.*x* und dann Windows Management Framework 3.0 oder 4.0 installieren. Weitere Informationen finden Sie unter [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).
    
    Aufgrund der Anforderungen für das Skype for Business Online-Modul müssen Sie eine 64-Bit-Version von Windows und eins der Microsoft 365-Module verwenden.
    
- Sie müssen die Module installieren, die für Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online und Teams erforderlich sind:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online-Verwaltungsshell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online, PowerShell-Modul](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Übersicht über PowerShell für Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  PowerShell muss so konfiguriert werden, dass signierte Skripts für Skype for Business Online und das Security &amp; Compliance Center ausgeführt werden. Führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Berechtigungen aus (eine PowerShell-Sitzung, die Sie **als Administrator ausführen**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online und Security &amp; Compliance Center mit dem Exchange Online PowerShell V2-Modul

Für die Verfahren in diesem Artikel wird das Exchange Online PowerShell V2-Modul verwendet, um eine Verbindung mit Exchange Online und dem Security &amp; Compliance Center herzustellen. Derzeit können Sie jedoch nicht zu beiden *im selben PowerShell-Fenster* eine Verbindung herstellen. Sie müssen also auswählen, ob eine Verbindung zum einen oder dem anderen hergestellt werden soll, wenn Sie ein PowerShell-Fenster für mehrere Microsoft 365-Dienste konfigurieren.

## <a name="connection-steps-when-using-just-a-password"></a>Schritte zum Herstellen einer Verbindung, wenn Sie nur ein Kennwort verwenden

Folgen Sie den nachstehend beschriebenen Schritten zum Herstellen einer Verbindung zu allen Diensten in einem einzigen PowerShell-Fenster, wenn Sie nur ein Kennwort für die Anmeldung verwenden.
  
1. Öffnen Sie Windows PowerShell.
    
2. Führen Sie diesen Befehl aus, und geben Sie die Anmeldeinformationen für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Führen Sie diesen Befehl aus, um mithilfe des Azure Active Directory PowerShell für Graph-Moduls eine Verbindung zu Azure AD herzustellen.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Wenn Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul verwenden, führen Sie alternativ diesen Befehl aus.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt. Sie müssen diese Cmdlets über PowerShell ausführen.

4. Führen Sie diese Befehle zum Herstellen einer Verbindung mit SharePoint Online aus. Geben Sie den Organisationsnamen für Ihre Domäne an. Für "litwareinc\.onmicrosoft.com" lautet der Organisationsnamenswert beispielsweise "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Führen Sie diese Befehle aus, um eine Verbindung mit Skype for Business Online herzustellen. Wenn Sie zum ersten Mal eine Verbindung herstellen, wird eine Warnung zur Erhöhung des `WSMan NetworkDelayms`-Werts angezeigt. Ignorieren Sie diese Warnung.
     
   > [!Note]
   > Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Führen Sie diesen Befehl aus, um eine Verbindung zu Exchange Online herzustellen.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Informationen zum Herstellen einer Verbindung mit Exchange Online für Microsoft 365-Clouds außer der weltweiten finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

   Alternativ können Sie diese Befehle zum Herstellen einer Verbindung mit dem Security &amp; Compliance Center ausführen.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Informationen zur Verbindung mit dem Security &amp; Compliance Center für Microsoft 365-Clouds außer der weltweiten finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

   Führen Sie diese Befehle zum Herstellen einer Verbindung mit Teams PowerShell aus.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Informationen zur Verbindung mit anderen Microsoft Teams-Clouds als der *Worldwide*-Cloud finden Sie unter [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell für Graph-Modul

Nachfolgend sehen Sie die Befehle für alle Dienste *mit Ausnahme des Security &amp; Compliance Centers* in einem einzigen Block bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls. Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Nachfolgend sehen Sie die Befehle für alle Dienste *mit Ausnahme von Exchange Online* in einem einzigen Block bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls. Geben Sie den Namen Ihres Domänenhosts und den UPN für die Anmeldung an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul

Nachfolgend sehen Sie die Befehle für alle Dienste *mit Ausnahme des Security &amp; Compliance Centers* in einem einzigen Block bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul. Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Nachfolgend sehen Sie die Befehle für alle Dienste *mit Ausnahme von Exchange Online* in einem einzigen Block bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul. Geben Sie den Namen Ihres Domänenhosts und den UPN für die Anmeldung an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Schritte zum Herstellen einer Verbindung bei Verwendung der mehrstufigen Authentifizierung

### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell für Graph-Modul

Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten (*außer dem Security &amp; Compliance Center*) mit mehrstufiger Authentifizierung herzustellen bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten (*außer Exchange Online*) mit mehrstufiger Authentifizierung herzustellen bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul

Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten (*außer dem Security &amp; Compliance Center*) mit mehrstufiger Authentifizierung herzustellen bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten (*außer Exchange Online*) mit mehrstufiger Authentifizierung herzustellen bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Schließen des PowerShell-Fensters

Führen Sie zum Schließen des PowerShell-Fensters diesen Befehl aus, um die aktiven Sitzungen in Skype for Business Online, SharePoint Online und Microsoft Teams zu entfernen:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Siehe auch

- [Verbinden mit Microsoft 365 über PowerShell](connect-to-microsoft-365-powershell.md)
- [Verwalten von SharePoint Online mit PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
