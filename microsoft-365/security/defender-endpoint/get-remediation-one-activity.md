---
title: Erhalten einer Korrekturaktivität nach ID
description: Gibt Informationen für die angegebene Korrekturaktivität zurück.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
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
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244443"
---
# <a name="get-one-remediation-activity-by-id"></a>Erhalten einer Korrekturaktivität nach ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Gibt Informationen für die angegebene Korrekturaktivität zurück. Stellt die gleichen Spalten wie Alle Korrekturaktivitäten "get all [remediation"](get-remediation-all-activities.md)dar, gibt jedoch nur Ergebnisse für die angegebene _Korrekturaktivität zurück._

[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).

## <a name="list-a-specified-remediation-activity-for-id"></a>Auflisten einer angegebenen Korrekturaktivität für (id)

**URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | RemediationTask.Read.All | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | RemediationTask.Read.Read | \'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'

## <a name="properties"></a>Eigenschaften

Property (id) | Datentyp | Beschreibung | Beispiel für einen zurückgegebenen Wert
:---|:---|:---|:---
category | String | Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration) | Software
completerEmail | Zeichenfolge | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails. | null
completerId | Zeichenfolge | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID. | null
completionMethod | Zeichenfolge | Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt. | Automatisch
createdOn | DateTime | Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde | 2021-01-12T18:54:11.5499478Z
description | Zeichenfolge | Beschreibung dieser Korrekturaktivität | Aktualisieren Sie Microsoft Silverlight auf eine spätere Version, um bekannte Sicherheitsrisiken für Ihre Geräte zu mindern.
dueOn | DateTime | Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat | 2021-01-13T00:00:00Z
fixedDevices |  | Die Anzahl der geräte, die behoben wurden | 2
id | Zeichenfolge | ID dieser Korrekturaktivität | 097d9735-5479-4899-b1b7-77398899df92
nameId | Zeichenfolge | Verwandter Produktname | Microsoft Silverlight
priority | Zeichenfolge | Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low) | Hoch
productId | Zeichenfolge | Verwandte Produkt-ID | microsoft-_-silverlight
productivityImpactRemediationType | Zeichenfolge | Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden. Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an. | AllExposedAssets
rbacGroupNames | Zeichenfolge | Verwandte Gerätegruppennamen | [ "Windows Server", "Windows 10" ]
recommendedProgram | Zeichenfolge | Empfohlenes Programm zum Upgrade auf | null
recommendedVendor | Zeichenfolge | Empfohlener Anbieter zum Upgrade auf | null
recommendedVersion | Zeichenfolge | Empfohlene Version zum Aktualisieren/Aktualisieren auf | null
relatedComponent | Zeichenfolge | Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung) | Microsoft Microsoft Silverlight
requesterEmail | Zeichenfolge | E-Mail-Adresse des Erstellers | globaladmin@UserName.contoso.com
requesterId | Zeichenfolge | Creator-Objekt-ID | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Zeichenfolge | Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat | null
scid | Zeichenfolge | SCID der zugehörigen Sicherheitsempfehlung | null
status | Zeichenfolge | Status der Korrekturaktivität (Aktiv/Abgeschlossen) | Aktiv
statusLastModifiedOn | DateTime | Datum, an dem das Statusfeld aktualisiert wurde | 2021-01-12T18:54:11.5499487Z
targetDevices | Long | Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist | 43
title | String | Titel dieser Korrekturaktivität | Microsoft Silverlight
type | Zeichenfolge | Behebungstyp | Aktualisieren
vendorId | Zeichenfolge | Verwandter Herstellername | Microsoft

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

- [Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
