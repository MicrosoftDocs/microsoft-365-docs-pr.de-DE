---
title: Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung, um Identitäts- und Gerätezugriff zu testen.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233728"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c6bc1-103">Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c6bc1-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c6bc1-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="c6bc1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c6bc1-105">[Identitäts- und Gerätezugriffskonfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe empfohlener Konfigurationen und Richtlinien für bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste, die in Azure Active Directory (Azure AD) integriert sind.</span><span class="sxs-lookup"><span data-stu-id="c6bc1-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c6bc1-106">So erstellen Sie eine Testumgebung mit gemeinsamen Identitäts- und Gerätezugriffskonfigurationen:</span><span class="sxs-lookup"><span data-stu-id="c6bc1-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="c6bc1-107">Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:</span><span class="sxs-lookup"><span data-stu-id="c6bc1-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="c6bc1-108">Reine Cloudbereitstellung</span><span class="sxs-lookup"><span data-stu-id="c6bc1-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c6bc1-109">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="c6bc1-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c6bc1-110">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="c6bc1-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="c6bc1-111">Verwenden [Sie allgemeine Identitäts- und](identity-access-policies.md) Gerätezugriffsrichtlinien, um die Richtlinien zu konfigurieren, die auf den für Ihre Testumgebung konfigurierten Voraussetzungen aufbauen, und den Schutz von Identitäten und Geräten zu untersuchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c6bc1-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6bc1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6bc1-112">See also</span></span>

[<span data-ttu-id="c6bc1-113">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="c6bc1-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="c6bc1-114">Identitätsplan</span><span class="sxs-lookup"><span data-stu-id="c6bc1-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c6bc1-115">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6bc1-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c6bc1-116">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6bc1-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c6bc1-117">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6bc1-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
