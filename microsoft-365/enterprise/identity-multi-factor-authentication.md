---
title: 'Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der mehrstufigen Authentifizierung für Benutzerkonten.
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981846"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="f0def-103">Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f0def-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f0def-104">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f0def-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="f0def-105">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0def-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f0def-p101">In diesem Schritt richten Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzuzufügen. MFA erfordert eine zusätzliche Überprüfungsmethode, nachdem Benutzer ihr Kennwort richtig eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem mit Kennwörtern ist, dass sie häufig von einem Angreifer leicht zu erraten sind oder unbewusst für nicht vertrauenswürdige Parteien freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0def-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="f0def-110">Die zweite Sicherheitsebene bei MFA kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="f0def-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="f0def-111">Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="f0def-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="f0def-112">Ein biometrisches Attribut, z. B. ein Fingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="f0def-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="f0def-113">Sie aktivieren MFA und konfigurieren die sekundäre Authentifizierungsmethode mit [bedingten Zugriffsrichtlinien](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), die es Ihnen ermöglichen, Azure Active Directory-Gruppen (Azure AD) zum Rollout von MFA für bestimmte Gruppen von Benutzern, z. B. Pilotbenutzer, geografische Regionen oder Abteilungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0def-113">You'll enable MFA and configure the secondary authentication method with [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="f0def-114">Teilen Sie Ihren Benutzern unbedingt mit, dass MFA aktiviert ist, damit sie die Anforderungen, z. B. obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können.</span><span class="sxs-lookup"><span data-stu-id="f0def-114">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="f0def-115">Weitere Informationen finden Sie unter [Planen der mehrstufigen Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="f0def-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="f0def-p103">In einigen Clientanwendungen, z. B. Microsoft Office 2010 oder früher und Apple Mail, können Sie MFA nicht verwenden. Um diese Apps zu nutzen, müssen Sie „App-Kennwörter“ anstelle Ihres herkömmlichen Kennworts verwenden. Das App-Kennwort ermöglicht der App, MFA zu umgehen und die Arbeit fortzusetzen. Weitere Informationen zu App-Kennwörtern finden Sie unter [Erstellen eines App-Kennworts für Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="f0def-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f0def-121">Testumgebungsanleitung: Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f0def-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="f0def-122">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="f0def-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="f0def-123">Verhindern unsicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="f0def-123">Prevent bad passwords</span></span>

<span data-ttu-id="f0def-124">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0def-124">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f0def-125">Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0def-125">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="f0def-126">So können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B. "</span><span class="sxs-lookup"><span data-stu-id="f0def-126">For example, you can specify terms that are specific to your organization, such as"</span></span>

- <span data-ttu-id="f0def-127">Markennamen</span><span class="sxs-lookup"><span data-stu-id="f0def-127">Brand names</span></span>
- <span data-ttu-id="f0def-128">Produktnamen</span><span class="sxs-lookup"><span data-stu-id="f0def-128">Product names</span></span>
- <span data-ttu-id="f0def-129">Standorte (z. B. Firmenhauptsitz)</span><span class="sxs-lookup"><span data-stu-id="f0def-129">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="f0def-130">Unternehmensspezifische interne Begriffe</span><span class="sxs-lookup"><span data-stu-id="f0def-130">Company-specific internal terms</span></span>
- <span data-ttu-id="f0def-131">Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben.</span><span class="sxs-lookup"><span data-stu-id="f0def-131">Abbreviations that have specific company meaning.</span></span>

<span data-ttu-id="f0def-132">Sie können unsichere Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory-Domänendienste (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) sperren.</span><span class="sxs-lookup"><span data-stu-id="f0def-132">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="f0def-133">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-password-prot) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="f0def-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="f0def-134">Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f0def-134">Protect against credential compromise</span></span>

