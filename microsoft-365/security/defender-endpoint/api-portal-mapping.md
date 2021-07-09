---
title: Api-Felder für Microsoft Defender für Endpunkterkennungen
description: Verstehen, wie die Felder der Erkennungs-API den Werten in Microsoft 365 Defender
keywords: Erkennungen, Erkennungsfelder, Felder, API, Felder, Pull-Erkennungen, Rest-API, Anforderung, Antwort
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
ms.openlocfilehash: f9a0d4ddeee5c1dc49c53e324854cabccc5f79e5
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339550"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>Api-Felder für Microsoft Defender für Endpunkterkennungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

Verstehen, welche Datenfelder als Teil der Erkennungs-API verfügbar gemacht werden und wie sie Microsoft 365 Defender zugeordnet werden.

>[!Note]
>- [Defender für Endpunkt-Warnung](alerts.md) besteht aus einer oder mehreren Erkennungen.
>- **Die Microsoft Defender ATP-Erkennung** besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen **Warnungsdetails.**
>- Die Microsoft Defender für Endpunkt-Warnungs-API ist die neueste API für die Benachrichtigungsnutzung und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung. Weitere Informationen finden Sie unter ["Warnungsmethoden und -eigenschaften"](alerts.md) und ["Warnungen auflisten".](get-alerts.md)

## <a name="detections-api-fields-and-portal-mapping"></a>Erkennungs-API-Felder und Portalzuordnung
In der folgenden Tabelle sind die verfügbaren Felder aufgeführt, die in der Api-Nutzlast für Erkennungen verfügbar gemacht werden. Es zeigt Beispiele für die aufgefüllten Werte und einen Verweis darauf, wie Daten im Portal widergespiegelt werden.

Die ArcSight-Feldspalte enthält die Standardzuordnung zwischen den Feldern Defender für Endpunkt und den integrierten Feldern in ArcSight. Sie können die Zuordnungsdatei aus dem Portal herunterladen, wenn Sie das SIEM-Integrationsfeature aktivieren, und sie an die Anforderungen Ihrer Organisation anpassen. Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Defender für Endpunkt.](enable-siem-integration.md)

Feldnummern stimmen mit den Zahlen in den folgenden Bildern überein.

