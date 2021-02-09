---
title: Tabelle "DeviceFileEvents" im Schema "Erweiterte Suche"
description: Informationen zu dateibezogenen Ereignissen in der Tabelle "DeviceFileEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, Dateierstellenevents, DeviceFileEvents, Dateien, Pfad, Hash, sha1, sha256, md5
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
ms.openlocfilehash: cccbd268c8f69d6623df1ef4c8208d20ead2e9f5
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145295"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Die Tabelle im Schema für die erweiterte Suche enthält Informationen zum Erstellen, Ändern und `DeviceFileEvents` anderen Dateisystemereignissen. [](advanced-hunting-overview.md) Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.

>[!TIP]
> Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).

| Spaltenname | Datentyp | Beschreibung |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum und Uhrzeit der Aufzeichnung des Ereignisses |
| `DeviceId` | string | Eindeutiger Bezeichner für den Computer im Dienst |
| `DeviceName` | string | Vollqualifizierter Domänenname (FQDN) des Computers |
| `ActionType` | string | Typ der Aktivität, die das Ereignis ausgelöst hat. Details finden Sie in der [In-Portal-Schemareferenz.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FolderPath` | string | Ordner mit der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA1` | string | SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `SHA256` | string | SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `MD5` | string | #A0 der Datei, auf die die aufgezeichnete Aktion angewendet wurde |
| `FileOriginUrl` | string | URL, von der die Datei heruntergeladen wurde |
| `FileOriginReferrerUrl` | string | URL der Webseite, die mit der heruntergeladenen Datei verknüpft ist |
| `FileOriginIP` | string | IP-Adresse, von der die Datei heruntergeladen wurde |
| `PreviousFolderPath` | string | Ursprünglicher Ordner, der die Datei enthält, bevor die aufgezeichnete Aktion angewendet wurde |
| `PreviousFileName` | string | Der ursprüngliche Name der Datei, die als Ergebnis der Aktion umbenannt wurde |
| `FileSize` | long | Größe der Datei in Byte |
| `InitiatingProcessAccountDomain` | string | Domäne des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountName` | string | Benutzername des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountSid` | string | Sicherheits-ID (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessAccountUpn` | string | Benutzerprinzipalname (UPN) des Kontos, das den für das Ereignis verantwortlichen Prozess verwendet hat |
| `InitiatingProcessMD5` | string | #A0 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA1` | string | SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat |
| `InitiatingProcessSHA256` | string | SHA-256 des Prozesses (Bilddatei), der das Ereignis initiiert hat. Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar. |
| `InitiatingProcessFolderPath` | string | Ordner, der den Prozess (Bilddatei) enthält, der das Ereignis initiiert hat |
| `InitiatingProcessFileName` | string | Name des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessId` | int | Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCommandLine` | string | Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat |
| `InitiatingProcessCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, zu dem der Prozess, der das Ereignis initiiert hat, gestartet wurde |
| `InitiatingProcessIntegrityLevel` | string | Integritätsstufe des Prozesses, der das Ereignis initiiert hat. Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden. Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen |
| `InitiatingProcessTokenElevation` | string | Tokentyp, der angibt, ob die Rechteerweiterung der Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat. |
| `InitiatingProcessParentId` | int | Prozess-ID (PID) des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentFileName` | string | Name des übergeordneten Prozesses, der den für das Ereignis verantwortlichen Prozess aussing |
| `InitiatingProcessParentCreationTime` | Datum/Uhrzeit | Datum und Uhrzeit, an dem das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde |
| `RequestProtocol` | string | Netzwerkprotokoll, falls zutreffend, zum Initiieren der Aktivität: Unknown, Local, SMB oder NFS |
| `ShareName` | string | Name des freigegebenen Ordners, der die Datei enthält |
| `RequestSourceIP` | string | IPv4- oder IPv6-Adresse des Remotegeräts, das die Aktivität initiiert hat |
| `RequestSourcePort` | string | Quellport auf dem Remotegerät, das die Aktivität initiiert hat |
| `RequestAccountName` | string | Benutzername des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `RequestAccountDomain` | string | Domäne des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `RequestAccountSid` | string | Sicherheits-ID (SID) des Kontos, das zum Remoteinitiieren der Aktivität verwendet wird |
| `ReportId` | long | Ereignisbezeichner basierend auf einem Repeating-Indikator. Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden. |
| `AppGuardContainerId` | string | Bezeichner für den virtualisierten Container, der von Application Guard zum Isolieren der Browseraktivität verwendet wird |
| `AdditionalFields` | string | Zusätzliche Informationen über die Entität oder das Ereignis |
| `InitiatingProcessFileSize` | long | Größe der Datei, die den für das Ereignis verantwortlichen Prozess verwendet hat |
| `SensitivityLabel` | string | Bezeichnung, die auf E-Mails, Dateien oder andere Inhalte angewendet wird, um sie zum Schutz von Informationen zu klassifizieren |
| `SensitivitySubLabel` | string | Unterkennzeichen, die auf E-Mails, Dateien oder andere Inhalte angewendet werden, um sie zum Schutz von Informationen zu klassifizieren; Vertraulichkeitsunterbezeichnungen sind unter Vertraulichkeitsbezeichnungen gruppieren, werden jedoch unabhängig behandelt. |
| `IsAzureInfoProtectionApplied` | boolean | Gibt an, ob die Datei von Azure Information Protection verschlüsselt wird. |

>[!NOTE]
> Dateihashinformationen werden immer angezeigt, wenn sie verfügbar sind. Es gibt jedoch mehrere mögliche Gründe, warum SHA1, SHA256 oder MD5 nicht berechnet werden kann. Die Datei kann sich beispielsweise im Remotespeicher befinden, durch einen anderen Prozess gesperrt, komprimiert oder als virtuell markiert sein. In diesen Szenarien werden die Dateihashinformationen leer angezeigt.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
