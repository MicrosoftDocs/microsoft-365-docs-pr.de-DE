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
ms.openlocfilehash: c654dc80620b98d09cf508e309d4410d9cf4a4dc
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639915"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="207a3-103">Die einfache Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="207a3-103">The lightweight base configuration</span></span>

<span data-ttu-id="207a3-104">In diesem Artikel erhalten Sie Schritt-für-Schritt-Anweisungen zum Erstellen einer vereinfachten Umgebung die ein Microsoft 365 E5-Abonnement und einen Computer mit Windows 10 Enterprise umfasst.</span><span class="sxs-lookup"><span data-stu-id="207a3-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Einfache Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="207a3-106">Verwenden die resultierende Umgebung zum Testen der Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="207a3-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="207a3-108">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="207a3-108">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="207a3-109">Phase 1: Erstellen des Office 365 E5-Abonnements</span><span class="sxs-lookup"><span data-stu-id="207a3-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="207a3-110">Wir beginnen mit einem Office 365 E5-Testabonnement und fügen dann das Microsoft 365 E5-Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="207a3-110">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="207a3-111">Für das Office 365 E5-Testabonnement benötigen Sie zunächst einen fiktiven Unternehmensnamen und ein neues Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="207a3-111">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="207a3-p101">Es wird empfohlen, eine Variante von „Contoso“ als Unternehmensnamen zu verwenden. Dies ist ein fiktives Unternehmen, das von Microsoft in Beispielen verwendet wird. Notieren Sie hier Ihren fiktiven Unternehmensnamen: ![](./media/Common-Images/TableLine.png).</span><span class="sxs-lookup"><span data-stu-id="207a3-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="207a3-p102">Wenn Sie sich für ein neues Microsoft-Konto registrieren möchten, wechseln Sie zu [https://outlook.com](https://outlook.com), und erstellen Sie ein Konto mit neuem E-Mail-Konto und neuer E-Mail-Adresse. Dieses Konto wird für die Registrierung für Office 365 verwendet.</span><span class="sxs-lookup"><span data-stu-id="207a3-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="207a3-116">Notieren Sie hier den Vor- und Nachnamen des Kontos: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="207a3-116">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="207a3-117">Notieren Sie hier die neue E-Mail-Kontoadresse: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="207a3-117">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="207a3-118">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="207a3-118">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="207a3-119">Öffnen Sie den Internetbrowser auf Ihrem Computer, und navigieren Sie zu [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="207a3-119">For the lightweight Office 365 dev/test environment, open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="207a3-120">Geben Sie auf der Seite **Willkommen, Grundlegendes zu Ihrer Person** die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="207a3-120">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="207a3-121">Tatsächlicher Standort</span><span class="sxs-lookup"><span data-stu-id="207a3-121">Your physical location</span></span>
    
  - <span data-ttu-id="207a3-122">Vor- und Nachname des neuen Microsoft-Kontos</span><span class="sxs-lookup"><span data-stu-id="207a3-122">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="207a3-123">Die neue E-Mail-Kontoadresse</span><span class="sxs-lookup"><span data-stu-id="207a3-123">Your new email account address</span></span>
    
  - <span data-ttu-id="207a3-124">Telefonnummer geschäftlich</span><span class="sxs-lookup"><span data-stu-id="207a3-124">A business phone number</span></span>
    
  - <span data-ttu-id="207a3-125">Fiktiver Unternehmensname</span><span class="sxs-lookup"><span data-stu-id="207a3-125">Your fictional company name</span></span>
    
  - <span data-ttu-id="207a3-126">Unternehmensgröße zwischen 250-999 Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="207a3-126">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="207a3-127">Klicken Sie auf **Nur noch ein Schritt**.</span><span class="sxs-lookup"><span data-stu-id="207a3-127">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="207a3-128">Geben Sie auf der Seite **Benutzer-ID erstellen** einen Benutzernamen auf Grundlage der neuen E-Mail-Adresse, den fiktiven Unternehmensnamen nach dem @-Zeichen (entfernen Sie alle Leerzeichen im Namen) und dann (zweimal) ein Kennwort für dieses neue Office 365-Konto ein. </span><span class="sxs-lookup"><span data-stu-id="207a3-128">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="207a3-129">Notieren Sie das verwendete Kennwort, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="207a3-129">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="207a3-130">Notieren Sie hier den fiktiven Unternehmensnamen, der im Folgenden **Organisationsname** genannt wird: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="207a3-130">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="207a3-131">Klicken Sie auf **Mein Konto erstellen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-131">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="207a3-p103">Geben Sie auf der Seite **Ich bin kein Roboter** die Rufnummer eines SMS-fähigen Mobiltelefons, und klicken Sie dann auf **SMS an mich**.</span><span class="sxs-lookup"><span data-stu-id="207a3-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="207a3-134">Geben Sie den Verifizierungscode ein, den Sie per SMS erhalten haben, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="207a3-134">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="207a3-135">Notieren Sie hier die URL der Anmeldeseite (auswählen und kopieren): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="207a3-135">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="207a3-136">Notieren Sie hier die Benutzer-ID (auswählen und kopieren): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="207a3-136">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="207a3-137">Dieser Wert wird **Name des globalen Office 365-Administrators** genannt.</span><span class="sxs-lookup"><span data-stu-id="207a3-137">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="207a3-138">Wenn **Alle Schritte wurden abgeschlossen.** angezeigt wird, klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="207a3-138">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="207a3-139">Warten Sie auf der nächsten Seite, bis die Einrichtung von Office 365 abgeschlossen ist und alle Kacheln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="207a3-139">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="207a3-140">Nun sollte die Hauptseite des Office 365-Portals angezeigt werden, über die Sie auf Office-Dienste und das Microsoft 365 Admin Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="207a3-140">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="207a3-141">Dann fordern wir Sie dazu auf, ein Office 365-Testabonnement zu erstellen, damit Ihre Dev/Test-Umgebung über einen separaten Azure AD-Mandanten verfügt, der getrennt ist von allen kostenpflichtigen Abonnements, die Sie aktuell haben.</span><span class="sxs-lookup"><span data-stu-id="207a3-141">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="207a3-142">Diese Trennung bedeutet, dass Sie Benutzer zum Testmandanten hinzufügen und entfernen können, ohne dass dies Auswirkungen auf Ihre Produktionsabonnements hat.</span><span class="sxs-lookup"><span data-stu-id="207a3-142">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="207a3-143">Phase 2: Konfigurieren des Office 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="207a3-143">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="207a3-144">In dieser Phase konfigurieren Sie Ihr Office 365-Abonnement mit weiteren Benutzern und weisen diesen Office 365 E5-Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="207a3-144">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="207a3-145">Befolgen Sie die Anweisungen unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), um Ihr Office 365-Abonnement von Ihrem Computer aus mit dem Azure Active Directory PowerShell-Modul für Graph zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="207a3-145">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="207a3-146">Geben Sie in das Dialogfeld „Windows PowerShell Credential Request“ den Namen des globalen Office 365-Administrators (z. B. „jdoe@contosotoycompany.onmicrosoft.com“) und sein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="207a3-146">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="207a3-147">Geben Sie den Namen Ihrer Organisation (z. B. „contosotoycompany“), den zweistelligen Ländercode für Ihren Standort und ein gemeinsames Kontokennwort ein, und führen Sie dann die folgenden Befehle von der PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="207a3-147">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="207a3-148">Für die Automatisierung und Vereinfachung der Konfiguration einer Dev/Test-Umgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="207a3-148">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="207a3-149">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="207a3-149">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="207a3-150">Aufzeichnen von Schlüsselinformationen für spätere Verweise</span><span class="sxs-lookup"><span data-stu-id="207a3-150">Record key information for future reference</span></span>

