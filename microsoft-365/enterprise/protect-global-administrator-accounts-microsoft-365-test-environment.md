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
ms.openlocfilehash: 86b2d325fc710fd8b387bc37cad5f8ea60df001d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353057"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="71008-103">Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="71008-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="71008-104">Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="71008-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="71008-105">In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.</span><span class="sxs-lookup"><span data-stu-id="71008-105">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="71008-106">Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="71008-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="71008-107">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="71008-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="71008-108">Schützen Sie Ihr dediziertes globales Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="71008-108">Protect your dedicated global administrator account.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="71008-110">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="71008-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="71008-111">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="71008-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="71008-112">Wenn Sie nur den Schutz globaler Administratorkonten auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="71008-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="71008-113">Wenn Sie den Schutz globaler Administratorkonten in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="71008-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="71008-114">Das Testen des globalen Administratorkonto Schutzes erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="71008-114">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="71008-115">Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="71008-115">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="71008-116">Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="71008-116">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="71008-117">Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="71008-117">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="71008-118">Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="71008-118">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="71008-119">Klicken Sie unter **aktive Benutzer**auf **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71008-119">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="71008-120">Geben Sie auf der Seite **neuer Benutzer** **DedicatedAdmin** unter **Vorname**, **Anzeigename**und **Benutzer**Name ein.</span><span class="sxs-lookup"><span data-stu-id="71008-120">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="71008-121">Klicken Sie auf **Kennwort**, aktivieren Sie **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="71008-121">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="71008-122">NoTieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="71008-122">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="71008-123">Deaktivieren **Sie dieses Benutzerkennwort bei der ersten Anmeldung ändern**.</span><span class="sxs-lookup"><span data-stu-id="71008-123">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="71008-124">Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.</span><span class="sxs-lookup"><span data-stu-id="71008-124">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="71008-125">Klicken Sie auf **Produktlizenzen**und dann auf **Enterprise Mobility + Security e5** und **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="71008-125">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="71008-126">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71008-126">Click **Add**.</span></span>
9. <span data-ttu-id="71008-127">Deaktivieren Sie auf der **Seite hinzugefügte Benutzer**das **Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="71008-127">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="71008-128">Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.</span><span class="sxs-lookup"><span data-stu-id="71008-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="71008-129">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der linken Navigationsleiste auf das Symbol Gruppen, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="71008-129">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="71008-130">Klicken Sie auf **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71008-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="71008-131">Geben Sie auf der Seite **neue Gruppe** **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="71008-131">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="71008-132">Klicken Sie auf **Besitzer auswählen** , klicken Sie auf ihr globales Administratorkonto, und klicken Sie dann auf **> schließen**.</span><span class="sxs-lookup"><span data-stu-id="71008-132">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="71008-133">Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="71008-133">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="71008-134">Klicken Sie auf der Seite **GlobalAdmins** auf **für Mitglied bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="71008-134">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="71008-135">Klicken Sie in der Liste auf das **DedicatedAdmin** -Konto, und klicken Sie dann auf **Speichern _GT_ schließen _GT_ schließen > Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="71008-135">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="71008-136">Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um die mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="71008-136">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="71008-137">Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten MFA verwenden.</span><span class="sxs-lookup"><span data-stu-id="71008-137">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="71008-138">Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="71008-138">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="71008-139">Klicken Sie auf **Azure Active Directory _GT_ Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="71008-139">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="71008-140">Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **Basisrichtlinie: MFA für Administratoren (Vorschau) erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="71008-140">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="71008-141">In den **Basisrichtlinien...**</span><span class="sxs-lookup"><span data-stu-id="71008-141">On the **Baseline policies…**</span></span> <span data-ttu-id="71008-142">auf **Richtlinie sofort _GT_ speichern**.</span><span class="sxs-lookup"><span data-stu-id="71008-142">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="71008-143">Diese zweite Richtlinie blockiert den Zugriff auf die globale Administratorkonto Authentifizierung, wenn das Anmelde Risiko Mittel oder hoch ist.</span><span class="sxs-lookup"><span data-stu-id="71008-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="71008-144">Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="71008-144">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="71008-145">Geben Sie auf dem **neuen** Blatt **globale Administratoren** in **Name**ein.</span><span class="sxs-lookup"><span data-stu-id="71008-145">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="71008-146">Klicken Sie \*\*\*\* im Abschnitt Zuweisungen auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="71008-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="71008-147">Klicken Sie auf der Registerkarte " **einbeziehen** " des Blades " **Benutzer und Gruppen** " auf Benutzer und Gruppen **_GT_ Benutzer und Gruppen > auswählen**.</span><span class="sxs-lookup"><span data-stu-id="71008-147">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="71008-148">Klicken Sie auf dem Blade **auswählen** auf die **GlobalAdmins > wählen Sie > fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="71008-148">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="71008-149">Klicken Sie \*\*\*\* im Abschnitt Zuweisungen auf **Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="71008-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="71008-150">Klicken Sie auf dem Blatt **Bedingungen** auf **Anmelde Risiko**, klicken Sie **auf Ja** , um zu **Konfigurieren**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="71008-150">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="71008-151">Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Blatts auf **erteilen**.</span><span class="sxs-lookup"><span data-stu-id="71008-151">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="71008-152">Klicken Sie auf der **Grant** -Blade auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="71008-152">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="71008-153">Klicken Sie auf dem **neuen** Blade \*\*\*\* auf für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="71008-153">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="71008-154">Beenden Sie die Registerkarten **Azure Portal** und **Microsoft 365 Admin Center** .</span><span class="sxs-lookup"><span data-stu-id="71008-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="71008-155">Um die erste Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem DedicatedAdmin-Konto an.</span><span class="sxs-lookup"><span data-stu-id="71008-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="71008-156">Sie sollten aufgefordert werden, MFA für das Benutzerkonto zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71008-156">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="71008-157">Dies zeigt, dass die erste Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="71008-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="71008-158">Weitere Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md#identity-global-admin) .</span><span class="sxs-lookup"><span data-stu-id="71008-158">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="71008-159">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="71008-159">Next step</span></span>

<span data-ttu-id="71008-160">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="71008-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="71008-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71008-161">See also</span></span>

[<span data-ttu-id="71008-162">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="71008-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="71008-163">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="71008-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="71008-164">Microsoft 365 Enterprise-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="71008-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="71008-165">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="71008-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
