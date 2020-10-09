---
title: Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung, um Identitäts- und Gerätezugriff zu testen.
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398807"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b0282-103">Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b0282-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b0282-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="b0282-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b0282-105">[Konfigurationen für den Identitäts-und Geräte Zugriff](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe von Features und Richtlinien für den bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste, die in Azure Active Directory (Azure AD) integriert sind.</span><span class="sxs-lookup"><span data-stu-id="b0282-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="b0282-106">So erstellen Sie eine Testumgebung, in der die allgemeinen Konfigurationen für den Identitäts-und Geräte Zugriff implementiert sind:</span><span class="sxs-lookup"><span data-stu-id="b0282-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="b0282-107">Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:</span><span class="sxs-lookup"><span data-stu-id="b0282-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="b0282-108">Reine Cloudbereitstellung</span><span class="sxs-lookup"><span data-stu-id="b0282-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="b0282-109">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="b0282-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="b0282-110">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="b0282-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="b0282-111">Verwenden Sie [Allgemeine Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) , um die Richtlinien zu konfigurieren, die auf den für Ihre Testumgebung konfigurierten Voraussetzungen aufbauen und den Schutz von Identitäten und Geräten untersuchen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b0282-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0282-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0282-112">See also</span></span>

[<span data-ttu-id="b0282-113">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="b0282-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="b0282-114">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="b0282-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b0282-115">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b0282-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b0282-116">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b0282-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b0282-117">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="b0282-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
