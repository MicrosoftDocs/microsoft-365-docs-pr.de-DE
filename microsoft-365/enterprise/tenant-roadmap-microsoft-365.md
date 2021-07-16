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
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464033"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mandanten-Roadmap für Microsoft 365

Ihr Microsoft 365 Mandant ist der Satz von Diensten, die Ihrer Organisation zugewiesen sind. In der Regel ist dieser Mandant einem oder mehreren Ihrer öffentlichen DNS-Domänennamen zugeordnet und fungiert als zentraler und isolierter Container für verschiedene Abonnements und die darin enthaltenen Lizenzen, die Sie Benutzerkonten zuweisen. Weitere Informationen finden Sie unter [Abonnements, Lizenzen, Konten und Mandanten für die Cloudangebote von Microsoft.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

Wenn Sie einen Microsoft 365 Mandanten erstellen, weisen Sie ihn einem bestimmten geografischen Standort zu. Sie können auch einen Mandanten mit mehreren geografischen Standorten haben und Ihren Mandanten von einem Standort an einen anderen verschieben.

Um Ihren Mandanten für Benutzer, Gruppen, Lizenzen und Cloud-Apps vorzubereiten, ist es wichtig, Ihre Mandantenkonfiguration sorgfältig zu planen und auszuführen.

## <a name="set-up-your-microsoft-365-tenant"></a>Richten Sie Ihren Microsoft 365-Mandanten ein.

Nachdem Sie sichergestellt haben, dass Ihr Netzwerk für den Zugriff auf Microsoft 365 sowohl für lokale als auch für Remotemitarbeiter optimiert ist, planen und konfigurieren Sie dann Ihren Microsoft 365 Mandanten für DNS-Domänennamen, allgemeine Dienste und für diese Identitätsinfrastruktur, die die sichere Benutzeranmeldung unterstützt.

### <a name="plan"></a>Plan

So planen Sie ihre Mandantenimplementierung:

- [Grundlegendes zu Abonnements, Lizenzen und Azure Active Directory (Azure AD)-Mandanten](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Grundlegendes zur Verwendung von SSL-Zertifikaten von Drittanbietern](plan-for-third-party-ssl-certificates.md)
- [Verstehen, wie ein Microsoft 365 Mandant in Azure AD-Dienste integriert ist](integrated-apps-and-azure-ads.md)
- [Planen der Client-App-Unterstützung](microsoft-365-client-support-certificate-based-authentication.md)
- [Bestimmen, wie die moderne Hybridauthentifizierung verwendet wird](hybrid-modern-auth-overview.md)
- [Planen von Upgrades für Office 2007 und Office 2010](plan-upgrade-previous-versions-office.md)
- [Grundlegendes zur Mandantenisolation](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>Bereitstellen

So stellen Sie Ihren Mandanten bereit: 

- Fügen Sie die [DNS-Domänen](../admin/setup/add-domain.md) für Ihre Organisation hinzu.
- Verwenden Sie die [Einrichtungshandbücher in der Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).
- Erstellen Sie Ihre [Identitätsinfrastruktur,](identity-roadmap-microsoft-365.md) und [sichern Sie Ihre Benutzeranmeldungen.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Verschieben der geografischen Standorte eines Mandanten

Microsoft öffnet weiterhin neue geografische Standorte für Rechenzentren (Geos) für Microsoft 365 Dienste. Diese neuen Rechenzentrumsregionen fügen Kapazität und Rechenressourcen hinzu, um die Kundenanforderungen und das Wachstum der Nutzung zu unterstützen. Darüber hinaus bieten die neuen Rechenzentrumsregionen die Aufbewahrung von Kundenkerndaten innerhalb der Geografie.

Weitere Informationen finden Sie unter [Verschieben von Kerndaten in neue Microsoft 365 Rechenzentrumsregionen.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Bereitstellen von Microsoft 365 Multi-Geo

Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern.

Mehr dazu unter [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Verwalten mehrerer Microsoft 365 Mandanten 

Obwohl ein einzelner Mandant für Ihre Organisation ideal ist, können Sie eine von vielen Organisationen mit mehreren Mandanten sein. Gründe können Fusionen und Käufe sein, Sie möchten eine administrative Isolation oder eine dezentralisierte IT.

Wenn Sie über mehrere Microsoft 365 Mandanten verfügen, finden Sie in den folgenden Artikeln weitere Informationen zu:

- [Zusammenarbeit zwischen Mandanten](microsoft-365-inter-tenant-collaboration.md)
- [Mandantenübergreifende Postfachmigration](cross-tenant-mailbox-migration.md)
- [Migrationen zwischen Mandanten](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Nächster Schritt

Beginnen Sie ihre Mandantenplanung mit [Abonnements, Lizenzen, Konten und Mandanten.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)