---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung
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
description: Gehen Sie wie folgt vor, um globale Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487636"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4b5b1-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4b5b1-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4b5b1-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="4b5b1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4b5b1-105">Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="4b5b1-106">In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="4b5b1-107">Das schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="4b5b1-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="4b5b1-108">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4b5b1-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4b5b1-109">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4b5b1-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4b5b1-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="4b5b1-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4b5b1-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4b5b1-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4b5b1-113">Wenn Sie den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4b5b1-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4b5b1-114">Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4b5b1-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b5b1-115">Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="4b5b1-116">Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="4b5b1-117">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4b5b1-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="4b5b1-118">Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="4b5b1-119">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="4b5b1-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="4b5b1-120">Wählen Sie **Benutzer**  >  **aktive Benutzer**aus, und wählen Sie dann **Benutzer hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="4b5b1-121">Geben Sie im Bereich **Benutzer hinzufügen** in den Feldern **Vorname**, **Anzeigename**und Benutzer **Name** **DedicatedAdmin** ein.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="4b5b1-122">Wählen Sie **Kennwort**aus, wählen Sie **das Kennwort erstellen**aus, und geben Sie dann ein sicheres Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="4b5b1-123">Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="4b5b1-124">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-124">Select **Next**.</span></span>
6. <span data-ttu-id="4b5b1-125">Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **Microsoft 365 E5**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="4b5b1-126">Wählen Sie im Bereich **Optionale Einstellungen** die Option **roles**  >  **Admin Center Access**  >  **Global admin**  >  **Next**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="4b5b1-127">Wählen Sie im Bereich **fast done** die Option **Hinzufügen fertig stellen**aus, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="4b5b1-128">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="4b5b1-129">Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich die Option **Gruppen** aus, und wählen Sie dann **Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="4b5b1-130">Wählen Sie **Gruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="4b5b1-131">Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="4b5b1-132">Wählen Sie im Bereich **Grundlagen einrichten die** Option **Gruppe erstellen**aus, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="4b5b1-133">Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **GlobalAdmins**ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="4b5b1-134">Wählen Sie in der Liste der Gruppen die Gruppe **GlobalAdmins** aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="4b5b1-135">Wählen Sie im Bereich **GlobalAdmins** die Option **Mitglieder**aus, und wählen Sie dann **Alle anzeigen und Mitglieder verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="4b5b1-136">Wählen Sie im Bereich **GlobalAdmins** die Option **Mitglieder hinzufügen**aus, wählen Sie das **DedicatedAdmin** -Konto und ihr globales Administratorkonto aus, und wählen Sie dann **Save**  >  **Close**  >  **Close**speichern aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="4b5b1-137">Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="4b5b1-138">Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="4b5b1-139">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="4b5b1-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4b5b1-140">Klicken Sie auf **Azure Active Directory**  >  **Sicherheits**  >  **bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="4b5b1-141">Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **Basisrichtlinie: MFA für Administratoren erfordern (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="4b5b1-142">Wählen Sie im Bereich **Basisrichtlinie** die Option **Richtlinie sofort > speichern verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="4b5b1-143">Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="4b5b1-144">Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="4b5b1-145">Geben Sie im **neuen** Bereich **globale Administratoren** in **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="4b5b1-146">Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="4b5b1-147">Wählen Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** die Option Benutzer und **Gruppen**  >  **Benutzer**  >  **und Gruppen**auswählen aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="4b5b1-148">Wählen Sie im Bereich **auswählen** die Gruppe **GlobalAdmins** aus, **und wählen Sie**dann  >  **Fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="4b5b1-149">Wählen Sie im Abschnitt **Zuweisungen** die Option **Bedingungen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="4b5b1-150">Wählen Sie im Bereich **Bedingungen** die **Option Anmelde Risiko**aus, wählen **Sie ja** für **configure**aus, wählen Sie **hoch** und **Mittel**aus, und wählen Sie dann **auswählen** und **Fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="4b5b1-151">Wählen Sie im Bereich **Zugriffssteuerung** des **neuen** Bereichs die Option **Grant**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="4b5b1-152">Wählen Sie im Bereich **erteilen** die Option **Zugriff blockieren**aus, und wählen Sie dann **auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="4b5b1-153">Wählen Sie im Bereich **neu** die **Option** für **Richtlinie aktivieren**aus, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="4b5b1-154">Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="4b5b1-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="4b5b1-155">Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="4b5b1-156">Sie sollten aufgefordert werden, MFA zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="4b5b1-157">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="4b5b1-158">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4b5b1-158">Next step</span></span>

<span data-ttu-id="4b5b1-159">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b5b1-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b5b1-160">See also</span></span>

[<span data-ttu-id="4b5b1-161">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="4b5b1-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="4b5b1-162">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b5b1-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4b5b1-163">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b5b1-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4b5b1-164">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4b5b1-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
