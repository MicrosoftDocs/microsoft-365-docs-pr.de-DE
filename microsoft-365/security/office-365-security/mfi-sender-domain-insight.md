---
title: Korrigieren der Absenderdomänen Einblicke
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 'Administratoren können sich über das Fix Sender Domain Insight im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center informieren.'
ms.openlocfilehash: 42a673c5e6b04109656ef35bb5a80504ed1f42a9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082458"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="49eb1-103">Korrigieren der Absenderdomänen Einblicke</span><span class="sxs-lookup"><span data-stu-id="49eb1-103">Fix sender domain insight</span></span>

<span data-ttu-id="49eb1-104">Office 365 erfordert, dass Nachrichten, die von internen lokalen e-Mail-Umgebungen gesendet werden, Office 365 werden, um bestimmte Sicherheitskriterien zu erfüllen:</span><span class="sxs-lookup"><span data-stu-id="49eb1-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="49eb1-105">Sie haben in Office 365 einen eingehenden Connector erstellt, um SMTP-Verbindungen von Ihrem lokalen e-Mail-Server mithilfe der Quell-IP-Adresse oder eines Zertifikats zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="49eb1-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="49eb1-106">Sie haben ihren lokalen e-Mail-Server so konfiguriert, dass e-Mails über Office 365 an die externe weltweiter geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="49eb1-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="49eb1-107">In Ihrer Konfiguration ist eine der folgenden Aussagen zutreffend:</span><span class="sxs-lookup"><span data-stu-id="49eb1-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="49eb1-108">Die e-Mail-Domäne des Absenders wird in Ihrer Office 365 Organisation registriert.</span><span class="sxs-lookup"><span data-stu-id="49eb1-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="49eb1-109">Weitere Informationen finden Sie unter Hinzufügen von Domänen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="49eb1-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="49eb1-110">Der lokale e-Mail-Server ist für die Verwendung eines Zertifikats zum Senden von e-Mails an Office 365 konfiguriert, das Zertifikat enthält einen Domänennamen, den Sie in Office 365 registriert haben, oder stimmt genau überein und Sie haben einen zertifikatbasierten Connector in Office 365 mit diesem erstellt. Domäne.</span><span class="sxs-lookup"><span data-stu-id="49eb1-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="49eb1-111">Nachrichten, die die Kriterien nicht erfüllen, werden nicht der Organisation zugeordnet und können zurückgewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="49eb1-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="49eb1-112">Das **Fix Sender Domain** Insight zeigt Ihnen e-Mails von Ihrer lokalen Umgebung, die die Kriterien nicht erfüllen, unterstützt Sie bei der Ermittlung potenziell gefährdeter Computer und Benutzerkonten in Ihrer lokalen e-Mail-Umgebung und unterstützt Sie bei der Durchführung Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="49eb1-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![Der Fix Sender Domain Insight im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center](../media/sender-domain-insight-selected.png)

<span data-ttu-id="49eb1-114">Wenn Sie auf **Details anzeigen**klicken, werden Sie zu einem anderen Widget mit weiteren Details weitergeleitet, wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="49eb1-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Das Detail-Widget im Fix Sender Domain Insight](../media/sender-domain-view-details.png)

<span data-ttu-id="49eb1-116">Sie sehen den eingehenden Connector, der für die Zustellung der Nachrichten an Office 365 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="49eb1-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="49eb1-117">Sie können auch auf **Beispiel Meldungs-IDs anzeigen** klicken, um Details zu den Nachrichten anzuzeigen, die von Ihrer lokalen e-Mail-Umgebung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="49eb1-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="49eb1-118">Da diese Nachrichten von Office 365 abgelehnt wurden, können Sie die Nachrichtenablaufverfolgung nicht verwenden, aber Sie können die Beispiel Nachrichten-IDs verwenden, um die Nachrichten in Ihrer lokalen e-Mail-Umgebung nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="49eb1-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Anzeigen von Beispiel Meldungs-IDs im Fix Sender Domain Insight](../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="49eb1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49eb1-120">See also</span></span>

<span data-ttu-id="49eb1-121">Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security #a0 Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="49eb1-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
