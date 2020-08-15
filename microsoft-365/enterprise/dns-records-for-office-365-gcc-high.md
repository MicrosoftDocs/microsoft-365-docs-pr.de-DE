---
title: DNS-Einträge für Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Zusammenfassung: DNS-Einträge für Office 365 gcc hoch'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690488"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="a989b-103">DNS-Einträge für Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="a989b-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="a989b-104">*Dieser Artikel bezieht sich auf Office 365 gcc High und Microsoft 365 gcc High*</span><span class="sxs-lookup"><span data-stu-id="a989b-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="a989b-105">Im Rahmen des onboardings für Office 365 gcc High müssen Sie Ihre SMTP-und SIP-Domänen Ihrem Online Dienste-Mandanten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a989b-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="a989b-106">Verwenden Sie dazu das Cmdlet New-MsolDomain in Azure AD PowerShell, oder verwenden Sie das [Azure Government-Portal](https://portal.azure.us) , um den Prozess des Hinzufügens der Domäne und des Besitzes zu unter Beweis zu starten.</span><span class="sxs-lookup"><span data-stu-id="a989b-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="a989b-107">Nachdem Sie Ihre Domänen Ihrem Mandanten hinzugefügt und überprüft haben, können Sie die entsprechenden DNS-Einträge für die unten aufgeführten Dienste mit dem folgenden Leitfaden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a989b-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="a989b-108">Möglicherweise müssen Sie die folgende Tabelle ändern, um die Anforderungen Ihrer Organisation in Bezug auf den eingehenden MX-Eintrag (n) und alle vorhandenen Exchange-Auto Ermittlungs Einträge anzupassen, die Sie in der richtigen Position haben.</span><span class="sxs-lookup"><span data-stu-id="a989b-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="a989b-109">Es wird dringend empfohlen, diese DNS-Einträge mit Ihrem Messaging-Team zu koordinieren, um Ausfälle oder falsche Zustellung von e-Mails zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a989b-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="a989b-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a989b-110">Exchange Online</span></span>

| <span data-ttu-id="a989b-111">Type</span><span class="sxs-lookup"><span data-stu-id="a989b-111">Type</span></span> | <span data-ttu-id="a989b-112">Priority</span><span class="sxs-lookup"><span data-stu-id="a989b-112">Priority</span></span> | <span data-ttu-id="a989b-113">Hostname</span><span class="sxs-lookup"><span data-stu-id="a989b-113">Host name</span></span> | <span data-ttu-id="a989b-114">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="a989b-114">Points to address or value</span></span> | <span data-ttu-id="a989b-115">TTL</span><span class="sxs-lookup"><span data-stu-id="a989b-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="a989b-116">MX</span><span class="sxs-lookup"><span data-stu-id="a989b-116">MX</span></span> | <span data-ttu-id="a989b-117">0</span><span class="sxs-lookup"><span data-stu-id="a989b-117">0</span></span> | @ | <span data-ttu-id="a989b-118">*Mandanten*. Mail.Protection.office365.US (Weitere Informationen finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="a989b-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="a989b-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-119">1 Hour</span></span> |
| <span data-ttu-id="a989b-120">TXT</span><span class="sxs-lookup"><span data-stu-id="a989b-120">TXT</span></span> | - | @ | <span data-ttu-id="a989b-121">v = spf1 include:SPF. Protection. office365. US-all</span><span class="sxs-lookup"><span data-stu-id="a989b-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="a989b-122">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-122">1 Hour</span></span> |
| <span data-ttu-id="a989b-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="a989b-123">CNAME</span></span> | - | <span data-ttu-id="a989b-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a989b-124">autodiscover</span></span> | <span data-ttu-id="a989b-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="a989b-125">autodiscover.office365.us</span></span> | <span data-ttu-id="a989b-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="a989b-127">Exchange-Auto Ermittlungs Eintrag</span><span class="sxs-lookup"><span data-stu-id="a989b-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="a989b-128">Wenn Sie Exchange Server lokal haben, sollten Sie den vorhandenen Datensatz bei der Migration zu Exchange Online beibehalten und diesen Eintrag aktualisieren, nachdem Sie die Migration abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a989b-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="a989b-129">Exchange Online MX-Eintrag</span><span class="sxs-lookup"><span data-stu-id="a989b-129">Exchange Online MX Record</span></span>

<span data-ttu-id="a989b-130">Der Wert des MX-Eintrags für Ihre akzeptierten Domänen folgt einem Standardformat, wie oben erwähnt: *Tenant*. Mail.Protection.office365.US, das den *Mandanten* durch den ersten Teil des Standardmandanten namens ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a989b-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="a989b-131">Wenn Ihr Mandantenname beispielsweise contoso.onmicrosoft.US lautet, verwenden Sie **contoso.Mail.Protection.office365.US** als Wert für den MX-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="a989b-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="a989b-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a989b-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="a989b-133">CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="a989b-133">CNAME records</span></span>

