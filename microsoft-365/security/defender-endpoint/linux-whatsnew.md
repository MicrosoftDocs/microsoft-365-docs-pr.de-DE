---
title: Neues in Microsoft Defender for Endpoint unter Linux
description: Liste der wichtigsten Änderungen für Microsoft Defender for Endpoint unter Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 999463f92c014e061bc4e2fdc22eedcd8f680a72
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903814"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Neues in Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender for Endpoint unter Linux ist jetzt in der Vorschau für Us Government-Kunden verfügbar. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Es wurde ein Problem behoben, bei dem die Verwendung von Microsoft Defender for Endpoint unter Linux auf Systemen mit DENOE-Dateisystemen dazu führte, dass das Betriebssystem hängte.
- Leistungsverbesserungen & anderen Fehlerbehebungen

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird. Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet. Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.
- Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können. Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`
- Weitere Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011853"></a>101.18.53

- EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )
- Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011299"></a>101.12.99

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010476"></a>101.04.76

- Fehlerbehebungen

## <a name="1010348"></a>101.03.48

- Fehlerbehebungen

## <a name="1010255"></a>101.02.55

- Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.
- Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden

## <a name="1010075"></a>101.00.75

- Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`
- Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen. Dies liegt an einer wesentlichen Änderung in einem Dateipfad. Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets. Dieses Problem ist in neueren Versionen nicht vorhanden.

- [Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)
- Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.
- Verbesserungen, um die Paketinstallation robuster zu machen
- Leistungsverbesserungen & Fehlerbehebungen
