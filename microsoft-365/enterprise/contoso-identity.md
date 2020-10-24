---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754641"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="5e3fd-103">Identität für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="5e3fd-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="5e3fd-104">Microsoft stellt Identity as a Service (IDaaS) in seinen Cloud-angeboten über Azure Active Directory (Azure AD) bereit.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5e3fd-105">Um Microsoft 365 für Unternehmen zu verabschieden, musste die Contoso-IDaaS-Lösung Ihren lokalen Identitätsanbieter verwenden und die Verbundauthentifizierung mit Ihren vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einschließen.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="5e3fd-106">Die Contoso Active Directory-Domänendienste Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="5e3fd-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="5e3fd-107">Contoso verwendet eine einzelne Active Directory-Domänendienste (AD DS) Gesamtstruktur für Contoso \. com mit sieben Unterdomänen, eine für jede Region der Welt.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="5e3fd-108">Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="5e3fd-109">Hier ist die Contoso-Gesamtstruktur mit regionalen Domänen für die verschiedenen Teile der Welt, die regionale Hubs enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Gesamtstruktur und Domänen von Contoso weltweit](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="5e3fd-111">Contoso hat beschlossen, die Konten und Gruppen in der Contoso \. -com-Gesamtstruktur zur Authentifizierung und Autorisierung für seine Microsoft 365-Arbeitslasten und-Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="5e3fd-112">Die Contoso-Verbund Authentifizierungsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="5e3fd-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="5e3fd-113">Contoso lässt Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="5e3fd-113">Contoso allows:</span></span>

- <span data-ttu-id="5e3fd-114">Kunden, Ihre Microsoft-, Facebook-oder Google Mail-Konten zu verwenden, um sich bei der öffentlichen Website des Unternehmens anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="5e3fd-115">Kreditoren und Partner, die ihre LinkedIn-, Salesforce-oder Google Mail-Konten verwenden, um sich beim Partner-Extranet des Unternehmens anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="5e3fd-116">Hier ist die Contoso-DMZ mit einer öffentlichen Website, einem Partner-Extranet und einer Reihe von Active Directory-Verbunddienste-Servern (AD FS).</span><span class="sxs-lookup"><span data-stu-id="5e3fd-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="5e3fd-117">Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso-Unterstützung für die Verbundauthentifizierung für Kunden und Partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="5e3fd-119">AD FS-Server in der DMZ erleichtern die Authentifizierung von Kunden Anmeldeinformationen durch ihre Identitätsanbieter für den Zugriff auf die öffentliche Website und Partner Anmeldeinformationen für den Zugriff auf das Partner-Extranet.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="5e3fd-120">Contoso hat beschlossen, diese Infrastruktur beizubehalten und für die Authentifizierung von Kunden und Partnern zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="5e3fd-121">Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="5e3fd-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="5e3fd-122">Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5e3fd-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="5e3fd-123">Contoso wollte seine lokale AD DS Gesamtstruktur für die Authentifizierung von Microsoft 365 Cloud-Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="5e3fd-124">Sie hat sich für die Verwendung der Kennworthash Synchronisierung (PHS) entschieden.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="5e3fd-125">PHS synchronisiert die lokale AD DS Gesamtstruktur mit dem Azure AD Mandanten Ihres Microsoft 365 for Enterprise-Abonnements und kopiert Benutzer-und Gruppenkonten sowie eine gehashte Version der Kennwörter für Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="5e3fd-126">Um die Verzeichnissynchronisierung durchführen zu können, hat Contoso das Azure AD Connect-Tool auf einem Server in seinem Pariser Datencenter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="5e3fd-127">Hier ist der Server, auf dem Azure AD Connect die Contoso AD DS-Gesamtstruktur für Änderungen abruft und diese Änderungen dann mit dem Azure AD Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Die Contoso-Verzeichnis Synchronisierungs Infrastruktur für PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="5e3fd-129">Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="5e3fd-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="5e3fd-130">Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](identity-access-policies.md) für drei Schutzebenen erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e3fd-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="5e3fd-131">*Basis* Schutz gilt für alle Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="5e3fd-132">*Vertrauliche* Schutzmaßnahmen gelten für Führungskräfte und Führungskräfte.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="5e3fd-133">*Streng geregelte* Schutzmaßnahmen gelten für bestimmte Benutzer in den Abteilungen Finanzen, Recht und Forschung, die Zugriff auf streng geregelte Daten haben.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="5e3fd-134">Im folgenden finden Sie eine Reihe von Contoso-Identitäts-und Geräte bedingten Zugriffsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="5e3fd-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5e3fd-136">Next step</span></span>

<span data-ttu-id="5e3fd-137">Erfahren Sie, wie Contoso seine Microsoft Endpoint Configuration Manager-Infrastruktur für die [Bereitstellung und Verwaltung von Windows 10 Enterprise](contoso-win10.md) in seiner Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e3fd-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e3fd-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e3fd-138">See also</span></span>

[<span data-ttu-id="5e3fd-139">Identitäts-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e3fd-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5e3fd-140">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5e3fd-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5e3fd-141">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="5e3fd-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
