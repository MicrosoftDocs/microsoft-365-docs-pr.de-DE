---
title: Mandanten-Roadmap für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Die Roadmap zum Einrichten Ihrer Mandanten für Microsoft 365.
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464033"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="d44b8-103">Mandanten-Roadmap für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d44b8-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="d44b8-104">Ihr Microsoft 365 Mandant ist der Satz von Diensten, die Ihrer Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="d44b8-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="d44b8-105">In der Regel ist dieser Mandant einem oder mehreren Ihrer öffentlichen DNS-Domänennamen zugeordnet und fungiert als zentraler und isolierter Container für verschiedene Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d44b8-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="d44b8-106">Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloudangebote von Microsoft.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="d44b8-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="d44b8-107">Wenn Sie einen Microsoft 365 Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu.</span><span class="sxs-lookup"><span data-stu-id="d44b8-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="d44b8-108">Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und Ihren Mandanten von einem Standort an einen anderen verschieben.</span><span class="sxs-lookup"><span data-stu-id="d44b8-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="d44b8-109">Um Ihren Mandanten für Benutzer, Gruppen, Lizenzen und Cloud-Apps vorzubereiten, ist es wichtig, Ihre Mandantenkonfiguration sorgfältig zu planen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d44b8-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="d44b8-110">Richten Sie Ihren Microsoft 365-Mandanten ein.</span><span class="sxs-lookup"><span data-stu-id="d44b8-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="d44b8-111">Nachdem Sie sichergestellt haben, dass Ihr Netzwerk für den Zugriff auf Microsoft 365 sowohl für lokale als auch für Remotemitarbeiter optimiert ist, planen und konfigurieren Sie dann Ihren Microsoft 365 Mandanten für DNS-Domänennamen, allgemeine Dienste und für diese Identitätsinfrastruktur, die die sichere Benutzeranmeldung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d44b8-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="d44b8-112">Plan</span><span class="sxs-lookup"><span data-stu-id="d44b8-112">Plan</span></span>

<span data-ttu-id="d44b8-113">So planen Sie ihre Mandantenimplementierung:</span><span class="sxs-lookup"><span data-stu-id="d44b8-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="d44b8-114">Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten</span><span class="sxs-lookup"><span data-stu-id="d44b8-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="d44b8-115">Grundlegendes zur Verwendung von SSL-Zertifikaten von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="d44b8-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="d44b8-116">Verstehen, wie ein Microsoft 365 Mandant in Azure AD-Dienste integriert ist</span><span class="sxs-lookup"><span data-stu-id="d44b8-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="d44b8-117">Planen der Client-App-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d44b8-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="d44b8-118">Bestimmen, wie die moderne Hybridauthentifizierung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="d44b8-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="d44b8-119">Planen von Upgrades für Office 2007 und Office 2010</span><span class="sxs-lookup"><span data-stu-id="d44b8-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="d44b8-120">Grundlegendes zur Mandantenisolation</span><span class="sxs-lookup"><span data-stu-id="d44b8-120">Understand tenant isolation</span></span>](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a><span data-ttu-id="d44b8-121">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="d44b8-121">Deploy</span></span>

<span data-ttu-id="d44b8-122">So stellen Sie Ihren Mandanten bereit:</span><span class="sxs-lookup"><span data-stu-id="d44b8-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="d44b8-123">Fügen Sie die [DNS-Domänen](../admin/setup/add-domain.md) für Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="d44b8-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="d44b8-124">Verwenden Sie die [Einrichtungshandbücher in der Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="d44b8-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="d44b8-125">Erstellen Sie Ihre [Identitätsinfrastruktur,](identity-roadmap-microsoft-365.md) und [sichern Sie Ihre Benutzeranmeldungen.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="d44b8-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="d44b8-126">Verschieben der geografischen Standorte eines Mandanten</span><span class="sxs-lookup"><span data-stu-id="d44b8-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="d44b8-127">Microsoft öffnet weiterhin neue geografische Standorte für Rechenzentren (Geos) für Microsoft 365 Dienste.</span><span class="sxs-lookup"><span data-stu-id="d44b8-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="d44b8-128">Diese neuen Rechenzentrumsregionen fügen Kapazität und Rechenressourcen hinzu, um die Kundenanforderungen und das Wachstum der Nutzung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d44b8-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="d44b8-129">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="d44b8-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="d44b8-130">Weitere Informationen finden Sie unter [Verschieben von Kerndaten in neue Microsoft 365 Rechenzentrumsregionen.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="d44b8-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="d44b8-131">Bereitstellen von Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="d44b8-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="d44b8-132">Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.</span><span class="sxs-lookup"><span data-stu-id="d44b8-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="d44b8-133">Mehr dazu unter [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="d44b8-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="d44b8-134">Verwalten mehrerer Microsoft 365 Mandanten</span><span class="sxs-lookup"><span data-stu-id="d44b8-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="d44b8-135">Obwohl ein einzelner Mandant für Ihre Organisation ideal ist, können Sie eine von vielen Organisationen mit mehreren Mandanten sein.</span><span class="sxs-lookup"><span data-stu-id="d44b8-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="d44b8-136">Gründe können Fusionen und Käufe sein, Sie möchten eine administrative Isolation oder eine dezentralisierte IT.</span><span class="sxs-lookup"><span data-stu-id="d44b8-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="d44b8-137">Wenn Sie über mehrere Microsoft 365 Mandanten verfügen, finden Sie in den folgenden Artikeln weitere Informationen zu:</span><span class="sxs-lookup"><span data-stu-id="d44b8-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="d44b8-138">Zusammenarbeit zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="d44b8-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="d44b8-139">Mandantenübergreifende Postfachmigration</span><span class="sxs-lookup"><span data-stu-id="d44b8-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="d44b8-140">Migrationen zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="d44b8-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="d44b8-141">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d44b8-141">Next step</span></span>

<span data-ttu-id="d44b8-142">Beginnen Sie ihre Mandantenplanung mit [Abonnements, Lizenzen, Konten und Mandanten.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="d44b8-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>