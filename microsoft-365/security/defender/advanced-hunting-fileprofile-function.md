---
title: FileProfile()-Funktion bei der erweiterten Suche für Microsoft 365 Defender
description: Erfahren Sie, wie Sie FileProfile() zum Anreichern von Informationen zu Dateien in Ihren erweiterten Suchergebnissen verwenden.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Bereicherung
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
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062080"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `FileProfile()` Funktion ist eine Anreicherungsfunktion bei der erweiterten [Suche,](advanced-hunting-overview.md) die dateien, die von der Abfrage gefunden werden, die folgenden Daten hinzufügt.

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| SHA1 | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| SHA256 | Zeichenfolge | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| MD5 | Zeichenfolge | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| FileSize | int | Größe der Datei in Bytes |
| GlobalPrevalence | int | Anzahl der Instanzen der Entität, die von Microsoft global beobachtet werden |
| GlobalFirstSeen | Datum/Uhrzeit | Datum und Uhrzeit, zu dem die Entität erstmals von Microsoft global beobachtet wurde |
| GlobalLastSeen | Datum/Uhrzeit | Datum und Uhrzeit, zu dem die Entität zuletzt von Microsoft global beobachtet wurde |
| Signer | Zeichenfolge | Informationen zum Signier der Datei |
| Aussteller | Zeichenfolge | Informationen zur ausstellenden Zertifizierungsstelle |
| SignerHash | Zeichenfolge | Eindeutiger Hashwert, der den Signier identifiziert |
| IsCertificateValid | boolean | Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist |
| IsRootSignerMicrosoft | boolean | Gibt an, ob der Signier des Stammzertifikats Microsoft ist |
| IsExecutable | boolean | Gibt an, ob es sich bei der Datei um eine portable ausführbare Datei (Portable Executable, PE) handelt |
| ThreatName | Zeichenfolge | Erkennungsname für gefundene Schadsoftware oder andere Bedrohungen |
| Publisher | Zeichenfolge | Name der Organisation, die die Datei veröffentlicht hat |
| SoftwareName | string | Name des Softwareprodukts |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumente

- **x**–Datei-ID-Spalte, die verwendet werden soll: , , , oder ; -Funktion wird `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` verwendet, wenn nicht angegeben
- **y**– Grenzwert für die Anzahl der datensätze, die bereichert werden müssen, 1-1000; -Funktion verwendet 100, wenn nicht angegeben


>[!TIP]
> Anreicherungsfunktionen zeigen ergänzende Informationen nur an, wenn sie verfügbar sind. Die Verfügbarkeit von Informationen ist unterschiedlich und hängt von vielen Faktoren ab. Achten Sie darauf, dies bei der Verwendung von FileProfile() in Ihren Abfragen oder beim Erstellen benutzerdefinierter Erkennungen zu berücksichtigen. Für optimale Ergebnisse empfehlen wir die Verwendung der FileProfile()-Funktion mit SHA1.

## <a name="examples"></a>Beispiele

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Nur die SPALTE "SHA1" projekt- und bereichern

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Anreichern der ersten 500 Datensätze und Auflisten von Dateien mit niedriger Verbreitung

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Weitere Abfragebeispiele erhalten](advanced-hunting-shared-queries.md)
