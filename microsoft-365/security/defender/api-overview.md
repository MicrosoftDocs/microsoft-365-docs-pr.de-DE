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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029729"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Übersicht über Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft 365 Defender basiert auf einer integrationsfähigen Plattform.

Verwenden Sie die Microsoft 365 Defender-APIs, um Workflows basierend auf den freigegebenen Vorfall- und erweiterten Suchtabellen zu automatisieren.

- **[Kombinierte Vorfallwarteschlange](api-incident.md)** – Konzentrieren Sie sich auf das, was wichtig ist, indem Sie den gesamten Angriffsbereich und alle betroffenen Ressourcen unter der Vorfall-API gruppieren.

- **[Produktübergreifende Bedrohungssuche](api-advanced-hunting.md)** – Nutzen Sie das Organisationswissen Ihres Sicherheitsteams, um nach Gefährdungszeichen zu suchen, indem Sie Eigene benutzerdefinierte Abfragen erstellen, um rohe Daten zu durchsuchen, die über mehrere Schutzprodukte gesammelt werden.

Verwenden Sie die [Streaming-API,](../defender-endpoint/raw-data-export.md) um Echtzeitereignisse und Warnungen von Instanzen zu versenden, sobald sie innerhalb eines einzelnen Datenstroms auftreten.

Zusammen mit diesen Microsoft 365 Defender-spezifischen APIs macht jedes unserer anderen Sicherheitsprodukte [zusätzliche APIs](api-articles.md) verfügbar, die Ihnen dabei helfen, ihre einzigartigen Funktionen zu nutzen.

> [!NOTE]
> Der Übergang zum einheitlichen Portal sollte sich nicht auf die PowerBi-Dashboards auswirken, die auf Microsoft Defender für Endpunkt-APIs basieren. Sie können weiterhin mit den vorhandenen APIs arbeiten, unabhängig vom Übergang zum interaktiven Portal.

## <a name="learn-more"></a>Weitere Informationen

| **Grundlegendes zum Zugriff auf die APIs** |
|-|
| [Informationen zu API-Kontingenten und Lizenzierung](api-terms.md) |
| [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md) |
| **Erstellen von Apps** |
| [Erstellen einer "Hello World"-App](api-hello-world.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers](api-create-app-user-context.md) |
| [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md) |
| [Erstellen einer App mit mehrinstanzenfähigem Partnerzugriff auf Microsoft 365 Defender APIs](api-partner-access.md) |
| **Problembehandlung und Verwaltung Ihrer Apps** |
| [Grundlegendes zu API-Fehlercodes](api-error-codes.md) |
| [Verwalten geheimer Schlüssel in Ihren Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementieren der OAuth 2.0-Autorisierung für die Benutzeranmeldung](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |