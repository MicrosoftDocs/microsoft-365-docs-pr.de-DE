---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068452"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="f8e3a-103">Identität für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="f8e3a-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="f8e3a-104">Microsoft bietet eine IDaaS (Identity as a Service, Identität als Dienst) in seinen Cloudangeboten mit Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f8e3a-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f8e3a-105">Um Microsoft 365 Enterprise einzuführen, musste für die IDaaS-Lösung von Contoso dessen lokaler Identitätsanbieter genutzt und weiterhin Verbundauthentifizierung mit den vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="f8e3a-106">Active Directory Domain Services-Gesamtstruktur von Contoso</span><span class="sxs-lookup"><span data-stu-id="f8e3a-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="f8e3a-107">Contoso verwendet eine einzelne Active Directory Domain Services(AD DS)-Gesamtstruktur für „contoso.com“ mit sieben Unterdomänen, eine für jede Region der Welt.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="f8e3a-108">Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="f8e3a-109">Hier sehen Sie die Contoso-Gesamtstruktur mit regionalen Domänen für die unterschiedlichen Regionen, die regionale Hubs enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Gesamtstruktur und Domänen von Contoso weltweit](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="f8e3a-111">Contoso wollte die Konten und Gruppen in der „contoso.com“-Gesamtstruktur zur Authentifizierung und Autorisierung seiner Microsoft 365-Arbeitslasten und -Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="f8e3a-112">Contosos Infrastruktur der Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f8e3a-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="f8e3a-113">Contoso lässt Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="f8e3a-113">Contoso allows:</span></span>

- <span data-ttu-id="f8e3a-114">Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei ihren öffentlichen Websites anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="f8e3a-115">Lieferanten und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partnerextranet anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="f8e3a-116">Hier sehen Sie die Contoso-DMZ mit einer öffentlichen Website, einem Partnerextranet und einer Reihe von Active Directory-Verbunddienste-Servern (AD FS).</span><span class="sxs-lookup"><span data-stu-id="f8e3a-116">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="f8e3a-117">Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-117">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Unterstützung von Contoso für die Verbundauthentifizierung für Kunden und Partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="f8e3a-119">AD FS-Server in der DMZ erleichtern das Authentifizieren von Kundenanmeldeinformationen durch den Identitätsanbieter für Zugriff auf die öffentliche Website und Partneranmeldeinformationen für Zugriff auf das Partnerextranet.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="f8e3a-120">Contoso hat sich entschlossen, seine Infrastruktur beizubehalten und diese für die Kunden- und Partnerauthentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="f8e3a-121">Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="f8e3a-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="f8e3a-122">Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f8e3a-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="f8e3a-123">Contoso wollte seine lokale AD DS-Gesamtstruktur für die Authentifizierung bei Microsoft 365-Cloudressourcen nutzen.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="f8e3a-124">Es entschied sich für Kennwort-Hash-Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="f8e3a-125">Bei der Kennwort-Hash-Synchronisierung wird die lokale AD DS-Gesamtstruktur mit dem Azure AD-Mandanten des Microsoft 365 Enterprise-Abonnements synchronisiert, wobei Benutzer- und Gruppenkonten und eine Hash-Version von Benutzerkontokennwörtern kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="f8e3a-126">Um die laufende Verzeichnissynchronisierung durchzuführen, hat Contoso das Azure AD Connect-Tool auf einem Server im Rechenzentrum in Paris bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="f8e3a-127">Hier sehen Sie den Server mit Azure AD Connect, das die AD DS-Gesamtstruktur von Contoso auf Änderungen abruft und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="f8e3a-129">Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="f8e3a-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="f8e3a-130">Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](identity-access-policies.md) für drei Schutzebenen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f8e3a-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="f8e3a-131">**Baseline**-Schutz gilt für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f8e3a-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="f8e3a-132">**Vertraulicher** Schutz gilt für die Geschäftsleitung und Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="f8e3a-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="f8e3a-133">**Hochgradig regulierter** Schutz gilt für bestimmte Benutzer der Finanz-, Rechts- und Forschungsabteilung, die Zugriff auf hochgradig regulierte Daten haben.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="f8e3a-134">Hier sehen Sie die resultierenden identitäts- und gerätebasierten Richtlinien für bedingten Zugriff von Contoso.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="f8e3a-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f8e3a-136">Next step</span></span>

<span data-ttu-id="f8e3a-137">[Erfahren Sie](contoso-win10.md), wie Contoso seine Microsoft Endpoint Configuration Manager-Infrastruktur verwendet, um das aktuelle Windows 10 Enterprise im gesamten Unternehmen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f8e3a-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8e3a-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8e3a-138">See also</span></span>

[<span data-ttu-id="f8e3a-139">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8e3a-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f8e3a-140">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="f8e3a-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f8e3a-141">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="f8e3a-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
