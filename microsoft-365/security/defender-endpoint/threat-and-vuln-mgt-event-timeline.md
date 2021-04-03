---
title: Ereigniszeitachse im Bedrohungs- und Sicherheitsrisikomanagement
description: Die Ereigniszeitachse ist ein Newsfeed für Risiken, mit dem Sie interpretieren können, wie Risiken in die Organisation eingeführt werden und welche Gegenmaßnahmen zur Reduzierung des Risikos eingetreten sind.
keywords: Ereigniszeitachse, mdatp-Ereigniszeitachse, mdatp tvm-Ereigniszeitachse, Bedrohungs- und Sicherheitsrisikoverwaltung, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90a124f9b0bf9ef775141e359224fde566c61c8d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501199"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a>Ereigniszeitachse – Bedrohungs- und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Die Ereigniszeitachse ist ein Newsfeed für Risiken, mit dem Sie interpretieren können, wie Risiken durch neue Sicherheitsrisiken oder Exploits in die Organisation eingeführt werden. Sie können Ereignisse anzeigen, die sich auf das Risiko Ihrer Organisation auswirken können. Beispielsweise finden Sie neue Sicherheitsrisiken, die eingeführt wurden, Sicherheitsrisiken, die ausgenutzt werden konnten, Exploits, die einem Exploit Kit hinzugefügt wurden, und vieles mehr.

Die Ereigniszeitachse enthält [](tvm-exposure-score.md) außerdem die Geschichte ihrer Belichtungsergebnis und [der Microsoft Secure Score für](tvm-microsoft-secure-score-devices.md) Geräte, damit Sie die Ursache für große Änderungen ermitteln können. Ereignisse können sich auf Ihre Geräte oder Ihre Bewertung für Geräte auswirken. Reduzieren Sie Ihre Risikoposition, indem Sie auf der Grundlage der priorisierten Sicherheitsempfehlungen das problembearbeiten, [was behoben werden muss.](tvm-security-recommendation.md)

