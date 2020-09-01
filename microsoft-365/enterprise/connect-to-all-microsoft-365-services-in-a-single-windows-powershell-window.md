---
title: Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307625"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster

Wenn Sie PowerShell zur Verwaltung von Microsoft 365 verwenden, ist es möglich, mehrere PowerShell-Sitzungen gleichzeitig in verschiedenen PowerShell-Fenstern zu öffnen, die Sie zum Verwalten von Benutzerkonten, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams und das Security &amp; Compliance Center benötigen. 
  
Dies ist für das Verwalten von Microsoft 365 nicht optimal, da es nicht möglich ist, Daten zwischen diesen Fenstern für eine dienstübergreifende Verwaltung auszutauschen. Dieses Thema beschreibt die Verwendung einer einzelnen Instanz von PowerShell, von der aus Sie Microsoft 365-Konten, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams und das Security &amp; Compliance Center verwalten können.

>[!Note]
>Dieser Artikel enthält derzeit nur die Befehle zum Herstellen der Verbindung mit der Worldwide-Cloud (+GCC). Hinweise stellen Links zu Artikeln mit Informationen über die Verbindung zu den anderen Microsoft 365-Clouds bereit.
>

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie Microsoft 365 von einer einzigen Instanz von PowerShell aus verwalten können, beachten Sie die folgenden Voraussetzungen:
  
- Das Microsoft 365-Geschäfts-, Schul- oder Unikonto, das Sie für diese Verfahren verwenden, muss Mitglied einer Microsoft 365-Administratorrolle sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide). Das ist eine Voraussetzung für PowerShell für Microsoft 365, nicht unbedingt für andere Microsoft 365-Dienste.
    
- Sie können folgende 64-Bit-Versionen von Windows verwenden:
    
  - Windows 10
    
  - Windows 8.1 oder Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 oder Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Sie müssen das Microsoft .NET Framework 4.5*x* und anschließend entweder das Windows Management Framework 3.0 oder das Windows Management Framework 4.0 installieren. Weitere Informationen finden Sie unter [Installieren von .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) und [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) oder [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    Aufgrund der Anforderungen für das Skype for Business Online-Modul müssen Sie eine 64-Bit-Version von Windows und eins der Microsoft 365-Module verwenden.
    
- Sie müssen die Module installieren, die für Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online und Teams erforderlich sind:
    
   - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [SharePoint Online-Verwaltungsshell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [Skype for Business Online, PowerShell-Modul](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [Übersicht über PowerShell für Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  PowerShell muss konfiguriert werden, um signierte Skripte für Skype for Business Online und das Security &amp; Compliance Center auszuführen. Dazu führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Berechtigungen aus (hierbei handelt es sich um ein PowerShell-Fenster, das Sie durch das Auswählen von **Als Administrator ausführen** öffnen).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Schritte zum Herstellen einer Verbindung, wenn Sie nur ein Kennwort verwenden

Hier sind die Schritte zum Herstellen einer Verbindung zu allen Diensten in einem einzigen PowerShell-Fenster aufgeführt, wenn Sie nur ein Kennwort für die Anmeldung verwenden.
  
1. Öffnen Sie Windows PowerShell.
    
2. Führen Sie diesen Befehl aus, und geben Sie die Anmeldeinformationen für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Führen Sie diesen Befehl aus, um mithilfe des Azure Active Directory PowerShell für Graph-Moduls eine Verbindung zu Azure AD herzustellen.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden, führen Sie alternativ diesen Befehl aus.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über PowerShell ausführen.

4. Führen Sie diese Befehle zum Herstellen einer Verbindung mit SharePoint Online aus. Geben Sie den Organisationsnamen für Ihre Domäne an. Für "litwareinc.onmicrosoft.com" lautet der Organisationsnamenswert beispielsweise "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Führen Sie diese Befehle aus, um eine Verbindung mit Skype for Business Online herzustellen. Eine Warnung über das Erhöhen des `WSMan NetworkDelayms`-Werts wird ggf. beim ersten Verbinden angezeigt und sollte ignoriert werden.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Führen Sie diesen Befehl aus, um eine Verbindung zu Exchange Online herzustellen.
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Um eine Verbindung zu Exchange Online für andere Microsoft 365-Clouds als der Worldwide-Cloud herzustellen, verwenden Sie den Parameter **-ExchangeEnvironmentName**. Weitere Informationen finden Sie unter [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps).

7. Führen Sie diese Befehle zum Herstellen einer Verbindung mit Teams PowerShell aus.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Informationen zur Verbindung mit anderen Microsoft Teams-Clouds als der Worldwide-Cloud finden Sie unter [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).

8. Führen Sie diese Befehle zum Herstellen einer Verbindung mit dem Security &amp; Compliance Center aus.
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > Informationen zur Verbindung mit dem Security &amp; Compliance Center für Microsoft 365-Clouds außer Worldwide finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

Hier finden Sie alle Befehle in einem einzigen Block, wenn Sie das Azure Active Directory PowerShell für Graph-Modul verwenden. Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Alternativ finden Sie hier alle Befehle in einem einzigen Block, wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden. Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Wenn Sie bereit sind, das PowerShell-Fenster zu schließen, führen Sie diesen Befehl aus, um die aktiven Sitzungen in Skype for Business Online, SharePoint Online, im Security &amp; Compliance Center und Teams zu entfernen:
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Schritte zum Herstellen einer Verbindung bei Verwendung der mehrstufigen Authentifizierung

Hier finden Sie alle Befehle in einem einzigen Block, um eine Verbindung mit Azure AD, SharePoint Online, Skype for Business, Exchange Online und Teams mit der mehrstufigen Authentifizierung in einem einzigen Fenster unter Verwendung des Azure Active Directory PowerShell für Graph-Moduls herzustellen. Geben Sie den Benutzerprinzipalnamen (UPN) eines Benutzerkontos und Ihren Domainhostnamen an, und führen Sie dann alle gleichzeitig aus.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

Alternativ finden Sie hier alle Befehle, wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

Informationen zum Security &amp; Compliance Center finden Sie unter [Verbinden mit PowerShell für Security & Compliance Center über die mehrstufige Authentifizierung](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) zum Herstellen einer Verbindung unter Verwendung der mehrstufigen Authentifizierung:

## <a name="see-also"></a>Siehe auch

- [Verbinden mit Microsoft 365 über PowerShell](connect-to-microsoft-365-powershell.md)
- [Verwalten von SharePoint Online mit PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
