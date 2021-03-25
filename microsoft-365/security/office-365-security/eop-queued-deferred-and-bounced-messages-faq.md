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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Häufig gestellte Fragen zu durch EOP in Warteschlangen eingereihten, verzögerten oder nicht zugestellten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Dieses Thema enthält Antworten auf häufig gestellte Fragen zu Nachrichten, die während des Exchange Online Protection (EOP)-Filterprozesses in die Warteschlange eingereiht, verzögert oder nicht gesendet wurden.

## <a name="why-is-mail-queuing"></a>Warum werden E-Mails in eine Warteschlange eingereiht?

Nachrichten werden in eine Warteschlange eingereiht oder zurückgestellt, wenn vom Dienst keine Verbindung zum Server des Empfängers hergestellt werden kann, um sie zuzustellen. Nachrichten werden nicht zurückgestellt, wenn vom Netzwerk des Empfängers ein Fehler der 500er-Serie zurückgegeben wird.

## <a name="how-does-a-message-become-deferred"></a>Wie kommt es zu einer Zurückstellung von Nachrichten?

Nachrichten werden gespeichert, wenn keine Verbindung mit dem Empfängerserver hergestellt werden kann und der Server des Empfängers einen "temporären Fehler" zurücksent, z. B. ein Verbindungs-Time-Out, eine verbindung verweigert oder ein Fehler der 400-Datenreihe. Liegt ein dauerhafter Fehler vor (z. B. ein Fehler der 500er-Serie), wird die Nachricht an den Absender zurückgesendet.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Wie lange werden Nachrichten zurückgestellt, und in welchem Intervall wird der Übertragungsversuch wiederholt?

Nachrichten, die sich in der Verschiebung befinden, verbleiben 1 Tag in unseren Warteschlangen. Wiederholungsversuche hängen davon ab, welcher Fehler vom E-Mail-System des Empfängers zurückgegeben wird. Die ersten Verschiebungen sind 15 Minuten oder weniger, mit nachfolgenden Wiederholungen (über das nächste halbe Dutzend oder so), die das Intervall über mehrere Wiederholungen auf maximal 60 Minuten erhöhen. Die Intervalldauererweiterung ist dynamisch, unter Berücksichtigung mehrerer Variablen wie Warteschlangengrößen und interner Nachrichtenpriorität. Im Wesentlichen sind es 15 Minuten (oder weniger), um zu starten und dann in den nächsten Stunden auf maximal 60 Minuten zu erweitern.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Wie werden Nachrichten aus einer Warteschlange verteilt, nachdem mein E-Mail-Server wiederhergestellt ist?

Nach der Wiederherstellung Ihres E-Mail-Servers werden alle in eine Warteschlange eingereihten Nachrichten automatisch in der Reihenfolge verarbeitet, in der sie empfangen und in die Warteschlange eingereiht wurden, bevor der Server nicht mehr zur Verfügung stand.
