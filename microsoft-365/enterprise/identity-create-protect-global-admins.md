---
title: 'Schritt 1: Erstellen und Schützen Ihrer globalen Administratorkonten'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ihre globalen Administratorkonten benötigen eine spezielle Behandlung, um sie vor der Kompromittierung von Anmeldeinformationen zu schützen.
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067342"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="803ff-103">Schritt 1: Erstellen und Schützen Ihrer globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="803ff-103">Step 1: Create and protect your global admin accounts</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="803ff-105">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="803ff-105">Protect global administrator accounts</span></span>

<span data-ttu-id="803ff-106">*Dies ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="803ff-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="803ff-107">In diesem Abschnitt verhindern Sie digitale Angriffe auf Ihre Organisation, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind.</span><span class="sxs-lookup"><span data-stu-id="803ff-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="803ff-108">Dazu müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="803ff-108">To do this, you must:</span></span>

- <span data-ttu-id="803ff-109">Erstellen Sie mehr als ein dediziertes globales Administratorkonto mit [starken Kennwörtern](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password), und verwenden Sie sie nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="803ff-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="803ff-110">Führen Sie tägliche Verwaltungsaufgaben aus, indem Sie bestimmte Administratorrollen, z. B. Exchange-Administrator oder Kennwortadministrator, anderen dedizierten Konten für diese Rollen oder Benutzerkonten von IT-Personal nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="803ff-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="803ff-111">Für Ihre dedizierten globalen Administratorkonten müssen Sie außerdem Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="803ff-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="803ff-112">Testen Sie Einstellungen für Benutzerkonto oder bedingte zugriffsbasierte mehrstufige Azure-Authentifizierung (MFA) mit einem Testbenutzerkonto, um sicherzustellen, dass die MFA korrekt und vorhersehbarer funktioniert.</span><span class="sxs-lookup"><span data-stu-id="803ff-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="803ff-113">Die MFA erfordert eine sekundäre Authentifizierungsform wie etwa einen an ein Smartphone gesendeten Verifizierungscode.</span><span class="sxs-lookup"><span data-stu-id="803ff-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="803ff-114">Erstellen und aktivieren Sie eine Richtlinie für den bedingten Zugriff für Ihre globalen Administratorkonten, die MFA erfordert und die stärkste in Ihrer Organisation verfügbare Form der sekundären Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="803ff-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="803ff-115">Weitere Informationen finden Sie unter [Mehrstufige Azure-Authentifizierung](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="803ff-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="803ff-116">Näheres zu weiteren Schutzmaßnahmen finden Sie unter [Schützen Ihrer globalen Office 365-Administratorkonten](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="803ff-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="803ff-117">Notfallzugriffs-Konten für Notfälle wie etwa einen Cyberangriff sollten nur cloudbasiert sein.</span><span class="sxs-lookup"><span data-stu-id="803ff-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="803ff-118">Sie können außerdem über globale Administratorkonten (berechtigt oder permanent) verfügen, die nicht rein cloudbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="803ff-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="803ff-119">Weitere Informationen finden Sie unter [Verwalten von Administratorkonten für den Notfallzugriff in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="803ff-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="803ff-120">Die Ergebnisse dieses Abschnitts sind:</span><span class="sxs-lookup"><span data-stu-id="803ff-120">The results of this section are:</span></span>

- <span data-ttu-id="803ff-121">Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich in den dedizierten Konten für globale Administratoren.</span><span class="sxs-lookup"><span data-stu-id="803ff-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="803ff-122">Verifizieren Sie dies mit dem folgenden Azure Active Directory PowerShell für Graph-Befehl:</span><span class="sxs-lookup"><span data-stu-id="803ff-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="803ff-123">Alle anderen Benutzerkonten für die Verwaltung Ihrer Abonnementdienste verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="803ff-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="803ff-124">Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="803ff-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="803ff-126">Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="803ff-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="803ff-127">Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-global-admin) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="803ff-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="803ff-128">Einrichten von Administratoren bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="803ff-128">Set up on-demand administrators</span></span>

<span data-ttu-id="803ff-129">*Dies ist optional und gilt nur für die Version E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="803ff-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="803ff-130">In diesem Abschnitt richten Sie Azure AD Privileged Identity Management (PIM) ein, um die Zeitspanne zu verringern, in der Ihre Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind.</span><span class="sxs-lookup"><span data-stu-id="803ff-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="803ff-131">PIM bietet bei Bedarf eine zeitnahe Zuweisung von Administratorrollen.</span><span class="sxs-lookup"><span data-stu-id="803ff-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="803ff-132">Statt dass Ihre Administratorkonten permanente Administratoren sind, werden sie zu berechtigten Administratoren.</span><span class="sxs-lookup"><span data-stu-id="803ff-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="803ff-133">Die Administratorrolle ist so lange inaktiv, bis sie von jemandem benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="803ff-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="803ff-134">Dann wird ein Aktivierungsvorgang ausgeführt, um dem Administratorkonto die Administratorrolle für einen bestimmten Zeitraum hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="803ff-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="803ff-135">Wenn die Zeit abgelaufen ist, entfernt PIM die Administratorrolle aus dem Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="803ff-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="803ff-136">PIM ist im Lieferumfang von Azure Active Directory Premium P2 verfügbar, das im Lieferumfang von Microsoft 365 E5 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="803ff-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="803ff-137">Alternativ hierzu können Sie einzelne Azure Active Directory Premium P2-Lizenzen für Ihre Administratorkonten erwerben.</span><span class="sxs-lookup"><span data-stu-id="803ff-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="803ff-138">Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für Administratorkonten finden Sie unter [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="803ff-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="803ff-139">Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="803ff-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="803ff-140">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="803ff-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="803ff-141">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="803ff-141">Privileged access management</span></span>

<span data-ttu-id="803ff-p109">Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Office 365-Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Office 365-Mandanten benötigt. </span><span class="sxs-lookup"><span data-stu-id="803ff-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="803ff-p110">In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Office 365-Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Office 365-Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Office 365-Organisation zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="803ff-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="803ff-147">Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="803ff-147">Creating an approver's group</span></span>
- <span data-ttu-id="803ff-148">Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="803ff-148">Enabling privileged access</span></span>
- <span data-ttu-id="803ff-149">Erstellen von Genehmigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="803ff-149">Creating approval policies</span></span>

<span data-ttu-id="803ff-p111">Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="803ff-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="803ff-153">Weitere Informationen zum Aktivieren von Privileged Access Management in Office 365 finden Sie im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="803ff-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="803ff-154">Weitere Informationen finden Sie im Thema [Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="803ff-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="803ff-156">Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Privileged Access Management](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="803ff-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="803ff-157">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pam) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="803ff-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="803ff-158">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="803ff-158">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="803ff-160">Schützen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="803ff-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

