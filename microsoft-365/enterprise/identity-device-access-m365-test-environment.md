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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung, um Identitäts- und Gerätezugriff zu testen.
ms.openlocfilehash: e43483afc9e17de9582b2998867b53cfff7d8492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601002"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="165c4-103">Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="165c4-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="165c4-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="165c4-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="165c4-105">[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Features und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="165c4-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="165c4-106">So erstellen Sie eine Testumgebung mit diesen Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="165c4-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="165c4-107">Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:</span><span class="sxs-lookup"><span data-stu-id="165c4-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="165c4-108">Reine Cloudbereitstellung</span><span class="sxs-lookup"><span data-stu-id="165c4-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="165c4-109">Kennworthashsynchronisierung (Password Hash Sync, PHS)</span><span class="sxs-lookup"><span data-stu-id="165c4-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="165c4-110">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="165c4-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="165c4-111">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen, und testen Sie den Schutz für Identitäten und Geräte.</span><span class="sxs-lookup"><span data-stu-id="165c4-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="165c4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="165c4-112">See also</span></span>

[<span data-ttu-id="165c4-113">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="165c4-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="165c4-114">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="165c4-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="165c4-115">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="165c4-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="165c4-116">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="165c4-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="165c4-117">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="165c4-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
