---
title: Unterstützung für die Validierung von mit DKIM signierten Nachrichten
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
description: Erfahren Sie mehr über die Validierung von DKIM-signierten Nachrichten in Exchange Online Schutz und Exchange Online
ms.openlocfilehash: 1dc160a4aa01a1a1e46a9b31bb09206d4b385d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598222"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="4069b-103">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4069b-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="4069b-104">Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Validierung von Domain Keys Identified Mail([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt))-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="4069b-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="4069b-105">DKIM ist eine Methode, anhand derer validiert wird, dass eine Nachricht von der angegebenen Domian stammt und nicht von jemand anderem gefälscht wurde.</span><span class="sxs-lookup"><span data-stu-id="4069b-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="4069b-106">Durch sie wird eine E-Mail mit der Organisation verbunden, die für deren Senden verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4069b-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="4069b-107">Die DKIM-Verifizierung steht automatisch für alle Nachrichten zur Verfügung, die über IPv6 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4069b-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="4069b-108">Office 365 unterstützt jetzt auch DKIM, wenn e-Mail-Nachrichten über IPv4 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4069b-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="4069b-109">Weitere Informationen zur Unterstützung von IPv6 finden Sie unter [Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="4069b-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="4069b-p102">DKIM validiert eine digital signierte Nachricht, die im DKIM-Signaturkopf in Nachrichtenkopfzeilen angezeigt wird. Die Ergebnisse einer DKIM-Signaturvalidierung werden in den Kopf mit Authentifizierungsergebnissen gestempelt, der RFC 7001 ([Nachrichtenkopfzeilenfeld für die Angabe des Authentifizierungsstatus der Nachricht](https://www.rfc-editor.org/rfc/rfc7001.txt)) entspricht. Der Nachrichtenkopftext sieht in etwa folgendermaßen aus (wobei "contoso.com" der Sender ist):</span><span class="sxs-lookup"><span data-stu-id="4069b-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="4069b-113">Administratoren können Exchange [-Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) für die Ergebnisse einer DKIM-Validierung erstellen, um Nachrichten bei Bedarf zu filtern oder weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="4069b-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
