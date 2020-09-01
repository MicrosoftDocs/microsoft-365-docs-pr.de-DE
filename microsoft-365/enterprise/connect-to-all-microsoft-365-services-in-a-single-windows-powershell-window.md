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
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="525d1-103">Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster</span><span class="sxs-lookup"><span data-stu-id="525d1-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="525d1-104">Wenn Sie PowerShell zur Verwaltung von Microsoft 365 verwenden, ist es möglich, mehrere PowerShell-Sitzungen gleichzeitig in verschiedenen PowerShell-Fenstern zu öffnen, die Sie zum Verwalten von Benutzerkonten, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams und das Security &amp; Compliance Center benötigen.</span><span class="sxs-lookup"><span data-stu-id="525d1-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="525d1-105">Dies ist für das Verwalten von Microsoft 365 nicht optimal, da es nicht möglich ist, Daten zwischen diesen Fenstern für eine dienstübergreifende Verwaltung auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="525d1-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="525d1-106">Dieses Thema beschreibt die Verwendung einer einzelnen Instanz von PowerShell, von der aus Sie Microsoft 365-Konten, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams und das Security &amp; Compliance Center verwalten können.</span><span class="sxs-lookup"><span data-stu-id="525d1-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="525d1-107">Dieser Artikel enthält derzeit nur die Befehle zum Herstellen der Verbindung mit der Worldwide-Cloud (+GCC).</span><span class="sxs-lookup"><span data-stu-id="525d1-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="525d1-108">Hinweise stellen Links zu Artikeln mit Informationen über die Verbindung zu den anderen Microsoft 365-Clouds bereit.</span><span class="sxs-lookup"><span data-stu-id="525d1-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="525d1-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="525d1-109">Before you begin</span></span>

<span data-ttu-id="525d1-110">Bevor Sie Microsoft 365 von einer einzigen Instanz von PowerShell aus verwalten können, beachten Sie die folgenden Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="525d1-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="525d1-111">Das Microsoft 365-Geschäfts-, Schul- oder Unikonto, das Sie für diese Verfahren verwenden, muss Mitglied einer Microsoft 365-Administratorrolle sein.</span><span class="sxs-lookup"><span data-stu-id="525d1-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="525d1-112">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="525d1-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="525d1-113">Das ist eine Voraussetzung für PowerShell für Microsoft 365, nicht unbedingt für andere Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="525d1-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="525d1-114">Sie können folgende 64-Bit-Versionen von Windows verwenden:</span><span class="sxs-lookup"><span data-stu-id="525d1-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="525d1-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="525d1-115">Windows 10</span></span>
    
  - <span data-ttu-id="525d1-116">Windows 8.1 oder Windows 8</span><span class="sxs-lookup"><span data-stu-id="525d1-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="525d1-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="525d1-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="525d1-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="525d1-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="525d1-119">Windows Server 2012 R2 oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="525d1-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="525d1-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="525d1-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="525d1-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="525d1-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="525d1-122">\* Sie müssen das Microsoft .NET Framework 4.5*x* und anschließend entweder das Windows Management Framework 3.0 oder das Windows Management Framework 4.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="525d1-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="525d1-123">Weitere Informationen finden Sie unter [Installieren von .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) und [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) oder [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="525d1-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="525d1-124">Aufgrund der Anforderungen für das Skype for Business Online-Modul müssen Sie eine 64-Bit-Version von Windows und eins der Microsoft 365-Module verwenden.</span><span class="sxs-lookup"><span data-stu-id="525d1-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="525d1-125">Sie müssen die Module installieren, die für Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online und Teams erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="525d1-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="525d1-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="525d1-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="525d1-127">SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="525d1-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="525d1-128">Skype for Business Online, PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="525d1-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="525d1-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="525d1-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="525d1-130">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="525d1-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="525d1-131">PowerShell muss konfiguriert werden, um signierte Skripte für Skype for Business Online und das Security &amp; Compliance Center auszuführen.</span><span class="sxs-lookup"><span data-stu-id="525d1-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="525d1-132">Dazu führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Berechtigungen aus (hierbei handelt es sich um ein PowerShell-Fenster, das Sie durch das Auswählen von **Als Administrator ausführen** öffnen).</span><span class="sxs-lookup"><span data-stu-id="525d1-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="525d1-133">Schritte zum Herstellen einer Verbindung, wenn Sie nur ein Kennwort verwenden</span><span class="sxs-lookup"><span data-stu-id="525d1-133">Connection steps when using just a password</span></span>

