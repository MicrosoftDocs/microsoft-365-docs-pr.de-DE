---
title: DeviceFileCertificateInfo-Tabelle im schema der erweiterten Suche
description: Informationen zum Signieren von Dateien finden Sie in der DeviceFileCertificateInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064383"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten. In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.

Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutige ID für das Gerät im Dienst |
| `DeviceName` | Zeichenfolge | Vollqualifizierter Domänenname (FQDN) des Geräts |
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
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
