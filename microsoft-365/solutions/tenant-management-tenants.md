---
title: Schritt 1. Ihre Microsoft 365 für Enterprise-Mandanten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Bereitstellen und Verwalten einzelner oder Microsoft 365 Mandanten mit Optionen für Multi-Geo- und verschiebende Standorte.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406384"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="6fb5c-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-104">Step 1.</span></span> <span data-ttu-id="6fb5c-105">Ihre Microsoft 365 für Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="6fb5c-106">Eine Ihrer ersten Mandantenentscheidungen ist, wie viele sie haben müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="6fb5c-107">Jeder Microsoft 365 Mandanten ist unterschiedlich, eindeutig und von allen anderen Mandanten Microsoft 365 getrennt.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="6fb5c-108">Der entsprechende Azure AD-Mandant ist auch unterschiedlich, eindeutig und von allen anderen mandanten Microsoft 365 getrennt.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="6fb5c-109">Einzelner Mandant</span><span class="sxs-lookup"><span data-stu-id="6fb5c-109">Single tenant</span></span>
<span data-ttu-id="6fb5c-110">Die Verwendung eines einzelnen Mandanten vereinfacht viele Aspekte der Verwendung von Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="6fb5c-111">Ein einzelner Mandant bedeutet einen einzelnen Azure AD-Mandanten mit einem einzigen Satz von Konten, Gruppen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="6fb5c-112">Berechtigungen und die Freigabe von Ressourcen in Ihrer Organisation können über diesen zentralen Identitätsanbieter durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="6fb5c-113">Ein einzelner Mandant bietet den Benutzern die funktionsreichste und vereinfachte Zusammenarbeit und Produktivität.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="6fb5c-114">Im Folgenden finden Sie ein Beispiel, das den Standardspeicherort und den Azure AD-Mandanten eines Microsoft 365 zeigt.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Ein einzelner Microsoft 365 mandanten mit seinem Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="6fb5c-116">Mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-116">Multiple tenants</span></span>

<span data-ttu-id="6fb5c-117">Es gibt viele Gründe, warum Ihre Organisation mehrere Mandanten haben könnte:</span><span class="sxs-lookup"><span data-stu-id="6fb5c-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="6fb5c-118">Administrative Isolation</span><span class="sxs-lookup"><span data-stu-id="6fb5c-118">Administrative isolation</span></span>
- <span data-ttu-id="6fb5c-119">Dezentralisierte IT</span><span class="sxs-lookup"><span data-stu-id="6fb5c-119">Decentralized IT</span></span>
- <span data-ttu-id="6fb5c-120">Historische Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="6fb5c-120">Historical decisions</span></span>
- <span data-ttu-id="6fb5c-121">Fusionen, Übernahmen oder Abkäufe</span><span class="sxs-lookup"><span data-stu-id="6fb5c-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="6fb5c-122">Klare Trennung des Brandings für Mischkonzerne</span><span class="sxs-lookup"><span data-stu-id="6fb5c-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="6fb5c-123">Vorproduktions-, Test- oder Sandkasten-Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="6fb5c-124">Hier ist ein Beispiel für eine Organisation mit zwei Mandanten (Mandant A und Mandant B) im gleichen Standarddatencenter-Geo.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="6fb5c-125">Jeder Mandant als separater Azure AD-Mandant.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-125">Each tenant as a separate Azure AD tenant.</span></span>

