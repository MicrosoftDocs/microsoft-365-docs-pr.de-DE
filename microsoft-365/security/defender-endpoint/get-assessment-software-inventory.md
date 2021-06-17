---
title: Exportieren der Softwareinventarisierungsbewertung pro Gerät
description: Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.
keywords: API, APIs, Exportbewertung, Bewertung pro Gerät, Bericht zur Bewertung von Sicherheitsrisiken, Bewertung der Sicherheitslücken des Geräts, Bericht über Sicherheitsrisiken, Bewertung der sicheren Konfiguration, Bericht über sichere Konfiguration, Bewertung von Software-Sicherheitsrisiken, Bericht über Software-Sicherheitsrisiken, Sicherheitsrisikobericht nach Computer,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 4f2e16acf474d6da8867a6bd392f9e90e0cf166e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984844"
---
# <a name="export-software-inventory-assessment-per-device"></a>Exportieren der Softwareinventarisierungsbewertung pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen. Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:

- [Exportieren von **OData** zur Softwareinventarisierungsbewertung](#1-export-software-inventory-assessment-odata)  Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100-K-Geräten._ Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.

- Exportieren der [Softwareinventarisierungsbewertung **über Dateien**](#2-export-software-inventory-assessment-via-files)  Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100-K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:

  - Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.

  - Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

Daten, die gesammelt werden (entweder mit _OData_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.

> [!Note]
>
> Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).

## <a name="1-export-software-inventory-assessment-odata"></a>1. Exportieren der Softwareinventarbewertung (OData)

### <a name="11-api-method-description"></a>1.1 API-Methodenbeschreibung

Diese API-Antwort enthält alle Daten der installierten Software pro Gerät. Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.

#### <a name="limitations"></a>Einschränkungen

- Die maximale Seitengröße beträgt 200.000.

- Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.

### <a name="12-permissions"></a>1.2 Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Application | Software.Read.All | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 Parameter

- pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort.

- $top – Anzahl der zurückzugebenden Ergebnisse (gibt nicht @odata.nextLink zurück und ruft daher nicht alle Daten ab)

### <a name="15-properties"></a>1.5-Eigenschaften

>[!NOTE]
>
>-Jeder Datensatz enthält ca. 0,5 KB Daten. Berücksichtigen Sie dies, wenn Sie den richtigen pageSize-Parameter für Sie auswählen.

>-Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet. Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.
>
>-Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben. Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.

Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
Deviceid | string | Eindeutiger Bezeichner für das Gerät im Dienst. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts. | johnlaptop.europe.contoso.com
DiskPaths | Array[string]  | Datenträgernachweis, dass das Produkt auf dem Gerät installiert ist. | [ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight Application \\ \\silverlight.exe" ]
EndOfSupportDate | string | Das Datum, an dem die Unterstützung für diese Software endet oder endet. | 2020-12-30
EndOfSupportStatus | string | Ende des Supportstatus. Kann diese möglichen Werte enthalten: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software. | Bevorstehende EOS
Id | string | Eindeutiger Bezeichner für den Datensatz. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Anzahl der Schwachstellen dieser Software auf diesem Gerät | 3
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen. | Windows 10
RbacGroupName | string | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None". | Server
RegistryPaths | Array[string] | Registrierungsnachweis, dass das Produkt auf dem Gerät installiert ist. | [ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]
SoftwareFirstSeenTimestamp | string | Diese Software wurde zum ersten Mal auf dem Gerät angezeigt. | 2019-04-07 02:06:47
SoftwareName | string | Name des Softwareprodukts. | Silverlight
SoftwareVendor | string | Name des Softwareanbieters. | Microsoft
SoftwareVersion | string | Versionsnummer des Softwareprodukts. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Beispiele

#### <a name="161-request-example"></a>1.6.1 Anforderungsbeispiel

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 Antwortbeispiel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Exportieren der Softwareinventarbewertung (über Dateien)

### <a name="21-api-method-description"></a>2.1 API-Methodenbeschreibung

Diese API-Antwort enthält alle Daten der installierten Software pro Gerät. Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion zurück.

#### <a name="211-limitations"></a>2.1.1 Einschränkungen

Die Rateneinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.

### <a name="22-permissions"></a>2.2 Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Application | Software.Read.All | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Software.Read | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parameter

- sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (maximal 24 Stunden)

### <a name="25-properties"></a>2.5-Eigenschaften

>[!Note]
>
>- Die Dateien werden & im mehrzeiligen JSON-Format gzipkomprimiert.
>
>- Die Download-URLs sind nur 3 Stunden gültig. Andernfalls können Sie den Parameter verwenden.
>
>_ Für eine maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie aus derselben Azure-Region herunterladen, in der sich Ihre Daten befinden.
>
Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | string | Die Zeit, zu der der Export generiert wurde. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Beispiele

#### <a name="261-request-example"></a>2.6.1 Anforderungsbeispiel

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 Antwortbeispiel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Siehe auch

- [Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät](get-assessment-methods-properties.md)

- [Exportieren der Bewertung der sicheren Konfiguration pro Gerät](get-assessment-secure-config.md)

- [Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät](get-assessment-software-vulnerabilities.md)

Andere verwandte

- [Risikobasierte bedrohungsbasierte & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
