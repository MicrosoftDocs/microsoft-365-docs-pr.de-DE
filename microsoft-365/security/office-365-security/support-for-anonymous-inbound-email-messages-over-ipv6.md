---
title: Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie die Unterstützung anonymer Nachrichten aus IPv6-Quellen für Exchange Online Schutz und Exchange Online konfigurieren.
ms.openlocfilehash: c29c1fa450ca2a2e213930c4f4a394aaf462e31d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031990"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6

Exchange Online Protection (EOP) und Exchange Online unterstützen das Empfangen von anonymen eingehenden E-Mails über IPv6 von Absendern, die keine Nachrichten über Transport Layer Security (TLS) senden. Sie können sich für den Empfang von Nachrichten über IPv6 anmelden [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), indem Sie diese Funktionalität vom Microsoft-Support anfordern, indem Sie das Microsoft 365 Admin Center unter öffnen, auf **Support**und dann auf **Neue Dienstanforderung**klicken). Wenn Sie sich nicht für IPv6 entscheiden, erhalten Sie weiterhin Nachrichten über IPv4.
  
Absender, die Nachrichten über IPv6 an den Dienst übermitteln, müssen die folgenden beiden Anforderungen erfüllen:
  
1. Die sendende IPv6-Adresse muss einen gültigen PTR-Eintrag aufweisen ([Reverse-DNS-Datensatz](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) der sendenden IPv6-Adresse). 
    
2. Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](https://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.
    
Diese Anforderungen müssen ungeachtet Ihrer Konfiguration vor der Aktivierung von IPv6 erfüllt sein. Wenn beide Anforderungen erfüllt sind, durchläuft die Nachricht das normale E-Mail-Filterverfahren des Dienstes. Wird nur eine der beiden erfüllt, wird die Nachricht mit einer der folgenden 450-Antworten zurückgewiesen:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Wenn Sie nicht gewählt haben, Nachrichten über IPv6 zu empfangen, und der Absender versucht, eine Nachricht über IPv6 zu erzwingen, indem er manuell eine Verbindung zum Mailserver herstellt, wird die Nachricht mit einer 550-Antwort zurückgewiesen, die in etwa folgendermaßen aussieht:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Weitere Informationen

[Unterstützung für die Validierung von mit DKIM signierten Nachrichten](support-for-validation-of-dkim-signed-messages.md)
  