>[!TIP]
>Informationen zu E-Mails zu neuen Sicherheitsrisikoereignissen finden Sie unter [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-event-timeline-page"></a>Navigieren zur Seite Ereigniszeitachse

Es gibt auch drei Einstiegspunkte aus dem Dashboard zur Verwaltung von Bedrohungen und [Sicherheitslücken:](tvm-dashboard-insights.md)

- **Belichtungsergebniskarte** der Organisation: Zeigen Sie im Diagramm "Belichtungsergebnis im Laufe der Zeit" auf die Ereignispunkte, und wählen Sie "Alle Ereignisse von diesem Tag anzeigen" aus. Die Ereignisse stellen Softwarerisiken dar.
- **Microsoft Secure Score for Devices**: Zeigen Sie im Diagramm "Ihre Bewertung für Geräte im Laufe der Zeit" auf die Ereignispunkte, und wählen Sie "Alle Ereignisse von diesem Tag anzeigen" aus. Die Ereignisse stellen neue Konfigurationsbewertungen dar.
- **Karte "Top-Ereignisse":** Wählen Sie "Weitere Anzeigen" unten in der Tabelle "Top Events" aus. Die Karte zeigt die drei auswirkungenreichsten Ereignisse der letzten 7 Tage an. Zu den auswirkungenreichen Ereignissen kann gehören, wenn sich das Ereignis auf eine große Anzahl von Geräten auswirkt oder wenn es sich um eine kritische Sicherheitslücke handelt.

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a>Belichtungsergebnis und Microsoft Secure Score for Devices Graphs

Zeigen Sie im Dashboard für die Bedrohungs- und Sicherheitsrisikoverwaltung auf das Diagramm Belichtungsergebnis, um die top-Software-Sicherheitsrisikoereignisse von diesem Tag anzuzeigen, die sich auf Ihre Geräte auswirken. Zeigen Sie auf das Microsoft Secure Score for Devices-Diagramm, um neue Sicherheitskonfigurationsbewertungen anzuzeigen, die sich auf Ihre Bewertung auswirken.

Wenn es keine Ereignisse gibt, die sich auf Ihre Geräte oder Ihre Bewertung für Geräte auswirken, wird keines angezeigt.

![Belichtungsergebnis mit ](images/tvm-event-timeline-exposure-score350.png) 
 ![ Dem Mauszeiger microsoft Secure Score for Devices](images/tvm-event-timeline-device-hover360.png)

### <a name="drill-down-to-events-from-that-day"></a>Drilldown zu Ereignissen von diesem Tag

Wenn Sie alle Ereignisse von diesem Tag anzeigen **auswählen,** gelangen Sie zur Seite Ereigniszeitachse mit einem benutzerdefinierten Datumsbereich für diesen Tag.

![Ereigniszeitachse ausgewählter benutzerdefinierter Datumsbereich](images/tvm-event-timeline-drilldown.png)

Wählen **Sie Benutzerdefinierter** Bereich aus, um den Datumsbereich in einen anderen benutzerdefinierten oder einen vordefinierten Zeitraum zu ändern.

![Optionen für den Datumsbereich der Ereigniszeitachse](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a>Übersicht über die Ereigniszeitachse

Auf der Seite Ereigniszeitachse können Sie alle erforderlichen Informationen zu einem Ereignis anzeigen. 

Features:

- Anpassen von Spalten
- Filtern nach Ereignistyp oder Prozent der betroffener Geräte
- Anzeigen von 30, 50 oder 100 Elementen pro Seite

Die beiden großen Zahlen oben auf der Seite zeigen die Anzahl neuer Sicherheitsrisiken und ausnutzende Sicherheitsrisiken an, nicht Ereignisse. Einige Ereignisse können mehrere Sicherheitsrisiken aufweisen, und einige Sicherheitsrisiken können mehrere Ereignisse aufweisen.

![Ereigniszeitachsenseite](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a>Spalten

- **Datum**: Monat, Tag, Jahr
- **Ereignis**: Auswirkungsereignis, einschließlich Komponente, Typ und Anzahl betroffener Geräte
- **Verwandte Komponente**: Software
- **Ursprünglich betroffener Geräte:** Die Anzahl und der Prozentsatz betroffener Geräte, als dieses Ereignis ursprünglich aufgetreten ist. Sie können auch nach dem Prozent der ursprünglich betroffenen Geräte filtern, und die Gesamtzahl der Geräte.
- **Aktuell betroffener Geräte:** die aktuelle Anzahl und der Prozentsatz der Geräte, die dieses Ereignis derzeit beeinflusst. Sie finden dieses Feld, indem Sie **Spalten anpassen auswählen.**
- **Typen**: spiegeln Zeitstempelereignisse wider, die sich auf die Bewertung auswirken. Sie können gefiltert werden.
    - Einem Exploitkit hinzugefügter Exploit
    - Exploit wurde überprüft
    - Neuer öffentlicher Exploit
    - Neue Sicherheitslücke
    - Neue Konfigurationsbewertung
- **Bewertungstrend**: Belichtungsergebnistrend

### <a name="icons"></a>Symbole

Die folgenden Symbole werden neben Ereignissen angezeigt:

- ![Fehlersymbol](images/tvm-black-bug-icon.png) Neuer öffentlicher Exploit
- ![Symbol für Berichtswarnung](images/report-warning-icon.png) Neue Sicherheitslücke wurde veröffentlicht
- ![Exploit Kit](images/bug-lightning-icon2.png) Exploit im Exploit Kit
- ![Fehlersymbol mit Warnungssymbol](images/bug-caution-icon2.png) Exploit überprüft

### <a name="drill-down-to-a-specific-event"></a>Drilldown zu einem bestimmten Ereignis

Nachdem Sie ein Ereignis ausgewählt haben, wird ein Flyout mit einer Liste der Details und aktuellen CVEs angezeigt, die sich auf Ihre Geräte auswirken. Sie können weitere CVEs anzeigen oder die zugehörige Empfehlung anzeigen.

Der Pfeil unter "Bewertungstrend" hilft Ihnen zu bestimmen, ob dieses Ereignis ihre belichtungsbedingte Bewertung möglicherweise ausgelöst oder gesenkt hat. Eine höhere Belichtungszahl bedeutet, dass Geräte anfälliger für die Nutzung sind.

![Flyout der Ereigniszeitachse](images/tvm-event-timeline-flyout500.png)

Wählen Sie von dort **auf der** Seite Sicherheitsempfehlungen die Option Zu zugehöriger Sicherheitsempfehlung wechseln die Empfehlung aus, die die neue Sicherheitslücke der Software [behebt.](tvm-security-recommendation.md) Nachdem Sie die Beschreibung und die Sicherheitsrisikodetails in der Sicherheitsempfehlung gelesen haben, können Sie eine Korrekturanforderung übermitteln und die Anforderung auf der Seite "Problembehebung" [nachverfolgen.](tvm-remediation.md)  

## <a name="view-event-timelines-in-software-pages"></a>Anzeigen von Ereigniszeitachsen auf Softwareseiten

Wählen Sie zum Öffnen einer Softwareseite ein Ereignis aus, > im Flyout den Namen der mit Hyperlinks verknüpften Software (wie Visual Studio 2017) im Abschnitt "Verwandte Komponente" auswählen. [Weitere Informationen zu Softwareseiten](tvm-software-inventory.md#software-pages)

Eine vollständige Seite mit allen Details einer bestimmten Software wird angezeigt. Bewegen Sie die Maus über das Diagramm, um die Zeitachse der Ereignisse für diese bestimmte Software anzuzeigen.

![Softwareseite mit einem Ereigniszeitachsendiagramm](images/tvm-event-timeline-software2.png)

Navigieren Sie zur Registerkarte Ereigniszeitachse, um alle Ereignisse im Zusammenhang mit dieser Software anzuzeigen. Sie können auch Sicherheitsempfehlungen, ermittelte Sicherheitsrisiken, installierte Geräte und Versionsverteilung sehen.

![Softwareseite mit registerkarte Ereigniszeitachse](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Gefährdungsscore](tvm-exposure-score.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
- [Sicherheitsrisiken korrigieren](tvm-remediation.md)
- [Softwarebestand](tvm-software-inventory.md)

