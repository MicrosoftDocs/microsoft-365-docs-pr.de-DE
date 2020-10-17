---
title: Einfache Standardkonfiguration
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Test Umgebungs Anleitung zum Erstellen einer einfachen Testumgebung zum Testen von Microsoft 365 für Unternehmen.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487388"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="d4814-103">Die einfache Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d4814-103">The lightweight base configuration</span></span>

<span data-ttu-id="d4814-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d4814-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d4814-105">In diesem Artikel wird beschrieben, wie eine vereinfachte Umgebung mit einem Microsoft 365 E5-Abonnement und einem Computer mit Windows 10 Enterprise erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4814-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="d4814-107">Das Erstellen einer einfachen Testumgebung umfasst fünf Phasen:</span><span class="sxs-lookup"><span data-stu-id="d4814-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="d4814-108">Phase 1: Erstellen Ihres Microsoft 365 E5-Abonnements</span><span class="sxs-lookup"><span data-stu-id="d4814-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="d4814-109">Phase 2: Konfigurieren des Office 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="d4814-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="d4814-110">Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d4814-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="d4814-111">Phase 4: Erstellen eines Computers mit Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4814-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="d4814-112">Phase 5: Einbinden des Windows 10-Computers in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4814-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="d4814-113">Verwenden Sie die resultierende Umgebung, um die Features und Funktionen von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)zu testen.</span><span class="sxs-lookup"><span data-stu-id="d4814-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="d4814-115">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d4814-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="d4814-116">Sie können diesen Artikel auch ausdrucken, um die speziellen Informationen zu notieren, die Sie für diese Umgebung in den kommenden 30 Tage des Office 365-Testabonnements benötigen.</span><span class="sxs-lookup"><span data-stu-id="d4814-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="d4814-117">Sie können das Testabonnement einfach um weitere 30 Tage verlängern.</span><span class="sxs-lookup"><span data-stu-id="d4814-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="d4814-118">Für eine dauerhafte Testumgebung erstellen Sie ein neues bezahltes Abonnement mit einem separaten Azure AD-Mandanten und einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="d4814-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="d4814-119">Phase 1: Erstellen Ihres Microsoft 365 E5-Abonnements</span><span class="sxs-lookup"><span data-stu-id="d4814-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="d4814-120">Wir beginnen mit einem Microsoft 365 E5-Testabonnement und fügen dann das Microsoft 365 E5-Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4814-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="d4814-121">Es wird empfohlen, ein Testabonnement für Office 365 zu erstellen, damit Ihre Testumgebung über einen separaten Azure AD Mandanten von beliebigen bezahlten Abonnements verfügt, die Sie derzeit haben.</span><span class="sxs-lookup"><span data-stu-id="d4814-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="d4814-122">Diese Trennung bedeutet, dass Sie Benutzer und Gruppen im Testmandanten hinzufügen und entfernen können, ohne dass sich dies auf Ihre Produktions Abonnements auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d4814-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="d4814-123">Für das Microsoft 365 E5-Testabonnement benötigen Sie zunächst einen fiktiven Unternehmensnamen und ein neues Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="d4814-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="d4814-p103">Es wird empfohlen, eine Variante von „Contoso“ als Unternehmensnamen zu verwenden. Dies ist ein fiktives Unternehmen, das von Microsoft in Beispielen verwendet wird. Notieren Sie hier Ihren fiktiven Unternehmensnamen: .</span><span class="sxs-lookup"><span data-stu-id="d4814-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![Zeile](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="d4814-p104">Wenn Sie sich für ein neues Microsoft-Konto registrieren möchten, wechseln Sie zu [https://outlook.com](https://outlook.com), und erstellen Sie ein Konto mit neuem E-Mail-Konto und neuer E-Mail-Adresse. Dieses Konto wird für die Registrierung für Office 365 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4814-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="d4814-129">Notieren Sie hier den Vor- und Nachnamen des Kontos: </span><span class="sxs-lookup"><span data-stu-id="d4814-129">Record the first and last name of your new account here:</span></span> ![Zeile](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="d4814-131">Notieren Sie hier die neue E-Mail-Kontoadresse:</span><span class="sxs-lookup"><span data-stu-id="d4814-131">Record the new email account address here:</span></span> ![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="d4814-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="d4814-134">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="d4814-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="d4814-135">Wechseln Sie in Ihrem Browser zu [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="d4814-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="d4814-136">Geben Sie in Schritt 1 der Seite **Danke für die Auswahl Office 365 E5** Ihre neue e-Mail-Kontoadresse ein.</span><span class="sxs-lookup"><span data-stu-id="d4814-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="d4814-137">Geben Sie in Schritt 2 des Trail-Abonnementprozesses die angeforderten Informationen ein, und führen Sie dann die Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="d4814-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="d4814-138">Geben Sie in Schritt 3 einen Organisationsnamen und dann einen Kontonamen ein, der als globaler Administrator für das Abonnement verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4814-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="d4814-139">Notieren Sie hier für Schritt 4 die Anmeldeseite (auswählen und kopieren):</span><span class="sxs-lookup"><span data-stu-id="d4814-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Zeile](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="d4814-141">Notieren Sie hier die Benutzer-ID: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d4814-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="d4814-142">Notieren Sie sich das Kennwort, das Sie an einem sicheren Ort eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="d4814-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="d4814-143">Dieser Wert wird **Name des globalen Administrators** genannt.</span><span class="sxs-lookup"><span data-stu-id="d4814-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="d4814-144">Wählen Sie **Gehe zu Setup**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="d4814-145">Wählen Sie in Office 365 E5 **-Setup *die Option Organization*. onmicrosoft.com für e-Mail und Anmeldung weiter verwenden**aus, und wählen Sie dann **beenden und später fortfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="d4814-146">Das Microsoft 365 Admin Center sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4814-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="d4814-147">Phase 2: Konfigurieren des Office 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="d4814-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="d4814-148">In dieser Phase konfigurieren Sie Ihr Abonnement mit weiteren Benutzern und weisen diesen Office 365 E5-Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="d4814-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="d4814-149">Verwenden Sie die Anweisungen unter [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module), um eine Verbindung zu Ihrem Abonnement mit dem Azure Active Directory PowerShell for Graph-Modul von Ihrem Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d4814-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="d4814-150">Geben Sie im Dialogfeld **Windows PowerShell Anmeldeinformationen** den globalen Administratornamen ein (beispielsweise *jdoe@contosotoycompany.onmicrosoft.com*) und das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="d4814-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="d4814-151">Geben Sie den Namen Ihrer Organisation ein (beispielsweise *contosotoycompany*), den zweistelligen Ländercode für Ihren Standort, ein gemeinsames Kontokennwort, und führen Sie dann die folgenden Befehle an der PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="d4814-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="d4814-152">Für die Automatisierung und Vereinfachung der Konfiguration einer Testumgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4814-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="d4814-153">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="d4814-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="d4814-154">Aufzeichnen von Schlüsselinformationen für spätere Verweise</span><span class="sxs-lookup"><span data-stu-id="d4814-154">Record key information for future reference</span></span>

