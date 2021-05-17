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
description: Administratoren erfahren, wie Sie die Unterstützung für anonyme eingehende E-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Protection konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300049"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="3c9e4-103">Hinzufügen von Unterstützung für anonyme eingehende E-Mails über IPv6 in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c9e4-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3c9e4-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="3c9e4-104">**Applies to**</span></span>
- [<span data-ttu-id="3c9e4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3c9e4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3c9e4-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="3c9e4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3c9e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c9e4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3c9e4-108">Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterstützen anonyme eingehende E-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="3c9e4-109">Der Quell-IPv6-E-Mail-Server muss die beiden folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="3c9e4-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="3c9e4-110">Die Quell-IPv6-Adresse muss über einen gültigen Reverse-DNS-Nachschlagedatensatz (Reverse DNS Lookup, PTR) verfügen, mit dem das Ziel den Domänennamen von der IPv6-Adresse finden kann.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="3c9e4-111">Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="3c9e4-112">Bevor Ihre Organisation anonyme eingehende E-Mails über IPv6 empfangen kann, muss sich ein Administrator an den Microsoft-Support wenden und diese fragen.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="3c9e4-113">Anweisungen zum Öffnen einer Supportanfrage finden Sie unter [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="3c9e4-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="3c9e4-114">Nachdem die Unterstützung für anonyme eingehende IPv6-Nachrichten in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung durchgehen, die vom Dienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3c9e4-115">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="3c9e4-115">Troubleshooting</span></span>

- <span data-ttu-id="3c9e4-116">Wenn der Quell-E-Mail-Server keinen IPv6-Reverse-DNS-Nachschlagedatensatz hat, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="3c9e4-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="3c9e4-117">450 4.7.25 Dienst nicht verfügbar, sendende IPv6-Adresse [2a01:111:f200:2004::240] muss über einen reversen DNS-Eintrag verfügen.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="3c9e4-118">Wenn der Absender die SPF- oder DKIM-Überprüfung nicht besteht, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="3c9e4-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="3c9e4-119">450 4.7.26 Dienst nicht verfügbar, über IPv6 gesendete Nachricht [2a01:111:f200:2004::240] muss entweder die SPF- oder die DKIM-Überprüfung bestehen.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="3c9e4-120">Wenn Sie versuchen, anonyme IPv6-Nachrichten zu empfangen, bevor Sie sich angemeldet haben, wird die Nachricht mit dem folgenden Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="3c9e4-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="3c9e4-121">550 5.2.1 Dienst nicht verfügbar, [contoso.com] akzeptiert keine E-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="3c9e4-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c9e4-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3c9e4-122">Related topics</span></span>

[<span data-ttu-id="3c9e4-123">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="3c9e4-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
