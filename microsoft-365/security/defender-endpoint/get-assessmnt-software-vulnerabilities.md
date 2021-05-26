---
title: Exportieren der Bewertung von Softwarerisiken pro Gerät
description: Die API-Antwort ist pro Gerät und enthält anfällige Software, die auf Ihren verfügbar gemachten Geräten installiert ist, sowie alle bekannten Sicherheitsrisiken in diesen Softwareprodukten. Diese Tabelle enthält außerdem Betriebssysteminformationen, CVE-IDs und Informationen zum Schweregrad des Sicherheitsrisikos.
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilites assessment, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: be21be07758c1123cdde38e3750cafe739bfb66a
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653653"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Exportieren der Bewertung von Softwarerisiken pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Gibt alle bekannten Sicherheitsrisiken und deren Details für alle Geräte auf Gerätebasis zurück.

Es gibt verschiedene API-Aufrufe, um verschiedene Datentypen zu erhalten. Da die Datenmenge sehr groß sein kann, gibt es zwei Möglichkeiten zum Abrufen:

- **OData**  Die API verwendet alle Daten in Ihrer Organisation als Json-Antworten nach dem OData-Protokoll. Diese Methode ist am besten für _kleine Organisationen mit weniger als 100K-Geräten._ Die Antwort wird paginiert, sodass Sie das odata.nextLink-Feld aus der Antwort verwenden können, \@ um die nächsten Ergebnisse zu erhalten.

- **über Dateien** Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100K-Geräten empfohlen. Diese API verwendet alle Daten in Ihrer Organisation als Downloaddateien. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:

  - Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten zu erhalten.

  - Laden Sie alle Dateien mithilfe der URLs zum Herunterladen herunter, und verarbeiten Sie die Daten nach Ben.

Die erfassten Daten (für _OData_ oder über Dateien _)_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.

Sofern nicht anders angegeben, sind **** alle aufgeführten Exportbewertungsmethoden der vollständige Export und nach Gerät **_(auch_** als pro **_Gerät bezeichnet)._**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Export software vulnerabilities assessment (OData)

### <a name="11-api-method-description"></a>Beschreibung der 1.1-API-Methode

Diese API-Antwort enthält alle Daten der installierten Software pro Gerät. Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.

#### <a name="limitations"></a>Einschränkungen

>- Die maximale Seitengröße beträgt 200.000.
>
>- Die Tarifeinschränkungen für diese API sind 30 Anrufe pro Minute und 1000 Anrufe pro Stunde.

### <a name="12-permissions"></a>1.2 Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Anwendung | Vulnerability.Read.All | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vulnerability.Read | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 Parameter

- pageSize (Standard = 50.000) – Anzahl der Ergebnisse als Antwort
- $top – Anzahl der zurückzukehrende Ergebnisse (gibt @odata.nextLink nicht zurück und zieht daher nicht alle Daten zurück)

### <a name="15-properties"></a>1.5 Eigenschaften
>
>[!Note]
>
>- Jeder Datensatz beträgt ca. 1 KB Daten. Berücksichtigen Sie dies bei der Auswahl des richtigen pageSize-Parameters für Sie.
>
>- Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben. Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.
>
>- Die in der folgenden Tabelle definierten Eigenschaften werden alphanumerisch nach Eigenschafts-ID aufgelistet.  Beim Ausführen dieser API wird die resultierende Ausgabe nicht unbedingt in der in diesen Tabellen aufgeführten Reihenfolge zurückgegeben.
>

