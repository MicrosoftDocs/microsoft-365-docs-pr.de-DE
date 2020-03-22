---
title: Pool für besonders riskante Zustellungen für ausgehende Nachrichten
f1.keywords:
- NOCSH
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie der Pool mit hoher Risikoverteilung verwendet wird, um die Reputation von e-Mail-Servern in den Office 365-Rechenzentren zu schützen.
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895359"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a><span data-ttu-id="d467a-103">Hochriskanter Zustellungs Pool für ausgehende Nachrichten in Office 365</span><span class="sxs-lookup"><span data-stu-id="d467a-103">High-risk delivery pool for outbound messages in Office 365</span></span>

<span data-ttu-id="d467a-104">E-Mail-Server in den Office 365-Rechenzentren sind möglicherweise vorübergehend für das Senden von Spam schuldig.</span><span class="sxs-lookup"><span data-stu-id="d467a-104">Email servers in the Office 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="d467a-105">Beispielsweise eine Schadsoftware oder ein böswilliger Spamangriff in einer lokalen e-Mail-Organisation, die ausgehende e-Mails über Office 365 oder kompromittierte Office 365 Konten sendet.</span><span class="sxs-lookup"><span data-stu-id="d467a-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Office 365, or compromised Office 365 accounts.</span></span> <span data-ttu-id="d467a-106">Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Office 365 Datacenter-Server in Blocklisten von Drittanbietern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d467a-106">These scenarios can result in the IP address of the affected Office 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="d467a-107">Ziel-e-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen e-Mails von diesen Nachrichtenquellen ab.</span><span class="sxs-lookup"><span data-stu-id="d467a-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="d467a-108">Um dies zu verhindern, werden alle ausgehenden Nachrichten von Office 365 Datacenter-Servern, die als Spam festgestellt werden oder die die Sende Grenzen des [Diensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder der [ausgehenden Spam-Richtlinien](configure-the-outbound-spam-policy.md) überschreiten, über den _hochriskanten Zustellungs Pool_gesendet.</span><span class="sxs-lookup"><span data-stu-id="d467a-108">To prevent this, all outbound messages from Office 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="d467a-109">Der Pool mit hoher Risikoverteilung ist ein sekundärer IP-Adresspool für ausgehende e-Mails, der nur zum Senden von Nachrichten mit niedriger Qualität verwendet wird (beispielsweise Spam und [Backscatter](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="d467a-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="d467a-110">Die Verwendung des Pools mit hoher Risikoverteilung verhindert, dass der normale IP-Adresspool für ausgehende e-Mails Spam sendet.</span><span class="sxs-lookup"><span data-stu-id="d467a-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="d467a-111">Der normale IP-Adresspool für ausgehende e-Mails behält die Reputation, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit verringert wird, dass diese IP-Adresse in IP-Sperrlisten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d467a-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="d467a-112">Die reale Möglichkeit, dass IP-Adressen im hochriskanten Zustellungs Pool in IP-Sperrlisten eingefügt werden, bleibt jedoch im Entwurf.</span><span class="sxs-lookup"><span data-stu-id="d467a-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="d467a-113">Die Zustellung an die vorgesehenen Empfänger ist nicht gewährleistet, da viele e-Mail-Organisationen keine Nachrichten aus dem Pool mit hoher Risikoverteilung annehmen.</span><span class="sxs-lookup"><span data-stu-id="d467a-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="d467a-114">Weitere Informationen finden Sie unter [Steuern von ausgehenden Spamnachrichten in Office 365](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d467a-114">For more information, see [Control outbound spam in Office 365](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d467a-115">Nachrichten, bei denen die Quell-e-Mail-Domäne keinen Datensatz und keinen im öffentlichen DNS definierten MX-Eintrag enthält, werden immer über den risikoreichen Zustellungs Pool weitergeleitet, unabhängig von ihrer Spam-oder sende Grenzwert-Disposition.</span><span class="sxs-lookup"><span data-stu-id="d467a-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="d467a-116">Bounce-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="d467a-116">Bounce messages</span></span>

<span data-ttu-id="d467a-117">Der ausgehende Pool mit hoher Risikoverteilung verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch bekannt als NDR, Unzustellbarkeitsnachrichten, Benachrichtigungen über Zustellungsstatus oder DSNs).</span><span class="sxs-lookup"><span data-stu-id="d467a-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="d467a-118">Zu den möglichen Ursachen für einen Anstieg bei Unzustellbarkeitsberichten gehören:</span><span class="sxs-lookup"><span data-stu-id="d467a-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="d467a-119">Eine Spoofing-Kampagne, die sich auf einen Kunden auswirkt, der den Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="d467a-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="d467a-120">Ein Verzeichnis Lese Angriff.</span><span class="sxs-lookup"><span data-stu-id="d467a-120">A directory harvest attack.</span></span>

- <span data-ttu-id="d467a-121">Ein Spamangriff.</span><span class="sxs-lookup"><span data-stu-id="d467a-121">A spam attack.</span></span>

- <span data-ttu-id="d467a-122">Ein Rogue-e-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="d467a-122">A rogue email server.</span></span>

<span data-ttu-id="d467a-123">Alle diese Probleme können zu einer plötzlichen Vergrößerung der Anzahl von Unzustellbarkeitsberichten führen, die vom Dienst verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d467a-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="d467a-124">Viele Male scheinen diese Unzustellbarkeitsberichte Spam auf andere e-Mail-Server und-Dienste zu sein (auch bekannt als _[Backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="d467a-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
