---
title: Übersicht über Microsoft 365 Defender-APIs
description: Erfahren Sie mehr über die verfügbaren APIs in Microsoft 365 Defender
keywords: API, APIs, Übersicht, Vorfall, Vorfälle, Bedrohungs Suche, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719190"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Übersicht über Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender ist auf einer integrationsfähigen Plattform aufgebaut.

Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf den freigegebenen Vorfällen und erweiterten Jagd Tabellen zu automatisieren.

- **[Kombinierte Vorfälle-Warteschlange](api-incident.md)** – konzentrieren Sie sich auf das, was kritisch ist, indem Sie den vollständigen Angriffsbereich und alle betroffenen Objekte zusammen mit der Vorfall-API gruppieren.

- **[Produktübergreifende Bedrohungs Suche](api-advanced-hunting.md)** – nutzen Sie das organisatorische wissen Ihres Sicherheitsteams, um nach Zeichen von Kompromissen zu suchen, indem Sie Ihre eigenen benutzerdefinierten Abfragen erstellen, um die Rohdaten zu Sichten, die über mehrere Schutzprodukte gesammelt wurden.

Zusammen mit diesen Microsoft 365 Defender-spezifischen APIs stellen alle unsere anderen Sicherheitsprodukte [zusätzliche APIs](api-articles.md) bereit, die Ihnen dabei helfen, ihre einzigartigen Funktionen zu nutzen.

## <a name="learn-more"></a>Weitere Informationen

| **Grundlegendes zum Zugriff auf die APIs** |
|-|
| [Informationen zu API-Kontingenten und Lizenzierung](api-terms.md) |
| [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md) |
| **Erstellen von Apps** |
| [Erstellen einer "Hello World"-App](api-hello-world.md) |
| [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md) |
| [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md) |
| [Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md) |
| **Problembehandlung und Wartung Ihrer Apps** |
| [Grundlegendes zu API-Fehlercodes](api-error-codes.md) |
| [Verwalten von Geheimnissen in ihren apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementieren der OAuth 2,0-Autorisierung für die Benutzeranmeldung](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
