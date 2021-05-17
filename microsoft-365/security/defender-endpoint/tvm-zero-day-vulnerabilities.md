---
title: Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikomanagement
description: Erfahren Sie, wie Sie Zero-Day-Sicherheitsrisiken in Ihrer Umgebung mithilfe von Bedrohungs- und Sicherheitsrisikomanagement.
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities, tvm, threat & Sicherheitsrisikomanagement, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be508e646a67f01887814a0e72170e438ee86212
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933061"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Eine Zero-Day-Sicherheitslücke ist eine öffentlich offengelegte Sicherheitslücke, für die keine offiziellen Patches oder Sicherheitsupdates veröffentlicht wurden. Zero-Day-Sicherheitsrisiken haben häufig einen hohen Schweregrad und werden aktiv ausgenutzt.

Bedrohungen und Sicherheitsrisikomanagement zeigen nur Zero-Day-Sicherheitsrisiken an, über die informationen enthalten sind.

## <a name="find-information-about-zero-day-vulnerabilities"></a>Informationen zu Zero-Day-Sicherheitsrisiken finden

Sobald eine Zero-Day-Sicherheitslücke gefunden wurde, werden Informationen dazu über die folgenden Erfahrungen in der Microsoft Defender Security Center.

### <a name="threat-and-vulnerability-management-dashboard"></a>Bedrohung und Sicherheitsrisikomanagement Dashboard

Suchen Sie auf der Karte "Top security recommendations" nach Empfehlungen mit einem Zero-Day-Tag.

![Die besten Empfehlungen mit einem Zero-Day-Tag.](images/tvm-zero-day-top-security-recommendations.png)

Suchen Sie auf der Karte "Besonders anfällige Software" nach Top-Software mit dem Tag "Zero-Day".

![Besonders anfällige Software mit einem Zero-Day-Tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>Seite "Schwächen"

Suchen Sie nach der benannten Zero-Day-Sicherheitslücke zusammen mit einer Beschreibung und Details.

- Wenn dieser Sicherheitsanfälligkeit eine CVE-ID zugewiesen ist, wird neben dem CVE-Namen die Zero-Day-Bezeichnung angezeigt.

- Wenn dieser Sicherheitsanfälligkeit keine CVE-ID zugewiesen ist, finden Sie sie unter einem internen, temporären Namen, der wie "TVM-XXXX-XXXX" aussieht. Der Name wird aktualisiert, sobald eine offizielle CVE-ID zugewiesen wurde, aber der vorherige interne Name ist weiterhin durchsuchbar und wird im Seitenbereich gefunden.

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>Seite "Softwareinventar"

Suchen Sie nach Software mit dem Zero-Day-Tag. Filtern Sie nach dem Tag "Zero Day", um nur Software mit Zero-Day-Sicherheitsrisiken zu sehen.

![Zero day example of Windows Server 2016 in the software inventory page.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>Softwareseite

Suchen Sie nach einem Zero-Day-Tag für jede Software, die von der Zero-Day-Sicherheitslücke betroffen ist.

![Zero day example for Windows Server 2016 software page.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>Seite mit Sicherheitsempfehlungen

Zeigen Sie klare Vorschläge zu Korrektur- und Abhilfemaßnahmen an, einschließlich Problemumgehungen, falls vorhanden. Filtern Sie nach dem Tag "Zero Day", um nur Sicherheitsempfehlungen zur Behandlung von Zero-Day-Sicherheitsrisiken zu sehen.

Wenn Software mit einer Zero-Day-Sicherheitslücke und zusätzlichen Sicherheitsrisiken zur Verfügung steht, erhalten Sie eine Empfehlung zu allen Sicherheitsrisiken.

![Zero day example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>Behebung von Zero-Day-Sicherheitsrisiken

Wechseln Sie zur Seite Sicherheitsempfehlung, und wählen Sie eine Empfehlung mit einem Nulltag aus. Ein Flyout wird mit Informationen zu den Zero-Day- und anderen Sicherheitsrisiken für diese Software geöffnet.

Es gibt einen Link zu Abhilfemaßnahmen und Problemumgehungen, wenn diese verfügbar sind. Problemumgehungen können dazu beitragen, das Risiko dieser Zero-Day-Sicherheitslücke zu verringern, bis ein Patch oder Sicherheitsupdate bereitgestellt werden kann.

Öffnen Sie Korrekturoptionen, und wählen Sie den Aufmerksamkeitstyp aus. Für die Zero-Day-Sicherheitsrisiken wird eine Option zur Behebung von "Aufmerksamkeit erforderlich" empfohlen, da ein Update noch nicht veröffentlicht wurde. Sie können kein Fälligkeitsdatum auswählen, da keine bestimmte Aktion durchzuführen ist. Wenn ältere Sicherheitsrisiken für diese Software vorhanden sind, die Sie bereinigungen möchten, können Sie die Option "Aufmerksamkeit erforderlich" außer Kraft setzen und "aktualisieren" auswählen.

![Flyoutbeispiel für zero day Windows Server 2016 auf der Seite sicherheitsempfehlungen.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>Nachverfolgen von Zero-Day-Korrekturaktivitäten

Wechseln Sie zur seite [Bedrohungs- und Sicherheitsrisikomanagement,](tvm-remediation.md) um das Problembehebungsaktivitätselement zu sehen. Wenn Sie die Option "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da es keine tatsächliche Aktion gibt, die wir überwachen können. Sie können nach Behebungstyp filtern, z. B. "Softwareupdate" oder "Aufmerksamkeit erforderlich", um alle Aktivitätselemente in derselben Kategorie zu sehen.

## <a name="patching-zero-day-vulnerabilities"></a>Patchen von Zero-Day-Sicherheitsrisiken

Wenn ein Patch für den Nulltag freigegeben wird, wird die Empfehlung in "Update" und eine blaue Beschriftung daneben mit der Bezeichnung "Neues Sicherheitsupdate für null Tag" geändert. Es wird nicht mehr als Zero-Day-Tag in Betracht ziehen, das Zero-Day-Tag wird von allen Seiten entfernt.

![Empfehlung für "Update Microsoft Windows 10" mit neuer Patchbeschriftung.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
- [Softwarebestand](tvm-software-inventory.md)
- [Sicherheitsrisiken in meiner Organisation](tvm-weaknesses.md)
