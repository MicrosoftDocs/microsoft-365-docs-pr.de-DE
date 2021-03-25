---
title: Einblicke in ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard
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
description: Administratoren können sich im Dashboard für den Nachrichtenfluss im Security & Compliance Center über den Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204137"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="826af-103">Einblicke in ausgehende und eingehende E-Mails im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="826af-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="826af-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="826af-104">**Applies to**</span></span>
- [<span data-ttu-id="826af-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="826af-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="826af-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="826af-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="826af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="826af-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="826af-108">Der **Einblick** in ausgehende und [](mail-flow-insights-v2.md) eingehende Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) kombiniert die Informationen aus dem [Connectorbericht](view-mail-flow-reports.md#connector-report) und dem früheren **TLS-Übersichtsbericht** an einem Ort.</span><span class="sxs-lookup"><span data-stu-id="826af-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="826af-109">Das Widget zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an Und von Ihrer Organisation zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="826af-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="826af-110">Die Verbindungen, die mit anderen E-Mail-Diensten hergestellt werden, werden von TLS verschlüsselt, wenn TLS von beiden Seiten angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="826af-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="826af-111">Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses.</span><span class="sxs-lookup"><span data-stu-id="826af-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget für ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="826af-113">Die Informationen im Widget stehen im Zusammenhang mit Connectors und dem TLS-Nachrichtenschutz in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="826af-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="826af-114">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="826af-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="826af-115">Konfigurieren des Nachrichtenflusses mit Connectors</span><span class="sxs-lookup"><span data-stu-id="826af-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="826af-116">Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt</span><span class="sxs-lookup"><span data-stu-id="826af-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="826af-117">Technische Referenzdetails zur Verschlüsselung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="826af-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="826af-118">Nachricht, die bei der Übertragung geschützt ist (durch TLS)</span><span class="sxs-lookup"><span data-stu-id="826af-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="826af-119">Wenn Sie **im** Widget auf Details anzeigen klicken, zeigt ihnen das Flyout Message **protected in transit (by TLS)** den TLS-Schutz für Nachrichten, die Ihre Organisation betreten und verlassen.</span><span class="sxs-lookup"><span data-stu-id="826af-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Nachrichten, die bei der Übertragung (durch TLS) geschützt sind und angezeigt werden, nachdem Sie im Widget Ausgehende und eingehende E-Mails auf Details anzeigen geklickt haben](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="826af-121">Derzeit ist TLS 1.2 die sicherste Version von TLS, die von Microsoft 365 angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="826af-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="826af-122">Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Audits verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="826af-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="826af-123">Wahrscheinlich haben Sie keine direkte Beziehung zu den meisten Quell- und Ziel-E-Mail-Servern (Sie besitzen sie nicht, und Microsoft auch nicht), daher haben Sie nicht viele Optionen, um die von diesen Servern verwendete TLS-Verschlüsselung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="826af-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="826af-124">Sie können jedoch Connectors [verwenden,](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) um den besten verfügbaren TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren E-Mail-Servern und Microsoft 365 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="826af-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="826af-125">Der E-Mail-Fluss zwischen Microsoft 365 und Ihren eigenen E-Mail-Servern oder Servern, die Zu Ihren Partnern gehören, ist häufig wichtiger und vertraulicher als normale Nachrichten, daher sollten Sie zusätzliche Sicherheit und Aufmerksamkeit auf diese Nachrichten anwenden.</span><span class="sxs-lookup"><span data-stu-id="826af-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="826af-126">Sie können Ihre eigenen E-Mail-Server aktualisieren oder beheben, um die verwendete TLS-Verschlüsselung zu verbessern, oder Ihre Partner kontaktieren, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="826af-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="826af-127">Der **Connectorbericht zeigt** sowohl das Volumen des Nachrichtenflusses als auch die TLS-Verschlüsselung für Nachrichten an, die Ihre Microsoft 365-Connectors verwenden.</span><span class="sxs-lookup"><span data-stu-id="826af-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="826af-128">Sie können auf den **Link Connectorbericht klicken,** um zum [Connectorbericht zu wechseln.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="826af-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="826af-129">Die folgenden Einblicke stehen möglicherweise auf der Seite **Connectorbericht** zur Verfügung, wenn die zugeordnete Bedingung erkannt wurde:</span><span class="sxs-lookup"><span data-stu-id="826af-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="826af-130">**Eingehender Partnerconnector mit erheblichem TLS1.0-E-Mail-Fluss**</span><span class="sxs-lookup"><span data-stu-id="826af-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="826af-131">**Eingehender OnPremises-Connector mit erheblichem TLS1.0-E-Mail-Fluss**</span><span class="sxs-lookup"><span data-stu-id="826af-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="826af-132">Für TLS 1.0-Verbindungen müssen Sie ihren E-Mail-Server oder den Server Ihres Partners wirklich aktualisiert oder behoben haben, um Probleme zu vermeiden, wenn die TLS 1.0-Unterstützung in Microsoft 365 nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="826af-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="826af-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="826af-133">See also</span></span>

<span data-ttu-id="826af-134">Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="826af-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>