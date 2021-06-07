---
title: Methoden und Eigenschaften der Korrekturaktivität
description: Die API-Antwort enthält Bedrohungen & Sicherheitsrisikomanagement in Ihrem Mandanten erstellten Korrekturaktivitäten. Sie können alle Wartungsaktivitäten, nur eine Korrekturaktivität oder Informationen zu verfügbar gemachten Geräten für eine ausgewählte Korrekturaufgabe anfordern.
keywords: APIs, Wartung, Korrektur-API, abrufen, Wartungsaufgaben, Korrekturmethoden, Korrektureigenschaften,
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
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769233"
---
# <a name="remediation-activity-methods-and-properties"></a>Methoden und Eigenschaften der Korrekturaktivität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Die API-Antwort enthält [Bedrohungs- & Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)   Korrekturaktivitäten, die in Ihrem Mandanten erstellt wurden.  

## <a name="methods"></a>Methoden

Methode | Datentyp | Beschreibung
:---|:---|:---
[Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md) | Untersuchungssammlung | Gibt Informationen zu allen Korrekturaktivitäten zurück.
[Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md) | Untersuchungsentität | Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaktivität zurück.
[Erhalten einer Korrekturaktivität nach ID](get-remediation-one-activity.md) | Untersuchungsentität | Gibt Informationen für die angegebene Korrekturaktivität zurück.

Erfahren Sie mehr über [Korrekturaktivitäten.](tvm-remediation.md)

## <a name="properties"></a>Eigenschaften

Eigenschafts-ID | Datentyp | Beschreibung
:---|:---|:---
category | String | Kategorie der Korrekturaktivität (Software/Sicherheitskonfiguration)
completerEmail | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mail
completerId | String | Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.
completionMethod | String | Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen abgeschlossen werden, die "Als abgeschlossen markieren" auswählt.
createdOn | DateTime | Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde
description | String | Beschreibung dieser Korrekturaktivität
dueOn | DateTime | Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat
fixedDevices |  | Die Anzahl der Geräte, die behoben wurden
id | String | ID dieser Korrekturaktivität
nameId | String | Verwandter Produktname
priority | String | Priorität des Erstellers für diese Korrekturaktivität (Hoch\Mittel\Niedrig)
Productid | String | Verwandte Produkt-ID
productivityImpactRemediationType | String | Einige Konfigurationsänderungen können nur für Geräte ohne Auswirkungen auf den Benutzer angefordert werden. Dieser Wert gibt die Auswahl zwischen "alle verfügbar gemachten Geräte" oder "nur Geräte ohne Auswirkungen auf den Benutzer" an.
rbacGroupNames | String | Verwandte Gerätegruppennamen
recommendedProgram | String | Empfohlenes Programm für ein Upgrade auf
recommendedVendor | String | Empfohlener Anbieter für ein Upgrade auf
recommendedVersion | String | Empfohlene Version, auf die aktualisiert/aktualisiert werden soll
relatedComponent | String | Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)
requesterEmail | String | Creator-E-Mail-Adresse
requesterId | String | Creator-Objekt-ID
requesterNotes | String | Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat
Scid | String | SCID der zugehörigen Sicherheitsempfehlung
status | String | Wartungsaktivitätsstatus (aktiv/abgeschlossen)
statusLastModifiedOn | DateTime | Datum, an dem das Statusfeld aktualisiert wurde
targetDevices | Long | Anzahl der verfügbar gemachten Geräte, für die diese Korrektur gilt
title | String | Titel dieser Korrekturaktivität
type | String | Korrekturtyp
Vendorid | String | Name des zugehörigen Anbieters

## <a name="see-also"></a>Siehe auch

- [Erhalten einer Korrekturaktivität nach ID](get-remediation-one-activity.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Auflisten verfügbarer Geräte einer Korrekturaktivität](get-remediation-exposed-devices-activities.md)

- [Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
