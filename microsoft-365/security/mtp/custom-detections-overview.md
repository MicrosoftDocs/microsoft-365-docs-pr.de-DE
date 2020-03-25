---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft Threat Protection
description: Grundlegendes zum Erstellen von benutzerdefinierten Erkennungen und Generieren von Benachrichtigungen mithilfe der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931732"
---
# <a name="custom-detections-overview"></a>Übersicht über benutzerdefinierte Erkennungen

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Mit benutzerdefinierten Erkennungen können Sie proaktiv auf verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte. Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen und Reaktions Aktionen auslösen.

Benutzerdefinierte Erkennungen arbeiten mit [Advanced Hunting](advanced-hunting-overview.md), die eine leistungsstarke, flexible Abfragesprache bietet, die eine umfassende Reihe von Ereignis-und Systeminformationen aus Ihrem Netzwerk abdeckt. Sie können festlegen, dass Sie in regelmäßigen Intervallen ausgeführt werden, indem Sie Warnungen generieren und Reaktions Aktionen ausführen, wenn Übereinstimmungen vorliegen.

Benutzerdefinierte Erkennungen stellen Folgendes bereit:
- Warnungen für regelbasierte Erkennungen, die aus erweiterten Jagd Abfragen erstellt wurden
- Automatische Antwort Aktionen

## <a name="related-topic"></a>Verwandtes Thema
- [Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln](custom-detection-rules.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)