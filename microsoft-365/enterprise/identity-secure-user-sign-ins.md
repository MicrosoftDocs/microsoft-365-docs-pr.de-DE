---
title: 'Schritt 3: Absichern und Verwalten von Benutzeranmeldungen'
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
description: Sie können die Benutzeranmeldungen auf Windows-Geräten und auf Microsoft 365 sicherer machen.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067292"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="9d9e3-103">Schritt 3: Absichern und Verwalten von Benutzeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="9d9e3-103">Step 3: Secure and manage your user sign-ins</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="9d9e3-105">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="9d9e3-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="9d9e3-106">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9d9e3-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9d9e3-107">Windows Hello for Business in Windows 10 Enterprise ersetzt Kennwörter durch eine starke zweistufige Authentifizierung, wenn sich jemand auf einem Windows-Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="9d9e3-108">Beide Faktoren zählen zu neuen Arten von Benutzeranmeldeinformationen, die mit einem Gerät verknüpft sind und biometrische Daten oder eine PIN erfordern.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="9d9e3-109">Weitere Informationen finden Sie unter [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="9d9e3-110">Einrichten der mehrstufigen Azure-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9d9e3-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="9d9e3-111">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9d9e3-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9d9e3-112">Im Rahmen dieses Schritts richten Sie die mehrstufige Azure-Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene zu Benutzeranmeldungen und -transaktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="9d9e3-113">Die mehrstufige Authentifizierung erfordert eine zusätzliche Überprüfungsmethode, nachdem die Benutzer ihr Kennwort korrekt eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="9d9e3-114">Ohne MFA ist das Kennwort die einzige Überprüfungsmethode.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="9d9e3-115">Das Problem bei Kennwörtern ist, dass viele von ihnen durch einen Angreifer leicht erraten oder unwissentlich mit nicht vertrauenswürdigen Parteien geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="9d9e3-116">Die zweite Sicherheitsebene bei MFA kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="9d9e3-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="9d9e3-117">Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="9d9e3-118">Ein biometrisches Attribut, z. B. ein Fingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="9d9e3-119">Sie aktivieren die mehrstufige Authentifizierung und konfigurieren die zweite Authentifizierungsmethode mithilfe von [Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), die es Ihnen ermöglichen, Azure Active Directory-Gruppen (Azure AD) zum Rollout von MFA für bestimmte Gruppen von Benutzern, z. B. Pilotbenutzer, geografische Regionen oder Abteilungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="9d9e3-120">Teilen Sie Ihren Benutzern unbedingt mit, dass die mehrstufige Authentifizierung aktiviert wird, damit sie die Anforderungen, z. B. die obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="9d9e3-121">Weitere Informationen finden Sie unter [Planen einer cloudbasierten Bereitstellung der mehrstufigen Azure-Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9d9e3-123">Testumgebungsanleitung: Mehrstufige Azure-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9d9e3-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="9d9e3-124">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="9d9e3-125">Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9d9e3-125">Protect against credential compromise</span></span>

<span data-ttu-id="9d9e3-126">*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9d9e3-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9d9e3-127">In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="9d9e3-128">Azure AD Identity Protection bietet verschiedene Möglichkeiten um zu verhindern, dass ein Angreifer die Anmeldeinformationen eines Benutzerkontos kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="9d9e3-129">Mit Azure AD Identity Protection können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9d9e3-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="9d9e3-130">Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="9d9e3-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="9d9e3-131">Azure AD verwendet das maschinelle Lernen, um Anomalien und verdächtige Aktivitäten wie Anmeldeaktivitäten und Aktivitäten nachdem Anmelden zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="9d9e3-132">Anhand dieser Daten generiert Azure AD Identity Protection Berichte und Warnungen, mit denen Sie die Probleme bewerten und entsprechende Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="9d9e3-133">Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="9d9e3-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="9d9e3-134">Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="9d9e3-135">Zusätzlich zu anderen Kontrollelementen für den bedingten Zugriff von Azure AD und Microsoft Intune können mithilfe dieser Richtlinien entweder Zugriffsversuche automatisch blockiert oder Korrekturmaßnahmen ergriffen werden. Hierzu gehören Kennwortzurücksetzungen und die Anforderung der mehrstufigen Azure-Authentifizierung für nachfolgende Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="9d9e3-136">Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="9d9e3-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="9d9e3-p107">Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="9d9e3-139">Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="9d9e3-140">Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="9d9e3-141">In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9d9e3-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="9d9e3-142">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="9d9e3-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="9d9e3-143">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9d9e3-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="9d9e3-144">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="9d9e3-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9d9e3-146">Testumgebungsanleitung: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9d9e3-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="9d9e3-147">Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![Schritt 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="9d9e3-149">Hinzufügen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="9d9e3-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
