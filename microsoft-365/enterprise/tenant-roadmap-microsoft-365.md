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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Die Roadmap zum Einrichten Ihrer Mandanten für Microsoft 365.
ms.openlocfilehash: 7834e8b7f9ff8a1b33f2f2a7ccc4a499e4da7c69
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775147"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="3ed01-103">Mandanten-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ed01-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="3ed01-104">Ihr Microsoft 365-Mandant ist die Gruppe von Diensten, die Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3ed01-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="3ed01-105">Normalerweise ist dieser Mandant einem oder mehreren Ihrer DNS-Domänennamen zugeordnet und fungiert als zentraler Container für unterschiedliche Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3ed01-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="3ed01-106">Wenn Sie einen Microsoft 365-Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu.</span><span class="sxs-lookup"><span data-stu-id="3ed01-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="3ed01-107">Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und den Mandanten von einem Standort an einen anderen Speicherort verlagern.</span><span class="sxs-lookup"><span data-stu-id="3ed01-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="3ed01-108">Um ihren Mandanten für die grundlegenden Dienste von Netzwerk und Identität vorzubereiten, ist es wichtig, die Mandanten Konfiguration sorgfältig zu planen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3ed01-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="3ed01-109">Plan</span><span class="sxs-lookup"><span data-stu-id="3ed01-109">Plan</span></span>

<span data-ttu-id="3ed01-110">So planen Sie die Implementierung Ihres Mandanten:</span><span class="sxs-lookup"><span data-stu-id="3ed01-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="3ed01-111">Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten</span><span class="sxs-lookup"><span data-stu-id="3ed01-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="3ed01-112">Grundlegendes zur Verwendung von Drittanbieter-SSL-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="3ed01-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="3ed01-113">Access-Setup Handbücher im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="3ed01-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="3ed01-114">Grundlegendes zu den Möglichkeiten, mit denen ein Microsoft 365-Mandant in Azure AD Dienste integriert ist</span><span class="sxs-lookup"><span data-stu-id="3ed01-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="3ed01-115">Planen der Client-App-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="3ed01-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="3ed01-116">Bestimmen der Verwendung der modernen Hybrid Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3ed01-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="3ed01-117">Planen von Office 2007-und Office 2010 Upgrades</span><span class="sxs-lookup"><span data-stu-id="3ed01-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="3ed01-118">Grundlegendes zur Mandanten Isolierung</span><span class="sxs-lookup"><span data-stu-id="3ed01-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="3ed01-119">Abrufen der Details zu Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="3ed01-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="3ed01-120">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="3ed01-120">Deploy</span></span>

<span data-ttu-id="3ed01-121">Um ihren Mandanten bereitzustellen, [fügen Sie die DNS-Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) für Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ed01-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="3ed01-122">Mandanten mit mehreren geografischen Standorten</span><span class="sxs-lookup"><span data-stu-id="3ed01-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="3ed01-123">Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.</span><span class="sxs-lookup"><span data-stu-id="3ed01-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="3ed01-124">Informationen zu Microsoft 365 Multi-Geo, einschließlich der Planung, Konfiguration und Verwaltung, finden Sie [hier](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="3ed01-124">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="3ed01-125">Migrieren der geografischen Standorte eines Mandanten</span><span class="sxs-lookup"><span data-stu-id="3ed01-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="3ed01-126">Microsoft öffnet weiterhin die neuen geografischen Standorte für das Rechenzentrum (GEOS) für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="3ed01-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="3ed01-127">In diesem neuen Datencenter-GEOS wird Kapazität hinzugefügt und Ressourcen zur Unterstützung von Kundenanforderungen und Nutzungs Wachstum berechnet.</span><span class="sxs-lookup"><span data-stu-id="3ed01-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="3ed01-128">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="3ed01-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="3ed01-129">Informationen zu Microsoft 365 Datacenter Geo, einschließlich der Vorgehensweise zum Anfordern einer Geo-Datenverlagerung, [finden Sie hier](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="3ed01-129">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="3ed01-130">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3ed01-130">Next step</span></span>

<span data-ttu-id="3ed01-131">Starten Sie Ihre Mandanten Planung mit [Abonnements, Lizenzen, Konten und Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="3ed01-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

