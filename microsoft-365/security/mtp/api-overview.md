---
title: Übersicht über Microsoft 365 Defender-APIs
description: Informationen zu den verfügbaren APIs in Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922186"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Übersicht über Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender baut auf einer integrationsbereiten Plattform auf.

Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf dem gemeinsam genutzten Vorfall und erweiterten Nachschlagetabellen zu automatisieren.

- **[Warteschlange für kombinierte](api-incident.md)** Vorfälle – Konzentrieren Sie sich auf das Wichtige, indem Sie den vollständigen Angriffsbereich und alle sich auswirkenden Ressourcen unter der Vorfall-API gruppieren.

- **[Produktübergreifende](api-advanced-hunting.md)** Bedrohungssuche : Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Anzeichen von Kompromissen zu fahnen, indem Sie Eigene benutzerdefinierte Abfragen erstellen, um Rohdaten zu siften, die in mehreren Schutzprodukten gesammelt wurden.

Zusammen mit diesen microsoft 365 Defender-spezifischen APIs stellen unsere anderen Sicherheitsprodukte zusätzliche [APIs](api-articles.md) bereit, um die vorteile ihrer einzigartigen Funktionen zu nutzen.

## <a name="learn-more"></a>Weitere Informationen

| **Informationen zum Zugriff auf die APIs** |
|-|
| [Informationen zu API-Kontingenten und -Lizenzierung](api-terms.md) |
| [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md) |
| **Erstellen von Apps** |
| [Erstellen einer "Hello world"-App](api-hello-world.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md) |
| [Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs](api-partner-access.md) |
| **Problembehandlung und Wartung Ihrer Apps** |
| [Verstehen von API-Fehlercodes](api-error-codes.md) |
| [Verwalten von Geheimschlüsseln in Ihren Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementieren der OAuth 2.0-Autorisierung für die Benutzer-Anmeldung](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |