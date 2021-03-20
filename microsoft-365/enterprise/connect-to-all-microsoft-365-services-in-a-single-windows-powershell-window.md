---
title: Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905128"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="3ca3d-103">Herstellen einer Verbindung mit allen Microsoft 365-Diensten in einem einzigen PowerShell-Fenster</span><span class="sxs-lookup"><span data-stu-id="3ca3d-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="3ca3d-104">Wenn Sie Microsoft 365 mithilfe von PowerShell verwalten, können mehrere PowerShell-Sitzungen zur gleichen Zeit geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="3ca3d-105">Möglicherweise verwenden Sie unterschiedliche PowerShell-Fenster zum Verwalten von Benutzerkonten, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams und des Security &amp; Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="3ca3d-106">Dieses Szenario ist für das Verwalten von Microsoft 365 nicht optimal, da es nicht möglich ist, Daten zwischen diesen Fenstern für eine dienstübergreifende Verwaltung auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="3ca3d-107">In diesem Artikel wird die Verwendung einer einzelnen Instanz von PowerShell beschrieben, von der aus Sie Microsoft 365-Konten, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams und das Security &amp; Compliance Center verwalten können.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="3ca3d-108">Dieser Artikel enthält derzeit nur die Befehle zum Herstellen der Verbindung mit der Worldwide-Cloud (+GCC).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="3ca3d-109">In Hinweisen werden Links zu Artikeln mit Informationen über die Verbindung zu den anderen Microsoft 365-Clouds bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3ca3d-110">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="3ca3d-110">Before you begin</span></span>