| <span data-ttu-id="a989b-134">Typ</span><span class="sxs-lookup"><span data-stu-id="a989b-134">Type</span></span> | <span data-ttu-id="a989b-135">Hostname</span><span class="sxs-lookup"><span data-stu-id="a989b-135">Host name</span></span> | <span data-ttu-id="a989b-136">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="a989b-136">Points to address or value</span></span> | <span data-ttu-id="a989b-137">TTL</span><span class="sxs-lookup"><span data-stu-id="a989b-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="a989b-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="a989b-138">CNAME</span></span> | <span data-ttu-id="a989b-139">sip</span><span class="sxs-lookup"><span data-stu-id="a989b-139">sip</span></span> | <span data-ttu-id="a989b-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="a989b-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="a989b-141">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-141">1 Hour</span></span> |
| <span data-ttu-id="a989b-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="a989b-142">CNAME</span></span> | <span data-ttu-id="a989b-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a989b-143">lyncdiscover</span></span> | <span data-ttu-id="a989b-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="a989b-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="a989b-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="a989b-146">SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="a989b-146">SRV records</span></span>

| <span data-ttu-id="a989b-147">Typ</span><span class="sxs-lookup"><span data-stu-id="a989b-147">Type</span></span> | <span data-ttu-id="a989b-148">Dienst</span><span class="sxs-lookup"><span data-stu-id="a989b-148">Service</span></span> | <span data-ttu-id="a989b-149">Protokoll</span><span class="sxs-lookup"><span data-stu-id="a989b-149">Protocol</span></span> | <span data-ttu-id="a989b-150">Port</span><span class="sxs-lookup"><span data-stu-id="a989b-150">Port</span></span> | <span data-ttu-id="a989b-151">Schriftbreite</span><span class="sxs-lookup"><span data-stu-id="a989b-151">Weight</span></span> | <span data-ttu-id="a989b-152">Priorität</span><span class="sxs-lookup"><span data-stu-id="a989b-152">Priority</span></span> | <span data-ttu-id="a989b-153">Name</span><span class="sxs-lookup"><span data-stu-id="a989b-153">Name</span></span> | <span data-ttu-id="a989b-154">Ziel</span><span class="sxs-lookup"><span data-stu-id="a989b-154">Target</span></span> | <span data-ttu-id="a989b-155">TTL</span><span class="sxs-lookup"><span data-stu-id="a989b-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="a989b-156">SRV</span><span class="sxs-lookup"><span data-stu-id="a989b-156">SRV</span></span> | <span data-ttu-id="a989b-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="a989b-157">\_sip</span></span> | <span data-ttu-id="a989b-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="a989b-158">\_tls</span></span> | <span data-ttu-id="a989b-159">443</span><span class="sxs-lookup"><span data-stu-id="a989b-159">443</span></span> | <span data-ttu-id="a989b-160">1</span><span class="sxs-lookup"><span data-stu-id="a989b-160">1</span></span> | <span data-ttu-id="a989b-161">100</span><span class="sxs-lookup"><span data-stu-id="a989b-161">100</span></span> | @ | <span data-ttu-id="a989b-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="a989b-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="a989b-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-163">1 Hour</span></span> |
| <span data-ttu-id="a989b-164">SRV</span><span class="sxs-lookup"><span data-stu-id="a989b-164">SRV</span></span> | <span data-ttu-id="a989b-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a989b-165">\_sipfederationtls</span></span> | <span data-ttu-id="a989b-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="a989b-166">\_tcp</span></span> | <span data-ttu-id="a989b-167">5061</span><span class="sxs-lookup"><span data-stu-id="a989b-167">5061</span></span> | <span data-ttu-id="a989b-168">1</span><span class="sxs-lookup"><span data-stu-id="a989b-168">1</span></span> | <span data-ttu-id="a989b-169">100</span><span class="sxs-lookup"><span data-stu-id="a989b-169">100</span></span> | @ | <span data-ttu-id="a989b-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="a989b-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="a989b-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="a989b-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="a989b-172">Zusätzliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="a989b-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a989b-173">Wenn Sie einen vorhandenen *msoID* -CNAME-Eintrag in Ihrer DNS-Zone haben, müssen Sie den Datensatz zu diesem Zeitpunkt aus DNS **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="a989b-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="a989b-174">Der msoID-Eintrag ist nicht mit Microsoft 365 Enterprise-apps *(ehemals Office 365 ProPlus)* kompatibel und verhindert, dass die Aktivierung erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a989b-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
