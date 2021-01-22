---
title: Übersicht über Microsoft 365 Defender-APIs
description: Erfahren Sie mehr über die verfügbaren APIs in Microsoft 365 Defender
keywords: API, APIs, Übersicht, Vorfall, Vorfälle, Bedrohungssuche, Microsoft 365 Defender
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
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931002"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Übersicht über Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender baut auf einer integrationsbereiten Plattform auf.

Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf dem gemeinsam genutzten Vorfall und erweiterten Tabellen für die Suche zu automatisieren.

- **[Kombinierte Vorfallswarteschlange](api-incident.md)** – Konzentrieren Sie sich auf wichtige Elemente, indem Sie den vollständigen Angriffsbereich und alle angegriffenen Ressourcen unter der Vorfall-API gruppieren.

- **[Produktübergreifende](api-advanced-hunting.md)** Bedrohungssuche – Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Anzeichen von Gefährdungen zu suchen, indem Sie eigene benutzerdefinierte Abfragen erstellen, um Rohdaten zu diebstahl, die in mehreren Schutzprodukten gesammelt wurden.

Zusammen mit diesen Microsoft 365 Defender-spezifischen APIs macht jedes unserer anderen Sicherheitsprodukte zusätzliche [APIs](api-articles.md) verfügbar, damit Sie ihre einzigartigen Funktionen nutzen können.

## <a name="learn-more"></a>Weitere Informationen

| **Verstehen des Zugriffs auf die APIs** |
|-|
| [Informationen zu API-Kontingenten und -Lizenzierung](api-terms.md) |
| [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md) |
| **Erstellen von Apps** |
| [Erstellen einer "Hello world"-App](api-hello-world.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md) |
| [Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 -Defender-APIs](api-partner-access.md) |
| **Problembehandlung und Wartung Ihrer Apps** |
| [Verstehen von API-Fehlercodes](api-error-codes.md) |
| [Verwalten geheimer Schlüssel in Ihren Apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementieren der OAuth 2.0-Autorisierung für die Benutzer anmeldung](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
