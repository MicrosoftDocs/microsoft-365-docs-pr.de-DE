---
title: Schutz von Benutzer- und Gerätezugriff
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Startseite zum Schützen des Zugriffs auf Microsoft 365-Daten und-Dienste
ms.openlocfilehash: 4d09ee0aa0ef36222ae0d238b0e7a44ee23994d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632210"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="93aee-103">Schutz von Benutzer- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="93aee-103">Protect user and device access</span></span>

<span data-ttu-id="93aee-104">Der Schutz des Zugriffs auf Ihre Microsoft 365-Daten und-Dienste ist für die Verteidigung gegen Cyberangriffe und den Schutz vor Datenverlusten entscheidend.</span><span class="sxs-lookup"><span data-stu-id="93aee-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="93aee-105">Derselbe Schutz kann auf andere SaaS-Anwendungen in Ihrer Umgebung und sogar auf lokale Anwendungen angewendet werden, die mit Azure Active Directory Application Proxy veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="93aee-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="93aee-106">Schritt 1: Überprüfen der Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="93aee-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="93aee-107">Empfohlene Funktionen zum Schutz von Identitäten und Geräten, die auf Office 365, andere SaaS-Dienste und lokale Anwendungen zugreifen, die mit dem Azure AD-Anwendungsproxy veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="93aee-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="93aee-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="93aee-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="93aee-109">Schritt 2: Schützen von Administratorkonten und Zugriff</span><span class="sxs-lookup"><span data-stu-id="93aee-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="93aee-110">Die Administratorkonten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, umfassen erweiterte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="93aee-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="93aee-111">Dies sind wertvolle Ziele für Hacker und cyberattackers.</span><span class="sxs-lookup"><span data-stu-id="93aee-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="93aee-112">Verwenden Sie zunächst Administratorkonten nur für die Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="93aee-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="93aee-113">Administratoren sollten über ein separates Benutzerkonto für reguläre, nicht administrative Zwecke verfügen und bei Bedarf nur Ihr Administratorkonto verwenden, um eine Aufgabe abzuschließen, die ihrer Auftragsfunktion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="93aee-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="93aee-114">Schützen Sie Ihre Administratorkonten mit mehrstufiger Authentifizierung und bedingtem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="93aee-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="93aee-115">Weitere Informationen finden Sie unter [Protecting Administrator Accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="93aee-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="93aee-116">Konfigurieren Sie als nächstes die privilegierte Zugriffsverwaltung in Office 365.</span><span class="sxs-lookup"><span data-stu-id="93aee-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="93aee-117">Die privilegierte Zugriffsverwaltung ermöglicht eine granulare Zugriffssteuerung über privilegierte Verwaltungsaufgaben in Office 365.</span><span class="sxs-lookup"><span data-stu-id="93aee-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="93aee-118">Damit können Sie Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit dem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="93aee-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="93aee-119">Übersicht über die Verwaltung privilegierter Zugriffsrechte</span><span class="sxs-lookup"><span data-stu-id="93aee-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="93aee-120">Konfigurieren von Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="93aee-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="93aee-121">Eine weitere wichtige Empfehlung ist die Verwendung von Workstations, die speziell für administrative Arbeiten konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="93aee-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="93aee-122">Hierbei handelt es sich um dedizierte Geräte, die nur für administrative Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93aee-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="93aee-123">Siehe [Sichern von privilegiertem Zugriff](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="93aee-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="93aee-124">Schließlich können Sie die Auswirkungen von versehentlichem Mangel an administrativem Zugriff verringern, indem Sie zwei oder mehr Notfall Zugriffskonten in Ihrem Mandanten erstellen.</span><span class="sxs-lookup"><span data-stu-id="93aee-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="93aee-125">Weitere Informationen finden Sie unter [Verwalten von Notfall Zugriffskonten in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="93aee-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="93aee-126">Schritt 3: Konfigurieren der empfohlenen Richtlinien für Identitäts-und Geräte Zugriff</span><span class="sxs-lookup"><span data-stu-id="93aee-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="93aee-127">Mehrstufige Authentifizierung (MFA) und Richtlinien für bedingten Zugriff sind leistungsstarke Tools zur Minderung von kompromittierten Konten und nicht autorisiertem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="93aee-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="93aee-128">Es wird empfohlen, eine Reihe von Richtlinien zu implementieren, die gemeinsam getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="93aee-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="93aee-129">Weitere Informationen, einschließlich Bereitstellungsschritten, finden Sie unter [Identity and Device Access Configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span><span class="sxs-lookup"><span data-stu-id="93aee-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="93aee-130">Diese Richtlinien implementieren die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="93aee-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="93aee-131">Mult-Factor-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="93aee-131">Mult-factor authentication</span></span>
- <span data-ttu-id="93aee-132">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="93aee-132">Conditional access</span></span>
- <span data-ttu-id="93aee-133">InTune-App-Schutz (app und Datenschutz für Geräte)</span><span class="sxs-lookup"><span data-stu-id="93aee-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="93aee-134">Intune-Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="93aee-134">Intune device compliance</span></span>
- <span data-ttu-id="93aee-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="93aee-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="93aee-136">Die Implementierung der InTune-Gerätekompatibilität erfordert die Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="93aee-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="93aee-137">Durch die Verwaltung von Geräten können Sie sicherstellen, dass Sie ordnungsgemäß und kompatibel sind, bevor Sie Ihnen den Zugriff auf Ressourcen in Ihrer Umgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="93aee-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="93aee-138">Siehe [Registrieren von Geräten für die Verwaltung in InTune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="93aee-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="93aee-139">Schritt 4: Konfigurieren von SharePoint-Gerätezugriffs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="93aee-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="93aee-140">Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng reglementierten Inhalten mit Gerätezugriffs Steuerelementen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="93aee-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="93aee-141">Weitere Informationen finden Sie unter [Richtlinien Empfehlungen für das Sichern von SharePoint-Websites und-Dateien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="93aee-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

