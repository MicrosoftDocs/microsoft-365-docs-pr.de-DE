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
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921504"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="d5b90-103">Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d5b90-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="d5b90-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 Enterprise- als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d5b90-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d5b90-105">Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d5b90-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="d5b90-106">In diesem Artikel wird beschrieben, wie Sie ihrer Microsoft 365-Testumgebung die Kennworthashsynchronisierung hinzufügen können, was zu dieser Konfiguration führt:</span><span class="sxs-lookup"><span data-stu-id="d5b90-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="d5b90-108">Das Einrichten dieser Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="d5b90-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="d5b90-109">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="d5b90-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="d5b90-110">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="d5b90-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="d5b90-111">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="d5b90-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="d5b90-112">Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d5b90-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="d5b90-113">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="d5b90-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="d5b90-114">Befolgen Sie die Anweisungen in [simulierter Unternehmensbasiskonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d5b90-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="d5b90-115">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d5b90-115">Your resulting configuration looks like this:</span></span>
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="d5b90-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="d5b90-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="d5b90-118">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d5b90-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="d5b90-119">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem virtuellen Azure-Netzwerk besteht.</span><span class="sxs-lookup"><span data-stu-id="d5b90-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="d5b90-120">DC1 ist ein Domänencontroller für das testlab.<*öffentlichen* Domänennamen> AD DS-Domäne.</span><span class="sxs-lookup"><span data-stu-id="d5b90-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="d5b90-121">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="d5b90-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="d5b90-122">Fügen Sie in dieser Phase eine öffentliche DNS-Domäne hinzu, und fügen Sie sie dann Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5b90-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="d5b90-123">Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um einen neuen öffentlichen DNS-Domänennamen zu erstellen, der auf Ihrem aktuellen Domänennamen basiert, und fügen Sie ihn dann Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5b90-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="d5b90-124">Es wird empfohlen, den Namen **testlab.<*Ihrer öffentlichen Domäne zu verwenden.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="d5b90-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="d5b90-125">Wenn Ihr öffentlicher Domänenname beispielsweise **<span>contoso</span>.com** ist, fügen Sie den öffentlichen Domänennamen hinzu: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="d5b90-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="d5b90-126">Fügen Sie als Nächstes **das  > Testlab.<** Ihrer öffentlichen Domäne zu Ihrem Microsoft 365-Test- oder kostenpflichtigen Abonnement hinzu, indem Sie den Domänenregistrierungsprozess durchfahren.</span><span class="sxs-lookup"><span data-stu-id="d5b90-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="d5b90-127">Dies besteht aus dem Hinzufügen zusätzlicher DNS-Einträge zum **testlab.<*Ihrer öffentlichen Domäne.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="d5b90-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="d5b90-128">Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d5b90-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="d5b90-129">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d5b90-129">Your resulting configuration looks like this:</span></span>
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="d5b90-131">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="d5b90-131">This configuration consists of:</span></span>

- <span data-ttu-id="d5b90-132">Ein Microsoft 365 E5-Test- oder kostenpflichtiges Abonnement mit  der DNS-Domäne testlab.<Ihren öffentlichen Domänennamen> registriert.</span><span class="sxs-lookup"><span data-stu-id="d5b90-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="d5b90-133">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="d5b90-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="d5b90-134">Beachten Sie, wie testlab.<*Ihrem öffentlichen* Domänennamen> ist:</span><span class="sxs-lookup"><span data-stu-id="d5b90-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="d5b90-135">Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d5b90-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="d5b90-136">In Ihren Microsoft 365-Abonnements registriert.</span><span class="sxs-lookup"><span data-stu-id="d5b90-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="d5b90-137">Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.</span><span class="sxs-lookup"><span data-stu-id="d5b90-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="d5b90-138">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="d5b90-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="d5b90-139">Installieren und konfigurieren Sie in dieser Phase das Azure AD Connect-Tool auf APP1, und überprüfen Sie dann, ob es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d5b90-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="d5b90-140">Installieren und konfigurieren Sie zunächst Azure AD Connect auf APP1.</span><span class="sxs-lookup"><span data-stu-id="d5b90-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="d5b90-141">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="d5b90-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="d5b90-142">Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="d5b90-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="d5b90-143">Wählen Sie auf der Taskleiste **Internet Explorer aus,** und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="d5b90-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="d5b90-144">Wählen Sie auf der Seite Microsoft Azure Active Directory Connect die Option **Herunterladen** aus, und wählen Sie dann **Ausführen aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="d5b90-145">Wählen Sie **auf der Seite Willkommen** bei Azure AD Connect die Option **Ich** stimme zu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="d5b90-146">Wählen Sie auf der Seite **Expresseinstellungen** die Option **Expresseinstellungen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="d5b90-147">Geben Sie **auf der Seite** Verbindung mit Azure AD herstellen den Namen Ihres globalen Administratorkontos in Benutzername **ein,** geben Sie das Kennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="d5b90-148">Geben Sie auf der Seite Verbindung mit **AD DS** herstellen **TESTLAB \\ Benutzer1** in **Benutzername ein,** geben Sie das Kennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="d5b90-149">Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option Installieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="d5b90-150">Wählen Sie **auf der Seite Konfiguration abgeschlossen** die Option Beenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="d5b90-151">Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="d5b90-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="d5b90-152">Wählen Sie im linken Navigationsbereich Benutzer **> Aktive Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="d5b90-153">Sie sehen das Konto **Benutzer 1**.</span><span class="sxs-lookup"><span data-stu-id="d5b90-153">Note the account named **User1**.</span></span> <span data-ttu-id="d5b90-154">Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d5b90-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="d5b90-155">Wählen Sie **das Benutzerkonto 1** aus, und wählen Sie dann **Lizenzen und Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="d5b90-156">Wählen **Sie unter** Produktlizenzen Ihren Standort aus (falls erforderlich), deaktivieren Sie die Office **365 E5-Lizenz,** und aktivieren Sie dann die Microsoft **365 E5-Lizenz.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="d5b90-157">Wählen **Sie unten** auf der Seite Speichern aus, und wählen Sie dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="d5b90-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="d5b90-158">Testen Sie als Nächstes die Möglichkeit, sich bei Ihrem Abonnement mit dem **user1@testlab.< >** Ihrem Domänennamenbenutzernamen des Benutzerkontos "User1" zu anmelden:</span><span class="sxs-lookup"><span data-stu-id="d5b90-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="d5b90-159">Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="d5b90-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="d5b90-160">Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben **User1@testlab.< >** Domänennamen und das Kennwort User1 an.</span><span class="sxs-lookup"><span data-stu-id="d5b90-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="d5b90-161">Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="d5b90-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="d5b90-162">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="d5b90-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="d5b90-163">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5b90-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="d5b90-164">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="d5b90-164">Your resulting configuration looks like this:</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="d5b90-166">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="d5b90-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="d5b90-167">Microsoft 365 E5- oder Office 365 E5-Testversionen oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.<*Ihrem* Domänennamen> registriert.</span><span class="sxs-lookup"><span data-stu-id="d5b90-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="d5b90-168">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="d5b90-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="d5b90-169">Azure AD Connect wird auf APP1 ausgeführt, um die DOMÄNE TESTLAB AD DS regelmäßig mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d5b90-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="d5b90-170">Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="d5b90-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5b90-171">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d5b90-171">Next step</span></span>

<span data-ttu-id="d5b90-172">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="d5b90-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5b90-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5b90-173">See also</span></span>

[<span data-ttu-id="d5b90-174">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d5b90-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d5b90-175">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d5b90-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d5b90-176">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d5b90-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)