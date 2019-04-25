---
title: 'Schritt 2: Sichern Ihrer privilegierten Identitäten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie Ihre Administratorkonten für maximalen Schutz.
ms.openlocfilehash: 4b4a8d01cdf71e30139fa448813a3ff7c43855c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285158"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="78a88-103">Schritt 2: Sichern Ihrer privilegierten Identitäten</span><span class="sxs-lookup"><span data-stu-id="78a88-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="78a88-104">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="78a88-104">Protect global administrator accounts</span></span>

<span data-ttu-id="78a88-105">*Dies ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="78a88-105">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="78a88-106">In diesem Abschnitt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="78a88-106">In this step, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span> <span data-ttu-id="78a88-107">Dazu müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="78a88-107">To do this, you must:</span></span>

- <span data-ttu-id="78a88-108">Erstellen Sie dedizierte globale Administratorkonten mit sehr [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="78a88-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="78a88-109">Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, zu Benutzerkonten von IT-Personal nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78a88-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="78a88-110">Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="78a88-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="78a88-p102">Testen Sie Einstellungen für Konto oder bedingte zugriffsbasierte Multi-Factor Authentication (MFA) pro Benutzer mit einem Testbenutzerkonto, um sicherzustellen, dass MFA korrekt und vorhersehbar arbeitet. Die MFA erfordert eine sekundäre Authentifizierung, wie einen an ein Smartphone gesendeten Verifizierungscode.</span><span class="sxs-lookup"><span data-stu-id="78a88-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="78a88-p103">Konfigurieren Sie die MFA für jedes der dedizierten globalen Office 365-Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung, die in Ihrer Organisation verfügbar ist. Unter [Multi-Factor Authentication](identity-multi-factor-authentication.md#identity-mfa) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="78a88-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="78a88-p104">Verwenden Sie eine bedingte Zugriffsrichtlinie, damit MFA für globalen Administratorkonten erforderlich ist. Weitere Informationen finden Sie unter [Administratorkonten schützen](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="78a88-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="78a88-p105">Verwenden Sie eine Office 365 Cloud App Security-Richtlinie, um die Aktivität globaler Administratorkonten zu überwachen. Unter [Erhöhte Sicherheit für Office 365 konfigurieren](infoprotect-configure-increased-security-office-365.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="78a88-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Configure increased security for Office 365](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="78a88-119">Unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) finden Sie weitere Informationen zur Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="78a88-119">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="78a88-p106">Organisationen sollten reine Cloud-Identitäten verwenden, um privilegierte Konten, z. B. globale Administratoren, für Break-Glass-Szenarien in Notfällen (wie Cyberangriff) zu erstellen. Weitere Informationen finden Sie unter [Administrativen Konten für den Notfallzugriff in Azure AD verwalten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="78a88-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="78a88-122">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="78a88-122">The results of this step are:</span></span>

- <span data-ttu-id="78a88-123">Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich im neuen Satz der dedizierten Konten für globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="78a88-123">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> <span data-ttu-id="78a88-124">Verifizieren Sie dies mit dem folgenden Azure Active Directory PowerShell für Graph-Befehl:</span><span class="sxs-lookup"><span data-stu-id="78a88-124">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="78a88-125">Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="78a88-125">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="78a88-126">Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="78a88-126">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="78a88-128">Testumgebungsanleitung: Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="78a88-128">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="78a88-129">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="78a88-129">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="78a88-130">Einrichten von globalen Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="78a88-130">Set up on-demand global administrators</span></span>

<span data-ttu-id="78a88-131">*Dies ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="78a88-131">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="78a88-132">In diesem Abschnitt richten Sie Azure AD Privileged Identity Management (PIM) ein, um die Zeitspanne zu verringern, in der Ihre globalen Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind.</span><span class="sxs-lookup"><span data-stu-id="78a88-132">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span> <span data-ttu-id="78a88-133">PIM bietet bei Bedarf eine zeitnahe Zuweisung der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="78a88-133">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="78a88-p109">Ihre globalen Administratorkonten werden zu berechtigten Administratoren anstelle von dauerhaften Administratoren. Die globale Administratorrolle ist inaktiv, bis eine Person sie benötigt. Sie durchlaufen dann einen Aktivierungsprozess, bei dem die globale Administratorrolle für eine bestimmte Zeitspanne zum globalen Administratorkonto hinzugefügt wird. Wenn der Zeitraum abgelaufen ist, entfernt PIM die globale Administratorrolle vom globalen Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="78a88-p109">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="78a88-p110">PIM ist zusammen mit Azure Active Directory Premium P2 erhältlich, das in Microsoft 365 Enterprise E5 enthalten ist. Alternativ können Sie für Ihre globalen Administratorkonten einzelne Azure Active Directory Premium P2-Lizenzen erwerben.</span><span class="sxs-lookup"><span data-stu-id="78a88-p110">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="78a88-140">Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für globale Administratorkonten finden Sie unter der [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="78a88-140">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="78a88-141">Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="78a88-141">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="78a88-142">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="78a88-142">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="78a88-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="78a88-143">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="78a88-144">Konfigurieren der Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="78a88-144">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

