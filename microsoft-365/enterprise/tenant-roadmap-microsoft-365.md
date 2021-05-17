---
title: Mandanten-Roadmap für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Die Roadmap zum Einrichten Ihrer Mandanten für Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909454"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mandanten-Roadmap für Microsoft 365

Ihr Microsoft 365-Mandant ist der Satz von Diensten, die Ihrer Organisation zugewiesen sind. In der Regel ist dieser Mandant einem oder mehreren öffentlichen DNS-Domänennamen zugeordnet und fungiert als zentraler und isolierter Container für verschiedene Abonnements und die zugehörigen Lizenzen, die Sie Benutzerkonten zuweisen. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)Mandanten für die Cloudangebote von Microsoft .

Wenn Sie einen Microsoft 365 erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu. Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und Ihren Mandanten von einem Standort an einen anderen verschieben.

Um Ihren Mandanten für Benutzer, Gruppen, Lizenzen und Cloud-Apps bereit zu machen, ist es wichtig, ihre Mandantenkonfiguration sorgfältig zu planen und auszuführen.

## <a name="set-up-your-microsoft-365-tenant"></a>Richten Sie Ihren Microsoft 365-Mandanten ein.

Nachdem Sie sichergestellt haben, dass Ihr Netzwerk für den Zugriff auf Microsoft 365 für lokale und Remotemitarbeiter optimiert ist, planen und konfigurieren Sie ihren Microsoft 365-Mandanten für DNS-Domänennamen, gemeinsame Dienste und für diese Identitätsinfrastruktur, die die sichere Benutzeranmeldeung unterstützt.

### <a name="plan"></a>Plan

So planen Sie die Mandantenimplementierung:

- [Verstehen von Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Informationen zur Verwendung von DRITTANBIETER-SSL-Zertifikaten](plan-for-third-party-ssl-certificates.md)
- [Verstehen der Integration Microsoft 365 Mandanten in Azure AD-Dienste](integrated-apps-and-azure-ads.md)
- [Planen der Client-App-Unterstützung](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestimmen der Verwendung der modernen Hybridauthentifizierung](hybrid-modern-auth-overview.md)
- [Planen von Office 2007- und Office 2010-Upgrades](plan-upgrade-previous-versions-office.md)
- [Verstehen der Mandantenisolation](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Bereitstellen

So stellen Sie Ihren Mandanten zur Bereitstellung ein: 

- Fügen Sie die [DNS-Domänen](../admin/setup/add-domain.md) für Ihre Organisation hinzu.
- Verwenden Sie [die Setupanleitungen im Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).
- Erstellen Sie Ihre [Identitätsinfrastruktur,](identity-roadmap-microsoft-365.md) und [sichern Sie Ihre Benutzer-Anmeldungen.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Verschieben der geografischen Standorte eines Mandanten

Microsoft öffnet weiterhin neue geografische Standorte des Rechenzentrums (Geos) für Microsoft 365 Dienste. Diese neuen Rechenzentrums-Geos fügen Kapazitäts- und Rechenressourcen hinzu, um die Kundenanforderungen und das Nutzungswachstum zu unterstützen. Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.

Weitere Informationen finden Sie unter [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Bereitstellen Microsoft 365 Multi-Geo

Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.

Mehr dazu unter [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Verwalten mehrerer Microsoft 365 Mandanten 

Obwohl ein einzelner Mandant für Ihre Organisation ideal ist, sind Sie möglicherweise eine von vielen Organisationen mit mehreren Mandanten. Gründe können Fusionen und Übernahmen, eine administrative Isolation oder eine dezentralisierte IT sein.

Wenn Sie über mehrere Microsoft 365 verfügen, finden Sie in diesen Artikeln weitere Informationen zu:

- [Zusammenarbeit zwischen Mandanten](microsoft-365-inter-tenant-collaboration.md)
- [Mandantenübergreifende Postfachmigration](cross-tenant-mailbox-migration.md)
- [Migrationen zwischen Mandanten](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Nächster Schritt

Starten Sie Ihre Mandantenplanung mit [Abonnements, Lizenzen, Konten und Mandanten.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)