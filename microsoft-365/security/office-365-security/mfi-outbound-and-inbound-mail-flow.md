---
title: Einblicke in den ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratoren können sich über den ausgehenden und eingehenden Nachrichtenfluss Insight im Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826893"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="51654-103">Einblicke in den ausgehenden und eingehenden Nachrichtenfluss im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="51654-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="51654-104">Der Einblicke für **ausgehende und eingehende e-Mails** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) im Security & Compliance Center kombiniert die Informationen aus dem [connectorbericht](view-mail-flow-reports.md#connector-report) und dem früheren TLS-Übersichts **Bericht** an einem zentralen Ort.</span><span class="sxs-lookup"><span data-stu-id="51654-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="51654-105">Das Widget zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an und von Ihrer Organisation zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51654-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="51654-106">Die Verbindungen, die mit anderen e-Mail-Diensten hergestellt werden, werden durch TLS verschlüsselt, wenn beide Seiten TLS anbieten.</span><span class="sxs-lookup"><span data-stu-id="51654-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="51654-107">Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses.</span><span class="sxs-lookup"><span data-stu-id="51654-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Fluss-Widget für ausgehende und eingehende Nachrichten im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="51654-109">Die Informationen im Widget beziehen sich auf Connectors und TLS-Nachrichtenschutz in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51654-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="51654-110">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="51654-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="51654-111">Konfigurieren des Nachrichtenflusses mit Connectors</span><span class="sxs-lookup"><span data-stu-id="51654-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="51654-112">Wie Exchange Online TLS zum Sichern von e-Mail-Verbindungen verwendet</span><span class="sxs-lookup"><span data-stu-id="51654-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="51654-113">Technische Referenzdetails zur Verschlüsselung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51654-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="51654-114">Nachricht ist bei der Übertragung geschützt (durch TLS)</span><span class="sxs-lookup"><span data-stu-id="51654-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="51654-115">Wenn Sie auf das Widget **Details anzeigen** klicken, zeigt das Flyout **Nachricht geschützt in Transit (über TLS)** den TLS-Schutz für Nachrichten an, die in Ihre Organisation eingehen und diese verlassen.</span><span class="sxs-lookup"><span data-stu-id="51654-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Nachrichten, die in der Übertragung geschützt sind (durch TLS), die angezeigt werden, nachdem Sie auf dem Widget für ausgehende und eingehende e-Mails auf Details anzeigen klicken.](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="51654-117">Derzeit ist TLS 1,2 die sicherste Version von TLS, die von Microsoft 365 angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="51654-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="51654-118">Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Überprüfungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="51654-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="51654-119">Sie haben wahrscheinlich keine direkte Beziehung zu den meisten Quell-und Ziel-e-Mail-Servern (Sie besitzen diese nicht und auch nicht Microsoft), sodass Sie nicht viele Optionen zum Verbessern der TLS-Verschlüsselung haben, die von diesen Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="51654-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="51654-120">Sie können jedoch [Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) verwenden, um den bestmöglichen TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren e-Mail-Servern und Microsoft 365 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="51654-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="51654-121">Der e-Mail-Fluss zwischen Microsoft 365 und ihren eigenen e-Mail-Servern oder Servern, die zu ihren Partnern gehören, ist häufig wichtiger und sensibler als reguläre Nachrichten, daher sollten Sie zusätzliche Sicherheit und Wachsamkeit für diese Nachrichten anwenden.</span><span class="sxs-lookup"><span data-stu-id="51654-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="51654-122">Sie können ein Upgrade oder eine Korrektur ihrer eigenen e-Mail-Server durchführen, um die verwendete TLS-Verschlüsselung zu verbessern oder Ihre Partner zu erreichen, um dasselbe zu tun.</span><span class="sxs-lookup"><span data-stu-id="51654-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="51654-123">Im **Bericht "Connector** " werden sowohl das Nachrichtenfluss Volumen als auch die TLS-Verschlüsselung für Nachrichten angezeigt, die Ihre Microsoft 365-Connectors verwenden.</span><span class="sxs-lookup"><span data-stu-id="51654-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="51654-124">Sie können auf den Link **connectorbericht** klicken, um zum [connectorbericht](view-mail-flow-reports.md#connector-report)zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="51654-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="51654-125">Die folgenden Einblicke stehen möglicherweise auf der Seite **connectorbericht** zur Verfügung, wenn die zugeordnete Bedingung erkannt wurde:</span><span class="sxs-lookup"><span data-stu-id="51654-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="51654-126">**Inbound-Partner-Konnektor, der signifikante TLS 1.0-Nachrichtenübermittlung sieht**</span><span class="sxs-lookup"><span data-stu-id="51654-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="51654-127">**Eingehender onpremises-Konnektor, der signifikante TLS 1.0-Nachrichtenübermittlung sieht**</span><span class="sxs-lookup"><span data-stu-id="51654-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="51654-128">Für TLS 1,0-Verbindungen müssen Sie Ihren e-Mail-Server oder den Server Ihres Partners wirklich aktualisieren oder reparieren lassen, um Probleme zu vermeiden, wenn die TLS 1,0-Unterstützung in Microsoft 365 schließlich veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="51654-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="51654-129">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="51654-129">See also</span></span>

<span data-ttu-id="51654-130">Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="51654-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
