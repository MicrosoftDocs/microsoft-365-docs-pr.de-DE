---
title: Pool für besonders riskante Zustellungen für ausgehende Nachrichten
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Wenn das E-Mail-System eines Kunden durch Schadsoftware oder einen böswilligen Spamangriff kompromittiert wurde und ausgehende Spamnachrichten durch den gehosteten Filterdienst sendet, kann dies dazu führen, dass die IP-Adressen der Office 365-Server im Rechenzentrum in Blockierungslisten von Drittanbietern aufgenommen werden.
ms.openlocfilehash: 5b9241dead5b40e9f216ecd3023d6f8b86fb0205
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081253"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="bda5d-103">Pool für besonders riskante Zustellungen für ausgehende Nachrichten</span><span class="sxs-lookup"><span data-stu-id="bda5d-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="bda5d-p101">Wenn das E-Mail-System eines Kunden durch Schadsoftware oder einen böswilligen Spamangriff kompromittiert wurde und ausgehende Spamnachrichten durch den gehosteten Filterdienst sendet, kann dies dazu führen, dass die IP-Adressen der Office 365-Server im Rechenzentrum in Blockierungslisten von Drittanbietern aufgenommen werden. Zielserver, die nicht den gehosteten Filterdienst, aber diese Sperrlisten verwenden, lehnen alle E-Mails ab, die von einer der gehosteten IP-Filterungsadressen gesendet werden, die diesen Listen hinzugefügt wurden. Um dies zu verhindern, werden alle ausgehenden Nachrichten, die den Spamschwellenwert überschreiten, über einen Pool für besonders riskante Zustellungen übermittelt. Dieser sekundäre Pool für ausgehende E-Mails wird nur zum Senden von Nachrichten mit möglicherweise schlechter Qualität gesendet werden. Dies dient dazu, dass der Rest des Netzwerks vor dem Versenden von Nachrichten geschützt wird, die mit höherer Wahrscheinlichkeit dazu führen, dass die sendende IP-Adresse gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="bda5d-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="bda5d-p102">Indem ein dedizierter Pool für besonders riskante Zustellungen verwendet wird, wird dazu beigetragen, dass der normale Pool für ausgehende Nachrichten nur Nachrichten sendet, die bekanntermaßen von hoher Qualität sind. Mit diesem sekundären IP-Pool wird die Wahrscheinlichkeit verringert, dass der normale IP-Pool für ausgehende Nachrichten einer Sperrliste hinzugefügt wird. Es verbleibt das Risiko, dass der Pool für besonders riskante Zustellungen in eine Sperrliste aufgenommen wird. Dies ist so beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="bda5d-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="bda5d-113">Nachrichten, bei denen die sendende Domäne nicht über einen Adresseintrag (A-Datensatz) verfügt, der die IP-Adresse der Domäne enthält, und nicht über einen MX-Eintrag, mit dem E-Mails an die Server geleitet werden können, die die E-Mail für eine bestimmte Domäne im DNS erhalten sollen: Derartige Nachrichten werden stets durch den Pool für besonders riskante Zustellungen geleitet, unabhängig von ihrer Spameinschätzung.</span><span class="sxs-lookup"><span data-stu-id="bda5d-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="bda5d-114">Grundlegendes zu Nachrichten für die Benachrichtigung über den Übermittlungsstatus (Delivery Status Notification, DSN)</span><span class="sxs-lookup"><span data-stu-id="bda5d-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="bda5d-115">Der Pool für besonders riskante Zustellungen für ausgehende Nachrichten verwaltet die Zustellung aller Nachrichten mit "Unzustellbar" oder "Fehler".</span><span class="sxs-lookup"><span data-stu-id="bda5d-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="bda5d-116">Mögliche Ursachen für einen Anstieg der DSN-Meldungen sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="bda5d-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="bda5d-117">Eine Spoofingkampagne, die Auswirkungen auf einen Kunden des Diensts hat</span><span class="sxs-lookup"><span data-stu-id="bda5d-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="bda5d-118">Ein Verzeichnisdiebstahl-Angriff (Directory Harvest Attack)</span><span class="sxs-lookup"><span data-stu-id="bda5d-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="bda5d-119">Ein Spamangriff</span><span class="sxs-lookup"><span data-stu-id="bda5d-119">A spam attack</span></span>
    
- <span data-ttu-id="bda5d-120">Ein nicht autorisierter SMTP-Server</span><span class="sxs-lookup"><span data-stu-id="bda5d-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="bda5d-p103">Jedes dieser Probleme kann dazu führen, dass die Anzahl der DSN-Meldungen, die der Dienst verarbeitet, plötzlich ansteigt. Häufig werden diese DSN-Meldungen von anderen E-Mail-Servern und -Diensten als Spam klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="bda5d-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="bda5d-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bda5d-123">For more information</span></span>

[<span data-ttu-id="bda5d-124">Konfigurieren der Richtlinie für ausgehende Spamnachrichten</span><span class="sxs-lookup"><span data-stu-id="bda5d-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="bda5d-125">Häufig gestellte Fragen zum Anti-Spam-Schutz</span><span class="sxs-lookup"><span data-stu-id="bda5d-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

