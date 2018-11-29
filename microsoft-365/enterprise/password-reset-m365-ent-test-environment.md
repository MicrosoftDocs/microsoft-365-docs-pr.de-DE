---
title: Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen der Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868141"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="baae2-103">Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="baae2-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="baae2-104">Die Azure AD Self-Service-Kennwortzurücksetzung (SSPR) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="baae2-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="baae2-105">Dieser Artikel beschreibt, wie Sie die Kennwortzurücksetzung in Ihrer Microsoft 365-Testumgebung in zwei Phasen konfigurieren und testen:</span><span class="sxs-lookup"><span data-stu-id="baae2-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="baae2-106">Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="baae2-106">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="baae2-107">Konfigurieren Sie und testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="baae2-107">Configure and test password reset for the User 2 account.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="baae2-109">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="baae2-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="baae2-110">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="baae2-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="baae2-p101">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="baae2-p101">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Through-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="baae2-114">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="baae2-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="baae2-115">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5.</span><span class="sxs-lookup"><span data-stu-id="baae2-115">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="baae2-116">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="baae2-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="baae2-117">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory-Domäne TESTLAB von Windows Server mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="baae2-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="baae2-118">Phase 2: Konfigurieren und testen Sie die Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="baae2-118">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="baae2-119">In dieser Phase konfigurieren Sie die Kennwortzurücksetzung im Azure AD-Mandanten durch Gruppenmitgliedschaft und vergewissern sich anschließend, dass sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="baae2-119">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="baae2-120">Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="baae2-120">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="baae2-121">Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="baae2-121">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="baae2-122">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen > Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="baae2-122">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="baae2-p102">Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest. Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="baae2-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="baae2-125">Klicken Sie auf die Gruppe **PWReset** in der Liste, und klicken Sie dann auf **Mitglieder**.</span><span class="sxs-lookup"><span data-stu-id="baae2-125">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="baae2-p103">Klicken Sie auf **Mitglieder hinzufügen**, klicken Sie auf **Benutzer 2**, und klicken Sie dann auf **Auswählen**. Schließen Sie die Seiten **PWReset** und **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="baae2-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="baae2-128">Klicken Sie auf der Azure Active Directory-Seite auf **Kennwortzurücksetzung**.</span><span class="sxs-lookup"><span data-stu-id="baae2-128">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="baae2-129">Wählen Sie auf der Seite **Eigenschaften** unter der Option **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt**.</span><span class="sxs-lookup"><span data-stu-id="baae2-129">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="baae2-130">Wählen Sie unter **Gruppe auswählen** den Eintrag **PWReset** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="baae2-130">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="baae2-131">Schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="baae2-131">Close the private browser instance.</span></span>

<span data-ttu-id="baae2-132">Als Nächstes testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="baae2-132">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="baae2-133">Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="baae2-133">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="baae2-134">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an.</span><span class="sxs-lookup"><span data-stu-id="baae2-134">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="baae2-135">Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="baae2-135">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="baae2-136">Nachdem beide Angaben überprüft wurden, klicken Sie auf **Sieht gut aus**, und schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="baae2-136">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="baae2-137">Öffnen Sie eine neue private Browserinstanz, und wechseln Sie zu [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="baae2-137">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="baae2-138">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an, geben Sie die Zeichen aus dem CAPTCHA ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="baae2-138">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="baae2-p104">Klicken Sie in **Überprüfungsschritt 1** auf **E-Mail an meine alternative E-Mail-Adresse senden**, und klicken Sie dann auf **E-Mail**. Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="baae2-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="baae2-p105">Geben Sie unter **Wiederherstellen des Kontos** ein neues Kennwort für das Konto von Benutzer 2 ein, und klicken Sie dann auf **Fertig stellen**. Notieren Sie sich das geänderte Kennwort für das Konto von Benutzer 2, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="baae2-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="baae2-p106">Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://portal.office.com](https://portal.office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 2 und dem neuen Kennwort an. Die **Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="baae2-p106">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="baae2-145">Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-password-reset.md) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der Kennwortzurücksetzung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="baae2-145">See the [Simplify password resets](identity-password-reset.md) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="baae2-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="baae2-146">Next step</span></span>

<span data-ttu-id="baae2-147">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="baae2-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="baae2-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baae2-148">See also</span></span>

[<span data-ttu-id="baae2-149">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="baae2-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="baae2-150">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="baae2-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="baae2-151">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="baae2-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
