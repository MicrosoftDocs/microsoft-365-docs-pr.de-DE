---
title: 'Schritt 7: Einrichten der mehrstufigen Authentifizierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren der mehrstufigen Authentifizierung für Benutzerkonten.
ms.openlocfilehash: 5cfa3d68e22eb8a7e11324d361a9122b3e89680d
ms.sourcegitcommit: f3bf836df0f915fa05422fbc7ea3882c1ea4bac7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "20329107"
---
# <a name="step-7-set-up-multi-factor-authentication"></a><span data-ttu-id="194e2-103">Schritt 7: Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="194e2-103">Step 7: Set up multi-factor authentication</span></span>

<span data-ttu-id="194e2-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="194e2-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="194e2-p101">In Schritt 7 richten Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) ein, um eine zweite Sicherheitsebene für Benutzeranmeldungen und Transaktionen hinzuzufügen. MFA erfordert eine zusätzliche Überprüfungsmethode, nachdem Benutzer ihr Kennwort richtig eingegeben haben. Ohne MFA ist das Kennwort die einzige Überprüfungsmethode. Das Problem mit Kennwörtern ist, dass sie häufig von einem Angreifer leicht zu erraten sind oder unbewusst für nicht vertrauenswürdige Parteien freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="194e2-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="194e2-109">Die zweite Sicherheitsebene bei MFA kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="194e2-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="194e2-110">Ein persönliches und vertrauenswürdiges Gerät, das nicht leicht gefälscht oder dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="194e2-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="194e2-111">Ein biometrisches Attribut, z. B. ein Fingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="194e2-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="194e2-p102">Sie aktivieren MFA und konfigurieren die sekundäre Authentifizierungsmethode auf Benutzerkontobasis. Teilen Sie den Benutzern unbedingt mit, dass MFA aktiviert ist, damit sie die Anforderungen (z. B. obligatorische Verwendung eines Smartphones zum Anmelden) verstehen und sich erfolgreich anmelden können.</span><span class="sxs-lookup"><span data-stu-id="194e2-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="194e2-114">Weitere Informationen finden Sie unter [Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span><span class="sxs-lookup"><span data-stu-id="194e2-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="194e2-115">Zum Konfigurieren der mehrstufigen Authentifizierung folgen Sie den Anweisungen unter [Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span><span class="sxs-lookup"><span data-stu-id="194e2-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

>[!Note]
><span data-ttu-id="194e2-p103">Sie können auch MFA mit bedingten Zugriffsrichtlinien anfordern. Sie können beispielsweise eine Richtlinie konfigurieren, die MFA erfordert, wenn die Authentifizierung als mittelmäßig oder hoch riskant eingestuft wird. Weitere Informationen finden Sie unter [Schritt 2: Konfigurieren von Richtlinieneinstellungen für bedingten Zugriff](infoprotect-configure-conditional-access-policy-settings.md) in der Phase des Schutzes von Daten.</span><span class="sxs-lookup"><span data-stu-id="194e2-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](infoprotect-configure-conditional-access-policy-settings.md) in the Information Protection phase.</span></span>
>

>[!Note]
><span data-ttu-id="194e2-p104">In einigen Clientanwendungen, z. B. Microsoft Office 2010 oder früher und Apple Mail, können Sie MFA nicht verwenden. Um diese Apps zu nutzen, müssen Sie „App-Kennwörter“ anstelle Ihres herkömmlichen Kennworts verwenden. Das App-Kennwort ermöglicht der App, MFA zu umgehen und die Arbeit fortzusetzen. Weitere Informationen zu App-Kennwörtern finden Sie unter [Erstellen eines App-Kennworts für Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="194e2-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="194e2-124">Testumgebungsanleitung: Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="194e2-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="194e2-125">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step7) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="194e2-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step7) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="194e2-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="194e2-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="194e2-127">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="194e2-127">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