<span data-ttu-id="207a3-151">Sie können diesen Artikel auch ausdrucken, um die speziellen Informationen zu notieren, die Sie für diese Umgebung in den kommenden 30 Tage des Office 365-Testabonnements benötigen.</span><span class="sxs-lookup"><span data-stu-id="207a3-151">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="207a3-152">Sie können das Testabonnement einfach um weitere 30 Tage verlängern.</span><span class="sxs-lookup"><span data-stu-id="207a3-152">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="207a3-153">Für eine dauerhafte Entwicklungs-/Testumgebung erstellen Sie ein neues bezahltes Abonnement mit einem separaten Azure AD-Mandanten und einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="207a3-153">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="207a3-154">Notieren Sie diese Werte:</span><span class="sxs-lookup"><span data-stu-id="207a3-154">Record these values:</span></span>
  
- <span data-ttu-id="207a3-155">Name des globalen Office 365-Administrators: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (aus Schritt 9 von Phase 2)</span><span class="sxs-lookup"><span data-stu-id="207a3-155">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="207a3-156">Notieren Sie auch das Kennwort für dieses Konto, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="207a3-156">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="207a3-157">Organisationsname für das Testabonnement: ![](./media/Common-Images/TableLine.png) (aus Schritt 4 von Phase 2)</span><span class="sxs-lookup"><span data-stu-id="207a3-157">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="207a3-158">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung den folgenden Befehl aus, um die Konten für Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5 anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="207a3-158">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="207a3-159">Notieren Sie hier die Kontonamen:</span><span class="sxs-lookup"><span data-stu-id="207a3-159">Record the account names here:</span></span>
    
  - <span data-ttu-id="207a3-160">Kontoname für Benutzer 2: benutzer2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="207a3-160">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="207a3-161">Kontoname für Benutzer 3: benutzer3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="207a3-161">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="207a3-162">Kontoname für Benutzer 4: benutzer4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="207a3-162">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="207a3-163">Kontoname für Benutzer 5: benutzer5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="207a3-163">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="207a3-164">Notieren Sie auch das gemeinsame Kennwort für diese Konten, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="207a3-164">Also record the passwords for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="207a3-165">Verwenden einer Office 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="207a3-165">Phase 1: Create an Office 365 dev/test environment</span></span>

