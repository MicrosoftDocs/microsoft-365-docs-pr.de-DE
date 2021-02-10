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
description: In diesem Artikel erfahren Sie mehr über Backscatter and Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165955"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="69f9e-103">Rückläufer in EOP</span><span class="sxs-lookup"><span data-stu-id="69f9e-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="69f9e-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="69f9e-104">**Applies to**</span></span>
- [<span data-ttu-id="69f9e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="69f9e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="69f9e-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="69f9e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="69f9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69f9e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="69f9e-108">*Rückläufer sind* Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet), die Sie für Nachrichten erhalten, die Sie nicht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="69f9e-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="69f9e-109">Spammer forieren die "Von"-Adresse ihrer Nachrichten (spoofing) und verwenden häufig echte E-Mail-Adressen, um ihre Nachrichten zu täuschen.</span><span class="sxs-lookup"><span data-stu-id="69f9e-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="69f9e-110">Wenn Spammer also unausweichlich Nachrichten an nicht vorhandene Empfänger senden (Spam ist ein Vorgang mit hohem Volumen), wird der Ziel-E-Mail-Server im Wesentlichen dazu verfälscht, die nicht zustellbare Nachricht in einem Unzustellbarkeitsbericht an den gefälschten Absender in der "Von:"-Adresse zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="69f9e-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="69f9e-111">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterniert EOP alle Anstrengungen, Nachrichten aus ungernen Quellen zu identifizieren und im Hintergrund zu löschen, ohne einen NDR zu generieren.</span><span class="sxs-lookup"><span data-stu-id="69f9e-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="69f9e-112">Aber basierend auf dem schruppigen E-Mail-Fluss über den Dienst besteht immer die Möglichkeit, dass EOP versehentlich einen Rückscatter sendet.</span><span class="sxs-lookup"><span data-stu-id="69f9e-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="69f9e-113">Backscatterer.org verwaltet eine Sperrliste (auch als DNS-Sperrliste oder DNSBL bezeichnet) von E-Mail-Servern, die für das Senden von Rückscattern verantwortlich waren, und die EOP-Server werden möglicherweise in dieser Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69f9e-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="69f9e-114">Wir versuchen jedoch nicht, uns selbst aus der Backscatterer.org-Sperrliste zu entfernen, da es sich nicht um eine Liste von Spammern handelt (nach eigenem Eingeständnis).</span><span class="sxs-lookup"><span data-stu-id="69f9e-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="69f9e-115">Die Backscatter.org Website ( ) empfiehlt die Verwendung ihres Diensts, um eingehende E-Mails im abgesicherten Modus anstelle des Zurückweisens zu überprüfen (große E-Mail-Dienste senden fast immer einen <http://www.backscatterer.org/?target=usage> Rückscatter).</span><span class="sxs-lookup"><span data-stu-id="69f9e-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
