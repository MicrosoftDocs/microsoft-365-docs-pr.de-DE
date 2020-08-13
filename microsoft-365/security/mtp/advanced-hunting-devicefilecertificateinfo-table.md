---
title: DeviceFileCertificateInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Datei Signierungsinformationen in der DeviceFileCertificateInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, digitale Signatur, Zertifikat, Dateisignierung, DeviceFileCertificateInfo
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 33f9c726839f17afbb935c6d028cc4eaa5b74843
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649451"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Gilt für:**
- Microsoft Threat Protection

Die `DeviceFileCertificateInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Dateisignatur Zertifikaten. In dieser Tabelle werden Daten verwendet, die aus Zertifikat Überprüfungsaktivitäten regelmäßig für Dateien auf Endpunkten ausgeführt wurden.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `IsSigned` | Boolescher Wert | Gibt an, ob die Datei signiert ist |
| `SignatureType` | string | Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden. |
| `Signer` | string | Informationen über den unterschreibenden der Datei |
| `SignerHash` | string | Eindeutiger Hashwert zur Identifizierung der signierenden |
| `Issuer` | string | Informationen zur ausstellenden Zertifizierungsstelle (Certification Authority, ca) |
| `IssuerHash` | string | Eindeutiger Hashwert zur Identifizierung der ausstellenden Zertifizierungsstelle (Certification Authority, ca) |
| `CertificateSerialNumber` | string | Bezeichner für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist |
| `CrlDistributionPointUrls` | string |  JSON-Array, das die URLs von Netzwerkfreigaben auflistet, die Zertifikate und Zertifikatsperrlisten enthalten |
| `CertificateCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit der Erstellung des Zertifikats |
| `CertificateExpirationTime` | Datum/Uhrzeit | Datum und Uhrzeit des Ablaufs des Zertifikats festgelegt |
| `CertificateCountersignatureTime` | Datum/Uhrzeit | Datum und Uhrzeit der Gegenzeichnung des Zertifikats |
| `IsTrusted` | Boolescher Wert | Gibt an, ob die Datei vertrauenswürdig ist, basierend auf den Ergebnissen der WinVerifyTrust-Funktion, die nach unbekannten Stammzertifikat Informationen, ungültigen Signaturen, gesperrten Zertifikaten und anderen fragwürdigen Attributen sucht. |
| `IsRootSignerMicrosoft` | Boolescher Wert | Gibt an, ob die Signatur des Stammzertifikats Microsoft lautet. |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Zum Identifizieren eindeutiger Ereignisse muss diese Spalte zusammen mit den Spalten DeviceName und Timestamp verwendet werden. | 

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Jagd auf Geräte, e-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
