---
title: Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
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
- seo-marvel-apr2020
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Demonstrieren der Kennworthashsynchronisierung und Anmeldung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 2930d147e2ae3277b0af4d2aa81a602c73128439
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686548"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="23688-103">Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="23688-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="23688-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="23688-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="23688-105">Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="23688-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="23688-106">In diesem Artikel wird beschrieben, wie Sie Kennwort-Hash-Synchronisierung in der Microsoft 365-Testumgebung hinzufügen können, woraus die folgende Konfiguration resultiert:</span><span class="sxs-lookup"><span data-stu-id="23688-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="23688-108">Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="23688-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="23688-109">Erstellen der simulierten Microsoft 365-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="23688-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="23688-110">Installieren und Konfigurieren von Azure AD Connect auf APP1.</span><span class="sxs-lookup"><span data-stu-id="23688-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="23688-111">Wechseln Sie zu [Microsoft 365 for Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) für eine visuelle Zuordnung zu allen Artikeln im Stapel Microsoft 365 for Enterprise Test Lab Guide.</span><span class="sxs-lookup"><span data-stu-id="23688-111">Go to [Microsoft 365 for enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="23688-112">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="23688-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="23688-p102">Befolgen Sie die Anweisungen in der [simulierten Unternehmensstandardkonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Damit wird die Konfiguration unten implementiert.</span><span class="sxs-lookup"><span data-stu-id="23688-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="23688-116">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="23688-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="23688-117">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="23688-117">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="23688-118">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem virtuellen Azure-Netzwerk besteht.</span><span class="sxs-lookup"><span data-stu-id="23688-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="23688-119">DC1 ist ein Domänencontroller für testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="23688-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="23688-120">AD DS-Domäne.</span><span class="sxs-lookup"><span data-stu-id="23688-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="23688-121">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="23688-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="23688-122">In dieser Phase fügen Sie eine öffentliche DNS-Domäne zu Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="23688-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="23688-123">Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um basierend auf Ihrem aktuellen Domänennamen einen neuen öffentlichen DNS-Domänennamen zu erstellen und diesen Ihrem Abonnement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="23688-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="23688-124">Es wird empfohlen, dass Sie den Namen **testlab.**\<your public domain> verwenden.</span><span class="sxs-lookup"><span data-stu-id="23688-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="23688-125">Wenn Ihre öffentliche Domänenname beispielsweise **<span>contoso</span>.com** ist, fügen Sie den öffentlichen Domänennamen **<span>testlab</span>.contoso.com** hinzu.</span><span class="sxs-lookup"><span data-stu-id="23688-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="23688-126">Als Nächstes fügen Sie **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="23688-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="23688-127">Domäne zu Ihrem Microsoft 365-Test-oder kostenpflichtigen Abonnement, indem Sie den Domänen Registrierungsprozessdurch gehen.</span><span class="sxs-lookup"><span data-stu-id="23688-127">domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="23688-128">Dies umfasst das Hinzufügen von zusätzlichen DNS-Einträgen zur Domäne **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="23688-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="23688-129">Domain vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="23688-129">domain.</span></span> <span data-ttu-id="23688-130">Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="23688-130">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span> 

<span data-ttu-id="23688-131">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="23688-131">Here is your resulting configuration.</span></span>
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="23688-133">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="23688-133">This configuration consists of:</span></span>

- <span data-ttu-id="23688-134">Ein Microsoft 365 E5-Test-oder kostenpflichtiges Abonnement mit der DNS-Domäne testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="23688-134">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="23688-135">registriert.</span><span class="sxs-lookup"><span data-stu-id="23688-135">registered.</span></span>
- <span data-ttu-id="23688-136">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="23688-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="23688-137">Beachten Sie, wie wir testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="23688-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="23688-138">heißt jetzt:</span><span class="sxs-lookup"><span data-stu-id="23688-138">is now:</span></span>

- <span data-ttu-id="23688-139">Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="23688-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="23688-140">In Ihren Microsoft 365-Abonnements registriert.</span><span class="sxs-lookup"><span data-stu-id="23688-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="23688-141">Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.</span><span class="sxs-lookup"><span data-stu-id="23688-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="23688-142">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="23688-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="23688-143">In dieser Phase installieren und konfigurieren Sie das Azure AD Connect-Tool auf APP1 und vergewissern sich, dass es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="23688-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="23688-144">Installieren Sie zunächst Azure AD Connect auf APP1 und konfigurieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="23688-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="23688-145">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="23688-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="23688-146">Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="23688-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="23688-147">Klicken Sie auf der Taskleiste auf **Internet Explorer**, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="23688-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="23688-148">Klicken Sie auf der Seite „Microsoft Azure Active Directory Connect“ auf **Herunterladen** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="23688-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="23688-149">Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme zu** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23688-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="23688-150">Klicken Sie auf der Seite **Express-Einstellungen** auf **Express-Einstellungen verwenden**.</span><span class="sxs-lookup"><span data-stu-id="23688-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="23688-151">Geben Sie auf der Seite **Mit Azure AD verbinden** unter **Benutzername** den Namen Ihres globalen Administratorkontos und unter **Kennwort** das zugehörige Kennwort ein. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23688-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="23688-152">Geben Sie auf der Seite **Mit AD DS verbinden** den Namen **TESTLAB\\Benutzer1** unter **Benutzername** und das zugehörige Kennwort unter **Kennwort** ein. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23688-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="23688-153">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="23688-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="23688-154">Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="23688-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="23688-155">Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="23688-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="23688-156">Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="23688-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="23688-157">Sie sehen das Konto **Benutzer 1**.</span><span class="sxs-lookup"><span data-stu-id="23688-157">Note the account named **User1**.</span></span> <span data-ttu-id="23688-158">Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="23688-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="23688-159">Klicken Sie auf das **User1**-Konto und dann auf **Lizenzen und Apps**.</span><span class="sxs-lookup"><span data-stu-id="23688-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="23688-160">Wählen Sie in **Produktlizenzen** Ihren Standort aus (sofern erforderlich), deaktivieren Sie die **Office 365 E5**-Lizenz, und aktivieren Sie die **Microsoft 365 E5**-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="23688-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="23688-161">Klicken Sie unten auf der Seite auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="23688-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="23688-162">Als nächstes testen Sie die Möglichkeit, sich mit <strong>user1@testlab.</strong>\<your domain name> bei Ihrem Abonnement anzumelden</span><span class="sxs-lookup"><span data-stu-id="23688-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="23688-163">Benutzername des User1-Kontos.</span><span class="sxs-lookup"><span data-stu-id="23688-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="23688-164">Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="23688-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="23688-165">Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<your domain name> ein</span><span class="sxs-lookup"><span data-stu-id="23688-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="23688-166">und das Kennwort für User1.</span><span class="sxs-lookup"><span data-stu-id="23688-166">and the User1 password.</span></span> <span data-ttu-id="23688-167">Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="23688-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="23688-168">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="23688-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="23688-169">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23688-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="23688-170">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="23688-170">Here is your resulting configuration.</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="23688-172">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="23688-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="23688-173">Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="23688-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="23688-174">registriert.</span><span class="sxs-lookup"><span data-stu-id="23688-174">registered.</span></span>
- <span data-ttu-id="23688-175">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="23688-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="23688-176">Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements regelmäßig zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="23688-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="23688-177">Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="23688-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="23688-178">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="23688-178">Next step</span></span>

<span data-ttu-id="23688-179">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="23688-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="23688-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23688-180">See also</span></span>

[<span data-ttu-id="23688-181">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="23688-181">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="23688-182">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="23688-182">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="23688-183">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="23688-183">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


