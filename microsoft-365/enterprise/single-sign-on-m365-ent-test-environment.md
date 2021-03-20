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
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904864"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="71a94-103">Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="71a94-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="71a94-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 Enterprise- als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="71a94-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="71a94-105">Azure AD Seamless Single Sign-On (Seamless SSO) meldet sich automatisch bei Benutzern an, wenn sie sich auf ihren PCs oder Geräten befinden, die mit ihrem Organisationsnetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="71a94-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="71a94-106">Azure AD Seamless SSO bietet Benutzern einfachen Zugriff auf cloudbasierte Anwendungen, ohne dass zusätzliche lokale Komponenten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="71a94-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="71a94-107">In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für Azure AD Seamless SSO konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71a94-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="71a94-108">Das Einrichten von nahtlosen Azure AD-SSO umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="71a94-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="71a94-109">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="71a94-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="71a94-110">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="71a94-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="71a94-112">Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="71a94-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="71a94-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="71a94-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="71a94-114">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="71a94-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="71a94-115">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="71a94-115">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="71a94-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="71a94-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="71a94-118">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="71a94-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="71a94-119">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="71a94-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="71a94-120">Azure AD Connect wird unter APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne von TESTLAB regelmäßig mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="71a94-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="71a94-121">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="71a94-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="71a94-122">Konfigurieren Sie in dieser Phase Azure AD Connect in APP1 für Azure AD Seamless SSO, und überprüfen Sie dann, ob es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="71a94-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="71a94-123">Konfigurieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="71a94-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="71a94-124">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="71a94-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="71a94-125">Führen Sie auf dem APP1-Desktop Azure AD Connect aus.</span><span class="sxs-lookup"><span data-stu-id="71a94-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="71a94-126">Wählen Sie **auf der Seite Willkommen** die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="71a94-127">Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Benutzeranmelden ändern** aus, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="71a94-128">Geben Sie **auf der Seite Verbindung mit Azure AD** herstellen Ihre Anmeldeinformationen für ihr globales Administratorkonto ein, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="71a94-129">Wählen Sie **auf der Seite Benutzeranmelden** die Option **Einmaliges Anmelden aktivieren** aus, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="71a94-130">Wählen Sie **auf der Seite Einmaliges Anmelden** aktivieren die Option **Anmeldeinformationen eingeben aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="71a94-131">Geben Sie **im Dialogfeld Windows-Sicherheit** **benutzer1** und das Kennwort des Benutzerkontos ein, wählen Sie **OK** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="71a94-132">Wählen Sie **auf der Seite Bereit** zum Konfigurieren die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="71a94-133">Wählen Sie **auf der Seite Konfiguration abgeschlossen** die Option Beenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="71a94-134">Wählen Sie im Azure-Portal im linken Bereich **Azure Active Directory** Azure AD Connect  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="71a94-135">Stellen Sie **sicher,** dass das Feature Für einmaliges Anmelden nahtlos als **Aktiviert angezeigt wird.**</span><span class="sxs-lookup"><span data-stu-id="71a94-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="71a94-136">Testen Sie als Nächstes die Möglichkeit, sich bei Ihrem Abonnement mit dem <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="71a94-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="71a94-137">Benutzername des User1-Kontos.</span><span class="sxs-lookup"><span data-stu-id="71a94-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="71a94-138">Wählen Sie in Internet Explorer auf APP1 das Einstellungssymbol aus, und wählen Sie **dann Internetoptionen aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="71a94-139">Wählen **Sie unter Internetoptionen** die Registerkarte **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="71a94-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="71a94-140">Wählen **Sie Lokales Intranet** aus, und wählen Sie dann Websites **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="71a94-141">Wählen **Sie im lokalen Intranet** erweitert **aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="71a94-142">Geben Sie unter Diese **Website zur Zone hinzufügen** https **<span>://</span>autologon.microsoftazuread-sso.com** ein, wählen Sie **Schließen**  >    >  **schließen**  >  **OK hinzufügen OK aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="71a94-143">Melden Sie sich ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="71a94-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="71a94-144">Wenn Sie zur Anmeldung aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="71a94-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="71a94-145">name, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="71a94-145">name, and then select **Next**.</span></span> <span data-ttu-id="71a94-146">Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden.</span><span class="sxs-lookup"><span data-stu-id="71a94-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="71a94-147">Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.</span><span class="sxs-lookup"><span data-stu-id="71a94-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="71a94-148">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD ist.</span><span class="sxs-lookup"><span data-stu-id="71a94-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="71a94-149">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71a94-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="71a94-150">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="71a94-150">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="71a94-152">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="71a94-152">This configuration consists of:</span></span>

- <span data-ttu-id="71a94-153">Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit dem Testlab der DNS-Domäne.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="71a94-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="71a94-154">registriert.</span><span class="sxs-lookup"><span data-stu-id="71a94-154">registered.</span></span>
- <span data-ttu-id="71a94-155">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="71a94-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="71a94-156">Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="71a94-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="71a94-157">Azure AD Seamless SSO ist aktiviert, damit sich Computer im simulierten Intranet bei Microsoft 365-Cloudressourcen anmelden können, ohne ein Benutzerkontokennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="71a94-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="71a94-158">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="71a94-158">Next step</span></span>

<span data-ttu-id="71a94-159">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="71a94-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="71a94-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71a94-160">See also</span></span>

[<span data-ttu-id="71a94-161">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="71a94-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="71a94-162">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="71a94-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="71a94-163">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="71a94-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)