<span data-ttu-id="207a3-166">Wenn Sie nur eine Office 365-Entwicklungs-/Testumgebung benötigen, sind Sie hier fertig.</span><span class="sxs-lookup"><span data-stu-id="207a3-166">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="207a3-167">Weitere Testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="207a3-167">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="207a3-168">Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="207a3-168">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="207a3-169">In dieser Phase registrieren Sie sich für das Microsoft 365 E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="207a3-169">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="207a3-170">Fügen Sie zuerst das Testabonnement für Microsoft 365 E5 hinzu, und weisen Sie ihrem globalen Administratorkonto eine Microsoft 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="207a3-170">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="207a3-171">Melden Sie sich mit einer privaten Instanz eines Internetbrowsers mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) an. </span><span class="sxs-lookup"><span data-stu-id="207a3-171">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="207a3-172">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-172">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="207a3-173">Finden Sie auf der Seite**Dienste kaufen** das Element **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="207a3-173">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="207a3-174">Zeigen Sie mit Ihrem Mauszeiger darauf und klicken Sie **Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="207a3-174">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="207a3-175">Wählen Sie auf der Seite **Microsoft 365 E5 Testversion** aus, ob Sie eine SMS oder einen Anruf erhalten möchten, geben Sie Ihre Telefonnummer ein und klicken Sie dann **SMS an mich senden** oder **Mich anrufen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-175">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="207a3-176">Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-176">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="207a3-177">Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="207a3-177">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="207a3-178">Klicken Sie im Microsoft 365 Admin Center **Aktiver Benutzer** und klicken Sie dann auf Ihr Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="207a3-178">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="207a3-179">Klicken Sie **Bearbeiten** für **Produktlizenzen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-179">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="207a3-180">Deaktivieren Sie die Lizenz für Office 365 Enterprise E5 und aktivieren Sie die Lizenz für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="207a3-180">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="207a3-181">Klicken Sie auf **Speichern > Schließen > Schließen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-181">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="207a3-182">Wiederholen Sie dann die Schritte 8 bis 11 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).</span><span class="sxs-lookup"><span data-stu-id="207a3-182">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="207a3-183">Das Testabonnement für Microsoft 365 E5 ist 30 Tage gültig.</span><span class="sxs-lookup"><span data-stu-id="207a3-183">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="207a3-184">Ändern Sie für eine dauerhafte Testumgebung dieses Testabonnement in ein kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="207a3-184">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="207a3-185">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="207a3-185">Your test environment now has:</span></span>
  
