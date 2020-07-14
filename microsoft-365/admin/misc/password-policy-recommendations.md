---
title: Empfehlungen für Kennwortrichtlinien
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Erfahren Sie, wie Sie Ihre Organisation vor Kennwortangriffen schützen und warum Sie häufig verwendete Kennwörter verbieten und die risikobasierte mehrstufige Authentifizierung aktivieren sollten.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015923"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="a5a01-103">Empfehlungen für Kennwortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a5a01-103">Password policy recommendations</span></span>
 
<span data-ttu-id="a5a01-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="a5a01-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="a5a01-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span><span class="sxs-lookup"><span data-stu-id="a5a01-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="a5a01-106">Um zu ermitteln, wie oft Microsoft 365-Kennwörter in Ihrer Organisation ablaufen, lesen Sie die Informationen unter [Festlegen der Kennwortablaufrichtlinie für Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a5a01-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="a5a01-107">Weitere Informationen über Microsoft 365-Kennwörter finden Sie in diesen [verwandten Artikeln](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="a5a01-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="a5a01-108">Grundlegendes zu Kennwortempfehlungen</span><span class="sxs-lookup"><span data-stu-id="a5a01-108">Understanding password recommendations</span></span>

<span data-ttu-id="a5a01-109">Empfohlene Kennwortpraktiken werden in einige allgemeine Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="a5a01-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="a5a01-110">**Schutz vor häufig vorkommenden Angriffen** Legen Sie fest, wo Benutzer Kennwörter eingeben können (bekannte und vertrauenswürdige Geräte mit guter Erkennung von Malware, überprüften Websites) und welche Kennwörter verwendet werden dürfen (Länge und Eindeutigkeit).</span><span class="sxs-lookup"><span data-stu-id="a5a01-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="a5a01-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span><span class="sxs-lookup"><span data-stu-id="a5a01-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="a5a01-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span><span class="sxs-lookup"><span data-stu-id="a5a01-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="a5a01-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span><span class="sxs-lookup"><span data-stu-id="a5a01-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="a5a01-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span><span class="sxs-lookup"><span data-stu-id="a5a01-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="a5a01-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span><span class="sxs-lookup"><span data-stu-id="a5a01-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="a5a01-116">Kennwortrichtlinien für Administratoren</span><span class="sxs-lookup"><span data-stu-id="a5a01-116">Password guidelines for administrators</span></span>

<span data-ttu-id="a5a01-117">The primary goal of a more secure password system is password diversity.</span><span class="sxs-lookup"><span data-stu-id="a5a01-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="a5a01-118">You want your password policy to contain lots of different and hard to guess passwords.</span><span class="sxs-lookup"><span data-stu-id="a5a01-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="a5a01-119">Here are a few recommendations for keeping your organization as secure as possible.</span><span class="sxs-lookup"><span data-stu-id="a5a01-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="a5a01-120">Halten Sie eine Mindestlänge von 8 Zeichen ein (länger ist nicht unbedingt besser).</span><span class="sxs-lookup"><span data-stu-id="a5a01-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="a5a01-121">Don't require character composition requirements.</span><span class="sxs-lookup"><span data-stu-id="a5a01-121">Don't require character composition requirements.</span></span> <span data-ttu-id="a5a01-122">For example, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="a5a01-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="a5a01-123">Fordern Sie kein obligatorisches periodisches Zurücksetzen der Kennwörter für Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="a5a01-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="a5a01-124">Verbieten Sie gängige Kennwörter, um die anfälligsten Kennwörter von Ihrem System fernzuhalten.</span><span class="sxs-lookup"><span data-stu-id="a5a01-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="a5a01-125">Informieren Sie Ihre Benutzer, dass sie ihre Organisationskennwörter nicht für private Zwecke wiederverwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="a5a01-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="a5a01-126">Erzwingen Sie die Registrierung für die [mehrstufige Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="a5a01-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="a5a01-127">Aktivieren Sie risikobasierte mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a5a01-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="a5a01-128">Kennwortratgeber für Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5a01-128">Password guidance for your users</span></span>

<span data-ttu-id="a5a01-129">Here's some password guidance for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="a5a01-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="a5a01-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span><span class="sxs-lookup"><span data-stu-id="a5a01-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="a5a01-131">Verwenden Sie kein Kennwort, das einem auf anderen Websites verwendeten Kennwort entspricht oder ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="a5a01-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="a5a01-132">Verwenden Sie kein einzelnes Wort, z. B. **Kennwort** und keinen häufig verwendeten Ausdruck, z. B. **Ichliebedich**</span><span class="sxs-lookup"><span data-stu-id="a5a01-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="a5a01-133">Verwenden Sie Kennwörter, die selbst für Personen schwer zu erraten sind, die viel über Sie wissen (wie z. B. die Namen und Geburtstage Ihrer Freunde und Familie, Ihre Lieblingsbands und Phrasen, die Sie gerne verwenden).</span><span class="sxs-lookup"><span data-stu-id="a5a01-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="a5a01-134">Einige allgemeine Ansätze sowie deren negative Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="a5a01-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="a5a01-135">Dies sind einige der am häufigsten verwendeten Kennwortverwaltungspraktiken, aber Recherchen warnen vor deren negativen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="a5a01-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="a5a01-136">Anforderungen für den Ablauf von Benutzerkennwörtern</span><span class="sxs-lookup"><span data-stu-id="a5a01-136">Password expiration requirements for users</span></span>

<span data-ttu-id="a5a01-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span><span class="sxs-lookup"><span data-stu-id="a5a01-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="a5a01-138">In these cases, the next password can be predicted based on the previous password.</span><span class="sxs-lookup"><span data-stu-id="a5a01-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="a5a01-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span><span class="sxs-lookup"><span data-stu-id="a5a01-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="a5a01-140">Anforderung an die Länge von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="a5a01-140">Requiring long passwords</span></span>

<span data-ttu-id="a5a01-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span><span class="sxs-lookup"><span data-stu-id="a5a01-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="a5a01-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span><span class="sxs-lookup"><span data-stu-id="a5a01-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="a5a01-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span><span class="sxs-lookup"><span data-stu-id="a5a01-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="a5a01-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span><span class="sxs-lookup"><span data-stu-id="a5a01-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="a5a01-145">Fordern der Verwendung von mehreren Zeichensätzen</span><span class="sxs-lookup"><span data-stu-id="a5a01-145">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="a5a01-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span><span class="sxs-lookup"><span data-stu-id="a5a01-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="a5a01-147">Most systems enforce some level of password complexity requirements.</span><span class="sxs-lookup"><span data-stu-id="a5a01-147">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="a5a01-148">For example, passwords need characters from all three of the following categories:</span><span class="sxs-lookup"><span data-stu-id="a5a01-148">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="a5a01-149">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="a5a01-149">uppercase characters</span></span>

- <span data-ttu-id="a5a01-150">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="a5a01-150">lowercase characters</span></span>

- <span data-ttu-id="a5a01-151">Nicht alphanumerische Zeichen</span><span class="sxs-lookup"><span data-stu-id="a5a01-151">non-alphanumeric characters</span></span>

<span data-ttu-id="a5a01-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span><span class="sxs-lookup"><span data-stu-id="a5a01-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="a5a01-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span><span class="sxs-lookup"><span data-stu-id="a5a01-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="a5a01-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span><span class="sxs-lookup"><span data-stu-id="a5a01-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="a5a01-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span><span class="sxs-lookup"><span data-stu-id="a5a01-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="a5a01-156">Erfolgreiche Muster</span><span class="sxs-lookup"><span data-stu-id="a5a01-156">Successful Patterns</span></span>

<span data-ttu-id="a5a01-157">Im Gegensatz dazu finden Sie hier einige Empfehlungen zur Förderung der Kennwortvielfalt.</span><span class="sxs-lookup"><span data-stu-id="a5a01-157">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="a5a01-158">Häufig verwendete Kennwörter sperren</span><span class="sxs-lookup"><span data-stu-id="a5a01-158">Ban common passwords</span></span>

<span data-ttu-id="a5a01-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span><span class="sxs-lookup"><span data-stu-id="a5a01-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="a5a01-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span><span class="sxs-lookup"><span data-stu-id="a5a01-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="a5a01-161">Weisen Sie die Benutzer an, keine Kennwörter der Organisation an anderer Stelle wiederzuverwenden</span><span class="sxs-lookup"><span data-stu-id="a5a01-161">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="a5a01-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span><span class="sxs-lookup"><span data-stu-id="a5a01-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="a5a01-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span><span class="sxs-lookup"><span data-stu-id="a5a01-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="a5a01-164">Erzwingen Sie die Registrierung für die mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a5a01-164">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="a5a01-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span><span class="sxs-lookup"><span data-stu-id="a5a01-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="a5a01-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span><span class="sxs-lookup"><span data-stu-id="a5a01-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="a5a01-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span><span class="sxs-lookup"><span data-stu-id="a5a01-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="a5a01-168">Weitere Informationen finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a5a01-168">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="a5a01-169">Aktivieren Sie die risikobasierte mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a5a01-169">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="a5a01-170">Durch die risikobasierte mehrstufige Authentifizierung wird sichergestellt, dass sich der Benutzer nachweisen kann, dass er der rechtmäßige Kontoinhaber ist, falls unser System verdächtige Aktivitäten erkennt.</span><span class="sxs-lookup"><span data-stu-id="a5a01-170">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="a5a01-171">Möchten Sie mehr darüber wissen?</span><span class="sxs-lookup"><span data-stu-id="a5a01-171">Want to know more?</span></span> <span data-ttu-id="a5a01-172">Empfohlene Literatur</span><span class="sxs-lookup"><span data-stu-id="a5a01-172">Recommended reading</span></span>

- [<span data-ttu-id="a5a01-173">Können starke Webkennwörter etwas bewirken?</span><span class="sxs-lookup"><span data-stu-id="a5a01-173">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="a5a01-174">Kennwortportfolios und der "Finite-Effort"-Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5a01-174">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="a5a01-175">Verhindern unsicherer Kennwörter, indem man die Gedanken der Benutzer liest</span><span class="sxs-lookup"><span data-stu-id="a5a01-175">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="a5a01-176">Auswählen sicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="a5a01-176">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="a5a01-177">Zeit zum Überdenken der obligatorischen Kennwortänderungen</span><span class="sxs-lookup"><span data-stu-id="a5a01-177">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="a5a01-178">Liste der schlechtesten Kennwörter 2015</span><span class="sxs-lookup"><span data-stu-id="a5a01-178">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [<span data-ttu-id="a5a01-179">Herunterladen von Dateien aus dem Internet</span><span class="sxs-lookup"><span data-stu-id="a5a01-179">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a><span data-ttu-id="a5a01-180">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a5a01-180">Related articles</span></span>

[<span data-ttu-id="a5a01-181">Zurücksetzen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="a5a01-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="a5a01-182">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="a5a01-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="a5a01-183">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="a5a01-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="a5a01-184">Erneutes Senden eines Benutzerkennworts – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="a5a01-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
