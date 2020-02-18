---
title: 'Phase 2: Beendigungskriterien für die Identitätsinfrastruktur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für identitätsbasierte Dienste und Infrastrukturen erfüllt.
ms.openlocfilehash: 3fd4d0a1df50d55cb7a21668b609341d0c01aa35
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067306"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="939c9-103">Phase 2: Beendigungskriterien für die Identitätsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="939c9-103">Phase 2: Identity infrastructure exit criteria</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="939c9-105">Stellen Sie sicher, dass Ihre Identitätsinfrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="939c9-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="939c9-106">Unter [Voraussetzungen](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) finden Sie weitere Empfehlungen zur Identitätsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="939c9-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="939c9-107">Erforderlich: Ihre globalen Administratorkonten sind geschützt</span><span class="sxs-lookup"><span data-stu-id="939c9-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="939c9-108">Sie haben [Ihre globalen Office 365-Administratorkonten geschützt](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts), um Versuche von Angreifern zur Kompromittierung von Anmeldeinformationen zu vereiteln, die zu Verstößen gegen Ihr Microsoft 365-Abonnement führen können.</span><span class="sxs-lookup"><span data-stu-id="939c9-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="939c9-109">Wenn Sie diese Anforderung überspringen, können Ihre globalen Administratorkonten anfällig für Angriffe und Kompromittierung sein. Dadurch kann ein Angreifer systemweiten Zugriff auf Ihre Daten erhalten, um diese zu stehlen, zu zerstören oder für Lösegeldforderungen zu missbrauchen.</span><span class="sxs-lookup"><span data-stu-id="939c9-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="939c9-110">Gegebenenfalls hilft Ihnen [Schritt 1](identity-create-protect-global-admins.md#identity-global-admin), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="939c9-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-111">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-111">How to test</span></span>

<span data-ttu-id="939c9-112">Gehen Sie folgendermaßen vor, um sicherzustellen, dass Sie Ihre globalen Administratorkonten geschützt haben:</span><span class="sxs-lookup"><span data-stu-id="939c9-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="939c9-113">Führen Sie den folgenden Azure Active Directory PowerShell für Graph-Befehl an der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="939c9-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="939c9-114">Es sollte nur die Liste der dedizierten globalen Administratorkonten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="939c9-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="939c9-115">Melden Sie sich bei Office 365 mit jedem der Konten aus Schritt 1 an.</span><span class="sxs-lookup"><span data-stu-id="939c9-115">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="939c9-116">Bei jeder Anmeldung muss die mehrstufige Authentifizierung und die stärkste Form der sekundären Authentifizierung in Ihrer Organisation verlangt werden.</span><span class="sxs-lookup"><span data-stu-id="939c9-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="939c9-117">Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden bei Office 365 finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="939c9-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="939c9-118">Optional: Sie haben Privileged Identity Management zur Unterstützung einer bedarfsgesteuerten Zuweisung der globalen Administratorrolle eingerichtet</span><span class="sxs-lookup"><span data-stu-id="939c9-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="939c9-119">Sie haben nach den Anweisungen in [Konfigurieren von Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) PIM in Ihrem Azure AD-Mandanten aktiviert und Ihre globalen Administratorkonten als berechtigte Administratoren konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="939c9-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="939c9-120">Sie haben auch die Empfehlungen in [Schützen des privilegierten Zugriffs für hybride und Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) befolgt, um eine Roadmap zu entwickeln, die den privilegierten Zugriff vor Cyberangriffen schützt.</span><span class="sxs-lookup"><span data-stu-id="939c9-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="939c9-121">Wenn Sie diese Option überspringen, sind Ihre globalen Administratorkonten ständigen Onlineangriffen ausgesetzt und können bei einer Gefährdung zulassen, dass ein Angreifer Ihre vertraulichen Informationen stiehlt, zerstört oder gegen Lösegeldforderungen sperrt.</span><span class="sxs-lookup"><span data-stu-id="939c9-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="939c9-122">Gegebenenfalls kann [Schritt 1](identity-create-protect-global-admins.md#identity-pim) bei dieser Option hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="939c9-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="939c9-123">Optional: Sie haben Privileged Access Management in Office 365 konfiguriert</span><span class="sxs-lookup"><span data-stu-id="939c9-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="939c9-124">Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="939c9-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="939c9-125">Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="939c9-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="939c9-126">Gegebenenfalls hilft Ihnen [Schritt 1](identity-create-protect-global-admins.md#identity-pam), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="939c9-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="939c9-127">Optional: Azure AD-Kennwortschutz verhindert die Verwendung von unsicheren Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="939c9-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="939c9-128">Sie haben das Sperren unsicherer Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) für global gesperrte Kennwörter und optional für benutzerdefinierte Ausdrücke aktiviert.</span><span class="sxs-lookup"><span data-stu-id="939c9-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="939c9-129">Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-password-prot) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="939c9-130">Optional: Benutzer können ihre eigenen Kennwörter zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="939c9-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="939c9-131">Sie haben [Schnelle Bereitstellung der Self-Service-Kennwortzurücksetzung in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) verwendet, um die Kennwortzurücksetzung für die Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="939c9-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="939c9-132">Wenn Sie diese Bedingung nicht erfüllen, sind Benutzer von Benutzerkontoadministratoren abhängig, um ihre Kennwörter zurückzusetzen, was zusätzlichen IT-Verwaltungsaufwand bedeutet.</span><span class="sxs-lookup"><span data-stu-id="939c9-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="939c9-133">Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-pw-reset) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="939c9-134">Optional: Benutzer können Azure AD Seamless Single Sign-on für die Anmeldung verwenden</span><span class="sxs-lookup"><span data-stu-id="939c9-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="939c9-135">Sie haben [Azure AD Connect: Nahtloses einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) für Ihre Organisation aktiviert, um die Anmeldung von Benutzern bei cloudbasierten Anwendungen, z. B. Office 365, zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="939c9-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="939c9-136">Wenn Sie diese Option überspringen, werden die Benutzer möglicherweise zur Eingabe von Anmeldeinformationen aufgefordert, wenn sie auf zusätzliche Anwendungen zugreifen, die Ihren Azure AD-Mandanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="939c9-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="939c9-137">Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-sso) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="939c9-138">Optional: Der Office 365-Anmeldebildschirm ist für Ihre Organisation personalisiert</span><span class="sxs-lookup"><span data-stu-id="939c9-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="939c9-139">Sie haben entsprechend den Anweisungen unter [Hinzufügen eines Unternehmensbrandings zu den Anmelde- und Zugriffspanelseiten](https://aka.ms/aadpaddbranding) das Branding Ihrer Organisation auf der Anmeldeseite von Office 365 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="939c9-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="939c9-140">Wenn Sie diese Option überspringen, sehen die Benutzer einen allgemeinen Office 365-Anmeldebildschirm und sind sich möglicherweise nicht sicher, dass sie sich auf der Website Ihrer Organisation anmelden.</span><span class="sxs-lookup"><span data-stu-id="939c9-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="939c9-141">Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-custom-sign-in) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="939c9-142">Optional: Die mehrstufige Azure-Authentifizierung ist für Ihre Benutzer aktiviert</span><span class="sxs-lookup"><span data-stu-id="939c9-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="939c9-143">Sie haben den [Plan für die mehrstufige Azure-Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) und [Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) verwendet, um die mehrstufige Azure-Authentifizierung (Multi-Factor Authentication, MFA) für ihre Benutzerkonten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="939c9-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="939c9-p104">Wenn Sie diese Option überspringen, sind die Benutzerkonten anfällig für eine Gefährdung der Anmeldeinformationen durch Cyberangriffe. Wenn das Kennwort eines Benutzerkontos manipuliert wurde, sind alle Ressourcen und Funktionen des Kontos, z. B. Administratorrollen, für den Angreifer verfügbar. Dadurch kann der Angreifer interne Dokumente und andere Daten kopieren, zerstören oder Lösegeld dafür verlangen.</span><span class="sxs-lookup"><span data-stu-id="939c9-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="939c9-147">Gegebenenfalls hilft Ihnen [Schritt 3](identity-secure-user-sign-ins.md#identity-mfa) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-148">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-148">How to test</span></span>

1.  <span data-ttu-id="939c9-149">Erstellen Sie ein Testbenutzerkonto, und weisen Sie ihm eine Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="939c9-149">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="939c9-150">Konfigurieren Sie die mehrstufige Azure-Authentifizierung für das Testbenutzerkonto mit der zusätzlichen Überprüfungsmethode, die Sie für tatsächliche Benutzerkonten verwenden, z. B. Senden einer SMS an Ihr Telefon.</span><span class="sxs-lookup"><span data-stu-id="939c9-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="939c9-151">Melden Sie sich mit dem Testbenutzerkonto beim Office 365-Portal an.</span><span class="sxs-lookup"><span data-stu-id="939c9-151">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="939c9-152">Vergewissern Sie sich, dass Sie von MFA zur Eingabe der zusätzlichen Überprüfungsinformationen aufgefordert werden und die Authentifizierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="939c9-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="939c9-153">Löschen Sie das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a><span data-ttu-id="939c9-154">Optional: Azure AD Identity Protection ist zum Schutz vor Gefährdung der Anmeldeinformationen aktiviert (nur Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="939c9-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="939c9-155">Sie haben Azure AD Identity Protection zu folgenden Zwecken aktiviert:</span><span class="sxs-lookup"><span data-stu-id="939c9-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="939c9-156">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="939c9-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="939c9-157">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="939c9-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="939c9-158">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="939c9-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="939c9-p105">Wenn Sie diese Option überspringen, sind Sie nicht in der Lage, Kompromittierungsversuche von Anmeldeinformationen zu erkennen oder automatisch zu verhindern bzw. identitätsbezogene Sicherheitsvorfälle zu untersuchen. Dies macht Ihr Unternehmen potenziell anfällig für eine erfolgreiche Kompromittierung von Anmeldeinformationen und die resultierende Bedrohung für vertrauliche Daten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="939c9-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="939c9-161">Gegebenenfalls hilft Ihnen [Schritt 3](identity-secure-user-sign-ins.md#identity-ident-prot) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="939c9-162">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-162">How to test</span></span>

1. <span data-ttu-id="939c9-163">Erstellen Sie ein Testbenutzerkonto mit einem anfänglichen Kennwort.</span><span class="sxs-lookup"><span data-stu-id="939c9-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="939c9-164">Führen Sie die Schritte in [Zulassen, dass Benutzer ihre eigenen Kennwörter in Office 365 zurücksetzen](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) aus, um das Kennwort für das Testbenutzerkonto zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="939c9-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="939c9-165">Melden Sie sich ab, und melden Sie sich dann mit dem zurückgesetzten Kennwort wieder am Testbenutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="939c9-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="939c9-166">Löschen Sie das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="939c9-167">Erforderlich für Hybrididentiät: Benutzer und Gruppen werden mit Azure AD synchronisiert</span><span class="sxs-lookup"><span data-stu-id="939c9-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="939c9-168">Wenn Sie über lokale Active Directory Domain Services (AD DS) verfügen, haben Sie Azure AD Connect zum Synchronisieren von Benutzerkonten und Gruppen zwischen Ihren lokalen AD DS und Ihrem Azure AD-Mandanten verwendet.</span><span class="sxs-lookup"><span data-stu-id="939c9-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="939c9-169">Dank der Verzeichnissynchronisierung können sich Ihre Benutzer bei Office 365 und anderen Microsoft Cloud Services mit denselben Anmeldeinformationen anmelden, die sie zum Anmelden an ihren Computern und zum Zugriff auf lokale Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="939c9-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="939c9-170">Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-sync), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="939c9-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="939c9-171">Wenn Sie diese Anforderung überspringen, haben Sie zwei Sätze von Benutzerkonten und Gruppen:</span><span class="sxs-lookup"><span data-stu-id="939c9-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="939c9-172">Benutzerkonten und Gruppen, die in Ihren lokalen AD DS vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="939c9-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="939c9-173">Benutzerkonten und Gruppen, die in Ihrem Azure AD-Mandanten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="939c9-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="939c9-p106">In diesem Zustand müssen die beiden Sätze von Benutzerkonten und Gruppen manuell von IT-Administratoren und Benutzern verwaltet werden. Dies führt zwangsläufig zu nicht synchronisierten Konten, deren Kennwörtern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="939c9-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-176">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-176">How to test</span></span>
<span data-ttu-id="939c9-177">Um zu überprüfen, ob die Authentifizierung mit lokalen Anmeldeinformationen funktioniert, melden Sie sich mit Ihren lokalen Anmeldeinformationen beim Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="939c9-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="939c9-178">Führen Sie folgende Schritte aus, um zu überprüfen, ob die Verzeichnissynchronisierung ordnungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="939c9-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="939c9-179">Erstellen Sie eine neue Testgruppe in AD DS.</span><span class="sxs-lookup"><span data-stu-id="939c9-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="939c9-180">Warten Sie, bis die Synchronisierungszeit abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="939c9-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="939c9-181">Überprüfen Sie Ihren Azure AD-Mandanten, um sicherzustellen, dass der Name der neuen Testgruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="939c9-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="939c9-182">Optional: Verzeichnissynchronisierung wird überwacht</span><span class="sxs-lookup"><span data-stu-id="939c9-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="939c9-183">Sie haben [Azure AD Connect Health für die Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (für die Synchronisierung von Kennwörtern) oder [Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (für Verbundauthentifizierung) verwendet und Azure AD Connect Health bereitgestellt. Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="939c9-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="939c9-184">Installieren des Azure AD Connect Health-Agents auf jedem Ihrer lokalen Identitätsserver.</span><span class="sxs-lookup"><span data-stu-id="939c9-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="939c9-185">Verwenden des Azure AD Connect Health-Portals zum Überwachen des Zustands der laufenden Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="939c9-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="939c9-186">Wenn Sie diese Option überspringen, können Sie den Zustand Ihrer cloudbasierten Identitätsinfrastruktur genauer beurteilen.</span><span class="sxs-lookup"><span data-stu-id="939c9-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="939c9-187">Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-sync-health) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-188">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-188">How to test</span></span>
<span data-ttu-id="939c9-189">Das Azure AD Connect Health-Portal zeigt den aktuellen und korrekten Zustand Ihrer lokalen Domänencontroller und der fortlaufenden Synchronisierung an.</span><span class="sxs-lookup"><span data-stu-id="939c9-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="939c9-190">Optional: Kennwortrückschreiben ist für Ihre Benutzer aktiviert</span><span class="sxs-lookup"><span data-stu-id="939c9-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="939c9-191">Sie haben die Anweisungen unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) befolgt, um das Kennwortrückschreiben für den Azure AD-Mandanten Ihres Microsoft 365 Enterprise-Abonnements zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="939c9-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="939c9-192">Wenn Sie diese Option überspringen, müssen Benutzer, die nicht mit Ihrem lokalen Netzwerk verbunden sind, ihre AD DS-Kennwörter über einen IT-Administrator zurücksetzen oder entsperren.</span><span class="sxs-lookup"><span data-stu-id="939c9-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="939c9-193">Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-pw-writeback) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="939c9-194">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn Azure AD ein hohes Risiko einer Kontogefährdung erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="939c9-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="939c9-195">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-195">How to test</span></span>

<span data-ttu-id="939c9-196">Sie testen das Kennwortrückschreiben durch Ändern Ihres Kennworts in Office 365.</span><span class="sxs-lookup"><span data-stu-id="939c9-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="939c9-197">Sie sollten Ihr Konto und das neue Kennwort für den Zugriff auf lokale AD DS-Ressourcen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="939c9-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="939c9-198">Erstellen Sie in Ihrem lokalen AD DS ein Testbenutzerkonto, lassen Sie Verzeichnissynchronisierung zu, und erteilen Sie dem Konto im Microsoft 365 Admin Center eine Microsoft 365 Enterprise-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="939c9-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="939c9-199">Melden Sie sich von einem Remotecomputer, der Ihrer lokalen AD DS-Domäne angehört, mit den Anmeldeinformationen des Testbenutzerkontos beim Computer und beim Office-Portal an.</span><span class="sxs-lookup"><span data-stu-id="939c9-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="939c9-200">Wählen Sie **Einstellungen > Office 365-Einstellungen > Kennwort > Kennwort ändern**.</span><span class="sxs-lookup"><span data-stu-id="939c9-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="939c9-201">Geben Sie das aktuelle Kennwort ein, geben Sie ein neues Kennwort ein, und bestätigen Sie es dann.</span><span class="sxs-lookup"><span data-stu-id="939c9-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="939c9-202">Melden Sie sich beim Office-Portal und Remotecomputer ab, und melden Sie sich dann beim Computer mit dem Testbenutzerkonto und dem neuen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="939c9-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="939c9-203">Dies beweist, dass Sie das Kennwort eines lokalen AD DS-Benutzerkontos unter Verwendung des Azure AD-Mandanten ändern konnten.</span><span class="sxs-lookup"><span data-stu-id="939c9-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-204">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-204">How to test</span></span>

<span data-ttu-id="939c9-205">Melden Sie sich mit Ihrem Benutzerkontonamen und mittels mehrstufiger Azure-Authentifizierung beim Office 365-Portal an.</span><span class="sxs-lookup"><span data-stu-id="939c9-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="939c9-206">Auf der Anmeldeseite sollten Ihre benutzerdefinierten Branding-Elemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="939c9-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="939c9-207">Optional: Self-Service-Gruppenverwaltung ist für bestimmte Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert</span><span class="sxs-lookup"><span data-stu-id="939c9-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="939c9-208">Sie haben bestimmt, welche Gruppen für Self-Service-Verwaltung geeignet sind, deren Besitzer bezüglich des Workflows und der Verantwortlichkeiten der Gruppenverwaltung instruiert und für diese Gruppen [die Self-Service-Verwaltung in Azure AD eingerichtet](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="939c9-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="939c9-209">Wenn Sie diese Option überspringen, müssen alle Verwaltungsaufgaben für Azure AD-Gruppen von IT-Administratoren erledigt werden.</span><span class="sxs-lookup"><span data-stu-id="939c9-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="939c9-210">Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-self-service-groups) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-211">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-211">How to test</span></span>
1.  <span data-ttu-id="939c9-212">Erstellen Sie ein Testbenutzerkonto in Azure AD mit dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="939c9-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="939c9-213">Melden Sie sich wie beim Testbenutzerkonto an, und erstellen Sie eine Azure AD-Testsicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="939c9-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="939c9-214">Melden Sie sich ab, und melden Sie sich dann mit Ihrem IT-Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="939c9-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="939c9-215">Konfigurieren Sie die Testsicherheitsgruppe für Self-Service-Verwaltung für das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="939c9-216">Melden Sie sich ab, und melden Sie sich dann mit Ihrem Testbenutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="939c9-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="939c9-217">Verwenden Sie das Azure-Portal, um Mitglieder zu der Testsicherheitsgruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="939c9-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="939c9-218">Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="939c9-219">Optional: Dynamische Gruppenmitgliedschaftseinstellungen fügen Benutzerkonten automatisch basierend auf Benutzerkontoattributen zu Gruppen hinzu</span><span class="sxs-lookup"><span data-stu-id="939c9-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="939c9-220">Sie haben den Satz von dynamischen Azure AD-Gruppen bestimmt und nach den Anweisungen in [Erstellen attributbasierter Regeln für dynamische Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) die Gruppen und die Regeln erstellt, die den Satz von Benutzerkontoattributen und Werten für die Gruppenmitgliedschaft bestimmen.</span><span class="sxs-lookup"><span data-stu-id="939c9-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="939c9-p110">Wenn Sie diese Option überspringen, muss die Gruppenmitgliedschaft manuell vorgenommen werden, wenn neue Konten hinzugefügt oder Benutzerkontoattribute im Lauf der Zeit geändert werden. Wenn beispielsweise eine Person aus der Vertriebsabteilung in die Buchhaltung wechselt, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="939c9-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="939c9-223">Aktualisieren Sie den Wert des Attributs „Abteilung“ für dieses Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="939c9-224">Entfernen Sie es manuell aus der Gruppe „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="939c9-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="939c9-225">Fügen Sie es manuell der Gruppe „Buchhaltung“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="939c9-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="939c9-226">Wenn die Gruppen „Vertrieb“ und „Buchhaltung“ dynamisch wären, müssten Sie nur den Wert „Abteilung“ für das Benutzerkonto ändern.</span><span class="sxs-lookup"><span data-stu-id="939c9-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="939c9-227">Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-dyn-groups) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-228">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-228">How to test</span></span>

1. <span data-ttu-id="939c9-229">Erstellen Sie eine dynamische Testgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie eine Regel für den Abteilungswert „test1“.</span><span class="sxs-lookup"><span data-stu-id="939c9-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="939c9-230">Erstellen Sie ein Testbenutzerkonto in Azure AD, und legen Sie die Eigenschaft „Abteilung“ auf „test1“ fest.</span><span class="sxs-lookup"><span data-stu-id="939c9-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="939c9-231">Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es ein Mitglied der dynamischen Testgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="939c9-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="939c9-232">Ändern Sie den Wert der Eigenschaft „Abteilung“ für das Testbenutzerkonto in „test2“.</span><span class="sxs-lookup"><span data-stu-id="939c9-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="939c9-233">Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es kein Mitglied der dynamischen Testgruppe mehr ist.</span><span class="sxs-lookup"><span data-stu-id="939c9-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="939c9-234">Löschen Sie die dynamische Testgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="939c9-235">Optional: Gruppenbasierte Lizenzierung für automatisches Zuweisen und Entfernen von Lizenzen zu Benutzerkonten basierend auf der Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="939c9-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="939c9-236">Sie haben für die entsprechenden Azure AD-Sicherheitsgruppen [gruppenbasierte Lizenzierung aktiviert](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal), damit Ihre Microsoft 365 Enterprise-Lizenzen automatisch zugewiesen oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="939c9-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="939c9-237">Wenn Sie diese Option überspringen, müssen Sie Folgendes manuell ausführen:</span><span class="sxs-lookup"><span data-stu-id="939c9-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="939c9-238">Zuweisen von Lizenzen für neue Benutzer, die Zugriff haben sollen.</span><span class="sxs-lookup"><span data-stu-id="939c9-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="939c9-239">Entfernen von Lizenzen von Benutzern, die nicht mehr in Ihrer Organisation sind oder keinen Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="939c9-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="939c9-240">Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-group-license) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="939c9-241">Testen</span><span class="sxs-lookup"><span data-stu-id="939c9-241">How to test</span></span>

