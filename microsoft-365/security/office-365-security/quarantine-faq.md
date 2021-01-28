---
title: Häufig gestellte Fragen zu isolierten Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können häufig gestellte Fragen und Antworten zu isolierten Nachrichten in Exchange Online Protection (EOP) anzeigen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: abd2304e83d2814cab55d13312535bd94308d8be
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032601"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="a1e8f-103">Häufig gestellte Fragen zu isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a1e8f-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a1e8f-104">Dieses Thema enthält häufig gestellte Fragen und Antworten zu E-Mail-Nachrichten in Quarantäne für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="a1e8f-105">Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zum [Antispamschutz.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="a1e8f-106">Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum [Schutz vor Schadsoftware.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="a1e8f-107">Fragen und Antworten zum Schutz vor Spoofing finden Sie unter Häufig gestellte Fragen zum [Antis spoofing-Schutz.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="a1e8f-108">Wie verwalte ich Nachrichten, die für Schadsoftware isoliert wurden?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="a1e8f-109">Nur Administratoren können Nachrichten verwalten, die für Schadsoftware isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="a1e8f-110">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="a1e8f-111">Wie isoliere ich Spam?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-111">How do I quarantine spam?</span></span>

<span data-ttu-id="a1e8f-112">Standardmäßig werden Nachrichten, die von der Spamfilterung als Spam oder Massen-E-Mail klassifiziert wurden, an das Postfach des Benutzers zugestellt und in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="a1e8f-113">Sie können jedoch antispamrichtlinien erstellen und konfigurieren, um Spam- oder Massen-E-Mail-Nachrichten stattdessen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="a1e8f-114">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1e8f-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="a1e8f-115">Wie vererbe ich Benutzern Zugriff auf die Quarantäne?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="a1e8f-116">Ein Benutzer muss über ein gültiges Konto verfügen, um auf seine eigenen Nachrichten in Quarantäne zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="a1e8f-117">Für eigenständiges EOP müssen Benutzer als E-Mail-Benutzer in EOP dargestellt werden (manuell erstellt oder über verzeichnissynchronisierung erstellt).</span><span class="sxs-lookup"><span data-stu-id="a1e8f-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="a1e8f-118">Weitere Informationen zum Verwalten von Benutzern in eigenständigen EOP-Umgebungen finden Sie unter [Verwalten von E-Mail-Benutzern in EOP.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="a1e8f-119">Auf welche Nachrichten können Endbenutzer in Quarantäne zugreifen?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="a1e8f-120">Benutzer können auf Spam-, Massen-E-Mails und (ab April 2020) Phishingnachrichten zugreifen, bei denen sie Empfänger sind.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="a1e8f-121">Endbenutzer können nicht auf In-Quarantäne-Schadsoftware, Phishing mit hoher  Sicherheit oder Nachrichten zugreifen, die aufgrund der Aktion "Nachricht an gehostete Quarantäne senden" in Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a1e8f-122">Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter "Suchen und Veröffentlichen von Isolierten Nachrichten [als Benutzer".](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="a1e8f-123">Wie lange werden Nachrichten unter Quarantäne gestellt?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="a1e8f-124">Sie konfigurieren mithilfe von Antispamrichtlinien, wie lange Spam-, Phishing- und Massen-E-Mail-Nachrichten in Quarantäne bleiben.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="a1e8f-125">Der Standardwert beträgt 30 Tage, was auch der Höchstwert ist.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="a1e8f-126">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a1e8f-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="a1e8f-127">Bei Nachrichten, die von der Nachrichtenflussregelaktion "Nachricht in gehostete Quarantäne isolieren" isoliert **wurden,** werden die Nachrichten 30 Tage lang in Quarantäne gehalten.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a1e8f-128">Sie können diese Dauer nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-128">You can't configure this duration.</span></span>

<span data-ttu-id="a1e8f-129">Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="a1e8f-130">Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="a1e8f-131">Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und frei geben.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="a1e8f-132">Administratoren können die [Cmdlets "Get-QuarantineMessage"](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) und ["Release-QuarantineMessage"](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwenden, um isolierte Nachrichten in einer Massensendung zu finden und frei zu geben und falsch positive Ergebnisse in Massen zu melden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="a1e8f-133">Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="a1e8f-134">Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?</span><span class="sxs-lookup"><span data-stu-id="a1e8f-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="a1e8f-135">Platzhalter werden im Security & Compliance Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="a1e8f-136">Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige E-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="a1e8f-137">Sie können jedoch Platzhalter in Exchange Online PowerShell oder in der eigenständigen EOP PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="a1e8f-138">Kopieren Sie beispielsweise den folgenden PowerShell-Code in Editor, und speichern Sie die Datei als PS1 an einem Speicherort, den Sie leicht finden können (z. B. C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="a1e8f-138">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="a1e8f-139">Führen Sie dann nach dem Herstellen einer Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) oder [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)den folgenden Befehl aus, um das Skript auszuführen:</span><span class="sxs-lookup"><span data-stu-id="a1e8f-139">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="a1e8f-140">Das Skript führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a1e8f-140">The script does the following actions:</span></span>

- <span data-ttu-id="a1e8f-141">Suchen Sie unveröffentlichte Nachrichten, die von allen Absendern in der Domäne fabrikam als Spam isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-141">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="a1e8f-142">Die maximale Anzahl von Ergebnissen beträgt 50.000 (50 Seiten mit 1000 Ergebnissen).</span><span class="sxs-lookup"><span data-stu-id="a1e8f-142">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="a1e8f-143">Speichern Sie die Ergebnisse in einer CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-143">Save the results to a CSV file.</span></span>
- <span data-ttu-id="a1e8f-144">Geben Sie die übereinstimmenden isolierten Nachrichten für alle ursprünglichen Empfänger frei.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-144">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="a1e8f-145">Nachdem Sie eine Nachricht freigegeben haben, können Sie sie nicht mehr los.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-145">After you release a message, you can't release it again.</span></span>
