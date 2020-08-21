---
title: Häufig gestellte Fragen zu Nachrichten in Quarantäne
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Administratoren können häufig gestellte Fragen und Antworten zu unter Quarantäne gestellten Nachrichten in Exchange Online Protection (EoP) anzeigen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826789"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="4428b-103">Häufig gestellte Fragen zu Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="4428b-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="4428b-104">Dieses Thema enthält häufig gestellte Fragen und Antworten zu isolierten e-Mail-Nachrichten für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern.</span><span class="sxs-lookup"><span data-stu-id="4428b-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="4428b-105">Fragen und Antworten zum Antispamschutz finden Sie unter [Anti-Spam Protection FAQ](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="4428b-106">Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="4428b-107">Fragen und Antworten zum Schutz vor Spoofing finden Sie unter [Anti-Spoofing-Schutz – FAQ](anti-spoofing-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="4428b-108">Wie kann ich Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden?</span><span class="sxs-lookup"><span data-stu-id="4428b-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="4428b-109">Nur Administratoren können Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4428b-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="4428b-110">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="4428b-111">Wie kann ich Spam isolieren?</span><span class="sxs-lookup"><span data-stu-id="4428b-111">How do I quarantine spam?</span></span>

<span data-ttu-id="4428b-112">Standardmäßig werden Nachrichten, die durch Spamfilterung als Spam oder Massen-e-Mail klassifiziert werden, an das Postfach des Benutzers übermittelt und in den Junk-e-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="4428b-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="4428b-113">Sie können jedoch Anti-Spam-Richtlinien erstellen und konfigurieren, um Spam-oder Massen-e-Mail-Nachrichten stattdessen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="4428b-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="4428b-114">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="4428b-115">Wie gebe ich Benutzern Zugriff auf die Quarantäne?</span><span class="sxs-lookup"><span data-stu-id="4428b-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="4428b-116">Ein Benutzer muss über ein gültiges Konto verfügen, um in der Quarantäne auf seine eigenen Nachrichten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4428b-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="4428b-117">Eigenständige EoP erfordert, dass Benutzer als e-Mail-Benutzer in EoP dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt).</span><span class="sxs-lookup"><span data-stu-id="4428b-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="4428b-118">Weitere Informationen zum Verwalten von Benutzern in eigenständigen EoP-Umgebungen finden Sie unter [Verwalten von e-Mail-Benutzern in EoP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="4428b-119">Auf welche Nachrichten kann der Benutzer in der Quarantäne zugreifen?</span><span class="sxs-lookup"><span data-stu-id="4428b-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="4428b-120">Benutzer können auf Spam, Massen-e-Mails und (ab April 2020) Phishing-Nachrichten zugreifen, wenn Sie ein Empfänger sind.</span><span class="sxs-lookup"><span data-stu-id="4428b-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="4428b-121">Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher Zuverlässigkeit oder Nachrichten zugreifen, die aufgrund der **Nachrichtenübermittlung an die gehostete Quarantäne** Aktion in Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4428b-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4428b-122">Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4428b-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="4428b-123">Wie lange werden Nachrichten in der Quarantäne aufbewahrt?</span><span class="sxs-lookup"><span data-stu-id="4428b-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="4428b-124">Sie konfigurieren, wie lange Spam-, Phishing-und Massen-e-Mail-Nachrichten mithilfe von antispamregeln in der Quarantäne aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="4428b-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="4428b-125">Der Standardwert ist 30 Tage, was auch das Maximum ist.</span><span class="sxs-lookup"><span data-stu-id="4428b-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="4428b-126">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4428b-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="4428b-127">Bei Nachrichten, die von der Aktion Nachrichtenfluss Regel unter Quarantäne gestellt wurden, die **Nachricht an die gehostete Quarantäne senden**, werden die Nachrichten 30 Tage lang in Quarantäne aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="4428b-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="4428b-128">Diese Dauer kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4428b-128">You can't configure this duration.</span></span>

<span data-ttu-id="4428b-129">Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4428b-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="4428b-130">Kann ich mehr als eine Quarantänenachricht gleichzeitig freigeben oder melden?</span><span class="sxs-lookup"><span data-stu-id="4428b-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="4428b-131">Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und freigeben.</span><span class="sxs-lookup"><span data-stu-id="4428b-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="4428b-132">Administratoren können die Cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) und [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell oder eigenständiger EoP-PowerShell verwenden, um isolierte Nachrichten massenhaft zu finden und freizugeben und falsch positive Ergebnisse in Massen zu melden.</span><span class="sxs-lookup"><span data-stu-id="4428b-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="4428b-133">Werden bei der Suche nach in der Quarantäne isolierte Nachrichten Platzhalterzeichen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="4428b-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="4428b-134">Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?</span><span class="sxs-lookup"><span data-stu-id="4428b-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="4428b-135">Platzhalter werden im Security & Compliance Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4428b-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="4428b-136">Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="4428b-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="4428b-137">Sie können jedoch Platzhalter in Exchange Online PowerShell oder eigenständiger EoP PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="4428b-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="4428b-138">Führen Sie beispielsweise den folgenden Befehl aus, um nach Nachrichten mit Spamquarantäne von allen Absendern in der Domäne contoso.com zu suchen:</span><span class="sxs-lookup"><span data-stu-id="4428b-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="4428b-139">Führen Sie dann den folgenden Befehl aus, um diese Nachrichten an alle ursprünglichen Empfänger freizugeben:</span><span class="sxs-lookup"><span data-stu-id="4428b-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="4428b-140">Nachdem Sie eine Nachricht veröffentlicht haben, können Sie Sie nicht erneut freigeben.</span><span class="sxs-lookup"><span data-stu-id="4428b-140">After you release a message, you can't release it again.</span></span>
