---
title: Bericht über Geräteintehität und -kompatibilität in Microsoft Defender ATP
description: Nachverfolgen von Erkennungen des Gerätestatus, Antivirusstatus, Betriebssystemplattform und Windows 10-Versionen mithilfe des Geräteinteitäts- und Complianceberichts
keywords: Integritätsstatus, Antivirus, Betriebssystemplattform, Windows 10-Version, Version, Integrität, Compliance, Status
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
ms.technology: mde
ms.openlocfilehash: 5229ba068672035c2dce3afee1919f9c2d7f9e44
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186449"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Bericht über Geräteintehität und -kompatibilität in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Der Gerätestatusbericht enthält informationen auf hoher Ebene zu den Geräten in Ihrer Organisation. Der Bericht enthält Trendinformationen, die den Sensorstatus, den Antivirusstatus, Betriebssystemplattformen und Windows 10-Versionen anzeigen.

Das Dashboard ist in zwei Abschnitte unterteilt: ![ Abbildung des Geräteberichts](images/device-reports.png)
 
Abschnitt | Beschreibung
:---|:---
1 | Gerätetrends
2 | Gerätezusammenfassung (aktueller Tag)
 
 
## <a name="device-trends"></a>Gerätetrends 
Standardmäßig zeigt der Gerätetrend Geräteinformationen aus dem 30-Tage-Zeitraum an, der am letzten ganztägigen Tag endet. Um eine bessere Perspektive für Trends in Ihrer Organisation zu gewinnen, können Sie den Berichtszeitraum optimieren, indem Sie den angezeigten Zeitraum anpassen. Wählen Sie einen Zeitraum aus den Dropdownoptionen aus, um den Zeitraum anzupassen:
 
- 30 Tage
- 3 Monate
- 6 Monate
- Benutzerdefiniert

>[!NOTE]
>Diese Filter werden nur auf den Abschnitt Gerätetrends angewendet. Dies wirkt sich nicht auf den Abschnitt "Gerätezusammenfassung" aus.

## <a name="device-summary"></a>Gerätezusammenfassung 
Während die Gerätetrends trendende Geräteinformationen zeigen, werden in der Gerätezusammenfassung Geräteinformationen angezeigt, die auf den aktuellen Tag begrenzt sind. 

>[!NOTE]
>Die im Zusammenfassungsabschnitt angezeigten Daten sind auf 180 Tage vor dem aktuellen Datum begrenzt. Wenn das heutige Datum z. B. der 27. März 2019 ist, spiegeln die Daten im Zusammenfassungsabschnitt Zahlen vom 28. September 2018 bis zum 27. März 2019 wider.<br>
> Der auf den Abschnitt Trends angewendete Filter wird nicht auf den Zusammenfassungsabschnitt angewendet. 
 
Im Abschnitt Gerätetrends können Sie einen Drilldown zur Geräteliste mit dem entsprechenden Filter erstellen. Wenn Sie beispielsweise auf die Inaktive Leiste auf der Sensorstatuskarte klicken, erhalten Sie die Geräteliste mit Ergebnissen, die nur Geräte anzeigen, deren Sensorstatus inaktiv ist. 
 
 
 
## <a name="device-attributes"></a>Geräteattribute
Der Bericht besteht aus Karten, die die folgenden Geräteattribute anzeigen:
 
- **Integritätsstatus:** Zeigt Informationen zum Sensorstatus auf Geräten an, die eine aggregierte Ansicht von aktiven Geräten, beeinträchtigter Kommunikation, inaktiver Oder ohne Sensordaten anzeigen.
  
- **Antivirusstatus für aktive Windows 10-Geräte:** zeigt die Anzahl der Geräte und den Status von Microsoft Defender Antivirus an.
    
- **Betriebssystemplattformen**: zeigt die Verteilung von Betriebssystemplattformen an, die in Ihrer Organisation vorhanden sind. 
 
- **Windows 10-Versionen**: zeigt die Verteilung von Windows 10-Geräten und deren Versionen in Ihrer Organisation an.
 
 
 
## <a name="filter-data"></a>Filtern von Daten
 
Verwenden Sie die bereitgestellten Filter, um Geräte mit bestimmten Attributen ein- oder auszuschließen.

Sie können mehrere Filter auswählen, die aus den Geräteattributen angewendet werden. 
 
>[!NOTE]
>Diese Filter gelten **für alle** Karten im Bericht.
 
So zeigen Sie z. B. Daten zu Windows 10-Geräten mit active sensor health state an:
 
1. Unter **Filters > Sensor health state > Active**.
2. Wählen Sie dann **Betriebssystemplattformen > Windows 10 aus.**
3. Wählen Sie **Anwenden** aus.


## <a name="related-topic"></a>Verwandtes Thema
- [Bedrohungsschutzbericht](threat-protection-reports.md)
