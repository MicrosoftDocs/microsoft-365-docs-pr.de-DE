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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterungsprozesses in die Warteschlange eingereiht, zurückgestellt oder nicht gesendet wurden.

## <a name="why-is-mail-queuing"></a>Warum werden E-Mails in eine Warteschlange eingereiht?

Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen. Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.

## <a name="how-does-a-message-become-deferred"></a>Wie kommt es zu einer Zurückstellung von Nachrichten?

Nachrichten werden gespeichert, wenn keine Verbindung mit dem Empfängerserver hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" zurück gibt, z. B. ein Verbindungs-Time-Out, eine verweigerte Verbindung oder ein Fehler der 400er-Serie. Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?

In die Warteschlange gestellte Nachrichten verbleiben 1 Tag in der Warteschlange. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Die ersten Wiederholungen liegen bei maximal 15 Minuten, bei nachfolgenden Wiederholungen (über das nächste halbe Dutzend) wird das Intervall über mehrere Wiederholungen auf maximal 60 Minuten erhöht. Die Intervalldauererweiterung ist dynamisch und berücksichtigt mehrere Variablen wie Warteschlangengrößen und interne Nachrichtenpriorität. Im Wesentlichen dauert der Start 15 Minuten (oder weniger), dann wird er in den nächsten Stunden auf maximal 60 Minuten erweitert.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?

Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.
