---
title: DeviceFileEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu dateibezogenen Ereignissen in der DeviceFileEvents-Tabelle des schemas für erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, filecreationevents, DeviceFileEvents, files, path, hash, sha1, sha256, md5
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
ms.openlocfilehash: 10009edab33d04ca01da9459c394634d0622cf3d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063543"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die `DeviceFileEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zur Dateierstellung, -änderung und anderen Dateisystemereignissen. Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MD5` | string | MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileOriginUrl` | Zeichenfolge | URL, von der die Datei heruntergeladen wurde |
| `FileOriginReferrerUrl` | Zeichenfolge | URL der Webseite, die mit der heruntergeladenen Datei verknüpft ist |
| `FileOriginIP` | Zeichenfolge | IP-Adresse, von der die Datei heruntergeladen wurde |
| `PreviousFolderPath` | Zeichenfolge | Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde |
| `PreviousFileName` | Zeichenfolge | Ursprünglicher Name der Datei, die als Ergebnis der Aktion umbenannt wurde |
| `FileSize` | long | Größe der Datei in Bytes |
| `InitiatingProcessAccountDomain` | Zeichenfolge | Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war |
| `InitiatingProcessAccountName` | Zeichenfolge | Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte |
| `InitiatingProcessAccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessAccountUpn` | Zeichenfolge | Benutzerprinzipalname (UPN) des Kontos, das den für das Ereignis verantwortlichen Prozess führte |
| `InitiatingProcessMD5` | Zeichenfolge | MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA1` | Zeichenfolge | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | Zeichenfolge | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFolderPath` | string | Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | Zeichenfolge | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | Zeichenfolge | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessIntegrityLevel` | Zeichenfolge | Integritätsebene des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | Zeichenfolge | Tokentyp, der angibt, ob die Berechtigungserweiterung für die Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war, |
| `InitiatingProcessParentFileName` | Zeichenfolge | Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `RequestProtocol` | Zeichenfolge | Netzwerkprotokoll, das ggf. zum Initiieren der Aktivität verwendet wird: Unbekannt, Lokal, SMB oder NFS |
| `ShareName` | Zeichenfolge | Name des freigegebenen Ordners, der die Datei enthält |
| `RequestSourceIP` | Zeichenfolge | IPv4- oder IPv6-Adresse des Remotegeräts, das die Aktivität initiiert hat |
| `RequestSourcePort` | Zeichenfolge | Quellport auf dem Remotegerät, das die Aktivität initiiert hat |
| `RequestAccountName` | Zeichenfolge | Benutzername des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `RequestAccountDomain` | Zeichenfolge | Domäne des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `RequestAccountSid` | Zeichenfolge | Security Identifier (SID) des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden. |
| `AppGuardContainerId` | Zeichenfolge | Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird |
| `AdditionalFields` | Zeichenfolge | Zusätzliche Informationen zur Entität oder zum Ereignis |
| `InitiatingProcessFileSize` | long | Größe der Datei, die den prozessverantwortlichen Vorgang für das Ereignis führte |
| `SensitivityLabel` | Zeichenfolge | Bezeichnung, die auf E-Mails, Dateien oder andere Inhalte angewendet wird, um sie zum Schutz von Informationen zu klassifizieren |
| `SensitivitySubLabel` | Zeichenfolge | Sublabel, das auf eine E-Mail, Datei oder andere Inhalte angewendet wird, um sie zum Schutz von Informationen zu klassifizieren; Vertraulichkeitsunterbezeichnungen werden unter Vertraulichkeitsbezeichnungen gruppieren, aber unabhängig behandelt |
| `IsAzureInfoProtectionApplied` | boolean | Gibt an, ob die Datei von Azure Information Protection verschlüsselt wird |

>[!NOTE]
> Dateihashinformationen werden immer angezeigt, wenn sie verfügbar sind. Es gibt jedoch mehrere mögliche Gründe, warum ein SHA1, SHA256 oder MD5 nicht berechnet werden kann. Die Datei kann sich beispielsweise im Remotespeicher befinden, durch einen anderen Prozess gesperrt, komprimiert oder als virtuell markiert sein. In diesen Szenarien werden die Dateihashinformationen leer angezeigt.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
