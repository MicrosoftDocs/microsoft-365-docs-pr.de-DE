---
title: Fileprofile ()-Funktion im Advanced Hunting for Microsoft Threat Protection
description: Hier erfahren Sie, wie Sie mithilfe des Datei Profils () Informationen zu Dateien in ihren erweiterten Suchabfrageergebnissen bereichern.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Datei Profil, Datei Profil, Funktion, Bereicherung
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
ms.openlocfilehash: e99e545b5578b5eff8c19345dc672f735e4f7bd2
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430585"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Die `FileProfile()` Funktion ist eine Anreicherungs Funktion in [Advanced Hunting](advanced-hunting-overview.md) , die die folgenden Daten zu Dateien hinzufügt, die von der Abfrage gefunden wurden.

| Spalte | Datentyp | Beschreibung |
|------------|-------------|-------------|
| SHA1 | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| SHA256 | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| MD5 | string | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| FileSize | int | Größe der Datei in Bytes |
| GlobalPrevalence | int | Anzahl der Instanzen der Entität, die von Microsoft Global beobachtet wurden |
| GlobalFirstSeen | Datum/Uhrzeit | Datum und Uhrzeit, zu der die Entität erstmals von Microsoft Global beobachtet wurde |
| GlobalLastSeen | Datum/Uhrzeit | Datum und Uhrzeit, zu der die Entität zuletzt von Microsoft Global beobachtet wurde |
| Signierers | string | Informationen über den unterschreibenden der Datei |
| Aussteller | string | Informationen zur ausstellenden Zertifizierungsstelle (Certification Authority, ca) |
| SignerHash | string | Eindeutiger Hashwert zur Identifizierung der signierenden |
| IsCertificateValid | Boolescher Wert | Gibt an, ob das zum Signieren der Datei verwendete Zertifikat gültig ist. |
| IsRootSignerMicrosoft | Boolescher Wert | Gibt an, ob die Signatur des Stammzertifikats Microsoft lautet. |
| IsExecutable | Boolescher Wert | Gibt an, ob es sich bei der Datei um eine PE-Datei (Portable Executable) handelt |
| Bedrohungsname | string | Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen |
| Publisher | string | Name der Organisation, die die Datei veröffentlicht hat |
| Software Name | string | Name des Softwareprodukts |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumente

- **x**– zu verwendende Datei-ID-Spalte: `SHA1` , `SHA256` , `InitiatingProcessSHA1` , oder `InitiatingProcessSHA256` ; Funktion verwendet, `SHA1` Wenn nicht angegeben
- **y**– Grenzwert für die Anzahl der zu bereichenden Datensätze, 1-1000; Funktion verwendet 100, wenn nicht angegeben

## <a name="examples"></a>Beispiele

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projizieren Sie nur die SHA1-Spalte und bereichern Sie Sie

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Bereichern der ersten 500-Datensätze und Auflisten von Dateien mit niedriger Prävalenz

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
- [Abrufen weiterer Abfragebeispiele](advanced-hunting-shared-queries.md)
