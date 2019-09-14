---
title: Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung
author: JoeDavies-MSFT
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
ms.openlocfilehash: c8d7aed1422f9d0c5891157e6fb7d3d30d976c4a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981896"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="610fa-103">Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="610fa-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="610fa-104">[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Features und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610fa-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="610fa-105">So erstellen Sie eine Testumgebung mit diesen Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="610fa-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="610fa-106">Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:</span><span class="sxs-lookup"><span data-stu-id="610fa-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="610fa-107">Reine Cloudbereitstellung</span><span class="sxs-lookup"><span data-stu-id="610fa-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="610fa-108">Kennworthashsynchronisierung (Password Hash Sync, PHS)</span><span class="sxs-lookup"><span data-stu-id="610fa-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="610fa-109">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="610fa-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="610fa-110">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen, und testen Sie den Schutz für Identitäten und Geräte.</span><span class="sxs-lookup"><span data-stu-id="610fa-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="610fa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610fa-111">See also</span></span>

[<span data-ttu-id="610fa-112">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="610fa-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="610fa-113">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="610fa-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="610fa-114">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="610fa-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="610fa-115">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="610fa-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="610fa-116">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="610fa-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
