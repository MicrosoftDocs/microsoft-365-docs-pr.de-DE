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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier finden Sie Antworten auf die häufigsten Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterungsprozesses in die Warteschlange eingereiht, zurückgestellt oder nicht gesendet wurden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165427"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="5504e-103">Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="5504e-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5504e-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="5504e-104">**Applies to**</span></span>
- [<span data-ttu-id="5504e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5504e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="5504e-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="5504e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="5504e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5504e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5504e-108">Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterungsprozesses in die Warteschlange eingereiht, zurückgestellt oder nicht gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5504e-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="5504e-109">Warum werden E-Mails in eine Warteschlange eingereiht?</span><span class="sxs-lookup"><span data-stu-id="5504e-109">Why is mail queuing?</span></span>

<span data-ttu-id="5504e-110">Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen.</span><span class="sxs-lookup"><span data-stu-id="5504e-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="5504e-111">Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5504e-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="5504e-112">Wie kommt es zu einer Zurückstellung von Nachrichten?</span><span class="sxs-lookup"><span data-stu-id="5504e-112">How does a message become deferred?</span></span>

<span data-ttu-id="5504e-113">Nachrichten werden gespeichert, wenn keine Verbindung mit dem Empfängerserver hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" zurück gibt, z. B. ein Verbindungs-Time-Out, eine verweigerte Verbindung oder ein Fehler der 400er-Serie.</span><span class="sxs-lookup"><span data-stu-id="5504e-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="5504e-114">Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="5504e-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="5504e-115">Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?</span><span class="sxs-lookup"><span data-stu-id="5504e-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="5504e-116">In die Warteschlange gestellte Nachrichten verbleiben 1 Tag in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="5504e-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="5504e-117">Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5504e-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="5504e-118">Die ersten Wiederholungen liegen bei maximal 15 Minuten, bei nachfolgenden Wiederholungen (über das nächste halbe Dutzend) wird das Intervall über mehrere Wiederholungen auf maximal 60 Minuten erhöht.</span><span class="sxs-lookup"><span data-stu-id="5504e-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="5504e-119">Die Intervalldauererweiterung ist dynamisch und berücksichtigt mehrere Variablen wie Warteschlangengrößen und interne Nachrichtenpriorität.</span><span class="sxs-lookup"><span data-stu-id="5504e-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="5504e-120">Im Wesentlichen dauert der Start 15 Minuten (oder weniger), dann wird er in den nächsten Stunden auf maximal 60 Minuten erweitert.</span><span class="sxs-lookup"><span data-stu-id="5504e-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="5504e-121">Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?</span><span class="sxs-lookup"><span data-stu-id="5504e-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="5504e-122">Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.</span><span class="sxs-lookup"><span data-stu-id="5504e-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
