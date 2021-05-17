---
title: Microsoft Defender for Endpoint Detections-API-Felder
description: Verstehen, wie die Erkennungs-API-Felder den Werten in Microsoft Defender Security Center
keywords: Erkennungen, Erkennungsfelder, Felder, API, Felder, Pullerkennungen, Rest-API, Anforderung, Antwort
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
ms.openlocfilehash: d6d2ad9abe88d0099b58dd2df486120082bb22c1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933637"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>Microsoft Defender for Endpoint Detections-API-Felder

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

Erfahren Sie, welche Datenfelder im Rahmen der Erkennungs-API verfügbar gemacht werden und wie sie Microsoft Defender Security Center.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen.
>- **Microsoft Defender ATP Die Erkennung** besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den **zugehörigen Warnungsdetails.**
>- Die Microsoft Defender for Endpoint Alert-API ist die neueste API für den Warnungsverbrauch und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung. Weitere Informationen finden Sie unter [Warnungsmethoden und -eigenschaften und](alerts.md) [Warnungen auflisten.](get-alerts.md)

## <a name="detections-api-fields-and-portal-mapping"></a>Erkennungen von API-Feldern und Portalzuordnung
In der folgenden Tabelle sind die verfügbaren Felder aufgeführt, die in der Erkennungs-API-Nutzlast verfügbar sind. Es enthält Beispiele für die aufgefüllten Werte und einen Verweis darauf, wie Daten im Portal widerspiegelt werden.

Die Spalte ArcSight-Feld enthält die Standardzuordnung zwischen den Feldern Defender for Endpoint und den integrierten Feldern in ArcSight. Sie können die Zuordnungsdatei aus dem Portal herunterladen, wenn Sie das SIEM-Integrationsfeature aktivieren, und sie an die Anforderungen Ihrer Organisation anpassen. Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Defender for Endpoint](enable-siem-integration.md).

Feldnummern entsprechen den Zahlen in den folgenden Bildern.

