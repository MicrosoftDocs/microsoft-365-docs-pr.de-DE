---
title: Schritt 1. Ihre Microsoft 365 for Enterprise-Mandanten
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
description: Bereitstellen und Verwalten einzelner oder mehrerer Microsoft 365-Mandanten mit Optionen für Multi-Geo- und verschiebende Standorte.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406384"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="4fa77-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="4fa77-104">Step 1.</span></span> <span data-ttu-id="4fa77-105">Ihre Microsoft 365 for Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="4fa77-106">Eine Ihrer ersten Mandantenentscheidungen ist, wie viele sie haben müssen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="4fa77-107">Jeder Microsoft 365-Mandant ist unterschiedlich, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt.</span><span class="sxs-lookup"><span data-stu-id="4fa77-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="4fa77-108">Der entsprechende Azure AD-Mandant ist auch unterschiedlich, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt.</span><span class="sxs-lookup"><span data-stu-id="4fa77-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="4fa77-109">Einzelner Mandant</span><span class="sxs-lookup"><span data-stu-id="4fa77-109">Single tenant</span></span>
<span data-ttu-id="4fa77-110">Die Verwendung eines einzelnen Mandanten vereinfacht viele Aspekte der Verwendung von Microsoft 365 in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4fa77-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="4fa77-111">Ein einzelner Mandant bedeutet einen einzelnen Azure AD-Mandanten mit einem einzigen Satz von Konten, Gruppen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="4fa77-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="4fa77-112">Berechtigungen und die Freigabe von Ressourcen in Ihrer Organisation können über diesen zentralen Identitätsanbieter durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fa77-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="4fa77-113">Ein einzelner Mandant bietet den Benutzern die funktionsreichste und vereinfachte Zusammenarbeit und Produktivität.</span><span class="sxs-lookup"><span data-stu-id="4fa77-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="4fa77-114">Im Folgenden finden Sie ein Beispiel, das den Standardspeicherort und den Azure AD-Mandanten eines Microsoft 365-Mandanten zeigt.</span><span class="sxs-lookup"><span data-stu-id="4fa77-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Ein einzelner Microsoft 365-Mandant mit seinem Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="4fa77-116">Mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-116">Multiple tenants</span></span>

<span data-ttu-id="4fa77-117">Es gibt viele Gründe, warum Ihre Organisation mehrere Mandanten haben könnte:</span><span class="sxs-lookup"><span data-stu-id="4fa77-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="4fa77-118">Administrative Isolation</span><span class="sxs-lookup"><span data-stu-id="4fa77-118">Administrative isolation</span></span>
- <span data-ttu-id="4fa77-119">Dezentralisierte IT</span><span class="sxs-lookup"><span data-stu-id="4fa77-119">Decentralized IT</span></span>
- <span data-ttu-id="4fa77-120">Historische Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="4fa77-120">Historical decisions</span></span>
- <span data-ttu-id="4fa77-121">Fusionen, Übernahmen oder Abkäufe</span><span class="sxs-lookup"><span data-stu-id="4fa77-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="4fa77-122">Klare Trennung des Brandings für Mischkonzerne</span><span class="sxs-lookup"><span data-stu-id="4fa77-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="4fa77-123">Vorproduktions-, Test- oder Sandkasten-Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="4fa77-124">Hier ist ein Beispiel für eine Organisation mit zwei Mandanten (Mandant A und Mandant B) im gleichen Standarddatencenter-Geo.</span><span class="sxs-lookup"><span data-stu-id="4fa77-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="4fa77-125">Jeder Mandant als separater Azure AD-Mandant.</span><span class="sxs-lookup"><span data-stu-id="4fa77-125">Each tenant as a separate Azure AD tenant.</span></span>

