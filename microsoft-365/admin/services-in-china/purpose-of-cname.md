---
title: Was ist der Zweck des CNAME-Eintrags für MSOID in Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 'Erfahren Sie mehr über den #A0 "MSOID" in Office 365, der Sie zum besten Server für Authentifizierungsprozesse leitet, damit Sie schneller reagieren können.'
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914306"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="7766d-103">Was ist der Zweck des CNAME-Eintrags für MSOID in Office 365?</span><span class="sxs-lookup"><span data-stu-id="7766d-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="7766d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="7766d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="7766d-105">Das Folgende gilt nur für \*\*Office 365 betrieben von 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="7766d-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="7766d-p101">[] Möglicherweise wundern Sie sich, warum Sie den CNAME-Eintrag "MSOID" in Office 365 hinzufügen müssen. Dieser Eintrag muss für alle benutzerdefinierten Domänen hinzugefügt werden, ganz gleich, welches Abonnement Sie verwenden. Warum benötigen Sie diesen Eintrag? Zur Beantwortung dieser Frage müssen wir ein wenig in die Technik einsteigen, aber es geht im Wesentlichen darum, bei bestimmten Authentifizierungsprozessen die Umleitung auf den besten Server zu erreichen, damit Sie schnellere Antworten erhalten.</span><span class="sxs-lookup"><span data-stu-id="7766d-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="7766d-p102">Zur Technik: Wenn Sie eine Clientanwendung ausführen, die mit Office 365 zusammenarbeitet, wie Skype for Business Online, Outlook, Windows PowerShell oder das Microsoft Azure Active Directory-Synchronisierungstool, müssen Ihre Anmeldeinformationen authentifiziert werden. Office 365 verwendet einen CNAME-Eintrag, um auf den korrekten Authentifizierungsendpunkt für Ihren Standort zu verweisen, wodurch bei der Authentifizierung eine schnelle Reaktionszeit sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7766d-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="7766d-p103">Wenn dieser CNAME-Eintrag für Ihre Domäne fehlt, verwenden die Anwendungen einen standardmäßigen Authentifizierungsendpunkt in den USA, was bedeutet, dass die Authentifizierung ggf. langsamer erfolgt. Wenn dieser CNAME-Eintrag nicht ordnungsgemäß konfiguriert ist, wenn es beispielsweise einen Tippfehler im Feld **Verweist auf die Adresse** gibt, sind diese Anwendungen nicht in der Lage, eine Authentifizierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="7766d-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="7766d-114">**Wenn Office 365 #A0** Ihrer Domäne verwaltet, Office 365 sie diesen #A1 für Sie einrichten.</span><span class="sxs-lookup"><span data-stu-id="7766d-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="7766d-115">**Wenn Sie DNS-Einträge** für Ihre Domäne auf Ihrem DNS-Host verwalten, erstellen Sie diesen Eintrag selbst, indem Sie die Anweisungen [für Ihren DNS-Host befolgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="7766d-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="7766d-116">Wenn Sie eine Office 365 planen und mehr über alle DNS-Einträge erfahren möchten, die Sie möglicherweise hinzufügen oder aktualisieren müssen, lesen Sie dazu in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="7766d-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
