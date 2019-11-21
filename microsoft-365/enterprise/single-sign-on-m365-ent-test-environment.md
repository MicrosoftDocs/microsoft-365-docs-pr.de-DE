---
title: Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen des nahtlosen einmaliges Anmeldens in Azure AD für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: a32dca8c37d9e6788aef801e9f99a90b724e86b1
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757672"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="93b82-103">Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="93b82-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="93b82-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="93b82-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="93b82-p101">Beim nahtlosen einmaligen Anmelden von Azure AD werden Benutzer automatisch angemeldet, wenn sie auf ihren Computern oder Geräten arbeiten, die mit ihrem Organisationsnetzwerk verbunden sind. Das nahtlose einmalige Anmelden in Azure AD bietet Benutzern einfachen Zugriff auf cloudbasierte Anwendungen, ohne dass dafür zusätzliche lokale Komponenten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="93b82-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="93b82-107">Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für das nahtlose einmalige Anmelden in Azure AD konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="93b82-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="93b82-108">Die Einrichtung besteht aus zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="93b82-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="93b82-109">Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="93b82-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="93b82-110">Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="93b82-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="93b82-112">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="93b82-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="93b82-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="93b82-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="93b82-p102">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="93b82-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="93b82-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="93b82-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="93b82-118">Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5 oder Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="93b82-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="93b82-119">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="93b82-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="93b82-120">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Microsoft 365- oder Office 365-Abonnements in regelmäßigen Abständen zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="93b82-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="93b82-121">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="93b82-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="93b82-122">In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD und vergewissern sich dann, dass es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="93b82-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="93b82-123">Konfigurieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="93b82-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="93b82-124">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="93b82-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="93b82-125">Führen Sie Azure AD Connect über den Desktop von APP1 aus.</span><span class="sxs-lookup"><span data-stu-id="93b82-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="93b82-126">Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="93b82-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="93b82-127">Klicken Sie auf der Seite **Weitere Aufgaben** auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="93b82-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="93b82-128">Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="93b82-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="93b82-129">Wählen Sie auf der Seite **Benutzeranmeldung** die Option **Einmaliges Anmelden aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="93b82-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="93b82-130">Klicken Sie auf der Seite **Einmaliges Anmelden aktivieren** auf **Anmeldeinformationen eingeben**.</span><span class="sxs-lookup"><span data-stu-id="93b82-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="93b82-p103">Geben Sie im Dialogfeld **Windows-Sicherheit** den Benutzer **Benutzer1** und das Kennwort für das Konto „Benutzer1“ ein, und klicken Sie dann auf **OK**. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="93b82-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="93b82-133">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="93b82-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="93b82-134">Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="93b82-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="93b82-p104">Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Einmaliges Anmelden** als **Aktiviert** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="93b82-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="93b82-137">Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen <strong>user1@testlab.</strong>\<Ihre öffentliche Domäne> des Kontos „Benutzer1“ beim Ihrem Office 365-Abonnement anmelden können.</span><span class="sxs-lookup"><span data-stu-id="93b82-137">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="93b82-138">Klicken Sie in Internet Explorer auf APP1 auf das Symbol „Einstellungen“, und klicken Sie dann auf **Internetoptionen**.</span><span class="sxs-lookup"><span data-stu-id="93b82-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="93b82-139">Klicken Sie unter **Internetoptionen** auf die Registerkarte **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="93b82-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="93b82-140">Klicken Sie auf **Lokales Intranet** und dann auf **Sites**.</span><span class="sxs-lookup"><span data-stu-id="93b82-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="93b82-141">Klicken Sie unter **Lokales Intranet** auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="93b82-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="93b82-142">Geben Sie unter **Diese Website zur Zone hinzufügen** die Adresse **https<span>://</span>autologon.microsoftazuread-sso.com** ein, und klicken Sie auf **Hinzufügen > Schließen > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="93b82-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="93b82-143">Melden Sie sich von Office 365 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="93b82-143">Sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="93b82-144">Wenn Sie aufgefordert werden, sich anzumelden, geben Sie <strong>user1@testlab.</strong>\<Ihren öffentlichen Domänennamen> an, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="93b82-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="93b82-145">Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden.</span><span class="sxs-lookup"><span data-stu-id="93b82-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="93b82-146">Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.</span><span class="sxs-lookup"><span data-stu-id="93b82-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="93b82-147">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD und Office 365 ist.</span><span class="sxs-lookup"><span data-stu-id="93b82-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD and Office 365.</span></span> <span data-ttu-id="93b82-148">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93b82-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="93b82-149">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="93b82-149">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="93b82-151">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="93b82-151">This configuration consists of:</span></span>

- <span data-ttu-id="93b82-152">Testversionen oder kostenpflichtigen Abonnements von Microsoft 365 E5 oder Office 365 E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>.</span><span class="sxs-lookup"><span data-stu-id="93b82-152">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="93b82-153">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="93b82-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="93b82-154">Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365- oder Office 365-Abonnements mit der AD DS-Domäne "TESTLAB" zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="93b82-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="93b82-155">Das nahtlose einmalige Anmelden in Azure AD wird aktiviert, damit sich Computer im simulierten Intranet bei Microsoft 365-Cloudressourcen anmelden können, ohne ein Kennwort für ein Benutzerkonto anzugeben.</span><span class="sxs-lookup"><span data-stu-id="93b82-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="93b82-156">Im Schritt [Vereinfachen der Benutzeranmeldung](identity-secure-your-passwords.md#identity-sso) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der nahtlosen einmaligen Anmeldung in Azure AD in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="93b82-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="93b82-157">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="93b82-157">Next step</span></span>

<span data-ttu-id="93b82-158">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="93b82-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="93b82-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93b82-159">See also</span></span>

[<span data-ttu-id="93b82-160">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93b82-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="93b82-161">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93b82-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="93b82-162">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93b82-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


