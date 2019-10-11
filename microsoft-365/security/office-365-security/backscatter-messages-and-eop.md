---
title: Rückläufernachrichten und EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Rückläufernachrichten sind die automatischen Unzustellbarkeitsnachrichten, die von E-Mail-Servern, meist als Reaktion auf eingehende Spamnachrichten, gesendet werden. Die Backscatterer DNSBL ist eine Liste von IP-Adressen, von denen Rückläufernachrichten gesendet werden. Es ist keine Spammerliste, daher versuchen wir nicht, unsere Server aus der Backscatterer DNSBL zu löschen.
ms.openlocfilehash: 481203e4a91f24c9ae1992dce402b0d3e951110e
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440562"
---
# <a name="backscatter-messages-and-eop"></a>Rückläufernachrichten und EOP

Rückläufernachrichten sind die automatischen Unzustellbarkeitsnachrichten, die von E-Mail-Servern, meist als Reaktion auf eingehende Spamnachrichten, gesendet werden. Da Exchange Online Protection (EOP) ein Spamfilterdienst ist, werden E-Mail-Nachrichten an nicht vorhandene Empfänger und andere verdächtige Ziele von dem Dienst zurückgewiesen. In diesem Fall generiert EOP eine Unzustellbarkeitsnachricht (Non-Delivery Report, NDR) und übermittelt sie zurück an den „Absender". Da Spammer häufig gefälschte oder ungültige Absenderadressen in ihren Nachrichten verwenden, verursacht die Absenderadresse, an die die Unzustellbarkeitsnachricht gesendet wird, möglicherweise eine Rückläufernachricht. Daraufhin können Postausgangsserver, die mit dem EOP-Netzwerk verbunden sind, auf der Backscatterer DNSBL (DNS Block List, DNS-basierte Sperrliste) gelistet werden. Die Backscatterer DNSBL ist eine Liste von IP-Adressen, von denen Rückläufernachrichten gesendet werden. Es ist keine Spammerliste, daher versuchen wir nicht, unsere Server aus der Backscatterer DNSBL zu löschen.

> [!TIP]
> Laut den Anweisungen auf der Backscatterer-Website stellt die Verwendung des Zurückweisungsmodus für alle eingehenden E-Mails keine empfohlene Konfiguration oder Verwendung des Diensts dar. Er sollte stattdessen im sicheren Modus verwendet werden. Weitere Informationen zum Implementieren der richtigen Rückläuferkonfiguration finden Sie auf der [Website Backscatterer.org](http://www.backscatterer.org/?target=usage).

## <a name="related-topics"></a>Verwandte Themen

[Erweiterte Spam Filterungsoptionen](advanced-spam-filtering-asf-options.md)
