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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918882"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="89f1f-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="89f1f-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="89f1f-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="89f1f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="89f1f-105">Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="89f1f-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="89f1f-106">In diesem Artikel wird beschrieben, wie Sie Richtlinien für bedingten Zugriff in Azure Active Directory (Azure AD) verwenden, um globale Administratorkonten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="89f1f-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="89f1f-107">Der Schutz globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="89f1f-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="89f1f-108">Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="89f1f-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="89f1f-109">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="89f1f-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="89f1f-111">Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="89f1f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="89f1f-112">Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="89f1f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="89f1f-113">Wenn Sie den globalen Administratorkontoschutz auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="89f1f-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="89f1f-114">Wenn Sie den globalen Administratorkontoschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="89f1f-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="89f1f-115">Für das Testen des globalen Administratorkontoschutzes ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für active Directory Domain Services (AD DS) umfasst.</span><span class="sxs-lookup"><span data-stu-id="89f1f-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="89f1f-116">Es wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="89f1f-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="89f1f-117">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="89f1f-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="89f1f-118">Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="89f1f-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="89f1f-119">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="89f1f-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="89f1f-120">Wählen **Sie Benutzer** Aktive  >  **Benutzer** aus, und wählen Sie dann Benutzer hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="89f1f-121">Geben Sie **im Bereich** Benutzer hinzufügen **dedicatedAdmin** in die Felder **Vorname,** **Anzeigename** und **Benutzername** ein.</span><span class="sxs-lookup"><span data-stu-id="89f1f-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="89f1f-122">Wählen **Sie Kennwort** aus, wählen Sie Lassen Sie mich das Kennwort **erstellen,** und geben Sie dann ein starkes Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="89f1f-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="89f1f-123">Noten Sie das Kennwort für dieses neue Konto an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="89f1f-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="89f1f-124">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="89f1f-124">Select **Next**.</span></span>
6. <span data-ttu-id="89f1f-125">Wählen Sie **im Bereich Produktlizenzen** zuweisen die Option **Microsoft 365 E5** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="89f1f-126">Wählen Sie **im Bereich Optionale Einstellungen** die Option **Rollen** Admin  >  **Center access** Global  >  **admin**  >  **Next aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="89f1f-127">Wählen Sie **im Bereich You're almost done** die Option Hinzufügen fertig stellen aus, und wählen Sie dann Schließen  **aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="89f1f-128">Erstellen Sie als Nächstes eine neue Gruppe namens GlobalAdmins, und fügen Sie ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="89f1f-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="89f1f-129">Wählen Sie auf der **Registerkarte Microsoft 365 Admin Center** im linken Navigationsbereich Gruppen aus, und wählen Sie dann Gruppen **aus.** </span><span class="sxs-lookup"><span data-stu-id="89f1f-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="89f1f-130">Wählen Sie **Gruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="89f1f-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="89f1f-131">Wählen Sie **im Bereich Gruppentyp auswählen** die Option **Sicherheit** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="89f1f-132">Wählen Sie **im Bereich** Einrichten der Grundlagen die Option Gruppe erstellen aus, und wählen Sie dann Schließen **aus.** </span><span class="sxs-lookup"><span data-stu-id="89f1f-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="89f1f-133">Geben Sie im Bereich Überprüfen und Fertig stellen **des Hinzufügens** von Gruppen **die Option GlobalAdmins** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="89f1f-134">Wählen Sie in der Liste der Gruppen die **Gruppe GlobalAdmins** aus.</span><span class="sxs-lookup"><span data-stu-id="89f1f-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="89f1f-135">Wählen Sie **im Bereich GlobalAdmins** **Mitglieder** aus, und wählen Sie dann Alle anzeigen und Mitglieder **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="89f1f-136">Wählen Sie **im Bereich GlobalAdmins** Mitglieder hinzufügen **aus,** wählen Sie das **Konto DedicatedAdmin** und Ihr globales Administratorkonto aus, und wählen Sie dann **Schließen** schließen  >    >  **speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="89f1f-137">Erstellen Sie als Nächstes Richtlinien für bedingten Zugriff, um die mehrstufige Authentifizierung für globale Administratorkonten zu erfordern und die Authentifizierung zu verweigern, wenn das Anmelderisiko mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="89f1f-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="89f1f-138">Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="89f1f-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="89f1f-139">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="89f1f-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="89f1f-140">Klicken **Sie auf Bedingter Azure Active**  >  **Directory-Sicherheitszugriff.**  >  </span><span class="sxs-lookup"><span data-stu-id="89f1f-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="89f1f-141">Wählen Sie **im Bereich Bedingter** Zugriff – Richtlinien die **Option Baseline policy: Require MFA for admins (preview)** aus.</span><span class="sxs-lookup"><span data-stu-id="89f1f-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="89f1f-142">Wählen Sie **im Bereich Baseline policy** die Option Richtlinie sofort > Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="89f1f-143">Diese zweite Richtlinie blockiert den Zugriff auf die globale Administratorkontoauthentifizierung, wenn das Anmelderisiko mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="89f1f-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="89f1f-144">Wählen Sie **im Bereich Bedingter Zugriff – Richtlinien** die Option Neue Richtlinie **aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="89f1f-145">Geben Sie **im Bereich Neu** den Namen globale **Administratoren** **ein.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="89f1f-146">Wählen Sie **im Abschnitt Zuweisungen** die Option **Benutzer und Gruppen aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="89f1f-147">Wählen Sie **auf der** Registerkarte Include im Bereich **Benutzer und** Gruppen die Option Benutzer und **Gruppen** Auswählen Benutzer  >  **und Gruppen** Auswählen  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="89f1f-148">Wählen Sie **im Bereich** Auswählen die **Gruppe GlobalAdmins** aus, und wählen Sie **dann Fertig**  >  **auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="89f1f-149">Wählen Sie **im Abschnitt Zuordnungen** die Option **Bedingungen aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="89f1f-150">Wählen Sie **im** Bereich Bedingungen die Option **Anmelderisiko** aus, wählen Sie **Ja** für **Konfigurieren** aus, wählen Sie **Hoch** und **Mittel** aus, und wählen Sie **dann Auswählen** und **Fertig aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="89f1f-151">Wählen Sie **im Abschnitt Zugriffssteuerelemente** im **Bereich Neu** die Option **Gewähren aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="89f1f-152">Wählen Sie **im Bereich** Gewähren die Option **Zugriff blockieren** aus, und wählen Sie dann **Auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="89f1f-153">Wählen Sie **im Bereich Neu** die Option **Ein** für Richtlinie **aktivieren** aus, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="89f1f-154">Schließen Sie **die Registerkarten Azure-Portal** und **Microsoft 365 Admin Center.**</span><span class="sxs-lookup"><span data-stu-id="89f1f-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="89f1f-155">Um die erste Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="89f1f-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="89f1f-156">Sie sollten aufgefordert werden, MFA zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="89f1f-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="89f1f-157">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="89f1f-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="89f1f-158">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="89f1f-158">Next step</span></span>

<span data-ttu-id="89f1f-159">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="89f1f-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="89f1f-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89f1f-160">See also</span></span>

[<span data-ttu-id="89f1f-161">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="89f1f-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="89f1f-162">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="89f1f-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="89f1f-163">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="89f1f-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="89f1f-164">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="89f1f-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)