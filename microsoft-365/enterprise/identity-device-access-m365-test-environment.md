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
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327807"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Identitäts- und Gerätezugriff für Ihre Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

[Konfigurationen für den Identitäts-und Geräte Zugriff](microsoft-365-policies-configurations.md) sind eine Reihe von Features und Richtlinien für den bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste, die in Azure Active Directory (Azure AD) integriert sind.

So erstellen Sie eine Testumgebung, in der die allgemeinen Konfigurationen für den Identitäts-und Geräte Zugriff implementiert sind:

1. Konfigurieren Sie Ihre Testumgebung mit den erforderlichen Identitäts- und Sicherheitsfeatures, basierend auf dem von Ihnen gewählten Identitätsmodell und der gewählten Authentifizierungsmethode:

  - [Reine Cloudbereitstellung](cloud-only-prereqs-m365-test-environment.md)
  - [Kennworthashsynchronisierung (Password hash synchronization, PHS)](phs-prereqs-m365-test-environment.md)
  - [Passthrough-Authentifizierung (PTA)](pta-prereqs-m365-test-environment.md)

2. Verwenden Sie [Allgemeine Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) , um die Richtlinien zu konfigurieren, die auf den für Ihre Testumgebung konfigurierten Voraussetzungen aufbauen und den Schutz von Identitäten und Geräten untersuchen und überprüfen.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für zusätzliche Identitäten](m365-enterprise-test-lab-guides.md#identity)

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