![Mehrere Microsoft 365 Mandanten mit eigenen Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="6fb5c-127">Wenn Sie über mehrere Mandanten verfügen, gibt es Einschränkungen und zusätzliche Überlegungen beim Verwalten und Bereitstellen von Diensten für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="6fb5c-128">Zusammenarbeit zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="6fb5c-129">Wenn Sie möchten, dass Ihre Benutzer auf sichere Weise zwischen verschiedenen Microsoft 365-Mandanten zusammenarbeiten, umfassen optionen für die mandantenübergreifende Zusammenarbeit die Verwendung eines zentralen Speicherorts für Dateien und Unterhaltungen, die Freigabe von Kalendern, die Verwendung von Chats, Audio-/Videoanrufe für die Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="6fb5c-130">Weitere Informationen finden Sie unter [Microsoft 365 Zusammenarbeit zwischen Mandanten.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="6fb5c-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="6fb5c-131">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6fb5c-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="6fb5c-132">Vor der mandantenübergreifenden Postfachmigration (in der Vorschau) müssen Sie beim Verschieben von Exchange Online Postfächern zwischen Mandanten ein Benutzerpostfach vollständig aus dem aktuellen Mandanten (dem Quell-Mandanten) in den lokalen Mandanten verschieben und dann in einen neuen Mandanten (den Ziel mandanten) integrieren.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="6fb5c-133">Mit dem neuen mandantenübergreifenden Migrationsfeature können Mandantenadministratoren sowohl in Quell- als auch in Ziel mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="6fb5c-134">Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="6fb5c-135">Hier sind zwei Beispiel-Mandanten und ihre Postfächer vor der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Mehrere Microsoft 365 Mandanten und deren Postfächer](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="6fb5c-137">In dieser Abbildung verfügen zwei separate Mandanten über eigene Domänen und eine Reihe von Exchange Postfächern.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="6fb5c-138">Hier ist der Ziel-Mandant (Mandant A) nach der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Der Ziel-Mandant nach der mandantenübergreifenden Postfachmigration](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="6fb5c-140">In dieser Abbildung verfügt ein einzelner Mandant sowohl über Domänen als auch über beide Exchange Postfächer.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="6fb5c-141">Weitere Informationen finden Sie unter [Mandantenübergreifende Postfachmigration](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="6fb5c-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="6fb5c-142">Migrationen zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="6fb5c-143">Es gibt verschiedene Architekturansätze für Fusionen, Übernahmen, Abgänge und andere Szenarien, die Sie dazu führen können, einen vorhandenen Microsoft 365 mandanten zu einem neuen Mandanten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="6fb5c-144">Ausführliche Anleitungen finden Sie [unter Microsoft 365 Mandantenmigrationen](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span><span class="sxs-lookup"><span data-stu-id="6fb5c-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="6fb5c-145">Multi-Geo für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="6fb5c-146">Mit Microsoft 365 Multi-Geo können Sie Ruhedaten an den anderen geografischen Standorten des Rechenzentrums bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenresidenz zu erfüllen, und gleichzeitig Ihr globales Rollout moderner Produktivitätserfahrungen für Ihre Mitarbeiter entsperren.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="6fb5c-147">In einer Multi-Geo-Umgebung besteht ihr Microsoft 365 aus einem Standard- oder zentralen Standort, an dem Ihr Microsoft 365-Abonnement ursprünglich erstellt wurde, und einem oder mehreren Satellitenstandorten.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="6fb5c-148">In einem Multi-Geo-Mandanten werden die Informationen zu geografischen Standorten, Gruppen und Benutzerinformationen in einem globalen Azure AD-Mandanten gemastert.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="6fb5c-149">Da Ihre Mandanteninformationen zentral gemastert und mit jedem geografischen Standort synchronisiert werden, werden Die Zusammenarbeitserfahrungen, an denen alle Personen aus Ihrem Unternehmen beteiligt sind, über die Standorte hinweg gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="6fb5c-150">Im Folgenden finden Sie ein Beispiel für eine Organisation mit ihrem Standardstandort in Europa und einem Satellitenstandort in Nordamerika.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="6fb5c-151">Beide Standorte teilen sich denselben globalen Azure AD-Mandanten für den einzelnen Microsoft 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Beispiel für einen Multi-Geo-Microsoft 365 Mandanten](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="6fb5c-153">Mehr dazu unter [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="6fb5c-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="6fb5c-154">Verschieben von Kerndaten in einen neuen Geografischen Datencenter</span><span class="sxs-lookup"><span data-stu-id="6fb5c-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="6fb5c-155">Microsoft öffnet weiterhin neue Datencenter-Geos für Microsoft 365 Dienste.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="6fb5c-156">Diese neuen Rechenzentrumsregionen erweitern Kapazitäten und Rechenleistung zur Unterstützung unserer laufenden Kundennachfrage und des Nutzungswachstums.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="6fb5c-157">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="6fb5c-158">Auch wenn das Öffnen eines neuen Geocenters keine Auswirkungen auf Sie und Ihre Kerndaten hat, die in einem bereits vorhandenen Rechenzentrums-Geo gespeichert sind, können Sie mit Microsoft eine frühzeitige Migration der ruhenden Kernkundendaten Ihrer Organisation zu einem neuen Geografischen Datencenter anfordern.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="6fb5c-159">Hier ist ein Beispiel, in dem ein Microsoft 365 mandanten aus dem Geografischen Rechenzentrum der Europäischen Union (EU) in das Rechenzentrum im Vereinigten Königreich (Großbritannien) verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Beispiel für das Verschieben eines Microsoft 365 zwischen Geos des Rechenzentrums](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="6fb5c-161">Weitere Informationen finden Sie unter [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="6fb5c-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="6fb5c-162">Produkte und Lizenzen für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="6fb5c-163">Ihr Microsoft 365-Mandant wird erstellt, wenn Sie Ihr erstes Produkt erwerben, z. B. Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="6fb5c-164">Zusammen mit dem Produkt sind Lizenzen, die eine monatliche oder jährliche Gebühr in Rechnung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="6fb5c-165">Ein Administrator weist dann eine verfügbare Lizenz aus einem Ihrer Produkte einem Benutzerkonto zu, entweder direkt oder über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="6fb5c-166">Je nach den Geschäftlichen Anforderungen Ihrer Organisation verfügen Sie möglicherweise über eine Reihe von Produkten, die jeweils über einen eigenen Pool von Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="6fb5c-167">Für die Bestimmung des Satz von Produkten und der Anzahl der Lizenzen für die einzelnen Produkte ist eine gewisse Planung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6fb5c-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="6fb5c-168">Stellen Sie sicher, dass Sie über genügend Lizenzen für die Benutzerkonten verfügen, die erweiterte Features benötigen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="6fb5c-169">Verhindern Sie, dass Ihnen lizenzen oder zu viele nicht zugewiesene Lizenzen aufgrund von Personaländerungen in Ihrer Organisation nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="6fb5c-170">Ergebnisse von Schritt 1</span><span class="sxs-lookup"><span data-stu-id="6fb5c-170">Results of Step 1</span></span>

<span data-ttu-id="6fb5c-171">Für Ihre Microsoft 365 für Enterprise-Mandanten haben Sie ermittelt:</span><span class="sxs-lookup"><span data-stu-id="6fb5c-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="6fb5c-172">Wie viele Mandanten Sie haben oder benötigen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="6fb5c-173">Für jeden Mandanten, welche Produkte und Lizenzen erworben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="6fb5c-174">Gibt an, ob ein Mandant Multi-Geo sein muss, um die Anforderungen an die Datenresidenz zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="6fb5c-175">Gibt an, ob Sie eine mandantenübergreifende Zusammenarbeit einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="6fb5c-176">Gibt an, ob Sie einen Mandanten zu einem anderen migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="6fb5c-177">Gibt an, ob Sie Kerndaten aus einem Geografischen Datencenter in ein neues verschieben müssen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="6fb5c-178">Hier ist ein Beispiel für einen neuen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-178">Here is an example of a new tenant.</span></span>

![Beispiel für einen neuen Mandanten](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="6fb5c-180">In dieser Abbildung verfügt der Mandant über:</span><span class="sxs-lookup"><span data-stu-id="6fb5c-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="6fb5c-181">Ein Standardspeicherort, der einem geografischen Microsoft 365 datencenter entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="6fb5c-182">Eine Reihe von Produkten und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-182">A set of products and licenses.</span></span>
- <span data-ttu-id="6fb5c-183">Der Satz von Cloudproduktivitäts-Apps, von denen einige spezifisch für Produkte sind.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="6fb5c-184">Ein Azure AD-Mandant, der globale Administratorkonten und einen anfänglichen DNS-Domänennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="6fb5c-185">Wenn wir die zusätzlichen Schritte dieser Lösung durchziehen, werden wir diese Abbildung erstellen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="6fb5c-186">Laufende Wartung für Mandanten</span><span class="sxs-lookup"><span data-stu-id="6fb5c-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="6fb5c-187">Auf fortlaufender Basis müssen Sie möglicherweise:</span><span class="sxs-lookup"><span data-stu-id="6fb5c-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="6fb5c-188">Fügen Sie einen neuen Mandanten hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-188">Add a new tenant.</span></span>
- <span data-ttu-id="6fb5c-189">Fügen Sie einem Mandanten mit einer anfänglichen Anzahl von Lizenzen neue Produkte hinzu.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="6fb5c-190">Ändern Sie den Satz von Lizenzen für ein Produkt in einem Mandanten, um die sich ändernden Personalanforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="6fb5c-191">Verschieben Sie Ihre Kerndaten von einem Mandanten an einen neuen geografischen Standort des Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="6fb5c-192">Add Multi-Geo for data residency requirements.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="6fb5c-193">Einrichten der mandantenübergreifenden Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="6fb5c-194">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6fb5c-194">Next step</span></span>

<span data-ttu-id="6fb5c-195">[![Schritt 2. Optimieren des Mandanten für den Zugriff auf das Netzwerk](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="6fb5c-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="6fb5c-196">Fahren Sie mit [dem Netzwerk](tenant-management-networking.md) fort, um optimale Netzwerke von Ihren Mitarbeitern zu Microsoft 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6fb5c-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