Property (id) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
CveId | string | Eindeutige ID, die der Sicherheitslücke unter dem System für häufige Sicherheitsrisiken und -risiken (Common Vulnerabilities and Exposures, CVE) zugewiesen ist. | CVE-2020-15992
CvssScore | string | Die CVSS-Bewertung des CVE. | 6.2
DeviceId | string | Eindeutige ID für das Gerät im Dienst. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Vollqualifizierter Domänenname (FQDN) des Geräts. | johnlaptop.europe.contoso.com
DiskPaths  | \[Arrayzeichenfolge\] | Datenträgerbeweis, dass das Produkt auf dem Gerät installiert ist. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | Die Ausnutzungsebene dieser Sicherheitsanfälligkeit (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | string | Das erste Mal, dass der CVE dieses Produkts auf dem Gerät angezeigt wurde. | 2020-11-03 10:13:34.8476880
Id | string | Eindeutige ID für den Datensatz. | 123ABG55_573AG&mnp!
LastSeenTimestamp | string | Das letzte Mal, dass der CVE auf dem Gerät angezeigt wurde. | 2020-11-03 10:13:34.8476880
OSPlatform | string | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Weitere Informationen finden Sie unter tvm supported operating systems and platforms. | Windows10
RbacGroupName  | string | Die rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keinem RBAC-Gruppen zugewiesen ist, wird der Wert "Nicht zugewiesen" angezeigt. Wenn die Organisation keine RBAC-Gruppen enthält, ist der Wert "None". | Server
RecommendationReference | string | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (optional) | string | Name oder Beschreibung des Sicherheitsupdates, das vom Softwareanbieter bereitgestellt wird, um die Sicherheitslücke zu bean standen. | Sicherheitsupdates vom April 2020
RecommendedSecurityUpdateId (optional) | string | Bezeichner der anwendbaren Sicherheitsupdates oder bezeichner für die entsprechenden Anleitungen oder Knowledge Base (KB)-Artikel | 4550961
RegistryPaths  | \[Arrayzeichenfolge\] | Registrierungsbeweis, dass das Produkt auf dem Gerät installiert ist. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | string | Name des Softwareprodukts. | chrome
SoftwareVendor | string | Name des Softwareanbieters. | google
SoftwareVersion | string | Versionsnummer des Softwareprodukts. | 81.0.4044.138
VulnerabilitySeverityLevel  | string | Schweregrad, der der Sicherheitslücke zugewiesen ist, basierend auf der CVSS-Bewertung und dynamischen Faktoren, die von der Bedrohungslandschaft beeinflusst werden. | Mittel

### <a name="16-examples"></a>1.6 Beispiele

#### <a name="161-request-example"></a>1.6.1 Anforderungsbeispiel

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 Antwortbeispiel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Bewertung von Softwarerisiken exportieren (über Dateien)

### <a name="21-api-method-description"></a>Beschreibung der 2.1-API-Methode

Diese API-Antwort enthält alle Daten der installierten Software pro Gerät. Gibt eine Tabelle mit einem Eintrag für jede eindeutige Kombination aus DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID zurück.

#### <a name="212-limitations"></a>2.1.2 Einschränkungen

Die Tarifeinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.

### <a name="22-permissions"></a>2.2 Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Anwendung | Vulnerability.Read.All | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vulnerability.Read | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4-Parameter

- sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (Maximal 24 Stunden)

### <a name="25-properties"></a>2.5-Eigenschaften

>[!Note]
>
>- Die Dateien sind gzip-komprimierte & im mehrstufigen Json-Format.
>
>- Die #A0 sind nur für 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.
>
>- Um die maximale Downloadgeschwindigkeit Ihrer Daten zu erhalten, können Sie sicherstellen, dass Sie aus derselben Azure-Region heruntergeladen werden, in der sich Ihre Daten befinden.
>

>[!Note]
>
>- Jeder Datensatz beträgt ca. 1 KB Daten. Berücksichtigen Sie dies bei der Auswahl des richtigen pageSize-Parameters für Sie.
>
>- Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben. Diese Spalten sind temporär und können entfernt werden, verwenden Sie bitte nur die dokumentierten Spalten.
>
>- Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.  Beim Ausführen dieser API wird die resultierende Ausgabe nicht unbedingt in der in diesen Tabellen aufgeführten Reihenfolge zurückgegeben.
>

Property (id) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\]  | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | Der Zeitpunkt, zu dem der Export generiert wurde. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Beispiele

#### <a name="261-request-example"></a>2.6.1 Anforderungsbeispiel

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 Antwortbeispiel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Siehe auch

- [Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät](get-assessmnt-1methods-properties.md)

- [Exportieren einer sicheren Konfigurationsbewertung pro Gerät](get-assessmnt-secure-cfg.md)

- [Exportieren der Softwareinventarbewertung pro Gerät](get-assessmnt-software-inventory.md)

Andere verwandte

- [Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