<span data-ttu-id="d4814-155">Wenn Sie diese Werte noch nicht aufgezeichnet haben, notieren Sie Sie jetzt:</span><span class="sxs-lookup"><span data-stu-id="d4814-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="d4814-156">Globaler Administratorname:</span><span class="sxs-lookup"><span data-stu-id="d4814-156">Global administrator name:</span></span> ![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-158">.onmicrosoft.com (aus Schritt 6 von Phase 1)</span><span class="sxs-lookup"><span data-stu-id="d4814-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="d4814-159">Notieren Sie auch das Kennwort für dieses Konto, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="d4814-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="d4814-160">Organisationsname für das Testabonnement:</span><span class="sxs-lookup"><span data-stu-id="d4814-160">Your trial subscription organization name:</span></span> ![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="d4814-162">(aus Schritt 4 von Phase 1)</span><span class="sxs-lookup"><span data-stu-id="d4814-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="d4814-163">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung den folgenden Befehl aus, um die Konten für Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5 anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d4814-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="d4814-164">Notieren Sie hier die Kontonamen:</span><span class="sxs-lookup"><span data-stu-id="d4814-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="d4814-165">Benutzer 2 Kontoname: user2@</span><span class="sxs-lookup"><span data-stu-id="d4814-165">User 2 account name: user2@</span></span>![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d4814-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="d4814-168">Benutzer 3 Kontoname: user3@</span><span class="sxs-lookup"><span data-stu-id="d4814-168">User 3 account name: user3@</span></span>![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d4814-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="d4814-171">Benutzer 4 Kontoname: user4@</span><span class="sxs-lookup"><span data-stu-id="d4814-171">User 4 account name: user4@</span></span>![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d4814-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="d4814-174">Benutzer 5 Kontoname: user5@</span><span class="sxs-lookup"><span data-stu-id="d4814-174">User 5 account name: user5@</span></span>![Zeile](../media/Common-Images/TableLine.png)<span data-ttu-id="d4814-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d4814-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="d4814-177">Notieren Sie auch das gemeinsame Kennwort für diese Konten, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="d4814-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="d4814-178">Verwenden einer Office 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d4814-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="d4814-179">Wenn Sie nur eine Office 365 Testumgebung benötigen, müssen Sie den Rest dieses Artikels nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="d4814-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="d4814-180">Weitere testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="d4814-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="d4814-181">Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d4814-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="d4814-182">In dieser Phase registrieren Sie sich für das Microsoft 365 E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4814-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="d4814-183">Fügen Sie zuerst das Testabonnement für Microsoft 365 E5 hinzu, und weisen Sie ihrem globalen Administratorkonto die neue Microsoft 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="d4814-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="d4814-184">Verwenden Sie in einem privaten Internet Browser-Fenster Ihre Anmeldeinformationen für das globale Administratorkonto, um sich beim Microsoft 365 Admin Center unter anzumelden [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="d4814-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="d4814-185">Wählen Sie auf der Seite **Microsoft 365 Admin Center** im linken Navigations **Bereich Abrechnungs > Dienste kaufen**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="d4814-186">Wählen Sie auf der Seite " **Dienste kaufen** " **Microsoft 365 E5**aus, und wählen Sie dann **﻿Kostenlose Testversion abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="d4814-187">Entscheiden Sie auf der **Microsoft 365 E5-Testseite** , eine Textnachricht oder einen Anruf zu erhalten, geben Sie Ihre Telefonnummer ein, und wählen Sie dann **Text mich** oder **rufen Sie mich**an.</span><span class="sxs-lookup"><span data-stu-id="d4814-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="d4814-188">Führen Sie eine Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="d4814-188">Perform the verification.</span></span>

5. <span data-ttu-id="d4814-189">Wählen Sie auf der Seite **Bestätigung Ihrer Bestellung** die Option **jetzt testen**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="d4814-190">Wählen Sie auf der Seite **Bestellbestätigung** die Option **Continue**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="d4814-191">Wählen Sie im Microsoft 365 Admin Center die Option **Benutzer > aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="d4814-192">Wählen Sie unter **aktive Benutzer**Ihr Administratorkonto aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="d4814-193">Wählen Sie **Lizenzen und apps**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="d4814-194">Deaktivieren Sie die Lizenz für Office 365 Enterprise E5 und aktivieren Sie die Lizenz für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d4814-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="d4814-195">Wählen Sie **Änderungen speichern**aus, und schließen Sie dann den Bereich Benutzerkontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="d4814-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="d4814-196">Wiederholen Sie dann die Schritte 8 bis 11 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).</span><span class="sxs-lookup"><span data-stu-id="d4814-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4814-197">Die Länge des Microsoft 365 E5-Testabonnements beträgt 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="d4814-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="d4814-198">Ändern Sie für eine dauerhafte Testumgebung dieses Testabonnement in ein kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="d4814-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="d4814-199">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d4814-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="d4814-200">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d4814-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="d4814-201">Alle Ihre entsprechenden Benutzerkonten (entweder nur der globale Administrator oder alle fünf Benutzerkonten) können Microsoft 365 E5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4814-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="d4814-202">Die resultierende Konfiguration, die Microsoft 365 E5 hinzufügt, sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d4814-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Phase 3 der Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="d4814-204">Phase 4: Erstellen eines Computers mit Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4814-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="d4814-205">In dieser Phase erstellen Sie einen eigenständigen Computer unter Windows 10 Enterprise entweder als physischen Computer, als virtuellen Computer oder als virtuellen Azure-Computer.</span><span class="sxs-lookup"><span data-stu-id="d4814-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="d4814-206">Physischer Computer</span><span class="sxs-lookup"><span data-stu-id="d4814-206">Physical computer</span></span>

<span data-ttu-id="d4814-207">Installieren Sie auf einem PC Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d4814-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="d4814-208">Sie können die Windows 10 Enterprise-Testversion [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d4814-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="d4814-209">Virtueller Computer</span><span class="sxs-lookup"><span data-stu-id="d4814-209">Virtual machine</span></span>

<span data-ttu-id="d4814-210">Verwenden Sie zum Erstellen eines virtuellen Computers den Hypervisor Ihrer Wahl, und installieren Sie dann Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d4814-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="d4814-211">Sie können die Windows 10 Enterprise-Testversion [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d4814-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="d4814-212">Virtueller Computer in Azure</span><span class="sxs-lookup"><span data-stu-id="d4814-212">Virtual machine in Azure</span></span>

<span data-ttu-id="d4814-p111">Zum Erstellen eines virtuellen Computers mit Windows 10 in Microsoft Azure ***benötigen Sie ein Visual Studio-basiertes Abonnement***, das Zugriff auf das Image für Windows 10 Enterprise hat. Andere Arten von Azure-Abonnements, wie z. B. Testabonnements und kostenpflichtige Abonnements, haben keinen Zugriff auf dieses Image. Die neuesten Informationen finden Sie unter [Verwenden des Windows-Clients in Azure für Entwicklungs-/Testszenarien](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="d4814-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4814-216">[!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4814-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="d4814-217">Informationen dazu finden Sie unter [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="d4814-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="d4814-218">Mit diesen Befehlssätzen werden ein virtueller Windows 10 Enterprise-Computer mit dem Namen „WIN10“ hat sowie die gesamte erforderliche Infrastruktur, einschließlich einer Ressourcengruppe, eines Speicherkontos und eines virtuellen Netzwerks erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4814-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="d4814-219">Wenn Sie bereits mit Azure-Infrastrukturdiensten vertraut sind, passen Sie diese Anweisungen entsprechend ihrer derzeit bereitgestellten Infrastruktur an.</span><span class="sxs-lookup"><span data-stu-id="d4814-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="d4814-220">Starten Sie zuerst eine Microsoft PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="d4814-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="d4814-221">Melden Sie sich bei Ihrem Azure-Konto mit diesem Befehl an.</span><span class="sxs-lookup"><span data-stu-id="d4814-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="d4814-222">Rufen Sie Ihren Abonnement Namen mit diesem Befehl ab.</span><span class="sxs-lookup"><span data-stu-id="d4814-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="d4814-223">Tragen Sie Ihr Azure-Abonnement ein.</span><span class="sxs-lookup"><span data-stu-id="d4814-223">Set your Azure subscription.</span></span> <span data-ttu-id="d4814-224">Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der \< and > Zeichen, durch den korrekten Namen.</span><span class="sxs-lookup"><span data-stu-id="d4814-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="d4814-225">Im nächsten Schritt wird eine neue Ressourcengruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4814-225">Next, create a new resource group.</span></span> <span data-ttu-id="d4814-226">Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d4814-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="d4814-227">Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="d4814-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="d4814-228">Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der \< and > Zeichen, durch die richtigen Namen.</span><span class="sxs-lookup"><span data-stu-id="d4814-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="d4814-229">Erstellen Sie als nächstes ein neues virtuelles Netzwerk und den virtuellen WIN10-Computer mit diesen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="d4814-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="d4814-230">Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort des lokalen Administratorkontos für WIN10 an, und bewahren Sie dieses an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="d4814-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="d4814-231">Phase 5: Einbinden des Windows 10-Computers in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4814-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="d4814-232">Nachdem Sie den physischen oder virtuellen Computer mit Windows 10 Enterprise erstellt haben, melden Sie sich mit einem lokalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="d4814-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4814-233">Verwenden Sie für einen virtuellen Computer in Azure  [diese Anweisungen](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) , um eine Verbindung mit diesem herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d4814-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="d4814-234">Als Nächstes fügen Sie den WIN10-Computer dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4814-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="d4814-235">Wählen Sie auf dem Desktop des WIN10-Computers **> Einstellungen > Konten > Access work oder School > Connect**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="d4814-236">Wählen Sie im Dialogfeld **Arbeits-oder Schulkonto einrichten** die Option **diesem Gerät mit Azure Active Directory beitreten**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="d4814-237">Geben Sie im **Arbeits-oder Schulkonto**den Namen des globalen Administratorkontos Ihres Microsoft 365 E5-Abonnements ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="d4814-238">Geben Sie unter **Kennwort eingeben**das Kennwort für Ihr globales Administratorkonto ein, und wählen Sie dann **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="d4814-239">Wenn Sie aufgefordert werden, sicherzustellen, dass es sich um Ihre Organisation handelt, wählen Sie **beitreten**aus, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d4814-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="d4814-240">Schließen Sie das Fenster mit den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d4814-240">Close the settings window.</span></span>
    
<span data-ttu-id="d4814-241">Installieren Sie als nächstes Microsoft 365-Apps für Enterprise auf dem WIN10-Computer:</span><span class="sxs-lookup"><span data-stu-id="d4814-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="d4814-242">Öffnen Sie den Microsoft-Edge-Browser, und melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen für das globale Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="d4814-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="d4814-243">Wählen Sie auf der Registerkarte **Microsoft Office Startseite** die Option **Office installieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="d4814-244">Wenn Sie dazu aufgefordert werden, wählen Sie **Ausführen**aus, und wählen Sie dann **Ja** für die **Benutzerkontensteuerung**aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="d4814-245">Warten Sie, bis Office die Installation beendet hat.</span><span class="sxs-lookup"><span data-stu-id="d4814-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="d4814-246">Wenn Sie sehen, dass **Sie alle festgelegt haben**, wählen Sie **Schließen** zweimal aus.</span><span class="sxs-lookup"><span data-stu-id="d4814-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="d4814-247">Die resultierende Umgebung sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d4814-247">Your resulting environment looks like this:</span></span>

![Phase 5 der Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="d4814-249">Dies schließt den WIN10-Computer mit ein:</span><span class="sxs-lookup"><span data-stu-id="d4814-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="d4814-250">Er wurde dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d4814-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="d4814-251">Er wurde als Azure AD-Gerät in Microsoft Intune (EMS) registriert.</span><span class="sxs-lookup"><span data-stu-id="d4814-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="d4814-252">Microsoft 365-Apps für Enterprise installiert.</span><span class="sxs-lookup"><span data-stu-id="d4814-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="d4814-253">Sie können nun mit weiteren Features von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)experimentieren.</span><span class="sxs-lookup"><span data-stu-id="d4814-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d4814-254">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d4814-254">Next steps</span></span>

<span data-ttu-id="d4814-255">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="d4814-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="d4814-256">Identität</span><span class="sxs-lookup"><span data-stu-id="d4814-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="d4814-257">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="d4814-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="d4814-258">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="d4814-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="d4814-259">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4814-259">See also</span></span>

[<span data-ttu-id="d4814-260">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4814-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d4814-261">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4814-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d4814-262">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d4814-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
