---
title: Api zum Abrufen von Warnungen
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Warnungsressourcentyps in Microsoft Defender für Endpunkt.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289679"
---
# <a name="alert-resource-type"></a>Warnungsressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Warnung erhalten](get-alert-info-by-id.md) | [Warnung](alerts.md) | Ruft ein einzelnes [Warnungsobjekt](alerts.md) ab.
[Warnungen auflisten](get-alerts.md) | [Warnungssammlung](alerts.md) | [Warnungssammlung auflisten.](alerts.md)
[Warnung aktualisieren](update-alert.md) | [Warnung](alerts.md) | Aktualisieren sie eine bestimmte [Warnung.](alerts.md)
[Warnungen bei Batchaktualisierungen](batch-update-alerts.md) | | Aktualisieren eines Batches von [Warnungen.](alerts.md)
[Warnung erstellen](create-alert-by-reference.md)|[Warnung](alerts.md)|Erstellen Sie eine Warnung basierend auf Ereignisdaten, die aus [der erweiterten Suche](run-advanced-query-api.md)abgerufen wurden.
[Verwandte Domänen auflisten](get-alert-related-domain-info.md)|Domänensammlung| Listet URLs auf, die der Warnung zugeordnet sind.
[Auflisten verwandter Dateien](get-alert-related-files-info.md) | [Dateisammlung](files.md) |  Auflisten der Dateientitäten, die der [Warnung](alerts.md)zugeordnet sind. [](files.md)
[Verwandte IPs auflisten](get-alert-related-ip-info.md) | IP-Sammlung | IPs auflisten, die der Warnung zugeordnet sind.
[Abrufen verwandter Computer](get-alert-related-machine-info.md) | [Computer](machine.md) | Der [Computer,](machine.md) der der [Warnung](alerts.md)zugeordnet ist.
[Abrufen verwandter Benutzer](get-alert-related-user-info.md) | [Benutzer](user.md) | Der [Benutzer,](user.md) der der [Warnung](alerts.md)zugeordnet ist.

## <a name="properties"></a>Eigenschaften

Eigenschaft |    Typ    |    Beschreibung
:---|:---|:---
id | Zeichenfolge | Warnungs-ID.
title | String | Warnungstitel.
description | String | Warnungsbeschreibung.
alertCreationTime | Nullable DateTimeOffset | Datum und Uhrzeit (in UTC), an dem die Warnung erstellt wurde.
lastEventTime | Nullable DateTimeOffset | Das letzte Auftreten des Ereignisses, das die Warnung auf demselben Gerät ausgelöst hat.
firstEventTime | Nullable DateTimeOffset | Das erste Auftreten des Ereignisses, das die Warnung auf diesem Gerät ausgelöst hat.
lastUpdateTime | Nullable DateTimeOffset | Datum und Uhrzeit (in UTC), an dem die Warnung zuletzt aktualisiert wurde.
resolvedTime | Nullable DateTimeOffset | Datum und Uhrzeit, an denen der Status der Warnung in "Aufgelöst" geändert wurde.
incidentId | Nullable Long | Die [Vorfall-ID](view-incidents-queue.md) der Warnung.
investigationId | Nullable Long | Die [Untersuchungs-ID](automated-investigations.md) im Zusammenhang mit der Warnung.
investigationState | Nullable Enum | Der aktuelle Status der [Untersuchung](automated-investigations.md). Mögliche Werte sind: 'Unknown', 'Terminated', 'SuccessfullyRemediated', "Gutartig", "Fehlgeschlagen", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".
assignedTo | Zeichenfolge | Besitzer der Warnung.
Schweregrad | Enum | Der Schweregrad der Warnung. Mögliche Werte sind: "UnSpecified", "Informational", "Low", "Medium" und "High".
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: "Unknown", "New", "InProgress" und "Resolved".
classification | Nullable Enum | Spezifikation der Warnung. Mögliche Werte sind: 'Unknown', 'FalsePositive', 'TruePositive'.
Bestimmung | Nullable Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".
category| String | Die Kategorie der Warnung.
detectionSource | Zeichenfolge | Erkennungsquelle.
threatFamilyName | Zeichenfolge | Bedrohungsfamilie.
threatName | Zeichenfolge | Name der Bedrohung.
machineId | Zeichenfolge | ID einer [](machine.md) Computerentität, die der Warnung zugeordnet ist.
computerDnsName | Zeichenfolge | [Computer](machine.md) vollqualifizierte Name.
aadTenantId | Zeichenfolge | Die Azure Active Directory-ID.
detectorId | Zeichenfolge | Die ID des Identifikationsgeräts, das die Warnung ausgelöst hat.
Kommentare | Liste der Warnungskommentare | Alert Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.
Beweis | Liste der Warnungsnachweise | Nachweise im Zusammenhang mit der Warnung. Siehe Beispiel unten.

### <a name="response-example-for-getting-single-alert"></a>Antwortbeispiel für das Abrufen einer einzelnen Warnung:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
