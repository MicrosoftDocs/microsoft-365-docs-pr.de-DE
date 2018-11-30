---
title: 'Schritt 2: Schützen von globalen Administratorkonten'
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
description: Verstehen und konfigurieren Sie Ihre Administratorkonten für maximalen Schutz.
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868196"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="4c3ef-103">Schritt 2: Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="4c3ef-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="4c3ef-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4c3ef-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4c3ef-p101">In diesem Schritt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. Dazu müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="4c3ef-107">Erstellen Sie dedizierte globale Administratorkonten mit sehr [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="4c3ef-108">Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, zu Benutzerkonten von IT-Personal nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="4c3ef-109">Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="4c3ef-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="4c3ef-p102">Testen Sie Einstellungen für Konto oder bedingte zugriffsbasierte Multi-Factor Authentication (MFA) pro Benutzer mit einem Testbenutzerkonto, um sicherzustellen, dass MFA korrekt und vorhersehbar arbeitet. Die MFA erfordert eine sekundäre Authentifizierung, wie einen an ein Smartphone gesendeten Verifizierungscode.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="4c3ef-p103">Konfigurieren Sie die MFA für jedes der dedizierten globalen Office 365-Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung, die in Ihrer Organisation verfügbar ist. Unter [Multi-Factor Authentication](identity-multi-factor-authentication.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="4c3ef-p104">Verwenden Sie eine bedingte Zugriffsrichtlinie, damit MFA für globalen Administratorkonten erforderlich ist. Weitere Informationen finden Sie unter [Administratorkonten schützen](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="4c3ef-p105">Verwenden Sie eine Office 365 Cloud App Security-Richtlinie, um die Aktivität globaler Administratorkonten zu überwachen. Unter [Erhöhte Sicherheit für Office 365 konfigurieren](infoprotect-configure-increased-security-office-365.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="4c3ef-118">Unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) finden Sie weitere Informationen zur Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="4c3ef-p106">Organisationen sollten reine Cloud-Identitäten verwenden, um privilegierte Konten, z. B. globale Administratoren, für Break-Glass-Szenarien in Notfällen (wie Cyberangriff) zu erstellen. Weitere Informationen finden Sie unter [Administrativen Konten für den Notfallzugriff in Azure AD verwalten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="4c3ef-121">Die Ergebnisse dieses Schritts sind:</span><span class="sxs-lookup"><span data-stu-id="4c3ef-121">The results of this step are:</span></span>

- <span data-ttu-id="4c3ef-p107">Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Rolle des globalen Administrators verfügen, sind der neue Satz der dedizierten globalen Administratorkonten. Überprüfen Sie dies mit dem folgenden Windows Azure AD V2 PowerShell-Befehl:</span><span class="sxs-lookup"><span data-stu-id="4c3ef-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="4c3ef-124">Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="4c3ef-125">Anweisungen zum Installieren des Azure AD V2 PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c3ef-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4c3ef-127">Testumgebungsanleitung: Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="4c3ef-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4c3ef-128">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="4c3ef-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c3ef-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4c3ef-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="4c3ef-130">Einrichten von globalen Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="4c3ef-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

