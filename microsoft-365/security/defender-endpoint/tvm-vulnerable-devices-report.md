---
title: Bericht über anfällige Geräte – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Ein Bericht mit anfälligen Gerätetrends und aktuellen Statistiken. Das Ziel ist, dass Sie den Atem und umfang Ihrer Gerätebelichtung verstehen.
keywords: mdatp-tvm vulnerable devices, mdatp, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f481ddca897594bd73de9b5f4762903f23fb24c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500459"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Bericht über anfällige Geräte – Bedrohungs- und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Der Bericht zeigt Diagramme und Balkendiagramme mit anfälligen Gerätetrends und aktuellen Statistiken. Das Ziel ist, dass Sie den Atem und umfang Ihrer Gerätebelichtung verstehen. 

Greifen Sie auf den Bericht im Microsoft Defender Security Center zu Berichte **> gefährdeten Geräten zu**

Es gibt zwei Spalten:

- Trends (im Laufe der Zeit). Kann die letzten 30 Tage, 3 Monate, 6 Monate oder einen benutzerdefinierten Datumsbereich anzeigen.
- Heute (aktuelle Informationen)

**Filter**: Sie können die Daten nach Schweregraden der Sicherheitsanfälligkeit, Exploitverfügbarkeit, Sicherheitsrisikoalter, Betriebssystemplattform, Windows 10-Version oder Gerätegruppe filtern.

**Drilldown**: Wenn Sie einen Einblick erhalten möchten, wählen Sie das entsprechende Balkendiagramm aus, um eine gefilterte Liste von Geräten auf der Seite Geräteinventar anzeigen zu können. Von dort können Sie die Liste exportieren.

## <a name="severity-level-graphs"></a>Schweregraddiagramme

Jedes Gerät wird nur einmal nach der schwersten Sicherheitslücke auf diesem Gerät gezählt.

![Ein Diagramm der aktuellen Schweregrade für Sicherheitslücken für Geräte und ein Diagramm, das die Ebenen im Laufe der Zeit zeigt.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Exploit-Verfügbarkeitsdiagramme

Jedes Gerät wird basierend auf der höchsten Stufe bekannter Exploits nur einmal gezählt.

![Ein Diagramm der aktuellen Verfügbarkeit von Geräte-Exploits und ein Diagramm, das die Verfügbarkeit im Laufe der Zeit zeigt.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Altersdiagramme für Sicherheitslücken

Jedes Gerät wird nur einmal unter dem ältesten Datum für die Veröffentlichung von Sicherheitslücken gezählt. Ältere Sicherheitsrisiken haben eine höhere Wahrscheinlichkeit, ausgebeutet zu werden.

![Ein Diagramm des aktuellen Alters von Sicherheitslücken für Geräte und ein Diagramm, das das Alter im Laufe der Zeit zeigt.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Anfällige Geräte nach Betriebssystemplattformdiagrammen

Die Anzahl der Geräte auf jedem Betriebssystem, die aufgrund von Softwarerisiken verfügbar gemacht werden.

![Ein Diagramm der aktuellen anfälligen Geräte nach Betriebssystemplattform und ein Diagramm, das anfällige Geräte nach Betriebssystemplattformen im Laufe der Zeit zeigt.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Anfällige Geräte nach Windows 10-Versionsdiagrammen

Die Anzahl der Geräte auf jeder Windows 10-Version, die aufgrund anfälliger Anwendungen oder Betriebssysteme verfügbar gemacht werden.

![Ein Diagramm der aktuellen anfälligen Geräte nach Windows 10-Version und ein Diagramm mit anfälligen Geräten nach Windows 10-Version im Laufe der Zeit.](images/tvm-report-version.png)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
