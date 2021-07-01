---
title: Verwenden von Domänen-Verbinden
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
description: Erfahren Sie, wie Sie mit Domänen-Verbinden aktivierten Registrierungsstellen arbeiten und Ihre Domäne Microsoft 365 hinzufügen.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228013"
---
# <a name="using-domain-connect"></a><span data-ttu-id="e7bdc-103">Verwenden von Domänen-Verbinden</span><span class="sxs-lookup"><span data-stu-id="e7bdc-103">Using Domain Connect</span></span>

 <span data-ttu-id="e7bdc-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="e7bdc-105">Registrierungsstellen, die [Domain Connect](https://www.domainconnect.org/) unterstützen, ermöglichen es Ihnen, Ihre Domäne in einem dreistufigen Prozess zu Microsoft 365 hinzuzufügen, der nur wenige Minuten dauert.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="e7bdc-106">Im Assistenten werden wir nur überprüfen, ob Sie der Besitzer der Domäne sind. Anschließend werden die Einträge der Domäne automatisch eingerichtet, damit E-Mails bei Microsoft 365 eingehen und andere Microsoft 365-Dienste wie Microsoft Teams mit Ihrer Domäne verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="e7bdc-107">Stellen Sie sicher, dass alle Popupblocker in Ihrem Browser deaktiviert sind, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="e7bdc-108">Domain Connect-Registrierungsstellen, die eine Microsoft 365-Integration ermöglichen</span><span class="sxs-lookup"><span data-stu-id="e7bdc-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="e7bdc-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="e7bdc-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="e7bdc-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="e7bdc-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="e7bdc-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="e7bdc-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="e7bdc-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="e7bdc-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="e7bdc-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="e7bdc-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="e7bdc-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="e7bdc-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="e7bdc-115">SecureServer oder WildWestDomains (GoDaddy-Wiederverkäufer, die SecureServer DNS-Hosting verwenden)</span><span class="sxs-lookup"><span data-stu-id="e7bdc-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="e7bdc-116">Mad Dog Web Hosting</span><span class="sxs-lookup"><span data-stu-id="e7bdc-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="e7bdc-117">"Untername"</span><span class="sxs-lookup"><span data-stu-id="e7bdc-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="e7bdc-118">Was geschieht mit meinen E-Mails und meiner Website?</span><span class="sxs-lookup"><span data-stu-id="e7bdc-118">What happens to my email and website?</span></span>

<span data-ttu-id="e7bdc-119">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne aktualisiert, damit er auf Microsoft 365 verweist. Daraufhin gehen sämtliche E-Mails für Ihre Domäne bei Microsoft 365 ein.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="e7bdc-120">Stellen Sie sicher, dass Sie in Microsoft 365 Benutzer und Postfächer für alle Personen hinzugefügt und erstellt haben, die in Ihrer Domäne E-Mails erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="e7bdc-121">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert diese weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="e7bdc-122">Die Einrichtungsschritte für Domain Connect wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-122">The Domain Connect setup steps don't affect your website.</span></span>