1. <span data-ttu-id="939c9-242">Erstellen Sie eine Testsicherheitsgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie die gruppenbasierte Lizenzierung, um Microsoft 365 Enterprise-Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="939c9-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="939c9-243">Erstellen Sie ein Testbenutzerkonto in Azure AD, und fügen Sie es der Testsicherheitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="939c9-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="939c9-244">Untersuchen Sie die Eigenschaften des Benutzerkontos im Microsoft 365 Admin Center, um zu überprüfen, ob dem Konto die Microsoft 365 Enterprise-Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="939c9-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="939c9-245">Entfernen Sie das Testbenutzerkonto aus der Testsicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="939c9-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="939c9-246">Untersuchen Sie die Eigenschaften des Benutzerkontos, um zu überprüfen, ob ihm die Microsoft 365 Enterprise-Lizenzen nicht mehr zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="939c9-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="939c9-247">Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="939c9-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="939c9-248">Optional: Zugriffsüberprüfungen, die für die Überwachung des Zugriffs konfiguriert und verwendet werden</span><span class="sxs-lookup"><span data-stu-id="939c9-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="939c9-249">Sie haben diese Artikel zum Konfigurieren verschiedener Typen von Zugriffsüberprüfungen zum Überwachen der Gruppenmitgliedschaften, des Zugriffs auf Unternehmensanwendungen und der Rollenzuweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="939c9-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="939c9-250">Gruppen und Apps</span><span class="sxs-lookup"><span data-stu-id="939c9-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="939c9-251">Azure AD-Rollen</span><span class="sxs-lookup"><span data-stu-id="939c9-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="939c9-252">Azure-Ressourcenrollen</span><span class="sxs-lookup"><span data-stu-id="939c9-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="939c9-253">Gegebenenfalls hilft Ihnen [Schritt 6](identity-configure-identity-governance.md#identity-access-reviews) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="939c9-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="939c9-254">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="939c9-254">Results and next steps</span></span>

<span data-ttu-id="939c9-255">Ihre Identitätsinfrastruktur in der Microsoft 365-Cloud verwendet starke Authentifizierung, geschützte Administratorkonten und vereinfachten Benutzerzugriff und vereinfachte Benutzerverwaltung.</span><span class="sxs-lookup"><span data-stu-id="939c9-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![Phase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="939c9-257">Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, ist die nächste Phase [Windows 10 Enterprise](windows10-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="939c9-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

