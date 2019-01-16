---
title: Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler administrator
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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer unternehmensumgebung Microsoft 365 Test zu schützen.
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867582"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8ac3c-103">Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler administrator</span><span class="sxs-lookup"><span data-stu-id="8ac3c-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8ac3c-p101">Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. In diesem Artikel wird beschrieben, wie mit Office 365-Cloud-App-Sicherheit und Azure AD bedingte Zugriffsrichtlinien globale Administratorkonten schützen.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="8ac3c-106">Es gibt zwei Phasen zum Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler Administrator:</span><span class="sxs-lookup"><span data-stu-id="8ac3c-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="8ac3c-107">Erstellen der testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="8ac3c-108">Schützen Sie Ihre dedizierten globale Administratorkonto ein.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-108">Protect your dedicated global administrator account.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8ac3c-110">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8ac3c-111">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8ac3c-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8ac3c-112">Wenn Sie auf einfache Weise mit den Mindestanforderungen globaler Administrator Kontoschutz testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8ac3c-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8ac3c-113">Wenn Sie in einer simulierten Enterprise globaler Administrator Kontoschutz testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8ac3c-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ac3c-p102">Testen globale Administratorkonto ein Protection erfordert nicht den simulierten Enterprise Test Environment, einem simulierten Intranet umfasst Folgendes mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie globaler Administrator Kontoschutz testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="8ac3c-116">Phase 2: Konfigurieren von Cloud-App Sicherheits- und bedingte Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8ac3c-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="8ac3c-117">Erstellen Sie zunächst eine Richtlinie Office 365-Cloud-App-Sicherheit, um globaler Administrator Kontoaktivitäten überwachen und Senden von Benachrichtigungen an die e-Mail-Adresse des globalen Administratorkontos.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="8ac3c-118">Melden Sie sich bei der Office-Portal unter [http://portal.office.com](http://portal.office.com) mit Ihrer globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-118">Sign in to the Office portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="8ac3c-p103">Klicken Sie auf die Kachel " **Admin** ". Klicken Sie auf die Registerkarte **Office Admin Center** auf **Zentriert Admin > Sicherheit und Compliance**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="8ac3c-121">Klicken Sie im linken Navigationsbereich auf **Warnungen > Erweiterte Warnungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="8ac3c-122">Klicken Sie auf der Seite **Erweiterte Warnungen verwalten** auf **Office 365 Cloud App Security aktivieren**, und klicken Sie dann auf **Zu Office 365 Cloud App Security wechseln**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="8ac3c-123">Klicken Sie auf der neuen **Dashboard**-Registerkarte auf **Steuern > Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="8ac3c-124">Klicken Sie auf der Seite **Richtlinie** auf **Richtlinie erstellen**, und klicken Sie dann auf **Aktivitätsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="8ac3c-125">Geben Sie im Feld **Richtlinienname** den Namen **Administrative Aktivität** ein.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="8ac3c-126">Klicken Sie unter **Schweregrad der Richtlinie** auf **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="8ac3c-127">Klicken Sie unter **Kategorie** auf **Privilegierte Konten**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="8ac3c-128">Klicken Sie in **Filter für die Richtlinie erstellen** unter **Aktivitäten entspricht allen folgenden Kriterien** auf **Administrative Aktivität**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="8ac3c-p104">Klicken Sie unter **Benachrichtigungen** auf **Benachrichtigung als E-Mail senden**. Geben Sie unter **An** die E-Mail-Adresse Ihres globalen Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="8ac3c-131">Klicken Sie unten auf der Seite auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="8ac3c-132">Schließen Sie die Registerkarte **Dashboard** .</span><span class="sxs-lookup"><span data-stu-id="8ac3c-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="8ac3c-133">Im nächsten Schritt erstellen Sie ein neues Benutzerkonto als dedizierten globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="8ac3c-134">Klicken Sie auf der Registerkarte **Office Admin Center** unter **aktive Benutzer**auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="8ac3c-135">Geben Sie auf der Seite **Neuer Benutzer** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Username**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="8ac3c-p105">Klicken Sie auf **Kennwort**, klicken Sie auf **mich das Kennwort zu erstellen**, und geben Sie ein sicheres Kennwort. Tragen Sie das Kennwort für das neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="8ac3c-138">Deaktivieren **Sie dieser Benutzer ändern ihres Kennworts beim erstmaligen Anmelden ist**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="8ac3c-139">Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="8ac3c-140">Klicken Sie auf **Produktlizenzen**, und schalten Sie die **Enterprise-Mobilität + Sicherheit E5** und **Office 365 Enterprise E5 Lizenzen** .</span><span class="sxs-lookup"><span data-stu-id="8ac3c-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="8ac3c-141">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-141">Click **Add**.</span></span>
8. <span data-ttu-id="8ac3c-142">Klicken Sie auf die **Benutzer Seite hinzugefügt wurde**deaktivieren Sie **das Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="8ac3c-143">Im nächsten Schritt erstellen Sie eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie das Konto DedicatedAdmin hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="8ac3c-144">Klicken Sie auf das Gruppensymbol im linken Navigationsbereich auf der Registerkarte **Office-Verwaltungskonsole** , und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="8ac3c-145">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="8ac3c-146">Geben Sie auf der Seite **Neue Gruppe** **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="8ac3c-147">Klicken Sie auf **Select Besitzer** auf das globale Administratorkonto ein, und klicken Sie dann auf **Hinzufügen > Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="8ac3c-148">Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="8ac3c-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="8ac3c-149">Klicken Sie auf der Seite **GlobalAdmins** auf **Element bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="8ac3c-150">In der Liste, klicken Sie auf das Konto **DedicatedAdmin** , und klicken Sie dann auf **Speichern > Schließen > Schließen > Administrationscenter**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="8ac3c-151">Erstellen Sie als Nächstes bedingte Zugriffsrichtlinien für globale Administratorkonten mehrstufige Authentifizierung erforderlich ist und Authentifizierung verweigern, wenn das Risiko-Anmeldung Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="8ac3c-152">Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten mehrstufiger Authentifizierung das verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="8ac3c-153">Wechseln Sie in einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8ac3c-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8ac3c-154">Klicken Sie auf **Azure Active Directory > bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="8ac3c-155">Klicken Sie auf das Blade **bedingte – Richtlinien Zugriff** auf **Baseline-Richtlinie: erfordern mehrstufiger Authentifizierung das für Administratoren (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="8ac3c-p106">Klicken Sie auf das Blade **... Baseline-Richtlinien** auf **Verwenden Sie die Richtlinie sofort > Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="8ac3c-158">In diesem zweiten Richtlinie blockiert den Zugriff auf globaler Administrator Kontoauthentifizierung bei das Anmeldung Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="8ac3c-159">Klicken Sie auf das Blade **bedingte – Richtlinien Zugriff** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="8ac3c-160">Geben Sie auf der Blade **New** **globale Administratoren** im **Feld Name**ein.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="8ac3c-161">Klicken Sie im Abschnitt **Zuordnungen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="8ac3c-162">Klicken Sie auf der Registerkarte **einschließen** von der Blade- **Benutzer und Gruppen** auf **Benutzer und Gruppen auswählen > Benutzer und Gruppen > Wählen Sie**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="8ac3c-163">Klicken Sie auf das Blade **Wählen Sie** auf der **GlobalAdmins > Wählen Sie > Fertig**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="8ac3c-164">Klicken Sie im Abschnitt **Zuordnungen** auf **Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="8ac3c-165">Klicken Sie in der Blade **Bedingungen** auf **Anmelden Risiko**, klicken Sie auf **Ja** , für die **Konfiguration**, klicken Sie auf **Hoch** und **Mittel**und klicken Sie dann auf **auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="8ac3c-166">Klicken Sie im Abschnitt **Zugreifen auf Steuerelemente** von der **neu** Blade auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="8ac3c-167">Klicken Sie in der **Grant** -Blade auf **Blockieren Sie den Zugriff**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="8ac3c-168">Klicken Sie auf das Blade **neu** **auf** für die **Richtlinie zu aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="8ac3c-169">Schließen Sie die Registerkarten **Azure-Portal** und **Office-Verwaltungskonsole** .</span><span class="sxs-lookup"><span data-stu-id="8ac3c-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="8ac3c-p107">Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Konto DedicatedAdmin. Sie werden aufgefordert, auf das Benutzerkonto mehrstufiger Authentifizierung das konfigurieren. Dies veranschaulicht, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="8ac3c-173">Finden Sie unter der [globalen Administratorkonten Protect](identity-designate-protect-admin-accounts.md) Schritt in der Phase Identität Informationen und Links zu Ihrer globalen Administratorkonten in der Produktion zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8ac3c-174">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8ac3c-174">Next step</span></span>

<span data-ttu-id="8ac3c-175">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="8ac3c-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ac3c-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ac3c-176">See also</span></span>

[<span data-ttu-id="8ac3c-177">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="8ac3c-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8ac3c-178">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8ac3c-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8ac3c-179">Bereitstellung von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8ac3c-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8ac3c-180">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8ac3c-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
