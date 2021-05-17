---
title: Unterstützung für die Überprüfung von dkIM (Domain Keys Identified Mail) signierten Nachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Überprüfung von DKIM-signierten Nachrichten in Exchange Online Protection und Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206461"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="745a6-103">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="745a6-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="745a6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="745a6-104">**Applies to**</span></span>
- [<span data-ttu-id="745a6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="745a6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="745a6-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="745a6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="745a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="745a6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="745a6-108">Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Überprüfung von Domänenschlüsseln identifizierte E-Mails ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="745a6-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="745a6-109">DKIM überprüft, ob eine E-Mail-Nachricht nicht von einer anderen Person gefälscht wurde und von der Domäne gesendet wurde, von der sie sagt, *dass* sie stammt. </span><span class="sxs-lookup"><span data-stu-id="745a6-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="745a6-110">Es bindet eine E-Mail-Nachricht an die Organisation, die sie gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="745a6-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="745a6-111">Die DKIM-Überprüfung wird automatisch für alle Nachrichten verwendet, die mit IPv6 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="745a6-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="745a6-112">Microsoft 365 unterstützt auch DKIM, wenn E-Mails über IPv4 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="745a6-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="745a6-113">Weitere Informationen zur Unterstützung von IPv6 finden Sie unter [Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="745a6-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="745a6-114">DKIM überprüft eine digital signierte Nachricht, die im DKIM-Signature der Nachrichtenkopfzeilen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="745a6-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="745a6-115">Die Ergebnisse einer DKIM-Signature werden in der Kopfzeile Authentication-Results gestempelt.</span><span class="sxs-lookup"><span data-stu-id="745a6-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="745a6-116">Der Nachrichtenkopftext sieht in etwa folgendermaßen aus (wobei "contoso.com" der Sender ist):</span><span class="sxs-lookup"><span data-stu-id="745a6-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="745a6-117">Weitere Informationen zum Authentication-Results finden Sie unter RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="745a6-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="745a6-118">Die DKIM-Implementierung von Microsoft entspricht dieser RFC.</span><span class="sxs-lookup"><span data-stu-id="745a6-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="745a6-119">Administratoren können Exchange [E-Mail-Flussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) für die Ergebnisse der DKIM-Überprüfung erstellen.</span><span class="sxs-lookup"><span data-stu-id="745a6-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="745a6-120">Diese Nachrichtenflussregeln ermöglichen Administratoren das Filtern oder Routen von Nachrichten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="745a6-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>