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
description: Erfahren Sie, wie Sie den Benutzer- und Gerätezugriff auf Microsoft 365-Daten und -Dienste schützen und vor Datenverlust schützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051697"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="4c235-103">Schutz von Benutzer- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="4c235-103">Protect user and device access</span></span>

<span data-ttu-id="4c235-104">Der Schutz des Zugriffs auf Ihre Microsoft 365-Daten und -Dienste ist entscheidend für die Verteidigung vor Cyberangriffen und den Schutz vor Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="4c235-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="4c235-105">Dieselben Schutzmaßnahmen können auch auf andere SaaS-Anwendungen in Ihrer Umgebung und sogar auf lokale Anwendungen angewendet werden, die mit dem Azure Active Directory-Anwendungsproxy veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="4c235-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="4c235-106">Schritt 1: Überprüfen von Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4c235-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="4c235-107">Empfohlene Funktionen zum Schutz von Identitäten und Geräten, die auf Office 365, andere SaaS-Dienste und lokale Anwendungen zugreifen, die mit dem Azure AD-Anwendungsproxy veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4c235-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="4c235-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="4c235-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="4c235-109">Schritt 2: Schützen von Administratorkonten und Zugriff</span><span class="sxs-lookup"><span data-stu-id="4c235-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="4c235-110">Die administrativen Konten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, enthalten erhöhte Rechte.</span><span class="sxs-lookup"><span data-stu-id="4c235-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="4c235-111">Dies sind wertvolle Ziele für Hacker und Cyberangriffe.</span><span class="sxs-lookup"><span data-stu-id="4c235-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="4c235-112">Verwenden Sie zunächst nur Administratorkonten für die Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="4c235-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="4c235-113">Administratoren sollten über ein separates Benutzerkonto für die reguläre, nicht administrative Verwendung verfügen und ihr Administratorkonto nur verwenden, wenn dies erforderlich ist, um eine Aufgabe auszuführen, die mit ihrer Auftragsfunktion verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="4c235-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="4c235-114">Schützen Sie Ihre Administratorkonten mit mehrstufiger Authentifizierung und bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="4c235-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="4c235-115">Weitere Informationen finden Sie unter [Schützen von Administratorkonten](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="4c235-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="4c235-116">Konfigurieren Sie als Nächstes die Verwaltung des privilegierten Zugriffs in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c235-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="4c235-117">Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c235-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="4c235-118">Sie kann Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4c235-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="4c235-119">Übersicht über die Verwaltung privilegierter Zugriffe</span><span class="sxs-lookup"><span data-stu-id="4c235-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="4c235-120">Konfigurieren von Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="4c235-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="4c235-121">Eine weitere empfehlung ist die Verwendung von Arbeitsstationen, die speziell für administrative Arbeit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4c235-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="4c235-122">Dies sind dedizierte Geräte, die nur für Administrative Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c235-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="4c235-123">Weitere [Informationen finden Sie unter Schützen des privilegierten Zugriffs](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="4c235-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="4c235-124">Schließlich können Sie die Auswirkungen eines unbeabsichtigten Mangels an Administrativem Zugriff verringern, indem Sie zwei oder mehr Notfallzugriffskonten in Ihrem Mandanten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c235-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="4c235-125">Weitere [Informationen finden Sie unter Verwalten von Notfallzugriffskonten in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="4c235-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="4c235-126">Schritt 3: Konfigurieren empfohlener Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4c235-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="4c235-127">Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und Richtlinien für bedingten Zugriff sind leistungsstarke Tools zur Minderung von kompromittierten Konten und nicht autorisiertem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="4c235-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="4c235-128">Es wird empfohlen, eine Reihe von Richtlinien zu implementieren, die gemeinsam getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="4c235-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="4c235-129">Weitere Informationen, einschließlich bereitstellungsschritten, finden Sie unter [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4c235-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="4c235-130">Diese Richtlinien implementieren die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4c235-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="4c235-131">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4c235-131">Mult-factor authentication</span></span>
- <span data-ttu-id="4c235-132">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="4c235-132">Conditional access</span></span>
- <span data-ttu-id="4c235-133">Intune-App-Schutz (App- und Datenschutz für Geräte)</span><span class="sxs-lookup"><span data-stu-id="4c235-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="4c235-134">Intune-Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="4c235-134">Intune device compliance</span></span>
- <span data-ttu-id="4c235-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="4c235-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="4c235-136">Für die Implementierung der Intune-Gerätekonformität ist die Geräteregistrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c235-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="4c235-137">Mit der Verwaltung von Geräten können Sie sicherstellen, dass sie fehlerfrei und kompatibel sind, bevor sie Zugriff auf Ressourcen in Ihrer Umgebung erhalten.</span><span class="sxs-lookup"><span data-stu-id="4c235-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="4c235-138">Siehe [Registrieren von Geräten für die Verwaltung in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="4c235-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="4c235-139">Schritt 4: Konfigurieren von SharePoint-Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4c235-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="4c235-140">Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng regulierten Inhalten mit Gerätezugriffssteuerelementen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4c235-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="4c235-141">Weitere Informationen finden Sie unter [Richtlinienempfehlungen zum Sichern von SharePoint-Websites und -Dateien](../security/defender-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4c235-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



