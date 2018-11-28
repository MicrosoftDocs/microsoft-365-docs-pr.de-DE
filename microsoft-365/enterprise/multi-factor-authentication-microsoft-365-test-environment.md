---
title: Mehrstufige Authentifizierung für Microsoft 365 Unternehmen test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie mehrstufige Authentifizierung über Textnachrichten gesendet, um ein Smartphone in Ihrer Microsoft 365 Enterprise-testumgebung.
ms.openlocfilehash: 5ee4eca556d388b3fa8f7150626f919b07693c91
ms.sourcegitcommit: 42e4d280b562304335efc93787c89992504c5823
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538712"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e3a11-103">Mehrstufige Authentifizierung für Microsoft 365 Unternehmen test Environment.</span><span class="sxs-lookup"><span data-stu-id="e3a11-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e3a11-p101">Für eine zusätzliche Sicherheitsebene für die Anmeldung Office 365 oder eine beliebige Dienst oder einer Anwendung, die für Ihre Organisation den Azure AD-Mandanten verwendet, können Sie Azure mehrstufige Authentifizierung, die erforderlich sind mehr als nur einen Benutzernamen und das Kennwort ein, vergewissern Sie sich ein Konto. Mehrstufige Authentifizierung müssen Benutzer ein Telefonanrufs zu bestätigen, geben Sie einen Überprüfungscode in einer Textnachricht gesendet oder geben Sie ein app-Kennwort in ihrer Smartphones nach Eingabe der Kennwörter, ordnungsgemäß. Sie können erst nach diesem zweiten Authentifizierung Faktor erfüllt wurden anmelden.</span><span class="sxs-lookup"><span data-stu-id="e3a11-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="e3a11-107">In diesem Artikel wird beschrieben, wie aktivieren und Testen Sie die Text-basierten Authentifizierung für ein bestimmtes Konto.</span><span class="sxs-lookup"><span data-stu-id="e3a11-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="e3a11-108">Es gibt zwei Phasen mehrstufige Authentifizierung für ein Konto in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:</span><span class="sxs-lookup"><span data-stu-id="e3a11-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="e3a11-109">Erstellen der testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e3a11-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="e3a11-110">Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="e3a11-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e3a11-112">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e3a11-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e3a11-113">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3a11-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e3a11-114">Wenn Sie auf einfache Weise mit den Mindestanforderungen mehrstufige Authentifizierung testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e3a11-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e3a11-115">Wenn Sie in einer simulierten Enterprise mehrstufige Authentifizierung testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e3a11-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3a11-p102">Testen der mehrstufigen Authentifizierung erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie mehrstufige Authentifizierung testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3a11-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="e3a11-118">Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“</span><span class="sxs-lookup"><span data-stu-id="e3a11-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="e3a11-119">Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="e3a11-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="e3a11-120">Öffnen Sie eine separate, private Instanz des Browsers, fahren Sie mit dem Office-Portal ([https://office.com](https://office.com)), und melden Sie sich mit Ihrem globale Administratorkonto ein.</span><span class="sxs-lookup"><span data-stu-id="e3a11-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="e3a11-121">Klicken Sie auf der Hauptportalseite auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="e3a11-122">Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="e3a11-123">Klicken Sie im Bereich aktive Benutzer klicken Sie auf **mehr > Multi-Factor Authentication Setup**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="e3a11-124">Wählen Sie in der Liste der **Benutzer 2** -Konto aus.</span><span class="sxs-lookup"><span data-stu-id="e3a11-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="e3a11-125">Klicken Sie im Abschnitt **Benutzer 2** unter **QuickSteps** auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="e3a11-126">Klicken Sie im Dialogfeld **Informationen zum Aktivieren von mehrstufiger Aktualisierung** auf **Multi-Factor Authentication aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="e3a11-127">Klicken Sie auf **Schließen**, klicken Sie im Dialogfeld **erfolgreich aktualisiert** .</span><span class="sxs-lookup"><span data-stu-id="e3a11-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="e3a11-128">Klicken Sie auf der Registerkarte **Microsoft Office-Starts** auf das Benutzerkontosymbol in der oberen rechten Ecke, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="e3a11-129">Schließen Sie Ihre Browserinstanz.</span><span class="sxs-lookup"><span data-stu-id="e3a11-129">Close your browser instance.</span></span>
   
<span data-ttu-id="e3a11-130">Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="e3a11-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="e3a11-131">Öffnen Sie eine neue Instanz des Browsers private.</span><span class="sxs-lookup"><span data-stu-id="e3a11-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="e3a11-132">Wechseln Sie zu der Office-Portal ([https://office.com](https://office.com)) und melden Sie sich mit dem Konto Benutzer 2 (Benutzer2 @\<Name der Organisation >. onmicrosoft.com) und das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="e3a11-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="e3a11-p103">Nach der Anmeldung werden Sie aufgefordert, richten Sie das Konto für Weitere Informationen ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="e3a11-135">Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="e3a11-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="e3a11-136">Wählen Sie Ihr Land oder Ihre Region aus.</span><span class="sxs-lookup"><span data-stu-id="e3a11-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="e3a11-137">Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="e3a11-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="e3a11-138">Klicken Sie in- **Methode**auf **mich senden einen Code über Textnachricht**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="e3a11-139">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="e3a11-140">Geben Sie den Verifizierungscode aus der Textnachricht ein, die an Ihr Smartphone gesendet wurde, und klicken Sie dann auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="e3a11-141">Zeichnen Sie das auf der Seite **Schritt 3: Keep your existing applications** angezeigte App-Kennwort für das Konto „Benutzer 2“ an einem sicheren Ort auf, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="e3a11-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="e3a11-p104">Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie das ursprüngliche Kennwort und dann zwei Mal ein neues Kennwort ein, und klicken Sie dann auf **Kennwort ändern und anmelden**. Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="e3a11-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="e3a11-145">Das Office-Portal sollte für Benutzer 2 auf der Registerkarte **Microsoft Office Home** des Browsers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3a11-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="e3a11-146">Finden Sie im Schritt [Richten Sie mehrstufige Authentifizierung](identity-multi-factor-authentication.md) in der Phase Identität Informationen und Links zu Multi-Factor Authentication in der Produktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e3a11-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="e3a11-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e3a11-147">Next step</span></span>

<span data-ttu-id="e3a11-148">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="e3a11-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3a11-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3a11-149">See also</span></span>

[<span data-ttu-id="e3a11-150">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="e3a11-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e3a11-151">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3a11-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e3a11-152">Bereitstellung von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3a11-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e3a11-153">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3a11-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
