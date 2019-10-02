---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
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
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: 5c78e8cc9235eb2ca5de091c05d1883ed6cca1b4
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369606"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="b312d-103">Identität für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="b312d-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="b312d-104">**Zusammenfassung:** Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b312d-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="b312d-105">Microsoft bietet eine IDaaS (Identity as a Service, Identität als Dienst) in seinen Cloudangeboten mit Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b312d-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b312d-106">Um Microsoft 365 Enterprise einzuführen, musste für die IDaaS-Lösung von Contoso dessen lokaler Identitätsanbieter genutzt und weiterhin Verbundauthentifizierung mit den vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="b312d-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="b312d-107">Active Directory Domain Services-Gesamtstruktur von Contoso</span><span class="sxs-lookup"><span data-stu-id="b312d-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="b312d-108">Contoso verwendet eine einzelne Active Directory Domain Services(AD DS)-Gesamtstruktur für „contoso.com“ mit sieben Unterdomänen, eine für jede Region der Welt.</span><span class="sxs-lookup"><span data-stu-id="b312d-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="b312d-109">Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="b312d-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="b312d-110">Abbildung 1 zeigt die Contoso-Gesamtstruktur mit regionalen Domänen für die unterschiedlichen Regionen, die Regionalstellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b312d-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Gesamtstruktur und Domänen von Contoso weltweit](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="b312d-112">**Abbildung 1: Gesamtstruktur und Domänen von Contoso weltweit**</span><span class="sxs-lookup"><span data-stu-id="b312d-112">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="b312d-113">Contoso wollte die Konten und Gruppen in der „contoso.com“-Gesamtstruktur zur Authentifizierung und Autorisierung seiner Microsoft 365-Arbeitslasten und -Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="b312d-113">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="b312d-114">Contosos Infrastruktur der Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b312d-114">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="b312d-115">Contoso lässt Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="b312d-115">Contoso allows:</span></span>

- <span data-ttu-id="b312d-116">Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei ihren öffentlichen Websites anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b312d-116">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="b312d-117">Lieferanten und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partnerextranet anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b312d-117">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="b312d-p103">Abbildung 2 zeigt die Contoso-DMZ mit einer öffentlichen Website, einem Partnerextranet und einer Reihe von Active Directory Federation Services-Servern (AD FS). Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="b312d-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contosos Unterstützung für die Verbundauthentifizierung für Kunden und Partner](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="b312d-121">**Abbildung 2: Contosos Unterstützung für die Verbundauthentifizierung für Kunden und Partner**</span><span class="sxs-lookup"><span data-stu-id="b312d-121">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="b312d-122">AD FS-Server in der DMZ erleichtern das Authentifizieren von Kundenanmeldeinformationen durch den Identitätsanbieter für Zugriff auf die öffentliche Website und Partneranmeldeinformationen für Zugriff auf das Partnerextranet.</span><span class="sxs-lookup"><span data-stu-id="b312d-122">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="b312d-123">Contoso hat sich entschlossen, seine Infrastruktur beizubehalten und diese für die Kunden- und Partnerauthentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b312d-123">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD B2B and B2C solutions.</span></span> <span data-ttu-id="b312d-124">Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="b312d-124">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="b312d-125">Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b312d-125">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="b312d-126">Contoso wollte seine lokale AD DS-Gesamtstruktur für die Authentifizierung bei Microsoft 365-Cloudressourcen nutzen.</span><span class="sxs-lookup"><span data-stu-id="b312d-126">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="b312d-127">Es entschied sich für Kennwort-Hash-Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="b312d-127">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="b312d-128">Bei der Kennwort-Hash-Synchronisierung wird die lokale AD DS-Gesamtstruktur mit dem Azure AD-Mandanten des Microsoft 365 Enterprise-Abonnements synchronisiert, wobei Benutzer- und Gruppenkonten und eine Hash-Version von Benutzerkontokennwörtern kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b312d-128">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="b312d-129">Um die laufende Verzeichnissynchronisierung durchzuführen, hat Contoso das Azure AD Connect-Tool auf einem Server im Rechenzentrum in Paris bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b312d-129">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> <span data-ttu-id="b312d-130">Abbildung 3 zeigt den Server mit Azure AD Connect, das die AD DS-Gesamtstruktur von Contoso auf Änderungen abruft und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="b312d-130">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="b312d-132">**Abbildung 3: Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso**</span><span class="sxs-lookup"><span data-stu-id="b312d-132">**Figure 3: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="b312d-133">Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="b312d-133">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="b312d-134">Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](identity-access-policies.md) für drei Schutzebenen erstellt:</span><span class="sxs-lookup"><span data-stu-id="b312d-134">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="b312d-135">**Baseline**-Schutz gilt für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="b312d-135">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="b312d-136">**Vertraulicher** Schutz gilt für die Geschäftsleitung und Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="b312d-136">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="b312d-137">**Hochgradig regulierter** Schutz gilt für bestimmte Benutzer der Finanz-, Rechts- und Forschungsabteilung, die Zugriff auf hochgradig regulierte Daten haben.</span><span class="sxs-lookup"><span data-stu-id="b312d-137">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="b312d-138">Abbildung 4 zeigt die resultierenden identitäts- und gerätebasierten Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b312d-138">Figure 4 shows their resulting set of identity and device conditional access policies.</span></span>

![Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="b312d-140">**Abbildung 4: Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff**</span><span class="sxs-lookup"><span data-stu-id="b312d-140">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="b312d-141">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b312d-141">Next step</span></span>

<span data-ttu-id="b312d-142">[Erfahren Sie](contoso-win10.md), wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Windows 10 Enterprise über die Organisation hinweg bereitzustellen und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="b312d-142">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b312d-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b312d-143">See also</span></span>

[<span data-ttu-id="b312d-144">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b312d-144">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b312d-145">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="b312d-145">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b312d-146">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="b312d-146">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
