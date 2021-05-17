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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen der Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921492"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d0d5c-103">Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d0d5c-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d0d5c-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d0d5c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d0d5c-105">Die Self-Service-Kennwortzurücksetzung (SSPR) des Azure Active Directory (Azure AD) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="d0d5c-106">In diesem Artikel wird beschrieben, wie Sie Kennwortzurücksetzungen in Ihrer Microsoft 365 konfigurieren und testen.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="d0d5c-107">Das Einrichten von SSPR umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="d0d5c-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="d0d5c-108">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d0d5c-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="d0d5c-109">Phase 2: Aktivieren Sie das Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="d0d5c-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="d0d5c-110">Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d0d5c-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d0d5c-112">Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d0d5c-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d0d5c-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d0d5c-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d0d5c-114">Befolgen Sie zunächst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5c-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="d0d5c-115">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d0d5c-115">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="d0d5c-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="d0d5c-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="d0d5c-118">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="d0d5c-119">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="d0d5c-120">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="d0d5c-121">Phase 2: Aktivieren Sie das Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="d0d5c-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="d0d5c-122">Folgen Sie den Anweisungen unter [Phase 2 der Kennwortrückschreibung der Testumgebungsanleitungen](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="d0d5c-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="d0d5c-123">Sie müssen das Rückschreiben des Kennworts aktiviert haben, um das Kennwortzurücksetzen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="d0d5c-124">Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d0d5c-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="d0d5c-125">Konfigurieren Sie in dieser Phase die Kennwortzurücksetzung im Azure AD-Mandanten über die Gruppenmitgliedschaft, und überprüfen Sie dann, ob sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="d0d5c-126">Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="d0d5c-127">Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="d0d5c-128">Wählen Sie im Azure-Portal **Azure Active Directory**  >  **Gruppen**  >  **Neue Gruppe aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="d0d5c-129">Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="d0d5c-130">Wählen **Sie Mitglieder** aus, suchen und wählen Sie Benutzer **3** aus, wählen **Sie Auswählen** aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="d0d5c-131">Schließen Sie den Bereich **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="d0d5c-132">Wählen Sie Azure Active Directory linken Navigation  die Option Kennwortzurücksetzung aus.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="d0d5c-133">Wählen Sie im Bereich **Kennwort zurücksetzen, Eigenschaften** unter **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt** aus.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="d0d5c-134">Wählen **Sie Gruppe auswählen** aus, wählen Sie die Gruppe **PWReset** aus, und wählen Sie **dann Speichern**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="d0d5c-135">Schließen Sie die private Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-135">Close the private browser instance.</span></span>

<span data-ttu-id="d0d5c-136">Testen Sie als Nächstes die Kennwortzurücksetzung für das Benutzer 3-Konto.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="d0d5c-137">Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="d0d5c-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="d0d5c-138">Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 3 an.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="d0d5c-139">Wählen **Sie unter Weitere Informationen erforderlich** die Option Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="d0d5c-140">Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="d0d5c-141">Nachdem beide überprüft wurden, wählen **Sie Gut aussehen** aus, und schließen Sie dann die private Instanz des Browsers.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="d0d5c-142">Wechseln Sie in einer neuen privaten Browserinstanz zu [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="d0d5c-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="d0d5c-143">Geben Sie den Kontonamen Benutzer 3 ein, geben Sie die Zeichen aus dem CAPTCHA ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="d0d5c-144">Wählen **Sie für überprüfungsschritt 1** die Option **E-Mail meine alternative** E-Mail senden aus, und wählen Sie dann **E-Mail aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="d0d5c-145">Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="d0d5c-146">Geben **Sie unter Zurück in Ihr Konto** ein neues Kennwort für das Konto "Benutzer 3" ein, und wählen Sie dann Fertig stellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="d0d5c-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="d0d5c-147">Notieren Sie sich das geänderte Kennwort des Kontos von Benutzer 3, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="d0d5c-148">Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://portal.office.com](https://portal.office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 3 und dem neuen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="d0d5c-149">Die **Microsoft Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="d0d5c-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d0d5c-150">Next step</span></span>

<span data-ttu-id="d0d5c-151">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="d0d5c-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0d5c-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0d5c-152">See also</span></span>

[<span data-ttu-id="d0d5c-153">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d0d5c-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d0d5c-154">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d0d5c-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d0d5c-155">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d0d5c-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)