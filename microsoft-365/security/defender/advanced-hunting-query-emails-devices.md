---
title: Suche nach Bedrohungen über Geräte, E-Mails, Apps und Identitäten hinweg mit erweiterter Suche
description: Untersuchen Sie häufige Suchszenarien und Beispielabfragen, die Geräte, E-Mails, Apps und Identitäten abdecken.
keywords: Erweiterte Suche, Office365-Daten, Windows Geräte, Office365-E-Mails normalisieren sich, E-Mails, Apps, Identitäten, Bedrohungssuche, Suche nach Cyberbedrohungen, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: aacd0745ff507356035f8f460ed2b4307e9da6ed
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964873"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="87bf0-104">Gefahrensuche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="87bf0-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87bf0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="87bf0-105">**Applies to:**</span></span>
- <span data-ttu-id="87bf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bf0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="87bf0-107">[Mit der erweiterten Suche](advanced-hunting-overview.md) in Microsoft 365 Defender können Sie proaktiv nach Bedrohungen in folgenden Branchen suchen:</span><span class="sxs-lookup"><span data-stu-id="87bf0-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="87bf0-108">Von Microsoft Defender für Endpunkt verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="87bf0-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="87bf0-109">Von Microsoft 365 verarbeitete E-Mails</span><span class="sxs-lookup"><span data-stu-id="87bf0-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="87bf0-110">Cloud-App-Aktivitäten, Authentifizierungsereignisse und Domänencontrolleraktivitäten, die von Microsoft Cloud App Security und Microsoft Defender for Identity nachverfolgt werden</span><span class="sxs-lookup"><span data-stu-id="87bf0-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="87bf0-111">Mit dieser Sichtbarkeit können Sie schnell nach Bedrohungen suchen, die Abschnitte Ihres Netzwerks durchlaufen, einschließlich komplexer Eindringversuche, die per E-Mail oder im Web eingehen, lokale Berechtigungen erhöhen, privilegierte Domänenanmeldeinformationen erwerben und seitlich zu Ihren Geräten wechseln.</span><span class="sxs-lookup"><span data-stu-id="87bf0-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="87bf0-112">Hier sind allgemeine Techniken und Beispielabfragen basierend auf verschiedenen Suchszenarien, mit denen Sie untersuchen können, wie Sie Abfragen erstellen können, wenn Sie nach solchen komplexen Bedrohungen suchen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="87bf0-113">Abrufen von Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="87bf0-113">Get entity info</span></span>
<span data-ttu-id="87bf0-114">Verwenden Sie diese Abfragen, um zu erfahren, wie Sie schnell Informationen zu Benutzerkonten, Geräten und Dateien abrufen können.</span><span class="sxs-lookup"><span data-stu-id="87bf0-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="87bf0-115">Abrufen von Benutzerkonten aus E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="87bf0-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="87bf0-116">Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="87bf0-117">Sie können dies in der Regel für empfänger- oder absenderadressen mithilfe des *lokalen Hosts* aus der E-Mail-Adresse tun.</span><span class="sxs-lookup"><span data-stu-id="87bf0-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="87bf0-118">Im folgenden Codeausschnitt verwenden wir die [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto-Funktion, um den lokalen Host direkt vor den `@` E-Mail-Adressen des Empfängers in der Spalte zu `RecipientEmailAddress` extrahieren.</span><span class="sxs-lookup"><span data-stu-id="87bf0-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="87bf0-119">Die folgende Abfrage zeigt, wie dieser Codeausschnitt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="87bf0-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="87bf0-120">Zusammenführen der IdentityInfo-Tabelle</span><span class="sxs-lookup"><span data-stu-id="87bf0-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="87bf0-121">Sie können Kontonamen und andere Kontoinformationen abrufen, indem Sie die [IdentityInfo-Tabelle](advanced-hunting-identityinfo-table.md)zusammenführen oder verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="87bf0-122">Die folgende Abfrage ruft die Liste der Phishing- und Schadsoftwareerkennungen aus der [Tabelle EmailEvents ](advanced-hunting-emailevents-table.md) ab und verknüpft diese Informationen dann mit der `IdentityInfo` Tabelle, um detaillierte Informationen zu jedem Empfänger zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="87bf0-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="87bf0-123">Abrufen von Geräteinformationen</span><span class="sxs-lookup"><span data-stu-id="87bf0-123">Get device information</span></span>
<span data-ttu-id="87bf0-124">Das Schema für [die erweiterte Suche](advanced-hunting-schema-tables.md) enthält umfangreiche Geräteinformationen in verschiedenen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="87bf0-125">Die [DeviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) enthält beispielsweise umfassende Geräteinformationen basierend auf regelmäßig aggregierten Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="87bf0-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="87bf0-126">Diese Abfrage verwendet die `DeviceInfo` Tabelle, um zu überprüfen, ob sich ein potenziell gefährdeter Benutzer ( `<account-name>` ) bei geräten angemeldet hat, und listet dann die Warnungen auf, die auf diesen Geräten ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="87bf0-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="87bf0-127">Diese Abfrage `kind=inner` verwendet, um eine [innere Verknüpfung](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)anzugeben, die die Deduplizierung linker Seitenwerte für `DeviceId` verhindert.</span><span class="sxs-lookup"><span data-stu-id="87bf0-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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


