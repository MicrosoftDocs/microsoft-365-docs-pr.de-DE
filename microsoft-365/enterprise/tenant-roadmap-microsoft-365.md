---
title: Mandanten-Roadmap für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Die Roadmap zum Einrichten Ihrer Mandanten für Microsoft 365.
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446007"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mandanten-Roadmap für Microsoft 365

Ihr Microsoft 365-Mandant ist die Gruppe von Diensten, die Ihrer Organisation zugewiesen sind. Normalerweise ist dieser Mandant einem oder mehreren Ihrer DNS-Domänennamen zugeordnet und fungiert als zentraler Container für unterschiedliche Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen.

Wenn Sie einen Microsoft 365-Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu. Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und den Mandanten von einem Standort an einen anderen Speicherort verlagern.

Um ihren Mandanten für die grundlegenden Dienste von Netzwerk und Identität vorzubereiten, ist es wichtig, die Mandanten Konfiguration sorgfältig zu planen und auszuführen.

## <a name="plan"></a>Plan

So planen Sie die Implementierung Ihres Mandanten:

- [Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Grundlegendes zur Verwendung von Drittanbieter-SSL-Zertifikaten](plan-for-third-party-ssl-certificates.md)
- [Grundlegendes zu den Möglichkeiten, mit denen ein Microsoft 365-Mandant in Azure AD Dienste integriert ist](integrated-apps-and-azure-ads.md)
- [Planen der Client-App-Unterstützung](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestimmen der Verwendung der modernen Hybrid Authentifizierung](hybrid-modern-auth-overview.md)
- [Planen von Office 2007-und Office 2010 Upgrades](plan-upgrade-previous-versions-office.md)
- [Grundlegendes zur Mandanten Isolierung](microsoft-365-tenant-isolation-overview.md)
- [Abrufen der Details zu Microsoft 365 Service Assurance](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Bereitstellen

Um ihren Mandanten bereitzustellen, [fügen Sie die DNS-Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) für Ihre Organisation hinzu, und verwenden Sie die [Setup Handbücher im Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).

## <a name="tenants-with-multiple-geographic-locations"></a>Mandanten mit mehreren geografischen Standorten

Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.

Informationen zu Microsoft 365 Multi-Geo, einschließlich der Planung, Konfiguration und Verwaltung, finden Sie [hier](microsoft-365-multi-geo.md).

## <a name="move-a-tenants-geographic-locations"></a>Migrieren der geografischen Standorte eines Mandanten

Microsoft öffnet weiterhin die neuen geografischen Standorte für das Rechenzentrum (GEOS) für Microsoft 365-Dienste. In diesem neuen Datencenter-GEOS wird Kapazität hinzugefügt und Ressourcen zur Unterstützung von Kundenanforderungen und Nutzungs Wachstum berechnet. Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.

Informationen zu Microsoft 365 Datacenter Geo, einschließlich der Vorgehensweise zum Anfordern einer Geo-Datenverlagerung, [finden Sie hier](moving-data-to-new-datacenter-geos.md).

## <a name="next-step"></a>Nächster Schritt

Starten Sie Ihre Mandanten Planung mit [Abonnements, Lizenzen, Konten und Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

