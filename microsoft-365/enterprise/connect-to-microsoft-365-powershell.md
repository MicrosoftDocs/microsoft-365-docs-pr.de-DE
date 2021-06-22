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
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="2699f-103">Verbinden mit Microsoft 365 über PowerShell</span><span class="sxs-lookup"><span data-stu-id="2699f-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="2699f-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2699f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2699f-105">Mit PowerShell für Microsoft 365 können Sie Ihre Microsoft 365-Einstellungen über die Befehlszeile verwalten.</span><span class="sxs-lookup"><span data-stu-id="2699f-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="2699f-106">Um eine Verbindung mit PowerShell herzustellen, installieren Sie einfach die erforderliche Software, und stellen Sie eine Verbindung mit Ihrer Microsoft 365-Organisation her.</span><span class="sxs-lookup"><span data-stu-id="2699f-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="2699f-107">Es gibt zwei Versionen des PowerShell-Moduls, mit denen Sie die Verbindung zu Microsoft 365 herstellen und Benutzerkonten, Gruppen und Lizenzen verwalten können:</span><span class="sxs-lookup"><span data-stu-id="2699f-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="2699f-108">Azure Active Directory-PowerShell für Graph, dessen Cmdlets *AzureAD* in ihrem Namen enthalten</span><span class="sxs-lookup"><span data-stu-id="2699f-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="2699f-109">Microsoft Azure Active Directory-Modul für Windows PowerShell, dessen Cmdlets *MSol* in ihrem Namen enthalten</span><span class="sxs-lookup"><span data-stu-id="2699f-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="2699f-110">Zurzeit ersetzt das Modul „Azure Active Directory-PowerShell für Graph“ die Funktionen des Moduls „Microsoft Azure Active Directory-Modul für Windows PowerShell“ für Benutzer-, Gruppen- und Lizenzverwaltung nicht vollständig.</span><span class="sxs-lookup"><span data-stu-id="2699f-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="2699f-111">In einigen Fällen müssen Sie beide Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2699f-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="2699f-112">Sie können problemlos beide Versionen auf demselben Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="2699f-112">You can safely install both versions on the same computer.</span></span>

>[!Note]
><span data-ttu-id="2699f-113">Sie können sich auch über das Microsoft 365 Admin Center mit [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) verbinden.</span><span class="sxs-lookup"><span data-stu-id="2699f-113">You can also connect with the [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) from the Microsoft 365 admin center.</span></span>
>


## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2699f-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2699f-114">What do you need to know before you begin?</span></span>


<span data-ttu-id="2699f-115">**Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="2699f-115">**Operating system**</span></span>

<span data-ttu-id="2699f-p103">Sie müssen eine 64-Bit-Version von Windows verwenden. Die Unterstützung für die 32-Bit-Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell wurde 2014 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2699f-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="2699f-118">Sie können folgende Versionen von Windows verwenden:</span><span class="sxs-lookup"><span data-stu-id="2699f-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="2699f-119">Windows 10, Windows 8.1, Windows 8 oder Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2699f-119">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="2699f-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="2699f-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="2699f-121">Für Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 SP1 laden Sie [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) herunter. und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="2699f-121">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="2699f-122">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2699f-122">**PowerShell**</span></span>

