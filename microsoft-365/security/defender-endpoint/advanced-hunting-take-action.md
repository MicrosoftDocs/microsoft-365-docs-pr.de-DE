---
title: Ergreifen von Maßnahmen zu erweiterten Suchabfrageergebnissen in Microsoft Threat Protection
description: Schnelles Adressieren von Bedrohungen und betroffenen Ressourcen in ihren erweiterten Suchergebnissen
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500532"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Ergreifen von Maßnahmen für erweiterte Suchabfrageergebnisse

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Mithilfe leistungsstarker und umfassender Aktionsoptionen können [](advanced-hunting-overview.md) Sie schnell Bedrohungen oder gefährdete Ressourcen in der erweiterten Suche enthalten. Mit diesen Optionen können Sie:

- Ausführen verschiedener Aktionen auf Geräten
- Quarantänedateien

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um über erweiterte Suche Maßnahmen ergreifen zu können, benötigen Sie eine Rolle in Defender for Endpoint mit Berechtigungen zum Übermitteln von Korrekturaktionen [auf Geräten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options) Wenn Sie keine Aktion ergreifen können, wenden Sie sich an einen globalen Administrator, um die folgende Berechtigung zu erhalten:

*Aktive Abhilfemaßnahmen > Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung von Abhilfemaßnahmen*

## <a name="take-various-actions-on-devices"></a>Ausführen verschiedener Aktionen auf Geräten

Sie können die folgenden Aktionen auf Geräten ausführen, die von der `DeviceId` Spalte in den Abfrageergebnissen identifiziert werden:

- Isolieren betroffener Geräte, um eine Infektion zu enthalten oder zu verhindern, dass Angriffe sich lateral bewegen
- Sammeln von Untersuchungspaketen, um weitere forensische Informationen zu erhalten
- Ausführen einer Antivirenscan zum Suchen und Entfernen von Bedrohungen mithilfe der neuesten Sicherheitsintelligenzupdates
- Initiieren einer automatisierten Untersuchung zur Überprüfung und Behebung von Bedrohungen auf dem Gerät und möglicherweise anderen betroffenen Geräten
- Beschränken der App-Ausführung auf von Microsoft signierte ausführbare Dateien, um nachfolgende Bedrohungsaktivitäten durch Schadsoftware oder andere nicht vertrauenswürdige ausführbare Dateien zu verhindern

Weitere Informationen dazu, wie diese Reaktionsaktionen über Defender for Endpoint ausgeführt werden, finden Sie [unter Reaktionsaktionen auf Geräten.](respond-machine-alerts.md)

## <a name="quarantine-files"></a>Quarantänedateien

Sie können die *Quarantäneaktion* für Dateien bereitstellen, sodass sie bei Auftreten automatisch isoliert werden. Beim Auswählen dieser Aktion können Sie zwischen den folgenden Spalten auswählen, um zu bestimmen, welche Dateien in Ihren Abfrageergebnissen isoliert werden sollen:

- `SHA1` – In den meisten erweiterten Nachsuchetabellen ist dies sha-1 der Datei, die von der aufgezeichneten Aktion betroffen war. Wenn beispielsweise eine Datei kopiert wurde, wäre dies die kopierte Datei.
- `InitiatingProcessSHA1` – In den meisten erweiterten Nachsuchetabellen ist dies die Datei, die für das Initiieren der aufgezeichneten Aktion verantwortlich ist. Wenn beispielsweise ein untergeordneter Prozess gestartet wurde, wäre dies der übergeordnete Prozess. 
- `SHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `SHA1` Datei.
- `InitiatingProcessSHA256` – Dies ist das SHA-256-Äquivalent der durch die Spalte identifizierten `InitiatingProcessSHA1` Datei.

Weitere Informationen dazu, wie Quarantäneaktionen ergriffen werden und wie Dateien wiederhergestellt werden können, finden Sie unter [Reaktionsaktionen für Dateien](respond-file-alerts.md).

>[!NOTE]
>Um Dateien zu suchen und unter Quarantäne zu stellen, sollten die Abfrageergebnisse auch `DeviceId` Werte als Gerätebezeichner enthalten.  

## <a name="take-action"></a>Maßnahmen ergreifen

Wenn Sie eine der beschriebenen Aktionen ausführen möchten, wählen Sie einen oder mehrere Datensätze in den Abfrageergebnissen aus, und wählen Sie **dann Aktionen ausführen aus.** Ein Assistent führt Sie durch den Prozess der Auswahl und anschließenden Übermittlung Ihrer bevorzugten Aktionen.

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Überprüfen der ergriffenen Aktionen

Jede Aktion wird einzeln im Aktionscenter unter **Aktionscenterverlauf**  >   ( security.microsoft.com/action-center/history )[aufgezeichnet.](https://security.microsoft.com/action-center/history) Wechseln Sie zum Aktionscenter, um den Status der einzelnen Aktionen zu überprüfen.
 
## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
