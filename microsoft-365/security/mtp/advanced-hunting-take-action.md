---
title: Ausführen von Aktionen für erweiterte Jagd Abfrageergebnisse im Microsoft Threat Protection
description: Schnelles Adressieren von Bedrohungen und betroffenen Objekten in den Suchergebnissen der erweiterten Suche
keywords: Erweiterte Jagd, Bedrohungs Suche, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Take Action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429653"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Aktionen für erweiterte Jagd Abfrageergebnisse ausführen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Sie können schnell Bedrohungen enthalten oder gefährdete Objekte, die Sie in [Advanced Hunting](advanced-hunting-overview.md) finden, mit leistungsstarken und umfassenden Aktionsoptionen befassen. Mit diesen Optionen können Sie Folgendes tun:

- Ausführen verschiedener Aktionen auf Geräten
- Quarantänedateien

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Um durch die erweiterte Suche Aktionen durchführen zu können, benötigen Sie eine Rolle in Microsoft Defender ATP mit [Berechtigungen zum Übermitteln von Korrekturaktionen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Wenn Sie keine Aktion ausführen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:

*Aktive Korrekturaktionen > Threat and Vulnerability Management – Korrektur Behandlung*

## <a name="take-various-actions-on-devices"></a>Ausführen verschiedener Aktionen auf Geräten
Sie können die folgenden Aktionen auf Geräten durchführen, die von der `DeviceId` Spalte in den Abfrageergebnissen identifiziert werden:

- Isolieren der betroffenen Geräte für eine Infektion oder verhindern, dass Angriffe seitlich verschoben werden
- Ermittlungs Paket sammeln, um mehr forensische Informationen zu erhalten
- Ausführen eines Antivirus-Scans zum Auffinden und Entfernen von Bedrohungen mithilfe der neuesten Security Intelligence-Updates
- Initiieren einer automatisierten Untersuchung zum Überprüfen und Beheben von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten
- Einschränken der APP-Ausführung auf nur von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungen durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern

Wenn Sie mehr darüber erfahren möchten, wie diese Reaktions Aktionen über Microsoft Defender ATP durchgeführt werden, [Lesen Sie Informationen zu Antwort Aktionen auf Geräten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Quarantänedateien
Sie können die *Quarantäne* -Aktion für Dateien bereitstellen, damit Sie automatisch isoliert werden, wenn Sie auftreten. Wenn Sie diese Aktion auswählen, können Sie zwischen den folgenden Spalten wählen, um zu ermitteln, welche Dateien in der Abfrage zu Quarantäne gehören:

- `SHA1` — In den meisten erweiterten Jagd Tabellen ist dies der SHA-1 der Datei, der von der aufgezeichneten Aktion betroffen war. Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.
- `InitiatingProcessSHA1` — In den meisten erweiterten Jagd Tabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion zuständig ist. Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess. 
- `SHA256` – Dies ist das SHA-256-Äquivalent der Datei, die durch die Spalte identifiziert wird `SHA1` .
- `InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der Datei, die durch die Spalte identifiziert wird `InitiatingProcessSHA1` .

Weitere Informationen zur Verwendung von Quarantäneaktionen und zur Wiederherstellung von Dateien finden [Sie unter Informationen zu Antwort Aktionen für Dateien](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Um Dateien zu finden und zu isolieren, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.  

## <a name="take-action"></a>Aktion ausführen
Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie dann **Take Actions**aus. Ein Assistent führt Sie durch den Prozess des Auswählens und dann übermitteln Ihrer bevorzugten Aktionen.

![Bild des ausgewählten Datensatzes mit dem Bereich für die Überprüfung des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Überprüfen der ausgeführten Aktionen
Jede Aktion wird einzeln im [Action Center](mtp-action-center.md) unter dem Security.Microsoft.com/Action-Center/History ( **Action Center**  >  **History** ) aufgezeichnet.[security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history) Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.
 
## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Übersicht über das Aktionscenter](mtp-action-center.md)
