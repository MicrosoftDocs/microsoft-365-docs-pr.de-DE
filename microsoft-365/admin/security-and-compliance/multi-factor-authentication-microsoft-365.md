---
title: Mehrstufige Authentifizierung für Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) verwendet sowohl ein Kennwort, das stark sein sollte, als auch eine zusätzliche Überprüfungsmethode.
ms.openlocfilehash: 9b3347f1a8e7b1f62c9bbfe77a7f14c221ef28b5
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393643"
---
# <a name="multifactor-authentication-for-microsoft-365"></a><span data-ttu-id="4d943-103">Mehrstufige Authentifizierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d943-103">Multifactor authentication for Microsoft 365</span></span>

<span data-ttu-id="4d943-104">Kennwörter sind die am häufigsten verwendete Methode zum Authentifizieren einer Anmeldung bei einem Computer oder Onlinedienst, sind aber auch am anfälligsten.</span><span class="sxs-lookup"><span data-stu-id="4d943-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="4d943-105">Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen bei verschiedenen Computern und Diensten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d943-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="4d943-106">Um eine zusätzliche Sicherheitsstufe für Anmeldungen bereitzustellen, müssen Sie die mehrstufige Authentifizierung (MFA) verwenden, die sowohl ein Kennwort verwendet, das stark sein sollte, als auch eine zusätzliche Überprüfungsmethode basierend auf:</span><span class="sxs-lookup"><span data-stu-id="4d943-106">To provide an additional level of security for sign-ins, you must use multifactor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="4d943-107">Etwas, das Sie haben, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="4d943-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="4d943-108">Etwas, das Sie eindeutig und in besonderer Weise besitzen, z. B. Ihre Fingerabdrücke, Ihr Gesicht oder ein anderes biometrisches Attribut.</span><span class="sxs-lookup"><span data-stu-id="4d943-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="4d943-109">Die zusätzliche Überprüfungsmethode wird erst verwendet, nachdem das Kennwort des Benutzers überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="4d943-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="4d943-110">Bei der MFA verfügt der Angreifer selbst dann nicht über Ihr Smartphone oder Ihren Fingerabdruck, wenn ein sicheres Benutzerkennwort kompromittiert wurde, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4d943-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="4d943-111">MFA-Unterstützung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d943-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="4d943-112">Standardmäßig unterstützen sowohl Microsoft 365 als auch Office 365 MFA für Benutzerkonten mithilfe von:</span><span class="sxs-lookup"><span data-stu-id="4d943-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="4d943-113">Eine an ein Telefon gesendete Textnachricht, die erfordert, dass der Benutzer einen Überprüfungscode eingibt.</span><span class="sxs-lookup"><span data-stu-id="4d943-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="4d943-114">Ein Telefonanruf.</span><span class="sxs-lookup"><span data-stu-id="4d943-114">A phone call.</span></span>
- <span data-ttu-id="4d943-115">Die Microsoft Authenticator Smartphone-App.</span><span class="sxs-lookup"><span data-stu-id="4d943-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="4d943-116">In beiden Fällen verwendet die MFA-Anmeldung die Methode "Etwas, das Sie bei Ihnen haben, das nicht einfach dupliziert werden kann" für die zusätzliche Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="4d943-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="4d943-117">Es gibt mehrere Möglichkeiten, MFA für Microsoft 365 und Office 365 zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4d943-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="4d943-118">Mit Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="4d943-118">With security defaults</span></span>
- <span data-ttu-id="4d943-119">Mit Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4d943-119">With Conditional Access policies</span></span>
- <span data-ttu-id="4d943-120">Für jedes einzelne Benutzerkonto (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="4d943-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="4d943-121">Diese Methoden basieren auf Ihrem Microsoft 365 Plan.</span><span class="sxs-lookup"><span data-stu-id="4d943-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="4d943-122">Plan</span><span class="sxs-lookup"><span data-stu-id="4d943-122">Plan</span></span>|<span data-ttu-id="4d943-123">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="4d943-123">Recommendation</span></span>|<span data-ttu-id="4d943-124">Typ des Kunden</span><span class="sxs-lookup"><span data-stu-id="4d943-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="4d943-125">Alle pläne Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d943-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="4d943-126">Verwenden Sie Sicherheitsstandards, die MFA für alle Benutzerkonten erfordern.</span><span class="sxs-lookup"><span data-stu-id="4d943-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="4d943-127">Sie können auch MFA pro Benutzer für einzelne Benutzerkonten konfigurieren, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4d943-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="4d943-128">Kleinunternehmen</span><span class="sxs-lookup"><span data-stu-id="4d943-128">Small business</span></span>|
|<span data-ttu-id="4d943-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4d943-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="4d943-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4d943-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="4d943-131">Azure Active Directory (Azure AD) Premium P1-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="4d943-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="4d943-132">Verwenden Sie Richtlinien für bedingten Zugriff, um MFA für Benutzerkonten basierend auf der Gruppenmitgliedschaft, Apps oder anderen Kriterien anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4d943-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="4d943-133">Kleinunternehmen zu Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4d943-133">Small business to enterprise</span></span>|
|<span data-ttu-id="4d943-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4d943-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="4d943-135">Azure AD Premium P2 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="4d943-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="4d943-136">Verwenden Sie Azure AD Identity Protection, um MFA basierend auf Anmelderisikokriterien anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4d943-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="4d943-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="4d943-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="4d943-138">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="4d943-138">Security defaults</span></span>

<span data-ttu-id="4d943-139">Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4d943-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="4d943-140">Für diese Abonnements sind die Sicherheitsstandards aktiviert, die:</span><span class="sxs-lookup"><span data-stu-id="4d943-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="4d943-141">Erfordert, dass alle Ihre Benutzer MFA mit der Microsoft Authenticator-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d943-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="4d943-142">Blockiert die Legacyauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4d943-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="4d943-143">Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="4d943-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="4d943-144">Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.</span><span class="sxs-lookup"><span data-stu-id="4d943-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="4d943-145">Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4d943-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="4d943-146">Sie können Sicherheitsstandards für MFA mit Richtlinien für bedingten Zugriff deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d943-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="4d943-147">Sie aktivieren oder deaktivieren Die Sicherheitsstandards im **Eigenschaftenbereich** für Azure AD im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="4d943-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Abbildung der Seite "Verzeichniseigenschaften".](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="4d943-149">Sie können Sicherheitsstandards mit jedem Microsoft 365 Plan verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d943-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="4d943-150">Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="4d943-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="4d943-151">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4d943-151">Conditional Access policies</span></span>

<span data-ttu-id="4d943-152">Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="4d943-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="4d943-153">Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="4d943-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="4d943-154">Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d943-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="4d943-155">Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.</span><span class="sxs-lookup"><span data-stu-id="4d943-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="4d943-156">Sie können richtlinien für bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. das Anfordern von MFA für bestimmte Apps oder das Anmelden über ein kompatibles Gerät, z. B. ihren Laptop, auf dem Windows 10 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d943-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="4d943-157">Sie konfigurieren Richtlinien für bedingten Zugriff im **Sicherheitsbereich** für Azure AD im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="4d943-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Bild der Menüoption für bedingten Zugriff](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="4d943-159">Sie können Richtlinien für bedingten Zugriff mit folgenden Aktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="4d943-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="4d943-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4d943-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="4d943-161">Microsoft 365 E3 und E5</span><span class="sxs-lookup"><span data-stu-id="4d943-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="4d943-162">lizenzen für Azure AD Premium P1 und Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="4d943-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="4d943-163">Für kleine Unternehmen mit Microsoft 365 Business Premium können Sie richtlinien für bedingten Zugriff ganz einfach mit den folgenden Schritten verwenden:</span><span class="sxs-lookup"><span data-stu-id="4d943-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="4d943-164">Erstellen Sie eine Gruppe, die die Benutzerkonten enthält, die MFA erfordern.</span><span class="sxs-lookup"><span data-stu-id="4d943-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="4d943-165">Aktivieren Sie die Richtlinie **"MFA für globale Administratoren anfordern".**</span><span class="sxs-lookup"><span data-stu-id="4d943-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="4d943-166">Erstellen Sie eine gruppenbasierte Richtlinie für bedingten Zugriff mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="4d943-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="4d943-167">Aufgaben > Benutzer und Gruppen: Der Name Ihrer Gruppe aus Schritt 1 oben.</span><span class="sxs-lookup"><span data-stu-id="4d943-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="4d943-168">Aufgaben > Cloud-Apps oder -Aktionen: alle Cloud-Apps.</span><span class="sxs-lookup"><span data-stu-id="4d943-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="4d943-169">Zugriffssteuerungen > gewähren > Zugriff gewähren > mehrstufige Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d943-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="4d943-170">Aktivieren Sie die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4d943-170">Enable the policy.</span></span>
5. <span data-ttu-id="4d943-171">Fügen Sie der in Schritt 1 oben erstellten Gruppe ein Benutzerkonto hinzu, und testen Sie.</span><span class="sxs-lookup"><span data-stu-id="4d943-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="4d943-172">Um MFA für zusätzliche Benutzerkonten zu benötigen, fügen Sie sie der in Schritt 1 erstellten Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d943-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="4d943-173">Mit dieser Richtlinie für bedingten Zugriff können Sie die MFA-Anforderung für Ihre Benutzer in Ihrem eigenen Tempo bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d943-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="4d943-174">Unternehmen sollten [allgemeine Richtlinien für bedingten Zugriff](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) verwenden, um die folgenden Richtlinien zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4d943-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="4d943-175">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="4d943-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="4d943-176">MFA für alle Nutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="4d943-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="4d943-177">Blockieren von Legacy-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4d943-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="4d943-178">Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="4d943-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="4d943-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="4d943-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="4d943-180">Mit Azure AD Identity Protection können Sie eine zusätzliche Richtlinie für bedingten Zugriff erstellen, um [MFA zu erfordern, wenn das Anmelderisiko mittel oder hoch ist.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="4d943-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="4d943-181">Sie können Azure AD Identity Protection und risikobasierte Richtlinien für bedingten Zugriff verwenden mit:</span><span class="sxs-lookup"><span data-stu-id="4d943-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="4d943-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4d943-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="4d943-183">Azure AD Premium P2 Lizenzen</span><span class="sxs-lookup"><span data-stu-id="4d943-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="4d943-184">Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="4d943-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="4d943-185">Legacy-MFA pro Benutzer (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="4d943-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="4d943-186">Sie sollten entweder Sicherheitsstandards oder Richtlinien für bedingten Zugriff verwenden, um MFA für Ihre Benutzerkontoanmeldungen zu erfordern. Wenn jedoch eine davon nicht verwendet werden kann, empfiehlt Microsoft dringend MFA für Benutzerkonten mit Administratorrollen, insbesondere der globalen Administratorrolle, für Abonnements jeder Größe.</span><span class="sxs-lookup"><span data-stu-id="4d943-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="4d943-187">Sie aktivieren MFA für einzelne Benutzerkonten im **aktiven Benutzerbereich** des Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4d943-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Abbildung der Option "Mehrstufige Authentifizierung" auf der Seite "Aktive Benutzer"](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="4d943-189">Nach der Aktivierung wird der Benutzer bei der nächsten Anmeldung aufgefordert, sich für MFA zu registrieren und die zusätzliche Überprüfungsmethode auszuwählen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="4d943-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="4d943-190">Diese Methoden zusammen verwenden</span><span class="sxs-lookup"><span data-stu-id="4d943-190">Using these methods together</span></span>

<span data-ttu-id="4d943-191">Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards, Richtlinien für bedingten Zugriff und Nutzerkonteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4d943-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="4d943-192">*Element*</span><span class="sxs-lookup"><span data-stu-id="4d943-192">*Item*</span></span>|<span data-ttu-id="4d943-193">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="4d943-193">Enabled</span></span>|<span data-ttu-id="4d943-194">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="4d943-194">Disabled</span></span>|<span data-ttu-id="4d943-195">Sekundäre Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="4d943-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="4d943-196">**Sicherheitsstandards**</span><span class="sxs-lookup"><span data-stu-id="4d943-196">**Security defaults**</span></span>|<span data-ttu-id="4d943-197">Richtlinien für bedingten Zugriff können nicht verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4d943-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="4d943-198">Richtlinien für den bedingten Zugriff können verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4d943-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="4d943-199">Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="4d943-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="4d943-200">**Richtlinien für bedingten Zugriff**</span><span class="sxs-lookup"><span data-stu-id="4d943-200">**Conditional Access policies**</span></span>|<span data-ttu-id="4d943-201">Wenn eines aktiviert ist, können Sie die Sicherheitsstandards nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d943-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="4d943-202">Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren</span><span class="sxs-lookup"><span data-stu-id="4d943-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="4d943-203">Nutzerdefiniert bei der MFA-Registrierung</span><span class="sxs-lookup"><span data-stu-id="4d943-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="4d943-204">**Legacy-MFA pro Benutzer (nicht empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="4d943-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="4d943-205">Außerkraftsetzung von Sicherheitsstandards und Richtlinien für bedingten Zugriff, die MFA bei jeder Anmeldung erfordern</span><span class="sxs-lookup"><span data-stu-id="4d943-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="4d943-206">Außer Kraft gesetzt durch Sicherheitsstandards und Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4d943-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="4d943-207">Nutzerdefiniert bei der MFA-Registrierung</span><span class="sxs-lookup"><span data-stu-id="4d943-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="4d943-208">Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Benutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App bei der nächsten Anmeldung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4d943-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="4d943-209">Möglichkeiten zum Verwalten von MFA-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4d943-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="4d943-210">Es gibt zwei Möglichkeiten zum Verwalten von MFA-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4d943-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="4d943-211">Im Azure-Portal haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="4d943-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="4d943-212">Aktivieren und Deaktivieren von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="4d943-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="4d943-213">Konfigurieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4d943-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="4d943-214">Im Microsoft 365 Admin Center können Sie MFA-Einstellungen pro Benutzer und Dienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d943-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d943-215">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4d943-215">Next steps</span></span>

[<span data-ttu-id="4d943-216">Einrichten der MFA für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d943-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="4d943-217">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4d943-217">Related content</span></span>

<span data-ttu-id="4d943-218">[Aktivieren der mehrstufigen Authentifizierung](../../business-video/turn-on-mfa.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="4d943-218">[Turn on multifactor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="4d943-219">[Aktivieren der mehrstufigen Authentifizierung für Ihr Telefon](../../business-video/set-up-mfa.md) (Video)</span><span class="sxs-lookup"><span data-stu-id="4d943-219">[Turn on multifactor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>