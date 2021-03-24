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
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051520"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="442fe-103">Identität für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="442fe-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="442fe-104">Microsoft stellt Identity as a Service (IDaaS) über seine Cloudangebote über Azure Active Directory (Azure AD) bereit.</span><span class="sxs-lookup"><span data-stu-id="442fe-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="442fe-105">Um Microsoft 365 enterprise zu übernehmen, musste die Contoso IDaaS-Lösung ihren lokalen Identitätsanbieter verwenden und die Verbundauthentifizierung mit ihren vorhandenen vertrauenswürdigen Identitätsanbietern von Drittanbietern umfassen.</span><span class="sxs-lookup"><span data-stu-id="442fe-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="442fe-106">Die Gesamtstruktur "Contoso Active Directory Domain Services"</span><span class="sxs-lookup"><span data-stu-id="442fe-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="442fe-107">Contoso verwendet eine einzelne Active Directory Domain Services (AD DS)-Gesamtstruktur für contoso com mit sieben Unterdomänen, eine für jede Region \. der Welt.</span><span class="sxs-lookup"><span data-stu-id="442fe-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="442fe-108">Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="442fe-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="442fe-109">Hier sehen Sie die Contoso-Gesamtstruktur mit regionalen Domänen für die verschiedenen Teile der Welt, die regionale Hubs enthalten.</span><span class="sxs-lookup"><span data-stu-id="442fe-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Gesamtstruktur und Domänen von Contoso weltweit](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="442fe-111">Contoso hat beschlossen, die Konten und Gruppen in der contoso com-Gesamtstruktur für die Authentifizierung und Autorisierung für seine \. Microsoft 365-Workloads und -Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="442fe-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="442fe-112">Die Contoso-Verbundauthentifizierungsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="442fe-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="442fe-113">Contoso lässt Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="442fe-113">Contoso allows:</span></span>

- <span data-ttu-id="442fe-114">Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei der öffentlichen Website des Unternehmens zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="442fe-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="442fe-115">Anbieter und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partner-Extranet des Unternehmens zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="442fe-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="442fe-116">Hier sehen Sie die Contoso-DMZ mit einer öffentlichen Website, einem Partner-Extranet und einer Reihe von Active Directory Federation Services (AD FS)-Servern.</span><span class="sxs-lookup"><span data-stu-id="442fe-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="442fe-117">Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="442fe-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso-Unterstützung für die Verbundauthentifizierung für Kunden und Partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="442fe-119">AD FS-Server in der DMZ erleichtern die Authentifizierung von Kundenanmeldeinformationen durch ihre Identitätsanbieter für den Zugriff auf die öffentliche Website und Partneranmeldeinformationen für den Zugriff auf das Partner-Extranet.</span><span class="sxs-lookup"><span data-stu-id="442fe-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="442fe-120">Contoso hat beschlossen, diese Infrastruktur zu behalten und sie der Kunden- und Partnerauthentifizierung zu widmen.</span><span class="sxs-lookup"><span data-stu-id="442fe-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="442fe-121">Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](/azure/active-directory/b2b/hybrid-organizations) und [B2C](/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="442fe-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="442fe-122">Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="442fe-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="442fe-123">Contoso wollte seine lokale AD DS-Gesamtstruktur für die Authentifizierung bei Microsoft 365-Cloudressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="442fe-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="442fe-124">Sie hat sich für die Verwendung der Kennworthashsynchronisierung (Password Hash Synchronization, PHS) entschieden.</span><span class="sxs-lookup"><span data-stu-id="442fe-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="442fe-125">PHS synchronisiert die lokale AD #A0 mit dem Azure #A1 ihres Microsoft 365 #A1 und kopiert Benutzer- und Gruppenkonten sowie eine Hashversion von Benutzerkontenkennwörtern.</span><span class="sxs-lookup"><span data-stu-id="442fe-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="442fe-126">Für die Verzeichnissynchronisierung hat Contoso das Azure AD Connect-Tool auf einem Server im Pariser Rechenzentrum bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="442fe-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="442fe-127">Hier ist der Server, auf dem Azure AD Connect ausgeführt wird, der die Contoso AD DS-Gesamtstruktur auf Änderungen abruft und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="442fe-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Die Contoso PHS-Verzeichnissynchronisierungsinfrastruktur](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="442fe-129">Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="442fe-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="442fe-130">Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](../security/defender-365-security/identity-access-policies.md) für drei Schutzebenen erstellt:</span><span class="sxs-lookup"><span data-stu-id="442fe-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/defender-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="442fe-131">*Grundlegende* Schutzbestimmungen gelten für alle Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="442fe-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="442fe-132">*Vertrauliche* Schutzmaßnahmen gelten für leitende Führungskräfte und Führungskräfte.</span><span class="sxs-lookup"><span data-stu-id="442fe-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="442fe-133">*Streng regulierte* Schutzbestimmungen gelten für bestimmte Benutzer in den Finanz-, Rechts- und Forschungsabteilungen, die Zugriff auf streng regulierte Daten haben.</span><span class="sxs-lookup"><span data-stu-id="442fe-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="442fe-134">Hier sehen Sie den resultierenden Satz von Richtlinien für den bedingten Zugriff für Contoso-Identität und Geräte.</span><span class="sxs-lookup"><span data-stu-id="442fe-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="442fe-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="442fe-136">Next step</span></span>

<span data-ttu-id="442fe-137">Erfahren Sie, wie Contoso seine Microsoft Endpoint Configuration Manager-Infrastruktur verwendet, um [Windows 10 Enterprise](contoso-win10.md) in der gesamten Organisation zu bereitstellen und auf dem aktuellen Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="442fe-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="442fe-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="442fe-138">See also</span></span>

[<span data-ttu-id="442fe-139">Identitäts-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="442fe-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="442fe-140">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="442fe-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="442fe-141">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="442fe-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)