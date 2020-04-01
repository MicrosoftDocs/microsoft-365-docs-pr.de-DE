---
title: Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Der Administrator kann erfahren, wie die Unterstützung für anonyme eingehende e-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Schutz konfiguriert wird.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083641"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="0bf81-103">Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6 in Office 365</span><span class="sxs-lookup"><span data-stu-id="0bf81-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="0bf81-104">Office 365 Organisationen mit Exchange Online Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer unterstützen anonyme eingehende e-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="0bf81-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="0bf81-105">Der Quell-IPv6-e-Mail-Server muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="0bf81-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="0bf81-106">Die IPv6-Quelladresse muss einen gültigen PTR-Eintrag (Reverse DNS Lookup) besitzen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="0bf81-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="0bf81-107">Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](https://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.</span><span class="sxs-lookup"><span data-stu-id="0bf81-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="0bf81-108">Bevor Ihre Organisation anonyme eingehende e-Mails über IPv6 erhalten kann, muss sich ein Administrator an den Microsoft-Support wenden und ihn Fragen:</span><span class="sxs-lookup"><span data-stu-id="0bf81-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="0bf81-109">Öffnen Sie das Microsoft 365 Admin Center <https://admin.microsoft.com/adminportal/home> unter, und klicken Sie auf **Hilfe** (?).</span><span class="sxs-lookup"><span data-stu-id="0bf81-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="0bf81-110">Geben Sie im Dialogfeld **Hilfe benötigen?** ein, das angezeigt wird, in das Suchfeld ein (beispielsweise "Anonym eingehende IPv6-e-Mail anfordern"), und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="0bf81-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="0bf81-111">Klicken Sie unten auf der Seite auf **Support kontaktieren**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="0bf81-112">Füllen Sie auf der angezeigten Seite **Kontakt Support** die Informationen aus, und überprüfen Sie diese (Scrollen Sie nach Bedarf), und klicken Sie dann auf **Kontakt mit mir**.</span><span class="sxs-lookup"><span data-stu-id="0bf81-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="0bf81-113">Nachdem die anonyme eingehende IPv6-Nachrichten Unterstützung in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung geleitet, die vom Dienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0bf81-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0bf81-114">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="0bf81-114">Troubleshooting</span></span>

- <span data-ttu-id="0bf81-115">Wenn der Quell-e-Mail-Server keinen IPv6-Reverse-DNS-Nachschlage Eintrag aufweist, werden die Nachrichten mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="0bf81-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="0bf81-116">450 4.7.25-Dienst nicht verfügbar ist, muss das Senden einer IPv6-Adresse [2a01:111: F200:2004:: 240] einen Reverse-DNS-Eintrag aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0bf81-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="0bf81-117">Wenn der Absender die SPF-oder DKIM-Validierung nicht übergibt, werden die Nachrichten mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="0bf81-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="0bf81-118">450 4.7.26-Dienst nicht verfügbar, Nachrichten, die über IPv6 gesendet werden [2a01:111: F200:2004:: 240] müssen die SPF-oder DKIM-Validierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="0bf81-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="0bf81-119">Wenn Sie versuchen, anonyme IPv6-Nachrichten zu erhalten, bevor Sie sich entschieden haben, wird die Nachricht mit folgendem Fehler zurückgewiesen:</span><span class="sxs-lookup"><span data-stu-id="0bf81-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="0bf81-120">550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine e-Mails über IPv6.</span><span class="sxs-lookup"><span data-stu-id="0bf81-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="0bf81-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bf81-121">For more information</span></span>

[<span data-ttu-id="0bf81-122">Unterstützung für die Validierung von mit DKIM signierten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="0bf81-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
