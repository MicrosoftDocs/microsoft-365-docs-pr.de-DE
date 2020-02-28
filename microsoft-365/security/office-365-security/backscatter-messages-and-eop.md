---
title: Rückläufernachrichten und EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Backscatter-Nachrichten sind automatische Bounce-Nachrichten, die an gefälschte e-Mail-Adressen gesendet werden. Die Rückläufer-DNSBL identifiziert Server, die Rück Streu Nachrichten senden (die viele legitime e-Mail-Quellen enthalten können). Da es sich nicht um eine Spammer-Liste handelt, versuchen wir nicht, uns selbst aus dem BACKSCATTERER-DNSBL zu entfernen.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313810"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="9aa06-105">Rückläufernachrichten und EOP</span><span class="sxs-lookup"><span data-stu-id="9aa06-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="9aa06-106">Bei Rück *Läufer Nachrichten* handelt es sich um Unzustellbarkeitsberichte (auch als NDR oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="9aa06-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="9aa06-107">Spammer fälschen die von:-Adresse Ihrer Nachrichten, und Sie verwenden häufig reale e-Mail-Adressen, um Ihren Nachrichten Glaubwürdigkeit zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="9aa06-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="9aa06-108">Wenn also ein Spammer unweigerlich Nachrichten an nicht vorhandene Empfänger sendet (Spam ist eine Operation mit hohem Volumen), gibt der Ziel-e-Mail-Server wahrscheinlich die unzustellbare Nachricht in einem Unzustellbarkeitsbericht zurück, der an den gefälschten Absender in der from:-Adresse gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9aa06-108">So, when a spammer inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server will likely return the undeliverable message in an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="9aa06-109">Exchange Online Protection (EoP) unternimmt alle Anstrengungen, um Nachrichten aus fragwürdigen Quellen zu identifizieren und automatisch zu löschen, ohne einen Unzustellbarkeitsbericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9aa06-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="9aa06-110">Aber basierend auf der reinen Volumen-e-Mail, die den Dienst durchläuft, besteht immer die Möglichkeit, dass EoP unbeabsichtigt Rück Streu Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="9aa06-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="9aa06-111">BACKSCATTERER.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von e-Mail-Servern, die für das Senden von Backscatter-Nachrichten zuständig waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9aa06-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="9aa06-112">Wir versuchen jedoch nicht, uns aus der BACKSCATTERER.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.</span><span class="sxs-lookup"><span data-stu-id="9aa06-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="9aa06-113">Die Backscatter.org-Website<http://www.backscatterer.org/?target=usage>() empfiehlt die Verwendung Ihres Diensts zum Überprüfen eingehender e-Mails im abgesicherten Modus anstelle des ablehnen-Modus (große e-Mail-Dienste senden fast immer einige Backscatter-Nachrichten).</span><span class="sxs-lookup"><span data-stu-id="9aa06-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
