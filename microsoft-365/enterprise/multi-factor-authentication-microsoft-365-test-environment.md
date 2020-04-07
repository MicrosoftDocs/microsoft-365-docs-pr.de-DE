---
title: Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die mehrstufige Authentifizierung mit Textnachrichten, die an ein Smartphone in Ihrer Microsoft 365 Enterprise-Testumgebung gesendet werden.
ms.openlocfilehash: b17c6b3b39bebaff2737ea5e9bb198beef00844c
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153880"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="35877-103">Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="35877-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="35877-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="35877-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="35877-105">Für eine zusätzliche Sicherheitsstufe für die Anmeldung bei Microsoft 365 oder für einen Dienst oder eine Anwendung, die den Azure AD Mandanten für Ihr Abonnement verwendet, können Sie die Azure-mehrstufige Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen eines Kontos erfordert.</span><span class="sxs-lookup"><span data-stu-id="35877-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="35877-106">Bei der mehrstufigen Authentifizierung müssen Benutzer einen Telefonanruf bestätigen, einen in einer Textnachricht gesendeten Bestätigungscode eingeben oder ein App-Kennwort auf dem Smartphone angeben, nachdem Sie die entsprechenden Kennwörter korrekt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="35877-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="35877-107">Eine Anmeldung ist nur möglich, nachdem diese zweite Authentifizierungsstufe passiert wurde.</span><span class="sxs-lookup"><span data-stu-id="35877-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="35877-108">In diesem Artikel wird beschrieben, wie Sie die Textnachrichten basierte Authentifizierung für ein bestimmtes Benutzerkonto aktivieren und testen.</span><span class="sxs-lookup"><span data-stu-id="35877-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="35877-109">Es gibt zwei Phasen zum Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="35877-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="35877-110">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="35877-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="35877-111">Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="35877-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="35877-112">Aktivieren und testen Sie die mehrstufige Authentifizierung mit einer Richtlinie für bedingten Zugriff (optional).</span><span class="sxs-lookup"><span data-stu-id="35877-112">Enable and test multi-factor authentication with a Conditional Access policy (optional).</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="35877-114">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="35877-114">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="35877-115">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="35877-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="35877-116">Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="35877-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="35877-117">Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="35877-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35877-118">Zum Testen der mehrstufigen Authentifizierung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="35877-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="35877-119">Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="35877-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="35877-120">Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="35877-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="35877-121">Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="35877-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="35877-122">Öffnen Sie eine separate private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich dann mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="35877-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="35877-123">Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="35877-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="35877-124">Klicken Sie im Bereich aktive Benutzer auf **mehr**stufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35877-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="35877-125">Wählen Sie in der Liste das Konto **Benutzer 2** aus.</span><span class="sxs-lookup"><span data-stu-id="35877-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="35877-126">Klicken Sie im Abschnitt **Benutzer 2** unter **QuickSteps** auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="35877-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="35877-127">Klicken Sie im Dialogfeld **Informationen zum Aktivieren von mehrstufiger Aktualisierung** auf **Multi-Factor Authentication aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="35877-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="35877-128">Klicken Sie im Dialogfeld **Updates erfolgreich** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="35877-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="35877-129">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der oberen rechten Ecke auf das Symbol für das Benutzerkonto, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="35877-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="35877-130">Schließen Sie Ihre Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="35877-130">Close your browser instance.</span></span>
   
