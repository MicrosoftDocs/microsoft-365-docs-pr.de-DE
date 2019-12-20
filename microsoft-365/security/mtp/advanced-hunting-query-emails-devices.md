---
title: Ermitteln von Bedrohungen auf Geräten und in E-Mails mithilfe der erweiterten Suche
description: Untersuchen Sie häufige Suchszenarien und Beispielabfragen für Geräte und E-Mails.
keywords: erweiterte Suche, Office 365-Daten, Windows-Geräte, Office 365-E-Mails normalisieren, E-Mails, Suche nach Bedrohungen, Suche nach Cyberbedrohungen, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da985621c1cee3fe5aa30d961380ef3f3d83de8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808750"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Suche nach Bedrohungen auf Geräten und in E-Mails

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Die [erweiterte Suche](advanced-hunting-overview.md) in Microsoft Threat Protection bietet Ihnen die Möglichkeit, auf Ihren Windows-Geräten und in Ihren Office 365-E-Mails proaktiv nach Bedrohungen zu suchen. Nachfolgend finden Sie einige Suchszenarien und Beispielabfragen, die Ihnen dabei helfen, zu verstehen, wie Sie Abfragen erstellen können, die sowohl Geräte als auch E-Mails umfassen.

## <a name="obtain-user-accounts-from-email-addresses"></a>Abrufen von Benutzerkonten aus E-Mail-Adressen
Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen. Verwenden Sie dazu den *lokalen Host* aus der E-Mail-Adresse:

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Diese Normalisierungstechnik wird in den folgenden Szenarien verwendet.

## <a name="hunting-scenarios"></a>Suchszenarien

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind
Angenommen, Sie kennen eine E-Mail-Adresse, von der aus schädliche Dateien gesendet werden, dann können Sie diese Abfrage ausführen, um zu ermitteln, ob Dateien von diesem Absender auf Ihren Geräten vorhanden sind. Sie können die Abfrage beispielsweise verwenden, um die Anzahl der von einer Schadsoftware-Verteilungskampagne betroffenen Geräte zu ermitteln.

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails
Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden. Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern
Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen. Wenn Sie wissen, dass Sie E-Mail-Nachrichten eines bekannten bösartigen Absenders erhalten haben, können Sie diese Abfrage verwenden, um PowerShell-Aktivitäten aufzulisten und zu überprüfen, die innerhalb von 30 Minuten nach dem Empfang einer E-Mail von diesem Absender ausgeführt wurden.  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)