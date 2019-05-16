---
title: 'Phase 2: Beendigungskriterien für die Identitätsinfrastruktur'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für identitätsbasierte Dienste und Infrastrukturen erfüllt.
ms.openlocfilehash: aabd9f5db223b4b1aba0173dcfb739fe27553555
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072125"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="c1230-103">Phase 2: Beendigungskriterien für die Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="c1230-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c1230-104">Stellen Sie sicher, dass Ihre Identitätsinfrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="c1230-104">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="c1230-105">Unter [Voraussetzungen](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) finden Sie weitere Empfehlungen zur Identitätsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="c1230-105">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="c1230-106">Erforderlich: Alle Benutzer, Gruppen und Gruppenmitgliedschaften wurden erstellt</span><span class="sxs-lookup"><span data-stu-id="c1230-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="c1230-107">Sie haben Benutzerkonten und Gruppen zu folgenden Zwecken erstellt:</span><span class="sxs-lookup"><span data-stu-id="c1230-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="c1230-108">Mitarbeiter in Ihrer Organisation und die Lieferanten, Vertragsnehmer und Partner, die für oder mit Ihrer Organisation arbeiten, verfügen über ein entsprechendes Benutzerkonto in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c1230-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="c1230-109">Azure Active Directory-Gruppen und deren Mitglieder enthalten Benutzerkonten und andere Gruppen für verschiedene Zwecke, z. B. die Bereitstellung von Sicherheitseinstellungen für Microsoft Cloud Services, automatische Lizenzierung und weitere Verwendungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="c1230-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="c1230-110">Gegebenenfalls hilft Ihnen [Schritt 1](identity-plan-users-groups.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c1230-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="c1230-111">Erforderlich: Ihre globalen Administratorkonten sind geschützt</span><span class="sxs-lookup"><span data-stu-id="c1230-111">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="c1230-112">Sie haben [Ihre globalen Office 365-Administratorkonten geschützt](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts), um die Gefährdung von Anmeldeinformationen zu vermeiden, die zu Verstößen gegen ein Office 365-Abonnement führen kann.</span><span class="sxs-lookup"><span data-stu-id="c1230-112">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="c1230-113">Wenn Sie diese Anforderung überspringen, können Ihre globalen Administratorkonten anfällig für Angriffe und Kompromittierung sein. Dadurch kann ein Angreifer systemweiten Zugriff auf Ihre Daten erhalten, um diese zu stehlen, zu zerstören oder für Lösegeldforderungen zu missbrauchen.</span><span class="sxs-lookup"><span data-stu-id="c1230-113">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="c1230-114">Gegebenenfalls hilft Ihnen [Schritt 2](identity-designate-protect-admin-accounts.md#identity-global-admin), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c1230-114">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-115">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-115">How to test</span></span>

<span data-ttu-id="c1230-116">Gehen Sie folgendermaßen vor, um sicherzustellen, dass Sie Ihre globalen Administratorkonten geschützt haben:</span><span class="sxs-lookup"><span data-stu-id="c1230-116">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="c1230-p101">Führen Sie an der PowerShell-Eingabeaufforderung den folgenden Azure AD V2-Befehl aus. Nur die Liste der dedizierten globalen Administratorkonten sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1230-p101">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="c1230-p102">Melden Sie sich bei Office 365 mit jedem der Konten aus Schritt 1 an. Jede Anmeldung muss die mehrstufige Authentifizierung und die stärkste Form der sekundären Authentifizierung in Ihrer Organisation anfordern.</span><span class="sxs-lookup"><span data-stu-id="c1230-p102">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="c1230-121">Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden bei Office 365 finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c1230-121">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="c1230-122">Optional: Sie haben Privileged Identity Management zur Unterstützung einer bedarfsgesteuerten Zuweisung der globalen Administratorrolle eingerichtet</span><span class="sxs-lookup"><span data-stu-id="c1230-122">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="c1230-123">Sie haben nach den Anweisungen in [Konfigurieren von Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) PIM in Ihrem Azure AD-Mandanten aktiviert und Ihre globalen Administratorkonten als berechtigte Administratoren konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c1230-123">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="c1230-124">Sie haben auch die Empfehlungen in [Schützen des privilegierten Zugriffs für hybride und Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) befolgt, um eine Roadmap zu entwickeln, die den privilegierten Zugriff vor Cyberangriffen schützt.</span><span class="sxs-lookup"><span data-stu-id="c1230-124">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="c1230-125">Wenn Sie diese Option überspringen, sind Ihre globalen Administratorkonten ständigen Onlineangriffen ausgesetzt und können bei einer Gefährdung zulassen, dass ein Angreifer Ihre vertraulichen Informationen stiehlt, zerstört oder gegen Lösegeldforderungen sperrt.</span><span class="sxs-lookup"><span data-stu-id="c1230-125">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="c1230-126">Gegebenenfalls hilft Ihnen [Schritt 2](identity-designate-protect-admin-accounts.md#identity-pim) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-126">If needed, [Step 2](identity-designate-protect-admin-accounts.md#identity-pim) can help you with this option.</span></span>


<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="c1230-127">Erforderlich: Benutzer und Gruppen werden mit Azure AD synchronisiert</span><span class="sxs-lookup"><span data-stu-id="c1230-127">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="c1230-128">Wenn Sie einen vorhandenen lokalen Identitätsanbieter wie z. B. Active Directory Domain Services (AD DS) haben, haben Sie Azure AD Connect zum Synchronisieren von Benutzerkonten und Gruppen von Ihrem lokalen Identitätsanbieter mit Ihrem Azure AD-Mandanten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1230-128">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="c1230-129">Dank der Verzeichnissynchronisierung können sich Ihre Benutzer bei Office 365 und anderen Microsoft Cloud Services mit denselben Anmeldeinformationen anmelden, die sie zum Anmelden an ihren Computern und zum Zugriff auf lokale Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1230-129">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="c1230-130">Gegebenenfalls hilft Ihnen [Schritt 3](identity-azure-ad-connect.md#identity-sync), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c1230-130">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="c1230-131">Wenn Sie diese Anforderung überspringen, haben Sie zwei Sätze von Benutzerkonten und Gruppen:</span><span class="sxs-lookup"><span data-stu-id="c1230-131">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="c1230-132">Benutzerkonten und Gruppen, die in Ihrem lokalen Identitätsanbieter vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="c1230-132">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="c1230-133">Benutzerkonten und Gruppen, die in Ihrem Azure AD-Mandanten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="c1230-133">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="c1230-p103">In diesem Zustand müssen die beiden Sätze von Benutzerkonten und Gruppen manuell von IT-Administratoren und Benutzern verwaltet werden. Dies führt zwangsläufig zu nicht synchronisierten Konten, deren Kennwörtern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="c1230-p103">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-136">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-136">How to test</span></span>
<span data-ttu-id="c1230-137">Um zu überprüfen, ob die Authentifizierung mit lokalen Anmeldeinformationen funktioniert, melden Sie sich mit Ihren lokalen Anmeldeinformationen beim Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="c1230-137">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="c1230-138">Führen Sie folgende Schritte aus, um zu überprüfen, ob die Verzeichnissynchronisierung ordnungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="c1230-138">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="c1230-139">Erstellen Sie eine neue Testgruppe in AD DS.</span><span class="sxs-lookup"><span data-stu-id="c1230-139">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="c1230-140">Warten Sie, bis die Synchronisierungszeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="c1230-140">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="c1230-141">Überprüfen Sie Ihren Azure AD-Mandanten, um sicherzustellen, dass der Name der neuen Testgruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c1230-141">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="c1230-142">Optional: Verzeichnissynchronisierung wird überwacht</span><span class="sxs-lookup"><span data-stu-id="c1230-142">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="c1230-143">Sie haben [Azure AD Connect Health für die Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (für die Synchronisierung von Kennwörtern) oder [Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (für Verbundauthentifizierung) verwendet und Azure AD Connect Health bereitgestellt. Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c1230-143">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="c1230-144">Installieren des Azure AD Connect Health-Agents auf jedem Ihrer lokalen Identitätsserver.</span><span class="sxs-lookup"><span data-stu-id="c1230-144">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="c1230-145">Verwenden des Azure AD Connect Health-Portals zum Überwachen des Zustands der laufenden Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="c1230-145">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="c1230-146">Wenn Sie diese Option überspringen, können Sie den Zustand Ihrer cloudbasierten Identitätsinfrastruktur genauer beurteilen.</span><span class="sxs-lookup"><span data-stu-id="c1230-146">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="c1230-147">Gegebenenfalls hilft Ihnen [Schritt 3](identity-azure-ad-connect.md#identity-sync-health) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-147">If needed, [Step 3](identity-azure-ad-connect.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-148">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-148">How to test</span></span>
<span data-ttu-id="c1230-149">Das Azure AD Connect Health-Portal zeigt den aktuellen und korrekten Zustand Ihrer lokalen Identitätsserver und der fortlaufenden Synchronisierung an.</span><span class="sxs-lookup"><span data-stu-id="c1230-149">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="c1230-150">Optional: Die mehrstufige Authentifizierung ist für Ihre Benutzer aktiviert</span><span class="sxs-lookup"><span data-stu-id="c1230-150">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="c1230-151">Sie haben [Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan) und [Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) verwendet, um die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) für Ihre Benutzerkonten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c1230-151">You used [Plan for multi-factor authentication for Office 365 Deployments](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan) and [Set up multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="c1230-p104">Wenn Sie diese Option überspringen, sind die Benutzerkonten anfällig für eine Gefährdung der Anmeldeinformationen durch Cyberangriffe. Wenn das Kennwort eines Benutzerkontos manipuliert wurde, sind alle Ressourcen und Funktionen des Kontos, z. B. Administratorrollen, für den Angreifer verfügbar. Dadurch kann der Angreifer interne Dokumente und andere Daten kopieren, zerstören oder Lösegeld dafür verlangen.</span><span class="sxs-lookup"><span data-stu-id="c1230-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="c1230-155">Gegebenenfalls hilft Ihnen [Schritt 4](identity-multi-factor-authentication.md#identity-mfa) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-155">If needed, [Step 4](identity-multi-factor-authentication.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-156">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-156">How to test</span></span>

1.  <span data-ttu-id="c1230-157">Erstellen Sie im Office 365-Verwaltungsportal ein Testbenutzerkonto, und weisen Sie ihm eine Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="c1230-157">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="c1230-158">Konfigurieren Sie die mehrstufige Authentifizierung für das Testbenutzerkonto mit der zusätzlichen Überprüfungsmethode, die Sie für tatsächliche Benutzerkonten verwenden, z. B. Senden einer Nachricht an Ihr Telefon.</span><span class="sxs-lookup"><span data-stu-id="c1230-158">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="c1230-159">Melden Sie sich mit dem Testbenutzerkonto am Office 365- oder Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="c1230-159">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="c1230-160">Vergewissern Sie sich, dass Sie von MFA zur Eingabe der zusätzlichen Überprüfungsinformationen aufgefordert werden und die Authentifizierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c1230-160">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="c1230-161">Löschen Sie das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-161">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="c1230-162">Optional: Azure AD Identity Protection ist zum Schutz vor Gefährdung der Anmeldeinformationen aktiviert</span><span class="sxs-lookup"><span data-stu-id="c1230-162">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="c1230-163">Sie haben Azure AD Identity Protection zu folgenden Zwecken aktiviert:</span><span class="sxs-lookup"><span data-stu-id="c1230-163">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="c1230-164">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="c1230-164">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="c1230-165">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="c1230-165">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="c1230-166">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="c1230-166">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="c1230-p105">Wenn Sie diese Option überspringen, sind Sie nicht in der Lage, Kompromittierungsversuche von Anmeldeinformationen zu erkennen oder automatisch zu verhindern bzw. identitätsbezogene Sicherheitsvorfälle zu untersuchen. Dies macht Ihr Unternehmen potenziell anfällig für eine erfolgreiche Kompromittierung von Anmeldeinformationen und die resultierende Bedrohung für vertrauliche Daten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c1230-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="c1230-169">Gegebenenfalls hilft Ihnen [Schritt 4](identity-multi-factor-authentication.md#identity-ident-prot) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-169">If needed, [Step 4](identity-multi-factor-authentication.md#identity-ident-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="c1230-170">Optional: Benutzer können ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="c1230-170">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="c1230-171">Sie haben [Schnelle Bereitstellung der Self-Service-Kennwortzurücksetzung in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) verwendet, um die Kennwortzurücksetzung für die Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c1230-171">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="c1230-172">Wenn Sie diese Bedingung nicht erfüllen, sind Benutzer von Benutzerkontoadministratoren abhängig, um ihre Kennwörter zurückzusetzen, was zusätzlichen IT-Verwaltungsaufwand bedeutet.</span><span class="sxs-lookup"><span data-stu-id="c1230-172">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="c1230-173">Gegebenenfalls hilft Ihnen [Schritt 5](identity-password-reset.md#identity-pw-reset) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-173">If needed, [Step 5](identity-password-reset.md#identity-pw-reset) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-174">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-174">How to test</span></span>

1. <span data-ttu-id="c1230-175">Erstellen Sie ein Testbenutzerkonto mit einem anfänglichen Kennwort.</span><span class="sxs-lookup"><span data-stu-id="c1230-175">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="c1230-176">Führen Sie die Schritte in [Zulassen, dass Benutzer ihre eigenen Kennwörter in Office 365 zurücksetzen](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) aus, um das Kennwort für das Testbenutzerkonto zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="c1230-176">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="c1230-177">Melden Sie sich ab, und melden Sie sich dann mit dem zurückgesetzten Kennwort wieder am Testbenutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="c1230-177">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="c1230-178">Löschen Sie das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-178">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="c1230-179">Optional: Kennwortrückschreiben ist für Ihre Benutzer aktiviert</span><span class="sxs-lookup"><span data-stu-id="c1230-179">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="c1230-180">Sie haben die Anweisungen unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) befolgt, um das Kennwortrückschreiben für den Azure AD-Mandanten Ihres Microsoft 365 Enterprise-Abonnements zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c1230-180">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="c1230-181">Wenn Sie diese Option überspringen, müssen Benutzer, die nicht mit Ihrem lokalen Netzwerk verbunden sind, ihre AD DS-Kennwörter über einen IT-Administrator zurücksetzen oder entsperren.</span><span class="sxs-lookup"><span data-stu-id="c1230-181">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="c1230-182">Gegebenenfalls hilft Ihnen [Schritt 5](identity-password-reset.md#identity-pw-writeback) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-182">If needed, [Step 5](identity-password-reset.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="c1230-183">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn Azure AD ein hohes Risiko einer Kontogefährdung erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="c1230-183">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="c1230-184">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-184">How to test</span></span>

<span data-ttu-id="c1230-185">Sie testen das Kennwortrückschreiben durch Ändern Ihres Kennworts in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c1230-185">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="c1230-186">Sie sollten Ihr Konto und das neue Kennwort für den Zugriff auf lokale AD DS-Ressourcen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c1230-186">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="c1230-187">Erstellen Sie in Ihrem lokalen AD DS ein Testbenutzerkonto, lassen Sie Verzeichnissynchronisierung zu, und erteilen Sie dem Konto im Microsoft 365 Admin Center eine Office 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="c1230-187">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="c1230-188">Melden Sie sich von einem Remotecomputer, der Ihrer lokalen AD DS-Domäne angehört, mit den Anmeldeinformationen des Testbenutzerkontos beim Computer und beim Office-Portal an.</span><span class="sxs-lookup"><span data-stu-id="c1230-188">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="c1230-189">Wählen Sie **Einstellungen > Office 365-Einstellungen > Kennwort > Kennwort ändern**.</span><span class="sxs-lookup"><span data-stu-id="c1230-189">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="c1230-190">Geben Sie das aktuelle Kennwort ein, geben Sie ein neues Kennwort ein, und bestätigen Sie es dann.</span><span class="sxs-lookup"><span data-stu-id="c1230-190">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="c1230-191">Melden Sie sich beim Office-Portal und Remotecomputer ab, und melden Sie sich dann beim Computer mit dem Testbenutzerkonto und dem neuen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="c1230-191">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="c1230-192">Dies beweist, dass Sie das Kennwort eines lokalen AD DS-Benutzerkontos unter Verwendung des Azure AD-Mandanten ändern konnten.</span><span class="sxs-lookup"><span data-stu-id="c1230-192">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="c1230-193">Optional: Benutzer können Azure AD Seamless Single Sign-on für die Anmeldung verwenden</span><span class="sxs-lookup"><span data-stu-id="c1230-193">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="c1230-194">Sie haben [Azure AD Connect: Nahtloses einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) für Ihre Organisation aktiviert, um die Anmeldung von Benutzern bei cloudbasierten Anwendungen, z. B. Office 365, zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c1230-194">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="c1230-195">Wenn Sie diese Option überspringen, werden die Benutzer möglicherweise zur Eingabe von Anmeldeinformationen aufgefordert, wenn sie auf zusätzliche Anwendungen zugreifen, die Azure AD verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1230-195">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="c1230-196">Gegebenenfalls hilft Ihnen [Schritt 5](identity-password-reset.md#identity-sso) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-196">If needed, [Step 5](identity-password-reset.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="c1230-197">Optional: Der Office 365-Anmeldebildschirm ist für Ihre Organisation personalisiert</span><span class="sxs-lookup"><span data-stu-id="c1230-197">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="c1230-198">Sie haben entsprechend den Anweisungen unter [Hinzufügen eines Unternehmensbrandings zu den Anmelde- und Zugriffspanelseiten](http://aka.ms/aadpaddbranding) das Branding Ihrer Organisation auf der Anmeldeseite von Office 365 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c1230-198">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="c1230-199">Wenn Sie diese Option überspringen, sehen die Benutzer einen allgemeinen Office 365-Anmeldebildschirm und sind sich möglicherweise nicht sicher, dass sie sich auf der Website Ihrer Organisation anmelden.</span><span class="sxs-lookup"><span data-stu-id="c1230-199">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="c1230-200">Gegebenenfalls hilft Ihnen [Schritt 5](identity-password-reset.md#identity-custom-sign-in) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-200">If needed, [Step 5](identity-password-reset.md#identity-custom-sign-in) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-201">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-201">How to test</span></span>

<span data-ttu-id="c1230-p108">Melden Sie sich mit Ihrem Benutzerkontonamen und der mehrstufigen Authentifizierung am Office 365-Portal an. Ihre benutzerdefinierten Brandingelemente sollten auf der Anmeldeseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1230-p108">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="c1230-204">Optional: Self-Service-Gruppenverwaltung ist für bestimmte Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert</span><span class="sxs-lookup"><span data-stu-id="c1230-204">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="c1230-205">Sie haben bestimmt, welche Gruppen für Self-Service-Verwaltung geeignet sind, deren Besitzer bezüglich des Workflows und der Verantwortlichkeiten der Gruppenverwaltung instruiert und für diese Gruppen [die Self-Service-Verwaltung in Azure AD eingerichtet](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="c1230-205">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="c1230-206">Wenn Sie diese Option überspringen, müssen alle Verwaltungsaufgaben für Azure AD-Gruppen von IT-Administratoren erledigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1230-206">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="c1230-207">Gegebenenfalls hilft Ihnen [Schritt 6](identity-self-service-group-management.md#identity-self-service-groups) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-207">If needed, [Step 6](identity-self-service-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-208">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-208">How to test</span></span>
1.  <span data-ttu-id="c1230-209">Erstellen Sie ein Testbenutzerkonto in Azure AD mit dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="c1230-209">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="c1230-210">Melden Sie sich wie beim Testbenutzerkonto an, und erstellen Sie eine Azure AD-Testsicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="c1230-210">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="c1230-211">Melden Sie sich ab, und melden Sie sich dann mit Ihrem IT-Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="c1230-211">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="c1230-212">Konfigurieren Sie die Testsicherheitsgruppe für Self-Service-Verwaltung für das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-212">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="c1230-213">Melden Sie sich ab, und melden Sie sich dann mit Ihrem Testbenutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="c1230-213">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="c1230-214">Verwenden Sie das Azure-Portal, um Mitglieder zu der Testsicherheitsgruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1230-214">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="c1230-215">Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-215">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="c1230-216">Optional: Dynamische Gruppenmitgliedschaftseinstellungen fügen Benutzerkonten automatisch basierend auf Benutzerkontoattributen zu Gruppen hinzu</span><span class="sxs-lookup"><span data-stu-id="c1230-216">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="c1230-217">Sie haben den Satz von dynamischen Azure AD-Gruppen bestimmt und nach den Anweisungen in [Erstellen attributbasierter Regeln für dynamische Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) die Gruppen und die Regeln erstellt, die den Satz von Benutzerkontoattributen und Werten für die Gruppenmitgliedschaft bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c1230-217">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="c1230-p109">Wenn Sie diese Option überspringen, muss die Gruppenmitgliedschaft manuell vorgenommen werden, wenn neue Konten hinzugefügt oder Benutzerkontoattribute im Lauf der Zeit geändert werden. Wenn beispielsweise eine Person aus der Vertriebsabteilung in die Buchhaltung wechselt, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="c1230-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="c1230-220">Aktualisieren Sie den Wert des Attributs „Abteilung“ für dieses Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-220">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="c1230-221">Entfernen Sie es manuell aus der Gruppe „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="c1230-221">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="c1230-222">Fügen Sie es manuell der Gruppe „Buchhaltung“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="c1230-222">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="c1230-223">Wenn die Gruppen „Vertrieb“ und „Buchhaltung“ dynamisch wären, müssten Sie nur den Wert „Abteilung“ für das Benutzerkonto ändern.</span><span class="sxs-lookup"><span data-stu-id="c1230-223">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="c1230-224">Gegebenenfalls hilft Ihnen [Schritt 6](identity-self-service-group-management.md#identity-dyn-groups) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-224">If needed, [Step 6](identity-self-service-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-225">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-225">How to test</span></span>

1. <span data-ttu-id="c1230-226">Erstellen Sie eine dynamische Testgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie eine Regel für den Abteilungswert „test1“.</span><span class="sxs-lookup"><span data-stu-id="c1230-226">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="c1230-227">Erstellen Sie ein Testbenutzerkonto in Azure AD, und legen Sie die Eigenschaft „Abteilung“ auf „test1“ fest.</span><span class="sxs-lookup"><span data-stu-id="c1230-227">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="c1230-228">Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es ein Mitglied der dynamischen Testgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="c1230-228">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="c1230-229">Ändern Sie den Wert der Eigenschaft „Abteilung“ für das Testbenutzerkonto in „test2“.</span><span class="sxs-lookup"><span data-stu-id="c1230-229">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="c1230-230">Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es kein Mitglied der dynamischen Testgruppe mehr ist.</span><span class="sxs-lookup"><span data-stu-id="c1230-230">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="c1230-231">Löschen Sie die dynamische Testgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-231">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="c1230-232">Optional: Gruppenbasierte Lizenzierung für automatisches Zuweisen und Entfernen von Lizenzen zu Benutzerkonten basierend auf der Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="c1230-232">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="c1230-233">Sie haben für die entsprechenden Azure AD-Sicherheitsgruppen [gruppenbasierte Lizenzierung aktiviert](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal), damit Lizenzen für Office 365 und EMS automatisch zugewiesen oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c1230-233">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="c1230-234">Wenn Sie diese Option überspringen, müssen Sie Folgendes manuell ausführen:</span><span class="sxs-lookup"><span data-stu-id="c1230-234">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="c1230-235">Zuweisen von Lizenzen für neue Benutzer, die Zugriff auf Office 365 und EMS haben sollen.</span><span class="sxs-lookup"><span data-stu-id="c1230-235">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="c1230-236">Entfernen von Lizenzen von Benutzern, die nicht mehr in Ihrer Organisation sind oder keinen Zugriff auf Office 365 und EMS haben sollen.</span><span class="sxs-lookup"><span data-stu-id="c1230-236">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="c1230-237">Gegebenenfalls hilft Ihnen [Schritt 6](identity-self-service-group-management.md#identity-group-license) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="c1230-237">If needed, [Step 6](identity-self-service-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="c1230-238">Testen</span><span class="sxs-lookup"><span data-stu-id="c1230-238">How to test</span></span>

1. <span data-ttu-id="c1230-239">Erstellen Sie eine Testsicherheitsgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie die gruppenbasierte Lizenzierung, um Office 365- und EMS-Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c1230-239">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="c1230-240">Erstellen Sie ein Testbenutzerkonto in Azure AD, und fügen Sie es der Testsicherheitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="c1230-240">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="c1230-241">Untersuchen Sie die Eigenschaften des Benutzerkontos im Microsoft 365 Admin Center, um zu überprüfen, ob dem Konto die Office 365- und EMS-Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="c1230-241">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="c1230-242">Entfernen Sie das Testbenutzerkonto aus der Testsicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="c1230-242">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="c1230-243">Untersuchen Sie die Eigenschaften des Benutzerkontos, um zu überprüfen, ob ihm die Office 365- und EMS-Lizenzen nicht mehr zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="c1230-243">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="c1230-244">Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="c1230-244">Delete the test security group and the test user account.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="c1230-245">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c1230-245">Results and next steps</span></span>

<span data-ttu-id="c1230-246">Ihre Identitätsinfrastruktur in der Microsoft 365-Cloud verwendet starke Authentifizierung, geschützte Administratorkonten und vereinfachten Benutzerzugriff und vereinfachte Benutzerverwaltung.</span><span class="sxs-lookup"><span data-stu-id="c1230-246">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="c1230-247">Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, ist die nächste Phase [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c1230-247">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

