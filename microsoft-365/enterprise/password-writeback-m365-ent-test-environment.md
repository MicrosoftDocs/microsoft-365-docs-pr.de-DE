---
title: Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Zusammenfassung: Konfigurieren des Rückschreibens des Kennworts für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921480"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b33cb-103">Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b33cb-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b33cb-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="b33cb-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b33cb-105">Benutzer können das Kennwortrückschreiben verwenden, um ihre Kennwörter über Azure Active Directory (Azure AD) zu aktualisieren, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="b33cb-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="b33cb-106">Beim Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über den lokalen AD DS aktualisieren, in dem ihre ursprünglichen Benutzerkonten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="b33cb-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="b33cb-107">Dies hilft Roaming- oder Remotebenutzern, die über keine Remotezugriffsverbindung zu ihrem lokalen Netzwerk verfügen.</span><span class="sxs-lookup"><span data-stu-id="b33cb-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="b33cb-108">In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für das Kennwortrückschreiben konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b33cb-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="b33cb-109">Das Konfigurieren der Testumgebung für das Kennwortrückschreiben umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="b33cb-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="b33cb-110">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b33cb-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="b33cb-111">Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"</span><span class="sxs-lookup"><span data-stu-id="b33cb-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b33cb-113">Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="b33cb-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b33cb-114">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b33cb-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b33cb-115">Befolgen Sie zunächst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b33cb-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="b33cb-116">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="b33cb-116">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b33cb-118">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="b33cb-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="b33cb-119">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b33cb-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="b33cb-120">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="b33cb-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="b33cb-121">Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne „TESTLAB“ mit dem Azure AD-Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b33cb-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="b33cb-122">Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"</span><span class="sxs-lookup"><span data-stu-id="b33cb-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="b33cb-123">Konfigurieren Sie zuerst das Konto „User1“ mit der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="b33cb-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="b33cb-124">Melden Sie sich aus dem [Microsoft 365 Admin Center](https://portal.microsoft.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="b33cb-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="b33cb-125">Wählen **Sie Aktive Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="b33cb-126">Wählen Sie **auf der** Seite Aktive Benutzer das **Konto "User1"** aus.</span><span class="sxs-lookup"><span data-stu-id="b33cb-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="b33cb-127">Wählen Sie **im Bereich Benutzer1** **neben** Rollen bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="b33cb-128">Wählen Sie **im Bereich Benutzerrollen** bearbeiten für Benutzer1 die Option **Globaler Administrator** aus, wählen Sie **Speichern** und dann **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="b33cb-129">Als Nächstes konfigurieren Sie das Konto "User1" mit den Sicherheitseinstellungen, mit denen es Kennwörter im Auftrag von anderen Benutzern in der AD DS-Domäne "TESTLAB" ändern kann.</span><span class="sxs-lookup"><span data-stu-id="b33cb-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="b33cb-130">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.</span><span class="sxs-lookup"><span data-stu-id="b33cb-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="b33cb-131">Wählen Sie auf dem Desktop von APP1 **Start**, geben Sie **aktiv** ein, und wählen Sie dann **Active Directory-Benutzer und -Computer aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="b33cb-132">Wählen Sie auf der Menüleiste Ansicht **aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="b33cb-133">Wenn **Erweiterte Features** nicht aktiviert sind, wählen Sie sie aus, um sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b33cb-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="b33cb-134">Wählen Sie im Strukturbereich Ihre Domäne aus, und halten Sie sie (oder klicken Sie mit der rechten Maustaste), wählen Sie **Eigenschaften** aus, und wählen Sie dann **die** Registerkarte Sicherheit aus.</span><span class="sxs-lookup"><span data-stu-id="b33cb-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="b33cb-135">Wählen Sie **Erweitert** aus.</span><span class="sxs-lookup"><span data-stu-id="b33cb-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="b33cb-136">Wählen Sie **auf der** Registerkarte Berechtigungen die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="b33cb-137">Wählen **Sie Prinzipal auswählen** aus, geben Sie **Benutzer1 ein,** und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="b33cb-138">Wählen Sie unter **Gilt für** die Option **Untergeordnete Benutzerobjekte** aus.</span><span class="sxs-lookup"><span data-stu-id="b33cb-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="b33cb-139">Wählen Sie unter **Berechtigungen** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b33cb-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="b33cb-140">**Kennwort ändern**</span><span class="sxs-lookup"><span data-stu-id="b33cb-140">**Change password**</span></span>
    - <span data-ttu-id="b33cb-141">**Kennwort zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="b33cb-141">**Reset password**</span></span>

10. <span data-ttu-id="b33cb-142">Wählen Sie unter **Eigenschaften** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b33cb-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="b33cb-143">**Write lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="b33cb-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="b33cb-144">**Write pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="b33cb-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="b33cb-145">Wählen **Sie dreimal OK** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b33cb-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="b33cb-146">Schließen Sie **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="b33cb-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="b33cb-147">Konfigurieren Sie als Nächstes Azure AD Connect auf APP1 für das Rückschreiben des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="b33cb-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="b33cb-148">Verbinden Sie APP1 bei Bedarf mit dem Konto „TESTLAB\User1“.</span><span class="sxs-lookup"><span data-stu-id="b33cb-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="b33cb-149">Doppelklicken Sie auf dem Desktop von APP1 auf **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="b33cb-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="b33cb-150">Wählen Sie **auf der Seite Willkommen** die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="b33cb-151">Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Synchronisierungsoptionen anpassen** aus, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="b33cb-152">Geben Sie **auf der Seite Verbindung mit Azure AD** herstellen Ihre Anmeldeinformationen für ihr globales Administratorkonto ein, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="b33cb-153">Wählen Sie auf den Seiten Connect **directories** und **Domain/OU filtering** die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="b33cb-154">Wählen Sie **auf der** Seite Optionale Features die Option **Kennwortrückschreiben** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="b33cb-155">Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option **Konfigurieren** aus, und warten Sie, bis der Prozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b33cb-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="b33cb-156">Wenn die Konfiguration abgeschlossen ist, wählen Sie **Beenden aus.**</span><span class="sxs-lookup"><span data-stu-id="b33cb-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="b33cb-157">Sie können nun das Kennwortrückschreiben für Benutzer auf Computern testen, die nicht mit dem virtuellen Netzwerk Ihres simulierten Intranets verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b33cb-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="b33cb-158">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="b33cb-158">Your resulting configuration looks like this:</span></span>

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="b33cb-160">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="b33cb-160">This configuration consists of:</span></span>

- <span data-ttu-id="b33cb-161">Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="b33cb-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="b33cb-162">registriert.</span><span class="sxs-lookup"><span data-stu-id="b33cb-162">registered.</span></span>
- <span data-ttu-id="b33cb-163">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="b33cb-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="b33cb-164">Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b33cb-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="b33cb-165">Kennwortrückschreiben ist aktiviert, damit Benutzer ihre Kennwörter über Azure Active Directory ändern können, ohne mit dem vereinfachten Intranet verbunden sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b33cb-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="b33cb-166">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b33cb-166">Next step</span></span>

<span data-ttu-id="b33cb-167">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="b33cb-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b33cb-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b33cb-168">See also</span></span>

[<span data-ttu-id="b33cb-169">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b33cb-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b33cb-170">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b33cb-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b33cb-171">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b33cb-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)