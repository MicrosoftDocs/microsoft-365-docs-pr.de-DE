---
title: Migrieren erweiterter Jagd Abfragen von Microsoft Defender für Endpoint
description: Hier erfahren Sie, wie Sie Ihren Microsoft Defender für Endpoint-Abfragen anpassen, damit Sie Sie in Microsoft 365 Defender verwenden können.
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846856"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrieren erweiterter Jagd Abfragen von Microsoft Defender für Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Stellen Sie Ihre erweiterten Jagd Workflows von Microsoft Defender für Endpoint so ein, dass Sie mithilfe einer breiteren Datenmenge proaktiv nach Bedrohungen suchen. In Microsoft 365 Defender erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:

- Microsoft Defender für Endpunkt
- Microsoft Defender für Office 365
- Microsoft Cloud App-Sicherheit
- Microsoft Defender für Identity

>[!NOTE]
>Die meisten Microsoft Defender für Endpoint-Kunden können [Microsoft 365 Defender ohne zusätzliche Lizenzen verwenden](prerequisites.md#licensing-requirements). Um mit dem Übergang ihrer erweiterten Jagd Workflows von Defender for Endpoint zu beginnen, [Aktivieren Sie Microsoft 365 Defender](mtp-enable.md).

Sie können den Übergang ohne Beeinträchtigung des vorhandenen Verteidigers für Endpunkt Workflows durchführen. Gespeicherte Abfragen bleiben intakt, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und Warnungen generiert. Sie werden jedoch in Microsoft 365 Defender angezeigt. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Schema Tabellen nur in Microsoft 365 Defender
Das [Erweiterte Jagd Schema von Microsoft 365 Defender](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen, die Daten aus verschiedenen Microsoft 365-Sicherheitslösungen enthalten. Die folgenden Tabellen stehen nur in Microsoft 365 Defender zur Verfügung:

| Tabellenname | Beschreibung |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Warnungen von Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich schwere Informationen und Bedrohungskategorien  |
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
Die `AlertInfo` `AlertEvidence` Tabellen und ersetzen die `DeviceAlertEvents` Tabelle im Microsoft Defender für das Endpunkt Schema. Neben Daten zu Geräte Warnungen enthalten diese beiden Tabellendaten zu Warnungen für Identitäten, Apps und e-Mails.

Verwenden Sie die folgende Tabelle, um zu prüfen, wie `DeviceAlertEvents` Spalten Spalten in den `AlertInfo` -und-Tabellen zugeordnet werden `AlertEvidence` .

>[!TIP]
>Zusätzlich zu den Spalten in der folgenden Tabelle enthält die `AlertEvidence` Tabelle viele andere Spalten, die ein ganzheitlicheres Bild der Benachrichtigungen aus verschiedenen Quellen bieten. [Alle AlertEvidence-Spalten anzeigen](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents-Spalte | Wo die gleichen Daten in Microsoft 365 Defender zu finden sind |
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
| `ReportId` | Diese Spalte wird in der Regel in Microsoft Defender für Endpoint verwendet, um verwandte Datensätze in anderen Tabellen zu finden. In Microsoft 365 Defender können Sie verwandte Daten direkt aus der `AlertEvidence` Tabelle abrufen. |
| `Table` | Diese Spalte wird in der Regel in Microsoft Defender für Endpoint für zusätzliche Ereignisinformationen in anderen Tabellen verwendet. In Microsoft 365 Defender können Sie verwandte Daten direkt aus der `AlertEvidence` Tabelle abrufen. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Anpassen von vorhandenen Microsoft Defender für Endpoint-Abfragen
Microsoft Defender für Endpoint-Abfragen funktioniert nur, wenn Sie auf die Tabelle verweisen `DeviceAlertEvents` . Um diese Abfragen in Microsoft 365 Defender zu verwenden, wenden Sie diese Änderungen an:

- Ersetzen Sie `DeviceAlertEvents` durch `AlertInfo` .
- Verknüpfen Sie die `AlertInfo` und die `AlertEvidence` Tabellen `AlertId` , um äquivalente Daten abzurufen.

### <a name="original-query"></a>Ursprüngliche Abfrage
Die folgende Abfrage verwendet `DeviceAlertEvents` in Microsoft Defender für Endpoint, um die Warnungen zu erhalten, die _powershell.exe_ umfassen:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Geänderte Abfrage
Die folgende Abfrage wurde für die Verwendung in Microsoft 365 Defender angepasst. Anstatt den Dateinamen direkt von zu überprüfen, wird der Dateiname `DeviceAlertEvents` `AlertEvidence` in dieser Tabelle verknüpft und überprüft.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren von Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Erweiterte Suche in Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)