---
title: Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren von Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921528"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a8c45-103">Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="a8c45-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a8c45-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 Enterprise- als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="a8c45-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a8c45-105">Organisationen, die ihre lokale Active Directory Domain Services(AD DS)-Infrastruktur direkt für die Authentifizierung bei Cloud-basierten Microsoft-Diensten und -Anwendungen verwenden möchten, können Pass-Through-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8c45-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="a8c45-106">Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für Pass-Through-Authentifizierung konfigurieren, was zu folgender Konfiguration führt:</span><span class="sxs-lookup"><span data-stu-id="a8c45-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="a8c45-108">Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="a8c45-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="a8c45-109">Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="a8c45-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="a8c45-110">Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a8c45-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a8c45-112">Klicken Sie [hier](../downloads/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8c45-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a8c45-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="a8c45-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a8c45-p102">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8c45-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a8c45-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="a8c45-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a8c45-118">Microsoft 365 E5-Testversion oder kostenpflichtiges Abonnement.</span><span class="sxs-lookup"><span data-stu-id="a8c45-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="a8c45-119">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="a8c45-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="a8c45-120">Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements regelmäßig zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a8c45-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="a8c45-121">Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a8c45-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="a8c45-122">In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für die Verwendung von Pass-Through-Authentifizierung und vergewissern sich dann, dass sie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a8c45-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="a8c45-123">Konfigurieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="a8c45-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="a8c45-124">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="a8c45-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="a8c45-125">Führen Sie Azure AD Connect über den Desktop von APP1 aus.</span><span class="sxs-lookup"><span data-stu-id="a8c45-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="a8c45-126">Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="a8c45-127">Klicken Sie auf der Seite „Weitere Aufgaben“ auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="a8c45-128">Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="a8c45-129">Klicken Sie auf der Seite **Benutzeranmeldung** auf **Pass-Through-Authentifizierung**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="a8c45-130">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="a8c45-131">Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="a8c45-p104">Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Pass-Through-Authentifizierung** als **Aktiviert** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8c45-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="a8c45-p105">Klicken Sie auf **Pass-Through-Authentifizierung**. Im Bereich **Pass-Through-Authentifizierung** werden die Server aufgeführt, auf denen Ihre Authentifizierungsagenten installiert sind. APP1 sollte in der Liste angezeigt werden. Schließen Sie den Bereich **Pass-Through-Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="a8c45-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="a8c45-138">Testen Sie als Nächstes die Möglichkeit, sich bei Ihrem Abonnement mit dem <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="a8c45-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="a8c45-139">Benutzername des User1-Kontos.</span><span class="sxs-lookup"><span data-stu-id="a8c45-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="a8c45-140">Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="a8c45-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="a8c45-141">Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<your public domain> ein</span><span class="sxs-lookup"><span data-stu-id="a8c45-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="a8c45-142">und das Kennwort für User1.</span><span class="sxs-lookup"><span data-stu-id="a8c45-142">and the User1 password.</span></span> <span data-ttu-id="a8c45-143">Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="a8c45-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="a8c45-144">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="a8c45-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="a8c45-145">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8c45-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="a8c45-146">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="a8c45-146">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="a8c45-148">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="a8c45-148">This configuration consists of:</span></span>

- <span data-ttu-id="a8c45-149">Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit dem Testlab der DNS-Domäne.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="a8c45-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="a8c45-150">registriert.</span><span class="sxs-lookup"><span data-stu-id="a8c45-150">registered.</span></span>
- <span data-ttu-id="a8c45-p110">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Ein Authentifizierungsagent wird auf APP1 für die Verarbeitung von Pass-Through-Authentifizierungsanfragen vom Azure AD-Mandanten Ihres Microsoft 365-Abonnements ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8c45-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8c45-153">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a8c45-153">Next step</span></span>

<span data-ttu-id="a8c45-154">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="a8c45-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8c45-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8c45-155">See also</span></span>

[<span data-ttu-id="a8c45-156">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8c45-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8c45-157">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8c45-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a8c45-158">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8c45-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)