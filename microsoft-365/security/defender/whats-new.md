---
title: Neuerungen in Microsoft 365 Defender
description: Listet die neuen Features und Funktionen in Microsoft 365 Defender
keywords: Neuigkeiten in Microsoft 365 Defender, ga, allgemein verfügbar, Funktionen, verfügbar, neu
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
ms.openlocfilehash: 582116047900fc5f28d5580398cf5c065e6a3e23
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053023"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Neuerungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Sie möchten Microsoft 365 Defender ausprobieren? Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).
>

Die folgenden Features sind in der neuesten Version von Microsoft 365 Defender allgemein verfügbar.

RSS-Feed: Erhalten Sie Benachrichtigungen, wenn diese Seite aktualisiert wird, indem Sie die folgende URL kopieren und in Ihren Feed-Reader einfügen:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="april-2021"></a>April 2021
- Microsoft 365 Defender<br> Das verbesserte [Microsoft 365 Defender-Portal](https://security.microsoft.com) ist jetzt verfügbar. Diese neue Erfahrung vereint Defender für Endpunkt, Defender für Office 365, Defender for Identity und vieles mehr in einem einzigen Portal. Dies ist die neue Startseite zum Verwalten Ihrer Sicherheitskontrollen. [Erfahren Sie, was es Neues gibt](./overview-security-center.md).

- [bericht über Microsoft 365 Defender Bedrohungsanalyse](threat-analytics.md)<br>
 Die Bedrohungsanalyse hilft Ihnen, auf aktive Angriffe zu reagieren und sie zu minimieren. Sie können auch mehr über Angriffsversuche erfahren, die durch Microsoft 365 Defender Lösungen blockiert werden, und vorbeugende Maßnahmen ergreifen, um das Risiko einer weiteren Gefährdung zu mindern und die Resilienz zu erhöhen. Als Teil der einheitlichen Sicherheitsumgebung ist die Bedrohungsanalyse jetzt für Microsoft Defender für Endpunkt und Microsoft Defender für Office E5-Lizenzinhaber verfügbar.

## <a name="march-2021"></a>März 2021
- [CloudAppEvents-Tabelle](advanced-hunting-cloudappevents-table.md) <br>Hier finden Sie Informationen zu Ereignissen in verschiedenen Cloud-Apps und -Diensten, die von Microsoft Cloud App Security abgedeckt werden. Diese Tabelle enthält auch Informationen, die zuvor in verfügbar `AppFileEvents` waren.
## <a name="february-2021"></a>Februar 2021
- (Vorschau) Das erweiterte [Microsoft 365 Security Center https://security.microsoft.com) (](https://security.microsoft.com) ist jetzt in der öffentlichen Vorschau verfügbar. Diese neue Erfahrung bringt Defender für Endpunkt und Defender für Office 365 in die Mitte. [Weitere Informationen zu den Neuerungen](./overview-security-center.md).

## <a name="september-2020"></a>September 2020
- [IdentityDirectoryEvents-Tabelle](advanced-hunting-identitydirectoryevents-table.md) <br> Suchen von Ereignissen, die einen lokalen Domänencontroller betreffen, auf dem Active Directory (AD) ausgeführt wird. Diese Schematabelle für die [erweiterte Suche](advanced-hunting-overview.md) umfasst eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller.
- [AssignedIPAddresses()-Funktion](advanced-hunting-assignedipaddresses-function.md) <br> Verwenden Sie diese Funktion in Ihren erweiterten Suchabfragen, um schnell die neuesten IP-Adressen abzurufen, die einem Gerät zugewiesen sind, oder die neuesten IP-Adressen aus einem bestimmten Zeitpunkt.

## <a name="july-2020"></a>Juli 2020
- [FileProfile()-Funktion](advanced-hunting-fileprofile-function.md) <br> Verwenden Sie diese Funktion in Ihren erweiterten Suchabfragen, um die Ergebnisse mit umfassenden Dateiinformationen zu erweitern.
- [Identitäts- und App-Tabellen](advanced-hunting-schema-tables.md)<br> Erhalten Sie Einblicke in Authentifizierungsereignisse, Active Directory-Abfragen und App-bezogene Aktivitäten mit den Tabellen ["IdentityLogonEvents",](advanced-hunting-identitylogonevents-table.md) ["IdentityQueryEvents"](advanced-hunting-identityqueryevents-table.md)und ["AppFileEvents"](advanced-hunting-appfileevents-table.md) im Schema "Erweiterte Suche".
- [Suche starten](advanced-hunting-go-hunt.md)<br> Schnelles Pivot von der Untersuchung eines Vorfalls bis hin zur Überprüfung eines bestimmten Ereignisses, eines Benutzers, eines Geräts oder anderer Entitätstypen bei der erweiterten Suche.

## <a name="june-2020"></a>Juni 2020
- Twitter-Feed <br> Holen Sie sich die neuesten Sicherheitsanalysen, Informationen zu Bedrohungen, Produktnachrichten und vieles mehr – direkt im Dashboard.
- [EmailPostDeliveryEvents-Schematabelle](advanced-hunting-emailpostdeliveryevents-table.md) <br> Integrieren Sie Informationen zu Aktionen nach der Zustellung, die für E-Mail-Nachrichten ausgeführt werden, in Ihre erweiterten Suchabfragen.
- [Überprüfen von Datensätzen in der erweiterten Suche](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Überprüfen Sie Datensätze in Den Abfrageergebnissen schnell mit dem neuen Detailbereich.

## <a name="may-2020"></a>Mai 2020
- [Benutzerdefinierte Erkennungen](custom-detections-overview.md) <br> Verwenden Sie erweiterte Suchabfragen, um benutzerdefinierte Erkennungsregeln zu erstellen, die Sicherheitsereignisse und Systemzustände automatisch überwachen und darauf reagieren.

## <a name="february-2020"></a>Februar 2020
- [Vorfälle](incidents-overview.md) <br> Wissen Sie genau, wo ein Angriff begonnen hat, und andere Details, die Ihnen helfen, das Ausmaß des Angriffs zu erkennen.
- [Automatische Untersuchung und Reaktion](m365d-autoir.md) <br> Mit AIR können Ihre Sicherheitsteams die Kapazität Ihrer Organisation im Umgang mit Sicherheitswarnungen und Vorfällen erheblich verbessern.
- [Erweiterte Erweiterungen für die Suche](advanced-hunting-overview.md) <br> Proaktive Suche nach Bedrohungen im modernen Arbeitsbereich mit Kusto Query Language und einem sicherheitsoptimiertem Schema.

## <a name="march-2019"></a>März 2019
- Erweiterte Suche <br> Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.
- [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md) <br> Messung des Sicherheitsstatus einer Organisation mit einer höheren Zahl, die auf weitere durchgeführte Verbesserungsmaßnahmen hinweist. Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. 
- [Berichte](overview-security-center.md) <br>  Bietet eine Vielzahl von Karten, die eine Vielzahl von Bereichen abdecken, die Sicherheitsanalysten und Administratoren im Rahmen ihres täglichen Betriebs nachverfolgen.
