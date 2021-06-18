---
title: Zusätzliche Informationen für Cloudlösungsanbieter
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Zusätzliche, für die Migration aus der Microsoft Cloud Deutschland relevante Informationen für Cloudlösungsanbieter.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984916"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="a7dfb-103">Zusätzliche Informationen für Cloudlösungsanbieter</span><span class="sxs-lookup"><span data-stu-id="a7dfb-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="a7dfb-104">Cloudlösungsanbieter (Cloud Solution Providers, CSPs), die Kunden unterstützen, müssen während der Migration von Microsoft Cloud Deutschland in die neue deutsche Rechenzentrumsregion zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="a7dfb-105">Partner-Mandantenmigration</span><span class="sxs-lookup"><span data-stu-id="a7dfb-105">Partner tenant migration</span></span>

<span data-ttu-id="a7dfb-106">Partnermandanten von Microsoft Cloud Deutschland werden nicht migriert.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="a7dfb-107">Stattdessen wird für jeden Microsoft Partner in der neuen deutschen Rechenzentrumsregion ein neuer Office 365-Dienstmandant erstellt.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="a7dfb-108">CSP-Kundenmandanten werden in die neue deutsche Rechenzentrumsregion migriert und mit dem neuen Office 365-Dienstmandanten des gleichen Partners verknüpft.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="a7dfb-109">Nach der Umstellung des Kunden kann der Partner den Kunden mit dem neuen Office 365-Dienstmandanten in der deutschen Rechenzentrumsregion verwalten.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="a7dfb-110">Fehlende Abonnements in Azure</span><span class="sxs-lookup"><span data-stu-id="a7dfb-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="a7dfb-111">Nachdem die [Abonnement- und Lizenzumstellung (Phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) abgeschlossen ist, haben Cloudlösungsanbieter keinen Zugriff mehr auf die Azure-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="a7dfb-112">Um den Zugriff wiederherzustellen, führen Sie diese Schritte aus, um [den Zugriff auf die Verwaltung aller Azure-Abonnements und Verwaltungsgruppen zu erhöhen](/azure/role-based-access-control/elevate-access-global-admin).</span><span class="sxs-lookup"><span data-stu-id="a7dfb-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
