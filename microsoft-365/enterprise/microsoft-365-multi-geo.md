---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie Ihre Microsoft 365-Präsenz in mehreren geografischen Regionen mit Microsoft 365 Multi-Geo erweitern können.
ms.openlocfilehash: 10f941549fd4899d5b3a14c97e6f301339702722
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171326"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="7ffa0-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="7ffa0-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="7ffa0-104">Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="7ffa0-105">Wenden Sie sich an Ihr Microsoft-Kontoteam, um Ihr multinationales Unternehmen für Microsoft 365 Multi-Geo anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="7ffa0-106">Mit Microsoft 365 Multi-Geo können Sie ruhende Daten an den Datenresistenz-Anforderungen entsprechenden geografischen Speicherorten bereitstellen und speichern und gleichzeitig die globale Bereitstellung moderner Produktivitätserfahrungen für Ihre Mitarbeiter in Gang setzen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="7ffa0-107">Eine Video Einführung in Microsoft 365 Multi-Geo finden Sie unter [SharePoint Online und OneDrive Multi-Geo, um zu steuern, wo sich Ihre Daten befinden](https://www.youtube.com/watch?v=Do9U3JuROhk).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="7ffa0-108">Multi-Geo-Architektur</span><span class="sxs-lookup"><span data-stu-id="7ffa0-108">Multi-Geo architecture</span></span>

<span data-ttu-id="7ffa0-109">In einer Multi-Geo-Umgebung verfügt Ihr Microsoft 365-Mandant über einen zentralen Standort (an dem Ihr Microsoft 365-Abonnement ursprünglich bereitgestellt wurde) und über einen oder mehrere Satellitenstandort(e).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="7ffa0-110">Die Informationen über geografische Standorte, Gruppen und Benutzer eines Multi-Geo-Mandanten werden in Azure Active Directory (AAD) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7ffa0-111">Da Ihre Mandanteninformationen zentral verwaltet und an jedem geografischen Speicherort synchronisiert werden, wird das globale Bewusstsein durch das Teilen von Informationen und Erfahrungen im gesamten Unternehmen erhöht.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Screenshot der Multi-Geo-Zuordnung aus der SharePoint-Admin Center](../media/multi-geo-world-map.png)

<span data-ttu-id="7ffa0-113">Beachten Sie, dass Microsoft 365 Multi-Geo nicht zur Leistungsoptimierung entwickelt wurde, sondern zur Einhaltung von Datenaufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="7ffa0-114">Informationen zur Leistungsoptimierung vom Microsoft 365 finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) oder kontaktieren Sie Ihre Supportgruppe.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="7ffa0-115">Begrifflichkeiten</span><span class="sxs-lookup"><span data-stu-id="7ffa0-115">Terminology</span></span>

<span data-ttu-id="7ffa0-116">Dies sind die wichtigsten Begriffe für die Beschreibung von Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="7ffa0-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="7ffa0-117">**Zentraler Standort** – Der geografische Standort, an dem Ihr Mandant ursprünglich bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="7ffa0-118">**Geo-Administrator** – Ein Administrator, der einen oder mehrere der angegebenen Satellitenstandorte verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="7ffa0-119">**Geo-Code** – Eine Code aus drei Buchstaben für einen bestimmten Geo-Standort.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="7ffa0-120">**Geo-Standort** – Ein geografischer Standort, der in einem Multi-Geo-Mandanten verwendet werden kann, um Daten zu hosten, einschließlich Exchange-Postfächer und OneDrive- und SharePoint-Seiten.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="7ffa0-121">**Bevorzugter Datenspeicherort (PLD)** – Eine vom Administrator festgelegte Benutzereigenschaft, die angibt, an welchem geographischen Standort das Exchange-Postfach des Benutzers und OneDrive bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="7ffa0-122">Der PLD gibt außerdem an, wo vom Benutzer erstellte SharePoint-Seiten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="7ffa0-123">**Satelliten-Standort** – Der geographische Standort, an dem die Geo-fähigen Microsoft 365-Arbeitslasten (SharePoint, OneDrive und Exchange) in einem Multi-Geo-Mandanten aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="7ffa0-124">**Mandant** – Darstellung einer Organisation in der Microsoft 365-Cloud, mit der in der Regel eine oder mehrere Domäne(n) verknüpft ist/sind (zum Beispiel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="7ffa0-125">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="7ffa0-125">Licensing</span></span>

