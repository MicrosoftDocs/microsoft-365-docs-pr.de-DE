---
title: Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie Sie die Unterstützung für anonym eingehende E-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Protection konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290273"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="bf500-103">Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf500-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bf500-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="bf500-104">**Applies to**</span></span>
- [<span data-ttu-id="bf500-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bf500-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bf500-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="bf500-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bf500-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf500-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bf500-108">Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterstützen anonyme eingehende E-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="bf500-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="bf500-109">Der Quell-IPv6-E-Mail-Server muss die beiden folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="bf500-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="bf500-110">Die Quell-IPv6-Adresse muss über einen gültigen Reverse-DNS-Lookup (PTR)-Eintrag verfügen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse finden kann.</span><span class="sxs-lookup"><span data-stu-id="bf500-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="bf500-111">Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.</span><span class="sxs-lookup"><span data-stu-id="bf500-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="bf500-112">Bevor Ihre Organisation anonyme eingehende E-Mails über IPv6 empfangen kann, muss sich ein Administrator an den Support von Microsoft wenden und ihn bitten.</span><span class="sxs-lookup"><span data-stu-id="bf500-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="bf500-113">Anweisungen zum Öffnen einer Supportanfrage finden Sie unter Kontaktieren des Support [für Geschäftsprodukte - Administratorhilfe.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="bf500-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="bf500-114">Nachdem die Unterstützung für anonyme eingehende IPv6-Nachrichten in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung durch den Dienst gesendet.</span><span class="sxs-lookup"><span data-stu-id="bf500-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bf500-115">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="bf500-115">Troubleshooting</span></span>

- <span data-ttu-id="bf500-116">Wenn der Quell-E-Mail-Server keinen IPv6-Reverse-DNS-Lookup-Eintrag hat, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="bf500-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="bf500-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span><span class="sxs-lookup"><span data-stu-id="bf500-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="bf500-118">Wenn der Absender die SPF- oder DKIM-Überprüfung nicht besteht, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="bf500-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="bf500-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span><span class="sxs-lookup"><span data-stu-id="bf500-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="bf500-120">Wenn Sie versuchen, anonyme IPv6-Nachrichten zu empfangen, bevor Sie sich angemeldet haben, wird die Nachricht mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="bf500-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="bf500-121">550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine E-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="bf500-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf500-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bf500-122">Related topics</span></span>

[<span data-ttu-id="bf500-123">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="bf500-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
