---
title: Erstellen von DNS-Einträgen für Office 365 beim Verwalten Ihrer DNS-Einträge
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Erfahren Sie, wie Sie DNS-Einträge für Office 365, betrieben von 21Vianet, erstellen, wenn Sie Ihre DNS-Einträge verwalten. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914354"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="45281-103">Erstellen von DNS-Einträgen für Office 365 beim Verwalten Ihrer DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="45281-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="45281-104">Ausführliche Anweisungen zum Erstellen von DNS-Einträgen für Office 365, betrieben von 21Vianet, einschließlich des für das E-Mail-Routing erforderlichen MX-Eintrags, finden Sie unter [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="45281-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="45281-105">Weitere Optionen und einige Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="45281-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="45281-106">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="45281-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="45281-107">Beschreibungen der Funktionen der DNS-Einträge finden Sie unter [DNS-Grundlagen](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="45281-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="45281-108">Bei einigen #A0 können Sie nicht alle erforderlichen Datensatztypen erstellen, was zu Diensteinschränkungen führt, wenn Ihr Hostinganbieter [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)oder Umleitung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45281-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="45281-109">Wenn Ihr Anbieter keine SRV-, TXT- oder #A0 [](../get-help-with-domains/buy-a-domain-name.md) unterstützt, wird empfohlen, ihre Domäne an einen Anbieter zu übertragen, der alle erforderlichen [Datensatztypen unterstützt.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="45281-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="45281-110">Informationen dazu, welche DNS-Einträge erforderlich sind und welche Werte für jeden Eintrag verwendet werden sollen, einschließlich des MX-Eintrags für E-Mails, finden Sie unter [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="45281-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="45281-111">Beschreibungen der Funktionen der DNS-Einträge finden Sie unter [DNS-Grundlagen](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="45281-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
