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
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 83a4b7b52508002ad9bc5c27e1ebf68677808444
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087934"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="59373-104">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="59373-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="59373-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="59373-105">**Applies to:**</span></span>
- <span data-ttu-id="59373-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="59373-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="59373-107">Die [erweiterte Suche](advanced-hunting-overview.md) in Microsoft Threat Protection bietet Ihnen die Möglichkeit, auf Ihren Windows-Geräten und in Ihren Office 365-E-Mails proaktiv nach Bedrohungen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="59373-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="59373-108">Nachfolgend finden Sie einige Suchszenarien und Beispielabfragen, die Ihnen dabei helfen, zu verstehen, wie Sie Abfragen erstellen können, die sowohl Geräte als auch E-Mails umfassen.</span><span class="sxs-lookup"><span data-stu-id="59373-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="59373-109">Abrufen von Benutzerkonten aus E-Mail-Adressen</span><span class="sxs-lookup"><span data-stu-id="59373-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="59373-110">Beim Erstellen von Abfragen über [Tabellen, die Geräte und E-Mail-Nachrichten enthalten](advanced-hunting-schema-tables.md), müssen Sie wahrscheinlich Benutzerkontonamen aus E-Mail-Adressen von Absendern oder Empfängern abrufen.</span><span class="sxs-lookup"><span data-stu-id="59373-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="59373-111">Verwenden Sie dazu den *lokalen Host* aus der E-Mail-Adresse:</span><span class="sxs-lookup"><span data-stu-id="59373-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="59373-112">Diese Normalisierungstechnik wird in den folgenden Szenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="59373-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="59373-113">Suchszenarien</span><span class="sxs-lookup"><span data-stu-id="59373-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="59373-114">Überprüfen, ob Dateien bekannter bösartiger Absender auf Ihren Geräten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="59373-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="59373-115">Angenommen, Sie kennen eine E-Mail-Adresse, von der aus schädliche Dateien gesendet werden, dann können Sie diese Abfrage ausführen, um zu ermitteln, ob Dateien von diesem Absender auf Ihren Geräten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="59373-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="59373-116">Sie können die Abfrage beispielsweise verwenden, um die Anzahl der von einer Schadsoftware-Verteilungskampagne betroffenen Geräte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="59373-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="59373-117">Überprüfen von Anmeldeversuchen nach dem Empfang von bösartigen E-Mails</span><span class="sxs-lookup"><span data-stu-id="59373-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="59373-118">Diese Abfrage ermittelt die 10 neuesten Anmeldungen, die von E-Mail-Empfängern innerhalb von 30 Minuten nach dem Empfang bekannter bösartiger E-Mails ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="59373-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="59373-119">Sie können diese Abfrage verwenden, um zu überprüfen, ob die Konten der E-Mail-Empfänger kompromittiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59373-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="59373-120">Überprüfen von PowerShell-Aktivitäten nach dem Empfang von E-Mails von bekannten bösartigen Absendern</span><span class="sxs-lookup"><span data-stu-id="59373-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="59373-121">Bösartige E-Mail-Nachrichten enthalten häufig Dokumente und andere speziell gestaltete Anlagen, die PowerShell-Befehle ausführen, um zusätzliche Nutzlasten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="59373-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="59373-122">Wenn Sie wissen, dass Sie E-Mail-Nachrichten eines bekannten bösartigen Absenders erhalten haben, können Sie diese Abfrage verwenden, um PowerShell-Aktivitäten aufzulisten und zu überprüfen, die innerhalb von 30 Minuten nach dem Empfang einer E-Mail von diesem Absender ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="59373-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```kusto
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

## <a name="related-topics"></a><span data-ttu-id="59373-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="59373-123">Related topics</span></span>
- [<span data-ttu-id="59373-124">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="59373-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59373-125">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="59373-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="59373-126">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="59373-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="59373-127">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="59373-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="59373-128">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="59373-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
