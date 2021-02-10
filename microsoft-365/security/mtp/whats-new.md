---
title: Neuerungen in Microsoft 365 Defender
description: Liste der neuen Features und Funktionen in Microsoft 365 Defender
keywords: Neues in Microsoft Threat Protection, ga, allgemein verfügbar, Funktionen, verfügbar, neu
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4e065ff4da80b50ea11ff2069e8938c59f16f962
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165991"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Neuerungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Möchten Sie Microsoft 365 Defender erleben? Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)
>

Die folgenden Features sind allgemein in der neuesten Version von Microsoft 365 Defender verfügbar.

RSS-Feed: Erhalten Sie eine Benachrichtigung, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feedreader kopieren und einfügen:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```

## <a name="february-2021"></a>Februar 2021
- (Vorschau) Das erweiterte [Microsoft 365 https://security.microsoft.com) Security Center (](https://security.microsoft.com) ist jetzt in der öffentlichen Vorschau verfügbar. Diese neue Erfahrung bringt Defender für Endpoint und Defender für Office 365 in den Mittelpunkt. [Erfahren Sie mehr über die Geänderten.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)

## <a name="september-2020"></a>September 2020
- [Tabelle "IdentityDirectoryEvents"](advanced-hunting-identitydirectoryevents-table.md) <br> Hier finden Sie Ereignisse, an denen ein lokales Domänencontroller beteiligt ist, auf dem Active Directory (AD) ausgeführt wird. Diese [Schematabelle für die](advanced-hunting-overview.md) erweiterte Suche deckt eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller ab.
- [AssignedIPAddresses()-Funktion](advanced-hunting-assignedipaddresses-function.md) <br> Verwenden Sie diese Funktion in Ihren Abfragen für die erweiterte Suche, um schnell die neuesten IP-Adressen zu erhalten, die einem Gerät zugewiesen sind, oder die neuesten IP-Adressen aus einem bestimmten Zeitraum.

## <a name="july-2020"></a>Juli 2020
- [FileProfile()-Funktion](advanced-hunting-fileprofile-function.md) <br> Verwenden Sie diese Funktion in Erweiterten Suchabfragen, um die Ergebnisse mit umfassenden Dateiinformationen zu erweitern.
- [Identitäts- und App-Tabellen](advanced-hunting-schema-tables.md)<br> Erhalten Sie Einblicke in Authentifizierungsereignisse, Active Directory-Abfragen und App-bezogene Aktivitäten mit den [IdentityLogonEvents-,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents-](advanced-hunting-identityqueryevents-table.md)und [AppFileEvents-Tabellen](advanced-hunting-appfileevents-table.md) im Schema für die erweiterte Suche.
- [Suche starten](advanced-hunting-go-hunt.md)<br> Schnelles Pivot von der Untersuchung eines Vorfalls bis zur Überprüfung eines bestimmten Ereignisses, eines Benutzers, eines Geräts oder anderer Entitätstypen bei der erweiterten Suche.

## <a name="june-2020"></a>Juni 2020
- Twitterfeed <br> Erhalten Sie aktuelle Sicherheitsrecherch, Bedrohungsintelligenz, Produktnachrichten und vieles mehr – direkt im Dashboard.
- [Schematabelle "EmailPostDeliveryEvents"](advanced-hunting-emailpostdeliveryevents-table.md) <br> Integrieren Sie Informationen zu Aktionen nach der Zustellung, die für E-Mail-Nachrichten ausgeführt werden, in Ihre Abfragen für die erweiterte Suche.
- [Überprüfen von Datensätzen bei der erweiterten Suche](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Überprüfen Sie die Datensätze in den Abfrageergebnissen schnell mit dem neuen Detailbereich.

## <a name="may-2020"></a>Mai 2020
- [Benutzerdefinierte Erkennungen](custom-detections-overview.md) <br> Verwenden Sie erweiterte Suchabfragen, um benutzerdefinierte Erkennungsregeln zu erstellen, die sicherheitsereignisse und Systemzustände automatisch überwachen und darauf reagieren.

## <a name="february-2020"></a>Februar 2020
- [Vorfälle](incidents-overview.md) <br> Sie wissen genau, wo ein Angriff begonnen hat, und weitere Details, die Ihnen helfen, das Ausmaß des Angriffs zu erkennen.
- [Automatische Untersuchung und Reaktion](mtp-autoir.md) <br> Mit AIR können Ihre Sicherheitsteams die Kapazität Ihrer Organisation im Umgang mit Sicherheitswarnungen und Vorfällen erheblich verbessern.
- [Verbesserungen bei der erweiterten Suche](advanced-hunting-overview.md) <br> Proaktive Suche nach Bedrohungen im modernen Arbeitsbereich mit kusto Query Language und einem sicherheitsoptimierten Schema.

## <a name="march-2019"></a>März 2019
- Erweiterte Suche <br> Angebotsseite für verschiedene Funktionen zur Suche, mit denen Sie proaktiv Bedrohungen finden können, die E-Mails und Daten, Geräte und Identitäten betreffen.
- [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) <br> Messung des Sicherheitsstands einer Organisation mit einer höheren Zahl, die mehr Verbesserungsmaßnahmen anzeigt. Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. 
- [Berichte](monitoring-and-reporting.md) <br>  Bietet eine Vielzahl von Karten, die eine Vielzahl von Bereichen abdecken, die Sicherheitsanalysten und Administratoren im Rahmen ihres täglichen Betriebs nachverfolgen.
