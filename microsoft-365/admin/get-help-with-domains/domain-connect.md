---
title: Verwenden von Domänen verbinden
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Erfahren Sie, wie Sie mit domain connect-aktivierten Registrierungsstellen arbeiten und Ihre Domäne zu Microsoft 365 hinzufügen.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860655"
---
# <a name="using-domain-connect"></a><span data-ttu-id="3292b-103">Verwenden von Domänen verbinden</span><span class="sxs-lookup"><span data-stu-id="3292b-103">Using Domain Connect</span></span>

 <span data-ttu-id="3292b-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="3292b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="3292b-105">[Domain ](https://www.domainconnect.org/) Connect-aktivierte Registrierungsstellen ermöglicht es Ihnen, Ihre Domäne in einem Drei-Schritt-Prozess, der Minuten dauert, zu Microsoft 365 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3292b-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="3292b-106">Im Assistenten bestätigen wir nur, dass Sie der Domänenname sind, und richten dann automatisch die Datensätze Ihrer Domäne ein, damit E-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3292b-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3292b-107">Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="3292b-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="3292b-108">Integration von Domänen-Connect-Registrierungsstellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3292b-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="3292b-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="3292b-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="3292b-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="3292b-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="3292b-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3292b-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="3292b-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="3292b-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="3292b-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="3292b-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="3292b-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="3292b-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="3292b-115">SecureServer oder WildWestDomains (GoDaddy-Vertriebspartner, die SecureServer-DNS-Hosting verwenden)</span><span class="sxs-lookup"><span data-stu-id="3292b-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="3292b-116">MadDog-Webhosting</span><span class="sxs-lookup"><span data-stu-id="3292b-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
    - [<span data-ttu-id="3292b-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="3292b-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="3292b-118">Was geschieht mit meiner E-Mail und Website?</span><span class="sxs-lookup"><span data-stu-id="3292b-118">What happens to my email and website?</span></span>

<span data-ttu-id="3292b-119">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne auf Microsoft 365 aktualisiert, und alle E-Mails für Ihre Domäne werden an Microsoft 365 gesendet.</span><span class="sxs-lookup"><span data-stu-id="3292b-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="3292b-120">Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer eingerichtet haben, die E-Mails in Ihrer Domäne erhalten!</span><span class="sxs-lookup"><span data-stu-id="3292b-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="3292b-121">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="3292b-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="3292b-122">Die Schritte zum Einrichten von Domänen verbinden wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="3292b-122">The Domain Connect setup steps don't affect your website.</span></span>
