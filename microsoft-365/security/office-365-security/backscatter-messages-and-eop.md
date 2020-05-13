---
title: Backscatter in EoP
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
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über Backscatter und Microsoft Exchange Online Schutz (EoP).
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209631"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="ea90d-103">Backscatter in EoP</span><span class="sxs-lookup"><span data-stu-id="ea90d-103">Backscatter in EOP</span></span>

<span data-ttu-id="ea90d-104">Bei *Backscatter* handelt es sich um Unzustellbarkeitsberichte (auch als NDR-oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="ea90d-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="ea90d-105">Spammer fälschen die von:-Adresse Ihrer Nachrichten, und Sie verwenden häufig reale e-Mail-Adressen, um Ihren Nachrichten Glaubwürdigkeit zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="ea90d-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="ea90d-106">Wenn Spammer unweigerlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-e-Mail-Server im Wesentlichen dazu verleitet, die unzustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der from:-Adresse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea90d-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="ea90d-107">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer ist EoP bemüht, Nachrichten aus fragwürdigen Quellen zu identifizieren und automatisch zu löschen, ohne einen Unzustellbarkeitsbericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ea90d-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="ea90d-108">Aber basierend auf den lauter Volumen-e-Mails, die durch den Dienst fließen, besteht immer die Möglichkeit, dass EoP unbeabsichtigt Backscatter sendet.</span><span class="sxs-lookup"><span data-stu-id="ea90d-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="ea90d-109">BACKSCATTERER.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von e-Mail-Servern, die für das Senden von Backscatter zuständig waren, und EOP-Server werden möglicherweise in dieser Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea90d-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="ea90d-110">Wir versuchen jedoch nicht, uns aus der BACKSCATTERER.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern (nach eigenem Eingeständnis) handelt.</span><span class="sxs-lookup"><span data-stu-id="ea90d-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="ea90d-111">Die Backscatter.org-Website ( <http://www.backscatterer.org/?target=usage> ) empfiehlt die Verwendung Ihres Diensts zum Überprüfen eingehender e-Mails im abgesicherten Modus anstelle des ablehnen-Modus (große e-Mail-Dienste senden fast immer einige Backscatter).</span><span class="sxs-lookup"><span data-stu-id="ea90d-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
