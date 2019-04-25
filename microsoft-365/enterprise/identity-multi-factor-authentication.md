---
title: 'Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der mehrstufigen Authentifizierung für Benutzerkonten.
ms.openlocfilehash: 44d878a347e7b01263f9ba3a82f6443f5710dc43
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285466"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="3de25-103">Schritt 4: Konfigurieren der sicheren Benutzerauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="3de25-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="3de25-104">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3de25-104">Set up multi-factor authentication.</span></span>

<span data-ttu-id="3de25-105">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3de25-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3de25-p101">In diesem Schritt richten Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzuzufügen. MFA erfordert eine zusätzliche Überprüfungsmethode, nachdem Benutzer ihr Kennwort richtig eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem mit Kennwörtern ist, dass sie häufig von einem Angreifer leicht zu erraten sind oder unbewusst für nicht vertrauenswürdige Parteien freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3de25-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="3de25-110">Die zweite Sicherheitsebene bei MFA kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="3de25-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="3de25-111">Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="3de25-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="3de25-112">Ein biometrisches Attribut, z. B. ein Fingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="3de25-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="3de25-p102">Sie aktivieren MFA und konfigurieren die sekundäre Authentifizierungsmethode auf Benutzerkontobasis. Teilen Sie den Benutzern unbedingt mit, dass MFA aktiviert ist, damit sie die Anforderungen, z. B. obligatorische Verwendung eines Smartphones zum Anmelden, verstehen und sich erfolgreich anmelden können.</span><span class="sxs-lookup"><span data-stu-id="3de25-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="3de25-115">Weitere Informationen finden Sie unter [Planen der mehrstufigen Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="3de25-115">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="3de25-p103">In einigen Clientanwendungen, z. B. Microsoft Office 2010 oder früher und Apple Mail, können Sie MFA nicht verwenden. Um diese Apps zu nutzen, müssen Sie „App-Kennwörter“ anstelle Ihres herkömmlichen Kennworts verwenden. Das App-Kennwort ermöglicht der App, MFA zu umgehen und die Arbeit fortzusetzen. Weitere Informationen zu App-Kennwörtern finden Sie unter [Erstellen eines App-Kennworts für Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="3de25-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3de25-121">Testumgebungsanleitung: Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3de25-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3de25-122">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-mfa) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="3de25-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="3de25-123">Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="3de25-123">Protect against credential compromise</span></span>

<span data-ttu-id="3de25-124">*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3de25-124">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3de25-125">In diesem Abschnitt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3de25-125">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span> <span data-ttu-id="3de25-126">Azure AD Identity Protection bietet eine Reihe von Methoden, mit denen verhindert werden kann, dass sich ein Angreifer seitwärts durch Konten und Gruppen und folglich Ihre wertvollsten Daten bewegt.</span><span class="sxs-lookup"><span data-stu-id="3de25-126">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="3de25-127">Mit Azure AD Identity Protection können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3de25-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="3de25-128">Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3de25-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="3de25-p105">Azure Active Directory verwendet maschinelles Lernen, um Anomalien und verdächtige Aktivitäten automatisch zu erkennen, z. B. Anmeldungen und Aktivitäten nach der Anmeldung. Anhand dieser Daten generiert Identity Protection Berichte und Warnungen, mit denen Sie die Probleme auswerten und entsprechende Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="3de25-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="3de25-131">Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="3de25-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="3de25-p106">Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Mit diesen Richtlinien können Sie neben anderen von Azure Active Directory and Enterprise Mobility + Security (EMS) bereitgestellten bedingten Zugriffssteuerungen entweder den Zugriff automatisch blockieren oder Korrekturmaßnahmen ergreifen, z. B. Kennwörter zurücksetzen oder mehrstufige Authentifizierung für nachfolgende Anmeldungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="3de25-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="3de25-134">Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="3de25-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="3de25-p107">Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3de25-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="3de25-137">Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="3de25-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="3de25-138">Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="3de25-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="3de25-139">In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3de25-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="3de25-140">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="3de25-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="3de25-141">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="3de25-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="3de25-142">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="3de25-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3de25-144">Testumgebungsanleitung: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3de25-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3de25-145">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="3de25-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="3de25-146">Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="3de25-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="3de25-147">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3de25-147">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3de25-p108">In diesem Schritt überprüfen Sie Überwachungsprotokolle und Anmeldeaktivitäten mithilfe von Azure AD-Berichten. Es stehen zwei Arten von Berichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3de25-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="3de25-p109">Der **Aktivitätsbericht „Überwachungsprotokolle“** verzeichnet den Verlauf jeder in Ihrem Azure AD-Mandanten ausgeführten Aufgabe. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="3de25-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="3de25-152">Wer hat eine Person zu einer Administratorengruppe hinzugefügt?</span><span class="sxs-lookup"><span data-stu-id="3de25-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="3de25-153">Welche Benutzer melden sich bei einer bestimmten App an?</span><span class="sxs-lookup"><span data-stu-id="3de25-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="3de25-154">Wie viele Kennwortzurücksetzungen werden ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="3de25-154">How many password resets are happening?</span></span>

<span data-ttu-id="3de25-p110">Der **Aktivitätsbericht „Anmeldungen“** verzeichnet, wer die im Überwachungsprotokollbericht gemeldeten Aufgaben ausgeführt hat. In diesem Bericht finden Sie Antworten auf Fragen wie:</span><span class="sxs-lookup"><span data-stu-id="3de25-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="3de25-157">Welches Anmeldemuster gilt für einen bestimmten untersuchten Benutzer?</span><span class="sxs-lookup"><span data-stu-id="3de25-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="3de25-158">Wie groß ist das Volumen von Anmeldungen über einen Tag, eine Woche oder einen Monat?</span><span class="sxs-lookup"><span data-stu-id="3de25-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="3de25-159">Wie viele dieser Anmeldeversuche waren nicht erfolgreich und für welche Konten?</span><span class="sxs-lookup"><span data-stu-id="3de25-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="3de25-160">Weitere Informationen zu den Berichten und den Zugriffsmöglichkeiten auf diese finden Sie unter [Azure Active Directory-Berichterstellung](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3de25-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="3de25-161">In diesem Schritt lernen Sie die Berichte kennen und erfahren, wie Sie sie verwenden können, um zu Planungs- und Sicherheitszwecken Informationen über Azure AD-Ereignisse und -Aktivitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3de25-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="3de25-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3de25-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="3de25-163">Vereinfachen des Zugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="3de25-163">Simplify access for users</span></span>](identity-password-reset.md) |

