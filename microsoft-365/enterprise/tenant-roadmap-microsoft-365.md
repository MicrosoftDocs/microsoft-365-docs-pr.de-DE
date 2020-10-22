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
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656007"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mandanten-Roadmap für Microsoft 365

Ihr Microsoft 365-Mandant ist die Gruppe von Diensten, die Ihrer Organisation zugewiesen sind. Normalerweise ist dieser Mandant einem oder mehreren Ihrer DNS-Domänennamen zugeordnet und fungiert als zentraler Container für unterschiedliche Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloud-Angebote von Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

Wenn Sie einen Microsoft 365-Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu. Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und den Mandanten von einem Standort an einen anderen Speicherort verlagern.

Um ihren Mandanten für die Identität vorzubereiten, ist es wichtig, die Mandanten Konfiguration sorgfältig zu planen und auszuführen.


## <a name="set-up-your-microsoft-365-tenant"></a>Einrichten Ihres Microsoft 365-Mandanten

Nachdem Sie sichergestellt haben, dass Ihr Netzwerk für den Zugriff auf Microsoft 365 sowohl für lokale als auch für Remotemitarbeiter optimiert ist, planen und konfigurieren Sie Ihren Microsoft 365-Mandanten für DNS-Domänennamen, gemeinsame Dienste und für diese Identitätsinfrastruktur, die die sichere Benutzeranmeldung unterstützt.

## <a name="plan"></a>Plan

So planen Sie die Implementierung Ihres Mandanten:

- [Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Grundlegendes zur Verwendung von Drittanbieter-SSL-Zertifikaten](plan-for-third-party-ssl-certificates.md)
- [Grundlegendes zu den Möglichkeiten, mit denen ein Microsoft 365-Mandant in Azure AD Dienste integriert ist](integrated-apps-and-azure-ads.md)
- [Planen der Client-App-Unterstützung](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestimmen der Verwendung der modernen Hybrid Authentifizierung](hybrid-modern-auth-overview.md)
- [Planen von Office 2007-und Office 2010 Upgrades](plan-upgrade-previous-versions-office.md)
- [Grundlegendes zur Mandanten Isolierung](microsoft-365-tenant-isolation-overview.md)
- [Abrufen der Details zu Microsoft 365 Service Assurance](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a>Bereitstellen

So stellen Sie den Mandanten bereit: 

- Fügen Sie die [DNS-Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) für Ihre Organisation hinzu.
- Verwenden Sie die [Installationshandbücher im Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).
- Erstellen Sie Ihre [Identitätsinfrastruktur](identity-roadmap-microsoft-365.md) , und [Sichern Sie Ihre Benutzeranmeldungen](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Migrieren der geografischen Standorte eines Mandanten

Microsoft öffnet weiterhin die neuen geografischen Standorte für das Rechenzentrum (GEOS) für Microsoft 365-Dienste. In diesem neuen Datencenter-GEOS wird Kapazität hinzugefügt und Ressourcen zur Unterstützung von Kundenanforderungen und Nutzungs Wachstum berechnet. Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.

Weitere Informationen finden Sie unter [Moving Core Data to New Microsoft 365 Datacenter GEOS](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Bereitstellen von Microsoft 365 Multi-Geo

Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.

Weitere Informationen finden Sie unter [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenancies"></a>Verwalten mehrerer Microsoft 365 Mandanten 

Obwohl ein einzelner Mandant für Ihre einer Organisation ideal ist, sind Sie möglicherweise eine von vielen Organisationen mit mehreren Mandanten. Gründe für mehrere Mandanten können Fusionen und Übernahmen umfassen, Sie möchten eine administrative Isolierung oder eine dezentrale IT-Verwaltung.

Wenn Sie mehrere Microsoft 365-Mandanten haben, lesen Sie diese Artikel, um weitere Informationen zu erhalten:

- [Zusammenarbeit zwischen Mandanten](microsoft-365-inter-tenant-collaboration.md)
- [Mandantenübergreifende Postfachmigration](cross-tenant-mailbox-migration.md)
- [Migrationen zwischen Mandanten](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a>Nächster Schritt

Starten Sie Ihre Mandanten Planung mit [Abonnements, Lizenzen, Konten und Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
