---
title: Mandanten-Roadmap für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Die Roadmap zum Einrichten Ihrer Mandanten für Microsoft 365.
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446007"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="b3164-103">Mandanten-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3164-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="b3164-104">Ihr Microsoft 365-Mandant ist die Gruppe von Diensten, die Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="b3164-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="b3164-105">Normalerweise ist dieser Mandant einem oder mehreren Ihrer DNS-Domänennamen zugeordnet und fungiert als zentraler Container für unterschiedliche Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b3164-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="b3164-106">Wenn Sie einen Microsoft 365-Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu.</span><span class="sxs-lookup"><span data-stu-id="b3164-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="b3164-107">Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und den Mandanten von einem Standort an einen anderen Speicherort verlagern.</span><span class="sxs-lookup"><span data-stu-id="b3164-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="b3164-108">Um ihren Mandanten für die grundlegenden Dienste von Netzwerk und Identität vorzubereiten, ist es wichtig, die Mandanten Konfiguration sorgfältig zu planen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3164-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="b3164-109">Plan</span><span class="sxs-lookup"><span data-stu-id="b3164-109">Plan</span></span>

<span data-ttu-id="b3164-110">So planen Sie die Implementierung Ihres Mandanten:</span><span class="sxs-lookup"><span data-stu-id="b3164-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="b3164-111">Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten</span><span class="sxs-lookup"><span data-stu-id="b3164-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="b3164-112">Grundlegendes zur Verwendung von Drittanbieter-SSL-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b3164-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="b3164-113">Grundlegendes zu den Möglichkeiten, mit denen ein Microsoft 365-Mandant in Azure AD Dienste integriert ist</span><span class="sxs-lookup"><span data-stu-id="b3164-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="b3164-114">Planen der Client-App-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="b3164-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="b3164-115">Bestimmen der Verwendung der modernen Hybrid Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b3164-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="b3164-116">Planen von Office 2007-und Office 2010 Upgrades</span><span class="sxs-lookup"><span data-stu-id="b3164-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="b3164-117">Grundlegendes zur Mandanten Isolierung</span><span class="sxs-lookup"><span data-stu-id="b3164-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="b3164-118">Abrufen der Details zu Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="b3164-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="b3164-119">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b3164-119">Deploy</span></span>

<span data-ttu-id="b3164-120">Um ihren Mandanten bereitzustellen, [fügen Sie die DNS-Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) für Ihre Organisation hinzu, und verwenden Sie die [Setup Handbücher im Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="b3164-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="b3164-121">Mandanten mit mehreren geografischen Standorten</span><span class="sxs-lookup"><span data-stu-id="b3164-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="b3164-122">Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.</span><span class="sxs-lookup"><span data-stu-id="b3164-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="b3164-123">Informationen zu Microsoft 365 Multi-Geo, einschließlich der Planung, Konfiguration und Verwaltung, finden Sie [hier](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="b3164-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="b3164-124">Migrieren der geografischen Standorte eines Mandanten</span><span class="sxs-lookup"><span data-stu-id="b3164-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="b3164-125">Microsoft öffnet weiterhin die neuen geografischen Standorte für das Rechenzentrum (GEOS) für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="b3164-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="b3164-126">In diesem neuen Datencenter-GEOS wird Kapazität hinzugefügt und Ressourcen zur Unterstützung von Kundenanforderungen und Nutzungs Wachstum berechnet.</span><span class="sxs-lookup"><span data-stu-id="b3164-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="b3164-127">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="b3164-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="b3164-128">Informationen zu Microsoft 365 Datacenter Geo, einschließlich der Vorgehensweise zum Anfordern einer Geo-Datenverlagerung, [finden Sie hier](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="b3164-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="b3164-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b3164-129">Next step</span></span>

<span data-ttu-id="b3164-130">Starten Sie Ihre Mandanten Planung mit [Abonnements, Lizenzen, Konten und Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="b3164-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

