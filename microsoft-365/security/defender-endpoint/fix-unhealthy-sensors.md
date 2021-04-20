---
title: Beheben fehlerhafter Sensoren in Microsoft Defender for Endpoint
description: Beheben Sie Gerätesensoren, die als falsch konfiguriert oder inaktiv melden, sodass der Dienst Daten vom Gerät empfängt.
keywords: falsch konfiguriert, inaktiv, Sensor fix, Sensorintegte, keine Sensordaten, Sensordaten, beeinträchtigte Kommunikation, Kommunikation
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: 3a26951a796d72237f992e520e1b793654e467e3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893401"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Beheben fehlerhafter Sensoren in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

Geräte, die als falsch konfiguriert oder inaktiv kategorisiert sind, können aufgrund unterschiedlicher Ursachen gekennzeichnet werden. Dieser Abschnitt enthält einige Erläuterungen dazu, was dazu führte, dass ein Gerät als inaktiv oder falsch konfiguriert kategorisiert wurde.

## <a name="inactive-devices"></a>Inaktive Geräte

Ein inaktives Gerät wird aufgrund eines Problems nicht unbedingt gekennzeichnet. Die folgenden Aktionen auf einem Gerät können dazu führen, dass ein Gerät als inaktiv kategorisiert wird:

### <a name="device-is-not-in-use"></a>Gerät wird nicht verwendet

Wenn das Gerät aus irgendeinem Grund seit mehr als sieben Tagen nicht verwendet wird, bleibt es im Portal im Status "Inaktiv".

### <a name="device-was-reinstalled-or-renamed"></a>Gerät wurde neu installiert oder umbenannt
Ein neu installiertes oder umbenanntes Gerät generiert eine neue Geräteentität im Microsoft Defender Security Center. Die vorherige Geräteentität bleibt im Portal mit dem Status "Inaktiv" erhalten. Wenn Sie ein Gerät neu installiert und das Defender for Endpoint-Paket bereitgestellt haben, suchen Sie nach dem neuen Gerätenamen, um sicherzustellen, dass das Gerät normal meldet.

### <a name="device-was-offboarded"></a>Gerät wurde offboarded
Wenn das Gerät offboarded war, wird es weiterhin in der Geräteliste angezeigt. Nach sieben Tagen sollte der Zustand des Gerätestatus in inaktiv geändert werden.

### <a name="device-is-not-sending-signals"></a>Gerät sendet keine Signale
Wenn das Gerät aus irgendeinem Grund, einschließlich Bedingungen, die unter die Klassifizierung falsch konfigurierter Geräte fallen, keine Signale mehr als sieben Tage lang an einen der Microsoft Defender for Endpoint-Kanäle sendet, kann ein Gerät als inaktiv betrachtet werden. 

Erwarten Sie, dass ein Gerät den Status "Aktiv" hat? [Öffnen Sie ein Supportticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Falsch konfigurierte Geräte
Falsch konfigurierte Geräte können weiter wie folgt klassifiziert werden:
- Beeinträchtigte Kommunikation
- Keine Sensordaten

### <a name="impaired-communications"></a>Beeinträchtigte Kommunikation
Dieser Status gibt an, dass die Kommunikation zwischen dem Gerät und dem Dienst eingeschränkt ist.

Mit den folgenden vorgeschlagenen Aktionen können Probleme im Zusammenhang mit einem falsch konfigurierten Gerät mit eingeschränkter Kommunikation behoben werden:

- [Sicherstellen, dass das Gerät über eine Internetverbindung verfügt](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Für den Window Defender ATP-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Microsoft Defender for Endpoint-Dienst kommunizieren.

- [Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Überprüfen Sie, ob die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP den Proxyserver in Ihrer Umgebung ermitteln und kommunizieren kann und dass der Proxyserver Datenverkehr an die URLs des Microsoft Defender for Endpoint-Diensts zulässt.

Wenn Sie Korrekturmaßnahmen ergriffen haben und der Gerätestatus weiterhin falsch konfiguriert ist, öffnen [Sie ein Supportticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

### <a name="no-sensor-data"></a>Keine Sensordaten
Ein falsch konfiguriertes Gerät mit dem Status "Keine Sensordaten" verfügt über eine Kommunikation mit dem Dienst, kann aber nur Teilsensordaten melden.
Führen Sie diese Aktionen aus, um bekannte Probleme im Zusammenhang mit einem falsch konfigurierten Gerät mit dem Status "Keine Sensordaten" zu beheben:

- [Sicherstellen, dass das Gerät über eine Internetverbindung verfügt](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Für den Window Defender ATP-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Microsoft Defender for Endpoint-Dienst kommunizieren.

- [Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Überprüfen Sie, ob die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP den Proxyserver in Ihrer Umgebung ermitteln und kommunizieren kann und dass der Proxyserver Datenverkehr an die URLs des Microsoft Defender for Endpoint-Diensts zulässt.

- [Sicherstellen, dass der Diagnosedatendienst aktiviert ist](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Wenn die Geräte nicht ordnungsgemäß melden, müssen Sie möglicherweise überprüfen, ob der Windows 10-Diagnosedatendienst auf den automatischen Start festgelegt ist und auf dem Endpunkt ausgeführt wird.

- [Stellen Sie sicher, dass Microsoft Defender Antivirus nicht von der Richtlinie deaktiviert ist](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Wenn auf Ihren Geräten ein Antischasoftwareclient eines Drittanbieters ausgeführt wird, benötigt der Defender for Endpoint-Agent, dass der Microsoft Defender Antivirus Early Launch Antimalware (ELAM)-Treiber aktiviert ist.

Wenn Sie Korrekturmaßnahmen ergriffen haben und der Gerätestatus weiterhin falsch konfiguriert ist, öffnen [Sie ein Supportticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

## <a name="see-also"></a>Siehe auch
- [Überprüfen des Sensorintestatus in Microsoft Defender for Endpoint](check-sensor-status.md)
