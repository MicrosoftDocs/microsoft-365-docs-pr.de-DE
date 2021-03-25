---
title: Abrufen der Benachrichtigungs-API
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Warnung in Microsoft Defender for Endpoint.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199621"
---
# <a name="alert-resource-type"></a>Ressourcentyp "Warnung"

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Methoden

Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Warnung erhalten](get-alert-info-by-id.md) | [Warnung](alerts.md) | Ein einzelnes [Warnungsobjekt](alerts.md) erhalten.
[Warnungen auflisten](get-alerts.md) | [Warnungssammlung](alerts.md) | Auflisten [der Warnungssammlung.](alerts.md)
[Warnung aktualisieren](update-alert.md) | [Warnung](alerts.md) | Aktualisieren einer [bestimmten Warnung](alerts.md).
[Batchupdatewarnungen](batch-update-alerts.md) | | Aktualisieren eines Batches von [Warnungen](alerts.md).
[Erstellen einer Warnung](create-alert-by-reference.md)|[Warnung](alerts.md)|Erstellen Sie eine Warnung basierend auf Ereignisdaten, die von [Advanced Hunting erhalten wurden.](run-advanced-query-api.md)
[Auflisten verwandter Domänen](get-alert-related-domain-info.md)|Domänensammlung| Listet URLs auf, die der Warnung zugeordnet sind.
[Auflisten verwandter Dateien](get-alert-related-files-info.md) | [Dateisammlung](files.md) |  Listet [die](files.md) Dateientitäten auf, die der Warnung [zugeordnet sind.](alerts.md)
[Auflisten verwandter IPs](get-alert-related-ip-info.md) | IP-Auflistung | Listet IPs auf, die der Warnung zugeordnet sind.
[Verwandte Computer erhalten](get-alert-related-machine-info.md) | [Maschine](machine.md) | Der [Computer,](machine.md) der der Warnung [zugeordnet ist.](alerts.md)
[Verwandte Benutzer erhalten](get-alert-related-user-info.md) | [Benutzer](user.md) | Der [Benutzer,](user.md) der der Warnung [zugeordnet ist.](alerts.md)


## <a name="properties"></a>Eigenschaften

Eigenschaft |    Typ    |    Beschreibung
:---|:---|:---
id | String | Warnungs-ID.
title | String | Warnungstitel.
description | String | Warnungsbeschreibung.
alertCreationTime | Nullable DateTimeOffset | Das Datum und die Uhrzeit (in UTC), zu der die Warnung erstellt wurde.
lastEventTime | Nullable DateTimeOffset | Das letzte Vorkommen des Ereignisses, das die Warnung auf demselben Gerät ausgelöst hat.
firstEventTime | Nullable DateTimeOffset | Das erste Vorkommen des Ereignisses, das die Warnung auf diesem Gerät ausgelöst hat.
lastUpdateTime | Nullable DateTimeOffset | Datum und Uhrzeit (in UTC), zu der die Warnung zuletzt aktualisiert wurde.
resolvedTime | Nullable DateTimeOffset | Datum und Uhrzeit, in dem der Status der Warnung in "Aufgelöst" geändert wurde.
incidentId | Nullable Long | Die [Vorfall-ID](view-incidents-queue.md) der Warnung.
investigationId | Nullable Long | Die [Untersuchungs-ID](automated-investigations.md) im Zusammenhang mit der Warnung.
investigationState | Nullable Enum | Der aktuelle Status der [Untersuchung](automated-investigations.md). Mögliche Werte sind: "Unknown", "Terminated", "SuccessfullyRemediated", "Benign", "Failed", "PartiallyRemediated", "Running", "PendingApproval", "PendingResource", "PartiallyInvestigated", "TerminatedByUser", "TerminatedBySystem", "Queued", "InnerFailure", "PreexistingAlert", "UnsupportedOs", "UnsupportedAlertType", "SuppressedAlert".
assignedTo | String | Besitzer der Warnung.
Schweregrad | Enum | Der Schweregrad der Warnung. Mögliche Werte sind: "UnSpecified", "Informational", "Low", "Medium" und "High".
status | Enum | Gibt den aktuellen Status der Warnung an. Mögliche Werte sind: "Unbekannt", "Neu", "InProgress" und "Aufgelöst".
classification | Nullable Enum | Spezifikation der Warnung. Mögliche Werte sind: "Unbekannt", "FalsePositive", "TruePositive".
Bestimmung | Nullable Enum | Gibt die Bestimmung der Warnung an. Mögliche Werte sind: "NotAvailable", "Apt", "Malware", "SecurityPersonnel", "SecurityTesting", "UnwantedSoftware", "Other".
category| String | Die Kategorie der Warnung.
detectionSource | String | Erkennungsquelle.
threatFamilyName | String | Bedrohungsfamilie.
threatName | String | Bedrohungsname.
machineId | String | ID einer [Computerentität,](machine.md) die der Warnung zugeordnet ist.
computerDnsName | String | [vollqualifizierten](machine.md) Namen des Computers.
aadTenantId | String | Die Azure Active Directory-ID.
detectorId | String | Die ID des Melders, der die Warnung ausgelöst hat.
Kommentare | Liste der Warnungskommentare | Alert Comment-Objekt enthält: Kommentarzeichenfolge, createdBy-Zeichenfolge und createTime-Datumszeit.
Beweis | Liste der Warnungsbeweis | Nachweise im Zusammenhang mit der Warnung. Siehe Beispiel unten.

### <a name="response-example-for-getting-single-alert"></a>Antwortbeispiel zum Abrufen einer einzelnen Warnung:

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
