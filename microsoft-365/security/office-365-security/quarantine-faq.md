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
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206631"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="6c381-103">Häufig gestellte Fragen zu isolierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="6c381-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6c381-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="6c381-104">**Applies to**</span></span>
- [<span data-ttu-id="6c381-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6c381-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6c381-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="6c381-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6c381-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c381-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6c381-108">Dieses Thema enthält häufig gestellte Fragen und Antworten zu isolierten E-Mail-Nachrichten für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="6c381-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="6c381-109">Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zu [Antispamschutz](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="6c381-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="6c381-110">Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum Schutz [vor Schadsoftware.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6c381-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="6c381-111">Fragen und Antworten zum Schutz vor Spoofing finden Sie unter Häufig gestellte Fragen zum Schutz [vor Spoofing.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="6c381-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="6c381-112">Wie verwalte ich Nachrichten, die für Schadsoftware isoliert wurden?</span><span class="sxs-lookup"><span data-stu-id="6c381-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="6c381-113">Nur Administratoren können Nachrichten verwalten, die für Schadsoftware isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="6c381-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="6c381-114">Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="6c381-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="6c381-115">Wie isoliere ich Spam?</span><span class="sxs-lookup"><span data-stu-id="6c381-115">How do I quarantine spam?</span></span>

<span data-ttu-id="6c381-116">Standardmäßig werden Nachrichten, die per Spamfilterung als Spam oder Massen-E-Mail klassifiziert werden, an das Postfach des Benutzers zugestellt und in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="6c381-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="6c381-117">Sie können jedoch Antispamrichtlinien erstellen und konfigurieren, um Spam- oder Massen-E-Mail-Nachrichten zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="6c381-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="6c381-118">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6c381-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="6c381-119">Wie kann ich Benutzern Zugriff auf die Quarantäne ermöglichen?</span><span class="sxs-lookup"><span data-stu-id="6c381-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="6c381-120">Ein Benutzer muss über ein gültiges Konto verfügen, um in Quarantäne auf eigene Nachrichten zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="6c381-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="6c381-121">Eigenständiges EOP erfordert, dass Benutzer in EOP als E-Mail-Benutzer dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt).</span><span class="sxs-lookup"><span data-stu-id="6c381-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="6c381-122">Weitere Informationen zum Verwalten von Benutzern in eigenständigen EOP-Umgebungen finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6c381-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="6c381-123">Auf welche Nachrichten können Endbenutzer in Quarantäne zugreifen?</span><span class="sxs-lookup"><span data-stu-id="6c381-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="6c381-124">Benutzer können auf Spam-, Massen-E-Mails und (ab April 2020) Phishingnachrichten zugreifen, wenn sie Empfänger sind.</span><span class="sxs-lookup"><span data-stu-id="6c381-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="6c381-125">Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher  Vertrauenssicherheit oder Nachrichten zugreifen, die aufgrund der Nachricht an die gehostete Quarantäneaktion in Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="6c381-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="6c381-126">Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter Suchen und Veröffentlichen isolierter Nachrichten [als Benutzer.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="6c381-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="6c381-127">Wie lange werden Nachrichten in der Quarantäne aufbewahrt?</span><span class="sxs-lookup"><span data-stu-id="6c381-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="6c381-128">Sie konfigurieren, wie lange Spam-, Phishing- und Massen-E-Mail-Nachrichten mithilfe von Antispamrichtlinien in der Quarantäne aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="6c381-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="6c381-129">Der Standardwert ist 30 Tage, was auch das Maximum ist.</span><span class="sxs-lookup"><span data-stu-id="6c381-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="6c381-130">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6c381-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="6c381-131">Für Nachrichten, die von der Nachrichtenflussregelaktion isoliert wurden **Die** Nachricht in die gehostete Quarantäne senden, werden die Nachrichten 30 Tage lang in Quarantäne gehalten.</span><span class="sxs-lookup"><span data-stu-id="6c381-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="6c381-132">Sie können diese Dauer nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c381-132">You can't configure this duration.</span></span>

<span data-ttu-id="6c381-133">Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c381-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="6c381-134">Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?</span><span class="sxs-lookup"><span data-stu-id="6c381-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="6c381-135">Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6c381-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="6c381-136">Administratoren können die [Cmdlets Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) und [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwenden, um isolierte Nachrichten in Massen zu finden und frei zu geben und falsch positive Ergebnisse in Massen zu melden.</span><span class="sxs-lookup"><span data-stu-id="6c381-136">Admins can use the the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="6c381-137">Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="6c381-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="6c381-138">Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?</span><span class="sxs-lookup"><span data-stu-id="6c381-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="6c381-139">Platzhalter werden im Security & Compliance Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6c381-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="6c381-140">Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige E-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="6c381-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="6c381-141">Sie können jedoch Platzhalter in Exchange Online PowerShell oder in der eigenständigen EOP PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c381-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="6c381-142">Kopieren Sie beispielsweise den folgenden PowerShell-Code in NotePad, und speichern Sie die Datei als PS1 an einem Speicherort, den Sie leicht finden können (z. B. C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="6c381-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="6c381-143">Führen Sie dann nach der Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) oder [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)den folgenden Befehl aus, um das Skript auszuführen:</span><span class="sxs-lookup"><span data-stu-id="6c381-143">Then, after you connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="6c381-144">Das Skript führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6c381-144">The script does the following actions:</span></span>

- <span data-ttu-id="6c381-145">Suchen Sie unveröffentlichte Nachrichten, die von allen Absendern in der fabrikam-Domäne als Spam isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="6c381-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="6c381-146">Die maximale Anzahl der Ergebnisse beträgt 50.000 (50 Seiten mit 1.000 Ergebnissen).</span><span class="sxs-lookup"><span data-stu-id="6c381-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="6c381-147">Speichern Sie die Ergebnisse in einer CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="6c381-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="6c381-148">Geben Sie die übereinstimmenden isolierten Nachrichten für alle ursprünglichen Empfänger frei.</span><span class="sxs-lookup"><span data-stu-id="6c381-148">Release the matching quarantined messages to all original recipients.</span></span>

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

<span data-ttu-id="6c381-149">Nachdem Sie eine Nachricht veröffentlicht haben, können Sie sie nicht mehr veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6c381-149">After you release a message, you can't release it again.</span></span>