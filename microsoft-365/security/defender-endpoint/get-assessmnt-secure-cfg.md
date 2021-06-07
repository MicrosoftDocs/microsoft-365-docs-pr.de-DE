---
title: Exportieren der Bewertung der sicheren Konfiguration pro Gerät
description: Gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.
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
ms.openlocfilehash: ab33db7fb7acf1969973a7af8f80ea97ef3d378f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778334"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Exportieren der Bewertung der sicheren Konfiguration pro Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Gibt alle Konfigurationen und deren Status pro Gerät zurück.

Es gibt verschiedene API-Aufrufe, um unterschiedliche Arten von Daten abzurufen. Da die Datenmenge groß sein kann, gibt es zwei Möglichkeiten, sie abzurufen:

- [Exportieren Sie **OData**](#1-export-secure-configuration-assessment-odata)zur Bewertung der sicheren Konfiguration: Die API ruft alle Daten in Ihrer Organisation als JSON-Antworten nach dem OData-Protokoll ab. Diese Methode eignet sich am besten für _kleine Organisationen mit weniger als 100 K-Geräten._ Die Antwort ist paginiert, sodass Sie das \@ Feld odata.nextLink aus der Antwort verwenden können, um die nächsten Ergebnisse abzurufen.

- Exportieren der [Bewertung der sicheren Konfiguration **über Dateien:**](#2-export-secure-configuration-assessment-via-files)Diese API-Lösung ermöglicht das schnellere und zuverlässigere Abrufen größerer Datenmengen. Daher wird es für große Organisationen mit mehr als 100 K-Geräten empfohlen. Diese API ruft alle Daten in Ihrer Organisation als Downloaddateien ab. Die Antwort enthält URLs zum Herunterladen aller Daten aus Azure Storage. Mit dieser API können Sie alle Ihre Daten aus Azure Storage wie folgt herunterladen:

  - Rufen Sie die API auf, um eine Liste der Download-URLs mit allen Organisationsdaten abzurufen.

  - Laden Sie alle Dateien mithilfe der Download-URLs herunter, und verarbeiten Sie die Daten nach Bedarf.

Daten, die gesammelt werden (entweder mit _OData_ oder _über Dateien),_ sind die aktuelle Momentaufnahme des aktuellen Zustands und enthalten keine historischen Daten. Um historische Daten zu sammeln, müssen Kunden die Daten in ihren eigenen Datenspeichern speichern.

> [!Note]
>
> Sofern nicht anders angegeben, sind alle aufgeführten Exportbewertungsmethoden **_vollständige Exporte_** und **_nach Gerät_** (auch als **_pro Gerät_** bezeichnet).

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Exportieren der Bewertung der sicheren Konfiguration (OData)

### <a name="11-api-method-description"></a>1.1 API-Methodenbeschreibung

Diese API-Antwort enthält die Bewertung der sicheren Konfiguration auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.

#### <a name="111-limitations"></a>1.1.1 Einschränkungen

- Die maximale Seitengröße beträgt 200.000.

- Die Rateneinschränkungen für diese API liegen bei 30 Aufrufen pro Minute und 1.000 Aufrufen pro Stunde.

### <a name="12-permissions"></a>1.2 Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Anwendung | Vulnerability.Read.All | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vulnerability.Read | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 Parameter

- pageSize \( default = 50.000 \) – Anzahl der Ergebnisse als Antwort

- \$top – Anzahl der zurückzugebenden Ergebnisse \( gibt \@ odata.nextLink nicht zurück und ruft daher nicht alle Daten ab\)

### <a name="15-properties"></a>1.5-Eigenschaften

>[!Note]
>
>- Die in der folgenden Tabelle definierten Eigenschaften werden alphabetisch nach Eigenschafts-ID aufgelistet.  Beim Ausführen dieser API wird die resultierende Ausgabe nicht notwendigerweise in der in dieser Tabelle aufgeführten Reihenfolge zurückgegeben.
>
>- Einige zusätzliche Spalten werden möglicherweise in der Antwort zurückgegeben. Diese Spalten sind temporär und können entfernt werden. Verwenden Sie nur die dokumentierten Spalten.
>

Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
ConfigurationCategory | string | Kategorie oder Gruppe, zu der die Konfiguration gehört: Anwendung, Betriebssystem, Netzwerk, Konten, Sicherheitskontrollen | Sicherheitskontrollen
ConfigurationId | string | Eindeutiger Bezeichner für eine bestimmte Konfiguration | scid-10000
ConfigurationImpact | string | Bewertung der Auswirkungen der Konfiguration auf die Gesamtkonfigurationsbewertung (1-10) | 9 
ConfigurationName | string | Anzeigename der Konfiguration | Geräte in Microsoft Defender für Endpunkt onboarden
ConfigurationSubcategory | string | Unterkategorie oder Untergruppe, zu der die Konfiguration gehört. In vielen Fällen beschreibt dies bestimmte Funktionen oder Features. | Onboarding von Geräten
Deviceid | Zeichenfolge | Eindeutiger Bezeichner für das Gerät im Dienst. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | Zeichenfolge | Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Geräts. | johnlaptop.europe.contoso.com
IsApplicable | bool | Gibt an, ob die Konfiguration oder Richtlinie anwendbar ist. | true
IsCompliant | bool | Gibt an, ob die Konfiguration oder Richtlinie ordnungsgemäß konfiguriert ist | false
IsExpectedUserImpact | bool | Gibt an, ob es Auswirkungen auf den Benutzer gibt, wenn die Konfiguration angewendet wird. | true
OSPlatform | Zeichenfolge | Plattform des Betriebssystems, das auf dem Gerät ausgeführt wird. Gibt spezifische Betriebssysteme an, einschließlich Variationen innerhalb der gleichen Familie, wie z. B. Windows 10 und Windows 7. Ausführliche Informationen finden Sie unter tvm-unterstützte Betriebssysteme und Plattformen. | Windows 10
RbacGroupName | Zeichenfolge | Die Rollenbasierte Zugriffssteuerungsgruppe (RBAC). Wenn dieses Gerät keiner RBAC-Gruppe zugewiesen ist, lautet der Wert "Nicht zugewiesen". Wenn die Organisation keine RBAC-Gruppen enthält, lautet der Wert "None". | Server
RecommendationReference | Zeichenfolge | Ein Verweis auf die Empfehlungs-ID im Zusammenhang mit dieser Software. | sca-_-scid-20000
Zeitstempel | Zeichenfolge | Zeitpunkt, zu dem die Konfiguration zuletzt auf dem Gerät angezeigt wurde | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Beispiele

#### <a name="161-request-example"></a>1.6.1 Anforderungsbeispiel

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 Antwortbeispiel

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Exportieren der Bewertung der sicheren Konfiguration (über Dateien)

### <a name="21-api-method-description"></a>2.1 API-Methodenbeschreibung

Diese API-Antwort enthält die Bewertung der sicheren Konfiguration auf Ihren verfügbar gemachten Geräten und gibt einen Eintrag für jede eindeutige Kombination aus DeviceId, ConfigurationId, zurück.

#### <a name="212-limitations"></a>2.1.2 Einschränkungen

Die Rateneinschränkungen für diese API sind 5 Anrufe pro Minute und 20 Anrufe pro Stunde.

### <a name="22-permissions"></a>2.2 Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
---|---|---
Anwendung | Vulnerability.Read.All | \'Sicherheitsrisikoinformationen "Bedrohungs- und Sicherheitsrisikomanagement" lesen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vulnerability.Read | \'Sicherheitsrisikoinformationen "Bedrohungs- und Sicherheitsrisikomanagement" lesen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parameter

- sasValidHours – Die Anzahl der Stunden, für die die Download-URLs gültig sind (maximal 24 Stunden).

### <a name="25-properties"></a>2.5-Eigenschaften

>[!Note]
>
>- Die Dateien werden & im mehrzeiligen JSON-Format gzipkomprimiert.
>
>- Die Download-URLs sind nur 3 Stunden gültig. andernfalls können Sie den Parameter verwenden.
>
>- Für eine maximale Downloadgeschwindigkeit Ihrer Daten können Sie sicherstellen, dass Sie die Daten aus derselben Azure-Region herunterladen, in der sich Ihre Daten befinden.
>
Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
Exportieren von Dateien | \[Arrayzeichenfolge\] | Eine Liste der Download-URLs für Dateien, die die aktuelle Momentaufnahme der Organisation enthalten | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | Zeichenfolge | Die Zeit, zu der der Export generiert wurde. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Beispiele

#### <a name="261-request-example"></a>2.6.1 Anforderungsbeispiel

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 Antwortbeispiel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Siehe auch

- [Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät](get-assessmnt-1methods-properties.md)

- [Exportieren der Softwareinventarisierungsbewertung pro Gerät](get-assessmnt-software-inventory.md)

- [Exportieren der Bewertung von Software-Sicherheitsrisiken pro Gerät](get-assessmnt-software-vulnerabilities.md)

Andere verwandte

- [Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
