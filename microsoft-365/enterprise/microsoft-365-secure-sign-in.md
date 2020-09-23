---
title: Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Legen Sie fest, dass sich Ihre Benutzer über mehrstufige Authentifizierung (MFA) und andere Features sicher anmelden müssen.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132241"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="dfdc8-103">Sichere Benutzeranmeldungen beim Microsoft 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="dfdc8-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="dfdc8-104">So erhöhen Sie die Sicherheit von Benutzeranmeldungen:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="dfdc8-105">Verwenden des Azure Active Directory-Kennwortschutzes (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-105">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="dfdc8-106">Verwenden der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-106">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="dfdc8-107">Bereitstellen von Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dfdc8-107">Deploy identity and device access policies</span></span>

## <a name="azure-ad-password-protection"></a><span data-ttu-id="dfdc8-108">Azure AD-Kennwortschutz</span><span class="sxs-lookup"><span data-stu-id="dfdc8-108">Azure AD Password Protection</span></span>

<span data-ttu-id="dfdc8-109">Der Azure AD-Kennwortschutz erkennt und blockiert als schwach bekannte Kennwörter und deren Varianten und kann zusätzlich für Ihre Organisation spezifische schwache Ausdrücke blockieren.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-109">Azure AD Password Protection detects and blocks known weak passwords and their variants, and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="dfdc8-110">Listen standardmäßig global gesperrter Kennwörter werden automatisch auf alle Benutzer in einem Azure AD-Mandanten angewendet.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-110">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="dfdc8-111">Sie können zusätzliche Einträge in einer benutzerdefinierten Liste gesperrter Kennwörter angeben.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-111">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="dfdc8-112">Wenn Benutzer ihre Kennwörter ändern oder zurücksetzen, werden diese Listen gesperrter Kennwörter überprüft, um die Verwendung von sicheren Kennwörtern zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-112">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="dfdc8-113">Weitere Informationen finden Sie unter [Konfigurieren des Azure AD-Kennwortschutzes](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-113">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="dfdc8-114">MFA (mehrstufige Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-114">MFA</span></span>

<span data-ttu-id="dfdc8-115">MFA erfordert, dass Nutzeranmeldungen einer zusätzlichen Überprüfung unterzogen werden, die über das Kennwort des Nutzerkontos hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-115">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="dfdc8-116">Selbst wenn ein böswilliger Nutzer ein Nutzerkontokennwort ermittelt, muss er in der Lage sein, auf eine zusätzliche Überprüfung zu antworten, z. B. eine Textnachricht, die an ein Smartphone gesendet wird, bevor der Zugriff gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-116">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![Das richtige Kennwort und eine zusätzliche Überprüfungsergebnisse bei einer erfolgreichen Anmeldung](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="dfdc8-118">Der erste Schritt bei der Verwendung von MFA besteht darin, sie ***für alle Administratorkonten als erforderlich festzulegen*** (diese Konten werden auch als privilegierte Konten bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-118">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="dfdc8-119">Über diesen ersten Schritt hinaus empfiehlt Microsoft, die mehrstufige Authentifizierung unbedingt für alle Benutzer vorzugeben.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-119">Beyond this first step, Microsoft strongly recommends MFA For all users.</span></span>

<span data-ttu-id="dfdc8-120">Basierend auf Ihrem Microsoft 365-Plan gibt es drei Möglichkeiten, von Ihren Administratoren oder Nutzern die Verwendung der mehrstufigen Authentifizierung zu verlangen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-120">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="dfdc8-121">Plan</span><span class="sxs-lookup"><span data-stu-id="dfdc8-121">Plan</span></span> | <span data-ttu-id="dfdc8-122">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="dfdc8-122">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="dfdc8-123">Alle Microsoft 365-Pläne (ohne Azure AD Premium P1- oder P2-Lizenzen)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-123">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="dfdc8-124">[Aktivieren Sie die Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-124">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="dfdc8-125">Zu den Sicherheitsstandards in Azure AD gehört MFA für Nutzer und Administratoren.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-125">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="dfdc8-126">Microsoft 365 E3 (einschließlich Azure AD Premium P1-Lizenzen)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-126">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="dfdc8-127">Verwenden Sie [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common), um die folgenden Richtlinien zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-127">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="dfdc8-128">- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-128">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="dfdc8-129">- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-129">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="dfdc8-130">- [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-130">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="dfdc8-131">Microsoft 365 E5 (einschließlich Azure AD Premium P2-Lizenzen)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-131">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="dfdc8-132">Nutzen Sie den Azure AD-Identity Protection, beginnen Sie mit der Implementierung des von Microsoft [empfohlenen Satzes von bedingtem Zugriff und zugehörigen Richtlinien](../enterprise/identity-access-policies.md), indem Sie die folgenden 2 Richtlinien nutzen:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-132">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="dfdc8-133">- [MFA erforderlich, wenn das Anmelderisiko mittel oder hoch ist](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-133">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="dfdc8-134">- [Nutzer mit hohem Risiko müssen das Kennwort ändern](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="dfdc8-134">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="dfdc8-135">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="dfdc8-135">Security defaults</span></span>

<span data-ttu-id="dfdc8-136">Die Sicherheitsstandards sind eine neue Funktion für kostenpflichtige Microsoft 365- und Office 365- oder Testabonnements, die nach dem 21. Oktober 2019 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-136">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="dfdc8-137">Bei diesen Abonnements sind die Sicherheitsstandards aktiviert, sodass ***alle Nutzer MFA mit der Microsoft Authenticator-App verwenden müssen***.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-137">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="dfdc8-138">Nutzer haben 14 Tage Zeit, sich mit ihrem Smartphone mit der Microsoft Authenticator-App für MFA zu registrieren. Dies beginnt mit der ersten Anmeldung, nachdem die Sicherheitsstandards aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-138">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="dfdc8-139">Nach Ablauf von 14 Tagen kann sich der Nutzer erst nach Abschluss der MFA-Registrierung anmelden.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-139">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="dfdc8-140">Sicherheitsstandards stellen sicher, dass alle Organisationen über eine grundlegende Sicherheitsstufe für die Nutzeranmeldung verfügen, die standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-140">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="dfdc8-141">Sie können Sicherheitsstandards für MFA mit Richtlinien für den bedingten Zugriff oder für einzelne Konten deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-141">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="dfdc8-142">Weitere Informationen finden Sie in dieser [Übersicht der Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-142">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="dfdc8-143">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="dfdc8-143">Conditional Access policies</span></span>

<span data-ttu-id="dfdc8-144">Richtlinien für den bedingten Zugriff sind eine Reihe von Regeln, die die Bedingungen angeben, unter denen Anmeldungen ausgewertet werden und der Zugriff gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-144">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="dfdc8-145">Sie können beispielsweise eine Richtlinie für den bedingten Zugriff erstellen, in der Folgendes angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-145">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="dfdc8-146">Entspricht die Bezeichnung eines Benutzerkontos dem Namen eines Mitglieds einer Gruppe von Benutzern, denen Exchange, Benutzer, Kennwort sowie Sicherheits-, SharePoint- oder globale Administratorrollen zugewiesen sind, ist eine mehrstufige Authentifizierung (MFA) erforderlich, bevor der Zugriff genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-146">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="dfdc8-147">Diese Richtlinie ermöglicht es Ihnen, MFA basierend auf einer Gruppenmitgliedschaft zu verlangen, anstatt einzelne Benutzerkonten für MFA zu konfigurieren, wenn diesen Administratorrollen zugewiesen oder entzogen wurden.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-147">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="dfdc8-148">Sie können die Richtlinien für den bedingten Zugriff auch für erweiterte Funktionen verwenden, z. B. wenn die Anmeldung von einem kompatiblen Gerät aus erfolgen muss, z. B. von Ihrem Laptop unter Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-148">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="dfdc8-149">Für den bedingten Zugriff sind Azure AD Premium P1-Lizenzen erforderlich, die in Microsoft 365 E3 und E5 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-149">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="dfdc8-150">Weitere Informationen finden Sie in dieser [Übersicht über den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-150">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="dfdc8-151">Diese Methoden zusammen verwenden</span><span class="sxs-lookup"><span data-stu-id="dfdc8-151">Using these methods together</span></span>

<span data-ttu-id="dfdc8-152">Denken Sie dabei an Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-152">Keep the following in mind:</span></span>

- <span data-ttu-id="dfdc8-153">Sie können die Sicherheitsstandards nicht aktivieren, wenn Sie Richtlinien für den bedingten Zugriff aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-153">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="dfdc8-154">Sie können keine Richtlinien für den bedingten Zugriff aktivieren, wenn Sie die Sicherheitsstandards aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-154">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="dfdc8-155">Wenn die Sicherheitsstandards aktiviert sind, werden alle neuen Nutzer zur MFA-Registrierung und zur Verwendung der Microsoft Authenticator-App aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-155">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="dfdc8-156">Diese Tabelle zeigt die Ergebnisse der Aktivierung von MFA mit Sicherheitsstandards und Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-156">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="dfdc8-157">Methode</span><span class="sxs-lookup"><span data-stu-id="dfdc8-157">Method</span></span> | <span data-ttu-id="dfdc8-158">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="dfdc8-158">Enabled</span></span> | <span data-ttu-id="dfdc8-159">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="dfdc8-159">Disabled</span></span> | <span data-ttu-id="dfdc8-160">Zusätzliche Authentifizierungsmethode</span><span class="sxs-lookup"><span data-stu-id="dfdc8-160">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="dfdc8-161">**Sicherheitsstandards**</span><span class="sxs-lookup"><span data-stu-id="dfdc8-161">**Security defaults**</span></span>  | <span data-ttu-id="dfdc8-162">Richtlinien für bedingten Zugriff können nicht verwendet werden</span><span class="sxs-lookup"><span data-stu-id="dfdc8-162">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="dfdc8-163">Richtlinien für den bedingten Zugriff können verwendet werden</span><span class="sxs-lookup"><span data-stu-id="dfdc8-163">Can use Conditional Access policies</span></span> | <span data-ttu-id="dfdc8-164">Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="dfdc8-164">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="dfdc8-165">**Richtlinien für bedingten Zugriff**</span><span class="sxs-lookup"><span data-stu-id="dfdc8-165">**Conditional Access policies**</span></span> | <span data-ttu-id="dfdc8-166">Wenn welche aktiviert sind, können Sie die Sicherheitsstandards nicht aktivieren</span><span class="sxs-lookup"><span data-stu-id="dfdc8-166">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="dfdc8-167">Wenn alle deaktiviert sind, können Sie die Sicherheitsstandards aktivieren</span><span class="sxs-lookup"><span data-stu-id="dfdc8-167">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="dfdc8-168">Werden vom Benutzer während der MFA-Registrierung festgelegt</span><span class="sxs-lookup"><span data-stu-id="dfdc8-168">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-policies"></a><span data-ttu-id="dfdc8-169">Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dfdc8-169">Identity and device access policies</span></span>

<span data-ttu-id="dfdc8-170">Einstellungen und Richtlinien für den Identitäts- und Gerätezugriff sind empfohlene Voraussetzungen. Deren Einstellungen bestimmen in Kombination mit bedingtem Zugriff, Intune und Azure AD Identity Protection-Richtlinien für den Identitätsschutz, ob und unter welchen Bedingungen einer bestimmten Zugriffsanforderung zugestimmt werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-170">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="dfdc8-171">Diese Ermittlung basiert auf dem Benutzerkonto der Anmeldung, dem verwendeten Gerät, der vom Benutzer für die Anmeldung verwendeten App, dem Ort, an dem die Zugriffsanforderung erfolgt sowie einer Bewertung des Risikos der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-171">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="dfdc8-172">Diese Funktion trägt dazu bei, sicherzustellen, dass nur autorisierte Benutzer und Geräte auf Ihre kritischen Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-172">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="dfdc8-173">Für Azure AD Identity Protection sind Azure AD Premium P2-Lizenzen erforderlich, die in Microsoft 365 E5 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-173">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="dfdc8-174">Identitäts- und Gerätezugriffsrichtlinien sind für die Verwendung auf drei Ebenen definiert:</span><span class="sxs-lookup"><span data-stu-id="dfdc8-174">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="dfdc8-175">Der grundlegende Schutz bietet ein Mindestmaß an Sicherheit für Ihre Identitäten und Geräte, die auf Ihre Apps und Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-175">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="dfdc8-176">Der Schutz vertraulicher Daten bietet zusätzliche Sicherheit für bestimmte Daten.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-176">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="dfdc8-177">Identitäten und Geräte müssen höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-177">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="dfdc8-178">Der Schutz für Umgebungen mit strengen Datensicherheitsbestimmungen ist für in der Regel kleine Mengen von Daten bestimmt, die streng vertraulich sind, Geschäftsgeheimnisse enthalten oder Datenschutzbestimmungen unterliegen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-178">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="dfdc8-179">Identitäten und Geräte müssen viel höheren Sicherheits- und Geräteintegritätsanforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-179">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="dfdc8-180">Diese Ebenen und die entsprechenden Konfigurationen bieten einheitliche Schutzniveaus für Ihre Daten, Identitäten und Geräte.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-180">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="dfdc8-181">Microsoft empfiehlt dringend das Konfigurieren und Bereitstellen von Identitäts- und Gerätezugriffsrichtlinien in Ihrer Organisation, einschließlich spezifischer Einstellungen für Microsoft Teams, Exchange Online und SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dfdc8-181">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="dfdc8-182">Weitere Informationen finden Sie unter [Konfigurationen für den Identitäts- und Gerätezugriff](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="dfdc8-182">For more information, see [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="dfdc8-183">Technische Administratorressourcen für mehrstufige Authentifizierung (MFA) und sichere Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="dfdc8-183">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="dfdc8-184">MFA für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfdc8-184">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="dfdc8-185">Identitäts-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfdc8-185">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="dfdc8-186">Azure Academy Azure AD-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="dfdc8-186">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="dfdc8-187">Konfigurieren Sie die Registrierungsrichtlinie für die Azure-Multi-Faktor-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dfdc8-187">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="dfdc8-188">Konfigurationen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="dfdc8-188">Identity and device access configurations</span></span>](microsoft-365-policies-configurations.md)
