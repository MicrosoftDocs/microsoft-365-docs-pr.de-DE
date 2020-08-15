---
title: DNS-Einträge für Office 365 DoD
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
description: 'Zusammenfassung: DNS-Einträge für Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690499"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="95733-103">DNS-Einträge für Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="95733-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="95733-104">*Dieser Artikel bezieht sich auf Office 365 DoD und Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="95733-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="95733-105">Im Rahmen des onboardings für Office 365 DoD müssen Sie Ihre SMTP-und SIP-Domänen zu Ihrem Online Dienste-Mandanten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95733-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="95733-106">Verwenden Sie dazu das Cmdlet New-MsolDomain in Azure AD PowerShell, oder verwenden Sie das [Azure Government-Portal](https://portal.azure.us) , um den Prozess des Hinzufügens der Domäne und des Besitzes zu unter Beweis zu starten.</span><span class="sxs-lookup"><span data-stu-id="95733-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="95733-107">Nachdem Sie Ihre Domänen Ihrem Mandanten hinzugefügt und überprüft haben, können Sie die entsprechenden DNS-Einträge für die unten aufgeführten Dienste mit dem folgenden Leitfaden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95733-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="95733-108">Möglicherweise müssen Sie die folgende Tabelle ändern, um die Anforderungen Ihrer Organisation in Bezug auf den eingehenden MX-Eintrag (n) und alle vorhandenen Exchange-Auto Ermittlungs Einträge anzupassen, die Sie in der richtigen Position haben.</span><span class="sxs-lookup"><span data-stu-id="95733-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="95733-109">Es wird dringend empfohlen, diese DNS-Einträge mit Ihrem Messaging-Team zu koordinieren, um Ausfälle oder falsche Zustellung von e-Mails zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="95733-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="95733-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95733-110">Exchange Online</span></span>

| <span data-ttu-id="95733-111">Type</span><span class="sxs-lookup"><span data-stu-id="95733-111">Type</span></span> | <span data-ttu-id="95733-112">Priority</span><span class="sxs-lookup"><span data-stu-id="95733-112">Priority</span></span> | <span data-ttu-id="95733-113">Hostname</span><span class="sxs-lookup"><span data-stu-id="95733-113">Host name</span></span> | <span data-ttu-id="95733-114">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="95733-114">Points to address or value</span></span> | <span data-ttu-id="95733-115">TTL</span><span class="sxs-lookup"><span data-stu-id="95733-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="95733-116">MX</span><span class="sxs-lookup"><span data-stu-id="95733-116">MX</span></span> | <span data-ttu-id="95733-117">0</span><span class="sxs-lookup"><span data-stu-id="95733-117">0</span></span> | @ | <span data-ttu-id="95733-118">*Mandanten*. Mail.Protection.office365.US (Weitere Informationen finden Sie weiter unten)</span><span class="sxs-lookup"><span data-stu-id="95733-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="95733-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-119">1 Hour</span></span> |
| <span data-ttu-id="95733-120">TXT</span><span class="sxs-lookup"><span data-stu-id="95733-120">TXT</span></span> | - | @ | <span data-ttu-id="95733-121">v = spf1 include:SPF. Protection. office365. US-all</span><span class="sxs-lookup"><span data-stu-id="95733-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="95733-122">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-122">1 Hour</span></span> |
| <span data-ttu-id="95733-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="95733-123">CNAME</span></span> | - | <span data-ttu-id="95733-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="95733-124">autodiscover</span></span> | <span data-ttu-id="95733-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="95733-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="95733-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="95733-127">Exchange-Auto Ermittlungs Eintrag</span><span class="sxs-lookup"><span data-stu-id="95733-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="95733-128">Wenn Sie Exchange Server lokal haben, sollten Sie den vorhandenen Datensatz bei der Migration zu Exchange Online beibehalten und diesen Eintrag aktualisieren, nachdem Sie die Migration abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="95733-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="95733-129">Exchange Online MX-Eintrag</span><span class="sxs-lookup"><span data-stu-id="95733-129">Exchange Online MX Record</span></span>

<span data-ttu-id="95733-130">Der Wert des MX-Eintrags für Ihre akzeptierten Domänen folgt einem Standardformat, wie oben erwähnt: *Tenant*. Mail.Protection.office365.US, das den *Mandanten* durch den ersten Teil des Standardmandanten namens ersetzt.</span><span class="sxs-lookup"><span data-stu-id="95733-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="95733-131">Wenn Ihr Mandantenname beispielsweise contoso.onmicrosoft.US lautet, verwenden Sie **contoso.Mail.Protection.office365.US** als Wert für den MX-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="95733-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="95733-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95733-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="95733-133">CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="95733-133">CNAME records</span></span>

