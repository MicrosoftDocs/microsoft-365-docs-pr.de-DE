---
title: Schritt 1. Ihre Microsoft 365 Enterprise-Mandanten
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
ms.custom:
- Ent_Solutions
description: Bereitstellen und Verwalten einzelner oder mehrerer Microsoft 365-Mandanten mit Optionen für Multi-Geo- und Verschieben von Standorten.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908591"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="1f1b1-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-104">Step 1.</span></span> <span data-ttu-id="1f1b1-105">Ihre Microsoft 365 Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="1f1b1-106">Eine Ihrer ersten Mandantenentscheidungen ist, wie viele sie haben müssen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="1f1b1-107">Jeder Microsoft 365-Mandant ist unterschiedlich, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="1f1b1-108">Der entsprechende Azure AD-Mandant ist auch anders, eindeutig und von allen anderen Microsoft 365-Mandanten getrennt.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="1f1b1-109">Einzelner Mandant</span><span class="sxs-lookup"><span data-stu-id="1f1b1-109">Single tenant</span></span>
<span data-ttu-id="1f1b1-110">Die Verwendung eines einzelnen Mandanten vereinfacht viele Aspekte der Nutzung von Microsoft 365 in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="1f1b1-111">Ein einzelner Mandant bedeutet einen einzelnen Azure AD-Mandanten mit einem einzigen Satz von Konten, Gruppen und Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="1f1b1-112">Berechtigungen und die Freigabe von Ressourcen in Ihrer Organisation können über diesen zentralen Identitätsanbieter durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="1f1b1-113">Ein einzelner Mandant bietet ihren Benutzern die funktionsreichste und vereinfachte Zusammenarbeit und Produktivität.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="1f1b1-114">Hier ist ein Beispiel für den Standardspeicherort und den Azure AD-Mandanten eines Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Ein einzelner Microsoft 365-Mandant mit seinem Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="1f1b1-116">Mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-116">Multiple tenants</span></span>

<span data-ttu-id="1f1b1-117">Es gibt viele Gründe, warum Ihre Organisation mehrere Mandanten haben könnte:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="1f1b1-118">Administrative Isolation</span><span class="sxs-lookup"><span data-stu-id="1f1b1-118">Administrative isolation</span></span>
- <span data-ttu-id="1f1b1-119">Dezentralisierte IT</span><span class="sxs-lookup"><span data-stu-id="1f1b1-119">Decentralized IT</span></span>
- <span data-ttu-id="1f1b1-120">Historische Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="1f1b1-120">Historical decisions</span></span>
- <span data-ttu-id="1f1b1-121">Fusionen, Übernahmen oder Übernahmen</span><span class="sxs-lookup"><span data-stu-id="1f1b1-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="1f1b1-122">Klare Trennung des Brandings für Mischkonzernorganisationen</span><span class="sxs-lookup"><span data-stu-id="1f1b1-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="1f1b1-123">Präproduktions-, Test- oder Sandkasten-Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="1f1b1-124">Hier ist ein Beispiel für eine Organisation mit zwei Mandanten (Mandant A und Mandant B) in derselben Standard-Rechenzentrums-Geo.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="1f1b1-125">Jeder Mandant als separater Azure AD-Mandant.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-125">Each tenant as a separate Azure AD tenant.</span></span>

