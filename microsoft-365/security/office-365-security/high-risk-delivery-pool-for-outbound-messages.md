---
title: Pools für die Zustellung ausgehender Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die Übermittlungspools zum Schutz der Reputation von E-Mail-Servern in den Microsoft 365-Rechenzentren verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599911"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="09d20-103">Pools für die Zustellung ausgehender Nachrichten</span><span class="sxs-lookup"><span data-stu-id="09d20-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="09d20-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="09d20-104">**Applies to**</span></span>
- [<span data-ttu-id="09d20-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="09d20-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="09d20-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="09d20-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="09d20-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09d20-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="09d20-108">E-Mail-Server in den Microsoft 365-Rechenzentren können sich vorübergehend für das Senden von Spam entschuldigen.</span><span class="sxs-lookup"><span data-stu-id="09d20-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="09d20-109">Beispielsweise ein Schadsoftware- oder bösartiger Spamangriff in einer lokalen E-Mail-Organisation, die ausgehende E-Mails über Microsoft 365 sendet, oder gefährdete Microsoft 365-Konten.</span><span class="sxs-lookup"><span data-stu-id="09d20-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="09d20-110">Angreifer versuchen außerdem, die Erkennung zu vermeiden, indem Sie Nachrichten über die Microsoft 365-Weiterleitung weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="09d20-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="09d20-111">Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365-Rechenzentrumsserver auf Blocklisten von Drittanbietern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="09d20-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="09d20-112">Ziel-E-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen E-Mails aus diesen Nachrichtenquellen ab.</span><span class="sxs-lookup"><span data-stu-id="09d20-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="09d20-113">Pool mit hohem Risiko</span><span class="sxs-lookup"><span data-stu-id="09d20-113">High-risk delivery pool</span></span>
<span data-ttu-id="09d20-114">Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365-Rechenzentrumsservern, [](configure-the-outbound-spam-policy.md) die als Spam festgelegt sind oder die Sendegrenzwerte des Diensts oder ausgehender Spamrichtlinien überschreiten, über den Pool mit hohem Risiko gesendet. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="09d20-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="09d20-115">Der Pool mit hohem Risiko ist ein separater IP-Adresspool für ausgehende E-Mails, der nur zum Senden von Nachrichten niedriger Qualität (z. B. Spam und [Backscatter) verwendet wird.](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="09d20-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="09d20-116">Die Verwendung des Pools für die Zustellung mit hohem Risiko verhindert, dass der normale IP-Adresspool für ausgehende E-Mails Spam sendet.</span><span class="sxs-lookup"><span data-stu-id="09d20-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="09d20-117">Der normale IP-Adresspool für ausgehende E-Mails behält die Reputation bei, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit verringert wird, dass diese IP-Adresse auf IP-Sperrlisten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="09d20-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="09d20-118">Die sehr reale Möglichkeit, dass IP-Adressen im Pool mit hohem Risiko auf IP-Sperrlisten platziert werden, bleibt, aber dies ist entwurfsweise.</span><span class="sxs-lookup"><span data-stu-id="09d20-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="09d20-119">Die Zustellung an die vorgesehenen Empfänger ist nicht garantiert, da viele E-Mail-Organisationen keine Nachrichten aus dem Pool mit hohem Risiko annehmen.</span><span class="sxs-lookup"><span data-stu-id="09d20-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="09d20-120">Weitere Informationen finden Sie unter [Steuern von ausgehenden Spamnachrichten.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="09d20-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="09d20-121">Nachrichten, bei denen die Quell-E-Mail-Domäne keinen A-Eintrag und keinen im öffentlichen DNS definierten MX-Eintrag hat, werden immer über den Pool mit hohem Risiko geroutet, unabhängig von ihrer Spam- oder Sendelimitdisposition.</span><span class="sxs-lookup"><span data-stu-id="09d20-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="09d20-122">Unzustellbarkeitsnachrichten</span><span class="sxs-lookup"><span data-stu-id="09d20-122">Bounce messages</span></span>

<span data-ttu-id="09d20-123">Der Pool für ausgehende Zustellung mit hohem Risiko verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte, Unzustellbarkeitsnachrichten, Zustellungsstatusbenachrichtigungen oder DSNs bekannt).</span><span class="sxs-lookup"><span data-stu-id="09d20-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="09d20-124">Mögliche Ursachen für einen Anstieg von Unerschbungs- und</span><span class="sxs-lookup"><span data-stu-id="09d20-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="09d20-125">Eine Spoofingkampagne, die sich auf einen der Kunden auswirkt, die den Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="09d20-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="09d20-126">Ein Verzeichnisleseangriff.</span><span class="sxs-lookup"><span data-stu-id="09d20-126">A directory harvest attack.</span></span>
- <span data-ttu-id="09d20-127">Ein Spamangriff.</span><span class="sxs-lookup"><span data-stu-id="09d20-127">A spam attack.</span></span>
- <span data-ttu-id="09d20-128">Ein nicht autorisierter E-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="09d20-128">A rogue email server.</span></span>

<span data-ttu-id="09d20-129">All diese Probleme können zu einer plötzlichen Zunahme der Anzahl von Unntkräften führen, die vom Dienst verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="09d20-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="09d20-130">Viele Male scheinen diese Unntsprechenden Spam für andere E-Mail-Server und -Dienste (auch als _[Backscatter bekannt) zu sein.](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="09d20-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
