---
title: Jagd auf Bedrohungen über Geräte, e-Mails, Apps und Identitäten mit Advanced Hunting
description: Untersuchen Sie häufige Jagd Szenarien und Beispielabfragen, die Geräte, e-Mails, Apps und Identitäten abdecken.
keywords: Erweiterte Suche, Office365-Daten, Windows-Geräte, Office365-e-Mails, e-Mails, apps, Identitäten, Bedrohungs Suche, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 6c758c05a64cd7ce84a2b021fe32f9e5ce5c1090
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431063"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="8916d-104">Jagen nach Bedrohungen auf Geräten, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="8916d-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8916d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8916d-105">**Applies to:**</span></span>
- <span data-ttu-id="8916d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8916d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8916d-107">[Advanced Hunting](advanced-hunting-overview.md) in Microsoft Threat Protection ermöglicht Ihnen eine proaktive Suche nach Bedrohungen in folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="8916d-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="8916d-108">Von Microsoft Defender ATP verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="8916d-108">Devices managed by Microsoft Defender ATP</span></span>
- <span data-ttu-id="8916d-109">Von Microsoft 365 verarbeitete e-Mails</span><span class="sxs-lookup"><span data-stu-id="8916d-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="8916d-110">Cloud-App-Aktivitäten, Authentifizierungsereignisse und Domänencontroller Aktivitäten nachverfolgt von Microsoft Cloud App Security und Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8916d-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Azure ATP</span></span>

