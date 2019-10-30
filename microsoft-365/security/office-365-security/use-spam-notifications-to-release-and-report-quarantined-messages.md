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
ms.openlocfilehash: 7042f847dbc8df9d60efc694a07a258eff411f6d
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772209"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="9edcc-104">Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365</span><span class="sxs-lookup"><span data-stu-id="9edcc-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="9edcc-105">Wenn Ihr Administrator Spambenachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der an Ihr Postfach adressierte Nachrichten aufgelistet werden, die stattdessen als Spam identifiziert und isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="9edcc-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="9edcc-106">Wenn Sie Administrator sind und dieses Feature aktivieren möchten, können Sie die Option auswählen, wenn Sie [eine standardmäßige Anti-Spam-Richtlinie ändern](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="9edcc-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="9edcc-107">Die empfangene Nachricht enthält die Anzahl der Spam isolierten Nachrichten, die Sie haben, und das Datum und die Uhrzeit (in Universal Coordinated Time oder UTC) der letzten Nachricht in der Liste.</span><span class="sxs-lookup"><span data-stu-id="9edcc-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="9edcc-108">Die Liste enthält für jede Nachricht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9edcc-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="9edcc-109">**Absender** Der Absender Name und die e-Mail-Adresse der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9edcc-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="9edcc-110">**Betreff** Der Betreffzeilentext der in Quarantäne verschobenen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9edcc-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="9edcc-111">**Datum** Datum und Uhrzeit (UTC-Angabe) der Verschiebung der Nachricht in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="9edcc-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>     
  
<span data-ttu-id="9edcc-112">Dies sind die Aktionen, die Sie mit einer isolierten Nachricht durchführen können:</span><span class="sxs-lookup"><span data-stu-id="9edcc-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="9edcc-113">**Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9edcc-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="9edcc-114">**Überprüfen** Sie, um zum Quarantäne Portal innerhalb des Security and Compliance Centers zu navigieren, wenn Sie andere Aktionen wie Preview oder Release durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="9edcc-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="9edcc-115">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9edcc-115">Be aware of the following:</span></span>
  
- <span data-ttu-id="9edcc-116">Nachrichten, die in Quarantäne verschoben werden, da Sie einer Nachrichtenfluss Regel entsprechen, werden nicht in Nachrichten mit Benutzerquarantäne eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9edcc-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="9edcc-117">Es werden nur Spamquarantäne-Nachrichten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9edcc-117">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="9edcc-118">Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.</span><span class="sxs-lookup"><span data-stu-id="9edcc-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

