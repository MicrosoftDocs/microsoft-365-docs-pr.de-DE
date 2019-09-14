---
title: 'Schritt 2: Sichern Ihrer privilegierten Identitäten'
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
description: Verstehen und konfigurieren Sie Ihre Administratorkonten für maximalen Schutz.
ms.openlocfilehash: b9c645d597dfeb2bdc42e2b0b7615252dc1f5ecb
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981906"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="4124c-103">Schritt 2: Sichern Ihrer privilegierten Identitäten</span><span class="sxs-lookup"><span data-stu-id="4124c-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="4124c-104">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="4124c-104">Protect global administrator accounts</span></span>

<span data-ttu-id="4124c-105">*Dies ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4124c-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4124c-106">In diesem Abschnitt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="4124c-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="4124c-107">Dazu müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="4124c-107">To do this, you must:</span></span>

- <span data-ttu-id="4124c-108">Erstellen Sie dedizierte globale Administratorkonten mit sehr [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4124c-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="4124c-109">Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, zu Benutzerkonten von IT-Personal nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4124c-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="4124c-110">Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="4124c-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="4124c-p102">Testen Sie Einstellungen für Konto oder bedingte zugriffsbasierte Multi-Factor Authentication (MFA) pro Benutzer mit einem Testbenutzerkonto, um sicherzustellen, dass MFA korrekt und vorhersehbar arbeitet. Die MFA erfordert eine sekundäre Authentifizierung, wie einen an ein Smartphone gesendeten Verifizierungscode.</span><span class="sxs-lookup"><span data-stu-id="4124c-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="4124c-113">Aktivieren Sie die Richtlinie für den bedingten Zugriff **Basisplan-Richtlinie: MFA für Administratoren erforderlich** für Ihre globalen Administratorkonten, und verwenden Sie die stärkste in Ihrer Organisation verfügbare Form der sekundären Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4124c-113">Enable the **Baseline policy: Require MFA for admins** conditional access policy for your global administrator accounts and use the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="4124c-114">Weitere Informationen finden Sie unter [Multi-Factor Authentication (mehrstufige Authentifizierung)](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="4124c-114">See [Multi-factor authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="4124c-115">Weitere Schutzmaßnahmen finden Sie unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="4124c-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="4124c-p104">Organisationen sollten reine Cloud-Identitäten verwenden, um privilegierte Konten, z. B. globale Administratoren, für Break-Glass-Szenarien in Notfällen (wie Cyberangriff) zu erstellen. Weitere Informationen finden Sie unter [Administrativen Konten für den Notfallzugriff in Azure AD verwalten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="4124c-p104">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="4124c-118">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="4124c-118">The results of this section are:</span></span>

- <span data-ttu-id="4124c-119">Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich in den dedizierten Konten für globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="4124c-119">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="4124c-120">Verifizieren Sie dies mit dem folgenden Azure Active Directory PowerShell für Graph-Befehl:</span><span class="sxs-lookup"><span data-stu-id="4124c-120">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="4124c-121">Alle anderen Benutzerkonten für die Verwaltung Ihrer Abonnementdienste verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="4124c-121">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="4124c-122">Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="4124c-122">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="4124c-124">Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4124c-124">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="4124c-125">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="4124c-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="4124c-126">Einrichten von globalen Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="4124c-126">Set up on-demand global administrators</span></span>

<span data-ttu-id="4124c-127">*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4124c-127">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4124c-128">In diesem Abschnitt richten Sie Azure AD Privileged Identity Management (PIM) ein, um die Zeitspanne zu verringern, in der Ihre globalen Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind.</span><span class="sxs-lookup"><span data-stu-id="4124c-128">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="4124c-129">PIM bietet bei Bedarf eine zeitnahe Zuweisung der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="4124c-129">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="4124c-p107">Ihre globalen Administratorkonten werden zu berechtigten Administratoren anstelle von dauerhaften Administratoren. Die globale Administratorrolle ist inaktiv, bis eine Person sie benötigt. Sie durchlaufen dann einen Aktivierungsprozess, bei dem die globale Administratorrolle für eine bestimmte Zeitspanne zum globalen Administratorkonto hinzugefügt wird. Wenn der Zeitraum abgelaufen ist, entfernt PIM die globale Administratorrolle vom globalen Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="4124c-p107">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="4124c-p108">PIM ist zusammen mit Azure Active Directory Premium P2 erhältlich, das in Microsoft 365 Enterprise E5 enthalten ist. Alternativ können Sie für Ihre globalen Administratorkonten einzelne Azure Active Directory Premium P2-Lizenzen erwerben.</span><span class="sxs-lookup"><span data-stu-id="4124c-p108">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="4124c-136">Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für globale Administratorkonten finden Sie unter der [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="4124c-136">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="4124c-137">Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="4124c-137">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="4124c-138">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="4124c-138">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="4124c-139">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4124c-139">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="4124c-140">Konfigurieren der Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="4124c-140">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

