---
title: Tabelle "DeviceFileCertificateInfo" im Schema "Erweiterte Suche"
description: Informationen zum Signieren von Dateien in der Tabelle "DeviceFileCertificateInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, digitale Signatur, Zertifikat, Dateisignierung, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931314"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte `DeviceFileCertificateInfo` [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten. In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `IsSigned` | Boolescher Wert | Gibt an, ob die Datei signiert ist |
| `SignatureType` | string | Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst oder aus einer externen Katalogdatei gelesen wurden. |
| `Signer` | string | Informationen zum Signier der Datei |
| `SignerHash` | string | Eindeutiger Hashwert, der den Signier identifiziert |
| `Issuer` | string | Informationen zur ausstellenden Zertifizierungsstelle |
| `IssuerHash` | string | Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle identifiziert |
| `CertificateSerialNumber` | string | Bezeichner für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist |
| `CrlDistributionPointUrls` | string |  JSON-Array, das die URLs von Netzwerkfreigaben auflistet, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten |
| `CertificateCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit der Zertifikatserg nkung |
| `CertificateExpirationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Ablaufs des Zertifikats |
| `CertificateCountersignatureTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem und zu der das Zertifikat gegensigniert wurde |
| `IsTrusted` | Boolescher Wert | Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust -Funktion vertrauenswürdig ist, die auf unbekannte Stammzertifikatinformationen, ungültige Signaturen, gesperrte Zertifikate und andere fragwürdige Attribute überprüft. |
| `IsRootSignerMicrosoft` | Boolescher Wert | Gibt an, ob der Signer des Stammzertifikats Microsoft ist. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. | 

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