<span data-ttu-id="f0def-135">*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0def-135">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f0def-136">In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0def-136">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="f0def-137">Azure AD Identity Protection bietet eine Reihe von Methoden, mit denen verhindert werden kann, dass sich ein Angreifer seitwärts durch Konten und Gruppen und folglich Ihre wertvollsten Daten bewegt.</span><span class="sxs-lookup"><span data-stu-id="f0def-137">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="f0def-138">Mit Azure AD Identity Protection können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f0def-138">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="f0def-139">Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="f0def-139">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="f0def-140">Azure AD verwendet das maschinelle Lernen, um Anomalien und verdächtige Aktivitäten wie Anmeldeaktivitäten und Aktivitäten nachdem Anmelden zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="f0def-140">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="f0def-141">Anhand dieser Daten generiert Azure AD Identity Protection Berichte und Warnungen, mit denen Sie die Probleme bewerten und entsprechende Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="f0def-141">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="f0def-142">Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="f0def-142">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="f0def-143">Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="f0def-143">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="f0def-144">Mit diesen Richtlinien in Verbindung mit anderen Kontrollelementen für den bedingten Zugriff von Azure AD und Microsoft Intune können entweder Zugriffsversuche automatisch blockiert oder Korrekturmaßnahmen ergriffen werden. Hierzu gehören Kennwortzurücksetzungen und die Durchsetzung der Multi-Factor Authentication für nachfolgende Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="f0def-144">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="f0def-145">Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="f0def-145">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="f0def-p108">Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f0def-p108">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="f0def-148">Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="f0def-148">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="f0def-149">Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="f0def-149">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="f0def-150">In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f0def-150">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="f0def-151">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="f0def-151">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="f0def-152">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f0def-152">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="f0def-153">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="f0def-153">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f0def-155">Testumgebungsanleitung: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f0def-155">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="f0def-156">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="f0def-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="f0def-157">Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="f0def-157">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="f0def-158">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0def-158">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f0def-p109">In diesem Schritt überprüfen Sie Überwachungsprotokolle und Anmeldeaktivitäten mithilfe von Azure AD-Berichten. Es stehen zwei Arten von Berichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f0def-p109">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="f0def-p110">Der **Aktivitätsbericht „Überwachungsprotokolle“** verzeichnet den Verlauf jeder in Ihrem Azure AD-Mandanten ausgeführten Aufgabe. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="f0def-p110">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="f0def-163">Wer hat eine Person zu einer Administratorengruppe hinzugefügt?</span><span class="sxs-lookup"><span data-stu-id="f0def-163">Who added someone to an admin group?</span></span>
- <span data-ttu-id="f0def-164">Welche Benutzer melden sich bei einer bestimmten App an?</span><span class="sxs-lookup"><span data-stu-id="f0def-164">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="f0def-165">Wie viele Kennwortzurücksetzungen werden ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="f0def-165">How many password resets are happening?</span></span>

<span data-ttu-id="f0def-p111">Der **Aktivitätsbericht „Anmeldungen“** verzeichnet, wer die im Überwachungsprotokollbericht gemeldeten Aufgaben ausgeführt hat. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="f0def-p111">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="f0def-168">Welches Anmeldemuster gilt für einen bestimmten untersuchten Benutzer?</span><span class="sxs-lookup"><span data-stu-id="f0def-168">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="f0def-169">Wie groß ist das Volumen von Anmeldungen über einen Tag, eine Woche oder einen Monat?</span><span class="sxs-lookup"><span data-stu-id="f0def-169">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="f0def-170">Wie viele dieser Anmeldeversuche waren nicht erfolgreich und für welche Konten?</span><span class="sxs-lookup"><span data-stu-id="f0def-170">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="f0def-171">Weitere Informationen zu den Berichten und den Zugriffsmöglichkeiten auf diese finden Sie unter [Azure Active Directory-Berichterstellung](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f0def-171">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="f0def-172">In diesem Schritt lernen Sie die Berichte kennen und erfahren, wie Sie sie verwenden können, um zu Planungs- und Sicherheitszwecken Informationen über Azure AD-Ereignisse und -Aktivitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0def-172">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="f0def-173">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f0def-173">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="f0def-174">Vereinfachen des Zugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="f0def-174">Simplify access for users</span></span>](identity-password-reset.md) |

