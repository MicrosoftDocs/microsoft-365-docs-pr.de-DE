---
title: Einrichten Ihrer Domäne (hostspezifische Anweisungen)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 1b82fd40556b1bf828f9f367aa1175f21723cc8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399884"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="f359a-103">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="f359a-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="f359a-104">Um eine benutzerdefinierte Domäne (contoso.com) mit Office 365 verwenden zu können, müssen Sie Ihre Domäne überprüfen und die DNS-Einträge Ihrer Domäne konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f359a-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="f359a-105">Sie können DNS-Einträge mithilfe der Verwaltungstools auf Ihrem Domänenhost hinzufügen und verwalten oder Microsoft die Kontrolle über Ihre Domäneneinträge erteilen, und wir werden Sie für Sie einrichten.</span><span class="sxs-lookup"><span data-stu-id="f359a-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="f359a-106">Wählen Sie Ihren Domänenhost unten aus, um die genauen Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f359a-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="f359a-107">Wenn Sie nicht sicher sind, wer Ihr Host ist, finden Sie weitere Informationen unter [Suchen ihrer Domänen Registrierungs](find-your-domain-registrar.md)Stelle.</span><span class="sxs-lookup"><span data-stu-id="f359a-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="f359a-108">Lassen Sie Office 365 Ihre DNS-Einträge verwalten.</span><span class="sxs-lookup"><span data-stu-id="f359a-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="f359a-109">1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="f359a-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="f359a-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="f359a-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="f359a-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="f359a-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="f359a-112">Google-Domänen</span><span class="sxs-lookup"><span data-stu-id="f359a-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="f359a-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="f359a-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="f359a-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="f359a-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="f359a-115">NameCheap</span><span class="sxs-lookup"><span data-stu-id="f359a-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="f359a-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="f359a-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="f359a-117">Oder erfahren Sie, wie Sie Namen [Server ändern, um Office 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="f359a-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="f359a-118">Verwalten Ihrer eigenen DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="f359a-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="f359a-119">1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="f359a-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="f359a-120">Hover</span><span class="sxs-lookup"><span data-stu-id="f359a-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="f359a-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="f359a-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="f359a-122">Verwaltet von Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="f359a-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="f359a-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="f359a-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="f359a-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="f359a-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="f359a-125">Azure DNS-Zonen</span><span class="sxs-lookup"><span data-stu-id="f359a-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="f359a-126">name.com</span><span class="sxs-lookup"><span data-stu-id="f359a-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="f359a-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="f359a-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="f359a-128">NameCheap</span><span class="sxs-lookup"><span data-stu-id="f359a-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="f359a-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="f359a-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="f359a-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="f359a-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="f359a-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="f359a-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="f359a-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="f359a-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="f359a-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="f359a-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="f359a-134">Netzwerklösungen</span><span class="sxs-lookup"><span data-stu-id="f359a-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="f359a-135">DreamHost</span><span class="sxs-lookup"><span data-stu-id="f359a-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="f359a-136">OVH</span><span class="sxs-lookup"><span data-stu-id="f359a-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="f359a-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="f359a-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="f359a-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="f359a-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="f359a-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="f359a-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="f359a-140">Register365 für Office 365</span><span class="sxs-lookup"><span data-stu-id="f359a-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="f359a-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="f359a-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="f359a-142">web.com</span><span class="sxs-lookup"><span data-stu-id="f359a-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="f359a-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="f359a-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="f359a-144">Windows-basiertes DNS</span><span class="sxs-lookup"><span data-stu-id="f359a-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="f359a-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="f359a-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="f359a-146">WiX</span><span class="sxs-lookup"><span data-stu-id="f359a-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="f359a-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="f359a-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="f359a-148">Yahoo!   Kleine Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f359a-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="f359a-149">Ich benötige allgemeine Anweisungen, da mein Domänenhost nicht in dieser Liste aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="f359a-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