- <span data-ttu-id="2699f-123">Für das Azure Active Directory PowerShell für Graph-Modul müssen Sie PowerShell 5.1 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="2699f-123">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="2699f-p104">Für das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul müssen Sie PowerShell 5.1 oder höher bis zu PowerShell 6 verwenden. PowerShell 7 kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2699f-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="2699f-126">Diese Verfahren sind für Benutzer vorgesehen, die Mitglieder einer Microsoft 365-Administratorrolle sind.</span><span class="sxs-lookup"><span data-stu-id="2699f-126">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="2699f-127">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2699f-127">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2699f-128">Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="2699f-128">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2699f-129">Befehle im Azure Active Directory PowerShell für Graph-Modul haben *AzureAD* in ihrem Cmdlet-Namen.</span><span class="sxs-lookup"><span data-stu-id="2699f-129">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="2699f-130">Sie können das [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2)-Modul oder [Azure PowerShell](/powershell/azure/install-az-ps) installieren.</span><span class="sxs-lookup"><span data-stu-id="2699f-130">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="2699f-131">Führen Sie bei Verfahren, die die neuen Cmdlets im Azure Active Directory PowerShell für Graph-Modul erfordern, die nachstehenden Schritte zum Installieren des Moduls und Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-131">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="2699f-132">Informationen zur Unterstützung für verschiedene Versionen von Windows finden Sie unter [Azure Active Directory PowerShell für Graph-Modul](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="2699f-132">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="2699f-133">Schritt 1: Installieren der erforderlichen Software</span><span class="sxs-lookup"><span data-stu-id="2699f-133">Step 1: Install the required software</span></span>

<span data-ttu-id="2699f-134">Diese Schritte sind nur einmal auf Ihrem Computer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2699f-134">These steps are required only one time on your computer.</span></span> <span data-ttu-id="2699f-135">Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2699f-135">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="2699f-136">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).</span><span class="sxs-lookup"><span data-stu-id="2699f-136">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="2699f-137">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2699f-137">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="2699f-138">Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2699f-138">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="2699f-139">Bei der ersten Verwendung der PSGallery wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2699f-139">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="2699f-140">Antworten Sie mit **Ja** oder **Ja für alle**, um mit der Installation fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="2699f-140">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="2699f-141">Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="2699f-141">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="2699f-p109">Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure Active Directory (Azure AD) herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).</span><span class="sxs-lookup"><span data-stu-id="2699f-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="2699f-144">Office 365-Cloud</span><span class="sxs-lookup"><span data-stu-id="2699f-144">Office 365 cloud</span></span> | <span data-ttu-id="2699f-145">Befehl</span><span class="sxs-lookup"><span data-stu-id="2699f-145">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="2699f-146">Office 365 weltweit (+GCC)</span><span class="sxs-lookup"><span data-stu-id="2699f-146">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="2699f-147">Office 365, betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="2699f-147">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="2699f-148">Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="2699f-148">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="2699f-149">Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="2699f-149">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="2699f-150">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-150">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="2699f-151">Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2699f-151">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="2699f-152">Nach dem Herstellen der Verbindung können Sie die Cmdlets für das [Azure Active Directory PowerShell für Graph-Modul](/powershell/module/azuread) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2699f-152">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2699f-153">Herstellen einer Verbindung mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2699f-153">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="2699f-154">Die Cmdlets im Microsoft Azure Active Directory-Modul für Windows PowerShell weisen *Msol* in ihrem Namen auf.</span><span class="sxs-lookup"><span data-stu-id="2699f-154">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="2699f-155">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell 7 und höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2699f-155">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="2699f-156">Für PowerShell 7 oder höher müssen Sie das Azure Active Directory PowerShell für Graph-Modul oder Azure PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="2699f-156">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="2699f-157">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2699f-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="2699f-158">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-158">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="2699f-159">Schritt 1: Installieren der erforderlichen Software</span><span class="sxs-lookup"><span data-stu-id="2699f-159">Step 1: Install the required software</span></span>

<span data-ttu-id="2699f-160">Diese Schritte sind nur einmal auf Ihrem Computer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2699f-160">These steps are required only one time on your computer.</span></span> <span data-ttu-id="2699f-161">Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2699f-161">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="2699f-162">Wenn Sie nicht Windows 10 ausführen, installieren Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten: [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="2699f-162">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="2699f-163">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="2699f-163">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="2699f-164">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).</span><span class="sxs-lookup"><span data-stu-id="2699f-164">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="2699f-165">Führen Sie den Befehl **Install-Module MSOnline** aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-165">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="2699f-166">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="2699f-166">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="2699f-167">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="2699f-167">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="2699f-168">Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="2699f-168">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="2699f-p113">Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure AD herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).</span><span class="sxs-lookup"><span data-stu-id="2699f-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="2699f-171">Office 365-Cloud</span><span class="sxs-lookup"><span data-stu-id="2699f-171">Office 365 cloud</span></span> | <span data-ttu-id="2699f-172">Befehl</span><span class="sxs-lookup"><span data-stu-id="2699f-172">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="2699f-173">Office 365 weltweit (+GCC)</span><span class="sxs-lookup"><span data-stu-id="2699f-173">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="2699f-174">Office 365, betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="2699f-174">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="2699f-175">Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="2699f-175">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="2699f-176">Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="2699f-176">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="2699f-177">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-177">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="2699f-178">Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2699f-178">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="2699f-179">Woher wissen Sie, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="2699f-179">How do you know it worked?</span></span>