> [!div class="mx-tableFixed"]
> 
> | Portalbezeichnung   | SIEM-Feldname           | ArcSight-Feld      | Beispielwert                                                                      | Beschreibung                                                                                                                                                                    |
> |------------------|---------------------------|---------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | 1                | AlertTitle                | name                | Microsoft Defender AV hat Schadsoftware mit hohem Schweregrad "Mikatz" erkannt | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 2                | Severity                  | deviceSeverity      | Hoch                                                                             | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 3                | Kategorie                  | deviceEventCategory | Schadsoftware                                                               | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 4                 | Erkennungsquelle                    | sourceServiceName   | Antivirus                                                                 | Microsoft Defender Antivirus oder Defender für Endpunkt. Für jede Erkennung verfügbarer Wert.                                                                                         |
> | 5                 | Machinename               | sourceHostName      | desktop-4a5ngd6                                                                           | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 6                 | FileName                  | fileName            | Robocopy.exe                                                                       | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                      |
> | 7                 | FilePath                  | Filepath            | C:\Windows\System32\Robocopy.exe                                                   | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                     |
> | 8                 | UserDomain                | sourceNtDomain      | Contoso                                                                            | Die Domäne des Benutzerkontexts, in dem die Aktivität ausgeführt wird, verfügbar für verhaltensbasierte Erkennungen für Defender für Endpunkte.                                                           |
> | 9                 | UserName                  | sourceUserName      | liz.bean                                                                           | Der Benutzerkontext, in dem die Aktivität ausgeführt wird, verfügbar für verhaltensbasierte Defender für Endpunkt-Erkennungen.                                                                           |
> | 10                | Sha1                      | fileHash            | 3da065e07b990034e9db7842167f70b63aa5329                                           | Verfügbar für Erkennungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                      |
> | 11                | Sha256                    | deviceCustomString6 | ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5                   | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 12                | Md5                       | deviceCustomString5 | db979c04a99b96d370988325bb5a8b21                                                   | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 13               | ThreatName                | deviceCustomString1  | HackTool:Win32/Mikatz!dha                                                         | Verfügbar für Microsoft Defender AV-Erkennungen.                                                                                                                                    |
> | 14                | Ipaddress                 | sourceAddress       | 218.90.204.141                                                                     | Verfügbar für Erkennungen, die Netzwerkereignissen zugeordnet sind. Beispiel: "Kommunikation mit einem schädlichen Netzwerkziel".                                                        |
> | 15               | Url                       | requestUrl          | down.esales360.cn                                                                  | Verfügbar für Erkennungen, die Netzwerkereignissen zugeordnet sind. Beispiel: "Kommunikation mit einem schädlichen Netzwerkziel".                                                         |
> | 16                | RemediationIsSuccess      | deviceCustomNumber2 | TRUE                                                                               | Verfügbar für Microsoft Defender AV-Erkennungen. ArcSight-Wert ist 1 bei TRUE und 0 bei FALSE.                                                                                    |
> | 17                | WasExecutingWhileDetected | deviceCustomNumber1 | FALSE                                                                              | Verfügbar für Microsoft Defender AV-Erkennungen. ArcSight-Wert ist 1 bei TRUE und 0 bei FALSE.                                                                                    |
> | 18                | AlertId                   | externalId          | 636210704265059241_673569822                                                       | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 19               | LinkToWDATP               | flexString1         | `https://securitycenter.windows.com/alert/636210704265059241_673569822`            | Für jede Erkennung verfügbarer Wert.                                                                                                                                               |
> | 20               | AlertTime                 | deviceReceiptTime   | 2017-05-07T01:56:59.3191352Z                                                       | Die Uhrzeit, zu der das Ereignis aufgetreten ist. Für jede Erkennung verfügbarer Wert.                                                                                       |
> |  21               | MachineDomain             | sourceDnsDomain     | contoso.com                                                                        | Domänenname für AAD-verbundene Geräte nicht relevant. Für jede Erkennung verfügbarer Wert.                                                                                           |
> | 22               | Akteur                     | deviceCustomString4 | Bor                                                                                   | Verfügbar für Warnungen im Zusammenhang mit einer bekannten Akteurgruppe.                                                                                                                         |
> | 21+5             | ComputerDnsName           | Keine Zuordnung          | liz-bean.contoso.com                                                               | Der vollqualifizierte Domänenname des Geräts. Für jede Erkennung verfügbarer Wert.                                                                                                    |
> |                  | LogOnUsers                | sourceUserId        | contoso\liz-bean;   contoso\jay-hardee                                             | Die Domäne und der Benutzer der interaktiven Anmeldebenutzer zum Zeitpunkt des Ereignisses. Hinweis: Für Geräte mit Windows 10 Version 1607 sind die Domäneninformationen nicht verfügbar. |
> |                  | InternalIPv4List          | Keine Zuordnung          | 192.168.1.7, 10.1.14.1                                                             | Liste der internen IPV4-IPs für aktive Netzwerkschnittstellen.                                                                                                                                                                               |
> |                  | InternalIPv6List          | Keine Zuordnung          | fd30:0000:0000:0001:ff4e:003e:0009:000e, FE80:CD00:0000:0CDE:1257:0000:211E:729C | Liste der internen IPV6-IPs für aktive Netzwerkschnittstellen.                                                                                                                                                                               |
| | LinkToMTP | Keine Zuordnung | `https://security.microsoft.com/alert/da637370718981685665_16349121` | Für jede Erkennung verfügbarer Wert.
| | IncidentLinkToMTP | Keine Zuordnung | `"https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Für jede Erkennung verfügbarer Wert.
| | IncidentLinkToWDATP | Keine Zuordnung | `https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Für jede Erkennung verfügbarer Wert.
> | Internes Feld | LastProcessedTimeUtc      | Keine Zuordnung          | 2017-05-07T01:56:58.9936648Z                                                       | Zeitpunkt, zu dem das Ereignis im Back-End eingetroffen ist. Dieses Feld kann verwendet werden, wenn der Anforderungsparameter für den Zeitraum festgelegt wird, in dem Erkennungen abgerufen werden.                         |
> |                  | Nicht Teil des Schemas    | deviceVendor        |                                                                                    | Statischer Wert in der ArcSight-Zuordnung – "Microsoft".                                                                                                                          |
> |                  | Nicht Teil des Schemas    | deviceProduct       |                                                                                    | Statischer Wert in der ArcSight-Zuordnung – "Microsoft Defender ATP".                                                                                                               |
> |                  | Nicht Teil des Schemas    | deviceVersion       |                                                                                    | Statischer Wert in der ArcSight-Zuordnung – "2.0", der verwendet wird, um die Zuordnungsversionen zu identifizieren.                                                                                         


![Abbildung der Warnung mit Zahlen](images/atp-alert-page.png)

![Abbildung des Bereichs "Warnungsdetails" mit Nummern](images/atp-siem-mapping13.png)

![Abbildung der Artefaktzeitachse mit Zahlen1](images/atp-siem-mapping3.png)

![Abbildung der Artefaktzeitachse mit Zahlen2](images/atp-siem-mapping4.png)

![Bildcomputeransicht](images/atp-mapping6.png)

![URL des Bildbrowsers](images/atp-mapping5.png)

![Warnung des Bild-Akteurs](images/atp-mapping7.png)


## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt](enable-siem-integration.md)
- [Konfigurieren von ArcSight zum Abrufen von Microsoft Defender für Endpunkterkennungen](configure-arcsight.md)
- [Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der REST-API](pull-alerts-using-rest-api.md)
- [Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md)