<span data-ttu-id="35877-131">Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="35877-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="35877-132">Öffnen Sie eine neue private Instanz Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="35877-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="35877-133">Wechseln Sie zum Office 365 Portal ([https://portal.office.com](https://portal.office.com)), und melden Sie sich mit dem Kontonamen und Kennwort des Benutzers 2 an.</span><span class="sxs-lookup"><span data-stu-id="35877-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="35877-134">Nachdem Sie sich angemeldet haben, werden Sie aufgefordert, das Konto einzurichten, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="35877-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="35877-135">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="35877-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="35877-136">Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="35877-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="35877-137">Wählen Sie Ihr Land oder Ihre Region aus.</span><span class="sxs-lookup"><span data-stu-id="35877-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="35877-138">Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="35877-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="35877-139">Klicken Sie in **Methode**auf **Senden Sie mir einen Code per Textnachricht**.</span><span class="sxs-lookup"><span data-stu-id="35877-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="35877-140">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="35877-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="35877-141">Geben Sie den Verifizierungscode aus der Textnachricht ein, die an Ihr Smartphone gesendet wurde, und klicken Sie dann auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="35877-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="35877-142">Zeichnen Sie das auf der Seite **Schritt 3: Keep your existing applications** angezeigte App-Kennwort für das Konto „Benutzer 2“ an einem sicheren Ort auf, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="35877-142">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="35877-p104">Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie das ursprüngliche Kennwort und dann zwei Mal ein neues Kennwort ein, und klicken Sie dann auf **Kennwort ändern und anmelden**. Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="35877-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="35877-146">Das Office-Portal für Benutzer 2 sollte auf der Registerkarte **Microsoft Office Startseite** Ihres Browsers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="35877-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="35877-147">Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="35877-147">Phase 3: Enable and test multi-factor authentication with a Conditional Access policy</span></span>

<span data-ttu-id="35877-148">*Diese Phase kann nur für eine Microsoft 365 Enterprise-Testumgebung verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="35877-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="35877-149">In dieser Phase aktivieren Sie die mehrstufige Authentifizierung für das Konto "Benutzer 3" mithilfe einer Gruppenrichtlinie und einer Richtlinie für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="35877-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a Conditional Access policy.</span></span>

<span data-ttu-id="35877-150">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen MFAUsers, und fügen Sie das Benutzerkonto 3 hinzu.</span><span class="sxs-lookup"><span data-stu-id="35877-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="35877-151">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Gruppen** , und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="35877-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="35877-152">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="35877-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="35877-153">Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="35877-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="35877-154">Klicken Sie im Bereich **Grundlagen einrichten** auf **Gruppe erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="35877-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="35877-155">Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **MFAUsers**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="35877-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="35877-156">Klicken Sie in der Liste der Gruppen auf die Gruppe **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="35877-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="35877-157">Klicken Sie im Bereich **MFAUsers** auf **Mitglieder**, und klicken Sie dann auf **Alle anzeigen und Mitglieder verwalten**.</span><span class="sxs-lookup"><span data-stu-id="35877-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="35877-158">Klicken Sie im Bereich **MFAUsers** auf **Mitglieder hinzufügen**, wählen Sie das Konto **Benutzer 3** aus, und klicken Sie dann auf **speichern > schließen > schließen**.</span><span class="sxs-lookup"><span data-stu-id="35877-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="35877-159">Erstellen Sie als nächstes eine Richtlinie für den bedingten Zugriff, um die mehrstufige Authentifizierung für Mitglieder der MFAUsers-Gruppe zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="35877-159">Next, create a Conditional Access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="35877-160">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="35877-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="35877-161">Klicken Sie auf **Azure Active Directory > Sicherheits > bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="35877-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="35877-162">Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="35877-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="35877-163">Geben Sie im **neuen** Bereich **MFA für Benutzerkonten** unter **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="35877-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="35877-164">Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="35877-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="35877-165">Klicken Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** auf Benutzer und Gruppen **> Benutzer und Gruppen auswählen > auswählen**.</span><span class="sxs-lookup"><span data-stu-id="35877-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="35877-166">Klicken Sie im Bereich **auswählen** auf die Gruppe **MFAUsers** , und klicken Sie dann auf **> fertig wählen**.</span><span class="sxs-lookup"><span data-stu-id="35877-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="35877-167">Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Bereichs auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="35877-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="35877-168">Klicken Sie im Bereich **Grant** auf **mehrstufige Authentifizierung erfordern**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="35877-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="35877-169">Klicken Sie im Bereich **neu** **auf** für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="35877-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="35877-170">Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="35877-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="35877-171">Um diese Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Benutzerkonto 3 an.</span><span class="sxs-lookup"><span data-stu-id="35877-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="35877-172">Sie sollten aufgefordert werden, MFA zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="35877-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="35877-173">Dies zeigt, dass die MFAUsers-Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="35877-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="35877-174">Informationen und Links zum Bereitstellen der mehrstufigen Authentifizierung in der Produktionsumgebung finden Sie im Schritt zum [Einrichten der mehr](identity-secure-user-sign-ins.md#identity-mfa) stufigen Authentifizierung in der Identitäts Phase.</span><span class="sxs-lookup"><span data-stu-id="35877-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="35877-175">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="35877-175">Next step</span></span>

<span data-ttu-id="35877-176">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="35877-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="35877-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35877-177">See also</span></span>

[<span data-ttu-id="35877-178">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="35877-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="35877-179">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35877-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35877-180">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="35877-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="35877-181">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35877-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