- <span data-ttu-id="207a3-186">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="207a3-186">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="207a3-187">Alle Ihre entsprechenden Benutzerkonten (entweder nur der globale Administrator oder alle fünf Benutzerkonten) können Microsoft 365 E5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="207a3-187">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="207a3-188">Hier sehen Sie die daraus resultierende Konfiguration, die Microsoft 365 E5 hinzugefügt, das Office 365 und Enterprise Security + Management (EMS) umfasst.</span><span class="sxs-lookup"><span data-stu-id="207a3-188">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Phase 2 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="207a3-190">Phase 4: Erstellen eines Computers mit Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="207a3-190">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="207a3-191">In dieser Phase erstellen Sie einen eigenständigen Computer unter Windows 10 Enterprise entweder als physischen Computer, als virtuellen Computer oder als virtuellen Azure-Computer.</span><span class="sxs-lookup"><span data-stu-id="207a3-191">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="207a3-192">Physischer Computer</span><span class="sxs-lookup"><span data-stu-id="207a3-192">Physical computer</span></span>

<span data-ttu-id="207a3-p109">Installieren Sie Windows 10 Enterprise auf einem PC. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="207a3-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="207a3-195">Virtueller Computer</span><span class="sxs-lookup"><span data-stu-id="207a3-195">Virtual machine</span></span>

<span data-ttu-id="207a3-p110">Erstellen Sie mit dem Hypervisor Ihrer Wahl einen virtuellen Computer, und installieren Sie Windows 10 Enterprise darauf. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="207a3-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="207a3-198">Virtueller Computer in Azure</span><span class="sxs-lookup"><span data-stu-id="207a3-198">Virtual machine in Azure</span></span>

