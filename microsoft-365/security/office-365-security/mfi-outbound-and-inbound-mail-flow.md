---
title: Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratoren können sich über den Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten im Dashboard für den Nachrichtenfluss im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029822"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="14e66-103">Einblick in den Ausgehenden und eingehenden Nachrichtenfluss im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="14e66-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="14e66-104">Der **Einblick** in ausgehende und [](mail-flow-insights-v2.md) eingehende Nachrichten im Nachrichtenflussdashboard im Security [](view-mail-flow-reports.md#connector-report) [& Compliance Center](https://protection.office.com) kombiniert die Informationen aus dem Connectorbericht und dem früheren **TLS-Übersichtsbericht** an einem Ort.</span><span class="sxs-lookup"><span data-stu-id="14e66-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="14e66-105">Das Widget zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an Und von Ihrer Organisation zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="14e66-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="14e66-106">Die Verbindungen, die mit anderen E-Mail-Diensten hergestellt werden, werden von TLS verschlüsselt, wenn TLS von beiden Seiten angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="14e66-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="14e66-107">Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses.</span><span class="sxs-lookup"><span data-stu-id="14e66-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget für ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="14e66-109">Die Informationen im Widget stehen im Zusammenhang mit Connectors und dem Schutz von TLS-Nachrichten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14e66-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="14e66-110">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="14e66-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="14e66-111">Konfigurieren des Nachrichtenflusses mit Connectors</span><span class="sxs-lookup"><span data-stu-id="14e66-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="14e66-112">Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt</span><span class="sxs-lookup"><span data-stu-id="14e66-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="14e66-113">Technische Referenzdetails zur Verschlüsselung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14e66-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="14e66-114">Nachricht, die bei der Übertragung geschützt ist (durch TLS)</span><span class="sxs-lookup"><span data-stu-id="14e66-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="14e66-115">Wenn Sie **auf** "Details anzeigen" im Widget klicken, wird im Flyout "Nachricht, die während der Übertragung **(durch TLS)** geschützt ist" der TLS-Schutz für Nachrichten angezeigt, die in Ihre Organisation ein- und austritten.</span><span class="sxs-lookup"><span data-stu-id="14e66-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Nachrichten, die bei der Übertragung (durch TLS) geschützt sind und angezeigt werden, nachdem Sie im Widget für ausgehende und eingehende E-Mails auf Details anzeigen geklickt haben](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="14e66-117">Derzeit ist TLS 1.2 die sicherste Version von TLS, die von Microsoft 365 angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="14e66-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="14e66-118">Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Überwachungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14e66-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="14e66-119">Wahrscheinlich haben Sie keine direkte Beziehung mit den meisten Quell- und Ziel-E-Mail-Servern (Sie besitzen sie nicht, und microsoft auch nicht), sodass Sie nicht viele Optionen haben, um die von diesen Servern verwendete TLS-Verschlüsselung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="14e66-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="14e66-120">Sie können jedoch Connectors [verwenden,](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) um den besten verfügbaren TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren E-Mail-Servern und Microsoft 365 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="14e66-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="14e66-121">Der E-Mail-Fluss zwischen Microsoft 365 und Ihren eigenen E-Mail-Servern oder -Servern, die Zu Ihren Partnern gehören, ist häufig wichtiger und vertraulicher als normale Nachrichten, daher sollten Sie zusätzliche Sicherheit und Meldungen auf diese Nachrichten anwenden.</span><span class="sxs-lookup"><span data-stu-id="14e66-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="14e66-122">Sie können Ihre eigenen E-Mail-Server aktualisieren oder korrigieren, um die verwendete TLS-Verschlüsselung zu verbessern, oder sich an Ihre Partner zu halten, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="14e66-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="14e66-123">Im **Connectorbericht werden** sowohl das Nachrichtenflussvolumen als auch die TLS-Verschlüsselung für Nachrichten angezeigt, die Ihre Microsoft 365-Connectors verwenden.</span><span class="sxs-lookup"><span data-stu-id="14e66-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="14e66-124">Sie können auf den **Connectorberichtslink klicken,** um zum [Connectorbericht zu wechseln.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="14e66-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="14e66-125">Die folgenden Erkenntnisse sind möglicherweise auf der Seite **"Connectorbericht"** verfügbar, wenn die zugeordnete Bedingung erkannt wurde:</span><span class="sxs-lookup"><span data-stu-id="14e66-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="14e66-126">**Eingehender Partnerconnector mit erheblichem TLS1.0-Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="14e66-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="14e66-127">**Eingehender OnPremises-Connector mit erheblichem TLS1.0-Nachrichtenfluss**</span><span class="sxs-lookup"><span data-stu-id="14e66-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="14e66-128">Für TLS 1.0-Verbindungen müssen Sie ihren E-Mail-Server oder den Server Ihres Partners aktualisiert oder behoben haben, um Probleme zu vermeiden, wenn der TLS 1.0-Support in Microsoft 365 möglicherweise nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="14e66-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="14e66-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14e66-129">See also</span></span>

<span data-ttu-id="14e66-130">Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="14e66-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
