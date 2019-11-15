---
title: Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen der Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 4ddcb0718fbb5546a0e37b648b698b46d7e55ec0
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640724"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5da2d-103">Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="5da2d-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5da2d-104">Die Self-Service-Kennwortzurücksetzung (SSPR) des Azure Active Directory (Azure AD) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="5da2d-104">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="5da2d-105">Dieser Artikel beschreibt, wie Sie die Kennwortzurücksetzung in Ihrer Microsoft 365-Testumgebung in drei Phasen konfigurieren und testen:</span><span class="sxs-lookup"><span data-stu-id="5da2d-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="5da2d-106">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="5da2d-106">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="5da2d-107">Aktivieren des Kennwortrückschreibens.</span><span class="sxs-lookup"><span data-stu-id="5da2d-107">Enable password writeback.</span></span>
3.  <span data-ttu-id="5da2d-108">Konfigurieren Sie und testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="5da2d-108">Configure and test password reset for the User 2 account.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5da2d-110">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5da2d-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5da2d-111">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="5da2d-111">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5da2d-p101">Befolgen Sie zuerst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5da2d-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="5da2d-115">Diese Konfiguration besteht aus:</span><span class="sxs-lookup"><span data-stu-id="5da2d-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="5da2d-116">Testversionen oder kostenpflichtigen Abonnements von Office 365 E5 und EMS E5.</span><span class="sxs-lookup"><span data-stu-id="5da2d-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="5da2d-117">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="5da2d-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="5da2d-118">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="5da2d-118">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>


## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="5da2d-119">Phase 2: Aktivieren Sie das Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="5da2d-119">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="5da2d-120">Folgen Sie den Anweisungen unter [Phase 2 der Kennwortrückschreibung der Testumgebungsanleitungen](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="5da2d-120">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="5da2d-121">Sie müssen das Rückschreiben des Kennworts aktiviert haben, um das Kennwortzurücksetzen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="5da2d-121">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="5da2d-122">Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="5da2d-122">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="5da2d-123">In dieser Phase konfigurieren Sie die Kennwortzurücksetzung im Azure AD-Mandanten durch Gruppenmitgliedschaft und vergewissern sich anschließend, dass sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5da2d-123">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="5da2d-124">Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="5da2d-124">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="5da2d-125">Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="5da2d-125">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="5da2d-126">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen > Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-126">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="5da2d-p102">Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest. Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="5da2d-129">Klicken Sie auf die Gruppe **PWReset** in der Liste, und klicken Sie dann auf **Mitglieder**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-129">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="5da2d-p103">Klicken Sie auf **Mitglieder hinzufügen**, klicken Sie auf **Benutzer 2**, und klicken Sie dann auf **Auswählen**. Schließen Sie die Seiten **PWReset** und **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="5da2d-132">Klicken Sie auf der Azure Active Directory-Seite auf **Kennwortzurücksetzung**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-132">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="5da2d-133">Wählen Sie auf der Seite **Eigenschaften** unter der Option **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-133">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="5da2d-134">Wählen Sie unter **Gruppe auswählen** den Eintrag **PWReset** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-134">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="5da2d-135">Schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="5da2d-135">Close the private browser instance.</span></span>

<span data-ttu-id="5da2d-136">Als Nächstes testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="5da2d-136">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="5da2d-137">Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="5da2d-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="5da2d-138">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an.</span><span class="sxs-lookup"><span data-stu-id="5da2d-138">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="5da2d-139">Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="5da2d-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="5da2d-140">Nachdem beide Angaben überprüft wurden, klicken Sie auf **Sieht gut aus**, und schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="5da2d-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="5da2d-141">Öffnen Sie eine neue private Browserinstanz, und wechseln Sie zu [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="5da2d-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="5da2d-142">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an, geben Sie die Zeichen aus dem CAPTCHA ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="5da2d-p104">Klicken Sie in **Überprüfungsschritt 1** auf **E-Mail an meine alternative E-Mail-Adresse senden**, und klicken Sie dann auf **E-Mail**. Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5da2d-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="5da2d-p105">Geben Sie unter **Wiederherstellen des Kontos** ein neues Kennwort für das Konto von Benutzer 2 ein, und klicken Sie dann auf **Fertig stellen**. Notieren Sie sich das geänderte Kennwort für das Konto von Benutzer 2, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="5da2d-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="5da2d-147">Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://portal.office.com](https://portal.office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 2 und dem neuen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="5da2d-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password.</span></span> <span data-ttu-id="5da2d-148">Die **Microsoft Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5da2d-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="5da2d-149">Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-secure-your-passwords.md#identity-pw-reset) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der Kennwortzurücksetzung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="5da2d-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="5da2d-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5da2d-150">Next step</span></span>

<span data-ttu-id="5da2d-151">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="5da2d-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5da2d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5da2d-152">See also</span></span>

[<span data-ttu-id="5da2d-153">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da2d-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5da2d-154">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da2d-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5da2d-155">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5da2d-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
