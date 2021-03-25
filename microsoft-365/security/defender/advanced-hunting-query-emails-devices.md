---
title: Suche nach Bedrohungen auf geräten, E-Mails, Apps und Identitäten mit erweiterter Suche
description: Untersuchen Sie gängige Suchszenarien und Beispielabfragen, die Geräte, E-Mails, Apps und Identitäten abdecken.
keywords: Erweiterte Suche, Office365-Daten, Windows-Geräte, Office365-E-Mails normalisieren, E-Mails, Apps, Identitäten, Bedrohungssuche, Cyberbedrohungensuche, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: e494bfe57c31c1d5044f72a8adb3e2548d531604
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199149"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Gefahrensuche über Geräte, E-Mails, Apps und Identitäten hinweg

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Die erweiterte Suche](advanced-hunting-overview.md) in Microsoft 365 Defender ermöglicht Ihnen die proaktive Suche nach Bedrohungen in allen:
- Von Microsoft Defender for Endpoint verwaltete Geräte
- Von Microsoft 365 verarbeitete E-Mails
- Cloud-App-Aktivitäten, Authentifizierungsereignisse und Domänencontrolleraktivitäten nachverfolgt von Microsoft Cloud App Security und Microsoft Defender for Identity

Mit dieser Sichtbarkeitsstufe können Sie schnell nach Bedrohungen abwehren, die Abschnitte Ihres Netzwerks durchqueren, einschließlich ausgefeilter Angriffe, die in E-Mails oder im Web eintreffen, lokale Berechtigungen erhöhen, privilegierte Domänenanmeldeinformationen erwerben und sich quer über Ihre Geräte bewegen. 

Im Folgenden finden Sie allgemeine Techniken und Beispielabfragen basierend auf verschiedenen Suchszenarien, mit denen Sie untersuchen können, wie Sie Abfragen erstellen können, wenn Sie nach so komplexen Bedrohungen suchen.

## <a name="get-entity-info"></a>Entitätsinformationen erhalten
Verwenden Sie diese Abfragen, um zu erfahren, wie Sie schnell Informationen zu Benutzerkonten, Geräten und Dateien erhalten können. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Abrufen von Benutzerkonten aus E-Mail-Adressen
Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen. Sie können dies im Allgemeinen für empfänger- oder absenderadressen mithilfe des lokalen Hosts über die *E-Mail-Adresse* tun.

Im folgenden Codeausschnitt verwenden wir die [Tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto-Funktion, um den lokalen Host direkt vor den E-Mail-Adressen `@` des Empfängers in der Spalte zu `RecipientEmailAddress` extrahieren.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
Die folgende Abfrage zeigt, wie dieser Codeausschnitt verwendet werden kann:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Zusammenführen der IdentityInfo-Tabelle

Sie können Kontonamen und andere Kontoinformationen abrufen, indem Sie die [IdentityInfo-Tabelle zusammenführen oder der Tabelle "IdentityInfo" beitreten.](advanced-hunting-identityinfo-table.md) Die folgende Abfrage ruft die Liste der Phishing- und Schadsoftwareerkennungen aus der [EmailEvents-Tabelle](advanced-hunting-emailevents-table.md) ab und schließt diese Informationen dann mit der Tabelle zusammen, um detaillierte Informationen zu den einzelnen Empfängern `IdentityInfo` zu erhalten. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Geräteinformationen erhalten
Das [schema der erweiterten Suche](advanced-hunting-schema-tables.md) enthält umfassende Geräteinformationen in verschiedenen Tabellen. Beispielsweise enthält die [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) umfassende Geräteinformationen, die auf regelmäßig aggregierten Ereignisdaten basieren. Diese Abfrage verwendet die Tabelle, um zu überprüfen, ob sich ein potenziell gefährdeter Benutzer ( ) bei allen Geräten angemeldet hat, und listet dann die Warnungen auf, die auf diesen Geräten `DeviceInfo` `<account-name>` ausgelöst wurden.

>[!Tip]
> Diese Abfrage `kind=inner` verwendet, um eine [innere Verknüpfung anzugeben,](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)die eine Deduplizierung linker Werte für `DeviceId` verhindert.

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>Suchszenarien

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Auflisten von Anmeldeaktivitäten von Benutzern, die E-Mails empfangen haben, die nicht erfolgreich abgezapft wurden
[Die automatische NS-Bereinigung (Zero-Hour Auto Purge, ZAP) behebt](../office-365-security/zero-hour-auto-purge.md) schädliche E-Mails, nachdem sie empfangen wurden. Wenn ZAP ausfällt, wird möglicherweise bösartiger Code auf dem Gerät ausgeführt und Konten gefährdet. Diese Abfrage überprüft die Anmeldeaktivität der Empfänger von E-Mails, die nicht erfolgreich von ZAP adressiert wurden.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Get logon attempts by domain accounts targeted by credential theft
Diese Abfrage identifiziert zunächst alle Anmeldeinformationszugriffswarnungen in der `AlertInfo` Tabelle. Anschließend wird die Tabelle zusammengeführt oder zusammengeführt, die sie nur nach den Namen der Zielkonten analysiert und nur für `AlertEvidence` Domänenkonten filtert. Schließlich wird die Tabelle überprüft, um alle Anmeldeaktivitäten der zielorientierten Konten der `IdentityLogonEvents` Domäne zu erhalten.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind
Vorausgesetzt, Sie kennen eine E-Mail-Adresse, die schädliche Dateien sendet ( ), können Sie diese Abfrage ausführen, um zu ermitteln, ob Dateien von diesem Absender `MaliciousSender@example.com` auf Ihren Geräten vorhanden sind. Sie können diese Abfrage beispielsweise verwenden, um Geräte zu identifizieren, die von einer Schadsoftwareverteilungskampagne betroffen sind.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails
Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden. Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern
Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen. Wenn Sie E-Mails von einem bekannten böswilligen Absender ( ) kennen, können Sie diese Abfrage verwenden, um PowerShell-Aktivitäten auflisten und überprüfen zu können, die innerhalb von 30 Minuten nach dem Empfangen einer E-Mail vom Absender aufgetreten `MaliciousSender@example.com` sind.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)