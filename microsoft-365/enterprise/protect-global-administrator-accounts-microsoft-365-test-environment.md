---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 5447177c6581b69d48272ceef7718552ea84dc9d
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202226"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ef73c-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ef73c-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ef73c-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="ef73c-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ef73c-105">Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="ef73c-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="ef73c-106">In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.</span><span class="sxs-lookup"><span data-stu-id="ef73c-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="ef73c-107">Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="ef73c-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="ef73c-108">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="ef73c-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="ef73c-109">Schützen Sie Ihr dediziertes globales Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="ef73c-109">Protect your dedicated global administrator account.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ef73c-111">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ef73c-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ef73c-112">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ef73c-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ef73c-113">Wenn Sie lediglich den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ef73c-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ef73c-114">Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ef73c-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="ef73c-115">Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält.</span><span class="sxs-lookup"><span data-stu-id="ef73c-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ef73c-116">Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="ef73c-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="ef73c-117">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="ef73c-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="ef73c-118">Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="ef73c-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="ef73c-119">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ef73c-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="ef73c-120">Klicken Sie unter **aktive Benutzer**auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="ef73c-121">Geben Sie auf der Seite **neuer Benutzer** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Benutzer**Name ein.</span><span class="sxs-lookup"><span data-stu-id="ef73c-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="ef73c-122">Klicken Sie auf **Kennwort**, klicken Sie auf **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="ef73c-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="ef73c-123">Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="ef73c-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="ef73c-124">Deaktivieren **Sie, dass dieser Benutzer sein Kennwort bei der ersten Anmeldung ändert**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="ef73c-125">Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="ef73c-126">Klicken Sie auf **Produktlizenzen**, und aktivieren Sie dann die **Microsoft 365 E5** -Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ef73c-126">Click **Product licenses**, and then turn the **Microsoft 365 E5** license on.</span></span>
8. <span data-ttu-id="ef73c-127">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-127">Click **Add**.</span></span>
9. <span data-ttu-id="ef73c-128">Deaktivieren Sie auf der **Seite Benutzer wurde hinzugefügt die Seite** **Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="ef73c-129">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef73c-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="ef73c-130">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf das Symbol Gruppen in der linken Navigationsleiste, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="ef73c-131">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="ef73c-132">Geben Sie auf der Seite **neue Gruppe** **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="ef73c-133">Klicken Sie auf **Besitzer auswählen** klicken Sie auf ihr globales Administratorkonto, und klicken Sie dann auf **#a0 schließen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="ef73c-134">Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ef73c-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="ef73c-135">Klicken Sie auf der Seite **GlobalAdmins** auf **für Mitglied bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="ef73c-136">Klicken Sie in der Liste auf das Konto **DedicatedAdmin** , und klicken Sie dann auf **speichern #a0 schließen #a1 #a2 Admin Center schließen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="ef73c-137">Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="ef73c-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="ef73c-138">Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef73c-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="ef73c-139">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ef73c-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ef73c-140">Klicken Sie auf **Azure Active Directory #a0 bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="ef73c-141">Klicken Sie auf dem Blatt **bedingter Zugriff – Richtlinien** auf **Baseline-Richtlinie: MFA für Administratoren erforderlich (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="ef73c-142">Auf den **Basisrichtlinien...**</span><span class="sxs-lookup"><span data-stu-id="ef73c-142">On the **Baseline policies…**</span></span> <span data-ttu-id="ef73c-143">auf **Richtlinie sofort verwenden #a0 speichern**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="ef73c-144">Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="ef73c-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="ef73c-145">Klicken Sie auf dem Blatt **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="ef73c-146">Geben Sie auf dem **neuen** Blade **globale Administratoren** in **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="ef73c-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="ef73c-147">Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="ef73c-148">Klicken Sie auf der Registerkarte **einschließen** des Blades **Benutzer und Gruppen** auf **Benutzer und Gruppen #a0 Benutzer und Gruppen auswählen #a1 auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="ef73c-149">Klicken Sie auf dem Blatt **auswählen** auf **GlobalAdmins #a0 wählen Sie #a1 fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="ef73c-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="ef73c-150">Klicken Sie im Abschnitt **Zuweisungen** auf **Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="ef73c-151">Klicken Sie auf dem Blatt **Bedingungen** auf **Anmelde Risiko**, klicken Sie **auf Ja** für **configure**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="ef73c-152">Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Blades auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="ef73c-153">Klicken Sie auf dem Blatt **Grant** auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="ef73c-154">Klicken Sie auf dem **neuen** Blade **auf für die** **Option Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ef73c-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="ef73c-155">Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="ef73c-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="ef73c-156">Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="ef73c-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="ef73c-157">Sie sollten aufgefordert werden, MFA für das Benutzerkonto zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef73c-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="ef73c-158">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef73c-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="ef73c-159">Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Protect Global Administrator Accounts](identity-create-protect-global-admins.md#identity-global-admin) Step in the Identity Phase.</span><span class="sxs-lookup"><span data-stu-id="ef73c-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="ef73c-160">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ef73c-160">Next step</span></span>

<span data-ttu-id="ef73c-161">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="ef73c-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef73c-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef73c-162">See also</span></span>

[<span data-ttu-id="ef73c-163">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="ef73c-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="ef73c-164">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ef73c-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ef73c-165">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="ef73c-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ef73c-166">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ef73c-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
