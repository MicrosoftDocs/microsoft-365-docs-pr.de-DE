---
title: Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie die Unterstützung für anonyme eingehende e-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Schutz konfiguriert wird.
ms.openlocfilehash: be226bf9814b0fcfadaaeb5b4bdda0ff133dd0c8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202149"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="e5785-103">Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5785-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e5785-104">Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer unterstützen anonyme eingehende e-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="e5785-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="e5785-105">Der Quell-IPv6-e-Mail-Server muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="e5785-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="e5785-106">Die IPv6-Quelladresse muss einen gültigen PTR-Eintrag (Reverse DNS Lookup) besitzen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="e5785-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="e5785-107">Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.</span><span class="sxs-lookup"><span data-stu-id="e5785-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="e5785-108">Bevor Ihre Organisation anonyme eingehende e-Mails über IPv6 erhalten kann, muss sich ein Administrator an den Microsoft-Support wenden und ihn Fragen.</span><span class="sxs-lookup"><span data-stu-id="e5785-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="e5785-109">Anweisungen zum Öffnen einer Supportanforderung finden Sie unter [kontaktieren des Supports für Business-Produkte – Administratorhilfe](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="e5785-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="e5785-110">Nachdem die anonyme eingehende IPv6-Nachrichten Unterstützung in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung geleitet, die vom Dienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e5785-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e5785-111">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e5785-111">Troubleshooting</span></span>

- <span data-ttu-id="e5785-112">Wenn der Quell-e-Mail-Server keinen IPv6-Reverse-DNS-Nachschlage Eintrag aufweist, werden die Nachrichten mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="e5785-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="e5785-113">450 4.7.25-Dienst nicht verfügbar ist, muss das Senden einer IPv6-Adresse [2a01:111: F200:2004:: 240] einen Reverse-DNS-Eintrag aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e5785-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="e5785-114">Wenn der Absender die SPF-oder DKIM-Validierung nicht übergibt, werden die Nachrichten mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="e5785-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="e5785-115">450 4.7.26-Dienst nicht verfügbar, Nachrichten, die über IPv6 gesendet werden [2a01:111: F200:2004:: 240] müssen die SPF-oder DKIM-Validierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="e5785-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="e5785-116">Wenn Sie versuchen, anonyme IPv6-Nachrichten zu erhalten, bevor Sie sich entschieden haben, wird die Nachricht mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="e5785-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="e5785-117">550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine e-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="e5785-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5785-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e5785-118">Related topics</span></span>

[<span data-ttu-id="e5785-119">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="e5785-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
