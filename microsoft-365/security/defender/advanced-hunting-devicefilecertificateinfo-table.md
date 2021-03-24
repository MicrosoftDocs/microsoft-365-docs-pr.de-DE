---
title: DeviceFileCertificateInfo-Tabelle im schema der erweiterten Suche
description: Informationen zum Signieren von Dateien finden Sie in der DeviceFileCertificateInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063536"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten. In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `IsSigned` | boolean | Gibt an, ob die Datei signiert ist |
| `SignatureType` | Zeichenfolge | Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden |
| `Signer` | Zeichenfolge | Informationen zum Signier der Datei |
| `SignerHash` | Zeichenfolge | Eindeutiger Hashwert, der den Signier identifiziert |
| `Issuer` | Zeichenfolge | Informationen zur ausstellenden Zertifizierungsstelle |
| `IssuerHash` | Zeichenfolge | Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle (Ca) identifiziert |
| `CertificateSerialNumber` | Zeichenfolge | Id für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist |
| `CrlDistributionPointUrls` | Zeichenfolge |  JSON-Array mit den URLs von Netzwerkfreigaben, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten |
| `CertificateCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das Zertifikat erstellt wurde |
| `CertificateExpirationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Ablaufs des Zertifikats |
| `CertificateCountersignatureTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das Zertifikat gegensigniert wurde |
| `IsTrusted` | boolean | Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust-Funktion vertrauenswürdig ist, die nach unbekannten Stammzertifikatinformationen, ungültigen Signaturen, widerrufenen Zertifikaten und anderen fragwürdigen Attributen sucht. |
| `IsRootSignerMicrosoft` | boolean | Gibt an, ob der Signier des Stammzertifikats Microsoft ist |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. | 

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
