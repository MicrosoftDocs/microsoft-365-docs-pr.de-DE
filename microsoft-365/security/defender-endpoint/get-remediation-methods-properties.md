---
title: Methoden und Eigenschaften der Korrekturaktivität
description: Die API-Antwort enthält & in Ihrem Mandanten erstellte Maßnahmen zur Behebung von Sicherheitslücken. Sie können alle Korrekturaktivitäten, nur eine Korrekturaktivität oder Informationen zu verfügbar gemachten Geräten für eine ausgewählte Behebungsaufgabe anfordern.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.openlocfilehash: f720d638ec469523a1d567dee9c01fa0974b0090
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061124"
---
# <a name="remediation-activity-methods-and-properties"></a>Methoden und Eigenschaften der Korrekturaktivität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Die API-Antwort enthält [&,](next-gen-threat-and-vuln-mgt.md)die in Ihrem Mandanten erstellt   wurden.  

## <a name="methods"></a>Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md) | Untersuchungssammlung | Gibt Informationen zu allen Korrekturaktivitäten zurück.
[Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md) | Untersuchungsentität | Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaktivität zurück.
[Get one remediation activity by Id](get-remediation-one-activity.md) | Untersuchungsentität | Gibt Informationen für die angegebene Korrekturaktivität zurück.

Erfahren Sie mehr [über Korrekturaktivitäten](tvm-remediation.md).

## <a name="properties"></a>Eigenschaften

Eigenschafts-ID | Datentyp | Beschreibung
:---|:---|:---
category | String | Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration)
completerEmail | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails.
completerId | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.
completionMethod | String | Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt.
createdOn | DateTime | Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde
description | String | Beschreibung dieser Korrekturaktivität
dueOn | DateTime | Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat
fixedDevices |  | Die Anzahl der geräte, die behoben wurden
id | String | ID dieser Korrekturaktivität
nameId | String | Verwandter Produktname
priority | String | Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low)
productId | String | Verwandte Produkt-ID
productivityImpactRemediationType | String | Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden. Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an.
rbacGroupNames | String | Verwandte Gerätegruppennamen
recommendedProgram | String | Empfohlenes Programm zum Upgrade auf
recommendedVendor | String | Empfohlener Anbieter zum Upgrade auf
recommendedVersion | String | Empfohlene Version zum Aktualisieren/Aktualisieren auf
relatedComponent | String | Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)
requesterEmail | String | E-Mail-Adresse des Erstellers
requesterId | String | Creator-Objekt-ID
requesterNotes | String | Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat
scid | String | SCID der zugehörigen Sicherheitsempfehlung
status | String | Status der Korrekturaktivität (Aktiv/Abgeschlossen)
statusLastModifiedOn | DateTime | Datum, an dem das Statusfeld aktualisiert wurde
targetDevices | Long | Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist
title | String | Titel dieser Korrekturaktivität
type | String | Behebungstyp
vendorId | String | Verwandter Herstellername

## <a name="see-also"></a>Siehe auch

- [Get one remediation activity by Id](get-remediation-one-activity.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md)

- [Risikobasiertes Bedrohungsmanagement & Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
