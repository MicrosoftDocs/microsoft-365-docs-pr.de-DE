---
title: Verwenden von Domäne Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: In diesem Artikel erfahren Sie, wie Sie mit Domänen verbindungsfähigen Registrierungsstellen arbeiten und Ihre Domäne zu Microsoft 365 hinzufügen.
ms.openlocfilehash: fb3f9315ed8ae056cadd2fd6a83f13f6713347f3
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079979"
---
# <a name="using-domain-connect"></a><span data-ttu-id="6acc4-103">Verwenden von Domäne Connect</span><span class="sxs-lookup"><span data-stu-id="6acc4-103">Using Domain Connect</span></span>

 <span data-ttu-id="6acc4-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="6acc4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="6acc4-105">Mit [Domänen Verbindungs](https://www.domainconnect.org/) fähigen Registrierungsstellen können Sie Ihre Domäne in einem dreistufigen Prozess, der Minuten dauert, zu Microsoft 365 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6acc4-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="6acc4-106">Im Assistenten bestätigen wir lediglich, dass Sie die Domäne besitzen und dann automatisch die Datensätze Ihrer Domäne einrichten, sodass e-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6acc4-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6acc4-107">Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="6acc4-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6acc4-108">Domänen Verbindungs Registrierungsstellen, die in Microsoft 365 integriert sind</span><span class="sxs-lookup"><span data-stu-id="6acc4-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6acc4-109">1 &amp; 1 Ionos</span><span class="sxs-lookup"><span data-stu-id="6acc4-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6acc4-110">123reg wußte</span><span class="sxs-lookup"><span data-stu-id="6acc4-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="6acc4-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6acc4-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6acc4-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="6acc4-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6acc4-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="6acc4-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6acc4-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6acc4-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6acc4-115">SecureServer oder WildWestDomains (GoDaddy Reseller mit SecureServer DNS-Hosting)</span><span class="sxs-lookup"><span data-stu-id="6acc4-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="6acc4-116">Maddog-Domänen</span><span class="sxs-lookup"><span data-stu-id="6acc4-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="6acc4-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="6acc4-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6acc4-118">Was geschieht mit meiner e-Mail und Website?</span><span class="sxs-lookup"><span data-stu-id="6acc4-118">What happens to my email and website?</span></span>

<span data-ttu-id="6acc4-119">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne so aktualisiert, dass er auf Microsoft 365 verweist, und alle e-Mails für Ihre Domäne beginnen mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6acc4-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6acc4-120">Stellen Sie sicher, dass Sie Benutzer hinzugefügt haben, und richten Sie in Microsoft 365 Postfächer für jeden ein, der e-Mails in Ihrer Domäne erhält!</span><span class="sxs-lookup"><span data-stu-id="6acc4-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="6acc4-121">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="6acc4-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6acc4-122">Die Schritte zum Einrichten von Domänen Verbindungen wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="6acc4-122">The Domain Connect setup steps don't affect your website.</span></span>