<span data-ttu-id="2699f-180">Wenn Sie keine Fehlermeldung erhalten, wurde die Verbindung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="2699f-180">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="2699f-181">Führen Sie für einen schnellen Test ein Microsoft 365-Cmdlet aus, z. B.  **Get-MsolUser**, und sehen Sie sich die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="2699f-181">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="2699f-182">Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="2699f-182">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="2699f-183">**Ein häufig auftretendes Problem ist ein falsches Kennwort**.</span><span class="sxs-lookup"><span data-stu-id="2699f-183">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="2699f-184">Führen Sie [Schritt 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) erneut aus, und achten Sie dabei auf die korrekte Eingabe des Benutzernamens und des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="2699f-184">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="2699f-185">**Das Microsoft Azure Active Directory-Modul für Windows PowerShell setzt voraus, dass Microsoft .NET Framework 3.5.* x* auf Ihrem Computer aktiviert ist**. Es ist wahrscheinlich, dass auf Ihrem Computer eine neuere Version installiert ist (z. B. Version 4 oder 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="2699f-185">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="2699f-186">Die Abwärtskompatibilität mit älteren Versionen von .NET Framework kann jedoch aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2699f-186">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="2699f-187">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="2699f-187">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="2699f-188">Informationen zu Windows Server 2012 oder Windows Server 2012 R2 finden Sie unter [Aktivieren von .NET Framework 3.5 mithilfe des Assistenten zum Hinzufügen von Rollen und Features](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="2699f-188">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="2699f-189">Informationen zu Windows 7 oder Windows Server 2008 R2 finden Sie unter[Das Azure Active Directory-Modul für Windows PowerShell kann nicht geöffnet werden](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="2699f-189">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="2699f-190">Informationen zu Windows 10, Windows 8.1 und Windows 8 finden Sie unter [Installieren von .NET Framework 3.5 unter Windows 10, Windows 8.1 und Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="2699f-190">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="2699f-191">**Möglicherweise ist Ihre Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell veraltet.**</span><span class="sxs-lookup"><span data-stu-id="2699f-191">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="2699f-192">Um dies zu überprüfen, führen Sie den folgenden Befehl in PowerShell für Microsoft 365 oder im Microsoft Azure Active Directory-Modul für Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="2699f-192">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="2699f-193">Wenn die zurückgegebene Versionsnummer niedriger als *1.0.8070.2* ist, deinstallieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell, und führen Sie die Installation über den vorstehenden [Schritt 1](#step-1-install-the-required-software) durch.</span><span class="sxs-lookup"><span data-stu-id="2699f-193">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="2699f-194">**Wenn Sie einen Verbindungsfehler erhalten**, finden Sie auf dieser Seite weitere Informationen: [Fehler "Connect-MsolService: Ausnahme vom Typ ausgelöst"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="2699f-194">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="2699f-195">**Wenn Sie einen "Get-Item: Pfad nicht gefunden"-Fehler erhalten**, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2699f-195">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a><span data-ttu-id="2699f-196">Mit Azure Cloud Shell verbinden</span><span class="sxs-lookup"><span data-stu-id="2699f-196">Connect with the Azure Cloud Shell</span></span>

<span data-ttu-id="2699f-197">Wählen Sie das PowerShell-Fenstersymbol in der oberen rechten Ecke der Taskleiste aus, damit Sie sich vom Microsoft 365 Admin Center aus mit Azure Cloud Shell verbinden können.</span><span class="sxs-lookup"><span data-stu-id="2699f-197">To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar.</span></span> <span data-ttu-id="2699f-198">Wählen Sie im Bereich “**Willkommen bei Azure Cloud Shell**“ “**PowerShell**“ aus.</span><span class="sxs-lookup"><span data-stu-id="2699f-198">In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.</span></span>

<span data-ttu-id="2699f-199">Sie benötigen ein aktives Azure-Abonnement für Ihre Organisation, das an Ihr Microsoft 365-Abonnement gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="2699f-199">You will need an active Azure subscription for your organization that is tied to your Microsoft 365 subscription.</span></span> <span data-ttu-id="2699f-200">Wenn Sie noch kein Abonnement haben, können Sie eins abschließen.</span><span class="sxs-lookup"><span data-stu-id="2699f-200">If you don't already have one, you can create one.</span></span> <span data-ttu-id="2699f-201">Sobald Sie ein Azure-Abonnement haben, wird ein PowerShell-Fenster geöffnet, in dem Sie PowerShell-Befehle und -Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="2699f-201">Once you have an Azure subscription, a PowerShell window opens from which you can run PowerShell commands and scripts.</span></span>

<span data-ttu-id="2699f-202">Weitere Informationen finden Sie unter “[Azure Cloud Shell](/azure/cloud-shell/overview)“.</span><span class="sxs-lookup"><span data-stu-id="2699f-202">For more information, see [Azure Cloud Shell](/azure/cloud-shell/overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="2699f-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2699f-203">See also</span></span>

- [<span data-ttu-id="2699f-204">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="2699f-204">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2699f-205">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2699f-205">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2699f-206">Verbinden mit allen Microsoft 365-Diensten in einem einzigen Windows PowerShell-Fenster</span><span class="sxs-lookup"><span data-stu-id="2699f-206">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