### <a name="get-file-event-information"></a><span data-ttu-id="87bf0-128">Abrufen von Dateiereignisinformationen</span><span class="sxs-lookup"><span data-stu-id="87bf0-128">Get file event information</span></span>

<span data-ttu-id="87bf0-129">Verwenden Sie die folgende Abfrage, um Informationen zu dateibezogenen Ereignissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-129">Use the following query to get information on file related events.</span></span> 

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceFileEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="get-network-event-information"></a><span data-ttu-id="87bf0-130">Abrufen von Netzwerkereignisinformationen</span><span class="sxs-lookup"><span data-stu-id="87bf0-130">Get network event information</span></span>

<span data-ttu-id="87bf0-131">Verwenden Sie die folgende Abfrage, um Informationen zu netzwerkbezogenen Ereignissen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-131">Use the following query to get information on network related events.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-agent-version-information"></a><span data-ttu-id="87bf0-132">Abrufen von Informationen zur Geräte-Agent-Version</span><span class="sxs-lookup"><span data-stu-id="87bf0-132">Get device agent version information</span></span>

<span data-ttu-id="87bf0-133">Verwenden Sie die folgende Abfrage, um die Version des Agents abzurufen, der auf einem Gerät ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87bf0-133">Use the following query to get the version of the agent running on a device.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where ClientVersion startswith "20.1"
| summarize by DeviceId
| join kind=inner (
    DeviceNetworkEvents 
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


### <a name="example-query-for-macos-devices"></a><span data-ttu-id="87bf0-134">Beispielabfrage für macOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="87bf0-134">Example query for macOS devices</span></span>

<span data-ttu-id="87bf0-135">Verwenden Sie die folgende Beispielabfrage, um alle Geräte mit macOS mit einer älteren Version als Csv anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-135">Use the following example query to see all devices running macOS with a version older than Catalina.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OSPlatform == "macOS" and  OSVersion !contains "10.15" and OSVersion !contains "11."
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```

### <a name="get-device-status-info"></a><span data-ttu-id="87bf0-136">Abrufen von Gerätestatusinformationen</span><span class="sxs-lookup"><span data-stu-id="87bf0-136">Get device status info</span></span>

<span data-ttu-id="87bf0-137">Verwenden Sie die folgende Abfrage, um den Status eines Geräts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-137">Use the following query to get status of a device.</span></span> <span data-ttu-id="87bf0-138">Im folgenden Beispiel überprüft die Abfrage, ob das Gerät integriert ist.</span><span class="sxs-lookup"><span data-stu-id="87bf0-138">In the following example, the query checks to see if the device is onboarded.</span></span>

```kusto
DeviceInfo
| where Timestamp > ago(1d)
| where OnboardingStatus != "Onboarded"
| summarize by DeviceId
| join kind=inner (
    DeviceInfo
    | where Timestamp > ago(1d)
) on DeviceId
| take 10
```


## <a name="hunting-scenarios"></a><span data-ttu-id="87bf0-139">Suchszenarien</span><span class="sxs-lookup"><span data-stu-id="87bf0-139">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="87bf0-140">Auflisten von Anmeldeaktivitäten von Benutzern, die E-Mails erhalten haben, die nicht erfolgreich angeheftet wurden</span><span class="sxs-lookup"><span data-stu-id="87bf0-140">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="87bf0-141">[Zap (Zero-Hour Auto Purge)](../office-365-security/zero-hour-auto-purge.md) behebt bösartige E-Mails, nachdem sie empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="87bf0-141">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="87bf0-142">Wenn ZAP fehlschlägt, kann bösartiger Code möglicherweise auf dem Gerät ausgeführt werden und Konten kompromittiert lassen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-142">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="87bf0-143">Diese Abfrage überprüft auf Anmeldeaktivitäten, die von den Empfängern von E-Mails vorgenommen wurden, die von ZAP nicht erfolgreich adressiert wurden.</span><span class="sxs-lookup"><span data-stu-id="87bf0-143">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="87bf0-144">Abrufen von Anmeldeversuchen nach Domänenkonten, auf die der Diebstahl von Anmeldeinformationen abzielt</span><span class="sxs-lookup"><span data-stu-id="87bf0-144">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="87bf0-145">Diese Abfrage identifiziert zunächst alle Warnungen beim Zugriff auf Anmeldeinformationen in der `AlertInfo` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="87bf0-145">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="87bf0-146">Anschließend wird die Tabelle zusammengeführt oder `AlertEvidence` verknüpft, die sie auf die Namen der Zielkonten analysiert und nur nach Domänenkonten filtert.</span><span class="sxs-lookup"><span data-stu-id="87bf0-146">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="87bf0-147">Schließlich wird die Tabelle überprüft, `IdentityLogonEvents` um alle Anmeldeaktivitäten der in die Domäne eingebundenen Zielkonten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-147">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="87bf0-148">Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="87bf0-148">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="87bf0-149">Wenn Sie von einer E-Mail-Adresse wissen, die schädliche Dateien ( `MaliciousSender@example.com` ) sendet, können Sie diese Abfrage ausführen, um zu ermitteln, ob Dateien von diesem Absender auf Ihren Geräten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="87bf0-149">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="87bf0-150">Sie können diese Abfrage beispielsweise verwenden, um Geräte zu identifizieren, die von einer Schadsoftwareverteilungskampagne betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="87bf0-150">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="87bf0-151">Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails</span><span class="sxs-lookup"><span data-stu-id="87bf0-151">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="87bf0-152">Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="87bf0-152">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="87bf0-153">Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.</span><span class="sxs-lookup"><span data-stu-id="87bf0-153">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="87bf0-154">Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern</span><span class="sxs-lookup"><span data-stu-id="87bf0-154">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="87bf0-155">Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="87bf0-155">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="87bf0-156">Wenn Sie wissen, dass E-Mails von einem bekannten böswilligen Absender ( ) stammen, `MaliciousSender@example.com` können Sie diese Abfrage verwenden, um PowerShell-Aktivitäten aufzuführen und zu überprüfen, die innerhalb von 30 Minuten nach dem Empfang einer E-Mail vom Absender aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="87bf0-156">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="87bf0-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="87bf0-157">Related topics</span></span>
- [<span data-ttu-id="87bf0-158">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="87bf0-158">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87bf0-159">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="87bf0-159">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="87bf0-160">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="87bf0-160">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="87bf0-161">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="87bf0-161">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="87bf0-162">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="87bf0-162">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="87bf0-163">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="87bf0-163">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
