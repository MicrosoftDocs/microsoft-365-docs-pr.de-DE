---
title: Microsoft 365 Enterprise-Foundation-Infrastruktur für Nicht-Unternehmen
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Durchlaufen Sie die vereinfachten Phasen der Foundation-Infrastruktur für Microsoft 365 Enterprise für Nicht-Unternehmen.
ms.openlocfilehash: 8e2c254bf352baa14ff62dad500e5cdfa0af4563
ms.sourcegitcommit: 639607bbf02bdedd3fa5cd7b0984b422fe6c874e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "35624633"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="6df72-103">Microsoft 365 Enterprise-Foundation-Infrastruktur für Nicht-Unternehmen</span><span class="sxs-lookup"><span data-stu-id="6df72-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="6df72-104">Nicht-Unternehmen können auch Microsoft 365 Enterprise einsetzen und den Geschäftswert einer integrierten und sicheren Infrastruktur erkennen, die Teamarbeit ermöglicht und Kreativität freisetzt.</span><span class="sxs-lookup"><span data-stu-id="6df72-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="6df72-105">Ein Nicht-Unternehmen hat in der Regel:</span><span class="sxs-lookup"><span data-stu-id="6df72-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="6df72-106">Eine kleine oder gar keine lokale IT-Infrastruktur, wie E-Mail- und Dateiserver und eine Active Directory Domain Services (AD DS)-Domäne.</span><span class="sxs-lookup"><span data-stu-id="6df72-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="6df72-107">Ein kleines IT-Team, von dem die meisten Informatiker sind, und nicht Spezialisten für eine bestimmte Technologie oder Arbeitsbelastung wie Vernetzung oder E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="6df72-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="6df72-108">Für Ihr kleineres Nicht-Unternehmen bietet Microsoft das [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="6df72-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="6df72-109">Es gibt jedoch Gründe, warum Sie Microsoft 365 Enterprise benötigen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="6df72-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="6df72-110">Ihre Organisation benötigt oder wird mehr als 300 Microsoft 365-Lizenzen benötigen, was das Maximum für Microsoft 365 Business darstellt.</span><span class="sxs-lookup"><span data-stu-id="6df72-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="6df72-111">Ihre Organisation benötigt die fortschrittliche Produktivität, Sprach-, Sicherheits- und Analysefunktionen, die mit Microsoft 365 Business nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="6df72-112">Dieser Artikel führt Sie durch eine vereinfachte Bereitstellung der für Ihr Nicht-Unternehmen geeigneten Foundation-Infrastruktur von Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6df72-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="6df72-113">Erstens: Einrichten Ihres Abonnements</span><span class="sxs-lookup"><span data-stu-id="6df72-113">First, set up your subscription</span></span>

<span data-ttu-id="6df72-114">Sie müssen die DNS-Domänen (Domain Name System) für Ihr Abonnement einrichten.</span><span class="sxs-lookup"><span data-stu-id="6df72-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="6df72-115">Wenn Sie bereits ein Office 365-Abonnement haben, sollte dies geschehen sein.</span><span class="sxs-lookup"><span data-stu-id="6df72-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="6df72-116">Wenn dies nicht der Fall ist, folgen Sie den Anweisungen unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="6df72-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="6df72-117">Als nächstes müssen Sie zusätzliche Sicherheit für Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="6df72-118">Folgen Sie den Anweisungen unter [Konfigurieren der erhöhten Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="6df72-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="6df72-119">Phase 1: Vernetzung</span><span class="sxs-lookup"><span data-stu-id="6df72-119">Phase 1: Networking</span></span>

