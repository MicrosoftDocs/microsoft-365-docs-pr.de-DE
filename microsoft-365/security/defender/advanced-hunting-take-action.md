---
title: Ergreifen von Maßnahmen für erweiterte Suchergebnisse in Microsoft 365 Defender
description: Schnelles Adressieren von Bedrohungen und betroffenen Ressourcen in ihren erweiterten Suchergebnissen
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Maßnahmen ergreifen
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4c90441bb7a492ac38c5fcb560d9246b3a0005b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064727"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Mithilfe leistungsstarker und umfassender Aktionsoptionen können [](advanced-hunting-overview.md) Sie schnell Bedrohungen oder gefährdete Ressourcen in der erweiterten Suche enthalten. Mit diesen Optionen können Sie:

- Ausführen verschiedener Aktionen auf Geräten
- Quarantänedateien

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Um maßnahmen über die erweiterte Suche ergreifen zu können, benötigen Sie eine Rolle in Microsoft Defender for Endpoint mit Berechtigungen zum Übermitteln von Korrekturaktionen [auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Wenn Sie keine Aktion ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:

*Aktive Abhilfemaßnahmen > Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung von Abhilfemaßnahmen*

## <a name="take-various-actions-on-devices"></a>Ausführen verschiedener Aktionen auf Geräten
Sie können die folgenden Aktionen auf Geräten ausführen, die von der `DeviceId` Spalte in Den Abfrageergebnissen identifiziert werden:

- Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich lateral bewegen
- Sammeln von Untersuchungspaketen, um weitere forensische Informationen zu erhalten
- Ausführen einer Antivirenscan zum Suchen und Entfernen von Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates
- Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten
- Beschränken der App-Ausführung auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern

Weitere Informationen dazu, wie diese Reaktionsaktionen über Microsoft Defender for Endpoint ausgeführt werden, finden Sie [unter Reaktionsaktionen auf Geräten.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Quarantänedateien
Sie können die *Quarantäneaktion* für Dateien bereitstellen, sodass sie bei Auftreten automatisch isoliert werden. Beim Auswählen dieser Aktion können Sie zwischen den folgenden Spalten auswählen, um zu bestimmen, welche Dateien in Ihren Abfrageergebnissen isoliert werden sollen:

- `SHA1` – In den meisten erweiterten Nachsuchetabellen ist dies sha-1 der Datei, die von der aufgezeichneten Aktion betroffen war. Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.
- `InitiatingProcessSHA1` – In den meisten erweiterten Nachsuchetabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion verantwortlich ist. Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess. 
- `SHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.
- `InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.

Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie unter [Reaktionsaktionen für Dateien](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.  

## <a name="take-action"></a>Maßnahmen ergreifen
Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie **dann Aktionen ausführen aus.** Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Überprüfen der ergriffenen Aktionen
Jede Aktion wird einzeln im [](m365d-action-center.md) Aktionscenter unter **Aktionscenterverlauf**  >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history) Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.
 
## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Übersicht über das Aktionscenter](m365d-action-center.md)
