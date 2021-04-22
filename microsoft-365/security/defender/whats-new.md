---
title: Neuerungen in Microsoft 365 Defender
description: Listet die neuen Features und Funktionen in Microsoft 365 Defender auf.
keywords: Neues in Microsoft 365 Defender, ga, allgemein verfügbar, Funktionen, verfügbar, neu
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9f4cc36172b0ac598b2719bee8ce56bf0f8a1b84
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933385"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Neuerungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Die folgenden Features sind allgemein in der neuesten Version von Microsoft 365 Defender verfügbar.

RSS-Feed: Erhalten Sie eine Benachrichtigung, wenn diese Seite aktualisiert wird, indem Sie die folgende URL in Ihren Feedleser kopieren und einfügen:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a>März 2021
- [CloudAppEvents-Tabelle](advanced-hunting-cloudappevents-table.md) <br>Hier finden Sie Informationen zu Ereignissen in verschiedenen Cloud-Apps und -Diensten, die von Microsoft Cloud App Security abgedeckt werden. Diese Tabelle enthält auch Informationen, die zuvor in verfügbar `AppFileEvents` waren.
## <a name="february-2021"></a>Februar 2021
- (Vorschau) Das erweiterte [Microsoft 365 https://security.microsoft.com) Security Center (](https://security.microsoft.com) ist jetzt in der öffentlichen Vorschau verfügbar. Diese neue Erfahrung bringt Defender for Endpoint und Defender für Office 365 in den Mittelpunkt. [Weitere Informationen zu den Neuerungen](./overview-security-center.md).

## <a name="september-2020"></a>September 2020
- [IdentityDirectoryEvents-Tabelle](advanced-hunting-identitydirectoryevents-table.md) <br> Hier finden Sie Ereignisse mit einem lokalen Domänencontroller, auf dem Active Directory (AD) ausgeführt wird. Diese [erweiterte Schematabelle](advanced-hunting-overview.md) für die Suche deckt eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller ab.
- [AssignedIPAddresses()-Funktion](advanced-hunting-assignedipaddresses-function.md) <br> Verwenden Sie diese Funktion in Ihren erweiterten Suchabfragen, um schnell die neuesten EINEM Gerät zugewiesenen IP-Adressen oder die neuesten IP-Adressen aus einer bestimmten Zeit zu erhalten.

## <a name="july-2020"></a>Juli 2020
- [FileProfile()-Funktion](advanced-hunting-fileprofile-function.md) <br> Verwenden Sie diese Funktion in Ihren erweiterten Suchabfragen, um Ergebnisse mit umfassenden Dateiinformationen zu bereichern.
- [Identitäts- und App-Tabellen](advanced-hunting-schema-tables.md)<br> Erhalten Sie Einblick in Authentifizierungsereignisse, Active Directory-Abfragen und app-bezogene Aktivitäten mit den [Tabellen IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)und [AppFileEvents](advanced-hunting-appfileevents-table.md) im schema der erweiterten Suche.
- [Suche starten](advanced-hunting-go-hunt.md)<br> Schnell von der Untersuchung eines Vorfalls zur Überprüfung eines bestimmten Ereignisses, eines Benutzers, eines Geräts oder anderer Entitätstypen bei der erweiterten Suche.

## <a name="june-2020"></a>Juni 2020
- Twitter-Feed <br> Erhalten Sie aktuelle Sicherheitsforschung, Bedrohungsinformationen, Produktnachrichten und vieles mehr – direkt im Dashboard.
- [EmailPostDeliveryEvents-Schematabelle](advanced-hunting-emailpostdeliveryevents-table.md) <br> Integrieren Sie Informationen zu Aktionen nach der Zustellung für E-Mail-Nachrichten in Ihre erweiterten Suchabfragen.
- [Überprüfen von Datensätzen bei der erweiterten Suche](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Überprüfen Sie die Datensätze in den Abfrageergebnissen schnell mit dem neuen Detailbereich.

## <a name="may-2020"></a>Mai 2020
- [Benutzerdefinierte Erkennungen](custom-detections-overview.md) <br> Verwenden Sie erweiterte Suchabfragen, um benutzerdefinierte Erkennungsregeln zu erstellen, die sicherheitsereignisse und Systemzustände automatisch überwachen und darauf reagieren.

## <a name="february-2020"></a>Februar 2020
- [Vorfälle](incidents-overview.md) <br> Wissen Sie genau, wo ein Angriff begonnen hat, und weitere Details, um das Ausmaß des Angriffs zu erkennen.
- [Automatische Untersuchung und Reaktion](m365d-autoir.md) <br> Mit AIR können Ihre Sicherheitsteams die Kapazität Ihrer Organisation im Umgang mit Sicherheitswarnungen und Vorfällen erheblich verbessern.
- [Erweiterte Verbesserungen bei der Suche](advanced-hunting-overview.md) <br> Proaktive Suche nach Bedrohungen im modernen Arbeitsbereich mit Kusto Query Language und einem sicherheitsoptimierten Schema.

## <a name="march-2019"></a>März 2019
- Erweiterte Suche <br> Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.
- [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) <br> Messung der Sicherheitslage einer Organisation mit einer höheren Anzahl, die mehr Verbesserungsmaßnahmen angibt. Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. 
- [Berichte](overview-security-center.md) <br>  Bietet eine Vielzahl von Karten, die eine Vielzahl von Bereichen abdecken, die Sicherheitsanalysten und Administratoren im Rahmen ihres täglichen Betriebs nachverfolgen.