<span data-ttu-id="6df72-120">Nicht-Unternehmen verfügen in der Regel über lokale Internetverbindungen in jedem Büro und verwenden keine Proxy-Server, Firewalls oder Paket-Inspektionsgeräte.</span><span class="sxs-lookup"><span data-stu-id="6df72-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="6df72-121">Der Internetdienstanbieter (Internet Service Provider, ISP), der die einzelnen Büros versorgt, verfügt über einen regional lokalen DNS-Server, so dass der Datenverkehr an den Microsoft 365-Netzwerkstandort geleitet wird, die Ihren Büros und deren lokalen Benutzern am nächsten sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="6df72-122">Daher müssen Sie nur bei Ihrem ISP überprüfen, ob die Verbindung an jedem Ihrer Standorte Folgendes tut:</span><span class="sxs-lookup"><span data-stu-id="6df72-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="6df72-123">Einen regional lokalen DNS-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="6df72-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="6df72-124">Ist für aktuelle und zukünftige Anforderungen geeignet, da Ihre Benutzer mehr Microsoft 365-Clouddienste nutzen.</span><span class="sxs-lookup"><span data-stu-id="6df72-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="6df72-125">Wenn Sie Proxyserver, Firewalls oder Paket-Inspektionsgeräte verwenden, finden Sie weitere Informationen unter [Netzwerkinfrastruktur für Microsoft 365 Enterprise](networking-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="6df72-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-126">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-126">Your configuration so far</span></span>

<span data-ttu-id="6df72-127">Hier ist eine visuelle Zusammenfassung, in der das Element "Phase 1" hervorgehoben ist.</span><span class="sxs-lookup"><span data-stu-id="6df72-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="6df72-128">**Ihre Organisation** kann aus mehreren Büros bestehen, von denen jedes eine lokale Internetverbindung mit einem ISP hat, der einen regional lokalen DNS-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="6df72-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="6df72-129">Über den ISP können Benutzer in jedem Büro den nächstgelegenen Microsoft 365-Netzwerkstandort und die Ressourcen Ihres Microsoft 365-Abonnements erreichen.</span><span class="sxs-lookup"><span data-stu-id="6df72-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="6df72-130">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="6df72-130">Phase 2: Identity</span></span>

<span data-ttu-id="6df72-131">Jeder Mitarbeiter Ihrer Organisation muss sich anmelden können, was ein Benutzerkonto im Azure Active Directory (Azure AD)-Mandanten Ihres Microsoft 365 Enterprise-Abonnements erfordert.</span><span class="sxs-lookup"><span data-stu-id="6df72-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="6df72-132">Gruppen werden dann verwendet, um Benutzerkonten und andere Gruppen zu enthalten, um zu kommunizieren oder Zugang zu berechtigten Ressourcen zu erhalten, wie beispielsweise einer SharePoint Online-Website oder einem Team.</span><span class="sxs-lookup"><span data-stu-id="6df72-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="6df72-133">Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="6df72-133">Administrator accounts</span></span>

<span data-ttu-id="6df72-134">Schützen Sie Ihre globalen Administrator-Benutzerkonten, indem Sie sehr sichere Kennwörter und Multi-Faktor-Authentifizierung (MFA) erfordern.</span><span class="sxs-lookup"><span data-stu-id="6df72-134">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="6df72-135">Weitere Informationen finden Sie unter [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="6df72-135">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="6df72-136">Wenn Ihre Organisation hohe Sicherheitsanforderungen hat und Sie über Microsoft 365 Enterprise E5 verfügen, verwenden Sie Azure AD Privileged Identity Management, um den Just-in-time-Administratorzugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6df72-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="6df72-137">Weitere Informationen finden Sie unter [Einrichten von globalen Administratoren bei Bedarf](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators).</span><span class="sxs-lookup"><span data-stu-id="6df72-137">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="6df72-138">Empfehlungen für Gruppen</span><span class="sxs-lookup"><span data-stu-id="6df72-138">Recommendations for groups</span></span>

<span data-ttu-id="6df72-139">Wenn Sie eine lokale AD DS-Domäne haben, verwenden Sie diese Gruppen in Microsoft 365 Enterprise weiterhin als Gruppen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6df72-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="6df72-140">Wenn Sie keine lokale AD DS-Domäne haben, erstellen Sie Sicherheitsgruppen in Azure AD mit diesen Sicherheitsebenen.</span><span class="sxs-lookup"><span data-stu-id="6df72-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="6df72-141">Sicherheitsstufe</span><span class="sxs-lookup"><span data-stu-id="6df72-141">Security level</span></span> | <span data-ttu-id="6df72-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6df72-142">Description</span></span> | <span data-ttu-id="6df72-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6df72-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="6df72-144">Basisplan</span><span class="sxs-lookup"><span data-stu-id="6df72-144">Baseline</span></span> | <span data-ttu-id="6df72-145">Dies ist ein minimaler und voreingestellter Standard für den Schutz von Daten und den Identitäten und Geräten, die auf Ihre Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6df72-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="6df72-146">Dies sind in der Regel die meisten Daten Ihrer Organisation, die von den meisten Ihrer Benutzer verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="6df72-147">Gruppen für wichtige Arbeitskräfte, wie Vertrieb, Marketing, Kundendienst, Verwaltung und Produktion.</span><span class="sxs-lookup"><span data-stu-id="6df72-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="6df72-148">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="6df72-148">Sensitive</span></span> | <span data-ttu-id="6df72-149">Dies ist ein zusätzlicher Schutz für eine Teilmenge Ihrer Daten, die über den Basisplan hinaus geschützt werden muss.</span><span class="sxs-lookup"><span data-stu-id="6df72-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="6df72-150">Diese Gruppen enthalten Benutzer, die vertrauliche Daten verwenden und erstellen, die spezifisch für Abteilungen und Projekte sind, die nicht für alle zugänglich sein sollen.</span><span class="sxs-lookup"><span data-stu-id="6df72-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="6df72-151">Produkt- oder Marketingteams, die zukünftige Produkte entwickeln</span><span class="sxs-lookup"><span data-stu-id="6df72-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="6df72-152">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="6df72-152">Highly regulated</span></span> | <span data-ttu-id="6df72-153">Dies ist die höchste Schutzstufe für in der Regel eine kleine Datenmenge, die hochgradig klassifiziert ist, als geistiges Eigentum oder Geschäftsgeheimnisse gilt oder Daten, die den Sicherheitsvorschriften entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="6df72-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="6df72-154">Teams in Forschungs-, Rechts- und Finanzabteilungen oder Teams, die Kunden- oder Partnerdaten speichern oder nutzen.</span><span class="sxs-lookup"><span data-stu-id="6df72-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="6df72-155">Hybrididentität</span><span class="sxs-lookup"><span data-stu-id="6df72-155">Hybrid identity</span></span>

<span data-ttu-id="6df72-156">Wenn Sie über eine lokale AD DS-Domäne verfügen, müssen Sie die Gruppe der Benutzerkonten, Gruppen und Kontakte Ihrer Domäne mit dem Azure AD-Mandanten Ihres Microsoft 365 Enterprise-Abonnements synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="6df72-157">Für Ihr Nicht-Unternehmen konfigurieren Sie Azure AD Connect auf einem Server mit Kennwort-Hash-Synchronisierung (Password Hash Synchronization, PHS).</span><span class="sxs-lookup"><span data-stu-id="6df72-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="6df72-158">Weitere Informationen finden Sie unter [Synchronisieren von Identitäten](identity-azure-ad-connect.md).</span><span class="sxs-lookup"><span data-stu-id="6df72-158">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="6df72-159">Mehr Sicherheit für den Benutzerzugriff mit Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="6df72-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="6df72-160">Azure AD bewertet die Bedingungen für die Anmeldung von Benutzern und kann Richtlinien für den bedingten Zugriff verwenden, um den Zugang zu gewähren oder zu verweigern sowie weitere Aktionen ausführen, die zum Abschließen der Anmeldung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="6df72-161">Wenn Azure AD beispielsweise feststellt, dass die Anmeldung unter mittleren oder hohen Risikobedingungen erfolgt, kann es erforderlich sein, dass der Benutzer eine MFA durchführt, um die Anmeldung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6df72-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="6df72-162">Sie wenden Richtlinien für den bedingten Zugriff auf Benutzerkonten oder Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="6df72-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="6df72-163">Um eine einfachere Zuordnung von Richtlinien für den bedingten Zugriff zu erleichtern, erstellen Sie diese Azure AD-Sicherheitsgruppen in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="6df72-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="6df72-164">BASISPLAN</span><span class="sxs-lookup"><span data-stu-id="6df72-164">Baseline</span></span>

  <span data-ttu-id="6df72-165">Enthält die Gruppen oder Benutzerkonten für Benutzer mit Zugriff auf Basisplandaten.</span><span class="sxs-lookup"><span data-stu-id="6df72-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="6df72-166">VERTRAULICH</span><span class="sxs-lookup"><span data-stu-id="6df72-166">Sensitive</span></span>

  <span data-ttu-id="6df72-167">Enthält die Gruppen oder Benutzerkonten für Benutzer mit Zugriff auf vertrauliche Daten.</span><span class="sxs-lookup"><span data-stu-id="6df72-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="6df72-168">STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="6df72-169">Enthält die Gruppen oder Benutzerkonten für Benutzer mit Zugriff auf streng geregelte Daten.</span><span class="sxs-lookup"><span data-stu-id="6df72-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="6df72-170">BEDINGTEN ZUGRIFF AUSSCHLIEßEN</span><span class="sxs-lookup"><span data-stu-id="6df72-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="6df72-171">Eine leere Gruppe, mit der Sie einen Benutzer vorübergehend von den Richtlinien für den bedingten Zugriff ausschließen können.</span><span class="sxs-lookup"><span data-stu-id="6df72-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="6df72-172">Hier ist die Liste der Richtlinien für den bedingten Zugriff von Azure AD, die aktiviert oder erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6df72-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="6df72-173">Azure AD-Richtlinie für den bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="6df72-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="6df72-174">Gruppen, auf die Sie angewendet wird</span><span class="sxs-lookup"><span data-stu-id="6df72-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="6df72-175">Basisplan-Richtlinie: MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="6df72-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="6df72-176">Diese Richtlinie gilt für Administratorrollen, daher müssen keine Gruppen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="6df72-177">Diese Richtlinie muss nur aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="6df72-178">Alle nachfolgenden Richtlinien müssen erstellt und aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="6df72-179">Sperrt Clients, die moderne Authentifizierung nicht unterstützen</span><span class="sxs-lookup"><span data-stu-id="6df72-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="6df72-180">Wählen Sie in den Richtlinieneinstellungen "alle Benutzer" aus.</span><span class="sxs-lookup"><span data-stu-id="6df72-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="6df72-181">Eine MFA ist erforderlich, wenn das Anmelde-Risiko mittel oder hoch ist (erfordert Microsoft 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="6df72-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="6df72-182">BASISPLAN</span><span class="sxs-lookup"><span data-stu-id="6df72-182">Baseline</span></span> |
| <span data-ttu-id="6df72-183">Eine MFA ist erforderlich, wenn das Anmelde-Risiko niedrig, mittel oder hoch ist (erfordert Microsoft 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="6df72-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="6df72-184">VERTRAULICH</span><span class="sxs-lookup"><span data-stu-id="6df72-184">Sensitive</span></span> |
| <span data-ttu-id="6df72-185">Eine MFA ist immer erforderlich</span><span class="sxs-lookup"><span data-stu-id="6df72-185">Always require MFA</span></span> | <span data-ttu-id="6df72-186">STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-187">Genehmigte Apps auf iOS- und Android-Geräten erforderlich</span><span class="sxs-lookup"><span data-stu-id="6df72-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="6df72-188">BASISPLAN, VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-189">Kompatible PCs erforderlich</span><span class="sxs-lookup"><span data-stu-id="6df72-189">Require compliant PCs</span></span> | <span data-ttu-id="6df72-190">BASISPLAN</span><span class="sxs-lookup"><span data-stu-id="6df72-190">Baseline</span></span> |
| <span data-ttu-id="6df72-191">Kompatible PCs und iOS- und Android-Geräte erforderlich</span><span class="sxs-lookup"><span data-stu-id="6df72-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="6df72-192">VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="6df72-193">Hier ist die Azure AD Identity Protection-Richtlinie zum Benutzerrisiko (erfordert Microsoft 365 Enterprise E5), um dies zu erstellen und zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="6df72-194">Azure AD Identity Protection-Richtlinie zum Benutzerrisiko</span><span class="sxs-lookup"><span data-stu-id="6df72-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="6df72-195">Gruppen, auf die Sie angewendet wird</span><span class="sxs-lookup"><span data-stu-id="6df72-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="6df72-196">Benutzer mit hohem Risiko müssen die Kennwörter ändern</span><span class="sxs-lookup"><span data-stu-id="6df72-196">High risk users must change passwords</span></span> | <span data-ttu-id="6df72-197">Wählen Sie in den Richtlinieneinstellungen "alle Benutzer" aus.</span><span class="sxs-lookup"><span data-stu-id="6df72-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="6df72-198">Siehe [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) für die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6df72-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="6df72-199">Gruppen zur einfacheren Verwaltung</span><span class="sxs-lookup"><span data-stu-id="6df72-199">Groups for easier management</span></span>

<span data-ttu-id="6df72-200">Hier sind einige Features, die Ihnen die Gruppen- und Lizenzverwaltung erleichtern können.</span><span class="sxs-lookup"><span data-stu-id="6df72-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="6df72-201">Feature</span><span class="sxs-lookup"><span data-stu-id="6df72-201">Feature</span></span> | <span data-ttu-id="6df72-202">Verwendung</span><span class="sxs-lookup"><span data-stu-id="6df72-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="6df72-203">Gruppenverwaltung durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="6df72-203">Self-service group management</span></span> | <span data-ttu-id="6df72-204">Ermöglicht die Verwaltung von Azure AD-Gruppen durch Gruppenbesitzer anstelle von IT-Mitarbeitern.</span><span class="sxs-lookup"><span data-stu-id="6df72-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="6df72-205">Weitere Informationen finden Sie unter [Self-Service-Gruppenverwaltung](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups).</span><span class="sxs-lookup"><span data-stu-id="6df72-205">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="6df72-206">Dynamische Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="6df72-206">Dynamic group membership</span></span> | <span data-ttu-id="6df72-207">Konfigurieren Sie das automatische Hinzufügen oder Entfernen von Benutzerkonten aus Azure AD-Gruppen basierend auf Benutzerkontoattributen wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="6df72-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="6df72-208">Weitere Informationen finden Sie unter [Dynamische Gruppenmitgliedschaft](identity-self-service-group-management.md#set-up-dynamic-group-membership).</span><span class="sxs-lookup"><span data-stu-id="6df72-208">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="6df72-209">Gruppenbasierte Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="6df72-209">Group-based licensing</span></span> | <span data-ttu-id="6df72-210">Verwenden Sie die Gruppenmitgliedschaft, um Lizenzen automatisch den Benutzerkonten zuzuordnen oder aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="6df72-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="6df72-211">Weitere Informationen finden Sie unter [Gruppenbasierte Lizenzierung](identity-self-service-group-management.md#set-up-automatic-licensing).</span><span class="sxs-lookup"><span data-stu-id="6df72-211">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="6df72-212">Wenn Sie eine gruppenbasierte Lizenzierung verwenden, erstellen Sie eine Gruppe mit dem Namen LIZENZIERT, die Benutzerkontennamen enthält, denen eine Microsoft 365 Enterprise-Lizenz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6df72-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="6df72-213">Überwachen des Benutzerzugriffs</span><span class="sxs-lookup"><span data-stu-id="6df72-213">Monitor user access</span></span>

<span data-ttu-id="6df72-214">Wenn Sie über Microsoft 365 Enterprise E5 verfügen, können Sie Azure AD Identity Protection verwenden, um die Benutzeranmeldungen zu überwachen und zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="6df72-215">Weitere Informationen hierzu finden Sie unter [Schutz vor Kompromittierung von Anmeldeinformationen](identity-multi-factor-authentication.md#protect-against-credential-compromise).</span><span class="sxs-lookup"><span data-stu-id="6df72-215">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-216">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-216">Your configuration so far</span></span>

<span data-ttu-id="6df72-217">Hier ist eine visuelle Zusammenfassung der Phase "Identität" für hybride Identität, in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="6df72-218">Zu den neuen und hervorgehobenen Elementen der hybriden Identität gehören:</span><span class="sxs-lookup"><span data-stu-id="6df72-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="6df72-219">Eine lokale AD DS-Domäne mit Benutzerkonten und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="6df72-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="6df72-220">Ein Windows-basierter Server mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="6df72-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="6df72-221">Der synchronisierte Satz von AD DS-Konten und Gruppen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6df72-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="6df72-222">Azure AD-Einstellungen für die Authentifizierung, die Sicherung globaler Konten und die Vereinfachung der Verwaltung von Gruppen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6df72-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="6df72-223">Azure AD-Richtlinien für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="6df72-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="6df72-224">Hier ist eine visuelle Zusammenfassung der Phase "Identität" für reine Cloudidentität, in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="6df72-225">Zu den neuen und hervorgehobenen Elementen der reinen Cloudidentität gehören:</span><span class="sxs-lookup"><span data-stu-id="6df72-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="6df72-226">Azure AD-Einstellungen für die Authentifizierung, die Sicherung globaler Konten und die Vereinfachung der Verwaltung von Gruppen und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6df72-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="6df72-227">Azure AD-Richtlinien für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="6df72-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="6df72-228">Phase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6df72-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="6df72-229">Um sicherzustellen, dass Ihre Windows 10 Enterprise-Geräte in die Identitäts- und Sicherheitsinfrastruktur von Microsoft 365 integriert sind, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="6df72-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="6df72-230">Hybrid (Sie verfügen über eine lokale AD DS-Domäne)</span><span class="sxs-lookup"><span data-stu-id="6df72-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="6df72-231">Für jedes vorhandene Windows 10 Enterprise-Gerät, das bereits mit Ihrer AD DS-Domäne verknüpft ist, verbinden Sie es mit dem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6df72-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="6df72-232">Siehe [Konfigurieren von in Azure Active Directory eingebundenen Hybridgeräten](https://go.microsoft.com/fwlink/p/?linkid=872870) für die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6df72-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="6df72-233">Für jedes neue Windows 10 Enterprise-Gerät verknüpfen Sie diese mit Ihrer AD DS-Domäne und verbinden Sie diese anschließend mit dem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6df72-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="6df72-234">Für jedes Windows 10 Enterprise-Gerät müssen Sie es für die Verwaltung mobiler Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="6df72-235">Siehe [Registrieren eines Windows 10-Geräts mit Intune unter Verwendung einer Gruppenrichtlinie](https://go.microsoft.com/fwlink/p/?linkid=872871) für die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6df72-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="6df72-236">Reine Cloud (Sie verfügen nicht über eine lokale AD DS-Domäne)</span><span class="sxs-lookup"><span data-stu-id="6df72-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="6df72-237">Verbinden Sie jedes Windows 10 Enterprise-Gerät mit dem Azure AD-Mandanten Ihres Abonnements.</span><span class="sxs-lookup"><span data-stu-id="6df72-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="6df72-238">Weitere Informationen finden Sie unter [Einbinden von geschäftlichen Geräten in das Netzwerk der Organisation](https://docs.microsoft.com/de-DE/azure/active-directory/user-help/user-help-join-device-on-network).</span><span class="sxs-lookup"><span data-stu-id="6df72-238">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="6df72-239">Nach der Installation und Verknüpfung installiert jedes Windows 10 Enterprise-Gerät automatisch Updates aus dem Windows Update for Business-Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="6df72-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="6df72-240">In der Regel ist es in einem Nicht-Unternehmen nicht erforderlich, eine Infrastruktur für die Verteilung und Installation von Windows 10-Updates einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6df72-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-241">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-241">Your configuration so far</span></span>

<span data-ttu-id="6df72-242">Hier ist eine visuelle Zusammenfassung der Phase "Windows 10 Enterprise", in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="6df72-243">Zu den neuen und hervorgehobenen Elementen von Windows 10 Enterprise gehören:</span><span class="sxs-lookup"><span data-stu-id="6df72-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="6df72-244">Windows 10 Enterprise wurde auf Windows-Geräten installiert, beispielsweise auf einem lokalen Laptop.</span><span class="sxs-lookup"><span data-stu-id="6df72-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="6df72-245">Das Volume Licensing Service Center, das Bilder für Neuinstallationen von Windows 10 Enterprise bereitstellt, und der Windows Update for Business Service, der die neuesten Updates bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6df72-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="6df72-246">Phase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="6df72-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="6df72-247">Microsoft 365 Enterprise enthält Office 365 ProPlus, die Abonnementversion von Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="6df72-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="6df72-248">Wie Office 2016 oder Office 2019 wird Office 365 ProPlus direkt auf Ihren Clientgeräten installiert.</span><span class="sxs-lookup"><span data-stu-id="6df72-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="6df72-249">Office 365 ProPlus erhält jedoch in regelmäßigen Abständen mit neuen Features.</span><span class="sxs-lookup"><span data-stu-id="6df72-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="6df72-250">Weitere Informationen finden Sie unter [Informationen zu Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="6df72-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="6df72-251">Für Ihr Nicht-Unternehmen installieren Sie Office 365 ProPlus manuell auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="6df72-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="6df72-252">Dies kann im Rahmen der Vorbereitung eines neuen Geräts für den Gebrauch oder durch den Benutzer im Rahmen seines Onboarding-Prozesses erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6df72-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="6df72-253">In beiden Fällen meldet sich der Administrator oder der Benutzer am Office 365-Portal unter https://portal.office.com an.</span><span class="sxs-lookup"><span data-stu-id="6df72-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="6df72-254">Klicken Sie auf der Registerkarte **Microsoft Office-Startseite** auf **Office installieren**, und durchlaufen Sie den Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="6df72-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="6df72-255">Feature-Updates für Office 365 ProPlus werden monatlich von jedem Computer heruntergeladen, auf dem sie installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="6df72-256">In der Regel ist es in einem Nicht-Unternehmen nicht erforderlich, eine Infrastruktur für die Verteilung von Office 365 ProPlus-Updates einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6df72-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-257">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-257">Your configuration so far</span></span>

<span data-ttu-id="6df72-258">Hier ist eine visuelle Zusammenfassung der Phase "Office 365 ProPlus", in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="6df72-259">Zu den neuen und hervorgehobenen Office 365 ProPlus-Elementen gehören:</span><span class="sxs-lookup"><span data-stu-id="6df72-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="6df72-260">Office 365 ProPlus wurde auf Geräten installiert, beispielsweise auf einem lokalen Laptop.</span><span class="sxs-lookup"><span data-stu-id="6df72-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="6df72-261">Das Office Content Delivery Network (CDN) für Office 365 ProPlus, auf das die Geräte für Office 365 ProPlus-Updates zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6df72-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="6df72-262">Phase 5: Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="6df72-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="6df72-263">Microsoft 365 Enterprise enthält Microsoft Intune für die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="6df72-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="6df72-264">Mit Intune können Sie Windows-, iOS-, Android- und macOS-Geräte verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation, einschließlich Ihrer Daten, zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6df72-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="6df72-265">Intune verwendet die Benutzer-, Gruppen- und Computerkonten von Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6df72-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="6df72-266">Intune bietet zwei Arten der Verwaltung mobiler Geräte:</span><span class="sxs-lookup"><span data-stu-id="6df72-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="6df72-267">Bei der Verwaltung mobiler Geräte (Mobile Device Management, MDM) handelt es sich um Geräte, die in Intune registriert werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="6df72-268">Nach der Registrierung sind sie verwaltete Geräte und können die von Ihrer Organisation verwendeten Richtlinien, Regeln und Einstellungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="6df72-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="6df72-269">Diese Geräte sind in der Regel im Besitz Ihrer Organisation und werden an Ihre Mitarbeiter ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6df72-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="6df72-270">Benutzer mit ihren eigenen persönlichen Geräten möchten möglicherweise nicht ihre Geräte registrieren oder von Intune mit Ihren Richtlinien und Einstellungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="6df72-271">Allerdings müssen Sie die Ressourcen und Daten Ihrer Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="6df72-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="6df72-272">Für dieses Szenario können Sie Ihre Anwendungen mit der mobilen Anwendungsverwaltung (Mobile Application Management, MAM) schützen.</span><span class="sxs-lookup"><span data-stu-id="6df72-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="6df72-273">Intune-Richtlinien können Gerätekompatibilität und App-Schutz erzwingen.</span><span class="sxs-lookup"><span data-stu-id="6df72-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="6df72-274">Hier ist die Liste der zu erstellenden Intune-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="6df72-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="6df72-275">Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="6df72-275">Intune policies</span></span> | <span data-ttu-id="6df72-276">Gruppen, auf die Sie angewendet wird</span><span class="sxs-lookup"><span data-stu-id="6df72-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="6df72-277">Gerätekompatibilitätsrichtlinie für Windows</span><span class="sxs-lookup"><span data-stu-id="6df72-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="6df72-278">BASISPLAN, VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-279">Gerätekompatibilitätsrichtlinie für iOS</span><span class="sxs-lookup"><span data-stu-id="6df72-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="6df72-280">VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-281">Gerätekompatibilitätsrichtlinie für macOS</span><span class="sxs-lookup"><span data-stu-id="6df72-281">Device compliance for macOS</span></span> | <span data-ttu-id="6df72-282">VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-283">Gerätekompatibilitätsrichtlinie für Android und Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="6df72-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="6df72-284">VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-285">App-Schutzrichtlinie für iOS</span><span class="sxs-lookup"><span data-stu-id="6df72-285">App protection policy for iOS</span></span> | <span data-ttu-id="6df72-286">BASISPLAN, VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-287">App-Schutzrichtlinie für macOS</span><span class="sxs-lookup"><span data-stu-id="6df72-287">App protection policy for macOS</span></span> | <span data-ttu-id="6df72-288">BASISPLAN, VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="6df72-289">App-Schutzrichtlinie für Android und Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="6df72-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="6df72-290">BASISPLAN, VERTRAULICH, STRENG GEREGELT</span><span class="sxs-lookup"><span data-stu-id="6df72-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="6df72-291">Siehe [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) für die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6df72-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-292">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-292">Your configuration so far</span></span>

<span data-ttu-id="6df72-293">Hier ist eine visuelle Zusammenfassung der Phase "Verwaltung mobiler Geräte", in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="6df72-294">Die neuen und hervorgehobenen Elemente für die Verwaltung mobiler Geräte umfassen:</span><span class="sxs-lookup"><span data-stu-id="6df72-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="6df72-295">In Intune registrierte Geräte, die beispielsweise Windows 10 Enterprise auf einem lokalen Laptop ausführen.</span><span class="sxs-lookup"><span data-stu-id="6df72-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="6df72-296">Intune-Richtlinien für die Gerätekompatibilität und den App-Schutz.</span><span class="sxs-lookup"><span data-stu-id="6df72-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="6df72-297">Phase 6: Informationsschutz</span><span class="sxs-lookup"><span data-stu-id="6df72-297">Phase 6: Information protection</span></span>

<span data-ttu-id="6df72-298">Microsoft 365 Enterprise verfügt über eine Vielzahl von Features zum Informationsschutz, mit denen Sie Klassifizierungen von Daten unterschiedlich behandeln können, indem Sie verschiedene Ebenen der Governance, Sicherheit und des Schutzes anwenden.</span><span class="sxs-lookup"><span data-stu-id="6df72-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="6df72-299">So benötigt beispielsweise die normale Korrespondenz zwischen den meisten Mitarbeitern und den Dokumenten, an denen sie arbeiten, eine gewisse Basis-Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="6df72-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="6df72-300">Finanzunterlagen, Kundendaten und Ihr geistiges Eigentum benötigen eine höhere Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="6df72-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="6df72-301">Der erste Schritt zu einer Informationsschutzstrategie ist die Festlegung der Sicherheitsebenen.</span><span class="sxs-lookup"><span data-stu-id="6df72-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="6df72-302">Viele Organisationen verwenden diese Ebenen, die bereits für Richtlinien für den bedingten Zugriff verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6df72-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="6df72-303">Basisplan</span><span class="sxs-lookup"><span data-stu-id="6df72-303">Baseline</span></span>

  <span data-ttu-id="6df72-304">Beispiele sind normale Geschäftskommunikation (E-Mail) und Dateien für Mitarbeiter in der Verwaltung, im Vertrieb oder im Kundendienst.</span><span class="sxs-lookup"><span data-stu-id="6df72-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="6df72-305">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="6df72-305">Sensitive</span></span>

  <span data-ttu-id="6df72-306">Beispiele sind Finanz- und rechtliche Informationen sowie Forschungs- und Entwicklungsdaten für neue Produkte oder Dienste.</span><span class="sxs-lookup"><span data-stu-id="6df72-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="6df72-307">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="6df72-307">Highly regulated</span></span>

  <span data-ttu-id="6df72-308">Beispiele sind personenbezogene Daten von Kunden und Partnern sowie Finanzdaten oder geistiges Eigentum Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6df72-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="6df72-309">Basierend auf diesen Ebenen der Datensicherheit ist der nächste Schritt die Identifizierung und Implementierung von:</span><span class="sxs-lookup"><span data-stu-id="6df72-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="6df72-310">Benutzerdefinierten Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="6df72-310">Custom sensitive information types</span></span>

  <span data-ttu-id="6df72-311">Microsoft 365 bietet eine große Auswahl an vertraulichen Datentypen, wie z. B. Krankenversicherungs- und Kreditkartennummern.</span><span class="sxs-lookup"><span data-stu-id="6df72-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="6df72-312">Wenn Sie in der bereitgestellten Liste keinen finden, den Sie benötigen, können Sie einen eigenen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6df72-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="6df72-313">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6df72-313">Retention labels</span></span>

  <span data-ttu-id="6df72-314">Um die Organisationsrichtlinien und regionalen Vorschriften einzuhalten, müssen Sie möglicherweise angeben, wie lange bestimmte Arten von Dokumenten oder Dokumente mit bestimmten Inhalten aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6df72-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="6df72-315">Sie können dies für E-Mails und Dokumente mit Aufbewahrungsbezeichnungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="6df72-316">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6df72-316">Sensitivity labels</span></span>

  <span data-ttu-id="6df72-317">Sie können E-Mails oder Dokumente mit einer benannten Vertraulichkeitsbezeichnung kennzeichnen, so dass zusätzliche Sicherheitsebenen angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6df72-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="6df72-318">Beispiele sind Wasserzeichen, Verschlüsselung und Berechtigungen, die angeben, wer auf die E-Mail bzw. das Dokument und die zulässigen Aktionen zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="6df72-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="6df72-319">Weitere Informationen hierzu finden Sie unter [Microsoft 365-Klassifizierungstypen](infoprotect-configure-classification.md#microsoft-365-classification-types).</span><span class="sxs-lookup"><span data-stu-id="6df72-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="6df72-320">Wenn Sie Vertraulichkeitsbezeichnungen mit Berechtigungen verwenden, müssen Sie möglicherweise zusätzliche Azure AD-Sicherheitsgruppen erstellen, um zu definieren, wer was mit E-Mails und Dokumenten tun darf.</span><span class="sxs-lookup"><span data-stu-id="6df72-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="6df72-321">Beispielsweise müssen Sie eine Vertraulichkeitsbezeichnung FORSCHUNG erstellen, um die E-Mails und Dokumente Ihres Forschungsteams zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6df72-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="6df72-322">Sie bestimmen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6df72-322">You determine that:</span></span>

- <span data-ttu-id="6df72-323">Forscher müssen die Möglichkeit haben, Dokumente zu ändern, die mit der Vertraulichkeitsbezeichnung "FORSCHUNG" gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="6df72-324">Angestellte, die nicht der Forschungsabteilung angehören, müssen Dokumente, die mit der Vertraulichkeitsbezeichnung "FORSCHUNG" gekennzeichnet sind, anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="6df72-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="6df72-325">Dies bedeutet, dass Sie zwei zusätzliche Gruppen erstellen und verwalten müssen:</span><span class="sxs-lookup"><span data-stu-id="6df72-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="6df72-326">FORSCHUNG – ALLE</span><span class="sxs-lookup"><span data-stu-id="6df72-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="6df72-327">FORSCHUNG – ANZEIGEN</span><span class="sxs-lookup"><span data-stu-id="6df72-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="6df72-328">Diese Gruppen und ihre Berechtigungen werden Teil der Konfiguration der Vertraulichkeitsbezeichnung FORSCHUNG.</span><span class="sxs-lookup"><span data-stu-id="6df72-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="6df72-329">Bei Vertraulichkeitsbezeichnung, die mit gruppenbasierten Berechtigungen konfiguriert sind, müssen Sie die Zugehörigkeit zu diesen Gruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="6df72-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="6df72-330">Ihre bisherige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6df72-330">Your configuration so far</span></span>

<span data-ttu-id="6df72-331">Hier ist eine visuelle Zusammenfassung der Phase "Informationsschutz", in der die neuen Elemente hervorgehoben sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="6df72-332">Zu den neuen und hervorgehobenen Elementen des Informationsschutzes gehören:</span><span class="sxs-lookup"><span data-stu-id="6df72-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="6df72-333">Vertraulichkeitsbezeichnungen für die drei Sicherheitsebenen, die Benutzer auf Dokumente anwenden können.</span><span class="sxs-lookup"><span data-stu-id="6df72-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="6df72-334">Benutzerdefinierte Informationstypen und Aufbewahrungsbezeichnungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6df72-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="6df72-335">Onboarding</span><span class="sxs-lookup"><span data-stu-id="6df72-335">Onboarding</span></span>

<span data-ttu-id="6df72-336">Mit Ihrer Microsoft 365 Enterprise-Infrastruktur können Sie Ihre Mitarbeiter mühelos integrieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="6df72-337">Ein neues Windows 10 Enterprise-Gerät</span><span class="sxs-lookup"><span data-stu-id="6df72-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="6df72-338">Bevor Sie einem Mitarbeiter ein neues Windows 10 Enterprise-Gerät zuweisen:</span><span class="sxs-lookup"><span data-stu-id="6df72-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="6df72-339">Für hybride Identität</span><span class="sxs-lookup"><span data-stu-id="6df72-339">For hybrid identity</span></span>

  <span data-ttu-id="6df72-340">Verbinden Sie das Gerät mit Ihrer AD DS-Domäne, verbinden Sie das Gerät mit Ihrem Azure AD-Mandanten und registrieren Sie das Gerät anschließend in Intune.</span><span class="sxs-lookup"><span data-stu-id="6df72-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="6df72-341">Für reine Cloudidentität</span><span class="sxs-lookup"><span data-stu-id="6df72-341">For cloud-only identity</span></span>

  <span data-ttu-id="6df72-342">Verbinden Sie das Gerät an den Azure AD-Mandanten Ihres Microsoft 365 Enterprise-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="6df72-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="6df72-343">Vorhandene Mitarbeiter mit einem AD DS-Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="6df72-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="6df72-344">Als Teil des ersten Onboardings für Ihre Organisation bei der Verwendung von Hybrididentität fügen Sie das AD DS-Benutzerkonto zu diesen Azure AD-Gruppen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6df72-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="6df72-345">LIZENZIERT</span><span class="sxs-lookup"><span data-stu-id="6df72-345">Licensed</span></span>
- <span data-ttu-id="6df72-346">Die entsprechenden AD DS- oder Azure AD-Sicherheitsgruppen, die Mitglieder der Azure AD-Gruppen BASELINE, VERTRAULICH und STRENG GEREGELT sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="6df72-347">Gruppen mit Vertraulichkeitsbezeichnung (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="6df72-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="6df72-348">Der bestehende Mitarbeiter sollte bereits zu den entsprechenden Arbeitsgruppen, Abteilungs- und regionalen AD DS-Gruppen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6df72-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="6df72-349">Sie können ein Benutzerkonto zu mehreren Azure Ad-Gruppen im Microsoft 365 Admin Center hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6df72-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6df72-350">Klicken Sie in den Eigenschaften des Benutzerkontos auf **Gruppen verwalten > Mitgliedschaften hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6df72-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="6df72-351">Wenn Sie PowerShell verwenden möchten, schauen Sie sich diese [herunterladbare Excel-Arbeitsmappe](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true) an, die die PowerShell-Befehle basierend auf einem angegebenen Benutzerkonto und ausgewählten Gruppennamen generiert.</span><span class="sxs-lookup"><span data-stu-id="6df72-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="6df72-352">Neuer Mitarbeiter mit einem reinen Cloudbenutzerkonto</span><span class="sxs-lookup"><span data-stu-id="6df72-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="6df72-353">Fügen Sie im Rahmen des ersten Onboardings für Ihre Organisation bei der Verwendung von reinen Cloudidentitäten das neue Benutzerkonto zu diesen Gruppen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6df72-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="6df72-354">LIZENZIERT</span><span class="sxs-lookup"><span data-stu-id="6df72-354">Licensed</span></span>
- <span data-ttu-id="6df72-355">Die entsprechenden Azure AD-Sicherheitsgruppen, die Mitglieder der Azure AD-Gruppen BASELINE, VERTRAULICH und STRENG GEREGELT sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="6df72-356">Arbeitsgruppen-, Abteilungs- und Regionalgruppen</span><span class="sxs-lookup"><span data-stu-id="6df72-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="6df72-357">Gruppen mit Vertraulichkeitsbezeichnung (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="6df72-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="6df72-358">Erstmalige Anmeldung bei Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df72-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="6df72-359">Geben Sie Angestellten, die sich zum ersten Mal bei Microsoft 365 anmelden, die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="6df72-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="6df72-360">Sich auf ihren Geräten mit ihren Benutzerkonto-Anmeldeinformationen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6df72-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="6df72-361">Sich mit einem Browser am Office 365-Portal unter https://portal.office.com anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6df72-361">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account.</span></span>
3. <span data-ttu-id="6df72-362">Auf der Registerkarte **Office 365 Home** auf **Office installieren** zu klicken, um Office 365 ProPlus auf Ihrem Gerät zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="6df72-363">Endergebnisse</span><span class="sxs-lookup"><span data-stu-id="6df72-363">End results</span></span>

<span data-ttu-id="6df72-364">Hier sind die Ergebnisse der Konfiguration der Microsoft 365 Enterprise Foundation-Infrastruktur für Ihr Nicht-Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="6df72-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="6df72-365">Infrastrukturergebnisse</span><span class="sxs-lookup"><span data-stu-id="6df72-365">Infrastructure results</span></span>

<span data-ttu-id="6df72-366">Nach dem Aufbau und der Konfiguration Ihrer Microsoft 365 Enterprise-Infrastruktur sollten Sie Folgendes haben:</span><span class="sxs-lookup"><span data-stu-id="6df72-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="6df72-367">Eine lokale Internetverbindung für jedes Ihrer Büros mit ausreichender Bandbreite, die von einem ISP bereitgestellt wird, der einen regional lokalen DNS-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="6df72-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="6df72-368">Für eine Hybrididentität läuft Azure AD Connect auf einem Server, der Ihre lokale AD DS-Domäne mit Ihrem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="6df72-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="6df72-369">Diese Gruppen sind:</span><span class="sxs-lookup"><span data-stu-id="6df72-369">These universal groups include:</span></span>
  - <span data-ttu-id="6df72-370">LIZENZIERT</span><span class="sxs-lookup"><span data-stu-id="6df72-370">Licensed</span></span>
  - <span data-ttu-id="6df72-371">BEDINGTEN ZUGRIFF AUSSCHLIEßEN</span><span class="sxs-lookup"><span data-stu-id="6df72-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="6df72-372">Die entsprechenden AD DS- oder Azure AD-Sicherheitsgruppen, die auch Mitglieder der Azure AD-Gruppen BASISPLAN, VERTRAULICH und STRENG GEREGELT sind</span><span class="sxs-lookup"><span data-stu-id="6df72-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="6df72-373">Arbeitsgruppen-, Abteilungs- und Regionalgruppen</span><span class="sxs-lookup"><span data-stu-id="6df72-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="6df72-374">Gruppen mit Vertraulichkeitsbezeichnung (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="6df72-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="6df72-375">Azure AD-Richtlinien für den bedingten Zugriff melden sich an, der die Azure AD-Gruppen BASISPLAN, VERTRAULICH und STRENG GEREGELT sowie BEDINGTEN ZUGRIFF AUSSCHLIEßEN verwenden.</span><span class="sxs-lookup"><span data-stu-id="6df72-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="6df72-376">Intune-Richtlinien für Anwendungen und Gerätekompatibilität.</span><span class="sxs-lookup"><span data-stu-id="6df72-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="6df72-377">Benutzerdefinierte Typen vertraulicher Informationen (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="6df72-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="6df72-378">Aufbewahrungsbezeichnungen (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="6df72-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="6df72-379">Vertraulichkeitsbezeichnungen (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="6df72-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="6df72-380">Hier ist eine visuelle Zusammenfassung der Infrastruktur, wenn Ihre Organisation eine Hybrididentität verwendet, die Ihre AD DS-Domäne, einen Azure AD Connect-Server und synchronisierte AD DS-Benutzer und -Gruppen umfasst.</span><span class="sxs-lookup"><span data-stu-id="6df72-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="6df72-381">Hier ist eine visuelle Zusammenfassung der Infrastruktur, wenn Ihre Organisation eine reine Cloud-Identität verwendet.</span><span class="sxs-lookup"><span data-stu-id="6df72-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="6df72-382">Mitarbeiterergebnisse</span><span class="sxs-lookup"><span data-stu-id="6df72-382">Employee results</span></span>

<span data-ttu-id="6df72-383">Nach dem Onboarding sollte jeder Mitarbeiter Folgendes haben:</span><span class="sxs-lookup"><span data-stu-id="6df72-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="6df72-384">Einen leistungsfähigen, lokalen Netzwerkpfad von ihrem Gerät zu den Microsoft 365-Clouddienste in ihrer Region.</span><span class="sxs-lookup"><span data-stu-id="6df72-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="6df72-385">Ein Benutzerkonto mit diesen Gruppenmitgliedschaften:</span><span class="sxs-lookup"><span data-stu-id="6df72-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="6df72-386">LIZENZIERT</span><span class="sxs-lookup"><span data-stu-id="6df72-386">Licensed</span></span>
   - <span data-ttu-id="6df72-387">Die entsprechenden AD DS- oder Azure AD-Sicherheitsgruppen, die auch Mitglieder der Azure AD-Gruppen BASISPLAN, VERTRAULICH und STRENG GEREGELT für Richtlinien für den bedingten Zugriff sind.</span><span class="sxs-lookup"><span data-stu-id="6df72-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="6df72-388">Die entsprechenden Arbeitsgruppen-, Abteilungs- und Regionalgruppen</span><span class="sxs-lookup"><span data-stu-id="6df72-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="6df72-389">Gruppen mit Vertraulichkeitsbezeichnung (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="6df72-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="6df72-390">Ein Windows 10 Enterprise-Gerät, das:</span><span class="sxs-lookup"><span data-stu-id="6df72-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="6df72-391">Mit dem Azure AD-Mandanten (nur Cloud) oder mit dem Azure AD-Mandanten und Ihrer AD DS-Domäne (Hybrid) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6df72-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="6df72-392">Sich automatisch mit den neuesten Produktverbesserungen und Sicherheitserweiterungen von Windows 10 Enterprise aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6df72-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="6df72-393">Office 365 ProPlus installiert hat, welches sich automatisch mit den neuesten Produktverbesserungen und Sicherheitserweiterungen von Office aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6df72-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="6df72-394">In Intune registriert ist und den Intune-Richtlinien für die Gerätekompatibilität und den App-Schutzrichtlinien unterliegt.</span><span class="sxs-lookup"><span data-stu-id="6df72-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="6df72-395">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6df72-395">Next step</span></span>

<span data-ttu-id="6df72-396">Bereitstellen Ihrer [Arbeitslasten und Szenarien](deploy-workloads.md), um von den Features und der Konfiguration Ihrer Microsoft 365 Enterprise Foundation-Infrastruktur zu profitieren.</span><span class="sxs-lookup"><span data-stu-id="6df72-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
