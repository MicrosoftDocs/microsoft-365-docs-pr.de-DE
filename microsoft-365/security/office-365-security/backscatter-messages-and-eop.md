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
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599732"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="e69fd-105">Rückläufernachrichten und EOP</span><span class="sxs-lookup"><span data-stu-id="e69fd-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="e69fd-106">Bei Rück *Läufer Nachrichten* handelt es sich um Unzustellbarkeitsberichte (auch als NDR oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="e69fd-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="e69fd-107">Spammer fälschen die von:-Adresse Ihrer Nachrichten, und Sie verwenden häufig reale e-Mail-Adressen, um Ihren Nachrichten Glaubwürdigkeit zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="e69fd-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="e69fd-108">Wenn Sie also unweigerlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), antwortet der Ziel-e-Mail-Server möglicherweise pflichtgemäß mit einem NDR, der an den gefälschten Absender in der von: address gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e69fd-108">So, when they inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server might dutifully respond with an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="e69fd-109">Exchange Online Protection (EoP) unternimmt alle Anstrengungen, um Nachrichten aus fragwürdigen Quellen zu identifizieren und automatisch zu löschen, ohne einen Unzustellbarkeitsbericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e69fd-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="e69fd-110">Aber basierend auf der reinen Volumen-e-Mail, die den Dienst durchläuft, besteht immer die Möglichkeit, dass EoP unbeabsichtigt Rück Streu Nachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="e69fd-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="e69fd-111">BACKSCATTERER.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von e-Mail-Servern, die für das Senden von Backscatter-Nachrichten zuständig waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e69fd-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="e69fd-112">Wir versuchen jedoch nicht, uns aus der BACKSCATTERER.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.</span><span class="sxs-lookup"><span data-stu-id="e69fd-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="e69fd-113">Entsprechend der Backscatter. or-Website (`http://www.backscatterer.org/?target=usage`) empfehlen Sie, ihren Dienst zu verwenden, um eingehende e-Mails im abgesicherten Modus anstelle des ablehnen-Modus zu überprüfen (große e-Mail-Dienste senden fast immer einige Backscatter-Nachrichten).</span><span class="sxs-lookup"><span data-stu-id="e69fd-113">According to the Backscatter.or website (`http://www.backscatterer.org/?target=usage`), they recommend using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