<span data-ttu-id="207a3-p111">Zum Erstellen eines virtuellen Computers mit Windows 10 in Microsoft Azure ***benötigen Sie ein Visual Studio-basiertes Abonnement***, das Zugriff auf das Image für Windows 10 Enterprise hat. Andere Arten von Azure-Abonnements, wie z. B. Testabonnements und kostenpflichtige Abonnements, haben keinen Zugriff auf dieses Image. Die neuesten Informationen finden Sie unter [Verwenden des Windows-Clients in Azure für Entwicklungs-/Testszenarien](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="207a3-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="207a3-p112">Die folgenden Befehlssätze verwenden die aktuelle Version von Azure PowerShell. Informationen dazu finden Sie unter [Erste Schritte mit Azure PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Mit diesen Befehlssätzen werden ein virtueller Windows 10 Enterprise-Computer mit dem Namen „WIN10“ sowie die gesamte erforderliche Infrastruktur, einschließlich einer Ressourcengruppe, eines Speicherkontos und eines virtuellen Netzwerks erstellt. Wenn Sie bereits mit den Azure-Infrastrukturdiensten vertraut sind, passen Sie diese Anweisungen entsprechend Ihrer aktuell bereitgestellten Infrastruktur an.</span><span class="sxs-lookup"><span data-stu-id="207a3-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="207a3-206">Starten Sie zuerst eine Microsoft PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="207a3-206">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="207a3-207">Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="207a3-207">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="207a3-208">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="207a3-208">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="207a3-p113">Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch den entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="207a3-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="207a3-p114">Im nächsten Schritt wird eine neue Ressourcengruppe erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="207a3-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="207a3-p115">Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch die entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="207a3-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="207a3-p116">Im nächsten Schritt erstellen Sie ein neues virtuelles Netzwerk und den virtuellen WIN10-Computer mit den folgenden Befehlen. Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort des lokalen Administratorkontos für WIN10 an, und bewahren Sie dieses an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="207a3-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="207a3-217">Phase 5: Einbinden des Windows 10-Computers in Azure AD</span><span class="sxs-lookup"><span data-stu-id="207a3-217">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="207a3-218">Nachdem Sie den physischen oder virtuellen Computer mit Windows 10 Enterprise erstellt haben, melden Sie sich mit einem lokalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="207a3-218">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="207a3-219">Für einen virtuellen Computer in Azure verbinden Sie diesen mithilfe der [folgenden Anweisungen](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="207a3-219">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="207a3-220">Als Nächstes fügen Sie den WIN10-Computer dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzu.</span><span class="sxs-lookup"><span data-stu-id="207a3-220">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="207a3-221">Klicken Sie auf dem Desktop des WIN10-Computers auf **Start > Einstellungen > Konten > Auf Arbeits- oder Schulkonto zugreifen > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="207a3-221">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="207a3-222">Klicken Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** auf **Dieses Gerät in Azure Active Directory einbinden**.</span><span class="sxs-lookup"><span data-stu-id="207a3-222">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="207a3-223">Geben Sie unter **Geschäfts-, Schul- oder Unikonto** den Namen des globalen Administratorkontos Ihres Microsoft 365 E5-Abonnements ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="207a3-223">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="207a3-224">Geben Sie unter **Kennwort eingeben** das Kennwort für das globale Administratorkonto ein, und klicken Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="207a3-224">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="207a3-225">Wenn Sie dazu aufgefordert werden, sicherzustellen, dass es sich hierbei um Ihre Organisation handelt, klicken Sie auf **Teilnehmen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="207a3-225">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="207a3-226">Schließen Sie das Fenster mit den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="207a3-226">Close the settings window.</span></span>
    
<span data-ttu-id="207a3-227">Installieren Sie im nächsten Schritt Office 365 ProPlus auf dem WIN10-Computer.</span><span class="sxs-lookup"><span data-stu-id="207a3-227">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="207a3-228">Öffnen Sie den Microsoft Edge-Browser, und melden Sie sich mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Office-Portal an.</span><span class="sxs-lookup"><span data-stu-id="207a3-228">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="207a3-229">Hilfe finden Sie unter [Wo kann ich mich bei Office 365 anmelden?](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="207a3-229">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="207a3-230">Klicken Sie auf der Registerkarte der **Microsoft Office-Startseite** auf **Office installieren**.</span><span class="sxs-lookup"><span data-stu-id="207a3-230">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="207a3-231">Wenn Sie dazu aufgefordert werden, klicken Sie auf **Ausführen**, und klicken Sie dann auf **Ja** für **Benutzerkontensteuerung**.</span><span class="sxs-lookup"><span data-stu-id="207a3-231">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="207a3-p118">Warten Sie, bis Office die Installation beendet hat. Wenn **Alles bereit** angezeigt wird, klicken Sie zweimal auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="207a3-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="207a3-234">Nachfolgend sehen Sie die daraus resultierende Umgebung.</span><span class="sxs-lookup"><span data-stu-id="207a3-234">Here is your resulting configuration.</span></span>

![Phase 5 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="207a3-236">Dies schließt den WIN10-Computer mit ein:</span><span class="sxs-lookup"><span data-stu-id="207a3-236">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="207a3-237">Er wurde dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="207a3-237">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="207a3-238">Er wurde als Azure AD-Gerät in Microsoft Intune (EMS) registriert.</span><span class="sxs-lookup"><span data-stu-id="207a3-238">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="207a3-239">Auf ihm ist Office 365 ProPlus installiert.</span><span class="sxs-lookup"><span data-stu-id="207a3-239">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="207a3-240">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="207a3-240">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="207a3-241">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="207a3-241">Next steps</span></span>

<span data-ttu-id="207a3-242">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="207a3-242">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="207a3-243">Identität</span><span class="sxs-lookup"><span data-stu-id="207a3-243">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="207a3-244">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="207a3-244">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="207a3-245">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="207a3-245">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="207a3-246">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="207a3-246">See also</span></span>

[<span data-ttu-id="207a3-247">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="207a3-247">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="207a3-248">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="207a3-248">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="207a3-249">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="207a3-249">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