<span data-ttu-id="8916d-111">Mit dieser Sichtbarkeitsstufe können Sie schnell nach Bedrohungen suchen, die Abschnitte in Ihrem Netzwerk durchlaufen, einschließlich ausgeklügelter Intrusionen, die in e-Mails oder im Internet eingehen, lokale Berechtigungen erhöhen, privilegierte Domänenanmeldeinformationen erwerben und seitlich auf die Geräte übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="8916d-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="8916d-112">Hier finden Sie allgemeine Techniken und Beispielabfragen basierend auf verschiedenen Jagd Szenarien, mit denen Sie untersuchen können, wie Sie Abfragen bei der Suche nach derart anspruchsvollen Bedrohungen konstruieren könnten.</span><span class="sxs-lookup"><span data-stu-id="8916d-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="8916d-113">Entitätsinformationen abrufen</span><span class="sxs-lookup"><span data-stu-id="8916d-113">Get entity info</span></span>
<span data-ttu-id="8916d-114">Verwenden Sie diese Abfragen, um zu erfahren, wie Sie schnell Informationen zu Benutzerkonten, Geräten und Dateien abrufen können.</span><span class="sxs-lookup"><span data-stu-id="8916d-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="8916d-115">Abrufen von Benutzerkonten aus E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="8916d-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="8916d-116">Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen.</span><span class="sxs-lookup"><span data-stu-id="8916d-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="8916d-117">Sie können dies in der Regel entweder für die Empfänger-oder Absenderadresse verwenden, indem Sie den *lokalen Host* aus der e-Mail-Adresse verwenden.</span><span class="sxs-lookup"><span data-stu-id="8916d-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="8916d-118">Im Codeausschnitt unten verwenden wir die Kusto-Funktion [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) , um den lokalen Host direkt vor den `@` e-Mail-Adressen von Empfängern in der Spalte zu extrahieren `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="8916d-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="8916d-119">Die folgende Abfrage zeigt, wie dieser Codeausschnitt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="8916d-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="8916d-120">Zusammenführen der IdentityInfo-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8916d-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="8916d-121">Sie können Kontonamen und andere Kontoinformationen abrufen, indem Sie die [IdentityInfo-Tabelle](advanced-hunting-identityinfo-table.md)zusammenführen oder beitreten.</span><span class="sxs-lookup"><span data-stu-id="8916d-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="8916d-122">Die folgende Abfrage ruft die Liste der Phishing-und Schadsoftware-Erkennungen in der [EmailEvents-Tabelle](advanced-hunting-emailevents-table.md) ab und verknüpft diese Informationen dann mit der `IdentityInfo` Tabelle, um detaillierte Informationen zu den einzelnen Empfängern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8916d-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="8916d-123">Abrufen von Geräteinformationen</span><span class="sxs-lookup"><span data-stu-id="8916d-123">Get device information</span></span>
<span data-ttu-id="8916d-124">Das [Advanced Hunting-Schema](advanced-hunting-schema-tables.md) stellt umfangreiche Geräteinformationen in verschiedenen Tabellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8916d-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="8916d-125">Beispielsweise bietet die [deviceInfo-Tabelle](advanced-hunting-deviceinfo-table.md) umfassende Geräteinformationen basierend auf Ereignisdaten, die regelmäßig aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="8916d-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="8916d-126">Diese Abfrage verwendet die `DeviceInfo` Tabelle, um zu überprüfen, ob sich ein potenziell gefährdeter Benutzer ( `<account-name>` ) an einem Gerät angemeldet hat, und listet dann die Warnungen auf, die auf diesen Geräten ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="8916d-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="8916d-127">Diese Abfrage verwendet, `kind=inner` um einen [Inner Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)anzugeben, der die Deduplizierung von Werten für linke Seiten verhindert `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="8916d-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="8916d-128">Suchszenarien</span><span class="sxs-lookup"><span data-stu-id="8916d-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="8916d-129">Auflisten von Anmeldeaktivitäten von Benutzern, die e-Mails empfangen haben, die nicht erfolgreich gezappt wurden</span><span class="sxs-lookup"><span data-stu-id="8916d-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="8916d-130">[Zero-Hour Auto Purge (zap)](../office-365-security/zero-hour-auto-purge.md) adressiert schädliche e-Mails, nachdem Sie empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="8916d-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="8916d-131">Wenn zap fehlschlägt, wird möglicherweise böswilliger Code auf dem Gerät ausgeführt, und die Konten werden kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="8916d-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="8916d-132">Diese Abfrage sucht nach Anmeldeaktivitäten, die von den Empfängern von e-Mails vorgenommen wurden, die von Zap nicht erfolgreich behandelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8916d-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="8916d-133">Abrufen von Anmeldeversuchen durch Domänenkonten, die von Anmeldeinformationen Diebstahl betroffen sind</span><span class="sxs-lookup"><span data-stu-id="8916d-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="8916d-134">Diese Abfrage identifiziert zunächst alle Zugriffs Warnungen für Anmeldeinformationen in der `AlertInfo` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8916d-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="8916d-135">Anschließend wird die Tabelle zusammengeführt oder verknüpft `AlertEvidence` , die Sie für die Namen der Zielkonten und Filter für Domänen verbundene Konten analysiert.</span><span class="sxs-lookup"><span data-stu-id="8916d-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="8916d-136">Schließlich wird die Tabelle überprüft, `IdentityLogonEvents` um alle Anmeldeaktivitäten von den mit der Domäne verbundenen Zielkonten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8916d-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="8916d-137">Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="8916d-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="8916d-138">Wenn Sie wissen, dass eine e-Mail-Adresse schädliche Dateien sendet ( `MaliciousSender@example.com` ), können Sie diese Abfrage ausführen, um zu ermitteln, ob Dateien von diesem Absender auf Ihren Geräten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8916d-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="8916d-139">Sie können diese Abfrage beispielsweise verwenden, um Geräte zu identifizieren, die von einer Malware Verteilungs Kampagne betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="8916d-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="8916d-140">Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails</span><span class="sxs-lookup"><span data-stu-id="8916d-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="8916d-141">Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="8916d-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="8916d-142">Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8916d-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="8916d-143">Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern</span><span class="sxs-lookup"><span data-stu-id="8916d-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="8916d-144">Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="8916d-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="8916d-145">Wenn Sie wissen, dass e-Mails von einem bekannten böswilligen Absender ( `MaliciousSender@example.com` ) stammen, können Sie diese Abfrage verwenden, um PowerShell-Aktivitäten aufzulisten und zu überprüfen, die innerhalb von 30 Minuten nach dem Empfang einer e-Mail vom Absender aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="8916d-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="8916d-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8916d-146">Related topics</span></span>
- [<span data-ttu-id="8916d-147">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="8916d-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8916d-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="8916d-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8916d-149">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="8916d-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8916d-150">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="8916d-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8916d-151">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="8916d-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8916d-152">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="8916d-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
