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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984916"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Zusätzliche Informationen für Cloudlösungsanbieter

Cloudlösungsanbieter (Cloud Solution Providers, CSPs), die Kunden unterstützen, müssen während der Migration von Microsoft Cloud Deutschland in die neue deutsche Rechenzentrumsregion zusätzliche Schritte ausführen.

## <a name="partner-tenant-migration"></a>Partner-Mandantenmigration

Partnermandanten von Microsoft Cloud Deutschland werden nicht migriert. Stattdessen wird für jeden Microsoft Partner in der neuen deutschen Rechenzentrumsregion ein neuer Office 365-Dienstmandant erstellt.

CSP-Kundenmandanten werden in die neue deutsche Rechenzentrumsregion migriert und mit dem neuen Office 365-Dienstmandanten des gleichen Partners verknüpft. Nach der Umstellung des Kunden kann der Partner den Kunden mit dem neuen Office 365-Dienstmandanten in der deutschen Rechenzentrumsregion verwalten.

## <a name="missing-subscriptions-in-azure"></a>Fehlende Abonnements in Azure

Nachdem die [Abonnement- und Lizenzumstellung (Phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) abgeschlossen ist, haben Cloudlösungsanbieter keinen Zugriff mehr auf die Azure-Abonnements.

Um den Zugriff wiederherzustellen, führen Sie diese Schritte aus, um [den Zugriff auf die Verwaltung aller Azure-Abonnements und Verwaltungsgruppen zu erhöhen](/azure/role-based-access-control/elevate-access-global-admin).
