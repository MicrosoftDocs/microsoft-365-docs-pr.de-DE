---
title: Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung
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
description: 'Zusammenfassung: Konfigurieren und Demonstrieren der Kennworthashsynchronisierung und Anmeldung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 905242a8f9d820943bd063439bbcdf94c0cd92da
ms.sourcegitcommit: 42e4d280b562304335efc93787c89992504c5823
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538732"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="db224-103">Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="db224-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="db224-p101">Viele Organisationen verwenden Azure AD Connect und Kennworthashsynchronisierung, um den Kontensatz in ihrer lokalen Windows Server Active Directory (AD)-Gesamtstruktur mit dem Kontensatz im Azure AD-Mandanten ihrer Office 365- und EMS E5-Abonnements zu synchronisieren. In diesem Artikel wird beschrieben, wie Sie die Kennworthashsynchronisierung zu Ihrer Microsoft 365-Testumgebung hinzufügen und so die folgende Konfiguration implementieren können:</span><span class="sxs-lookup"><span data-stu-id="db224-p101">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Windows Server Active Directory (AD) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions. This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="db224-107">Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="db224-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="db224-108">Erstellen der simulierten Microsoft 365-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="db224-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="db224-109">Installieren und Konfigurieren von Azure AD Connect auf APP1.</span><span class="sxs-lookup"><span data-stu-id="db224-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="db224-110">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="db224-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="db224-111">Phase 1: Erstellen der simulierten Microsoft 365-Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="db224-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="db224-p102">Befolgen Sie die Anweisungen in der [simulierten Unternehmensstandardkonfiguration für Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Damit wird die Konfiguration unten implementiert.</span><span class="sxs-lookup"><span data-stu-id="db224-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![Die simulierte Unternehmensstandardkonfiguration](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="db224-115">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="db224-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="db224-116">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5</span><span class="sxs-lookup"><span data-stu-id="db224-116">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="db224-p103">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem virtuellen Azure-Netzwerk besteht. DC1 ist der Domänencontroller für die Windows Server AD-Domäne „testlab. \<Ihr öffentlicher Domänenname>.</span><span class="sxs-lookup"><span data-stu-id="db224-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network. DC1 is a domain controller for the testlab.\<your public domain name> Windows Server AD domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="db224-119">Phase 2: Erstellen und Registrieren der TestLab-Domäne</span><span class="sxs-lookup"><span data-stu-id="db224-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="db224-120">In dieser Phase fügen Sie eine öffentliche DNS-Domäne zu Ihrem Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="db224-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="db224-p104">Als erstes arbeiten Sie mit Ihrem öffentlichen DNS-Registrierungsanbieter, um einen neuen öffentlichen DNS-Domänennamen basierend auf Ihrem aktuellen Domänennamen zu erstellen, und fügen diesen Ihrem Office 365-Abonnement hinzu. Es wird empfohlen, dass Sie den Namen **testlab.**\<Ihre öffentliche Domäne> verwenden. Wenn Ihre öffentliche Domänenname beispielsweise <span>**contoso</span>.com** ist, fügen Sie den öffentlichen Domänennamen **<span>testlab</span>.contoso.com** hinzu.</span><span class="sxs-lookup"><span data-stu-id="db224-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="db224-p105">Als Nächstes fügen Sie die Domäne **testlab.**\<Ihre öffentliche Domäne> zu Ihrer Testversion oder zu Ihrem dauerhaften Abonnement von Office 365 hinzu, indem Sie den Domänenregistrierungsprozess durchlaufen. Dieser besteht aus dem Hinzufügen zusätzlicher DNS-Einträge zur Domäne **testlab.**\<Ihre öffentliche Domäne>. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern und Domänen zu Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="db224-p105">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or permanent subscription by going through the domain registration process. This consists of adding additional DNS records to the **testlab.**\<your public domain> domain. For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="db224-127">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="db224-127">Here is your resulting configuration.</span></span>
  
![Registrierung des Domänennamens „testlab“](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="db224-129">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="db224-129">This configuration consists of:</span></span>

- <span data-ttu-id="db224-130">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5 mit der registrierten DNS-Domäne „testlab.\<Name Ihrer öffentlichen Domäne>“</span><span class="sxs-lookup"><span data-stu-id="db224-130">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="db224-131">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="db224-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="db224-132">Für „testlab.\<Name Ihrer öffentlichen Domäne>“ gilt jetzt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="db224-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="db224-133">Die Domäne wird von öffentlichen DNS-Datensätzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db224-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="db224-134">Die Domäne ist in Ihren Office 365- und EMS-Abonnements registriert.</span><span class="sxs-lookup"><span data-stu-id="db224-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="db224-135">Die Domäne ist die Windows Server AD-Domäne in Ihrem simulierten Intranet.</span><span class="sxs-lookup"><span data-stu-id="db224-135">The Windows Server AD domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="db224-136">Phase 3: Installieren von Azure AD Connect auf APP1</span><span class="sxs-lookup"><span data-stu-id="db224-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="db224-137">In dieser Phase installieren und konfigurieren Sie das Azure AD Connect-Tool auf APP1 und vergewissern sich, dass es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="db224-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="db224-138">Installieren Sie zunächst Azure AD Connect auf APP1 und konfigurieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="db224-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="db224-139">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="db224-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="db224-140">Öffnen Sie über den Desktop auf APP1 eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="db224-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="db224-141">Klicken Sie auf der Taskleiste auf **Internet Explorer**, und wechseln Sie zu [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="db224-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="db224-142">Klicken Sie auf der Seite „Microsoft Azure Active Directory Connect“ auf **Herunterladen** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="db224-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="db224-143">Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Ich stimme zu** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db224-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="db224-144">Klicken Sie auf der Seite **Express-Einstellungen** auf **Express-Einstellungen verwenden**.</span><span class="sxs-lookup"><span data-stu-id="db224-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="db224-145">Geben Sie auf der Seite **Mit Azure AD verbinden** unter **Benutzername** den Namen Ihres globalen Office 365-Administratorkontos und unter **Kennwort** das zugehörige Kennwort ein. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db224-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="db224-146">Geben Sie auf der Seite **Mit AD DS verbinden** den Namen **TESTLAB\\Benutzer1** unter **Benutzername** und das zugehörige Kennwort unter **Kennwort** ein. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db224-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="db224-147">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="db224-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="db224-148">Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="db224-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="db224-149">Gehen Sie im Internet Explorer zum Office-Portal ([https://office.com](https://office.com)).</span><span class="sxs-lookup"><span data-stu-id="db224-149">In Internet Explorer, go to the Office 365 portal ([https://office.com](https://office.com)).</span></span>
    
12. <span data-ttu-id="db224-150">Klicken Sie auf der Hauptportalseite auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="db224-150">From the main portal page, click **Admin**.</span></span>
    
13. <span data-ttu-id="db224-151">Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="db224-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="db224-p106">Sie sehen das Konto **Benutzer1**. Dieses Konto gehört zur Windows Server AD-Domäne „TESTLAB“. Dass es angezeigt wird, belegt, dass die Verzeichnissynchronisierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="db224-p106">Note the account named **User1**. This account is from the TESTLAB Windows Server AD domain and is proof that directory synchronization has worked.</span></span>
    
14. <span data-ttu-id="db224-p107">Klicken Sie auf das Konto **Benutzer1**. Für Produktlizenzen klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="db224-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
15. <span data-ttu-id="db224-p108">Wählen Sie unter **Product licenses** Ihr Land/Ihre Region aus, und klicken Sie dann für **Office 365 Enterprise E5** auf **Off**. (So schalten Sie die Lizenz auf **On**.) Führen Sie für die Lizenz **Enterprise Mobility + Security E5** die gleichen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="db224-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

16. <span data-ttu-id="db224-158">Klicken Sie unten auf der Seite auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="db224-158">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="db224-159">Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen <strong>Benutzer1@testlab.</strong>\<Name Ihrer öffentlichen Domäne>“ des Kontos „Benutzer1“ bei Ihrem Office 365-Abonnement anmelden können.</span><span class="sxs-lookup"><span data-stu-id="db224-159">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="db224-160">Melden Sie sich auf APP1 von Office 365 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.</span><span class="sxs-lookup"><span data-stu-id="db224-160">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="db224-p109">Wenn Sie aufgefordert werden, einen Benutzernamen und ein Kennwort anzugeben: Geben Sie „<strong>user1@testlab.</strong>\<Name Ihrer öffentlichen Domäne>“ und das Kennwort für „Benutzer1“ an. Sie sollten sich erfolgreich als „Benutzer1“ anmelden können.</span><span class="sxs-lookup"><span data-stu-id="db224-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="db224-p110">„Benutzer1“ hat zwar Domänenadministratorberechtigungen für die Windows Server AD-Domäne „TESTLAB“, ist aber kein globaler Office 365-Administrator. Deshalb wird das Symbol **Administrator** nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db224-p110">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="db224-165">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="db224-165">Here is your resulting configuration.</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="db224-167">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="db224-167">This configuration consists of:</span></span> 
  
- <span data-ttu-id="db224-168">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>.</span><span class="sxs-lookup"><span data-stu-id="db224-168">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="db224-p111">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf APP1 ausgeführt, um die Windows Server Active Directory-Domäne „TESTLAB“ mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements regelmäßig zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="db224-p111">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="db224-171">Das Konto „Benutzer1“ in der Windows Server AD-Domäne „TESTLAB“ wurde mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="db224-171">The User1 account in the TESTLAB  Windows Server AD domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="db224-172">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="db224-172">Next step</span></span>

<span data-ttu-id="db224-173">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="db224-173">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="db224-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db224-174">See also</span></span>

[<span data-ttu-id="db224-175">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db224-175">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="db224-176">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db224-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="db224-177">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db224-177">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


