---
title: Benennungsänderungen im Microsoft 365 Defender Advanced Hunting-Schema
description: Nachverfolgen und Überprüfen von Namensänderungen in Tabellen und Spalten im Schema für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Daten, Namensänderungen, Umbenennen, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932202"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Schema der erweiterten Suche – Namensänderungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) wird regelmäßig aktualisiert, um neue Tabellen und Spalten hinzuzufügen. In einigen Fällen werden vorhandene Spaltennamen umbenannt oder ersetzt, um die Benutzerfreundlichkeit zu verbessern. In diesem Artikel finden Sie Informationen zu Namensänderungen, die sich auf Ihre Abfragen auswirken könnten.

Namensänderungen werden automatisch auf Abfragen angewendet, die im Security Center gespeichert werden, einschließlich Abfragen, die von benutzerdefinierten Erkennungsregeln verwendet werden. Sie müssen diese Abfragen nicht manuell aktualisieren. Sie müssen jedoch die folgenden Abfragen aktualisieren:
- Abfragen, die mit der API ausgeführt werden
- Abfragen, die an anderer Stelle außerhalb des Sicherheitscenters gespeichert werden

## <a name="december-2020"></a>Dezember 2020

| Tabellenname | Ursprünglicher Spaltenname | Neuer Spaltenname | Änderungsgrund
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Kundenfeedback |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Kundenfeedback |

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)