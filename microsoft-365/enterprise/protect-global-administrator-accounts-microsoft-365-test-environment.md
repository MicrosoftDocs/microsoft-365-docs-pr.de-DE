---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 9452ac7bafec416833ece9cbcb645bd7eeee21cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084324"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d6836-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d6836-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d6836-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d6836-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d6836-105">Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="d6836-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="d6836-106">In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.</span><span class="sxs-lookup"><span data-stu-id="d6836-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="d6836-107">Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="d6836-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="d6836-108">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="d6836-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="d6836-109">Schützen Sie Ihr dediziertes globales Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="d6836-109">Protect your dedicated global administrator account.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d6836-111">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d6836-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d6836-112">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d6836-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d6836-113">Wenn Sie lediglich den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d6836-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d6836-114">Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d6836-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6836-115">Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält.</span><span class="sxs-lookup"><span data-stu-id="d6836-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="d6836-116">Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="d6836-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="d6836-117">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="d6836-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="d6836-118">Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="d6836-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="d6836-119">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d6836-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="d6836-120">Klicken Sie auf **Benutzer > aktive Benutzer**, und klicken Sie dann auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="d6836-121">Geben Sie im Bereich **Benutzer hinzufügen** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Benutzer**Name ein.</span><span class="sxs-lookup"><span data-stu-id="d6836-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="d6836-122">Klicken Sie auf **Kennwort**, klicken Sie auf **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="d6836-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="d6836-123">Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="d6836-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="d6836-124">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d6836-124">Click **Next**.</span></span>
6. <span data-ttu-id="d6836-125">Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **Microsoft 365 E5** oder **Office 365 E5**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d6836-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="d6836-126">Klicken Sie im Bereich **Optionale Einstellungen** auf **Rollen**, und wählen Sie dann **Admin Center-Zugriff** und **globaler Administrator**aus. Klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d6836-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="d6836-127">Klicken Sie im Bereich **Sie sind fast fertig** auf **Hinzufügen fertig stellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="d6836-128">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6836-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="d6836-129">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Gruppen** , und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="d6836-130">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="d6836-131">Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d6836-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="d6836-132">Klicken Sie im Bereich **Grundlagen einrichten** auf **Gruppe erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="d6836-133">Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **GlobalAdmins**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d6836-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="d6836-134">Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d6836-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="d6836-135">Klicken Sie im Bereich **GlobalAdmins** auf **Mitglieder**, und klicken Sie dann auf **Alle anzeigen und Mitglieder verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d6836-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="d6836-136">Klicken Sie im Bereich **GlobalAdmins** auf **Mitglieder hinzufügen**, wählen Sie das **DedicatedAdmin** -Konto und ihr globales Administratorkonto aus, und klicken Sie dann auf **speichern > schließen > schließen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="d6836-137">Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="d6836-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="d6836-138">Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6836-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="d6836-139">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d6836-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d6836-140">Klicken Sie auf **Azure Active Directory > Sicherheits > bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="d6836-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="d6836-141">Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **Baseline-Richtlinie: MFA für Administratoren erfordern (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="d6836-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="d6836-142">Klicken Sie im Bereich **Basisrichtlinie** auf **Richtlinie sofort > speichern verwenden**.</span><span class="sxs-lookup"><span data-stu-id="d6836-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="d6836-143">Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="d6836-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="d6836-144">Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d6836-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="d6836-145">Geben Sie im **neuen** Bereich **globale Administratoren** in **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="d6836-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="d6836-146">Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="d6836-147">Klicken Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** auf Benutzer und Gruppen **> Benutzer und Gruppen auswählen > auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="d6836-148">Klicken Sie im Bereich **auswählen** auf die Gruppe **GlobalAdmins** , und klicken Sie dann auf **> fertig wählen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="d6836-149">Klicken Sie im Abschnitt **Zuweisungen** auf **Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="d6836-150">Klicken Sie im Bereich **Bedingungen** auf **Anmelde Risiko**, klicken Sie auf **Ja** für **configure**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d6836-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="d6836-151">Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Bereichs auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="d6836-152">Klicken Sie im Bereich **erteilen** auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="d6836-153">Klicken Sie im Bereich **neu** **auf** für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d6836-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="d6836-154">Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="d6836-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="d6836-155">Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="d6836-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="d6836-156">Sie sollten aufgefordert werden, MFA zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d6836-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="d6836-157">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6836-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="d6836-158">Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Protect Global Administrator Accounts](identity-create-protect-global-admins.md#identity-global-admin) Step in the Identity Phase.</span><span class="sxs-lookup"><span data-stu-id="d6836-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d6836-159">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d6836-159">Next step</span></span>

<span data-ttu-id="d6836-160">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="d6836-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6836-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6836-161">See also</span></span>

[<span data-ttu-id="d6836-162">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="d6836-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d6836-163">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d6836-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d6836-164">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d6836-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d6836-165">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d6836-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
