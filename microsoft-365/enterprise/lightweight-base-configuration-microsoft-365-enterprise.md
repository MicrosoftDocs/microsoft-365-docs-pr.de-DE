---
title: Einfache Standardkonfiguration
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Tetstumgebungsanleitung zum Erstellen einer einfachen Testumgebung für das Testen von Microsoft 365 Enterprise.
ms.openlocfilehash: 0bbb54ca054ce1f4f96a32c887fba60b982375de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801650"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="3b4bb-103">Die einfache Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3b4bb-103">The lightweight base configuration</span></span>

<span data-ttu-id="3b4bb-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="3b4bb-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3b4bb-105">In diesem Artikel erhalten Sie Schritt-für-Schritt-Anweisungen zum Erstellen einer vereinfachten Umgebung die ein Microsoft 365 E5-Abonnement und einen Computer mit Windows 10 Enterprise umfasst.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Einfache Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="3b4bb-107">Verwenden die resultierende Umgebung zum Testen der Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="3b4bb-109">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-109">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="3b4bb-110">Phase 1: Erstellen des Office 365 E5-Abonnements</span><span class="sxs-lookup"><span data-stu-id="3b4bb-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="3b4bb-111">Wir beginnen mit einem Office 365 E5-Testabonnement und fügen dann das Microsoft 365 E5-Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="3b4bb-112">Für das Office 365 E5-Testabonnement benötigen Sie zunächst einen fiktiven Unternehmensnamen und ein neues Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="3b4bb-p101">Es wird empfohlen, eine Variante von „Contoso“ als Unternehmensnamen zu verwenden. Dies ist ein fiktives Unternehmen, das von Microsoft in Beispielen verwendet wird. Notieren Sie hier Ihren fiktiven Unternehmensnamen: .</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![Zeile](./media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="3b4bb-p102">Wenn Sie sich für ein neues Microsoft-Konto registrieren möchten, wechseln Sie zu [https://outlook.com](https://outlook.com), und erstellen Sie ein Konto mit neuem E-Mail-Konto und neuer E-Mail-Adresse. Dieses Konto wird für die Registrierung für Office 365 verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="3b4bb-118">Notieren Sie hier den Vor- und Nachnamen des Kontos: </span><span class="sxs-lookup"><span data-stu-id="3b4bb-118">Record the first and last name of your new account here:</span></span> ![Zeile](./media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="3b4bb-120">Notieren Sie hier die neue E-Mail-Kontoadresse:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-120">Record the new email account address here:</span></span> ![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-122">Outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="3b4bb-123">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="3b4bb-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="3b4bb-124">Öffnen Sie den Internetbrowser auf Ihrem Computer, und navigieren Sie zu [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="3b4bb-125">Geben Sie auf der Seite **Vielen Dank, dass Sie sich für Office 365 E5 entschieden haben** in Schritt 1 die Adresse Ihres neuen E-Mail-Kontos an.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="3b4bb-126">Geben Sie in Schritt 2 des Testabonnementprozesses die gewünschten Informationen ein, und führen Sie dann die Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="3b4bb-127">Geben Sie in Schritt 3 einen Organisationsnamen ein und dann einen Kontonamen, der als globaler Administrator für das Abonnement verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="3b4bb-128">Notieren Sie hier für Schritt 4 die Anmeldeseite (auswählen und kopieren):</span><span class="sxs-lookup"><span data-stu-id="3b4bb-128">For step 4, record the sign-in page here (select and copy):</span></span> ![Zeile](./media/Common-Images/TableLine.png) 
6. <span data-ttu-id="3b4bb-130">Notieren Sie hier die Benutzer-ID: ![Line](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-130">Record the user ID here: ![.onmicrosoft.com</span></span>  
   <span data-ttu-id="3b4bb-131">Notieren Sie das verwendete Kennwort, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="3b4bb-132">Dieser Wert wird **Name des globalen Office 365-Administrators** genannt.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-132">This value will be referred to as the **Office 365 global administrator name**.</span></span>
8. <span data-ttu-id="3b4bb-133">Klicken Sie auf **Zu Setup wechseln**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="3b4bb-134">Klicken Sie im Office 365 E5-Setup auf **Verwenden Sie *Ihre Organisation*.onmicrosoft.com weiter für E-Mails und die Anmeldung**, und klicken Sie dann auf **Beenden und zu einem späteren Zeitpunkt fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="3b4bb-135">Das Microsoft 365 Admin Center sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="3b4bb-136">Dann fordern wir Sie dazu auf, ein Office 365-Testabonnement zu erstellen, damit Ihre Testumgebung über einen separaten Azure AD-Mandanten verfügt, der getrennt ist von allen kostenpflichtigen Abonnements, die Sie aktuell haben.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="3b4bb-137">Diese Trennung bedeutet, dass Sie Benutzer zum Testmandanten hinzufügen und entfernen können, ohne dass dies Auswirkungen auf Ihre Produktionsabonnements hat.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="3b4bb-138">Phase 2: Konfigurieren des Office 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="3b4bb-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="3b4bb-139">In dieser Phase konfigurieren Sie Ihr Office 365-Abonnement mit weiteren Benutzern und weisen diesen Office 365 E5-Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-139">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="3b4bb-140">Befolgen Sie die Anweisungen unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), um Ihr Office 365-Abonnement von Ihrem Computer aus mit dem Azure Active Directory PowerShell-Modul für Graph zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="3b4bb-141">Geben Sie in das Dialogfeld **Windows PowerShell Credential Request** den Namen des globalen Office 365-Administrators (z. B. "jdoe@contosotoycompany.onmicrosoft.com") und sein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-141">In the **Windows PowerShell Credential Request** dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="3b4bb-142">Geben Sie den Namen Ihrer Organisation (z. B. „contosotoycompany“), den zweistelligen Ländercode für Ihren Standort und ein gemeinsames Kontokennwort ein, und führen Sie dann die folgenden Befehle von der PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="3b4bb-143">Für die Automatisierung und Vereinfachung der Konfiguration einer Testumgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="3b4bb-144">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="3b4bb-145">Aufzeichnen von Schlüsselinformationen für spätere Verweise</span><span class="sxs-lookup"><span data-stu-id="3b4bb-145">Record key information for future reference</span></span>

<span data-ttu-id="3b4bb-146">Sie können diesen Artikel auch ausdrucken, um die speziellen Informationen zu notieren, die Sie für diese Umgebung in den kommenden 30 Tage des Office 365-Testabonnements benötigen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="3b4bb-147">Sie können das Testabonnement einfach um weitere 30 Tage verlängern.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="3b4bb-148">Für eine dauerhafte Testumgebung erstellen Sie ein neues bezahltes Abonnement mit einem separaten Azure AD-Mandanten und einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="3b4bb-149">Notieren Sie diese Werte:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-149">Record these values:</span></span>
  
- <span data-ttu-id="3b4bb-150">Name des globalen Office 365-Administrators: </span><span class="sxs-lookup"><span data-stu-id="3b4bb-150">The Office 365 global administrator name:</span></span> ![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-152">.onmicrosoft.com (aus Schritt 6 von Phase 1)</span><span class="sxs-lookup"><span data-stu-id="3b4bb-152">Office 365 global administrator name: .onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="3b4bb-153">Notieren Sie auch das Kennwort für dieses Konto, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="3b4bb-154">Organisationsname für das Testabonnement:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-154">Your trial subscription organization name:</span></span> ![Zeile](./media/Common-Images/TableLine.png) <span data-ttu-id="3b4bb-156">(aus Schritt 4 von Phase 1)</span><span class="sxs-lookup"><span data-stu-id="3b4bb-156">Your trial subscription organization name:  (from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="3b4bb-157">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung den folgenden Befehl aus, um die Konten für Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5 anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="3b4bb-158">Notieren Sie hier die Kontonamen:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="3b4bb-159">Benutzer 2 Kontoname: user2@</span><span class="sxs-lookup"><span data-stu-id="3b4bb-159">User 2 account name: user2@.onmicrosoft.com</span></span>![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3b4bb-162">Benutzer 3 Kontoname: user3@</span><span class="sxs-lookup"><span data-stu-id="3b4bb-162">User 3 account name: user3@.onmicrosoft.com</span></span>![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3b4bb-165">Benutzer 4 Kontoname: user4@</span><span class="sxs-lookup"><span data-stu-id="3b4bb-165">User 4 account name: user4@.onmicrosoft.com</span></span>![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3b4bb-168">Benutzer 5 Kontoname: user5@</span><span class="sxs-lookup"><span data-stu-id="3b4bb-168">User 5 account name: user5@.onmicrosoft.com</span></span>![Zeile](./media/Common-Images/TableLine.png)<span data-ttu-id="3b4bb-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3b4bb-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="3b4bb-171">Notieren Sie auch das gemeinsame Kennwort für diese Konten, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="3b4bb-172">Verwenden einer Office 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3b4bb-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="3b4bb-173">Wenn Sie nur eine Office 365-Testumgebung benötigen, sind Sie hier fertig.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="3b4bb-174">Weitere Testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="3b4bb-175">Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3b4bb-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="3b4bb-176">In dieser Phase registrieren Sie sich für das Microsoft 365 E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="3b4bb-177">Fügen Sie zuerst das Testabonnement für Microsoft 365 E5 hinzu, und weisen Sie ihrem globalen Administratorkonto die neue Microsoft 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="3b4bb-178">Melden Sie sich mit einer privaten Instanz eines Internetbrowsers mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) an. </span><span class="sxs-lookup"><span data-stu-id="3b4bb-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="3b4bb-179">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="3b4bb-180">Klicken Sie auf der Seite **Dienste kaufen** auf **Microsoft 365 E5**, und klicken Sie dann **Kostenlose Testversion anfordern**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="3b4bb-181">Wählen Sie auf der Seite **Microsoft 365 E5 Testversion** aus, ob Sie eine SMS oder einen Anruf erhalten möchten, geben Sie Ihre Telefonnummer ein und klicken Sie dann **SMS an mich senden** oder **Mich anrufen**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="3b4bb-182">Führen Sie eine Überprüfung durch.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-182">Perform the verification.</span></span>

5. <span data-ttu-id="3b4bb-183">Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="3b4bb-184">Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="3b4bb-185">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="3b4bb-186">Klicken Sie in **Aktive Benutzer** auf Ihr Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="3b4bb-187">Klicken Sie auf **Lizenzen und Apps**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="3b4bb-188">Deaktivieren Sie die Lizenz für Office 365 Enterprise E5 und aktivieren Sie die Lizenz für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="3b4bb-189">Klicken Sie auf **Änderungen speichern**, und schließen Sie dann den Bereich mit den Benutzerkontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="3b4bb-190">Wiederholen Sie dann die Schritte 8 bis 11 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b4bb-191">Das Testabonnement für Microsoft 365 E5 ist 30 Tage gültig.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="3b4bb-192">Ändern Sie für eine dauerhafte Testumgebung dieses Testabonnement in ein kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="3b4bb-193">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="3b4bb-194">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="3b4bb-195">Alle Ihre entsprechenden Benutzerkonten (entweder nur der globale Administrator oder alle fünf Benutzerkonten) können Microsoft 365 E5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="3b4bb-196">Hier sehen Sie die daraus resultierende Konfiguration, die Microsoft 365 E5 hinzugefügt, das Office 365 und Enterprise Security + Management (EMS) umfasst.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Phase 3 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="3b4bb-198">Phase 4: Erstellen eines Computers mit Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b4bb-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="3b4bb-199">In dieser Phase erstellen Sie einen eigenständigen Computer unter Windows 10 Enterprise entweder als physischen Computer, als virtuellen Computer oder als virtuellen Azure-Computer.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="3b4bb-200">Physischer Computer</span><span class="sxs-lookup"><span data-stu-id="3b4bb-200">Physical computer</span></span>

<span data-ttu-id="3b4bb-p109">Installieren Sie Windows 10 Enterprise auf einem PC. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="3b4bb-203">Virtueller Computer</span><span class="sxs-lookup"><span data-stu-id="3b4bb-203">Virtual machine</span></span>

<span data-ttu-id="3b4bb-p110">Erstellen Sie mit dem Hypervisor Ihrer Wahl einen virtuellen Computer, und installieren Sie Windows 10 Enterprise darauf. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="3b4bb-206">Virtueller Computer in Azure</span><span class="sxs-lookup"><span data-stu-id="3b4bb-206">Virtual machine in Azure</span></span>

<span data-ttu-id="3b4bb-p111">Zum Erstellen eines virtuellen Computers mit Windows 10 in Microsoft Azure ***benötigen Sie ein Visual Studio-basiertes Abonnement***, das Zugriff auf das Image für Windows 10 Enterprise hat. Andere Arten von Azure-Abonnements, wie z. B. Testabonnements und kostenpflichtige Abonnements, haben keinen Zugriff auf dieses Image. Die neuesten Informationen finden Sie unter [Verwenden des Windows-Clients in Azure für Entwicklungs-/Testszenarien](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b4bb-p112">Die folgenden Befehlssätze verwenden die aktuelle Version von Azure PowerShell. Informationen dazu finden Sie unter [Erste Schritte mit Azure PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Mit diesen Befehlssätzen werden ein virtueller Windows 10 Enterprise-Computer mit dem Namen „WIN10“ sowie die gesamte erforderliche Infrastruktur, einschließlich einer Ressourcengruppe, eines Speicherkontos und eines virtuellen Netzwerks erstellt. Wenn Sie bereits mit den Azure-Infrastrukturdiensten vertraut sind, passen Sie diese Anweisungen entsprechend Ihrer aktuell bereitgestellten Infrastruktur an.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="3b4bb-214">Starten Sie zuerst eine Microsoft PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="3b4bb-215">Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="3b4bb-216">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="3b4bb-p113">Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch den entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="3b4bb-p114">Im nächsten Schritt wird eine neue Ressourcengruppe erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="3b4bb-p115">Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch die entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="3b4bb-p116">Im nächsten Schritt erstellen Sie ein neues virtuelles Netzwerk und den virtuellen WIN10-Computer mit den folgenden Befehlen. Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort des lokalen Administratorkontos für WIN10 an, und bewahren Sie dieses an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="3b4bb-225">Phase 5: Einbinden des Windows 10-Computers in Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b4bb-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="3b4bb-226">Nachdem Sie den physischen oder virtuellen Computer mit Windows 10 Enterprise erstellt haben, melden Sie sich mit einem lokalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b4bb-227">Für einen virtuellen Computer in Azure verbinden Sie diesen mithilfe der [folgenden Anweisungen](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="3b4bb-228">Als Nächstes fügen Sie den WIN10-Computer dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="3b4bb-229">Klicken Sie auf dem Desktop des WIN10-Computers auf **Start > Einstellungen > Konten > Auf Arbeits- oder Schulkonto zugreifen > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="3b4bb-230">Klicken Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** auf **Dieses Gerät in Azure Active Directory einbinden**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="3b4bb-231">Geben Sie unter **Geschäfts-, Schul- oder Unikonto** den Namen des globalen Administratorkontos Ihres Microsoft 365 E5-Abonnements ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="3b4bb-232">Geben Sie unter **Kennwort eingeben** das Kennwort für das globale Administratorkonto ein, und klicken Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="3b4bb-233">Wenn Sie dazu aufgefordert werden, sicherzustellen, dass es sich hierbei um Ihre Organisation handelt, klicken Sie auf **Teilnehmen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="3b4bb-234">Schließen Sie das Fenster mit den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-234">Close the settings window.</span></span>
    
<span data-ttu-id="3b4bb-235">Installieren Sie im nächsten Schritt Office 365 ProPlus auf dem WIN10-Computer.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-235">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="3b4bb-236">Öffnen Sie den Microsoft Edge-Browser, und melden Sie sich mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Office-Portal an.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="3b4bb-237">Hilfe finden Sie unter [Wo kann ich mich bei Office 365 anmelden?](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="3b4bb-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="3b4bb-238">Klicken Sie auf der Registerkarte der **Microsoft Office-Startseite** auf **Office installieren**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="3b4bb-239">Wenn Sie dazu aufgefordert werden, klicken Sie auf **Ausführen**, und klicken Sie dann auf **Ja** für **Benutzerkontensteuerung**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="3b4bb-p118">Warten Sie, bis Office die Installation beendet hat. Wenn **Alles bereit** angezeigt wird, klicken Sie zweimal auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="3b4bb-242">Nachfolgend sehen Sie die daraus resultierende Umgebung.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-242">Here is your resulting environment.</span></span>

![Phase 5 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="3b4bb-244">Dies schließt den WIN10-Computer mit ein:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="3b4bb-245">Er wurde dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="3b4bb-246">Er wurde als Azure AD-Gerät in Microsoft Intune (EMS) registriert.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="3b4bb-247">Auf ihm ist Office 365 ProPlus installiert.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-247">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="3b4bb-248">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="3b4bb-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="3b4bb-249">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3b4bb-249">Next steps</span></span>

<span data-ttu-id="3b4bb-250">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="3b4bb-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="3b4bb-251">Identität</span><span class="sxs-lookup"><span data-stu-id="3b4bb-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="3b4bb-252">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="3b4bb-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="3b4bb-253">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="3b4bb-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="3b4bb-254">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b4bb-254">See also</span></span>

[<span data-ttu-id="3b4bb-255">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b4bb-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3b4bb-256">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b4bb-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3b4bb-257">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b4bb-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
