---
title: Migrieren von erweiterten Jagd Abfragen von Microsoft Defender ATP
description: Hier erfahren Sie, wie Sie Ihre Microsoft Defender ATP-Abfragen anpassen können, damit Sie Sie in Microsoft Threat Protection verwenden können.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Zuordnung
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daa89ebf39f8fc6d2110720f61b8d02c074fb484
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338720"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Migrieren von erweiterten Jagd Abfragen von Microsoft Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft Threat Protection

Stellen Sie Ihre erweiterten Jagd Workflows von Microsoft Defender ATP so ein, dass Sie mit einer breiteren Datenmenge proaktiv nach Bedrohungen suchen. In Microsoft Threat Protection erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App-Sicherheit
- Azure Advanced Threat Protection

>[!NOTE]
>Die meisten Microsoft Defender ATP-Kunden können [Microsoft Threat Protection ohne zusätzliche Lizenzen verwenden](prerequisites.md#licensing-requirements). Um mit dem Übergang ihrer erweiterten Jagd Workflows von Microsoft Defender ATP zu beginnen, [Aktivieren Sie Microsoft Threat Protection](mtp-enable.md).

Sie können den Übergang ohne Auswirkungen auf die vorhandenen Microsoft Defender ATP-Workflows durchführen. Gespeicherte Abfragen bleiben intakt, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und Warnungen generiert. Sie werden jedoch in Microsoft Threat Protection angezeigt. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Schema Tabellen in Microsoft Threat Protection
Das [Advanced Hunting-Schema von Microsoft Threat Protection](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen, die Daten aus verschiedenen Microsoft 365-Sicherheitslösungen enthalten. Die folgenden Tabellen stehen nur in Microsoft Threat Protection zur Verfügung:

| Tabellenname | Beschreibung |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP, einschließlich schwere Informationen und Bedrohungskategorien  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Dateibezogene Aktivitäten in Cloud-apps und-Diensten |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informationen zu an e-Mails angeschlossenen Dateien |
| [EmailEvents](advanced-hunting-emailevents-table.md) | E-Mail-Ereignisse von Microsoft 365, einschließlich e-Mail-Zustellung und Blockierungs Ereignisse |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die e-Mails an das Empfängerpostfach übermittelt hat |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informationen zu URLs in e-Mails |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Ereignisse, die einen lokalen Domänencontroller mit Active Directory (AD) umfassen. Diese Tabelle enthält eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Authentifizierungsereignisse für Active Directory und Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Abfragen für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen |

## <a name="map-devicealertevents-table"></a>Map-DeviceAlertEvents-Tabelle
Die `AlertInfo` `AlertEvidence` Tabellen und ersetzen die `DeviceAlertEvents` Tabelle im ATP-Schema von Microsoft Defender. Neben Daten zu Geräte Warnungen enthalten diese beiden Tabellendaten zu Warnungen für Identitäten, Apps und e-Mails.

Verwenden Sie die folgende Tabelle, um zu prüfen, wie `DeviceAlertEvents` Spalten Spalten in den `AlertInfo` -und-Tabellen zugeordnet werden `AlertEvidence` .

>[!TIP]
>Zusätzlich zu den Spalten in der folgenden Tabelle enthält die `AlertEvidence` Tabelle viele andere Spalten, die ein ganzheitlicheres Bild der Benachrichtigungen aus verschiedenen Quellen bieten. [Alle AlertEvidence-Spalten anzeigen](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents-Spalte | Wo die gleichen Daten in Microsoft Threat Protection gefunden werden |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` und  `AlertEvidence` Tabellen |
| `Timestamp` | `AlertInfo` und  `AlertEvidence` Tabellen |
| `DeviceId` | `AlertEvidence` Tabelle |
| `DeviceName` | `AlertEvidence` Tabelle |
| `Severity` | `AlertInfo` Tabelle |
| `Category` | `AlertInfo` Tabelle |
| `Title` | `AlertInfo` Tabelle |
| `FileName` | `AlertEvidence` Tabelle |
| `SHA1` | `AlertEvidence` Tabelle |
| `RemoteUrl` | `AlertEvidence` Tabelle |
| `RemoteIP` | `AlertEvidence` Tabelle |
| `AttackTechniques` | `AlertInfo` Tabelle |
| `ReportId` | Diese Spalte wird in der Regel in Microsoft Defender ATP verwendet, um verwandte Datensätze in anderen Tabellen zu finden. In Microsoft Threat Protection können Sie verwandte Daten direkt aus der Tabelle abrufen `AlertEvidence` . |
| `Table` | Diese Spalte wird in der Regel in Microsoft Defender ATP für zusätzliche Ereignisinformationen in anderen Tabellen verwendet. In Microsoft Threat Protection können Sie verwandte Daten direkt aus der Tabelle abrufen `AlertEvidence` . |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Anpassen vorhandener ATP-Abfragen für Microsoft Defender
Microsoft Defender ATP-Abfragen funktionieren nur dann, wenn Sie auf die `DeviceAlertEvents` Tabelle verweisen. Wenn Sie diese Abfragen in Microsoft Threat Protection verwenden möchten, wenden Sie diese Änderungen an:

- Ersetzen Sie `DeviceAlertEvents` durch `AlertInfo` .
- Verknüpfen Sie die `AlertInfo` und die `AlertEvidence` Tabellen `AlertId` , um äquivalente Daten abzurufen.

### <a name="original-query"></a>Ursprüngliche Abfrage
Die folgende Abfrage verwendet `DeviceAlertEvents` in Microsoft Defender ATP, um die Warnungen zu erhalten, die _powershell.exe_beinhalten:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Geänderte Abfrage
Die folgende Abfrage wurde für die Verwendung in Microsoft Threat Protection angepasst. Anstatt den Dateinamen direkt von zu überprüfen, wird der Dateiname `DeviceAlertEvents` `AlertEvidence` in dieser Tabelle verknüpft und überprüft.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren von Microsoft Threat Protection](advanced-hunting-query-language.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Erweiterte Suche in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)