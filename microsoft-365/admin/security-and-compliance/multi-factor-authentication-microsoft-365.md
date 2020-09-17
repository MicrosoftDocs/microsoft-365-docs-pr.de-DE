---
title: Mehrstufige Authentifizierung für Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über die mehrstufige Authentifizierung in Microsoft 365.
ms.openlocfilehash: bca84e949e696b483b567bf5f72233840023abca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948712"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="3f8ba-103">Mehrstufige Authentifizierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f8ba-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="3f8ba-104">Kennwörter stellen die gängigste Methode zum Authentifizieren einer Anmeldung bei einem Computer oder Onlinedienst dar, sind aber auch am stärksten gefährdet.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="3f8ba-105">Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen für verschiedene Computer und Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="3f8ba-106">Um eine zusätzliche Sicherheitsstufe für Anmeldungen bereitzustellen, müssen Sie die mehrstufige Authentifizierung (MFA) verwenden, die ein starkes Kennwort verwendet, und eine zusätzliche Überprüfungsmethode basierend auf folgenden Faktoren:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="3f8ba-107">Etwas, das Sie mit sich haben, das nicht einfach dupliziert werden kann, beispielsweise ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="3f8ba-108">Etwas, das Sie eindeutig und biologisch haben, beispielsweise Fingerabdrücke, Gesicht oder andere biometrische Attribute.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="3f8ba-109">Die zusätzliche Überprüfungsmethode wird erst verwendet, nachdem das Kennwort des Benutzers überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="3f8ba-110">Bei MFA, auch wenn ein sicheres Benutzerkennwort kompromittiert wird, verfügt der Angreifer nicht über Ihr Smartphone oder Ihren Fingerabdruck, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="3f8ba-111">MFA-Unterstützung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f8ba-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="3f8ba-112">Standardmäßig unterstützen sowohl Microsoft 365 als auch Office 365 MFA für Benutzerkonten mit folgendem:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="3f8ba-113">Eine an ein Telefon gesendete Textnachricht, die den Benutzer zum Eingeben eines Überprüfungscodes benötigt.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="3f8ba-114">Ein Telefonanruf.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-114">A phone call.</span></span>
- <span data-ttu-id="3f8ba-115">Die Smart Phone-App für Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="3f8ba-116">In beiden Fällen verwendet die MFA-Anmeldung die Methode "etwas, das Sie mit sich haben, das nicht leicht dupliziert werden kann" für die zusätzliche Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="3f8ba-117">Es gibt mehrere Möglichkeiten, wie Sie MFA für Microsoft 365 und Office 365 aktivieren können:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="3f8ba-118">Mit Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="3f8ba-118">With security defaults</span></span>
- <span data-ttu-id="3f8ba-119">Mit bedingten Zugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3f8ba-119">With Conditional Access policies</span></span>
- <span data-ttu-id="3f8ba-120">Für jedes einzelne Benutzerkonto (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="3f8ba-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="3f8ba-121">Diese Methoden basieren auf Ihrem Microsoft 365-Plan.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="3f8ba-122">Plan</span><span class="sxs-lookup"><span data-stu-id="3f8ba-122">Plan</span></span>  |<span data-ttu-id="3f8ba-123">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="3f8ba-123">Recommendation</span></span>  | <span data-ttu-id="3f8ba-124">Typ des Kunden</span><span class="sxs-lookup"><span data-stu-id="3f8ba-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="3f8ba-125">Alle Microsoft 365-Pläne</span><span class="sxs-lookup"><span data-stu-id="3f8ba-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="3f8ba-126">Verwenden Sie Sicherheitsstandards, die MFA für alle Benutzerkonten erfordern.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="3f8ba-127">Sie können auch MFA auf Benutzerkonten Basis benötigen, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="3f8ba-128">Kleinunternehmen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-128">Small business</span></span> |
| <span data-ttu-id="3f8ba-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3f8ba-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="3f8ba-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="3f8ba-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="3f8ba-131">Azure Active Directory (Azure AD) Premium P1-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="3f8ba-132">Verwenden Sie Richtlinien für bedingten Zugriff, um MFA für Benutzerkonten zu erfordern, die auf Gruppenmitgliedschaften, Apps oder anderen Kriterien basieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="3f8ba-133">Small Business to Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f8ba-133">Small business to enterprise</span></span> |
| <span data-ttu-id="3f8ba-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3f8ba-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="3f8ba-135">Azure AD Premium P2-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="3f8ba-136">Verwenden Sie Azure AD Identitätsschutz, um MFA basierend auf Anmelde Risikokriterien zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="3f8ba-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f8ba-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="3f8ba-138">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="3f8ba-138">Security defaults</span></span>

<span data-ttu-id="3f8ba-139">Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="3f8ba-140">Bei diesen Abonnements sind Sicherheitsstandards aktiviert, was:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="3f8ba-141">Erfordert, dass alle Benutzer MFA mit der Microsoft Authenticator-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="3f8ba-142">Blockiert die Legacy Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="3f8ba-143">Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="3f8ba-144">Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="3f8ba-145">Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="3f8ba-146">Sie können Sicherheitsstandards zu Gunsten von MFA mit bedingten Zugriffsrichtlinien deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="3f8ba-147">Sie können Sicherheitsstandards im Bereich **Eigenschaften** für Azure AD im Azure-Portal aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Die Seite Verzeichniseigenschaften.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="3f8ba-149">Sie können Sicherheitsstandards mit einem beliebigen Microsoft 365-Plan verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="3f8ba-150">Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="3f8ba-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="3f8ba-151">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="3f8ba-151">Conditional Access policies</span></span>

<span data-ttu-id="3f8ba-152">Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="3f8ba-153">Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="3f8ba-154">Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="3f8ba-155">Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="3f8ba-156">Sie können auch Richtlinien für bedingten Zugriff für erweiterte Funktionen verwenden, beispielsweise für die Anforderung eines MFA für bestimmte Apps oder für die Ausführung der Anmeldung von einem kompatiblen Gerät aus, beispielsweise auf Ihrem Laptop mit Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="3f8ba-157">Sie konfigurieren Richtlinien für bedingten Zugriff aus dem **Sicherheits** Bereich für Azure AD im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Bilder der Menüoption für bedingten Zugriff](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="3f8ba-159">Sie können Richtlinien für bedingten Zugriff mit folgenden Bedingungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="3f8ba-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3f8ba-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="3f8ba-161">Microsoft 365 E3 und E5</span><span class="sxs-lookup"><span data-stu-id="3f8ba-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="3f8ba-162">Azure AD Premium P1-und Azure AD Premium-P2-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="3f8ba-163">Für kleine Unternehmen mit Microsoft 365 Business Premium können Sie mit den folgenden Schritten einfache Richtlinien für bedingten Zugriff verwenden:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="3f8ba-164">Erstellen Sie eine Gruppe, die die Benutzerkonten enthält, die MFA erfordern.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="3f8ba-165">Aktivieren Sie die Richtlinie **"MFA für globale Administratoren erfordern"** .</span><span class="sxs-lookup"><span data-stu-id="3f8ba-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="3f8ba-166">Erstellen Sie eine Gruppenbasierte Richtlinie für den bedingten Zugriff mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="3f8ba-167">Zuordnungen > Benutzer und Gruppen: der Name Ihrer Gruppe aus Schritt 1 oben.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="3f8ba-168">Zuordnungen > Cloud-Apps oder-Aktionen: alle Cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="3f8ba-169">Zugriffssteuerungen > gewähren > gewähren von Zugriff > erfordern mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="3f8ba-170">Aktivieren Sie die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-170">Enable the policy.</span></span>
5. <span data-ttu-id="3f8ba-171">Fügen Sie der in Schritt 1 oben erstellten Gruppe ein Benutzerkonto hinzu, und testen Sie.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="3f8ba-172">Wenn Sie MFA für zusätzliche Benutzerkonten benötigen, fügen Sie diese der in Schritt 1 erstellten Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="3f8ba-173">Mit dieser Richtlinie für bedingten Zugriff können Sie die MFA-Anforderung für Ihre Benutzer in Ihrem eigenen Tempo bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="3f8ba-174">Unternehmen sollten [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) verwenden, um die folgenden Richtlinien zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="3f8ba-175">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="3f8ba-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="3f8ba-176">MFA für alle Nutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="3f8ba-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="3f8ba-177">Legacy Authentifizierung blockieren</span><span class="sxs-lookup"><span data-stu-id="3f8ba-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="3f8ba-178">Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="3f8ba-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="3f8ba-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3f8ba-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="3f8ba-180">Mit Azure AD Identitätsschutz können Sie eine zusätzliche Richtlinie für den bedingten Zugriff erstellen, die [MFA erfordert, wenn das Anmelde Risiko Mittel oder hoch ist](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="3f8ba-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="3f8ba-181">Sie können Azure AD Identitätsschutz und risikobasierte Richtlinien für bedingten Zugriff verwenden:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="3f8ba-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3f8ba-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="3f8ba-183">Azure AD Premium P2-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="3f8ba-184">Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="3f8ba-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-person-mfa-not-recommended"></a><span data-ttu-id="3f8ba-185">Vermächtnis pro Person MFA (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="3f8ba-185">Legacy per person MFA (not recommended)</span></span>

<span data-ttu-id="3f8ba-186">Sie sollten entweder Sicherheitsstandards oder Richtlinien für bedingten Zugriff verwenden, um MFA für Ihre Benutzerkonto-Anmeldungen zu benötigen. Wenn eine dieser Funktionen jedoch nicht verwendet werden kann, empfiehlt Microsoft für alle Größen Abonnements dringend die Verwendung von MFA für Benutzerkonten mit Administratorrollen, vor allem mit der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="3f8ba-187">Sie aktivieren MFA für einzelne Benutzerkonten im Bereich **aktive Benutzer** des Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Option "Abbildung der mehrstufigen Authentifizierung" auf der Seite "aktive Benutzer"](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="3f8ba-189">Wenn sich der Benutzer das nächste Mal anmeldet, wird er aufgefordert, sich für MFA zu registrieren und die zusätzliche Überprüfungsmethode auszuwählen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="3f8ba-190">Diese Methoden zusammen verwenden</span><span class="sxs-lookup"><span data-stu-id="3f8ba-190">Using these methods together</span></span>

<span data-ttu-id="3f8ba-191">Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards, Richtlinien für bedingten Zugriff und Nutzerkonteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="3f8ba-192">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="3f8ba-192">Enabled</span></span> | <span data-ttu-id="3f8ba-193">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="3f8ba-193">Disabled</span></span> | <span data-ttu-id="3f8ba-194">Sekundäre Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="3f8ba-194">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="3f8ba-195">**Sicherheitsstandards**</span><span class="sxs-lookup"><span data-stu-id="3f8ba-195">**Security defaults**</span></span> | <span data-ttu-id="3f8ba-196">Richtlinien für bedingten Zugriff können nicht verwendet werden</span><span class="sxs-lookup"><span data-stu-id="3f8ba-196">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="3f8ba-197">Richtlinien für den bedingten Zugriff können verwendet werden</span><span class="sxs-lookup"><span data-stu-id="3f8ba-197">Can use Conditional Access policies</span></span> | <span data-ttu-id="3f8ba-198">Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="3f8ba-198">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="3f8ba-199">**Richtlinien für bedingten Zugriff**</span><span class="sxs-lookup"><span data-stu-id="3f8ba-199">**Conditional Access policies**</span></span> |<span data-ttu-id="3f8ba-200">Wenn welche aktiviert sind, können Sie die Sicherheitsstandards nicht aktivieren</span><span class="sxs-lookup"><span data-stu-id="3f8ba-200">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="3f8ba-201">Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren</span><span class="sxs-lookup"><span data-stu-id="3f8ba-201">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="3f8ba-202">Nutzerdefiniert bei der MFA-Registrierung</span><span class="sxs-lookup"><span data-stu-id="3f8ba-202">User-specified during MFA registration</span></span> |
| <span data-ttu-id="3f8ba-203">**Vermächtnis pro Person MFA (nicht empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="3f8ba-203">**Legacy Per Person MFA (not recommended)**</span></span> | <span data-ttu-id="3f8ba-204">Überschreibt Sicherheitsstandards und Richtlinien für bedingten Zugriff, für die die MFA bei jedem anmelden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="3f8ba-205">Durch Sicherheitsstandards und Richtlinien für bedingten Zugriff außer Kraft gesetzt</span><span class="sxs-lookup"><span data-stu-id="3f8ba-205">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="3f8ba-206">Nutzerdefiniert bei der MFA-Registrierung</span><span class="sxs-lookup"><span data-stu-id="3f8ba-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="3f8ba-207">Wenn Sicherheitsstandards aktiviert sind, werden alle neuen Benutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App bei der nächsten Anmeldung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="3f8ba-208">Möglichkeiten zum Verwalten von MFA-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="3f8ba-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="3f8ba-209">Es gibt zwei Möglichkeiten zum Verwalten von MFA-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="3f8ba-210">Im Azure-Portal haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="3f8ba-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="3f8ba-211">Aktivieren und Deaktivieren von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="3f8ba-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="3f8ba-212">Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="3f8ba-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="3f8ba-213">Im Microsoft 365 Admin Center können Sie die MFA-Einstellungen für einzelne Benutzer und Dienste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3f8ba-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="3f8ba-214">Der nächste Schritt</span><span class="sxs-lookup"><span data-stu-id="3f8ba-214">Your next step</span></span>

[<span data-ttu-id="3f8ba-215">Einrichten von MFA für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f8ba-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