> [!div class="mx-tableFixed"]
> 
> | Portalbeschriftung   | NAME des SIEM-Felds           | ArcSight-Feld      | Beispielwert                                                                      | Beschreibung                                                                                                                                                                    |
> |------------------|---------------------------|---------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | 1                | AlertTitle                | name                | Microsoft Defender AV erkannte Schadsoftware mit hohem Schweregrad "Mikatz" | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 2                | Severity                  | deviceSeverity      | Hoch                                                                             | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 3                | Kategorie                  | deviceEventCategory | Schadsoftware                                                               | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 4                 | Erkennungsquelle                    | sourceServiceName   | Antivirus                                                                 | Microsoft Defender Antivirus oder Defender for Endpoint. Wert, der für jede Erkennung verfügbar ist.                                                                                         |
> | 5                 | MachineName               | sourceHostName      | desktop-4a5ngd6                                                                           | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 6                 | FileName                  | fileName            | Robocopy.exe                                                                       | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                      |
> | 7                 | FilePath                  | filePath            | C:\Windows\System32\Robocopy.exe                                                   | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                     |
> | 8                 | UserDomain                | sourceNtDomain      | CONTOSO                                                                            | Die Domäne des Benutzerkontexts, in dem die Aktivität ausgeführt wird und für verhaltensbasierte Erkennungen von Defender for Endpoint verfügbar ist.                                                           |
> | 9                 | UserName                  | sourceUserName      | liz.bean                                                                           | Der Benutzerkontext, in dem die Aktivität ausgeführt wird, verfügbar für verhaltensbasierte Erkennungen von Defender for Endpoint.                                                                           |
> | 10               | Sha1                      | fileHash            | 3da065e07b990034e9db7842167f70b63aa5329                                           | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                      |
> | 11               | Sha256                    | deviceCustomString6 | ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5                   | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 12                | Md5                       | deviceCustomString5 | db979c04a99b96d370988325bb5a8b21                                                   | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 13               | ThreatName                | deviceCustomString1  | HackTool:Win32/Mikatz!dha                                                         | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 14                | IpAddress                 | sourceAddress       | 218.90.204.141                                                                     | Verfügbar für Erkennungen, die Netzwerkereignissen zugeordnet sind. Beispiel: "Kommunikation mit einem zielschädlichen Netzwerk".                                                        |
> | 15                | Url                       | requestUrl          | down.esales360.cn                                                                  | Verfügbar für Erkennungen, die Netzwerkereignissen zugeordnet sind. Beispiel: "Kommunikation mit einem zielschädlichen Netzwerk".                                                         |
> | 16                | RemediationIsSuccess      | deviceCustomNumber2 | TRUE                                                                               | Verfügbar für Microsoft Defender AV-Erkennungen. Der ArcSight-Wert ist 1, wenn TRUE und 0, wenn FALSE.                                                                                    |
> | 17                | WasExecutingWhileDetected | deviceCustomNumber1 | FALSE                                                                              | Verfügbar für Microsoft Defender AV-Erkennungen. Der ArcSight-Wert ist 1, wenn TRUE und 0, wenn FALSE.                                                                                    |
> | 18                | AlertId                   | externalId          | 636210704265059241_673569822                                                       | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 19               | LinkToWDATP               | flexString1         | `https://securitycenter.windows.com/alert/636210704265059241_673569822`            | Wert, der für jede Erkennung verfügbar ist.                                                                                                                                               |
> | 20               | AlertTime                 | deviceReceiptTime   | 2017-05-07T01:56:59.3191352Z                                                       | Der Zeitpunkt, zu dem das Ereignis aufgetreten ist. Wert, der für jede Erkennung verfügbar ist.                                                                                       |
> |  21               | MachineDomain             | sourceDnsDomain     | contoso.com                                                                        | Domänenname für AAD-beigetretene Geräte nicht relevant. Wert, der für jede Erkennung verfügbar ist.                                                                                           |
> | 22               | Akteur                     | deviceCustomString4 | BORON                                                                                   | Verfügbar für Warnungen im Zusammenhang mit einer bekannten Akteurgruppe.                                                                                                                         |
> | 21+5             | ComputerDnsName           | Keine Zuordnung          | liz-bean.contoso.com                                                               | Der vollqualifizierte Domänenname des Geräts. Wert, der für jede Erkennung verfügbar ist.                                                                                                    |
> |                  | LogOnUsers                | sourceUserId        | contoso\liz-bean;   contoso\jay-hardee                                             | Die Domäne und der Benutzer der interaktiven Anmeldebenutzer zum Zeitpunkt des Ereignisses. Hinweis: Für Geräte auf Windows 10 Version 1607 sind die Domäneninformationen nicht verfügbar. |
> |                  | InternalIPv4List          | Keine Zuordnung          | 192.168.1.7, 10.1.14.1                                                             | Liste der internen IPV4-IPs für aktive Netzwerkschnittstellen.                                                                                                                                                                               |
> |                  | InternalIPv6List          | Keine Zuordnung          | fd30:0000:0000:0001:ff4e:003e:0009:000e, FE80:CD00:0000:0CDE:1257:0000:211E:729C | Liste der internen IPV6-IPs für aktive Netzwerkschnittstellen.                                                                                                                                                                               |
| | LinkToMTP | Keine Zuordnung | `https://security.microsoft.com/alert/da637370718981685665_16349121` | Wert, der für jede Erkennung verfügbar ist.
| | IncidentLinkToMTP | Keine Zuordnung | `"https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Wert, der für jede Erkennung verfügbar ist.
| | IncidentLinkToWDATP | Keine Zuordnung | `https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Wert, der für jede Erkennung verfügbar ist.
> | Internes Feld | LastProcessedTimeUtc      | Keine Zuordnung          | 2017-05-07T01:56:58.9936648Z                                                       | Zeitpunkt, zu dem das Ereignis am Back-End-End eintraf. Dieses Feld kann beim Festlegen des Anforderungsparameters für den Zeitraum verwendet werden, in dem Erkennungen abgerufen werden.                         |
> |                  | Nicht Teil des Schemas    | deviceVendor        |                                                                                    | Statischer Wert in der ArcSight-Zuordnung – "Microsoft".                                                                                                                          |
> |                  | Nicht Teil des Schemas    | deviceProduct       |                                                                                    | Statischer Wert in der ArcSight-Zuordnung – "Microsoft Defender ATP".                                                                                                               |
> |                  | Nicht Teil des Schemas    | deviceVersion       |                                                                                    | Statischer Wert in der ArcSight-Zuordnung - "2.0", der zum Identifizieren der Zuordnungsversionen verwendet wird.                                                                                         


![Abbildung der Warnung mit Zahlen](images/atp-alert-page.png)

![Abbildung des Warnungsdetailsebereichs mit Zahlen](images/atp-siem-mapping13.png)

![Abbildung der Artefaktzeitachse mit Zahlen1](images/atp-siem-mapping3.png)

![Abbildung der Artefaktzeitachse mit Zahlen2](images/atp-siem-mapping4.png)

![Ansicht des Bildcomputers](images/atp-mapping6.png)

![Url des Bildbrowsers](images/atp-mapping5.png)

![Warnung des Bildschauspielers](images/atp-mapping7.png)


## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint](enable-siem-integration.md)
- [Konfigurieren von ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen](configure-arcsight.md)
- [Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md)
- [Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md)
