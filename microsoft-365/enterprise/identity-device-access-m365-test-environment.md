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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907468"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

[Identitäts- und Gerätezugriffskonfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe empfohlener Konfigurationen und Richtlinien für bedingten Zugriff, um den Zugriff auf alle Dienste zu schützen, die in Azure Active Directory (Azure AD) integriert sind.

So erstellen Sie eine Testumgebung mit gemeinsamen Identitäts- und Gerätezugriffskonfigurationen:

1. Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:

  - [Reine Cloudbereitstellung](cloud-only-prereqs-m365-test-environment.md)
  - [Kennworthashsynchronisierung (Password hash synchronization, PHS)](phs-prereqs-m365-test-environment.md)
  - [Passthrough-Authentifizierung (PTA)](pta-prereqs-m365-test-environment.md)

2. Verwenden [Sie allgemeine Identitäts- und](../security/office-365-security/identity-access-policies.md) Gerätezugriffsrichtlinien, um die Richtlinien zu konfigurieren, die auf den für Ihre Testumgebung konfigurierten Voraussetzungen aufbauen, und den Schutz von Identitäten und Geräten zu untersuchen und zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für zusätzliche Identitäten](m365-enterprise-test-lab-guides.md#identity)

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)