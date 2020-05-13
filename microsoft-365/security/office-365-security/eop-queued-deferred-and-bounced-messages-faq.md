---
title: Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Nachrichten, die während des Filterungsprozesses für den Exchange Online Schutz (EoP) in die Warteschlange gestellt, verzögert oder zurückgesendet wurden.
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206592"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten

Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Filterungsprozesses für den Exchange Online Schutz (EoP) in der Warteschlange, verzögert oder zurückgeprallt wurden.

## <a name="why-is-mail-queuing"></a>Warum werden E-Mails in eine Warteschlange eingereiht?

Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen. Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.

## <a name="how-does-a-message-become-deferred"></a>Wie kommt es zu einer Zurückstellung von Nachrichten?

Nachrichten werden zurückgehalten, wenn keine Verbindung mit dem Empfänger Server hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" wie ein Verbindungstimeout, eine Verbindung verweigert oder ein Fehler der 400-Serie zurückgibt. Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?

Nachrichten in Zurückstellung verbleiben für 1 Tag in unseren Warteschlangen. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Die ersten Verzögerungen sind 15 Minuten oder weniger, bei nachfolgenden Wiederholungsversuchen (im Laufe des nächsten halben Dutzends) wird das Intervall über mehrere Wiederholungsversuche auf maximal 60 Minuten erhöht. Die Ausdehnung der Intervalldauer ist dynamisch, wobei mehrere Variablen wie Warteschlangengrößen und interne Nachrichtenpriorität berücksichtigt werden müssen. In Basic ist es 15 Minuten (oder weniger), um zu beginnen, dann wird von dort in den nächsten Stunden auf 60 Minuten Max erweitert.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?

Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.
