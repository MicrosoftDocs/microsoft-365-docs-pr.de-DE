---
title: Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren des Rückschreibens des Kennworts für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 8148341359b66b147ecc5cf9b4927621db1f78dd
ms.sourcegitcommit: 6f94b7a272e33c492957336eae28f439e438c85b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "29993226"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c10dc-103">Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c10dc-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c10dc-p101">Mit dem Rückschreiben des Kennworts können Benutzer ihre Kennwörter über Azure Active Directory (Azure AD) aktualisieren, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird. Dank dem Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über das lokale Windows Server AD aktualisieren, wo ihre ursprünglichen Benutzerkonten gespeichert sind. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="c10dc-p101">Password writeback allows users to update their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="c10dc-107">Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für das Kennwortrückschreiben konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c10dc-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="c10dc-108">Die Einrichtung besteht aus zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="c10dc-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="c10dc-109">Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="c10dc-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="c10dc-110">Aktivieren Sie das Kennwortrückschreiben für die Windows Server AD-Domäne „TESTLAB“.</span><span class="sxs-lookup"><span data-stu-id="c10dc-110">Enable password writeback for the TESTLAB Windows Server AD domain.</span></span>
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c10dc-112">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c10dc-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c10dc-113">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c10dc-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c10dc-p102">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c10dc-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="c10dc-117">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="c10dc-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="c10dc-118">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5.</span><span class="sxs-lookup"><span data-stu-id="c10dc-118">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="c10dc-119">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="c10dc-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="c10dc-120">Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory-Domäne TESTLAB von Windows Server mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="c10dc-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a><span data-ttu-id="c10dc-121">Phase 2: Aktivieren Sie das Kennwortrückschreiben für die Windows Server AD-Domäne „TESTLAB“.</span><span class="sxs-lookup"><span data-stu-id="c10dc-121">Phase 2: Enable password writeback for the TESTLAB Windows Server AD domain</span></span>

<span data-ttu-id="c10dc-122">Konfigurieren Sie zuerst das Konto „User1“ mit der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="c10dc-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="c10dc-123">Melden Sie sich aus dem [Office-Portal](https://office.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="c10dc-123">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="c10dc-p103">Klicken Sie auf die Kachel **Admin** Kachel. Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="c10dc-126">Klicken Sie auf der Seite **Aktive Benutzer** auf das Konto **Benutzer 1**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="c10dc-127">Klicken Sie im Bereich **User1** auf **Bearbeiten** neben **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="c10dc-p104">Klicken Sie im Bereich **Benutzerrollen bearbeiten** für User1 auf **Globaler Administrator**. Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="c10dc-130">Als Nächstes konfigurieren Sie das Konto „User1“ mit den Sicherheitseinstellungen, mit denen es Kennwörter im Auftrag von anderen Benutzern in der Windows Satz AD-Domäne „TESTLAB“ ändern kann.</span><span class="sxs-lookup"><span data-stu-id="c10dc-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB Windows Server AD domain.</span></span>

1. <span data-ttu-id="c10dc-131">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="c10dc-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="c10dc-132">Klicken Sie auf dem Desktop von APP1 auf **Start**, geben Sie **active** ein, und klicken Sie dann auf **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="c10dc-p105">Klicken Sie in der Menüleiste auf **Ansicht**. Wenn **Erweiterte Funktionen** nicht aktiviert ist, klicken Sie darauf, um diese Option zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c10dc-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="c10dc-135">Klicken Sie im Strukturbereich mit der rechten Maustaste auf Ihre Domäne, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="c10dc-136">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="c10dc-137">Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="c10dc-138">Klicken Sie auf **Prinzipal auswählen**, geben Sie **User1** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="c10dc-139">Wählen Sie unter **Gilt für** die Option **Untergeordnete Benutzerobjekte** aus.</span><span class="sxs-lookup"><span data-stu-id="c10dc-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="c10dc-140">Wählen Sie unter **Berechtigungen** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c10dc-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="c10dc-141">Kennwort ändern</span><span class="sxs-lookup"><span data-stu-id="c10dc-141">Change password</span></span>
    - <span data-ttu-id="c10dc-142">Kennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="c10dc-142">Reset password</span></span>

10. <span data-ttu-id="c10dc-143">Wählen Sie unter **Eigenschaften** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c10dc-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="c10dc-144">Write lockoutTime</span><span class="sxs-lookup"><span data-stu-id="c10dc-144">Write lockoutTime</span></span>
    - <span data-ttu-id="c10dc-145">Write pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="c10dc-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="c10dc-146">Klicken Sie dreimal auf **OK**, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c10dc-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="c10dc-147">Schließen Sie **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="c10dc-148">Konfigurieren Sie als Nächstes Azure AD Connect auf APP1 für das Rückschreiben des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="c10dc-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="c10dc-149">Verbinden Sie APP1 bei Bedarf mit dem Konto „TESTLAB\User1“.</span><span class="sxs-lookup"><span data-stu-id="c10dc-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="c10dc-150">Doppelklicken Sie auf dem Desktop von APP1 auf **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="c10dc-151">Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="c10dc-152">Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Synchronisierungsoptionen anpassen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="c10dc-153">Geben Sie auf der Seite **Mit Azure AD verbinden** die Kontoanmeldeinformationen für User1 ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-153">On the **Connect to Azure AD** page, type the User 1 account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="c10dc-154">Klicken sie auf den Seiten **Verzeichnisse verbinden** und **Domänen-/OE-Filterung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="c10dc-155">Wählen Sie auf der Seite **Optionale Funktionen** die Option **Kennwortrückschreiben** aus, und klicken Sie auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="c10dc-155">On the **Optional features** page, select **Password writeback** and click Next.</span></span> 

8. <span data-ttu-id="c10dc-156">Klicken Sie auf der Seite **Bereit zum Konfigurieren** auf **Konfigurieren** und warten Sie, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c10dc-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="c10dc-157">Wenn die Option zum Abschließen der Konfiguration angezeigt wird, klicken Sie auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="c10dc-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="c10dc-158">Sie können jetzt das Kennwortrückschreiben für Benutzer auf Computern testen, die nicht mit dem virtuellen Netzwerk Ihres simulierten Intranets verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="c10dc-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="c10dc-159">Nachfolgend sehen Sie die daraus resultierende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="c10dc-159">Here is your resulting configuration:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="c10dc-161">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="c10dc-161">This configuration consists of:</span></span>

- <span data-ttu-id="c10dc-162">Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>.</span><span class="sxs-lookup"><span data-stu-id="c10dc-162">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="c10dc-163">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="c10dc-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="c10dc-164">Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements mit der Windows Server AD-Domäne TESTLAB zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="c10dc-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="c10dc-165">Kennwortrückschreiben ist aktiviert, damit Benutzer ihre Kennwörter über Azure Active Directory ändern können, ohne mit dem vereinfachten Intranet verbunden sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c10dc-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="c10dc-166">Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-password-writeback.md) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren des Kennwortrückschreibens in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="c10dc-166">See the [Simplify password updates](identity-password-writeback.md) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c10dc-167">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c10dc-167">Next step</span></span>

<span data-ttu-id="c10dc-168">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="c10dc-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c10dc-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c10dc-169">See also</span></span>

[<span data-ttu-id="c10dc-170">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c10dc-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c10dc-171">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c10dc-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c10dc-172">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c10dc-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


