---
title: Verbinden mit Microsoft 365 über PowerShell
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
description: Stellen Sie eine Verbindung mit Ihrem Microsoft 365-Mandanten mithilfe von PowerShell für Microsoft 365 her, um Admin Center-Aufgaben über die Befehlszeile auszuführen.
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782801"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="13110-103">Verbinden mit Microsoft 365 über PowerShell</span><span class="sxs-lookup"><span data-stu-id="13110-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="13110-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="13110-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="13110-105">Mit PowerShell für Microsoft 365 können Sie Ihre Microsoft 365-Einstellungen über die Befehlszeile verwalten.</span><span class="sxs-lookup"><span data-stu-id="13110-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="13110-106">Um eine Verbindung mit PowerShell herzustellen, installieren Sie einfach die erforderliche Software, und stellen Sie eine Verbindung mit Ihrer Microsoft 365-Organisation her.</span><span class="sxs-lookup"><span data-stu-id="13110-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="13110-107">Es gibt zwei Versionen des PowerShell-Moduls, mit denen Sie die Verbindung zu Microsoft 365 herstellen und Benutzerkonten, Gruppen und Lizenzen verwalten können:</span><span class="sxs-lookup"><span data-stu-id="13110-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="13110-108">Azure Active Directory-PowerShell für Graph, dessen Cmdlets *AzureAD* in ihrem Namen enthalten</span><span class="sxs-lookup"><span data-stu-id="13110-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="13110-109">Microsoft Azure Active Directory-Modul für Windows PowerShell, dessen Cmdlets *MSol* in ihrem Namen enthalten</span><span class="sxs-lookup"><span data-stu-id="13110-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="13110-110">Zurzeit ersetzt das Modul „Azure Active Directory-PowerShell für Graph“ die Funktionen des Moduls „Microsoft Azure Active Directory-Modul für Windows PowerShell“ für Benutzer-, Gruppen- und Lizenzverwaltung nicht vollständig.</span><span class="sxs-lookup"><span data-stu-id="13110-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="13110-111">In einigen Fällen müssen Sie beide Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="13110-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="13110-112">Sie können problemlos beide Versionen auf demselben Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="13110-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="13110-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="13110-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="13110-114">**Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="13110-114">**Operating system**</span></span>

<span data-ttu-id="13110-p103">Sie müssen eine 64-Bit-Version von Windows verwenden. Die Unterstützung für die 32-Bit-Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell wurde 2014 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="13110-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="13110-117">Sie können folgende Versionen von Windows verwenden:</span><span class="sxs-lookup"><span data-stu-id="13110-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="13110-118">Windows 10, Windows 8.1, Windows 8 oder Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="13110-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="13110-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="13110-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="13110-120">Für Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 SP1 laden Sie [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) herunter. und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="13110-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="13110-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="13110-121">**PowerShell**</span></span>

- <span data-ttu-id="13110-122">Für das Azure Active Directory PowerShell für Graph-Modul müssen Sie PowerShell 5.1 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="13110-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="13110-p104">Für das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul müssen Sie PowerShell 5.1 oder höher bis zu PowerShell 6 verwenden. PowerShell 7 kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13110-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="13110-125">Diese Verfahren sind für Benutzer vorgesehen, die Mitglieder einer Microsoft 365-Administratorrolle sind.</span><span class="sxs-lookup"><span data-stu-id="13110-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="13110-126">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="13110-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="13110-127">Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="13110-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="13110-128">Befehle im Azure Active Directory PowerShell für Graph-Modul haben *AzureAD* in ihrem Cmdlet-Namen.</span><span class="sxs-lookup"><span data-stu-id="13110-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="13110-129">Sie können das [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2)-Modul oder [Azure PowerShell](/powershell/azure/install-az-ps) installieren.</span><span class="sxs-lookup"><span data-stu-id="13110-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="13110-130">Führen Sie bei Verfahren, die die neuen Cmdlets im Azure Active Directory PowerShell für Graph-Modul erfordern, die nachstehenden Schritte zum Installieren des Moduls und Herstellen einer Verbindung mit Ihrem Microsoft 365-Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="13110-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="13110-131">Informationen zur Unterstützung für verschiedene Versionen von Windows finden Sie unter [Azure Active Directory PowerShell für Graph-Modul](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="13110-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="13110-132">Schritt 1: Installieren der erforderlichen Software</span><span class="sxs-lookup"><span data-stu-id="13110-132">Step 1: Install the required software</span></span>

