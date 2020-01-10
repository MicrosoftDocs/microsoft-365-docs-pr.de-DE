---
title: In Quarantäne stellen von E-Mail-Nachrichten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Sie können eine Quarantäne für eingehende e-Mail-Nachrichten in Office 365 einrichten, in der eingehende e-Mail-Nachrichten, die als Spam gefiltert wurden, Massen, Phishing-e-Mails und Schadsoftware, für eine spätere Überprüfung aufbewahrt werden können.
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021851"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="06a35-103">In Quarantäne stellen von E-Mail-Nachrichten in Office 365</span><span class="sxs-lookup"><span data-stu-id="06a35-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="06a35-104">Sie können die Quarantäne für eingehende e-Mail-Nachrichten in Office 365 einrichten, in dem Nachrichten, die als Spam, Massen-e-Mails, Phishing-e-Mails, e-Mails mit Schadsoftware und mit einer bestimmten e-Mail-Fluss Regel (auch bekannt als Trasport-Regel) gefiltert wurden, für eine spätere Aufbewahrung aufbewahrt werden können. Bewertung.</span><span class="sxs-lookup"><span data-stu-id="06a35-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="06a35-105">Standardmäßig werden Nachrichten, die nach Phishing-, Malware-und Nachrichtenfluss Regeln gefiltert wurden, an die Quarantäne gesendet, während Nachrichten, die als Spam gefiltert wurden, und Massen-e-Mails an den Junk-e-Mail-Ordner des Empfängers gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="06a35-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="06a35-106">Als Administrator können Sie Spamfilter Richtlinien (auch als Inhaltsfilter Richtlinien bezeichnet) einrichten, um Spam-und Massen-e-Mail-Nachrichten stattdessen an die Quarantäne zu senden.</span><span class="sxs-lookup"><span data-stu-id="06a35-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="06a35-107">Weitere Informationen finden Sie unter [Konfigurieren Ihrer Richtlinien für Spamfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="06a35-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="06a35-108">Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="06a35-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="06a35-109">Benutzer können nur mit ihren eigenen gefilterten Nachrichten in Quarantäne arbeiten.</span><span class="sxs-lookup"><span data-stu-id="06a35-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="06a35-110">Administratoren können Nachrichten in Quarantäne für alle Benutzer suchen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="06a35-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="06a35-111">Vertrauenswürdige Phishing-Nachrichten und Nachrichten, die in Nachrichtenfluss Regelaktionen unter Quarantäne gestellt werden, sind nur in der Administrator Quarantäne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06a35-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="06a35-112">Benutzer können auf Ihre eigenen Phishing-, Spam-und Massen-e-Mail-Nachrichten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="06a35-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="06a35-113">Erfahren Sie mehr über das Arbeiten mit isolierten Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="06a35-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="06a35-114">Verwalten von Nachrichten in Quarantäne als Administrator</span><span class="sxs-lookup"><span data-stu-id="06a35-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="06a35-115">Suchen und Freigeben von isolierten Nachrichten als Benutzer</span><span class="sxs-lookup"><span data-stu-id="06a35-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="06a35-116">Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und melden von Nachrichten in Spamquarantäne</span><span class="sxs-lookup"><span data-stu-id="06a35-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="06a35-117">Häufig gestellte Fragen (FAQ) zur Quarantäne</span><span class="sxs-lookup"><span data-stu-id="06a35-117">Quarantine FAQ</span></span>](quarantine-faq.md)
