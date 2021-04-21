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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904188"
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


> [!NOTE]
> Der Übergang zum einheitlichen Portal sollte sich nicht auf die PowerBi-Dashboards auswirken, die auf Microsoft Defender for Endpoint-APIs basieren. Sie können unabhängig vom interaktiven Portalübergang weiterhin mit den vorhandenen APIs arbeiten.


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