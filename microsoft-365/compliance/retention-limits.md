---
title: Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Erfahren Sie mehr über die maximale Anzahl von Richtlinien und Elementen pro Richtlinie für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien.
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107657"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="c4280-103">Einschränkungen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c4280-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="c4280-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="c4280-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="c4280-105">Wenn Sie [Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien](retention.md#retention-policies-and-retention-labels) verwenden, um Daten für Ihre Organisation automatisch zu speichern oder zu löschen, müssen Sie einige maximale Werte beachten.</span><span class="sxs-lookup"><span data-stu-id="c4280-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="c4280-106">Maximale Anzahl von Richtlinien pro Mandant</span><span class="sxs-lookup"><span data-stu-id="c4280-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="c4280-107">Ein einzelner Mandant kann maximal 10.000 Richtlinien (beliebige Konfiguration) besitzen.</span><span class="sxs-lookup"><span data-stu-id="c4280-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="c4280-108">Diese maximale Anzahl umfasst die verschiedenen Richtlinien für die Aufbewahrung und andere Richtlinien für Compliance wie z. B. DLP-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="c4280-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="c4280-109">Maximale Anzahl von Richtlinien für die Aufbewahrung pro Workload:</span><span class="sxs-lookup"><span data-stu-id="c4280-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="c4280-110">Exchange Online (beliebige Konfiguration): 1.800</span><span class="sxs-lookup"><span data-stu-id="c4280-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="c4280-111">SharePoint oder OneDrive: (alle Websites automatisch enthalten): 13</span><span class="sxs-lookup"><span data-stu-id="c4280-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="c4280-112">SharePoint oder OneDrive (bestimmte Speicherorte eingeschlossen oder ausgeschlossen): 2.600</span><span class="sxs-lookup"><span data-stu-id="c4280-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="c4280-113">Höchstzahl der Einträge pro Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c4280-113">Maximum number of items per policy</span></span>

<span data-ttu-id="c4280-114">Wenn Sie die optionale Konfiguration verwenden, um Ihre Aufbewahrungseinstellungen auf bestimmte Benutzer, bestimmte Microsoft 365-Gruppen oder bestimmte Websites auszudehnen, gibt es einige Einschränkungen pro Richtlinie, die zu beachten sind:</span><span class="sxs-lookup"><span data-stu-id="c4280-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="c4280-115">Maximale Anzahl von Elementen pro Aufbewahrungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="c4280-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="c4280-116">1.000 Postfächer (Benutzerpostfächer oder Gruppenpostfächer)</span><span class="sxs-lookup"><span data-stu-id="c4280-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="c4280-117">1.000 Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="c4280-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="c4280-118">1.000 Benutzer für private Teams-Chats</span><span class="sxs-lookup"><span data-stu-id="c4280-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="c4280-119">100 Websites (OneDrive oder SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c4280-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="c4280-120">Da diese Grenzwerte pro Richtlinie gelten, können Sie bei der Verwendung spezifischer Ein- oder Ausschlüsse, die dazu führen, dass diese Werte überschritten werden, zusätzliche Richtlinien mit denselben Aufbewahrungseinstellungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4280-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="c4280-121">[Beispielszenarios und Lösungen](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), die aus diesem Grund mehrere Aufbewahrungsrichtlinien verwenden, finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c4280-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="c4280-122">Mehrere Aufbewahrungsrichtlinien führen jedoch zu erhöhtem Verwaltungsaufwand. Prüfen Sie also immer sehr genau, ob Sie Ein- und Ausschlüsse benötigen.</span><span class="sxs-lookup"><span data-stu-id="c4280-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="c4280-123">Denken Sie daran, dass die Standardkonfiguration, die für den gesamten Standort gilt, nicht diesen Einschränkungen unterliegt. Und diese Konfigurationswahl könnte eine bessere Lösung sein, als mehrere Richtlinien zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c4280-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="c4280-124">Wenn Sie mehrere Richtlinien für dieses Szenario erstellen und verwalten müssen, erwägen Sie die Verwendung der [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) für eine effizientere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c4280-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="c4280-125">Beispiele für die Verwendung mehrerer Richtlinien zur Vermeidung einer Überschreitung der maximalen Werte</span><span class="sxs-lookup"><span data-stu-id="c4280-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="c4280-126">Die folgenden Beispiele bieten ein paar Entwurfslösungen für Fälle, in denen Sie nicht einfach den Ort für eine Aufbewahrungsrichtlinie angeben können, sondern die im vorherigen Abschnitt dokumentierte maximale Anzahl von Elementen berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="c4280-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="c4280-127">Exchange-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c4280-127">Exchange example:</span></span>

- <span data-ttu-id="c4280-128">**Voraussetzung**: In einer Organisation, die mehr als 40.000 Benutzerpostfächer hat, müssen die E-Mails der meisten Benutzer für 7 Jahre aufbewahrt werden, aber für eine Untermenge identifizierter Benutzer (425) müssen die E-Mails nur 5 Jahre aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="c4280-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="c4280-129">**Lösung**: Erstellen Sie eine Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 7 Jahren, und schließen Sie die Untermenge der Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="c4280-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="c4280-130">Erstellen Sie dann eine zweite Aufbewahrungsrichtlinie für Exchange-E-Mail mit einem Aufbewahrungszeitraum von 5 Jahren, und schließen Sie die Untermenge der Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="c4280-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="c4280-131">In beiden Fällen liegt die Anzahl der ein- und ausgeschlossenen Benutzer unter der maximalen Anzahl angegebener Postfächer für eine einzelne Richtlinie, und die Untermenge der Benutzer muss explizit aus der ersten Richtlinie ausgeschlossen werden, weil sie einen längeren [Aufbewahrungszeitraum](retention.md#the-principles-of-retention-or-what-takes-precedence) als die zweite Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="c4280-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="c4280-132">Wäre für die Untermenge von Benutzern eine Aufbewahrungsrichtlinie mit längerem Aufbewahrungszeitraum erforderlich, müssten Sie sie nicht aus der ersten Richtlinie ausschließen.</span><span class="sxs-lookup"><span data-stu-id="c4280-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="c4280-133">Bei dieser Lösung wird, wenn ein neuer Benutzer der Organisation beitritt, dessen Postfach automatisch in die erste Richtlinie für 7 Jahre aufgenommen, was keine Auswirkungen auf die maximale Anzahl unterstützter Benutzer hat.</span><span class="sxs-lookup"><span data-stu-id="c4280-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="c4280-134">Neue Benutzer, für die ein Aufbewahrungszeitraum von 5 Jahren erforderlich ist, erhöhen jedoch die Ein- und Ausschlussanzahl, deren Grenzwert bei 1.000 erreicht würde.</span><span class="sxs-lookup"><span data-stu-id="c4280-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="c4280-135">SharePoint-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c4280-135">SharePoint example:</span></span>

- <span data-ttu-id="c4280-136">**Voraussetzung**: Eine Organisation hat mehrere Tausend SharePoint-Sites, aber nur 2.000 Sites erfordern einen Aufbewahrungszeitraum von 10 Jahren, und 8.000 Sites erfordern einen Aufbewahrungszeitraum von 4 Jahren.</span><span class="sxs-lookup"><span data-stu-id="c4280-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="c4280-137">**Lösung**: Erstellen Sie 20 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 10 Jahren, die 100 spezifische Sites enthalten, und erstellen Sie 80 Aufbewahrungsrichtlinien für SharePoint mit einem Aufbewahrungszeitraum von 4 Jahren, die 100 spezifische Sites enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4280-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="c4280-138">Da Sie nicht alle SharePoint-Sites aufbewahren müssen, müssen Sie Aufbewahrungsrichtlinien erstellen, die die spezifischen Sites angeben.</span><span class="sxs-lookup"><span data-stu-id="c4280-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="c4280-139">Da eine Aufbewahrungsrichtlinie nicht mehr als 100 angegebene Sites unterstützt, müssen Sie mehrere Richtlinien für die zwei Aufbewahrungszeiträume erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4280-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="c4280-140">Diese Aufbewahrungszeiträume belegen die maximale Anzahl eingeschlossener Sites, weshalb die nächste neue Site, die aufbewahrt werden muss, eine neue Aufbewahrungsrichtlinie erfordern würde, unabhängig vom Aufbewahrungszeitraum.</span><span class="sxs-lookup"><span data-stu-id="c4280-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>