---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Führen Sie die folgenden Schritte aus, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290858"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="124fe-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="124fe-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="124fe-104">Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="124fe-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="124fe-105">In diesem Artikel wird beschrieben, wie Sie Office 365 Cloud App Security und Azure AD Conditional Access-Richtlinien zum Schutz globaler Administratorkonten verwenden.</span><span class="sxs-lookup"><span data-stu-id="124fe-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="124fe-106">Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="124fe-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="124fe-107">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="124fe-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="124fe-108">Schützen Sie Ihr dediziertes globales Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="124fe-108">Protect your dedicated global administrator account.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="124fe-110">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="124fe-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="124fe-111">In der Microsoft 365 Enterprise-Testumgebung werden E5-Versionen von Office 365 und Enterprise Management + Security (EMS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="124fe-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="124fe-112">Die Office 365 Cloud App-Sicherheitsfunktion ist nur in der E5-Version von Office 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="124fe-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="124fe-113">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="124fe-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="124fe-114">Wenn Sie nur den Schutz globaler Administratorkonten auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="124fe-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="124fe-115">Wenn Sie den Schutz globaler Administratorkonten in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="124fe-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="124fe-116">Das Testen des globalen Administratorkonto Schutzes erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="124fe-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="124fe-117">Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="124fe-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="124fe-118">Phase 2: Konfigurieren von Sicherheits-und bedingten Zugriffsrichtlinien für Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="124fe-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="124fe-119">Erstellen Sie zunächst eine Office 365 Cloud App-Sicherheitsrichtlinie, um die globale Administratorkonto Aktivität zu überwachen und Warnungen an die e-Mail-Adresse Ihres globalen Administratorkontos zu senden.</span><span class="sxs-lookup"><span data-stu-id="124fe-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="124fe-120">Melden Sie sich beim [Office 365 Security _AMP_ Compliance-Portal](https://protection.office.com/) mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="124fe-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="124fe-121">Klicken Sie im linken Navigationsbereich auf **Warnungen > Erweiterte Warnungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="124fe-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="124fe-122">Klicken Sie auf der Seite **Erweiterte Warnungen verwalten** auf **Office 365 Cloud App Security aktivieren**, und klicken Sie dann auf **Zu Office 365 Cloud App Security wechseln**.</span><span class="sxs-lookup"><span data-stu-id="124fe-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="124fe-123">Klicken Sie auf der neuen **Dashboard**-Registerkarte auf **Steuern > Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="124fe-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="124fe-124">Klicken Sie auf der Seite **Richtlinie** auf **Richtlinie erstellen**, und klicken Sie dann auf **Aktivitätsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="124fe-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="124fe-125">Geben Sie im Feld **Richtlinienname** den Namen **Administrative Aktivität** ein.</span><span class="sxs-lookup"><span data-stu-id="124fe-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="124fe-126">Klicken Sie unter **Schweregrad der Richtlinie** auf **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="124fe-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="124fe-127">Klicken Sie unter **Kategorie** auf **Privilegierte Konten**.</span><span class="sxs-lookup"><span data-stu-id="124fe-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="124fe-128">Klicken Sie in **Filter für die Richtlinie erstellen** unter **Aktivitäten entspricht allen folgenden Kriterien** auf **Administrative Aktivität**.</span><span class="sxs-lookup"><span data-stu-id="124fe-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="124fe-p104">Klicken Sie unter **Benachrichtigungen** auf **Benachrichtigung als E-Mail senden**. Geben Sie unter **An** die E-Mail-Adresse Ihres globalen Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="124fe-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="124fe-131">Klicken Sie unten auf der Seite auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="124fe-132">Schließt die Registerkarte **Dashboard** .</span><span class="sxs-lookup"><span data-stu-id="124fe-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="124fe-133">Als Nächstes erstellen Sie ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="124fe-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="124fe-134">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="124fe-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="124fe-135">Klicken Sie unter **aktive Benutzer**auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="124fe-136">Geben Sie auf der Seite **neuer Benutzer** **DedicatedAdmin** unter **Vorname**, **Anzeigename**und **Benutzer**Name ein.</span><span class="sxs-lookup"><span data-stu-id="124fe-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="124fe-137">Klicken Sie auf **Kennwort**, aktivieren Sie **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="124fe-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="124fe-138">NoTieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="124fe-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="124fe-139">Deaktivieren **Sie dieses Benutzerkennwort bei der ersten Anmeldung ändern**.</span><span class="sxs-lookup"><span data-stu-id="124fe-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="124fe-140">Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.</span><span class="sxs-lookup"><span data-stu-id="124fe-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="124fe-141">Klicken Sie auf **Produktlizenzen**und dann auf **Enterprise Mobility + Security e5** und **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="124fe-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="124fe-142">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-142">Click **Add**.</span></span>
9. <span data-ttu-id="124fe-143">Deaktivieren Sie auf der **Seite hinzugefügte Benutzer**das **Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="124fe-144">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="124fe-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="124fe-145">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der linken Navigationsleiste auf das Symbol Gruppen, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="124fe-146">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="124fe-147">Geben Sie auf der Seite **neue Gruppe** **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="124fe-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="124fe-148">Klicken Sie auf **Besitzer auswählen** , klicken Sie auf ihr globales Administratorkonto, und klicken Sie dann auf **> schließen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="124fe-149">Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="124fe-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="124fe-150">Klicken Sie auf der Seite **GlobalAdmins** auf **für Mitglied bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="124fe-151">Klicken Sie in der Liste auf das **DedicatedAdmin** -Konto, und klicken Sie dann auf **Speichern _GT_ schließen _GT_ schließen > Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="124fe-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="124fe-152">Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um die mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="124fe-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="124fe-153">Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="124fe-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="124fe-154">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="124fe-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="124fe-155">Klicken Sie auf **Azure Active Directory _GT_ Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="124fe-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="124fe-156">Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **Basisrichtlinie: MFA für Administratoren (Vorschau) erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="124fe-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="124fe-157">In den **Basisrichtlinien...**</span><span class="sxs-lookup"><span data-stu-id="124fe-157">On the **Baseline policies…**</span></span> <span data-ttu-id="124fe-158">auf **Richtlinie sofort _GT_ speichern**.</span><span class="sxs-lookup"><span data-stu-id="124fe-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="124fe-159">Diese zweite Richtlinie blockiert den Zugriff auf die globale Administratorkonto Authentifizierung, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="124fe-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="124fe-160">Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="124fe-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="124fe-161">Geben Sie auf dem **neuen** Blatt **globale Administratoren** in **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="124fe-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="124fe-162">Klicken Sie \*\*\*\* im Abschnitt Zuweisungen auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="124fe-163">Klicken Sie auf der Registerkarte " **einbeziehen** " des Blades " **Benutzer und Gruppen** " auf Benutzer und Gruppen **_GT_ Benutzer und Gruppen > auswählen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="124fe-164">Klicken Sie auf dem Blade **auswählen** auf die **GlobalAdmins > wählen Sie > fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="124fe-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="124fe-165">Klicken Sie \*\*\*\* im Abschnitt Zuweisungen auf **Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="124fe-166">Klicken Sie auf dem Blatt **Bedingungen** auf **Anmelde Risiko**, klicken Sie **auf Ja** , um zu **Konfigurieren**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="124fe-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="124fe-167">Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Blatts auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="124fe-168">Klicken Sie auf der **Grant** -Blade auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="124fe-169">Klicken Sie auf dem **neuen** Blade \*\*\*\* auf für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="124fe-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="124fe-170">Beenden Sie die Registerkarten **Azure Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="124fe-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="124fe-171">Um die erste Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="124fe-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="124fe-172">Sie sollten aufgefordert werden, MFA für das Benutzerkonto zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="124fe-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="124fe-173">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="124fe-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="124fe-174">Weitere Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md#identity-global-admin) .</span><span class="sxs-lookup"><span data-stu-id="124fe-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="124fe-175">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="124fe-175">Next step</span></span>

<span data-ttu-id="124fe-176">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="124fe-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="124fe-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="124fe-177">See also</span></span>

[<span data-ttu-id="124fe-178">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="124fe-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="124fe-179">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="124fe-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="124fe-180">Microsoft 365 Enterprise-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="124fe-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="124fe-181">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="124fe-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