<span data-ttu-id="13110-133">Diese Schritte sind nur einmal auf Ihrem Computer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13110-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="13110-134">Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="13110-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="13110-135">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).</span><span class="sxs-lookup"><span data-stu-id="13110-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="13110-136">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="13110-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="13110-137">Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="13110-137">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="13110-138">Bei der ersten Verwendung der PSGallery wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="13110-138">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="13110-139">Antworten Sie mit **Ja** oder **Ja für alle**, um mit der Installation fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="13110-139">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="13110-140">Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="13110-140">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="13110-p109">Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure Active Directory (Azure AD) herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).</span><span class="sxs-lookup"><span data-stu-id="13110-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="13110-143">Office 365-Cloud</span><span class="sxs-lookup"><span data-stu-id="13110-143">Office 365 cloud</span></span> | <span data-ttu-id="13110-144">Befehl</span><span class="sxs-lookup"><span data-stu-id="13110-144">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="13110-145">Office 365 weltweit (+GCC)</span><span class="sxs-lookup"><span data-stu-id="13110-145">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="13110-146">Office 365, betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="13110-146">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="13110-147">Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="13110-147">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="13110-148">Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="13110-148">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="13110-149">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="13110-149">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="13110-150">Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="13110-150">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="13110-151">Nach dem Herstellen der Verbindung können Sie die Cmdlets für das [Azure Active Directory PowerShell für Graph-Modul](/powershell/module/azuread) verwenden.</span><span class="sxs-lookup"><span data-stu-id="13110-151">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="13110-152">Herstellen einer Verbindung mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13110-152">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="13110-153">Die Cmdlets im Microsoft Azure Active Directory-Modul für Windows PowerShell weisen *Msol* in ihrem Namen auf.</span><span class="sxs-lookup"><span data-stu-id="13110-153">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="13110-154">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell 7 und höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13110-154">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="13110-155">Für PowerShell 7 oder höher müssen Sie das Azure Active Directory PowerShell für Graph-Modul oder Azure PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="13110-155">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="13110-156">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13110-156">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="13110-157">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="13110-157">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="13110-158">Schritt 1: Installieren der erforderlichen Software</span><span class="sxs-lookup"><span data-stu-id="13110-158">Step 1: Install the required software</span></span>

<span data-ttu-id="13110-159">Diese Schritte sind nur einmal auf Ihrem Computer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13110-159">These steps are required only one time on your computer.</span></span> <span data-ttu-id="13110-160">Sie müssen die Software aber wahrscheinlich regelmäßig aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="13110-160">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="13110-161">Wenn Sie nicht Windows 10 ausführen, installieren Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten: [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="13110-161">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="13110-162">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="13110-162">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="13110-163">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung mit erhöhten Rechten (d. h., führen Sie Windows PowerShell als Administrator aus).</span><span class="sxs-lookup"><span data-stu-id="13110-163">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="13110-164">Führen Sie den Befehl **Install-Module MSOnline** aus.</span><span class="sxs-lookup"><span data-stu-id="13110-164">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="13110-165">Wenn Sie zum Installieren des NuGet-Anbieters aufgefordert werden, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="13110-165">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="13110-166">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="13110-166">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="13110-167">Schritt 2: Herstellen einer Verbindung mit Azure AD für Ihr Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="13110-167">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="13110-p113">Wenn Sie für Ihr Microsoft 365-Abonnement mit einem Kontonamen und Kennwort oder mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eine Verbindung mit Azure AD herstellen möchten, führen Sie einen der folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung aus (sie muss nicht über erhöhte Rechte verfügen).</span><span class="sxs-lookup"><span data-stu-id="13110-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="13110-170">Office 365-Cloud</span><span class="sxs-lookup"><span data-stu-id="13110-170">Office 365 cloud</span></span> | <span data-ttu-id="13110-171">Befehl</span><span class="sxs-lookup"><span data-stu-id="13110-171">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="13110-172">Office 365 weltweit (+GCC)</span><span class="sxs-lookup"><span data-stu-id="13110-172">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="13110-173">Office 365, betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="13110-173">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="13110-174">Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="13110-174">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="13110-175">Office 365 U.S. Government DoD und Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="13110-175">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="13110-176">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort für Ihr Microsoft 365-Geschäfts-, Schul- oder Unikonto ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="13110-176">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="13110-177">Wenn Sie die mehrstufige Authentifizierung verwenden, folgen Sie den Anweisungen, um zusätzliche Authentifizierungsinformationen, z. B. einen Überprüfungscode, anzugeben.</span><span class="sxs-lookup"><span data-stu-id="13110-177">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="13110-178">Woher wissen Sie, dass der Vorgang erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="13110-178">How do you know it worked?</span></span>

