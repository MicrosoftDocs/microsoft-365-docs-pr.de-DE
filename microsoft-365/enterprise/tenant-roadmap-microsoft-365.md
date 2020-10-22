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
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656007"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="2887c-103">Mandanten-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2887c-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="2887c-104">Ihr Microsoft 365-Mandant ist die Gruppe von Diensten, die Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2887c-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="2887c-105">Normalerweise ist dieser Mandant einem oder mehreren Ihrer DNS-Domänennamen zugeordnet und fungiert als zentraler Container für unterschiedliche Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2887c-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="2887c-106">Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloud-Angebote von Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="2887c-107">Wenn Sie einen Microsoft 365-Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu.</span><span class="sxs-lookup"><span data-stu-id="2887c-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="2887c-108">Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und den Mandanten von einem Standort an einen anderen Speicherort verlagern.</span><span class="sxs-lookup"><span data-stu-id="2887c-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="2887c-109">Um ihren Mandanten für die Identität vorzubereiten, ist es wichtig, die Mandanten Konfiguration sorgfältig zu planen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2887c-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="2887c-110">Einrichten Ihres Microsoft 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="2887c-111">Nachdem Sie sichergestellt haben, dass Ihr Netzwerk für den Zugriff auf Microsoft 365 sowohl für lokale als auch für Remotemitarbeiter optimiert ist, planen und konfigurieren Sie Ihren Microsoft 365-Mandanten für DNS-Domänennamen, gemeinsame Dienste und für diese Identitätsinfrastruktur, die die sichere Benutzeranmeldung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2887c-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="2887c-112">Plan</span><span class="sxs-lookup"><span data-stu-id="2887c-112">Plan</span></span>

<span data-ttu-id="2887c-113">So planen Sie die Implementierung Ihres Mandanten:</span><span class="sxs-lookup"><span data-stu-id="2887c-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="2887c-114">Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="2887c-115">Grundlegendes zur Verwendung von Drittanbieter-SSL-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2887c-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="2887c-116">Grundlegendes zu den Möglichkeiten, mit denen ein Microsoft 365-Mandant in Azure AD Dienste integriert ist</span><span class="sxs-lookup"><span data-stu-id="2887c-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="2887c-117">Planen der Client-App-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="2887c-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="2887c-118">Bestimmen der Verwendung der modernen Hybrid Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2887c-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="2887c-119">Planen von Office 2007-und Office 2010 Upgrades</span><span class="sxs-lookup"><span data-stu-id="2887c-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="2887c-120">Grundlegendes zur Mandanten Isolierung</span><span class="sxs-lookup"><span data-stu-id="2887c-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="2887c-121">Abrufen der Details zu Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="2887c-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="2887c-122">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="2887c-122">Deploy</span></span>

<span data-ttu-id="2887c-123">So stellen Sie den Mandanten bereit:</span><span class="sxs-lookup"><span data-stu-id="2887c-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="2887c-124">Fügen Sie die [DNS-Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) für Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="2887c-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="2887c-125">Verwenden Sie die [Installationshandbücher im Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="2887c-126">Erstellen Sie Ihre [Identitätsinfrastruktur](identity-roadmap-microsoft-365.md) , und [Sichern Sie Ihre Benutzeranmeldungen](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="2887c-127">Migrieren der geografischen Standorte eines Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="2887c-128">Microsoft öffnet weiterhin die neuen geografischen Standorte für das Rechenzentrum (GEOS) für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="2887c-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="2887c-129">In diesem neuen Datencenter-GEOS wird Kapazität hinzugefügt und Ressourcen zur Unterstützung von Kundenanforderungen und Nutzungs Wachstum berechnet.</span><span class="sxs-lookup"><span data-stu-id="2887c-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="2887c-130">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="2887c-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="2887c-131">Weitere Informationen finden Sie unter [Moving Core Data to New Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="2887c-132">Bereitstellen von Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="2887c-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="2887c-133">Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.</span><span class="sxs-lookup"><span data-stu-id="2887c-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="2887c-134">Weitere Informationen finden Sie unter [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="2887c-135">Verwalten mehrerer Microsoft 365 Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="2887c-136">Obwohl ein einzelner Mandant für Ihre einer Organisation ideal ist, sind Sie möglicherweise eine von vielen Organisationen mit mehreren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2887c-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="2887c-137">Gründe für mehrere Mandanten können Fusionen und Übernahmen umfassen, Sie möchten eine administrative Isolierung oder eine dezentrale IT-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="2887c-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="2887c-138">Wenn Sie mehrere Microsoft 365-Mandanten haben, lesen Sie diese Artikel, um weitere Informationen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="2887c-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="2887c-139">Zusammenarbeit zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="2887c-140">Mandantenübergreifende Postfachmigration</span><span class="sxs-lookup"><span data-stu-id="2887c-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="2887c-141">Migrationen zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="2887c-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="2887c-142">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2887c-142">Next step</span></span>

<span data-ttu-id="2887c-143">Starten Sie Ihre Mandanten Planung mit [Abonnements, Lizenzen, Konten und Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="2887c-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
