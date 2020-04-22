---
title: Häufig gestellte Fragen (FAQ) zur Quarantäne
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Antworten auf häufig gestellte Fragen zur Quarantäne in Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634424"
---
# <a name="quarantine-faq"></a><span data-ttu-id="555f2-103">Häufig gestellte Fragen (FAQ) zur Quarantäne</span><span class="sxs-lookup"><span data-stu-id="555f2-103">Quarantine FAQ</span></span>

<span data-ttu-id="555f2-104">Dieses Thema enthält häufig gestellte Fragen und Antworten zur Quarantäne für Microsoft 365-Kunden mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutz Kunden (EoP) ohne Exchange Online Postfächer.</span><span class="sxs-lookup"><span data-stu-id="555f2-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="555f2-105">F: Wie kann ich Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden?</span><span class="sxs-lookup"><span data-stu-id="555f2-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="555f2-106">Nur Administratoren können Nachrichten verwalten, die auf Schadsoftware unter Quarantäne gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="555f2-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="555f2-107">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="555f2-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="555f2-108">F: Wie kann ich Spam isolieren?</span><span class="sxs-lookup"><span data-stu-id="555f2-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="555f2-109">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-109">A.</span></span> <span data-ttu-id="555f2-110">Standardmäßig werden Nachrichten, die durch Spamfilterung als Spam oder Massen-e-Mail klassifiziert werden, an das Postfach des Benutzers übermittelt und in den Junk-e-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="555f2-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="555f2-111">Sie können jedoch Anti-Spam-Richtlinien erstellen und konfigurieren, um Spam-oder Massen-e-Mail-Nachrichten stattdessen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="555f2-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="555f2-112">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="555f2-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="555f2-113">F.: Wie kann ich Benutzern Zugriff auf die Quarantäne gewähren?</span><span class="sxs-lookup"><span data-stu-id="555f2-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="555f2-114">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-114">A.</span></span> <span data-ttu-id="555f2-115">Ein Benutzer muss über ein gültiges Konto verfügen, um in der Quarantäne auf seine eigenen Nachrichten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="555f2-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="555f2-116">Eigenständige EoP erfordert, dass Benutzer als e-Mail-Benutzer in EoP dargestellt werden (manuell erstellt oder über die Verzeichnissynchronisierung erstellt).</span><span class="sxs-lookup"><span data-stu-id="555f2-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="555f2-117">Weitere Informationen zum Verwalten von Benutzern in eigenständigen EoP-Umgebungen finden Sie unter [Verwalten von e-Mail-Benutzern in EoP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="555f2-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="555f2-118">F.: auf welche Nachrichten kann der Benutzer in der Quarantäne zugreifen?</span><span class="sxs-lookup"><span data-stu-id="555f2-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="555f2-119">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-119">A.</span></span> <span data-ttu-id="555f2-120">Benutzer können auf Spam, Massen-e-Mails und (ab April 2020) Phishing-Nachrichten, bei denen es sich um einen Empfänger handelt, zugreifen.</span><span class="sxs-lookup"><span data-stu-id="555f2-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="555f2-121">Endbenutzer können nicht auf isolierte Schadsoftware, Phishing mit hoher Zuverlässigkeit oder Nachrichten zugreifen, die aufgrund der **Nachrichtenübermittlung an die gehostete Quarantäne** Aktion in Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="555f2-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="555f2-122">Weitere Informationen zu Benutzern, die auf isolierte Nachrichten zugreifen, finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="555f2-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="555f2-123">F.: wie lange werden Nachrichten in der Quarantäne aufbewahrt?</span><span class="sxs-lookup"><span data-stu-id="555f2-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="555f2-124">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-124">A.</span></span> <span data-ttu-id="555f2-125">Sie konfigurieren, wie lange Spam-, Phishing-und Massen-e-Mail-Nachrichten mithilfe von antispamregeln in der Quarantäne aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="555f2-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="555f2-126">Der Standardwert ist 30 Tage, was auch das Maximum ist.</span><span class="sxs-lookup"><span data-stu-id="555f2-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="555f2-127">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="555f2-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="555f2-128">Bei Nachrichten, die von der Aktion Nachrichtenfluss Regel unter Quarantäne gestellt wurden, die **Nachricht an die gehostete Quarantäne senden**, werden die Nachrichten 30 Tage lang in Quarantäne aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="555f2-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="555f2-129">Diese Dauer kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="555f2-129">You can't configure this duration.</span></span>

<span data-ttu-id="555f2-130">Nach Ablauf des Zeitraums werden die Nachrichten gelöscht und können nicht mehr hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="555f2-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="555f2-131">F.: kann ich mehr als eine isolierte Nachricht gleichzeitig freigeben oder melden?</span><span class="sxs-lookup"><span data-stu-id="555f2-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="555f2-132">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-132">A.</span></span> <span data-ttu-id="555f2-133">Im Security & Compliance Center können Sie bis zu 100 Nachrichten gleichzeitig auswählen und freigeben.</span><span class="sxs-lookup"><span data-stu-id="555f2-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="555f2-134">Administratoren können die Cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) und [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) in Exchange Online PowerShell oder eigenständiger Exchange Online Protection PowerShell verwenden, um isolierte Nachrichten massenhaft zu finden und freizugeben und falsch positive Ergebnisse in Massen zu melden.</span><span class="sxs-lookup"><span data-stu-id="555f2-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="555f2-135">F.: werden Platzhalter bei der Suche nach isolierten Nachrichten unterstützt?</span><span class="sxs-lookup"><span data-stu-id="555f2-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="555f2-136">Kann ich für eine bestimmte Domäne nach Nachricht in Quarantäne suchen?</span><span class="sxs-lookup"><span data-stu-id="555f2-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="555f2-137">A:</span><span class="sxs-lookup"><span data-stu-id="555f2-137">A.</span></span> <span data-ttu-id="555f2-138">Platzhalter werden im Security & Compliance Center nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="555f2-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="555f2-139">Wenn Sie beispielsweise nach einem Absender suchen, müssen Sie die vollständige e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="555f2-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="555f2-140">Sie können jedoch Platzhalter in Exchange Online PowerShell oder Exchange Online Protection PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="555f2-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="555f2-141">Führen Sie beispielsweise den folgenden Befehl aus, um nach Nachrichten mit Spamquarantäne von allen Absendern in der Domäne contoso.com zu suchen:</span><span class="sxs-lookup"><span data-stu-id="555f2-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="555f2-142">Führen Sie dann den folgenden Befehl aus, um diese Nachrichten an alle ursprünglichen Empfänger freizugeben:</span><span class="sxs-lookup"><span data-stu-id="555f2-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="555f2-143">Nachdem Sie eine Nachricht veröffentlicht haben, können Sie Sie nicht erneut freigeben.</span><span class="sxs-lookup"><span data-stu-id="555f2-143">After you release a message, you can't release it again.</span></span>