<span data-ttu-id="3ca3d-111">Bevor Sie Microsoft 365 von einer einzigen Instanz von PowerShell aus verwalten können, beachten Sie die folgenden Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="3ca3d-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="3ca3d-112">Das Microsoft 365-Geschäfts-, Schul- oder Unikonto, das Sie verwenden, muss über eine Microsoft 365-Administratorrolle verfügen.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="3ca3d-113">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span> <span data-ttu-id="3ca3d-114">Das ist eine Voraussetzung für PowerShell für Microsoft 365, aber nicht unbedingt für andere Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="3ca3d-115">Sie können folgende 64-Bit-Versionen von Windows verwenden:</span><span class="sxs-lookup"><span data-stu-id="3ca3d-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="3ca3d-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3ca3d-116">Windows 10</span></span>
    
  - <span data-ttu-id="3ca3d-117">Windows 8.1 oder Windows 8</span><span class="sxs-lookup"><span data-stu-id="3ca3d-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="3ca3d-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3ca3d-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="3ca3d-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3ca3d-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="3ca3d-120">Windows Server 2012 R2 oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3ca3d-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="3ca3d-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="3ca3d-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="3ca3d-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="3ca3d-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="3ca3d-123">\* Sie müssen Microsoft .NET Framework 4.5.*x* und dann Windows Management Framework 3.0 oder 4.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="3ca3d-124">Weitere Informationen finden Sie unter [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-124">For more information, see [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="3ca3d-125">Aufgrund der Anforderungen für das Skype for Business Online-Modul müssen Sie eine 64-Bit-Version von Windows und eins der Microsoft 365-Module verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="3ca3d-126">Sie müssen die Module installieren, die für Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online und Teams erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="3ca3d-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="3ca3d-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="3ca3d-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="3ca3d-128">SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="3ca3d-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="3ca3d-129">Skype for Business Online, PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="3ca3d-129">Skype for Business Online, PowerShell Module</span></span>](/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="3ca3d-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="3ca3d-130">Exchange Online PowerShell V2</span></span>](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="3ca3d-131">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ca3d-131">Teams PowerShell Overview</span></span>](/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="3ca3d-132">PowerShell muss so konfiguriert werden, dass signierte Skripts für Skype for Business Online und das Security &amp; Compliance Center ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="3ca3d-133">Führen Sie den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Berechtigungen aus (eine PowerShell-Sitzung, die Sie **als Administrator ausführen**).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="3ca3d-134">Schritte zum Herstellen einer Verbindung, wenn Sie nur ein Kennwort verwenden</span><span class="sxs-lookup"><span data-stu-id="3ca3d-134">Connection steps when using just a password</span></span>

<span data-ttu-id="3ca3d-135">Folgen Sie den nachstehend beschriebenen Schritten zum Herstellen einer Verbindung zu allen Diensten in einem einzigen PowerShell-Fenster, wenn Sie nur ein Kennwort für die Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="3ca3d-136">Öffnen Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3ca3d-137">Führen Sie diesen Befehl aus, und geben Sie die Anmeldeinformationen für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="3ca3d-138">Führen Sie diesen Befehl aus, um mithilfe des Azure Active Directory PowerShell für Graph-Moduls eine Verbindung zu Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="3ca3d-139">Wenn Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul verwenden, führen Sie alternativ diesen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="3ca3d-140">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="3ca3d-141">Sie müssen diese Cmdlets über PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="3ca3d-142">Führen Sie diese Befehle zum Herstellen einer Verbindung mit SharePoint Online aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="3ca3d-143">Geben Sie den Organisationsnamen für Ihre Domäne an.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="3ca3d-144">Für "litwareinc\.onmicrosoft.com" lautet der Organisationsnamenswert beispielsweise "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="3ca3d-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="3ca3d-145">Führen Sie diese Befehle aus, um eine Verbindung mit Skype for Business Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="3ca3d-146">Wenn Sie zum ersten Mal eine Verbindung herstellen, wird eine Warnung zur Erhöhung des `WSMan NetworkDelayms`-Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="3ca3d-147">Ignorieren Sie diese Warnung.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="3ca3d-148">Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3ca3d-149">Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="3ca3d-150">Führen Sie diese Befehle zum Herstellen einer Verbindung mit Exchange Online aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="3ca3d-151">Informationen zum Herstellen einer Verbindung mit Exchange Online für Microsoft 365-Clouds, außer der weltweiten, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="3ca3d-152">Führen Sie diese Befehle zum Herstellen einer Verbindung mit dem Security &amp; Compliance Center aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="3ca3d-153">Informationen zur Verbindung mit dem Security &amp; Compliance Center für Microsoft 365-Clouds außer der weltweiten finden Sie unter [Verbinden mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="3ca3d-154">Führen Sie diese Befehle zum Herstellen einer Verbindung mit Teams PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="3ca3d-155">Informationen zur Verbindung mit anderen Microsoft Teams-Clouds als der *Worldwide*-Cloud finden Sie unter [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="3ca3d-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3ca3d-156">Azure Active Directory PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="3ca3d-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3ca3d-157">Nachfolgend sehen Sie die Befehle für alle Dienste in einem einzigen Block bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="3ca3d-158">Geben Sie den Namen Ihres Domänenhosts und den UPN für die Anmeldung an, und führen Sie alle Befehle gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="3ca3d-159">Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="3ca3d-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="3ca3d-160">Nachfolgend sehen Sie die Befehle für alle Dienste in einem einzigen Block bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="3ca3d-161">Geben Sie den Namen Ihres Domänenhosts und den UPN für die Anmeldung an, und führen Sie alle Befehle gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="3ca3d-162">Schritte zum Herstellen einer Verbindung bei Verwendung der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3ca3d-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3ca3d-163">Azure Active Directory PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="3ca3d-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3ca3d-164">Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten mit mehrstufiger Authentifizierung herzustellen bei Verwendung des Azure Active Directory PowerShell für Graph-Moduls.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="3ca3d-165">Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="3ca3d-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="3ca3d-166">Nachfolgend sehen Sie alle Befehle in einem einzigen Block, um eine Verbindung mit mehreren Microsoft 365-Diensten mit mehrstufiger Authentifizierung herzustellen, bei Verwendung des Microsoft Azure Active Directory-Moduls für Windows PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="3ca3d-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="3ca3d-167">Schließen des PowerShell-Fensters</span><span class="sxs-lookup"><span data-stu-id="3ca3d-167">Close the PowerShell window</span></span>

<span data-ttu-id="3ca3d-168">Führen Sie zum Schließen des PowerShell-Fensters diesen Befehl aus, um die aktiven Sitzungen in Skype for Business Online, SharePoint Online und Microsoft Teams zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="3ca3d-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="3ca3d-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca3d-169">See also</span></span>

- [<span data-ttu-id="3ca3d-170">Verbinden mit Microsoft 365 über PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ca3d-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="3ca3d-171">Verwalten von SharePoint Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ca3d-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="3ca3d-172">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ca3d-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)