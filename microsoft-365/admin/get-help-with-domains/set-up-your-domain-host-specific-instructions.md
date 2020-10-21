---
title: Einrichten Ihrer Domäne (hostspezifische Anweisungen)
f1.keywords:
- NOCSH
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
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Hier erfahren Sie, wie Sie Ihre eigenen DNS-Einträge verwalten oder Ihre DNS-Einträge von Microsoft verwalten lassen.
ms.openlocfilehash: a22968fdfcdb6be8ecfdc9dde351de034edce4b2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645299"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="087cd-103">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="087cd-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="087cd-104">Um mit der Verwendung einer benutzerdefinierten Domäne (contoso.com) mit Microsoft 365 zu beginnen, müssen Sie Ihre Domäne überprüfen und die DNS-Einträge Ihrer Domäne konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="087cd-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="087cd-105">Sie können DNS-Einträge mithilfe der Verwaltungstools auf Ihrem Domänenhost hinzufügen und verwalten oder Microsoft die Kontrolle über Ihre Domäneneinträge erteilen, und wir werden Sie für Sie einrichten.</span><span class="sxs-lookup"><span data-stu-id="087cd-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="087cd-106">Wählen Sie Ihren Domänenhost unten aus, um die genauen Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="087cd-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="087cd-107">Wenn Sie nicht sicher sind, wer Ihr Host ist, finden Sie weitere Informationen unter [Suchen ihrer Domänen Registrierungs](find-your-domain-registrar.md)Stelle.</span><span class="sxs-lookup"><span data-stu-id="087cd-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="087cd-108">Lassen Sie Microsoft 365 Ihre DNS-Einträge verwalten</span><span class="sxs-lookup"><span data-stu-id="087cd-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="087cd-109">1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="087cd-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="087cd-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="087cd-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="087cd-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="087cd-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="087cd-112">Google-Domänen</span><span class="sxs-lookup"><span data-stu-id="087cd-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="087cd-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="087cd-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="087cd-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="087cd-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="087cd-115">NameCheap</span><span class="sxs-lookup"><span data-stu-id="087cd-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="087cd-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="087cd-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="087cd-117">Oder erfahren Sie, wie Sie Namen [Server ändern, um Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle einzurichten](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="087cd-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="087cd-118">Verwalten Ihrer eigenen DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="087cd-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="087cd-119">1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="087cd-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="087cd-120">Hover</span><span class="sxs-lookup"><span data-stu-id="087cd-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="087cd-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="087cd-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="087cd-122">Verwaltet von Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="087cd-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="087cd-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="087cd-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="087cd-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="087cd-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="087cd-125">Azure DNS-Zonen</span><span class="sxs-lookup"><span data-stu-id="087cd-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="087cd-126">name.com</span><span class="sxs-lookup"><span data-stu-id="087cd-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="087cd-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="087cd-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="087cd-128">NameCheap</span><span class="sxs-lookup"><span data-stu-id="087cd-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="087cd-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="087cd-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="087cd-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="087cd-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="087cd-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="087cd-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="087cd-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="087cd-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="087cd-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="087cd-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="087cd-134">Netzwerklösungen</span><span class="sxs-lookup"><span data-stu-id="087cd-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="087cd-135">DreamHost</span><span class="sxs-lookup"><span data-stu-id="087cd-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="087cd-136">OVH</span><span class="sxs-lookup"><span data-stu-id="087cd-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="087cd-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="087cd-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="087cd-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="087cd-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="087cd-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="087cd-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="087cd-140">Register365 für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="087cd-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="087cd-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="087cd-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="087cd-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="087cd-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="087cd-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="087cd-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="087cd-144"> Windows-basiertes DNS</span><span class="sxs-lookup"><span data-stu-id="087cd-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="087cd-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="087cd-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="087cd-146">WiX</span><span class="sxs-lookup"><span data-stu-id="087cd-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="087cd-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="087cd-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="087cd-148">Yahoo!   Kleine Unternehmen</span><span class="sxs-lookup"><span data-stu-id="087cd-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="087cd-149">Ich benötige allgemeine Anweisungen, da mein Domänenhost nicht in dieser Liste aufgeführt ist. </span><span class="sxs-lookup"><span data-stu-id="087cd-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