<span data-ttu-id="7ffa0-126">Microsoft 365 Multi-Geo wird als Add-On bei den folgenden Microsoft 365-Abonnementplänen für EA-Kunden mit mindestens 250 Microsoft 365-Arbeitsplätzen im Mandanten und mindestens 5 % der Arbeitsplätze für die Nutzung von Multi-Geo bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="7ffa0-127">Wenden Sie sich für weitere Informationen an Ihr Microsoft-Team.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-127">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="7ffa0-128">Microsoft 365 F1, E1, E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="7ffa0-128">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="7ffa0-129">Exchange Online Plan 1 oder Plan 2</span><span class="sxs-lookup"><span data-stu-id="7ffa0-129">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="7ffa0-130">OneDrive for Business Plan 1 oder Plan 2</span><span class="sxs-lookup"><span data-stu-id="7ffa0-130">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="7ffa0-131">SharePoint Online Plan 1 oder Plan 2</span><span class="sxs-lookup"><span data-stu-id="7ffa0-131">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="7ffa0-132">Verfügbarkeit von Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="7ffa0-132">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="7ffa0-133">Microsoft 365 Multi-Geo wird derzeit in diesen Regionen und Ländern angeboten:</span><span class="sxs-lookup"><span data-stu-id="7ffa0-133">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="7ffa0-134">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="7ffa0-134">Getting started</span></span>

<span data-ttu-id="7ffa0-135">Gehen Sie folgendermaßen vor, um mit Multi-Geo loszulegen:</span><span class="sxs-lookup"><span data-stu-id="7ffa0-135">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="7ffa0-136">Arbeiten Sie mit Ihrem Kontoteam, um den Serviceplan für _Multi-Geo-Funktionen in Microsoft 365_ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-136">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="7ffa0-137">Sie werden angeleitet, die benötigten Lizenzen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-137">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="7ffa0-138">Multi-Geo ist für EA/Bestandskunden mit mindestens 250 Microsoft 365-Abonnements verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-138">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="7ffa0-139">Bevor Sie mit der Verwendung von Microsoft 365 Multi-Geo beginnen können, muss Ihr Exchange Online-Mandant durch Microsoft für die Unterstützung von Multi-Geo konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-139">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="7ffa0-140">Dieser einmalige Konfigurationsprozess wird ausgelöst, nach dem Sie den Service-Plan für *Multi-Geo-Funktionen in Microsoft 365* bestellt haben und die Lizenzen in Ihrem Mandanten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-140">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="7ffa0-141">Sie erhalten Arbeits Auslastungs spezifische Benachrichtigungen im [Microsoft 365-Nachrichtencenter](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) , sobald Ihr Mandant den Konfigurationsprozess für jede Arbeitsauslastung abgeschlossen hat, und Sie können dann mit der Konfiguration und Verwendung Ihrer Microsoft 365 Multi-Geo-Funktionen beginnen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-141">You will receive workload specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="7ffa0-142">Die für die Konfiguration eines Mandanten für die Multi-Geo-Unterstützung erforderliche Zeit variiert von Mandanten zu Mandanten, aber die meisten Mandanten werden innerhalb eines Monats nach Erhalt der Funktions Lizenzen fertig gestellt.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-142">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="7ffa0-143">Größere oder komplexere Mandanten benötigen möglicherweise mehr Zeit, um den Konfigurationsprozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-143">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="7ffa0-144">Wenden Sie sich bei Bedarf an Ihr Konto Team, um Details zu ihrem jeweiligen Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7ffa0-144">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="7ffa0-145">Lesen Sie den Abschnitt [Planen Ihrer Multi-Geo-Umgebung](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-145">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="7ffa0-146">Erfahren Sie mehr über das [Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md) und darüber, [wie Ihre Benutzer die Umgebung erleben](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-146">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="7ffa0-147">Wenn Sie für die Einrichtung von Microsoft 365 Multi-Geo bereit sind, [konfigurieren Sie Ihren Mandanten für Multi-Geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-147">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="7ffa0-148">[Einrichten der Suche](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="7ffa0-148">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ffa0-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ffa0-149">See also</span></span>

[<span data-ttu-id="7ffa0-150">Multi-Geo in Exchange Online und OneDrive</span><span class="sxs-lookup"><span data-stu-id="7ffa0-150">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="7ffa0-151">Multi-Geo-Funktionen in OneDrive und SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7ffa0-151">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="7ffa0-152">Multi-Geo-Funktionen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7ffa0-152">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="7ffa0-153">Teams in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="7ffa0-153">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
