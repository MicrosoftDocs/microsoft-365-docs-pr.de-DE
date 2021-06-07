---
title: Abrufen einer Korrekturaktivität nach ID
description: Gibt Informationen für die angegebene Korrekturaktivität zurück.
keywords: APIs, Wartung, Korrektur-API, abrufen, Wartungsaufgaben, Korrektur nach ID,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772149"
---
# <a name="get-one-remediation-activity-by-id"></a>Abrufen einer Korrekturaktivität nach ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Gibt Informationen für die angegebene Korrekturaktivität zurück. Stellt die gleichen Spalten wie ["Alle Korrekturaktivität abrufen"](get-remediation-all-activities.md)dar, gibt jedoch nur Ergebnisse _für die angegebene Korrekturaktivität_ zurück.

[Erfahren Sie mehr über Korrekturaktivitäten.](tvm-remediation.md)

## <a name="list-a-specified-remediation-activity-for-id"></a>Auflisten einer angegebenen Korrekturaktivität für (ID)

**URL:** GET: /api/remediationTasks/id \{\}

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | RemediationTask.Read.All | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | RemediationTask.Read.Read | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'

## <a name="properties"></a>Eigenschaften

Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
category | String | Kategorie der Korrekturaktivität (Software/Sicherheitskonfiguration) | Software
completerEmail | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mail | null
completerId | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID. | null
completionMethod | String | Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen abgeschlossen werden, die "Als abgeschlossen markieren" auswählt. | Automatisch
createdOn | DateTime | Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde | 2021-01-12T18:54:11.5499478Z
description | String | Beschreibung dieser Korrekturaktivität | Aktualisieren Sie Microsoft Silverlight auf eine höhere Version, um bekannte Sicherheitsrisiken zu beheben, die sich auf Ihre Geräte auswirken.
dueOn | DateTime | Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat | 2021-01-13T00:00:00Z
fixedDevices |  | Die Anzahl der Geräte, die behoben wurden | 2
id | String | ID dieser Korrekturaktivität | 097d9735-5479-4899-b1b7-77398899df92
nameId | String | Verwandter Produktname | Microsoft Silverlight
priority | String | Priorität des Erstellers für diese Korrekturaktivität (Hoch\Mittel\Niedrig) | Hoch
Productid | String | Verwandte Produkt-ID | microsoft-_-silverlight
productivityImpactRemediationType | String | Einige Konfigurationsänderungen können nur für Geräte ohne Auswirkungen auf den Benutzer angefordert werden. Dieser Wert gibt die Auswahl zwischen "alle verfügbar gemachten Geräte" oder "nur Geräte ohne Auswirkungen auf den Benutzer" an. | AllExposedAssets
rbacGroupNames | String | Verwandte Gerätegruppennamen | [ "Windows Server", "Windows 10" ]
recommendedProgram | String | Empfohlenes Programm für ein Upgrade auf | null
recommendedVendor | String | Empfohlener Anbieter für ein Upgrade auf | null
recommendedVersion | String | Empfohlene Version, auf die aktualisiert/aktualisiert werden soll | null
relatedComponent | String | Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung) | Microsoft Microsoft Silverlight
requesterEmail | String | Creator-E-Mail-Adresse | globaladmin@UserName.contoso.com
requesterId | String | Creator-Objekt-ID | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | String | Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat | null
Scid | String | SCID der zugehörigen Sicherheitsempfehlung | null
status | String | Wartungsaktivitätsstatus (aktiv/abgeschlossen) | Aktiv
statusLastModifiedOn | DateTime | Datum, an dem das Statusfeld aktualisiert wurde | 2021-01-12T18:54:11.5499487Z
targetDevices | Long | Anzahl der verfügbar gemachten Geräte, für die diese Korrektur gilt | 43
title | String | Titel dieser Korrekturaktivität | Microsoft Silverlight
type | String | Korrekturtyp | Update
Vendorid | String | Name des zugehörigen Anbieters | Microsoft

## <a name="example"></a>Beispiel

### <a name="request-example"></a>Anforderungsbeispiel

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Anforderungsbeispiel

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>Siehe auch

- [Korrekturmethoden und -eigenschaften](get-remediation-methods-properties.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md)

- [Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
