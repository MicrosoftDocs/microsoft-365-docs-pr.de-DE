---
title: Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Wenn Ihr Administrator die Benachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der Nachrichten aufgelistet werden, die an Ihr Postfach gesendet wurden, die als Spam-, Massen-oder Phishing-Nachrichten identifiziert wurden. Nach der Benachrichtigung können Sie Nachrichten freigeben oder melden.
ms.openlocfilehash: c8253ba7002ac88932cbef07508215a3d9a65f75
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806708"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="482ad-104">Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365</span><span class="sxs-lookup"><span data-stu-id="482ad-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="482ad-105">Wenn Ihr Administrator Spambenachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der an Ihr Postfach adressierte Nachrichten aufgelistet werden, die stattdessen als Spam identifiziert und isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="482ad-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="482ad-106">Wenn Sie Administrator sind und dieses Feature aktivieren möchten, können Sie die Option auswählen, wenn Sie [eine standardmäßige Anti-Spam-Richtlinie ändern](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="482ad-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="482ad-107">Die empfangene Nachricht enthält die Anzahl der Spam isolierten Nachrichten, die Sie haben, und das Datum und die Uhrzeit (in Universal Coordinated Time oder UTC) der letzten Nachricht in der Liste.</span><span class="sxs-lookup"><span data-stu-id="482ad-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="482ad-108">Die Liste enthält für jede Nachricht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="482ad-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="482ad-109">**Absender** Der Absender Name und die e-Mail-Adresse der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="482ad-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="482ad-110">**Betreff** Der Betreffzeilentext der in Quarantäne verschobenen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="482ad-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="482ad-111">**Datum** Datum und Uhrzeit (UTC-Angabe) der Verschiebung der Nachricht in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="482ad-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="482ad-112">Dies sind die Aktionen, die Sie mit einer isolierten Nachricht durchführen können:</span><span class="sxs-lookup"><span data-stu-id="482ad-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="482ad-113">**Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="482ad-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="482ad-114">**Release** wenn es sich bei der Nachricht nicht um Spam handelt und Sie möchten, dass Office 365 die Nachricht an Ihr Postfach sendet.</span><span class="sxs-lookup"><span data-stu-id="482ad-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="482ad-115">**Überprüfen** Sie, um zum Quarantäne Portal innerhalb des Security and Compliance Centers zu navigieren, wenn Sie andere Aktionen wie Preview oder Release durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="482ad-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="482ad-116">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="482ad-116">Be aware of the following:</span></span>

- <span data-ttu-id="482ad-117">Nachrichten, die in Quarantäne verschoben werden, da Sie einer Nachrichtenfluss Regel entsprechen, werden nicht in Nachrichten mit Benutzerquarantäne eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="482ad-117">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="482ad-118">Es werden nur Spamquarantäne-Nachrichten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="482ad-118">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="482ad-119">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="482ad-119">You can only release a message and report it as a false positive (not junk) once.</span></span>
