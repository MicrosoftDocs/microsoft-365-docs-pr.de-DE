---
title: Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 1cd38798aa644b79c8f1d6362edd17a515b5c98d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598232"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="80126-103">Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6</span><span class="sxs-lookup"><span data-stu-id="80126-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="80126-104">Exchange Online Protection (EOP) und Exchange Online unterstützen das Empfangen von anonymen eingehenden E-Mails über IPv6 von Absendern, die keine Nachrichten über Transport Layer Security (TLS) senden.</span><span class="sxs-lookup"><span data-stu-id="80126-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="80126-105">Sie können sich für den Empfang von Nachrichten über IPv6 anmelden [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), indem Sie diese Funktionalität vom Microsoft-Support anfordern, indem Sie das Microsoft 365 Admin Center unter öffnen, auf **Support**und dann auf **Neue Dienstanforderung**klicken).</span><span class="sxs-lookup"><span data-stu-id="80126-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="80126-106">Wenn Sie sich nicht für IPv6 entscheiden, erhalten Sie weiterhin Nachrichten über IPv4.</span><span class="sxs-lookup"><span data-stu-id="80126-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="80126-107">Absender, die Nachrichten über IPv6 an den Dienst übermitteln, müssen die folgenden beiden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="80126-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="80126-108">Die sendende IPv6-Adresse muss einen gültigen PTR-Eintrag aufweisen ([Reverse-DNS-Datensatz](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) der sendenden IPv6-Adresse).</span><span class="sxs-lookup"><span data-stu-id="80126-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="80126-109">Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](https://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.</span><span class="sxs-lookup"><span data-stu-id="80126-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="80126-p102">Diese Anforderungen müssen ungeachtet Ihrer Konfiguration vor der Aktivierung von IPv6 erfüllt sein. Wenn beide Anforderungen erfüllt sind, durchläuft die Nachricht das normale E-Mail-Filterverfahren des Dienstes. Wird nur eine der beiden erfüllt, wird die Nachricht mit einer der folgenden 450-Antworten zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="80126-p102">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="80126-113">Wenn Sie nicht gewählt haben, Nachrichten über IPv6 zu empfangen, und der Absender versucht, eine Nachricht über IPv6 zu erzwingen, indem er manuell eine Verbindung zum Mailserver herstellt, wird die Nachricht mit einer 550-Antwort zurückgewiesen, die in etwa folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="80126-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="80126-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80126-114">For more information</span></span>

[<span data-ttu-id="80126-115">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="80126-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