<span data-ttu-id="525d1-134">Hier sind die Schritte zum Herstellen einer Verbindung zu allen Diensten in einem einzigen PowerShell-Fenster aufgeführt, wenn Sie nur ein Kennwort für die Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="525d1-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="525d1-135">Öffnen Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="525d1-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="525d1-136">Führen Sie diesen Befehl aus, und geben Sie die Anmeldeinformationen für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein.</span><span class="sxs-lookup"><span data-stu-id="525d1-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="525d1-137">Führen Sie diesen Befehl aus, um mithilfe des Azure Active Directory PowerShell für Graph-Moduls eine Verbindung zu Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="525d1-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="525d1-138">Wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden, führen Sie alternativ diesen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="525d1-139">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="525d1-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="525d1-140">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="525d1-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="525d1-141">Führen Sie diese Befehle zum Herstellen einer Verbindung mit SharePoint Online aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="525d1-142">Geben Sie den Organisationsnamen für Ihre Domäne an.</span><span class="sxs-lookup"><span data-stu-id="525d1-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="525d1-143">Für "litwareinc.onmicrosoft.com" lautet der Organisationsnamenswert beispielsweise "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="525d1-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="525d1-144">Führen Sie diese Befehle aus, um eine Verbindung mit Skype for Business Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="525d1-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="525d1-145">Eine Warnung über das Erhöhen des `WSMan NetworkDelayms`-Werts wird ggf. beim ersten Verbinden angezeigt und sollte ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="525d1-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="525d1-146">Führen Sie diesen Befehl aus, um eine Verbindung zu Exchange Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="525d1-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="525d1-147">Um eine Verbindung zu Exchange Online für andere Microsoft 365-Clouds als der Worldwide-Cloud herzustellen, verwenden Sie den Parameter **-ExchangeEnvironmentName**.</span><span class="sxs-lookup"><span data-stu-id="525d1-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="525d1-148">Weitere Informationen finden Sie unter [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="525d1-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="525d1-149">Führen Sie diese Befehle zum Herstellen einer Verbindung mit Teams PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="525d1-150">Informationen zur Verbindung mit anderen Microsoft Teams-Clouds als der Worldwide-Cloud finden Sie unter [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="525d1-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="525d1-151">Führen Sie diese Befehle zum Herstellen einer Verbindung mit dem Security &amp; Compliance Center aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="525d1-152">Informationen zur Verbindung mit dem Security &amp; Compliance Center für Microsoft 365-Clouds außer Worldwide finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="525d1-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="525d1-153">Hier finden Sie alle Befehle in einem einzigen Block, wenn Sie das Azure Active Directory PowerShell für Graph-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="525d1-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="525d1-154">Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="525d1-155">Alternativ finden Sie hier alle Befehle in einem einzigen Block, wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="525d1-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="525d1-156">Geben Sie den Namen Ihres Domänenhosts an, und führen Sie alle Befehle gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="525d1-157">Wenn Sie bereit sind, das PowerShell-Fenster zu schließen, führen Sie diesen Befehl aus, um die aktiven Sitzungen in Skype for Business Online, SharePoint Online, im Security &amp; Compliance Center und Teams zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="525d1-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="525d1-158">Schritte zum Herstellen einer Verbindung bei Verwendung der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="525d1-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="525d1-159">Hier finden Sie alle Befehle in einem einzigen Block, um eine Verbindung mit Azure AD, SharePoint Online, Skype for Business, Exchange Online und Teams mit der mehrstufigen Authentifizierung in einem einzigen Fenster unter Verwendung des Azure Active Directory PowerShell für Graph-Moduls herzustellen.</span><span class="sxs-lookup"><span data-stu-id="525d1-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="525d1-160">Geben Sie den Benutzerprinzipalnamen (UPN) eines Benutzerkontos und Ihren Domainhostnamen an, und führen Sie dann alle gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="525d1-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

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

<span data-ttu-id="525d1-161">Alternativ finden Sie hier alle Befehle, wenn Sie das Microsoft Azure Active Directory-Modul für PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="525d1-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

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

<span data-ttu-id="525d1-162">Informationen zum Security &amp; Compliance Center finden Sie unter [Verbinden mit PowerShell für Security & Compliance Center über die mehrstufige Authentifizierung](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) zum Herstellen einer Verbindung unter Verwendung der mehrstufigen Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="525d1-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="525d1-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="525d1-163">See also</span></span>

- [<span data-ttu-id="525d1-164">Verbinden mit Microsoft 365 über PowerShell</span><span class="sxs-lookup"><span data-stu-id="525d1-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="525d1-165">Verwalten von SharePoint Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="525d1-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="525d1-166">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="525d1-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
