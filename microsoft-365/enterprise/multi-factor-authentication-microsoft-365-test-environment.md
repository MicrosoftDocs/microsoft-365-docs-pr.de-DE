---
title: Mehrstufige Authentifizierung in Microsoft 365 für die Enterprise-Testumgebung
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
- seo-marvel-apr2020
description: Konfigurieren Sie die mehrstufige Authentifizierung mithilfe von Textnachrichten, die an ein Smartphone in Ihrer Microsoft 365 for Enterprise-Testumgebung gesendet werden.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558442"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="48ff2-103">Mehrstufige Authentifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="48ff2-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="48ff2-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="48ff2-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="48ff2-105">Für eine zusätzliche Sicherheitsstufe für die Anmeldung bei Microsoft 365 oder für einen Dienst oder eine Anwendung, die den Azure AD Mandanten für Ihr Abonnement verwendet, können Sie Azure AD mehrstufige Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen eines Kontos benötigt.</span><span class="sxs-lookup"><span data-stu-id="48ff2-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="48ff2-106">Bei der mehrstufigen Authentifizierung müssen Benutzer einen Telefonanruf bestätigen, einen in einer Textnachricht gesendeten Überprüfungscode eingeben oder die Authentifizierung mit einer APP auf ihren Smartphones überprüfen, nachdem Sie Ihre Kennwörter korrekt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="48ff2-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="48ff2-107">Sie können sich erst anmelden, nachdem dieser zweite Authentifizierungs Faktor erfüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="48ff2-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="48ff2-108">In diesem Artikel wird beschrieben, wie Sie die Textnachrichten basierte Authentifizierung für ein bestimmtes Benutzerkonto aktivieren und testen.</span><span class="sxs-lookup"><span data-stu-id="48ff2-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="48ff2-109">Das Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen und eine dritte optionale Phase:</span><span class="sxs-lookup"><span data-stu-id="48ff2-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="48ff2-110">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="48ff2-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="48ff2-111">Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="48ff2-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="48ff2-112">Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="48ff2-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="48ff2-114">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="48ff2-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="48ff2-115">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="48ff2-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="48ff2-116">Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="48ff2-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="48ff2-117">Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="48ff2-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="48ff2-118">Zum Testen der mehrstufigen Authentifizierung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="48ff2-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="48ff2-119">Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="48ff2-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="48ff2-120">Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="48ff2-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="48ff2-121">Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="48ff2-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="48ff2-122">Öffnen Sie eine separate private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ( [https://portal.microsoft.com](https://portal.microsoft.com) ), und melden Sie sich dann mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="48ff2-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="48ff2-123">Wählen Sie im linken Navigationsbereich **Benutzer**  >  **aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="48ff2-124">Wählen Sie im Bereich aktive Benutzer die Option **mehrstufige Authentifizierung** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="48ff2-125">Wählen Sie in der Liste das Konto **Benutzer 2** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="48ff2-126">Wählen Sie im Abschnitt **Benutzer 2** unter **schnell Schritte** die Option **aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="48ff2-127">Wählen Sie im Dialogfeld **Informationen zum Aktivieren der mehr** stufigen Authentifizierung die Option mehrstufige **Authentifizierung aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="48ff2-128">Wählen Sie im Dialogfeld **Updates erfolgreich** die Option **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="48ff2-129">Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** das Benutzerkonto Symbol in der oberen rechten Ecke aus, und wählen Sie dann **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="48ff2-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="48ff2-130">Schließen Sie Ihre Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="48ff2-130">Close your browser instance.</span></span>
   
<span data-ttu-id="48ff2-131">Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="48ff2-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="48ff2-132">Öffnen Sie eine neue private Instanz Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="48ff2-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="48ff2-133">Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com) , und melden Sie sich mit dem Kontonamen und Kennwort des Benutzers 2 an.</span><span class="sxs-lookup"><span data-stu-id="48ff2-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="48ff2-134">Nachdem Sie sich angemeldet haben, werden Sie aufgefordert, das Konto einzurichten, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="48ff2-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="48ff2-135">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="48ff2-136">Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="48ff2-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="48ff2-137">Wählen Sie Ihr Land oder Ihre Region aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="48ff2-138">Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="48ff2-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="48ff2-139">Wählen **Method** Sie unter Methode **die Option mir einen Code per Textnachricht senden** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="48ff2-140">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="48ff2-141">Geben Sie den Überprüfungscode aus der auf dem Smartphone empfangenen Textnachricht ein, und wählen Sie dann **überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="48ff2-142">Wählen Sie auf der Seite **Schritt 3: vorhandene Anwendungen beibehalten** die Option **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="48ff2-143">Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="48ff2-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="48ff2-144">Geben Sie das ursprüngliche Kennwort und ein neues Kennwort zweimal ein, und wählen Sie dann **Kennwort aktualisieren aus, und melden Sie sich an**.</span><span class="sxs-lookup"><span data-stu-id="48ff2-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="48ff2-145">Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="48ff2-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="48ff2-146">Das Office-Portal für Benutzer 2 sollte auf der Registerkarte **Microsoft Office Startseite** Ihres Browsers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="48ff2-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="48ff2-147">Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="48ff2-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="48ff2-148">*Diese Phase kann nur für eine Microsoft 365 für Enterprise-Testumgebung verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="48ff2-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="48ff2-149">In dieser Phase aktivieren Sie die mehrstufige Authentifizierung für das Konto "Benutzer 3" mithilfe einer Gruppenrichtlinie und einer Richtlinie für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="48ff2-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="48ff2-150">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen MFAUsers, und fügen Sie das Benutzerkonto 3 hinzu.</span><span class="sxs-lookup"><span data-stu-id="48ff2-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="48ff2-151">Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich die Option **Gruppen** aus, und wählen Sie dann **Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="48ff2-152">Wählen Sie **Gruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="48ff2-153">Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit** aus, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="48ff2-154">Wählen Sie im Bereich **Grundlagen einrichten die** Option **Gruppe erstellen** aus, und wählen Sie dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="48ff2-155">Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **MFAUsers** ein, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="48ff2-156">Wählen Sie in der Liste der Gruppen die Gruppe **MFAUsers** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="48ff2-157">Wählen Sie im Bereich **MFAUsers** die Option **Mitglieder** aus, und wählen Sie dann **Alle anzeigen und Mitglieder verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="48ff2-158">Wählen Sie im Bereich **MFAUsers** die Option **Mitglieder hinzufügen** aus, wählen Sie das Konto **Benutzer 3** aus, und wählen Sie dann **Save**  >  **Close**  >  **Close** speichern aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="48ff2-159">Erstellen Sie als nächstes eine Richtlinie für den bedingten Zugriff, um die mehrstufige Authentifizierung für Mitglieder der MFAUsers-Gruppe zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="48ff2-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="48ff2-160">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="48ff2-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="48ff2-161">Wählen Sie **Azure Active Directory**  >  **Sicherheits**  >  **bedingten Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="48ff2-162">Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="48ff2-163">Geben Sie im **neuen** Bereich **MFA für Benutzerkonten** in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="48ff2-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="48ff2-164">Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="48ff2-165">Wählen Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** die Option Benutzer und **Gruppen**  >  **Benutzer**  >  **und Gruppen** auswählen aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="48ff2-166">Wählen Sie im Bereich **auswählen** die Gruppe **MFAUsers** aus, **und wählen Sie** dann  >  **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="48ff2-167">Wählen Sie im Bereich **Zugriffssteuerung** des **neuen** Bereichs die Option **Grant** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="48ff2-168">Wählen Sie im Bereich **Grant** die Option **mehrstufige Authentifizierung erforderlich** aus, und wählen Sie dann **auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="48ff2-169">Wählen Sie im Bereich **neu** die **Option** für **Richtlinie aktivieren** aus, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="48ff2-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="48ff2-170">Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="48ff2-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="48ff2-171">Um diese Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Benutzerkonto 3 an.</span><span class="sxs-lookup"><span data-stu-id="48ff2-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="48ff2-172">Sie sollten aufgefordert werden, MFA zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="48ff2-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="48ff2-173">Dies zeigt, dass die MFAUsers-Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="48ff2-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="48ff2-174">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="48ff2-174">Next step</span></span>

<span data-ttu-id="48ff2-175">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="48ff2-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="48ff2-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ff2-176">See also</span></span>

[<span data-ttu-id="48ff2-177">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="48ff2-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="48ff2-178">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="48ff2-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="48ff2-179">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="48ff2-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="48ff2-180">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="48ff2-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
