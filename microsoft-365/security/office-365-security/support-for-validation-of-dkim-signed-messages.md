---
title: Unterstützung für die Überprüfung von DKIM (Domain Keys Identified Mail)-signierten Nachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Überprüfung von MIT DKIM signierten Nachrichten in Exchange Online Protection und Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845059"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="0cab8-103">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="0cab8-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0cab8-104">Exchange Online Protection (EOP) und Exchange Online unterstützen beide die eingehende Überprüfung von Domänenschlüsseln identifizierter E-Mail-Nachrichten[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="0cab8-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="0cab8-105">DKIM überprüft, ob eine E-Mail-Nachricht von einer anderen Person gefälscht wurde und dass sie von der Domäne gesendet wurde, von der sie sagt, dass *sie* stammt. </span><span class="sxs-lookup"><span data-stu-id="0cab8-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="0cab8-106">Es bindet eine E-Mail-Nachricht an die Organisation, die sie gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="0cab8-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="0cab8-107">Die DKIM-Überprüfung wird automatisch für alle Nachrichten verwendet, die mit IPv6 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cab8-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="0cab8-108">Microsoft 365 unterstützt dkIM auch, wenn E-Mails über IPv4 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cab8-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="0cab8-109">Weitere Informationen zur Unterstützung von IPv6 finden Sie unter [Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="0cab8-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="0cab8-110">DKIM überprüft eine digital signierte Nachricht, die in DKIM-Signature Kopfzeile der Nachrichtenkopfzeilen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0cab8-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="0cab8-111">Die Ergebnisse einer DKIM-Signature werden in der Kopfzeile Authentication-Results gestempelt.</span><span class="sxs-lookup"><span data-stu-id="0cab8-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="0cab8-112">Der Nachrichtenkopftext sieht in etwa folgendermaßen aus (wobei "contoso.com" der Sender ist):</span><span class="sxs-lookup"><span data-stu-id="0cab8-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="0cab8-113">Weitere Informationen zum Nachrichtenkopf Authentication-Results finden Sie unter RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="0cab8-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="0cab8-114">Die Microsoft -DKIM-Implementierung entspricht dieser RFC.</span><span class="sxs-lookup"><span data-stu-id="0cab8-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="0cab8-115">Administratoren können [Exchange-Nachrichtenflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) für die Ergebnisse der DKIM-Überprüfung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cab8-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="0cab8-116">Diese Nachrichtenflussregeln ermöglichen Administratoren das Filtern oder Routen von Nachrichten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="0cab8-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