<span data-ttu-id="13110-179">Wenn Sie keine Fehlermeldung erhalten, wurde die Verbindung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="13110-179">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="13110-180">Führen Sie für einen schnellen Test ein Microsoft 365-Cmdlet aus, z. B.  **Get-MsolUser**, und sehen Sie sich die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="13110-180">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="13110-181">Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="13110-181">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="13110-182">**Ein häufig auftretendes Problem ist ein falsches Kennwort**.</span><span class="sxs-lookup"><span data-stu-id="13110-182">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="13110-183">Führen Sie [Schritt 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) erneut aus, und achten Sie dabei auf die korrekte Eingabe des Benutzernamens und des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="13110-183">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="13110-184">**Das Microsoft Azure Active Directory-Modul für Windows PowerShell setzt voraus, dass Microsoft .NET Framework 3.5.* x* auf Ihrem Computer aktiviert ist**. Es ist wahrscheinlich, dass auf Ihrem Computer eine neuere Version installiert ist (z. B. Version 4 oder 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="13110-184">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="13110-185">Die Abwärtskompatibilität mit älteren Versionen von .NET Framework kann jedoch aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="13110-185">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="13110-186">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="13110-186">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="13110-187">Informationen zu Windows Server 2012 oder Windows Server 2012 R2 finden Sie unter [Aktivieren von .NET Framework 3.5 mithilfe des Assistenten zum Hinzufügen von Rollen und Features](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="13110-187">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="13110-188">Informationen zu Windows 7 oder Windows Server 2008 R2 finden Sie unter[Das Azure Active Directory-Modul für Windows PowerShell kann nicht geöffnet werden](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="13110-188">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="13110-189">Informationen zu Windows 10, Windows 8.1 und Windows 8 finden Sie unter [Installieren von .NET Framework 3.5 unter Windows 10, Windows 8.1 und Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="13110-189">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="13110-190">**Möglicherweise ist Ihre Version des Microsoft Azure Active Directory-Moduls für Windows PowerShell veraltet.**</span><span class="sxs-lookup"><span data-stu-id="13110-190">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="13110-191">Um dies zu überprüfen, führen Sie den folgenden Befehl in PowerShell für Microsoft 365 oder im Microsoft Azure Active Directory-Modul für Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="13110-191">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="13110-192">Wenn die zurückgegebene Versionsnummer niedriger als *1.0.8070.2* ist, deinstallieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell, und führen Sie die Installation über den vorstehenden [Schritt 1](#step-1-install-the-required-software) durch.</span><span class="sxs-lookup"><span data-stu-id="13110-192">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="13110-193">**Wenn Sie einen Verbindungsfehler erhalten**, finden Sie auf dieser Seite weitere Informationen: [Fehler "Connect-MsolService: Ausnahme vom Typ ausgelöst"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="13110-193">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="13110-194">**Wenn Sie einen "Get-Item: Pfad nicht gefunden"-Fehler erhalten**, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="13110-194">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="13110-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13110-195">See also</span></span>

- [<span data-ttu-id="13110-196">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="13110-196">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="13110-197">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13110-197">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="13110-198">Verbinden mit allen Microsoft 365-Diensten in einem einzigen Windows PowerShell-Fenster</span><span class="sxs-lookup"><span data-stu-id="13110-198">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