![Mehrere Microsoft 365-Mandanten mit ihren eigenen Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="1f1b1-127">Wenn Sie über mehrere Mandanten verfügen, gibt es Einschränkungen und zusätzliche Überlegungen bei der Verwaltung und Bereitstellung von Diensten für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="1f1b1-128">Zusammenarbeit zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="1f1b1-129">Wenn Sie möchten, dass Ihre Benutzer in verschiedenen Microsoft 365-Mandanten auf sichere Weise effektiver zusammenarbeiten, umfassen die Optionen für die mandantenübergreifende Zusammenarbeit die Verwendung eines zentralen Speicherorts für Dateien und Unterhaltungen, das Freigeben von Kalendern, die Verwendung von Chats, Audio-/Videoanrufe für die Kommunikation und das Sichern des Zugriffs auf Ressourcen und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="1f1b1-130">Weitere Informationen finden Sie unter Zusammenarbeit zwischen Mandanten in [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="1f1b1-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="1f1b1-131">Mandantenübergreifende Postfachmigration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1f1b1-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="1f1b1-132">Vor der mandantenübergreifenden Postfachmigration (in der Vorschau) müssen Sie beim Verschieben von Exchange Online-Postfächern zwischen Mandanten ein Benutzerpostfach vollständig von ihrem aktuellen Mandanten (dem Quell-Mandanten) in einen lokalen Mandanten auswechseln und dann in einen neuen Mandanten (den Ziel-Mandanten) integrieren.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="1f1b1-133">Mit dem neuen feature für die mandantenübergreifende Postfachmigration können Mandantenadministratoren sowohl in Quell- als auch in Ziel-Mandanten Postfächer zwischen den Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="1f1b1-134">Dadurch müssen keine Off-Board- und Onboardingpostfächer mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="1f1b1-135">Hier sind zwei Beispiel-Mandanten und ihre Postfächer vor der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Mehrere Microsoft 365-Mandanten und ihre Postfächer](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="1f1b1-137">In dieser Abbildung verfügen zwei separate Mandanten über eigene Domänen und einen Satz von Exchange-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="1f1b1-138">Hier ist der Ziel mandant (Mandant A) nach der mandantenübergreifenden Postfachmigration.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Der Ziel mandant nach der mandantenübergreifenden Postfachmigration](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="1f1b1-140">In dieser Abbildung verfügt ein einzelner Mandant sowohl über Domänen als auch über beide Gruppen von Exchange-Postfächern.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="1f1b1-141">Weitere Informationen finden Sie unter ["Mandantenübergreifende Postfachmigration".](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="1f1b1-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="1f1b1-142">Migrationen zwischen Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="1f1b1-143">Es gibt mehrere Architekturansätze für Fusionen, Übernahmen, Abgänge und andere Szenarien, die sie dazu führen können, einen vorhandenen Microsoft 365-Mandanten zu einem neuen Mandanten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="1f1b1-144">Ausführliche Anleitungen finden Sie unter [Microsoft 365-Migrationen](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)zwischen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="1f1b1-145">Multi-Geo für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="1f1b1-146">Mit Microsoft 365 Multi-Geo können Sie Ruhedaten an den anderen geografischen Standorten des Rechenzentrums bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenspeicherung zu erfüllen, und gleichzeitig Ihre globale Einführung moderner Produktivitätserfahrungen für Ihre Mitarbeiter freischalten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="1f1b1-147">In einer Multi-Geo-Umgebung besteht Ihr Microsoft 365-Mandant aus einem Standard- oder zentralen Standort, an dem Ihr Microsoft 365-Abonnement ursprünglich erstellt wurde, und einem oder mehreren Satellitenstandorten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="1f1b1-148">In einem Multi-Geo-Mandanten werden die Informationen zu geografischen Standorten, Gruppen und Benutzerinformationen in einem globalen Azure AD-Mandanten gemastert.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="1f1b1-149">Da Ihre Mandanteninformationen zentral gemastert und an jedem geografischen Standort synchronisiert werden, werden Die Zusammenarbeitserfahrungen, an denen alle Personen aus Ihrem Unternehmen beteiligt sind, über die Standorte hinweg freigegeben.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="1f1b1-150">Hier ist ein Beispiel für eine Organisation mit ihrem Standardstandort in Europa und einem Satellitenstandort in Nordamerika.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="1f1b1-151">Beide Standorte verwenden denselben globalen Azure AD-Mandanten für den einzelnen Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Beispiel für einen Multi-Geo-Microsoft 365-Mandanten](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="1f1b1-153">Mehr dazu unter [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="1f1b1-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="1f1b1-154">Verschieben von Kerndaten in eine neue Rechenzentrums-Geo</span><span class="sxs-lookup"><span data-stu-id="1f1b1-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="1f1b1-155">Microsoft öffnet weiterhin neue Rechenzentrums-Geos für Microsoft 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="1f1b1-156">Diese neuen Rechenzentrumsregionen erweitern Kapazitäten und Rechenleistung zur Unterstützung unserer laufenden Kundennachfrage und des Nutzungswachstums.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="1f1b1-157">Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="1f1b1-158">Obwohl das Öffnen einer neuen Rechenzentrums-Geo keine Auswirkungen auf Sie und Ihre Kerndaten hat, die in einer bereits vorhandenen Rechenzentrums-Geo gespeichert sind, können Sie mit Microsoft eine frühzeitige Migration der ruhenden Kundenkerndaten Ihrer Organisation zu einer neuen Rechenzentrums-Geo anfordern.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="1f1b1-159">Hier ist ein Beispiel, bei dem ein Microsoft 365-Mandant aus dem Geografischen des Rechenzentrums der Europäischen Union (EU) in das Rechenzentrum im Vereinigten Königreich verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Beispiel für das Verschieben eines Microsoft 365-Mandanten zwischen den geografischen Datencentern](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="1f1b1-161">Weitere Informationen finden Sie unter [Verschieben von Kerndaten in neue Geografische Datencenter von Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="1f1b1-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="1f1b1-162">Produkte und Lizenzen für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="1f1b1-163">Ihr Microsoft 365-Mandant wird erstellt, wenn Sie Ihr erstes Produkt erwerben, z. B. Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="1f1b1-164">Zusammen mit dem Produkt gibt es Lizenzen, denen eine monatliche oder jährliche Gebühr in Rechnung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="1f1b1-165">Ein Administrator weist dann einem Benutzerkonto eine verfügbare Lizenz aus einem Ihrer Produkte zu, entweder direkt oder über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="1f1b1-166">Je nach den Geschäftsanforderungen Ihrer Organisation verfügen Sie möglicherweise über eine Reihe von Produkten, die jeweils über einen eigenen Pool von Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="1f1b1-167">Das Bestimmen der Produkt- und Anzahl der Lizenzen für die einzelnen Produkte erfordert eine gewisse Planung:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="1f1b1-168">Stellen Sie sicher, dass Sie über genügend Lizenzen für die Benutzerkonten verfügen, die erweiterte Features benötigen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="1f1b1-169">Verhindern Sie, dass Lizenzen auslaufen oder sie zu viele nicht zugewiesene Lizenzen haben, basierend auf Änderungen bei der Personalbepersonalung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="1f1b1-170">Ergebnisse von Schritt 1</span><span class="sxs-lookup"><span data-stu-id="1f1b1-170">Results of Step 1</span></span>

<span data-ttu-id="1f1b1-171">Für Ihre Microsoft 365 Enterprise-Mandanten haben Sie ermittelt:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="1f1b1-172">Wie viele Mandanten Sie haben oder benötigen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="1f1b1-173">Für jeden Mandanten, welche Produkte und Lizenzen erworben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="1f1b1-174">Gibt an, ob ein Mandant Multi-Geo sein muss, um die Anforderungen an den Datenspeicher zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="1f1b1-175">Gibt an, ob Sie die mandantenübergreifende Zusammenarbeit einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="1f1b1-176">Gibt an, ob Sie einen Mandanten zu einem anderen migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="1f1b1-177">Gibt an, ob Sie Kerndaten von einer Rechenzentrums-Geo in eine neue verschieben müssen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="1f1b1-178">Hier ist ein Beispiel für einen neuen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-178">Here is an example of a new tenant.</span></span>

![Beispiel für einen neuen Mandanten](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="1f1b1-180">In dieser Abbildung hat der Mandant:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="1f1b1-181">Ein Standardspeicherort, der einem geografischen Standort des Microsoft 365-Rechenzentrums entspricht.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="1f1b1-182">Eine Reihe von Produkten und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-182">A set of products and licenses.</span></span>
- <span data-ttu-id="1f1b1-183">Der Satz von Cloud-Produktivitäts-Apps, von denen einige für Produkte spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="1f1b1-184">Ein Azure AD-Mandant, der globale Administratorkonten und einen anfänglichen DNS-Domänennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="1f1b1-185">Während wir die zusätzlichen Schritte dieser Lösung durchziehen, erstellen wir diese Abbildung.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="1f1b1-186">Laufende Wartung für Mandanten</span><span class="sxs-lookup"><span data-stu-id="1f1b1-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="1f1b1-187">Es kann sein, dass Sie regelmäßig:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="1f1b1-188">Fügen Sie einen neuen Mandanten hinzu.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-188">Add a new tenant.</span></span>
- <span data-ttu-id="1f1b1-189">Hinzufügen neuer Produkte zu einem Mandanten mit einer anfänglichen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="1f1b1-190">Ändern Sie den Satz von Lizenzen für ein Produkt in einem Mandanten, um sich an sich ändernde Mitarbeiteranforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="1f1b1-191">Verschieben Sie Ihre Kerndaten von einem Mandanten an einen neuen geografischen Standort des Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="1f1b1-192">Hinzufügen von Multi-Geo für Daten-Residency-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="1f1b1-193">Einrichten der mandantenübergreifenden Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="1f1b1-194">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1f1b1-194">Next step</span></span>

<span data-ttu-id="1f1b1-195">[![Schritt 2. Optimieren Ihres Mandanten für das Netzwerk für den Zugriff](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="1f1b1-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="1f1b1-196">Fahren Sie mit [dem Netzwerk](tenant-management-networking.md) fort, um optimale Netzwerke von Ihren Mitarbeitern zu Microsoft 365-Clouddiensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1f1b1-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
