---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868028"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="f39cf-103">Identität für die Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="f39cf-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="f39cf-104">**Zusammenfassung:** Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f39cf-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="f39cf-p101">Microsoft bietet mit Azure Active Directory (AD) eine IDaaS (Identity as a Service, Identität als Dienst) in seinen Cloudangeboten. Um Microsoft 365 Enterprise einzuführen, muss für die IDaaS-Lösung von Contoso dessen lokaler Identitätsanbieter genutzt und Verbundauthentifizierung mit den vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="f39cf-107">Contosos Windows Server Active Directory-Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="f39cf-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="f39cf-p102">Contoso verwendet eine einzige Windows Server Active Directory-Gesamtstruktur für „contoso.com“ mit sieben Unterdomänen (eine für jede Region der Erde). Die Zentrale, Regionalstellen und Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="f39cf-110">Abbildung 1 zeigt die Contoso-Gesamtstruktur mit regionalen Domänen für die unterschiedlichen Regionen, die Regionalstellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f39cf-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="f39cf-111">**Abbildung 1: Gesamtstruktur und Domänen von Contoso weltweit**</span><span class="sxs-lookup"><span data-stu-id="f39cf-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="f39cf-112">Contoso möchte die Konten und Gruppen in der „contoso.com“-Gesamtstruktur zur Authentifizierung und Autorisierung seiner cloudbasierten Apps und Arbeitslasten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f39cf-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="f39cf-113">Contosos Infrastruktur der Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f39cf-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="f39cf-114">Contoso lässt Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="f39cf-114">Contoso allows:</span></span>

- <span data-ttu-id="f39cf-115">Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei ihren öffentlichen Websites anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f39cf-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="f39cf-116">Lieferanten und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partnerextranet anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f39cf-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="f39cf-p103">Abbildung 2 zeigt die Contoso-DMZ mit einer öffentlichen Website, einem Partnerextranet und einer Reihe von Active Directory Federation Services-Servern (AD FS). Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="f39cf-119">**Abbildung 2: Contosos Unterstützung für die Verbundauthentifizierung für Kunden und Partner**</span><span class="sxs-lookup"><span data-stu-id="f39cf-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="f39cf-120">AD FS-Server in der DMZ authentifizieren Kundenanmeldeinformationen für Zugriff auf die öffentliche Website und Partneranmeldeinformationen für Zugriff auf das Partnerextranet.</span><span class="sxs-lookup"><span data-stu-id="f39cf-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="f39cf-p104">Contoso hat sich entschlossen, seine Infrastruktur beizubehalten und diese für die Kunden- und Partnerauthentifizierung zu verwenden. Die Identitätsingenieure bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="f39cf-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="f39cf-123">Hybrididentität mit Durchsatzauthentifizierung für cloudbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f39cf-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="f39cf-p105">Contoso wollte seine lokale Windows Server Active Directory-Gesamtstruktur für die Authentifizierung bei Microsoft 365 nutzen. Deshalb wurde eine Durchsatzauthentifizierung mit Kennworthashsynchronisierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="f39cf-126">Durchsatzauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f39cf-126">PTA authentication</span></span>

<span data-ttu-id="f39cf-p106">Für die Authentifizierung von Benutzeranmeldeinformationen verwendet Contoso die Durchsatzauthentifizierung. Wenn ein Contoso-Benutzer auf cloudbasierte Ressourcen zugreift, werden die gesendeten Anmeldeinformationen von Azure AD an einen Server im Rechenzentrum der Contoso-Zentrale übergeben, auf dem ein Authentifizierungs-Agent ausgeführt wird. Die Benutzeranmeldeinformationen werden im Auftrag von Azure AD von einem dieser Authentifizierungsserver überprüft.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="f39cf-130">In Abbildung 3 ist eine Reihe von Servern in der Contoso-Zentrale dargestellt, auf denen der Authentifizierungs-Agent ausgeführt wird und die Authentifizierungsanforderungen verarbeiten, die ihnen von Azure AD übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="f39cf-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="f39cf-131">**Abbildung 3: Infrastruktur der Durchsatzauthentifizierung bei Contoso**</span><span class="sxs-lookup"><span data-stu-id="f39cf-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="f39cf-132">Contoso hat sich für die Durchsatzauthentifizierung entschieden, um alle Sicherheitsanforderungen zu erfüllen. Dabei werden alle Authentifizierungsversuche auf unmittelbare Änderungen an Benutzerkontostatus, Kennwortrichtlinien und Anmeldestunden überprüft, die an der lokalen Windows Server AD-Gesamtstruktur erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f39cf-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="f39cf-133">Kennworthashsynchronisierung (PHS)</span><span class="sxs-lookup"><span data-stu-id="f39cf-133">PHS</span></span>

<span data-ttu-id="f39cf-p107">Bei der Kennworthashsynchronisierung wird die lokale Windows Server AD-Gesamtstruktur mit dem Azure AD-Mandanten ihres Microsoft 365 Enterprise-Abonnements synchronisiert, wobei Benutzer- und Gruppenkonten sowie eine Hashversion von Benutzerkontokennwörtern kopiert werden. Contoso hat sich für die Kennwortsynchronisierung entschieden, um eine alternative Authentifizierungsmethode direkt mit dem Azure AD-Mandanten bereitzustellen, falls die Durchsatzauthentifizierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="f39cf-p108">Um die laufende Verzeichnissynchronisierung durchzuführen, hat Contoso das Azure AD Connect-Tool auf einem Server im Rechenzentrum in Paris bereitgestellt. Abbildung 4 zeigt die Server mit Azure AD Connect, die die Windows Server Active Directory-Gesamtstruktur von Contoso auf Änderungen abfragt und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f39cf-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="f39cf-138">**Abbildung 4: Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso**</span><span class="sxs-lookup"><span data-stu-id="f39cf-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="f39cf-139">Richtlinien für bedingten Zugriff für Identität</span><span class="sxs-lookup"><span data-stu-id="f39cf-139">Conditional access policies for identity</span></span>

<span data-ttu-id="f39cf-140">Contoso hat eine Reihe von [Richtlinien für bedingten Zugriff](identity-access-policies.md) in Azure AD erstellt, um sicherzustellen, dass eine mehrstufige Authentifizierung und Kennwortänderungen erzwungen werden, wenn Azure AD feststellt, dass ein Anmelderisiko für eine Authentifizierungsanfrage besteht.</span><span class="sxs-lookup"><span data-stu-id="f39cf-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="f39cf-141">Abbildung 5 zeigt die resultierenden Richtlinien für bedingten Zugriff für Identität.</span><span class="sxs-lookup"><span data-stu-id="f39cf-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="f39cf-142">**Abbildung 5: Identitätsbasierte Richtlinien für bedingen Zugriff**</span><span class="sxs-lookup"><span data-stu-id="f39cf-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="f39cf-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f39cf-143">Next step</span></span>

<span data-ttu-id="f39cf-144">[Erfahren Sie](contoso-win10.md), wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Windows 10 Enterprise über die Organisation hinweg bereitzustellen und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="f39cf-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f39cf-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f39cf-145">See also</span></span>

[<span data-ttu-id="f39cf-146">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f39cf-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f39cf-147">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="f39cf-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f39cf-148">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="f39cf-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
