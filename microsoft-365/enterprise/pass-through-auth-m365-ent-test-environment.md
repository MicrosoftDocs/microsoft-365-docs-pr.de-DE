---
title: Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren von Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: ebb37ba414ee7fec0e6546fa01e2632a5112c227
ms.sourcegitcommit: 5a8e1a1396b0190b243d27d90a73f94f4b8d44ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "25093119"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="63979-103">Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="63979-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="63979-p101">Organisationen, die ihre lokale Windows Server Active Directory (AD)-Infrastruktur direkt für die Authentifizierung mit cloudbasierten Microsoft-Diensten und -Anwendungen verwenden möchten, können Pass-Through-Authentifizierung verwenden. Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für die Pass-Through-Authentifizierung konfigurieren können. Dabei ergibt sich die folgende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="63979-p101">Organizations that want to directly use their on-premises Windows Server Active Directory (AD) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication. This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="63979-107">Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="63979-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="63979-108">Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="63979-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="63979-109">Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="63979-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="63979-111">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63979-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="63979-112">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="63979-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="63979-p102">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="63979-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="63979-116">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="63979-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="63979-117">Testversionen oder dauerhafte Abonnements von Office 365 E5 und EMS E5.</span><span class="sxs-lookup"><span data-stu-id="63979-117">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="63979-p103">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf APP1 ausgeführt, um die Windows Server Active Directory-Domäne „TESTLAB“ mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements regelmäßig zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="63979-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="63979-120">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63979-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="63979-121">In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für die Verwendung von Pass-Through-Authentifizierung und vergewissern sich dann, dass sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="63979-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="63979-122">Konfigurieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="63979-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="63979-123">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="63979-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="63979-124">Führen Sie Azure AD Connect über den Desktop von APP1 aus.</span><span class="sxs-lookup"><span data-stu-id="63979-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="63979-125">Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="63979-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="63979-126">Klicken Sie auf der Seite „Weitere Aufgaben“ auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63979-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="63979-127">Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63979-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="63979-128">Klicken Sie auf der Seite **Benutzeranmeldung** auf **Pass-Through-Authentifizierung**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="63979-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="63979-129">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="63979-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="63979-130">Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="63979-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="63979-p104">Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Pass-Through-Authentifizierung** als **Aktiviert** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="63979-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="63979-p105">Klicken Sie auf **Pass-Through-Authentifizierung**. Im Bereich **Pass-Through-Authentifizierung** werden die Server aufgeführt, auf denen Ihre Authentifizierungsagenten installiert sind. APP1 sollte in der Liste angezeigt werden. Schließen Sie den Bereich **Pass-Through-Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="63979-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="63979-137">Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen „user1@testlab.\<Ihre öffentliche Domäne“ des Kontos „Benutzer1“ beim Ihrem Office 365-Abonnement anmelden können.</span><span class="sxs-lookup"><span data-stu-id="63979-137">Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="63979-138">Melden Sie sich auf APP1 von Office 365 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="63979-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="63979-p106">Wenn Sie aufgefordert werden, einen Benutzernamen und ein Kennwort anzugeben, geben Sie „Benutzer1@testlab.\<Ihre öffentliche Domäne> und das Kennwort für „Benutzer1“ an. Sie sollten sich erfolgreich als „Benutzer1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="63979-p106">When prompted for a user name and password, specify user1@testlab.\<your public domain> and the User1 password. You should successfully sign in as User1.</span></span>

<span data-ttu-id="63979-p107">„Benutzer1“ hat zwar Domänenadministratorberechtigungen für die Windows Server AD-Domäne „TESTLAB“, ist aber kein globaler Office 365-Administrator. Deshalb wird das Symbol **Administrator** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63979-p107">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="63979-143">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="63979-143">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="63979-145">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="63979-145">This configuration consists of:</span></span>

- <span data-ttu-id="63979-146">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>.</span><span class="sxs-lookup"><span data-stu-id="63979-146">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="63979-p108">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Ein Authentifizierungsagent wird auf APP1 für die Verarbeitung von Pass-Through-Authentifizierungsanfragen vom Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63979-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="63979-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="63979-149">Next step</span></span>

<span data-ttu-id="63979-150">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="63979-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="63979-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63979-151">See also</span></span>

[<span data-ttu-id="63979-152">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="63979-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="63979-153">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="63979-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="63979-154">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="63979-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


