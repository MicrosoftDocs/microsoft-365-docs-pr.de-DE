---
title: Methoden und Eigenschaften der Korrekturaktivität
description: Die API-Antwort enthält & Sicherheitsrisikomanagement, die in Ihrem Mandanten erstellt wurden. Sie können alle Korrekturaktivitäten, nur eine Korrekturaktivität oder Informationen zu verfügbar gemachten Geräten für eine ausgewählte Behebungsaufgabe anfordern.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation methods, remediation properties,
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
ms.openlocfilehash: 4c0ecd89c45ec2c91dc37f0c9cd0bfb868c0474e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245540"
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

Die API-Antwort enthält [& Sicherheitsrisikomanagement,](next-gen-threat-and-vuln-mgt.md)die in Ihrem   Mandanten erstellt wurden.  

## <a name="methods"></a>Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md) | Untersuchungssammlung | Gibt Informationen zu allen Korrekturaktivitäten zurück.
[Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md) | Untersuchungsentität | Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaktivität zurück.
[Erhalten einer Korrekturaktivität nach ID](get-remediation-one-activity.md) | Untersuchungsentität | Gibt Informationen für die angegebene Korrekturaktivität zurück.

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

- [Erhalten einer Korrekturaktivität nach ID](get-remediation-one-activity.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md)

- [Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
