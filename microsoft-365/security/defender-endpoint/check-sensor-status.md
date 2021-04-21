---
title: Überprüfen des Integritätsstatus des Sensors in Microsoft Defender for Endpoint
description: Überprüfen Sie den Sensorzustand auf Geräten, um zu ermitteln, welche Sensordaten falsch konfiguriert, inaktiv sind oder keine Sensordaten melden.
keywords: sensor, sensor health, misconfigured, inactive, no sensor data, sensor data, impaired communications, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904164"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Überprüfen des Sensorintestatus in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

Die **Kachel Geräte mit Sensorproblemen** befindet sich im Dashboard für Sicherheitsvorgänge. Diese Kachel enthält Informationen zur Fähigkeit des einzelnen Geräts, Sensordaten zur Verfügung zu stellen und mit dem Defender for Endpoint-Dienst zu kommunizieren. Es berichtet, wie viele Geräte Aufmerksamkeit erfordern und hilft Ihnen, problematische Geräte zu identifizieren und Maßnahmen zur Korrektur bekannter Probleme zu ergreifen.

Auf der Kachel befinden sich zwei Statusindikatoren, die Informationen zur Anzahl der Geräte bereitstellen, die dem Dienst nicht ordnungsgemäß melden:
- **Falsch konfiguriert** – Diese Geräte melden möglicherweise teilweise Sensordaten an den Defender for Endpoint-Dienst und können Konfigurationsfehler haben, die korrigiert werden müssen.
- **Inaktiv** : Geräte, die die Berichterstellung an den Defender for Endpoint-Dienst im letzten Monat für mehr als sieben Tage beendet haben.

Wenn Sie auf eine der Gruppen klicken, werden Sie zur **Geräteliste ,** gefiltert nach Ihrer Wahl, gefiltert.

![Screenshot der Kachel Geräte mit Sensorproblemen](images/atp-devices-with-sensor-issues-tile.png)

In **der Liste Geräte** können Sie die Integritätsstatusliste nach dem folgenden Status filtern:
- **Aktiv** – Geräte, die aktiv an den Defender for Endpoint-Dienst melden.
- **Falsch konfiguriert –** Diese Geräte melden möglicherweise teilweise Sensordaten an den Defender for Endpoint-Dienst, haben jedoch Konfigurationsfehler, die korrigiert werden müssen. Falsch konfigurierte Geräte können entweder eine oder eine Kombination der folgenden Probleme haben:
  - **Keine Sensordaten** – Geräte haben das Senden von Sensordaten beendet. Vom Gerät können eingeschränkte Warnungen ausgelöst werden.
  - **Beeinträchtigte Kommunikation** : Die Kommunikation mit dem Gerät ist beeinträchtigt. Das Senden von Dateien für eine tiefe Analyse, das Blockieren von Dateien, das Isolieren des Geräts vom Netzwerk und andere Aktionen, die eine Kommunikation mit dem Gerät erfordern, funktionieren möglicherweise nicht.
- **Inaktiv** – Geräte, die die Berichterstellung an den Defender for Endpoint-Dienst beendet haben.

Sie können die gesamte Liste auch im CSV-Format mit dem **Export-Feature** herunterladen. Weitere Informationen zu Filtern finden Sie unter [Anzeigen und Organisieren der Geräteliste](machines-view-overview.md).

>[!NOTE]
>Exportieren Sie die Liste im CSV-Format, um die ungefilterten Daten anzeigen zu können. Die CSV-Datei enthält alle Geräte in der Organisation, unabhängig davon, welche Filterung in der Ansicht selbst angewendet wird. Je nachdem, wie groß Ihre Organisation ist, kann es sehr viel Zeit dauern, bis sie heruntergeladen wird.

![Screenshot der Gerätelistenseite](images/atp-devices-list-page.png)

Sie können die Gerätedetails anzeigen, wenn Sie auf ein falsch konfiguriertes oder inaktives Gerät klicken.

## <a name="related-topic"></a>Verwandtes Thema
- [Beheben fehlerhafter Sensoren in Defender for Endpoint](fix-unhealthy-sensors.md)
