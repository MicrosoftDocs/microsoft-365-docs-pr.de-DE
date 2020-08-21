---
title: Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten
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
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Nachrichten, die während des Filterungsprozesses für den Exchange Online Schutz (EoP) in die Warteschlange gestellt, verzögert oder zurückgesendet wurden.
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827749"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="87835-103">Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="87835-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="87835-104">Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Filterungsprozesses für den Exchange Online Schutz (EoP) in der Warteschlange, verzögert oder zurückgeprallt wurden.</span><span class="sxs-lookup"><span data-stu-id="87835-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="87835-105">Warum werden E-Mails in eine Warteschlange eingereiht?</span><span class="sxs-lookup"><span data-stu-id="87835-105">Why is mail queuing?</span></span>

<span data-ttu-id="87835-106">Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen.</span><span class="sxs-lookup"><span data-stu-id="87835-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="87835-107">Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="87835-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="87835-108">Wie kommt es zu einer Zurückstellung von Nachrichten?</span><span class="sxs-lookup"><span data-stu-id="87835-108">How does a message become deferred?</span></span>

<span data-ttu-id="87835-109">Nachrichten werden zurückgehalten, wenn keine Verbindung mit dem Empfänger Server hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" wie ein Verbindungstimeout, eine Verbindung verweigert oder ein Fehler der 400-Serie zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="87835-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="87835-110">Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="87835-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="87835-111">Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?</span><span class="sxs-lookup"><span data-stu-id="87835-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="87835-112">Nachrichten in Zurückstellung verbleiben für 1 Tag in unseren Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="87835-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="87835-113">Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="87835-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="87835-114">Die ersten Verzögerungen sind 15 Minuten oder weniger, bei nachfolgenden Wiederholungsversuchen (im Laufe des nächsten halben Dutzends) wird das Intervall über mehrere Wiederholungsversuche auf maximal 60 Minuten erhöht.</span><span class="sxs-lookup"><span data-stu-id="87835-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="87835-115">Die Ausdehnung der Intervalldauer ist dynamisch, wobei mehrere Variablen wie Warteschlangengrößen und interne Nachrichtenpriorität berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="87835-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="87835-116">In Basic ist es 15 Minuten (oder weniger), um zu beginnen, dann wird von dort in den nächsten Stunden auf 60 Minuten Max erweitert.</span><span class="sxs-lookup"><span data-stu-id="87835-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="87835-117">Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?</span><span class="sxs-lookup"><span data-stu-id="87835-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="87835-118">Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.</span><span class="sxs-lookup"><span data-stu-id="87835-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
