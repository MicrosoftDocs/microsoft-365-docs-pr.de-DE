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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487458"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b8671-103">Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b8671-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b8671-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="b8671-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b8671-105">Viele Organisationen verwenden Azure AD Connect und die Kennwort-Hash-Synchronisierung, um die Gruppe von Konten in ihrer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur mit den Konten im Azure AD-Mandanten ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b8671-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="b8671-106">In diesem Artikel wird beschrieben, wie Sie der Microsoft 365-Testumgebung eine Kennworthash Synchronisierung hinzufügen können, die zu dieser Konfiguration führt:</span><span class="sxs-lookup"><span data-stu-id="b8671-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="b8671-108">Das Einrichten dieser Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="b8671-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="b8671-109">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="b8671-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="b8671-110">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="b8671-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="b8671-111">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="b8671-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="b8671-112">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="b8671-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="b8671-113">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="b8671-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="b8671-114">Befolgen Sie die Anweisungen unter [simulierte Enterprise-Basiskonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b8671-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="b8671-115">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8671-115">Your resulting configuration looks like this:</span></span>
  
![Die simulierte Unternehmensstandardkonfiguration](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b8671-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="b8671-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="b8671-118">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b8671-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="b8671-119">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem virtuellen Azure-Netzwerk besteht.</span><span class="sxs-lookup"><span data-stu-id="b8671-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="b8671-120">DC1 ist ein Domänencontroller für die testlab. <*ihren öffentlichen Domänennamen*> AD DS Domäne.</span><span class="sxs-lookup"><span data-stu-id="b8671-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="b8671-121">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="b8671-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="b8671-122">Fügen Sie in dieser Phase eine öffentliche DNS-Domäne hinzu, und fügen Sie Sie dann Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8671-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="b8671-123">Arbeiten Sie zunächst mit Ihrem öffentlichen DNS-Registrierungsanbieter zusammen, um einen neuen öffentlichen DNS-Domänennamen zu erstellen, der auf dem aktuellen Domänennamen basiert, und fügen Sie ihn dann Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8671-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="b8671-124">Es wird empfohlen, den Namen \**testlab. <*ihrer öffentlichen Domäne\* > \*\*zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8671-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="b8671-125">Wenn Ihr öffentlicher Domänenname beispielsweise " \*\* <span>contoso</span>. com"\*\* lautet, fügen Sie den öffentlichen Domänennamen hinzu: \*\* <span>testlab</span>. contoso.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="b8671-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="b8671-126">Fügen Sie als nächstes das \**testlab. <*Ihrer Public Domain\* > \*\* -Domäne zu Ihrem Microsoft 365-Test-oder kostenpflichtigen Abonnement hinzu, indem Sie den Domänen Registrierungsprozessdurch gehen.</span><span class="sxs-lookup"><span data-stu-id="b8671-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="b8671-127">Dies umfasst das Hinzufügen zusätzlicher DNS-Einträge zum \**testlab. <*Ihrer Public Domain\* > \*\* -Domäne.</span><span class="sxs-lookup"><span data-stu-id="b8671-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="b8671-128">Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="b8671-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="b8671-129">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8671-129">Your resulting configuration looks like this:</span></span>
  
![Registrierung des Domänennamens „testlab“](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="b8671-131">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="b8671-131">This configuration consists of:</span></span>

- <span data-ttu-id="b8671-132">Ein Microsoft 365 E5-Test-oder kostenpflichtiges Abonnement mit der DNS-Domäne testlab. <*ihren öffentlichen Domänennamen*> registriert.</span><span class="sxs-lookup"><span data-stu-id="b8671-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="b8671-133">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="b8671-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="b8671-134">Beachten Sie, wie testlab. <*ihren öffentlichen Domänennamen*> jetzt lautet:</span><span class="sxs-lookup"><span data-stu-id="b8671-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="b8671-135">Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8671-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="b8671-136">In Ihren Microsoft 365-Abonnements registriert.</span><span class="sxs-lookup"><span data-stu-id="b8671-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="b8671-137">Die Domäne ist die AD DS-Domäne in Ihrem simulierten Intranet.</span><span class="sxs-lookup"><span data-stu-id="b8671-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="b8671-138">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="b8671-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="b8671-139">Installieren und konfigurieren Sie in dieser Phase das Azure AD Connect-Tool auf App1, und stellen Sie dann sicher, dass es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b8671-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="b8671-140">Installieren und konfigurieren Sie zunächst Azure AD Connect auf App1.</span><span class="sxs-lookup"><span data-stu-id="b8671-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="b8671-141">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="b8671-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="b8671-142">Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus, um die verstärkte Sicherheit in Internet Explorer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="b8671-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="b8671-143">Wählen Sie in der Taskleiste **Internet Explorer** aus, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="b8671-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="b8671-144">Wählen Sie auf der Seite Microsoft Azure Active Directory Verbindung die Option **herunterladen**aus, und wählen Sie dann **Ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="b8671-145">Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme**zu, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="b8671-146">Wählen Sie auf der Seite **Express-Einstellungen** die Option **Express-Einstellungen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="b8671-147">Geben Sie auf der Seite mit **Azure AD verbinden** den Namen Ihres globalen Administratorkontos in **username ein,** geben Sie sein Kennwort in **Kennwort**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8671-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="b8671-148">Geben Sie auf der Seite mit **AD DS verbinden** in **username** **TESTLAB \\ User1** ein, geben Sie das Kennwort in **Kennwort**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8671-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="b8671-149">Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option " **Installieren**" aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="b8671-150">Wählen Sie auf der Seite **Konfiguration abgeschlossen** die Option **Beenden**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="b8671-151">Wechseln Sie im Internet Explorer zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="b8671-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="b8671-152">Wählen Sie im linken Navigationsbereich die Option **Benutzer > aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="b8671-153">Sie sehen das Konto **Benutzer 1**.</span><span class="sxs-lookup"><span data-stu-id="b8671-153">Note the account named **User1**.</span></span> <span data-ttu-id="b8671-154">Dieses Konto gehört zur AD DS-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b8671-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="b8671-155">Wählen Sie das Konto **User1** aus, und wählen Sie dann **Lizenzen und apps**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="b8671-156">Wählen Sie unter **Produktlizenzen**Ihren Standort (falls erforderlich) aus, deaktivieren Sie die **Office 365 E5** -Lizenz, und aktivieren Sie dann die **Microsoft 365 E5** -Lizenz.</span><span class="sxs-lookup"><span data-stu-id="b8671-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="b8671-157">Klicken Sie unten auf der Seite auf **Speichern** , und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="b8671-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="b8671-158">Als nächstes testen Sie die Möglichkeit, sich bei Ihrem Abonnement mit dem \**User1@testlab anzumelden. <*Ihren Domänennamen\* > \*\* Benutzernamen des user1-Kontos:</span><span class="sxs-lookup"><span data-stu-id="b8671-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="b8671-159">Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="b8671-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="b8671-160">Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie \**User1@testlab. <*Ihren Domänennamen\* > \*\* und das user1-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="b8671-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="b8671-161">Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="b8671-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="b8671-162">Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="b8671-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="b8671-163">Daher wird das Symbol **Admin** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8671-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="b8671-164">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b8671-164">Your resulting configuration looks like this:</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="b8671-166">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="b8671-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="b8671-167">Microsoft 365 E5 oder Office 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB. <*Ihren Domänennamen*> registriert.</span><span class="sxs-lookup"><span data-stu-id="b8671-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="b8671-168">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="b8671-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="b8671-169">Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB AD DS Domäne regelmäßig mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b8671-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="b8671-170">Das Konto „Benutzer 1“ in der AD DS-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b8671-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="b8671-171">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b8671-171">Next step</span></span>

<span data-ttu-id="b8671-172">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="b8671-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8671-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8671-173">See also</span></span>

[<span data-ttu-id="b8671-174">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8671-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b8671-175">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8671-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b8671-176">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="b8671-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
