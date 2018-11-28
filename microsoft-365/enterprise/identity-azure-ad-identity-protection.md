---
title: 'Schritt 15: Schutz vor Kompromittierung von Anmeldeinformationen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Grundlegendes zu und Konfiguration von Azure AD Identity Protection.
ms.openlocfilehash: ef6dddc72c6b94a2e83d76af43ae3fe1ef80a91c
ms.sourcegitcommit: f3bf836df0f915fa05422fbc7ea3882c1ea4bac7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "20329127"
---
# <a name="step-15-protect-against-credential-compromise"></a><span data-ttu-id="da26a-103">Schritt 15: Schutz vor Kompromittierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="da26a-103">Step 15: Protect against credential compromise</span></span>

<span data-ttu-id="da26a-104">*Dieser Schritt ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="da26a-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="da26a-p101">In Schritt 15 erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten. Azure AD Identity Protection bietet eine Reihe von Methoden, mit denen verhindert werden kann, dass sich ein Angreifer seitwärts durch Konten und Gruppen und folglich Ihre wertvollsten Daten bewegt.</span><span class="sxs-lookup"><span data-stu-id="da26a-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="da26a-107">Mit Azure AD Identity Protection können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da26a-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="da26a-108">Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="da26a-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="da26a-p102">Azure Active Directory verwendet maschinelles Lernen, um Anomalien und verdächtige Aktivitäten automatisch zu erkennen, z. B. Anmeldungen und Aktivitäten nach der Anmeldung. Anhand dieser Daten generiert Identity Protection Berichte und Warnungen, mit denen Sie die Probleme auswerten und entsprechende Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="da26a-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="da26a-111">Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="da26a-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="da26a-p103">Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Mit diesen Richtlinien können Sie neben anderen von Azure Active Directory and Enterprise Mobility + Security (EMS) bereitgestellten bedingten Zugriffssteuerungen entweder den Zugriff automatisch blockieren oder Korrekturmaßnahmen ergreifen, z. B. Kennwörter zurücksetzen oder mehrstufige Authentifizierung für nachfolgende Anmeldungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="da26a-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="da26a-114">Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="da26a-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="da26a-p104">Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="da26a-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="da26a-117">Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="da26a-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="da26a-118">Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="da26a-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="da26a-119">In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da26a-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="da26a-120">Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen</span><span class="sxs-lookup"><span data-stu-id="da26a-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="da26a-121">Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="da26a-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="da26a-122">Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle</span><span class="sxs-lookup"><span data-stu-id="da26a-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="da26a-124">Testumgebungsanleitung: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="da26a-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="da26a-125">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step15) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="da26a-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step15) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="da26a-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="da26a-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step16.png)| [<span data-ttu-id="da26a-127">Bereitstellen eines sicheren Remotezugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="da26a-127">Provide secure remote access to users</span></span>](identity-azure-ad-application-proxy.md) |


