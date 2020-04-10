---
title: Erstellen von DNS-Einträgen für Office 365 beim Verwalten von DNS-Einträgen
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Informationen zum Erstellen von DNS-Einträgen für Office 365, die von 21Vianet ausgeführt werden, wenn Ihre DNS-Einträge verwaltet werden. '
monikerRange: o365-21vianet
ms.openlocfilehash: b81ab3442e7087c4b7ee9bb3b5e5c2160d724986
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211997"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="3bc49-103">Erstellen von DNS-Einträgen für Office 365 beim Verwalten von DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="3bc49-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="3bc49-104">Ausführliche Anweisungen zum Erstellen von DNS-Einträgen für Office 365, die von 21Vianet betrieben werden, einschließlich des MX-Eintrags für das e-Mail-Routing, finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3bc49-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="3bc49-105">Weitere Optionen und einige Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="3bc49-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="3bc49-106">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="3bc49-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="3bc49-107">Beschreibungen der DNS-Einträge finden Sie unter [DNS Basics](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="3bc49-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="3bc49-108">Einige DNS-Hostinganbieter können nicht alle erforderlichen Datensatztypen erstellen, wodurch Diensteinschränkungen verursacht werden, [Wenn Ihr Hostinganbieter keine Unterstützung für SRV, CNAME, txt oder Umleitung bietet](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="3bc49-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="3bc49-109">Wenn Ihr Anbieter keine SRV-, txt-oder CNAME-Einträge unterstützt, wird empfohlen, dass Sie Ihre Domäne an einen Anbieter [übertragen](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) [, der alle erforderlichen Datensatztypen unterstützt](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="3bc49-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="3bc49-110">Um zu sehen, welche DNS-Einträge erforderlich sind, und die für jeden Datensatz zu verwendenden Werte finden, einschließlich des MX-Eintrags für e-Mail, finden Sie unter [Sammeln der erforderlichen Informationen zum Erstellen Office 365 DNS-Einträge](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span><span class="sxs-lookup"><span data-stu-id="3bc49-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span></span> <span data-ttu-id="3bc49-111">Beschreibungen der DNS-Einträge finden Sie unter [DNS Basics](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="3bc49-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