![Mehrere Microsoft 365-Mandanten mit eigenen Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="4fa77-127">Wenn Sie über mehrere Mandanten verfügen, gibt es Einschränkungen und zusätzliche Überlegungen beim Verwalten und Bereitstellen von Diensten für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4fa77-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="4fa77-128">Zusammenarbeit zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="4fa77-129">Wenn Sie möchten, dass Ihre Benutzer auf sichere Weise in verschiedenen Microsoft 365-Mandanten effektiver zusammenarbeiten, umfassen optionen für die mandantenübergreifende Zusammenarbeit die Verwendung eines zentralen Speicherorts für Dateien und Unterhaltungen, das Freigeben von Kalendern, die Verwendung von Chats, Audio-/Videoanrufe für die Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="4fa77-130">Weitere Informationen finden Sie unter Zusammenarbeit zwischen Mandanten in [Microsoft 365](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="4fa77-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="4fa77-131">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4fa77-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="4fa77-132">Vor der mandantenübergreifenden Postfachmigration (in der Vorschau) müssen Sie beim Verschieben von Exchange Online-Postfächern zwischen Mandanten ein Benutzerpostfach vollständig aus dem aktuellen Mandanten (dem Quell-Mandanten) in den lokalen Mandanten verschieben und dann in einen neuen Mandanten (den Ziel-Mandanten) integrieren.</span><span class="sxs-lookup"><span data-stu-id="4fa77-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="4fa77-133">Mit dem neuen mandantenübergreifenden Migrationsfeature können Mandantenadministratoren sowohl in Quell- als auch in Ziel mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="4fa77-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="4fa77-134">Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt.</span><span class="sxs-lookup"><span data-stu-id="4fa77-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="4fa77-135">Hier sind zwei Beispiel-Mandanten und ihre Postfächer vor der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="4fa77-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Mehrere Microsoft 365-Mandanten und ihre Postfächer](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="4fa77-137">In dieser Abbildung verfügen zwei separate Mandanten über eigene Domänen und eine Reihe von Exchange-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="4fa77-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="4fa77-138">Hier ist der Ziel-Mandant (Mandant A) nach der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="4fa77-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Der Ziel-Mandant nach der mandantenübergreifenden Postfachmigration](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="4fa77-140">In dieser Abbildung verfügt ein einzelner Mandant sowohl über Domänen als auch über beide Gruppen von Exchange-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="4fa77-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="4fa77-141">Weitere Informationen finden Sie unter [Mandantenübergreifende Postfachmigration](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="4fa77-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="4fa77-142">Migrationen zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="4fa77-143">Es gibt verschiedene Architekturansätze für Fusionen, Übernahmen, Abgänge und andere Szenarien, die Sie dazu führen können, einen vorhandenen Microsoft 365-Mandanten zu einem neuen Mandanten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="4fa77-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="4fa77-144">Ausführliche Anleitungen finden Sie unter Migrationen von Mandanten zu Mandanten in [Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="4fa77-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="4fa77-145">Multi-Geo für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="4fa77-146">Mit Microsoft 365 Multi-Geo können Sie Ruhedaten an den anderen geografischen Standorten des Rechenzentrums bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenresidenz zu erfüllen, und gleichzeitig Ihr globales Rollout moderner Produktivitätserfahrungen für Ihre Mitarbeiter entsperren.</span><span class="sxs-lookup"><span data-stu-id="4fa77-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="4fa77-147">In einer Multi-Geo-Umgebung besteht Ihr Microsoft 365-Mandant aus einem Standard- oder zentralen Standort, an dem Ihr Microsoft 365-Abonnement ursprünglich erstellt wurde, und einem oder mehreren Satellitenstandorten.</span><span class="sxs-lookup"><span data-stu-id="4fa77-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="4fa77-148">In einem Multi-Geo-Mandanten werden die Informationen zu geografischen Standorten, Gruppen und Benutzerinformationen in einem globalen Azure AD-Mandanten gemastert.</span><span class="sxs-lookup"><span data-stu-id="4fa77-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="4fa77-149">Da Ihre Mandanteninformationen zentral gemastert und mit jedem geografischen Standort synchronisiert werden, werden Die Zusammenarbeitserfahrungen, an denen alle Personen aus Ihrem Unternehmen beteiligt sind, über die Standorte hinweg gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="4fa77-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="4fa77-150">Im Folgenden finden Sie ein Beispiel für eine Organisation mit ihrem Standardstandort in Europa und einem Satellitenstandort in Nordamerika.</span><span class="sxs-lookup"><span data-stu-id="4fa77-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="4fa77-151">Beide Standorte teilen sich denselben globalen Azure AD-Mandanten für den einzelnen Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4fa77-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Beispiel für einen Multi-Geo-Microsoft 365-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="4fa77-153">Mehr dazu unter [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="4fa77-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="4fa77-154">Verschieben von Kerndaten in einen neuen Geografischen Datencenter</span><span class="sxs-lookup"><span data-stu-id="4fa77-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="4fa77-155">Microsoft öffnet weiterhin neue Datencenter-Geos für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="4fa77-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="4fa77-156">Diese neuen Rechenzentrumsregionen erweitern Kapazitäten und Rechenleistung zur Unterstützung unserer laufenden Kundennachfrage und des Nutzungswachstums.</span><span class="sxs-lookup"><span data-stu-id="4fa77-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="4fa77-157">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="4fa77-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="4fa77-158">Auch wenn das Öffnen eines neuen Geocenters keine Auswirkungen auf Sie und Ihre Kerndaten hat, die in einem bereits vorhandenen Rechenzentrums-Geo gespeichert sind, können Sie mit Microsoft eine frühzeitige Migration der ruhenden Kernkundendaten Ihrer Organisation zu einem neuen Geografischen Datencenter anfordern.</span><span class="sxs-lookup"><span data-stu-id="4fa77-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="4fa77-159">Im Folgenden finden Sie ein Beispiel, in dem ein Microsoft 365-Mandant vom Geografischen Rechenzentrum der Europäischen Union (EU) in das Rechenzentrum im Vereinigten Königreich (Großbritannien) verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="4fa77-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Beispiel für das Verschieben eines Microsoft 365-Mandanten zwischen Geografischen Datencentern](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="4fa77-161">Weitere Informationen finden Sie unter [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="4fa77-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="4fa77-162">Produkte und Lizenzen für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="4fa77-163">Ihr Microsoft 365-Mandant wird erstellt, wenn Sie Ihr erstes Produkt erwerben, z. B. Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4fa77-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="4fa77-164">Zusammen mit dem Produkt sind Lizenzen, die eine monatliche oder jährliche Gebühr in Rechnung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4fa77-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="4fa77-165">Ein Administrator weist dann eine verfügbare Lizenz aus einem Ihrer Produkte einem Benutzerkonto zu, entweder direkt oder über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="4fa77-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="4fa77-166">Je nach den Geschäftlichen Anforderungen Ihrer Organisation verfügen Sie möglicherweise über eine Reihe von Produkten, die jeweils über einen eigenen Pool von Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="4fa77-167">Für die Bestimmung des Satz von Produkten und der Anzahl der Lizenzen für die einzelnen Produkte ist eine gewisse Planung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="4fa77-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="4fa77-168">Stellen Sie sicher, dass Sie über genügend Lizenzen für die Benutzerkonten verfügen, die erweiterte Features benötigen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="4fa77-169">Verhindern Sie, dass Ihnen lizenzen oder zu viele nicht zugewiesene Lizenzen aufgrund von Personaländerungen in Ihrer Organisation nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4fa77-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="4fa77-170">Ergebnisse von Schritt 1</span><span class="sxs-lookup"><span data-stu-id="4fa77-170">Results of Step 1</span></span>

<span data-ttu-id="4fa77-171">Für Ihre Microsoft 365 Enterprise-Mandanten haben Sie ermittelt:</span><span class="sxs-lookup"><span data-stu-id="4fa77-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="4fa77-172">Wie viele Mandanten Sie haben oder benötigen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="4fa77-173">Für jeden Mandanten, welche Produkte und Lizenzen erworben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="4fa77-174">Gibt an, ob ein Mandant Multi-Geo sein muss, um die Anforderungen an die Datenresidenz zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="4fa77-175">Gibt an, ob Sie eine mandantenübergreifende Zusammenarbeit einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="4fa77-176">Gibt an, ob Sie einen Mandanten zu einem anderen migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="4fa77-177">Gibt an, ob Sie Kerndaten aus einem Geografischen Datencenter in ein neues verschieben müssen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="4fa77-178">Hier ist ein Beispiel für einen neuen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4fa77-178">Here is an example of a new tenant.</span></span>

![Beispiel für einen neuen Mandanten](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="4fa77-180">In dieser Abbildung verfügt der Mandant über:</span><span class="sxs-lookup"><span data-stu-id="4fa77-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="4fa77-181">Ein Standardspeicherort, der einem Geografischen Microsoft 365-Rechenzentrum entspricht.</span><span class="sxs-lookup"><span data-stu-id="4fa77-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="4fa77-182">Eine Reihe von Produkten und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-182">A set of products and licenses.</span></span>
- <span data-ttu-id="4fa77-183">Der Satz von Cloudproduktivitäts-Apps, von denen einige spezifisch für Produkte sind.</span><span class="sxs-lookup"><span data-stu-id="4fa77-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="4fa77-184">Ein Azure AD-Mandant, der globale Administratorkonten und einen anfänglichen DNS-Domänennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="4fa77-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="4fa77-185">Wenn wir die zusätzlichen Schritte dieser Lösung durchziehen, werden wir diese Abbildung erstellen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="4fa77-186">Laufende Wartung für Mandanten</span><span class="sxs-lookup"><span data-stu-id="4fa77-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="4fa77-187">Auf fortlaufender Basis müssen Sie möglicherweise:</span><span class="sxs-lookup"><span data-stu-id="4fa77-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="4fa77-188">Fügen Sie einen neuen Mandanten hinzu.</span><span class="sxs-lookup"><span data-stu-id="4fa77-188">Add a new tenant.</span></span>
- <span data-ttu-id="4fa77-189">Fügen Sie einem Mandanten mit einer anfänglichen Anzahl von Lizenzen neue Produkte hinzu.</span><span class="sxs-lookup"><span data-stu-id="4fa77-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="4fa77-190">Ändern Sie den Satz von Lizenzen für ein Produkt in einem Mandanten, um die sich ändernden Personalanforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="4fa77-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="4fa77-191">Verschieben Sie Ihre Kerndaten von einem Mandanten an einen neuen geografischen Standort des Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="4fa77-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="4fa77-192">Add Multi-Geo for data residency requirements.</span><span class="sxs-lookup"><span data-stu-id="4fa77-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="4fa77-193">Einrichten der mandantenübergreifenden Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="4fa77-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="4fa77-194">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4fa77-194">Next step</span></span>

<span data-ttu-id="4fa77-195">[![Schritt 2. Optimieren des Mandanten für den Zugriff auf das Netzwerk](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="4fa77-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="4fa77-196">Fahren Sie mit [dem Netzwerk](tenant-management-networking.md) fort, um optimale Netzwerke von Ihren Mitarbeitern zu Microsoft 365-Clouddiensten zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4fa77-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
