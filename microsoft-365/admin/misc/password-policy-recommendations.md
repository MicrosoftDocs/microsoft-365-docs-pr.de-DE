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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Erfahren Sie, wie Sie Ihre Organisation vor Kennwortangriffen schützen und warum Sie häufig verwendete Kennwörter verbieten und die risikobasierte mehrstufige Authentifizierung aktivieren sollten.
ms.openlocfilehash: 66a4048ac1add3a0d47f256dc29519a91ae6cb11
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926714"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="79739-103">Empfehlungen für Kennwortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="79739-103">Password policy recommendations</span></span>

<span data-ttu-id="79739-p101">Als Administrator einer Organisation sind Sie für das Einrichten der Kennwortrichtlinie für Benutzer in Ihrer Organisation verantwortlich. das Festlegen der Kennwortrichtlinie kann kompliziert und verwirrend sein, und dieser Artikel enthält Empfehlungen, wie Sie Ihre Organisation besser vor Kennwortangriffen schützen können.</span><span class="sxs-lookup"><span data-stu-id="79739-p101">As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="79739-106">Um zu ermitteln, wie oft Microsoft 365-Kennwörter in Ihrer Organisation ablaufen, lesen Sie die Informationen unter [Festlegen der Kennwortablaufrichtlinie für Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="79739-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="79739-107">Weitere Informationen über Microsoft 365-Kennwörter finden Sie in diesen [verwandten Artikeln](#related-articles).</span><span class="sxs-lookup"><span data-stu-id="79739-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="79739-108">Grundlegendes zu Kennwortempfehlungen</span><span class="sxs-lookup"><span data-stu-id="79739-108">Understanding password recommendations</span></span>

<span data-ttu-id="79739-109">Empfohlene Kennwortpraktiken werden in einige allgemeine Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="79739-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="79739-110">**Schutz vor häufig vorkommenden Angriffen** Legen Sie fest, wo Benutzer Kennwörter eingeben können (bekannte und vertrauenswürdige Geräte mit guter Erkennung von Malware, überprüften Websites) und welche Kennwörter verwendet werden dürfen (Länge und Eindeutigkeit).</span><span class="sxs-lookup"><span data-stu-id="79739-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="79739-p102">**Eindämmung erfolgreicher Angriffe** Bei der Eindämmung erfolgreicher Hackerangriffe geht es darum, die Gefährdung auf einen bestimmten Dienst einzuschränken oder den Schaden komplett zu verhindern, wenn das Kennwort eines Benutzers gestohlen wird. So sollte beispielsweise sichergestellt werden, dass durch den Angriff auf Ihre Social Networking-Anmeldeinformationen Ihr Bankkonto nicht angreifbar wird oder dass ein schlecht bewachtes Konto keine Reset-Links für ein wichtiges Konto zulässt.</span><span class="sxs-lookup"><span data-stu-id="79739-p102">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="79739-p103">**Die menschliche Natur verstehen** Viele gültige Kennwortpraktiken scheitern an natürlichen menschlichen Verhaltensweisen. Das Verständnis der menschlichen Natur ist von äußerster Bedeutung, denn Untersuchungen zeigen, dass fast jede Regel, die Sie Ihren Benutzern auferlegen, zu einer Schwächung der Kennwortqualität führt. Anforderungen an Länge, Sonderzeichen und Kennwortänderungen führen zu einer Normalisierung der Kennwörter, was es Angreifern erleichtert, Kennwörter zu erraten oder zu knacken.</span><span class="sxs-lookup"><span data-stu-id="79739-p103">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="79739-116">Kennwortrichtlinien für Administratoren</span><span class="sxs-lookup"><span data-stu-id="79739-116">Password guidelines for administrators</span></span>

<span data-ttu-id="79739-p104">Das primäre Ziel eines sichereren Kennwortsystems ist die Vielfalt der Kennwörter. Sie möchten, dass Ihre Kennwortrichtlinie viele verschiedene und schwer zu erratende Kennwörter umfasst. Hier sind ein paar Empfehlungen, wie Sie Ihre Organisation am besten schützen können.</span><span class="sxs-lookup"><span data-stu-id="79739-p104">The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="79739-120">Halten Sie eine Mindestlänge von 8 Zeichen ein (länger ist nicht unbedingt besser).</span><span class="sxs-lookup"><span data-stu-id="79739-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="79739-p105">Legen Sie keine Anforderungen an die Zeichenzusammensetzung fest. Zum Beispiel \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="79739-p105">Don't require character composition requirements. For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="79739-123">Fordern Sie kein obligatorisches periodisches Zurücksetzen der Kennwörter für Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="79739-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="79739-124">Verbieten Sie gängige Kennwörter, um die anfälligsten Kennwörter von Ihrem System fernzuhalten.</span><span class="sxs-lookup"><span data-stu-id="79739-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="79739-125">Informieren Sie Ihre Benutzer, dass sie ihre Organisationskennwörter nicht für private Zwecke wiederverwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="79739-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="79739-126">Erzwingen Sie die Registrierung für die [mehrstufige Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="79739-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="79739-127">Aktivieren Sie risikobasierte mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="79739-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="79739-128">Kennwortratgeber für Benutzer</span><span class="sxs-lookup"><span data-stu-id="79739-128">Password guidance for your users</span></span>

<span data-ttu-id="79739-p106">Hier finden Sie einige Kennwortanleitungen für Benutzer in Ihrer Organisation. Informieren Sie Ihre Benutzer über diese Empfehlungen und setzen Sie die empfohlenen Kennwortrichtlinien auf Organisationsebene durch.</span><span class="sxs-lookup"><span data-stu-id="79739-p106">Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="79739-131">Verwenden Sie kein Kennwort, das einem auf anderen Websites verwendeten Kennwort entspricht oder ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="79739-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="79739-132">Verwenden Sie kein einzelnes Wort, z. B. **Kennwort** und keinen häufig verwendeten Ausdruck, z. B. **Ichliebedich**</span><span class="sxs-lookup"><span data-stu-id="79739-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="79739-133">Verwenden Sie Kennwörter, die selbst für Personen schwer zu erraten sind, die viel über Sie wissen (wie z. B. die Namen und Geburtstage Ihrer Freunde und Familie, Ihre Lieblingsbands und Phrasen, die Sie gerne verwenden).</span><span class="sxs-lookup"><span data-stu-id="79739-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="79739-134">Einige allgemeine Ansätze sowie deren negative Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="79739-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="79739-135">Dies sind einige der am häufigsten verwendeten Kennwortverwaltungspraktiken, aber Recherchen warnen vor deren negativen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="79739-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="79739-136">Anforderungen für den Ablauf von Benutzerkennwörtern</span><span class="sxs-lookup"><span data-stu-id="79739-136">Password expiration requirements for users</span></span>

<span data-ttu-id="79739-p107">Anforderungen für den Ablauf von Kennwörtern schaden mehr als dass sie nützen, da diese Anforderungen die Benutzer dazu veranlassen, vorhersagbare Passwörter zu wählen, die aus aufeinanderfolgenden Wörtern und Zahlen bestehen, die eng miteinander verwandt sind. In diesen Fällen kann das nächste Kennwort anhand des vorherigen Kennwortes vorhergesagt werden. Anforderungen für den Ablauf von Kennwörtern bieten keine Vorteile hinsichtlich der Abwehr von Angriffen, da Cyberkriminelle Anmeldeinformationen, sobald sie diese herausgefunden haben, fast immer sofort verwenden. Weitere Informationen finden Sie unter [Zeit zum Überdenken der obligatorischen Kennwortänderungen](https://go.microsoft.com/fwlink/p/?linkid=861018).</span><span class="sxs-lookup"><span data-stu-id="79739-p107">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them. Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="79739-141">Anforderung an die Länge von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="79739-141">Requiring long passwords</span></span>

<span data-ttu-id="79739-p108">Anforderung an die Länge von Kennwörtern (mehr als ca. 10 Zeichen) können zu einem vorhersehbaren und nicht wünschenswerten Benutzerverhalten führen. Benutzer, die gezwungen werden, ein Kennwort mit 16 Zeichen zu verwenden, neigen beispielsweise dazu, sich wiederholende Muster wie **viervierviervier** oder **KennwortKennwort** auszuwählen, die die Anforderung an die Zeichenlänge erfüllen, aber nicht schwer zu erraten sind. Darüber hinaus erhöhen Längenanforderungen die Wahrscheinlichkeit, dass Benutzer andere unsichere Methoden verwenden, wie z. B., ihre Kennwörter aufzuschreiben, wiederzuverwenden oder unverschlüsselt in ihren Dokumenten zu speichern. Um Benutzer zu ermutigen, eindeutige Kennwörter zu erstellen, empfehlen wir eine angemessene Mindestlängenanforderung von 8 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="79739-p108">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="79739-146">Fordern der Verwendung von mehreren Zeichensätzen</span><span class="sxs-lookup"><span data-stu-id="79739-146">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="79739-p109">Anforderungen an die Kennwortkomplexität reduzieren den Schlüsselraum und veranlassen Benutzer dazu, auf vorhersehbare Weise zu handeln, wodurch sie mehr Schaden als Nutzen anrichten. Die meisten Systeme erzwingen ein bestimmtes Maß an Anforderungen an die Kennwortkomplexität. Beispielsweise müssen Kennwörter Zeichen aus allen drei der folgenden Kategorien enthalten:</span><span class="sxs-lookup"><span data-stu-id="79739-p109">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="79739-150">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="79739-150">uppercase characters</span></span>

- <span data-ttu-id="79739-151">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="79739-151">lowercase characters</span></span>

- <span data-ttu-id="79739-152">Nicht alphanumerische Zeichen</span><span class="sxs-lookup"><span data-stu-id="79739-152">non-alphanumeric characters</span></span>

<span data-ttu-id="79739-p110">Die meisten Benutzer verwenden ähnliche Muster, z. B. einen Großbuchstabe an der ersten Position, ein Symbol an der letzten Position und eine Zahl an den letzten 2 Stellen. Cyberkriminelle wissen dies, daher führen sie ihre Wörterbuchangriffe unter Verwendung der am häufigsten verwendeten Austauschzeichen durch, "$" für "s", "@" für "a", "1" für "l". Wenn Sie Ihre Benutzer zwingen, eine Kombination aus Groß- und Kleinbuchstaben, Ziffern und Sonderzeichen zu wählen, wirkt sich das negativ aus. Einige Komplexitätsanforderungen hindern Benutzer sogar daran, sichere und einprägsame Kennwörter zu verwenden, und zwingen sie dazu, weniger sichere und weniger einprägsame Kennwörter zu wählen.</span><span class="sxs-lookup"><span data-stu-id="79739-p110">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="79739-157">Erfolgreiche Muster</span><span class="sxs-lookup"><span data-stu-id="79739-157">Successful Patterns</span></span>

<span data-ttu-id="79739-158">Im Gegensatz dazu finden Sie hier einige Empfehlungen zur Förderung der Kennwortvielfalt.</span><span class="sxs-lookup"><span data-stu-id="79739-158">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="79739-159">Häufig verwendete Kennwörter sperren</span><span class="sxs-lookup"><span data-stu-id="79739-159">Ban common passwords</span></span>

<span data-ttu-id="79739-p111">Die wichtigste Kennwortanforderung, die Sie Ihren Benutzern bei der Erstellung von Kennwörtern auferlegen sollten, besteht darin, die Verwendung häufig verwendeter Kennwörter zu verbieten, um die Anfälligkeit Ihres Unternehmens für Brute-Force-Kennwortangriffe zu verringern. Häufig verwendete Benutzerkennwörter sind beispielsweise **abcdefg**, **Kennwort**, **123456**.</span><span class="sxs-lookup"><span data-stu-id="79739-p111">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="79739-162">Weisen Sie die Benutzer an, keine Kennwörter der Organisation an anderer Stelle wiederzuverwenden</span><span class="sxs-lookup"><span data-stu-id="79739-162">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="79739-p112">Eine der wichtigsten Botschaften, die Sie den Benutzern in Ihrer Organisation vermitteln müssen, ist, dass Sie ihr Organisationskennwort nirgendwo anders wiederverwenden dürfen. Die Verwendung von Organisationskennwörtern auf externen Websites erhöht die Wahrscheinlichkeit erheblich, dass Cyberkriminelle diese Kennwörter knacken.</span><span class="sxs-lookup"><span data-stu-id="79739-p112">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="79739-165">Erzwingen Sie die Registrierung für die mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="79739-165">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="79739-p113">Stellen Sie sicher, dass Ihre Benutzer Kontakt- und Sicherheitsinformationen aktualisieren (z. B. eine alternative E-Mail-Adresse, Telefonnummer oder ein Gerät, das für Pushbenachrichtigungen registriert ist), damit sie auf Sicherheitsherausforderungen reagieren und über Sicherheitsereignisse benachrichtigt werden können. Aktualisierte Kontakt- und Sicherheitsinformationen helfen Benutzern, ihre Identität zu verifizieren, wenn sie ihr Passwort vergessen haben oder wenn jemand anderes versucht, ihr Konto zu übernehmen. Zudem wird ein Out-of-Band-Benachrichtigungskanal für den Fall bereitgestellt, dass Sicherheitsereignisse wie Anmeldeversuche oder geänderte Kennwörter eintreten.</span><span class="sxs-lookup"><span data-stu-id="79739-p113">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="79739-169">Weitere Informationen finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="79739-169">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="79739-170">Aktivieren Sie die risikobasierte mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="79739-170">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="79739-171">Durch die risikobasierte mehrstufige Authentifizierung wird sichergestellt, dass sich der Benutzer nachweisen kann, dass er der rechtmäßige Kontoinhaber ist, falls unser System verdächtige Aktivitäten erkennt.</span><span class="sxs-lookup"><span data-stu-id="79739-171">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="79739-172">Möchten Sie mehr darüber wissen?</span><span class="sxs-lookup"><span data-stu-id="79739-172">Want to know more?</span></span> <span data-ttu-id="79739-173">Empfohlene Literatur</span><span class="sxs-lookup"><span data-stu-id="79739-173">Recommended reading</span></span>

- [<span data-ttu-id="79739-174">Können starke Webkennwörter etwas bewirken?</span><span class="sxs-lookup"><span data-stu-id="79739-174">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="79739-175">Kennwortportfolios und der "Finite-Effort"-Benutzer</span><span class="sxs-lookup"><span data-stu-id="79739-175">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="79739-176">Verhindern unsicherer Kennwörter, indem man die Gedanken der Benutzer liest</span><span class="sxs-lookup"><span data-stu-id="79739-176">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="79739-177">Auswählen sicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="79739-177">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="79739-178">Zeit zum Überdenken der obligatorischen Kennwortänderungen</span><span class="sxs-lookup"><span data-stu-id="79739-178">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="79739-179">Liste der schlechtesten Kennwörter 2015</span><span class="sxs-lookup"><span data-stu-id="79739-179">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-articles"></a><span data-ttu-id="79739-180">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="79739-180">Related articles</span></span>

[<span data-ttu-id="79739-181">Zurücksetzen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="79739-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="79739-182">Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft</span><span class="sxs-lookup"><span data-stu-id="79739-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="79739-183">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="79739-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="79739-184">Erneutes Senden eines Benutzerkennworts – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="79739-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
