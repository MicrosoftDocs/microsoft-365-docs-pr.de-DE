---
title: Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse in Microsoft 365 Defender
description: Schnelles Reagieren auf Bedrohungen und betroffene Ressourcen in den Abfrageergebnissen der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Maßnahmen ergreifen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932178"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Ergreifen von Maßnahmen für Abfrageergebnisse der erweiterten Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Mit leistungsstarken und umfassenden Aktionsoptionen können Sie schnell Bedrohungen eindää oder gefährdete Ressourcen, die Sie [bei](advanced-hunting-overview.md) der erweiterten Suche finden, adressieren. Mit diesen Optionen können Sie:

- Ausführen verschiedener Aktionen auf Geräten
- Quarantänedateien

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Um Aktionen über die erweiterte Suche ausführen zu können, benötigen Sie eine Rolle in Microsoft Defender for Endpoint mit Berechtigungen zum Übermitteln von Wartungsaktionen [auf Geräten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Wenn Sie keine Maßnahmen ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:

*Aktive Abhilfemaßnahmen > Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung von Abhilfemaßnahmen*

## <a name="take-various-actions-on-devices"></a>Ausführen verschiedener Aktionen auf Geräten
Sie können die folgenden Aktionen auf Geräten ausführen, die durch die `DeviceId` Spalte in Den Abfrageergebnissen identifiziert werden:

- Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich später bewegen
- Erfassen eines Untersuchungspakets, um forensische Informationen zu erhalten
- Führen Sie einen Antivirenscan aus, um Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates zu finden und zu entfernen.
- Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten
- Einschränken der Ausführung von Apps auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern

Weitere Informationen dazu, wie diese Reaktionsaktionen über Microsoft Defender for Endpoint ausgeführt werden, finden Sie [unter Antwortaktionen auf Geräten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Quarantänedateien
Sie können die *Quarantäneaktion* für Dateien bereitstellen, damit sie bei Auftreten automatisch unter Quarantäne gestellt werden. Wenn Sie diese Aktion auswählen, können Sie zwischen den folgenden Spalten auswählen, um zu identifizieren, welche Dateien in den Abfrageergebnissen isoliert werden sollen:

- `SHA1` - In den meisten erweiterten Tabellen für die Suche ist dies die SHA-1 der Datei, die von der aufgezeichneten Aktion betroffen war. Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.
- `InitiatingProcessSHA1` - In den meisten erweiterten Tabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion zuständig ist. Wenn beispielsweise ein untergeordneter Prozess gestartet wird, wäre dies der übergeordnete Prozess. 
- `SHA256` - Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.
- `InitiatingProcessSHA256` - Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.

Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie [unter Antwortaktionen für Dateien.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch Werte `DeviceId` als Gerätebezeichner enthalten.  

## <a name="take-action"></a>Ergreifen von Maßnahmen
Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie dann **"Aktionen ausführen" aus.** Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.

![Abbildung des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Überprüfen der ergriffenen Aktionen
Jede Aktion wird einzeln im [](mtp-action-center.md) Aktionscenter unter Dem Verlauf des Aktionscenters   >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history) Wechseln Sie zum Action Center, um den Status der einzelnen Aktionen zu überprüfen.
 
## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Übersicht über das Aktionscenter](mtp-action-center.md)
