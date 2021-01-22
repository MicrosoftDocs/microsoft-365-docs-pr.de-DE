---
title: Suche nach Bedrohungen auf allen Geräten, E-Mails, Apps und Identitäten mit erweiterter Suche
description: Untersuchen Sie gängige Suchszenarien und Beispielabfragen, die Geräte, E-Mails, Apps und Identitäten abdecken.
keywords: Erweiterte Suche, Office365-Daten, Windows-Geräte, Office365-E-Mails normalisieren, E-Mails, Apps, Identitäten, Bedrohungssuche, Cyberbedrohungssuche, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932250"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="612b1-104">Suche nach Bedrohungen auf allen Geräten, E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="612b1-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="612b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="612b1-105">**Applies to:**</span></span>
- <span data-ttu-id="612b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="612b1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="612b1-107">[Die erweiterte Suche](advanced-hunting-overview.md) in Microsoft 365 Defender ermöglicht Ihnen die proaktive Suche nach Bedrohungen in:</span><span class="sxs-lookup"><span data-stu-id="612b1-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="612b1-108">Von Microsoft Defender for Endpoint verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="612b1-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="612b1-109">Von Microsoft 365 verarbeitete E-Mails</span><span class="sxs-lookup"><span data-stu-id="612b1-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="612b1-110">Cloud-App-Aktivitäten, Authentifizierungsereignisse und Domänencontrolleraktivitäten, die von Microsoft Cloud App Security und Microsoft Defender for Identity nachverfolgt werden</span><span class="sxs-lookup"><span data-stu-id="612b1-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="612b1-111">Mit diesem Grad an Sichtbarkeit können Sie schnell nach Bedrohungen abwehren, die Abschnitte Ihres Netzwerks durchqueren, einschließlich ausgefeilter Angriffe, die in E-Mails oder im Web eintreffen, lokale Berechtigungen erhöhen, privilegierte Domänenanmeldeinformationen erwerben und auf Ihren Geräten weiter gehen.</span><span class="sxs-lookup"><span data-stu-id="612b1-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="612b1-112">Im Folgenden finden Sie allgemeine Techniken und Beispielabfragen basierend auf verschiedenen Suchszenarien, mit denen Sie untersuchen können, wie Sie Abfragen erstellen können, wenn Sie nach solchen komplexen Bedrohungen suchen.</span><span class="sxs-lookup"><span data-stu-id="612b1-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="612b1-113">Entitätsinformationen erhalten</span><span class="sxs-lookup"><span data-stu-id="612b1-113">Get entity info</span></span>
<span data-ttu-id="612b1-114">Verwenden Sie diese Abfragen, um zu erfahren, wie Sie schnell Informationen zu Benutzerkonten, Geräten und Dateien erhalten können.</span><span class="sxs-lookup"><span data-stu-id="612b1-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="612b1-115">Abrufen von Benutzerkonten aus E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="612b1-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="612b1-116">Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen.</span><span class="sxs-lookup"><span data-stu-id="612b1-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="612b1-117">Sie können dies im Allgemeinen für Empfänger- oder Absenderadressen mithilfe des lokalen Hosts aus der *E-Mail-Adresse* tun.</span><span class="sxs-lookup"><span data-stu-id="612b1-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="612b1-118">Im folgenden Codeausschnitt verwenden wir die [Tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto-Funktion, um den lokalen Host direkt vor den E-Mail-Adressen des Empfängers `@` in der Spalte zu `RecipientEmailAddress` extrahieren.</span><span class="sxs-lookup"><span data-stu-id="612b1-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="612b1-119">Die folgende Abfrage zeigt, wie dieser Codeausschnitt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="612b1-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="612b1-120">Zusammenführen der Tabelle "IdentityInfo"</span><span class="sxs-lookup"><span data-stu-id="612b1-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="612b1-121">Sie können Kontonamen und andere Kontoinformationen abrufen, indem Sie die IdentityInfo -Tabelle [zusammenführen oder verknüpfen.](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="612b1-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="612b1-122">Die folgende Abfrage ruft die Liste der Phishing- und Schadsoftwareerkennungen aus der Tabelle ["EmailEvents"](advanced-hunting-emailevents-table.md) ab und schließt diese Informationen dann mit der Tabelle zusammen, um detaillierte Informationen zu den einzelnen Empfängern `IdentityInfo` zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="612b1-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="612b1-123">Geräteinformationen erhalten</span><span class="sxs-lookup"><span data-stu-id="612b1-123">Get device information</span></span>
<span data-ttu-id="612b1-124">Das [Schema für die erweiterte Suche](advanced-hunting-schema-tables.md) bietet umfassende Geräteinformationen in verschiedenen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="612b1-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="612b1-125">Die Tabelle ["DeviceInfo"](advanced-hunting-deviceinfo-table.md) enthält beispielsweise umfassende Geräteinformationen basierend auf regelmäßig aggregierten Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="612b1-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="612b1-126">Diese Abfrage verwendet die Tabelle, um zu überprüfen, ob sich ein potenziell gefährdeter Benutzer ( ) bei geräten angemeldet hat, und listet dann die Warnungen auf, die auf diesen `DeviceInfo` `<account-name>` Geräten ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="612b1-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="612b1-127">Diese Abfrage `kind=inner` verwendet, um eine [innere Verknüpfung anzugeben,](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)die eine Deduplizierung linker Werte für `DeviceId` verhindert.</span><span class="sxs-lookup"><span data-stu-id="612b1-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="612b1-128">Suchszenarien</span><span class="sxs-lookup"><span data-stu-id="612b1-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="612b1-129">Anmeldeaktivitäten von Benutzern auflisten, die E-Mails erhalten haben, die nicht erfolgreich abgezappt wurden</span><span class="sxs-lookup"><span data-stu-id="612b1-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="612b1-130">[Zap (Zero-Hour Auto Purge) behebt](../office-365-security/zero-hour-auto-purge.md) schädliche E-Mails, nachdem sie empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="612b1-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="612b1-131">Wenn ZAP ausfällt, kann bösartiger Code auf dem Gerät ausgeführt werden und Konten gefährdet lassen.</span><span class="sxs-lookup"><span data-stu-id="612b1-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="612b1-132">Diese Abfrage überprüft die Anmeldeaktivität der Empfänger von E-Mails, die von ZAP nicht erfolgreich adressiert wurden.</span><span class="sxs-lookup"><span data-stu-id="612b1-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="612b1-133">Anmeldeversuche von Domänenkonten erhalten, die auf den Diebstahl von Anmeldeinformationen ausgerichtet sind</span><span class="sxs-lookup"><span data-stu-id="612b1-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="612b1-134">Diese Abfrage identifiziert zunächst alle Warnungen für den Zugriff auf Anmeldeinformationen in der `AlertInfo` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="612b1-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="612b1-135">Anschließend führt sie die Tabelle zusammen oder verbindet sie, die sie nach den Namen der Zielkonten analysiert, und filtert nur nach `AlertEvidence` Domänenkonten, die der Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="612b1-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="612b1-136">Schließlich wird die Tabelle überprüft, um alle Anmeldeaktivitäten der in die Domäne beigetretenen `IdentityLogonEvents` Zielkonten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="612b1-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="612b1-137">Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="612b1-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="612b1-138">Wenn Sie eine E-Mail-Adresse kennen, die schädliche Dateien ( ) sendet, können Sie diese Abfrage ausführen, um festzustellen, ob Dateien von diesem Absender auf Ihren `MaliciousSender@example.com` Geräten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="612b1-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="612b1-139">Sie können diese Abfrage beispielsweise verwenden, um Geräte zu identifizieren, die von einer Kampagne zur Verteilung von Schadsoftware betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="612b1-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="612b1-140">Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails</span><span class="sxs-lookup"><span data-stu-id="612b1-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="612b1-141">Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="612b1-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="612b1-142">Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.</span><span class="sxs-lookup"><span data-stu-id="612b1-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="612b1-143">Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern</span><span class="sxs-lookup"><span data-stu-id="612b1-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="612b1-144">Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="612b1-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="612b1-145">Wenn Sie E-Mails von einem bekannten böswilligen Absender ( ) kennen, können Sie diese Abfrage verwenden, um die PowerShell-Aktivitäten auflisten und überprüfen, die innerhalb von 30 Minuten nach dem Empfangen einer E-Mail vom Absender aufgetreten `MaliciousSender@example.com` sind.</span><span class="sxs-lookup"><span data-stu-id="612b1-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="612b1-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="612b1-146">Related topics</span></span>
- [<span data-ttu-id="612b1-147">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="612b1-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="612b1-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="612b1-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="612b1-149">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="612b1-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="612b1-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="612b1-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="612b1-151">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="612b1-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="612b1-152">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="612b1-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
