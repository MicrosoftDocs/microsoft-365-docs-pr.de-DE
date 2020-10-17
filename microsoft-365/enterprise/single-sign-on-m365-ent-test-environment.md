---
title: Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen des nahtlosen einmaliges Anmeldens in Azure AD für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487600"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3bb4d-103">Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3bb4d-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3bb4d-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="3bb4d-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3bb4d-p101">Azure AD nahtlose Einzel Sign-On (Seamless SSO) automatisch Benutzer, wenn Sie sich auf ihren PCs oder Geräten befinden, die mit Ihrem Organisationsnetzwerk verbunden sind. Azure AD nahtloses SSO bietet Benutzern einfachen Zugriff auf Cloud-basierte Anwendungen, ohne dass zusätzliche lokale Komponenten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-p101">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="3bb4d-107">In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für Azure AD nahtloses SSO konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="3bb4d-108">Das Einrichten Azure AD nahtlosen SSO umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="3bb4d-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="3bb4d-109">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3bb4d-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="3bb4d-110">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3bb4d-112">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="3bb4d-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3bb4d-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3bb4d-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3bb4d-114">Befolgen Sie die Anweisungen unter [Kennworthash Synchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3bb4d-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="3bb4d-115">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="3bb4d-115">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="3bb4d-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="3bb4d-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="3bb4d-118">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="3bb4d-119">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="3bb4d-120">Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB Active Directory-Domänendienste (AD DS) Domäne regelmäßig mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="3bb4d-121">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="3bb4d-122">Konfigurieren Sie in dieser Phase Azure AD Connect on App1 für Azure AD nahtloses SSO, und überprüfen Sie dann, ob es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="3bb4d-123">Konfigurieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="3bb4d-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="3bb4d-124">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="3bb4d-125">Führen Sie auf dem App1-Desktop Azure AD Connect aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="3bb4d-126">Wählen Sie auf der **Willkommensseite** **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="3bb4d-127">Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Benutzeranmeldung ändern**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="3bb4d-128">Geben Sie auf der Seite mit **Azure AD verbinden** die Anmeldeinformationen des globalen Administratorkontos ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="3bb4d-129">Wählen Sie auf der Seite **Benutzeranmeldung** die Option **einmaliges Anmelden aktivieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="3bb4d-130">Wählen Sie auf der Seite **einmaliges Anmelden aktivieren** die Option **Anmeldeinformationen eingeben**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="3bb4d-131">Geben Sie im Dialogfeld **Windows** -Sicherheit **User1** und das Kennwort des user1-Kontos ein, klicken Sie auf **OK**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="3bb4d-132">Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="3bb4d-133">Wählen Sie auf der Seite **Konfiguration abgeschlossen** die Option **Beenden**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="3bb4d-134">Wählen Sie im Azure-Portal im linken Bereich **Azure Active Directory**  >  **Azure AD Connect**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="3bb4d-135">Stellen Sie sicher, dass das **nahtlose Feature für einmaliges Anmelden** als **aktiviert**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="3bb4d-136">Testen Sie als nächstes die Möglichkeit, sich mit dem user1@testlab bei Ihrem Abonnement anzumelden <strong>.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="3bb4d-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="3bb4d-137">Benutzername des User1-Kontos.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="3bb4d-138">Wählen Sie unter Internet Explorer auf App1 das Symbol Einstellungen aus, und wählen Sie dann **Internet Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="3bb4d-139">Wählen Sie unter **Internet Optionen**die Registerkarte **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="3bb4d-140">Wählen Sie **Lokales Intranet**aus, und wählen Sie dann **Sites**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="3bb4d-141">Wählen Sie im **lokalen Intranet**die Option **erweitert**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="3bb4d-142">Geben Sie unter **diese Website zur Zone hinzufügen die**Option **https<span>://</span>Autologon.microsoftazuread-SSO.com**ein, und **Wählen Sie**  >  **Schließen**  >  **OK**  >  **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="3bb4d-143">Melden Sie sich ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="3bb4d-144">Wenn Sie zur Anmeldung aufgefordert werden, geben Sie <strong>User1@testlab an.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="3bb4d-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="3bb4d-145">Name, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-145">name, and then select **Next**.</span></span> <span data-ttu-id="3bb4d-146">Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="3bb4d-147">Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="3bb4d-148">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD ist.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="3bb4d-149">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="3bb4d-150">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="3bb4d-150">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="3bb4d-152">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="3bb4d-152">This configuration consists of:</span></span>

- <span data-ttu-id="3bb4d-153">Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne testlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="3bb4d-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="3bb4d-154">registriert.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-154">registered.</span></span>
- <span data-ttu-id="3bb4d-155">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="3bb4d-156">Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="3bb4d-157">Azure AD nahtloses SSO ist aktiviert, sodass Computer im simulierten Intranet sich bei den Cloud-Ressourcen von Microsoft 365 anmelden können, ohne ein Benutzerkontokennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="3bb4d-158">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3bb4d-158">Next step</span></span>

<span data-ttu-id="3bb4d-159">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="3bb4d-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bb4d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bb4d-160">See also</span></span>

[<span data-ttu-id="3bb4d-161">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bb4d-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3bb4d-162">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bb4d-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3bb4d-163">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="3bb4d-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
