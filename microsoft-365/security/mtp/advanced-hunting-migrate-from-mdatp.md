---
title: Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie Ihre Microsoft Defender for Endpoint-Abfragen so anpassen, dass Sie sie in Microsoft 365 Defender verwenden können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, M365, Microsoft Defender ATP, Mdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Zuordnung
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094807"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Verschieben Sie Ihre Workflows für die erweiterte Suche von Microsoft Defender for Endpoint, um proaktiv nach Bedrohungen zu abwehren, indem Sie einen größeren Satz von Daten verwenden. In Microsoft 365 Defender erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:

- Microsoft Defender für Endpunkt
- Microsoft Defender für Office 365
- Microsoft Cloud App-Sicherheit
- Microsoft Defender for Identity

>[!NOTE]
>Die meisten Microsoft Defender for Endpoint-Kunden können [Microsoft 365 Defender ohne zusätzliche Lizenzen verwenden.](prerequisites.md#licensing-requirements) Um mit dem Übergang Ihrer Workflows für die erweiterte Suche von Defender for Endpoint zu beginnen, aktivieren Sie [Microsoft 365 Defender](mtp-enable.md).

Sie können einen Übergang ohne Auswirkungen auf Ihre vorhandenen Defender for Endpoint-Workflows. Gespeicherte Abfragen bleiben erhalten, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und generieren Warnungen. Sie sind jedoch in Microsoft 365 Defender sichtbar. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schematabellen nur in Microsoft 365 Defender
Das [Microsoft 365 Defender Advanced Hunting-Schema](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen mit Daten aus verschiedenen Microsoft 365-Sicherheitslösungen. Die folgenden Tabellen sind nur in Microsoft 365 Defender verfügbar:

| Tabellenname | Beschreibung |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Warnungen von Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungskategorien  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Dateibezogene Aktivitäten in Cloud-Apps und -Diensten |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informationen zu Dateien, die an E-Mails angefügt sind |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365-E-Mail-Ereignisse, einschließlich E-Mail-Übermittlung und Blockieren von Ereignissen |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die E-Mails an das Empfängerpostfach zugestellt hat |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informationen zu URLs in E-Mails |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Ereignisse, an denen ein lokales Domänencontroller beteiligt ist, auf dem Active Directory (AD) ausgeführt wird. In dieser Tabelle wird eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller behandelt. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Authentifizierungsereignisse für Active Directory und Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen |

## <a name="map-devicealertevents-table"></a>Tabelle "DeviceAlertEvents zuordnung"
Die `AlertInfo` Tabelle und die Tabellen ersetzen die Tabelle im Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-Schema. Zusätzlich zu Daten zu Gerätewarnungen enthalten diese beiden Tabellen Daten zu Warnungen für Identitäten, Apps und E-Mails.

Verwenden Sie die folgende Tabelle, um zu überprüfen, wie Spalten Spalten in den Und `DeviceAlertEvents` `AlertInfo` Tabellen `AlertEvidence` zuordnungen.

>[!TIP]
>Zusätzlich zu den Spalten in der folgenden Tabelle enthält die Tabelle viele weitere Spalten, die ein ganzheitliches Bild von Warnungen aus `AlertEvidence` verschiedenen Quellen liefern. [Anzeigen aller AlertEvidence-Spalten](advanced-hunting-alertevidence-table.md) 

| Spalte "DeviceAlertEvents" | Wo die gleichen Daten in Microsoft 365 Defender zu finden sind |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` und  `AlertEvidence` Tabellen |
| `Timestamp` | `AlertInfo` und  `AlertEvidence` Tabellen |
| `DeviceId` | `AlertEvidence` Table |
| `DeviceName` | `AlertEvidence` Table |
| `Severity` | `AlertInfo` Table |
| `Category` | `AlertInfo` Table |
| `Title` | `AlertInfo` Table |
| `FileName` | `AlertEvidence` Table |
| `SHA1` | `AlertEvidence` Table |
| `RemoteUrl` | `AlertEvidence` Table |
| `RemoteIP` | `AlertEvidence` Table |
| `AttackTechniques` | `AlertInfo` Table |
| `ReportId` | Diese Spalte wird in der Regel in Microsoft Defender for Endpoint verwendet, um verwandte Datensätze in anderen Tabellen zu suchen. In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten. |
| `Table` | Diese Spalte wird in der Regel in Microsoft Defender for Endpoint für zusätzliche Ereignisinformationen in anderen Tabellen verwendet. In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Anpassen vorhandener Microsoft Defender für Endpunktabfragen
Microsoft Defender for Endpoint-Abfragen funktionieren wie beh nk, es sei denn, sie verweisen auf die `DeviceAlertEvents` Tabelle. Um diese Abfragen in Microsoft 365 Defender zu verwenden, wenden Sie die folgenden Änderungen an:

- Ersetzen `DeviceAlertEvents` Durch `AlertInfo` .
- Verbinden Sie `AlertInfo` die Tabellen und die `AlertEvidence` Tabellen, um entsprechende Daten zu `AlertId` erhalten.

### <a name="original-query"></a>Ursprüngliche Abfrage
Die folgende Abfrage wird `DeviceAlertEvents` in Microsoft Defender for __ Endpoint verwendet, um die Warnungen zu erhalten, diepowershell.exe:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Geänderte Abfrage
Die folgende Abfrage wurde für die Verwendung in Microsoft 365 Defender angepasst. Anstatt den Dateinamen direkt aus zu überprüfen, wird der Dateiname in dieser Tabelle bei der Verknüpfung und überprüfung auf `DeviceAlertEvents` `AlertEvidence` den Dateinamen überprüft.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a>Siehe auch
- [Aktivieren von Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Erweiterte Suche in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)