---
title: FileProfile()-Funktion bei der erweiterten Suche nach Microsoft 365 Defender
description: Erfahren Sie, wie Sie FileProfile() verwenden, um Informationen zu Dateien in den Abfrageergebnissen für die erweiterte Suche zu erweitern.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, FileProfile, Dateiprofil, Funktion, Anreicherung
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929550"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `FileProfile()` Funktion ist eine Anreicherungsfunktion bei der erweiterten [Suche,](advanced-hunting-overview.md) die den von der Abfrage gefundenen Dateien die folgenden Daten hinzufügt.

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| SHA1 | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| SHA256 | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| MD5 | string | #A0 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| FileSize | int | Größe der Datei in Byte |
| GlobalPrevalence | int | Anzahl der Instanzen der Entität, die von Microsoft global beobachtet werden |
| GlobalFirstSeen | Datum/Uhrzeit | Datum und Uhrzeit der ersten globalen Beobachtung der Entität durch Microsoft |
| GlobalLastSeen | Datum/Uhrzeit | Datum und Uhrzeit der letzten globalen Beobachtung der Entität durch Microsoft |
| Signer | string | Informationen zum Signier der Datei |
| Aussteller | string | Informationen zur ausstellenden Zertifizierungsstelle |
| SignerHash | string | Eindeutiger Hashwert, der den Signier identifiziert |
| IsCertificateValid | Boolescher Wert | Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist. |
| IsRootSignerMicrosoft | Boolescher Wert | Gibt an, ob der Signier des Stammzertifikats Microsoft ist. |
| IsExecutable | Boolescher Wert | Gibt an, ob es sich bei der Datei um eine portable ausführbare Datei (Portable Executable, PE) handelt. |
| ThreatName | string | Erkennungsname für schadsoftware- oder andere gefundene Bedrohungen |
| Publisher | string | Name der Organisation, die die Datei veröffentlicht hat |
| SoftwareName | string | Name des Softwareprodukts |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumente

- **x**– zu verwendende Datei-ID-Spalte: , , oder ; Wird bei nicht `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` angegebener Funktion verwendet
- **y**– Grenzwert für die Anzahl der datensätze, die anreichert werden soll, 1-1000; funktion verwendet 100, wenn nicht angegeben

## <a name="examples"></a>Beispiele

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Nur die Spalte "SHA1" projekten und erweitern

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Anreichern der ersten 500 Datensätze und Listendateien mit niedriger Verbreitung

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
