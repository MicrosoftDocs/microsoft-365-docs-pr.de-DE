---
title: Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: Dieses Thema bietet Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Microsoft Exchange Online Protection (EOP)-Filterungsprozesses in eine Warteschlange eingereiht, verzögert oder nicht zugestellt wurden.
ms.openlocfilehash: a59fde661dad34dfd7cb3653a571e79615c5276b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081302"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="034d1-103">Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="034d1-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="034d1-104">Dieses Thema bietet Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Microsoft Exchange Online Protection (EOP)-Filterungsprozesses in eine Warteschlange eingereiht, verzögert oder nicht zugestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="034d1-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="034d1-105">**F. Warum werden E-Mails in eine Warteschlange eingereiht?**</span><span class="sxs-lookup"><span data-stu-id="034d1-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="034d1-p101">A. Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen. Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="034d1-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="034d1-109">**F. Wie kommt es zu einer Zurückstellung von Nachrichten?**</span><span class="sxs-lookup"><span data-stu-id="034d1-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="034d1-p102">A. Nachrichten werden zurückgehalten, wenn keine Verbindung zum Server des Empfängers hergestellt werden kann und von diesem ein "temporärer Fehler" (z. B. "Verbindungstimeout" oder "Verbindung abgelehnt") oder ein Fehler der 400er-Serie zurückgegeben wird. Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="034d1-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="034d1-113">**F. Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?**</span><span class="sxs-lookup"><span data-stu-id="034d1-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="034d1-114">A.</span><span class="sxs-lookup"><span data-stu-id="034d1-114">A.</span></span> <span data-ttu-id="034d1-115">Nachrichten in Zurückstellung verbleiben für 1 Tag in unseren Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="034d1-115">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="034d1-116">Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="034d1-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="034d1-117">Die ersten Verzögerungen sind 15 Minuten oder weniger, bei nachfolgenden Wiederholungsversuchen (im Laufe des nächsten halben Dutzends) wird das Intervall über mehrere Wiederholungsversuche auf maximal 60 Minuten erhöht.</span><span class="sxs-lookup"><span data-stu-id="034d1-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="034d1-118">Die Ausdehnung der Intervalldauer ist dynamisch, wobei mehrere Variablen wie Warteschlangengrößen und interne Nachrichtenpriorität berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="034d1-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="034d1-119">In Basic ist es 15 Minuten (oder weniger), um zu beginnen, dann wird von dort in den nächsten Stunden auf 60 Minuten Max erweitert.</span><span class="sxs-lookup"><span data-stu-id="034d1-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="034d1-120">**F. Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?**</span><span class="sxs-lookup"><span data-stu-id="034d1-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="034d1-p104">A. Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.</span><span class="sxs-lookup"><span data-stu-id="034d1-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