| <span data-ttu-id="95733-134">Typ</span><span class="sxs-lookup"><span data-stu-id="95733-134">Type</span></span> | <span data-ttu-id="95733-135">Hostname</span><span class="sxs-lookup"><span data-stu-id="95733-135">Host name</span></span> | <span data-ttu-id="95733-136">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="95733-136">Points to address or value</span></span> | <span data-ttu-id="95733-137">TTL</span><span class="sxs-lookup"><span data-stu-id="95733-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="95733-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="95733-138">CNAME</span></span> | <span data-ttu-id="95733-139">sip</span><span class="sxs-lookup"><span data-stu-id="95733-139">sip</span></span> | <span data-ttu-id="95733-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="95733-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="95733-141">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-141">1 Hour</span></span> |
| <span data-ttu-id="95733-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="95733-142">CNAME</span></span> | <span data-ttu-id="95733-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="95733-143">lyncdiscover</span></span> | <span data-ttu-id="95733-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="95733-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="95733-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="95733-146">SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="95733-146">SRV records</span></span>

| <span data-ttu-id="95733-147">Typ</span><span class="sxs-lookup"><span data-stu-id="95733-147">Type</span></span> | <span data-ttu-id="95733-148">Dienst</span><span class="sxs-lookup"><span data-stu-id="95733-148">Service</span></span> | <span data-ttu-id="95733-149">Protokoll</span><span class="sxs-lookup"><span data-stu-id="95733-149">Protocol</span></span> | <span data-ttu-id="95733-150">Port</span><span class="sxs-lookup"><span data-stu-id="95733-150">Port</span></span> | <span data-ttu-id="95733-151">Schriftbreite</span><span class="sxs-lookup"><span data-stu-id="95733-151">Weight</span></span> | <span data-ttu-id="95733-152">Priorität</span><span class="sxs-lookup"><span data-stu-id="95733-152">Priority</span></span> | <span data-ttu-id="95733-153">Name</span><span class="sxs-lookup"><span data-stu-id="95733-153">Name</span></span> | <span data-ttu-id="95733-154">Ziel</span><span class="sxs-lookup"><span data-stu-id="95733-154">Target</span></span> | <span data-ttu-id="95733-155">TTL</span><span class="sxs-lookup"><span data-stu-id="95733-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="95733-156">SRV</span><span class="sxs-lookup"><span data-stu-id="95733-156">SRV</span></span> | <span data-ttu-id="95733-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="95733-157">\_sip</span></span> | <span data-ttu-id="95733-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="95733-158">\_tls</span></span> | <span data-ttu-id="95733-159">443</span><span class="sxs-lookup"><span data-stu-id="95733-159">443</span></span> | <span data-ttu-id="95733-160">1</span><span class="sxs-lookup"><span data-stu-id="95733-160">1</span></span> | <span data-ttu-id="95733-161">100</span><span class="sxs-lookup"><span data-stu-id="95733-161">100</span></span> | @ | <span data-ttu-id="95733-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="95733-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="95733-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-163">1 Hour</span></span> |
| <span data-ttu-id="95733-164">SRV</span><span class="sxs-lookup"><span data-stu-id="95733-164">SRV</span></span> | <span data-ttu-id="95733-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="95733-165">\_sipfederationtls</span></span> | <span data-ttu-id="95733-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="95733-166">\_tcp</span></span> | <span data-ttu-id="95733-167">5061</span><span class="sxs-lookup"><span data-stu-id="95733-167">5061</span></span> | <span data-ttu-id="95733-168">1</span><span class="sxs-lookup"><span data-stu-id="95733-168">1</span></span> | <span data-ttu-id="95733-169">100</span><span class="sxs-lookup"><span data-stu-id="95733-169">100</span></span> | @ | <span data-ttu-id="95733-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="95733-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="95733-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="95733-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="95733-172">Zusätzliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="95733-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95733-173">Wenn Sie einen vorhandenen *msoID* -CNAME-Eintrag in Ihrer DNS-Zone haben, müssen Sie den Datensatz zu diesem Zeitpunkt aus DNS **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="95733-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="95733-174">Der msoID-Eintrag ist nicht mit Microsoft 365 Enterprise-apps *(ehemals Office 365 ProPlus)* kompatibel und verhindert, dass die Aktivierung erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95733-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
