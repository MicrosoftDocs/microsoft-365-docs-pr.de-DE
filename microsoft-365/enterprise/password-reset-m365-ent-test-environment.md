---
title: Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066141"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="031ed-103">Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="031ed-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="031ed-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="031ed-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="031ed-105">Die Self-Service-Kennwortzurücksetzung (SSPR) des Azure Active Directory (Azure AD) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="031ed-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="031ed-106">Dieser Artikel beschreibt, wie Sie die Kennwortzurücksetzung in Ihrer Microsoft 365-Testumgebung in drei Phasen konfigurieren und testen:</span><span class="sxs-lookup"><span data-stu-id="031ed-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="031ed-107">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="031ed-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="031ed-108">Aktivieren des Kennwortrückschreibens.</span><span class="sxs-lookup"><span data-stu-id="031ed-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="031ed-109">Konfigurieren Sie und testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 3.</span><span class="sxs-lookup"><span data-stu-id="031ed-109">Configure and test password reset for the User 3 account.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="031ed-111">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="031ed-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="031ed-112">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="031ed-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="031ed-p101">Befolgen Sie zuerst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="031ed-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="031ed-116">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="031ed-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="031ed-117">Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5 oder Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="031ed-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="031ed-118">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="031ed-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="031ed-119">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Microsoft 365- oder Office 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="031ed-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="031ed-120">Phase 2: Aktivieren Sie das Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="031ed-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="031ed-121">Folgen Sie den Anweisungen unter [Phase 2 der Kennwortrückschreibung der Testumgebungsanleitungen](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="031ed-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="031ed-122">Sie müssen das Rückschreiben des Kennworts aktiviert haben, um das Kennwortzurücksetzen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="031ed-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="031ed-123">Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="031ed-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="031ed-124">In dieser Phase konfigurieren Sie die Kennwortzurücksetzung im Azure AD-Mandanten durch Gruppenmitgliedschaft und vergewissern sich anschließend, dass sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="031ed-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="031ed-125">Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="031ed-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="031ed-126">Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="031ed-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="031ed-127">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen > Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="031ed-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="031ed-128">Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest.</span><span class="sxs-lookup"><span data-stu-id="031ed-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="031ed-129">Klicken Sie auf **Mitglieder**, suchen und wählen Sie **Benutzer 3** aus, klicken Sie auf **Auswählen** und dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="031ed-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="031ed-130">Schließen Sie den Bereich **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="031ed-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="031ed-131">Klicken Sie im Azure Active Directory-Bereich in der linken Navigation auf **Kennwort zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="031ed-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="031ed-132">Wählen Sie im Bereich **Kennwort zurücksetzen, Eigenschaften** unter **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt** aus.</span><span class="sxs-lookup"><span data-stu-id="031ed-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="031ed-133">Klicken Sie auf **Gruppe auswählen**, wählen Sie die Gruppe **PWReset** aus, und klicken Sie dann auf **Auswählen > Speichern**.</span><span class="sxs-lookup"><span data-stu-id="031ed-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="031ed-134">Schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="031ed-134">Close the private browser instance.</span></span>

<span data-ttu-id="031ed-135">Als Nächstes testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 3.</span><span class="sxs-lookup"><span data-stu-id="031ed-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="031ed-136">Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="031ed-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="031ed-137">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 3 an.</span><span class="sxs-lookup"><span data-stu-id="031ed-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="031ed-138">Klicken Sie unter **Weitere Informationen erforderlich** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="031ed-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="031ed-139">Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="031ed-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="031ed-140">Nachdem beide Angaben überprüft wurden, klicken Sie auf **Sieht gut aus**, und schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="031ed-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="031ed-141">Öffnen Sie eine neue private Browserinstanz, und wechseln Sie zu [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="031ed-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="031ed-142">Geben Sie den Namen des Kontos von Benutzer 3 und die Zeichen aus dem CAPTCHA ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="031ed-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="031ed-p102">Klicken Sie in **Überprüfungsschritt 1** auf **E-Mail an meine alternative E-Mail-Adresse senden**, und klicken Sie dann auf **E-Mail**. Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="031ed-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="031ed-145">Geben Sie unter **Konto wieder aktivieren** ein neues Kennwort für das Konto von Benutzer 3 ein, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="031ed-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="031ed-146">Notieren Sie sich das geänderte Kennwort des Kontos von Benutzer 3, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="031ed-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="031ed-147">Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://portal.office.com](https://portal.office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 3 und dem neuen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="031ed-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="031ed-148">Die **Microsoft Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="031ed-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="031ed-149">Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-secure-your-passwords.md#identity-pw-reset) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der Kennwortzurücksetzung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="031ed-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="031ed-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="031ed-150">Next step</span></span>

<span data-ttu-id="031ed-151">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="031ed-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="031ed-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="031ed-152">See also</span></span>

[<span data-ttu-id="031ed-153">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="031ed-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="031ed-154">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="031ed-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="031ed-155">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="031ed-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
