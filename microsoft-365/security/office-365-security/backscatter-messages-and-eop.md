---
title: Rückläufer in EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Backscatter und Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204024"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="c77c2-103">Rückläufer in EOP</span><span class="sxs-lookup"><span data-stu-id="c77c2-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c77c2-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c77c2-104">**Applies to**</span></span>
- [<span data-ttu-id="c77c2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c77c2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c77c2-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="c77c2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c77c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c77c2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c77c2-108">*Backscatter* sind Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="c77c2-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="c77c2-109">Spammer fälschen (spoofen) die Absender-Adresse ihrer Nachrichten und verwenden häufig echte E-Mail-Adressen, um ihren Nachrichten Glaubwürdigkeit zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="c77c2-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="c77c2-110">Wenn Spammer also unausweichlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-E-Mail-Server im Wesentlichen dazu verheddert, die nicht zustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der Absenderadresse zurückzusendet.</span><span class="sxs-lookup"><span data-stu-id="c77c2-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="c77c2-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterniert EOP alle Anstrengungen, Nachrichten aus zweifelhaften Quellen zu identifizieren und im Hintergrund zu löschen, ohne einen Unndr zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c77c2-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="c77c2-112">Basierend auf dem volumenbasierten E-Mail-Fluss über den Dienst besteht jedoch immer die Möglichkeit, dass EOP versehentlich zurückscatter sendet.</span><span class="sxs-lookup"><span data-stu-id="c77c2-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="c77c2-113">Backscatterer.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von E-Mail-Servern, die für das Senden von Rückscatter verantwortlich waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c77c2-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="c77c2-114">Wir versuchen jedoch nicht, uns selbst aus der Backscatterer.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.</span><span class="sxs-lookup"><span data-stu-id="c77c2-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="c77c2-115">Die Backscatter.org Website ( ) empfiehlt die Verwendung ihres Diensts, um eingehende E-Mails im abgesicherten Modus anstelle des Ablehnungsmodus zu überprüfen (große E-Mail-Dienste senden fast immer ein paar <http://www.backscatterer.org/?target=usage> Zurückscatter).</span><span class="sxs-lookup"><span data-stu-id="c77c2-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
