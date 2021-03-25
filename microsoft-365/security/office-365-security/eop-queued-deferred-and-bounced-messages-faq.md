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
description: Hier finden Sie Antworten auf die häufigsten Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterprozesses in die Warteschlange eingereiht, verzögert oder nicht gesendet wurden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206791"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="84b00-103">Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="84b00-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="84b00-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="84b00-104">**Applies to**</span></span>
- [<span data-ttu-id="84b00-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="84b00-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="84b00-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="84b00-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="84b00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84b00-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="84b00-108">Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterprozesses in die Warteschlange eingereiht, verzögert oder nicht gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="84b00-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="84b00-109">Warum werden E-Mails in eine Warteschlange eingereiht?</span><span class="sxs-lookup"><span data-stu-id="84b00-109">Why is mail queuing?</span></span>

<span data-ttu-id="84b00-110">Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen.</span><span class="sxs-lookup"><span data-stu-id="84b00-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="84b00-111">Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84b00-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="84b00-112">Wie kommt es zu einer Zurückstellung von Nachrichten?</span><span class="sxs-lookup"><span data-stu-id="84b00-112">How does a message become deferred?</span></span>

<span data-ttu-id="84b00-113">Nachrichten werden gespeichert, wenn keine Verbindung mit dem Empfängerserver hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" zurücksent, z. B. ein Verbindungs-Time-Out, eine verbindung verweigert oder ein Fehler der 400-Datenreihe.</span><span class="sxs-lookup"><span data-stu-id="84b00-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="84b00-114">Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="84b00-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="84b00-115">Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?</span><span class="sxs-lookup"><span data-stu-id="84b00-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="84b00-116">Nachrichten, die sich in der Verschiebung befinden, verbleiben 1 Tag in unseren Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="84b00-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="84b00-117">Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84b00-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="84b00-118">Die ersten Verschiebungen sind 15 Minuten oder weniger, mit nachfolgenden Wiederholungen (über das nächste halbe Dutzend oder so), die das Intervall über mehrere Wiederholungen auf maximal 60 Minuten erhöhen.</span><span class="sxs-lookup"><span data-stu-id="84b00-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="84b00-119">Die Intervalldauererweiterung ist dynamisch, unter Berücksichtigung mehrerer Variablen wie Warteschlangengrößen und interner Nachrichtenpriorität.</span><span class="sxs-lookup"><span data-stu-id="84b00-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="84b00-120">Im Wesentlichen sind es 15 Minuten (oder weniger), um zu starten und dann in den nächsten Stunden auf maximal 60 Minuten zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="84b00-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="84b00-121">Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?</span><span class="sxs-lookup"><span data-stu-id="84b00-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="84b00-122">Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.</span><span class="sxs-lookup"><span data-stu-id="84b00-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
