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
description: 'Zusammenfassung: DNS-Einträge für Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690488"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="bf62f-103">DNS-Einträge für Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="bf62f-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="bf62f-104">*Dieser Artikel gilt für Office 365 GCC High und Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="bf62f-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="bf62f-105">Im Rahmen des Onboardings Office 365 GCC High müssen Sie Ihre SMTP- und SIP-Domänen zu Ihrem Online Services-Mandanten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf62f-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="bf62f-106">Dazu verwenden Sie das cmdlet New-MsolDomain in Azure AD PowerShell oder verwenden das [Azure Government Portal,](https://portal.azure.us) um mit dem Hinzufügen der Domäne und dem Nachweis des Besitzes zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="bf62f-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="bf62f-107">Nachdem Sie Ihre Domänen zu Ihrem Mandanten hinzugefügt und überprüft haben, verwenden Sie die folgenden Anleitungen, um die entsprechenden DNS-Einträge für die folgenden Dienste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf62f-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="bf62f-108">Möglicherweise müssen Sie die folgende Tabelle an die Anforderungen Ihrer Organisation im Hinblick auf die eingehenden MX-Einträge und alle vorhandenen Exchange AutoErmittlungsdatensatz(n) anpassen.</span><span class="sxs-lookup"><span data-stu-id="bf62f-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="bf62f-109">Es wird dringend empfohlen, diese DNS-Einträge mit Ihrem Messagingteam zu koordinieren, um Ausfälle oder fehlgeleitete E-Mails zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="bf62f-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="bf62f-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf62f-110">Exchange Online</span></span>

| <span data-ttu-id="bf62f-111">Type</span><span class="sxs-lookup"><span data-stu-id="bf62f-111">Type</span></span> | <span data-ttu-id="bf62f-112">Priority</span><span class="sxs-lookup"><span data-stu-id="bf62f-112">Priority</span></span> | <span data-ttu-id="bf62f-113">Hostname</span><span class="sxs-lookup"><span data-stu-id="bf62f-113">Host name</span></span> | <span data-ttu-id="bf62f-114">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="bf62f-114">Points to address or value</span></span> | <span data-ttu-id="bf62f-115">TTL</span><span class="sxs-lookup"><span data-stu-id="bf62f-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="bf62f-116">MX</span><span class="sxs-lookup"><span data-stu-id="bf62f-116">MX</span></span> | <span data-ttu-id="bf62f-117">0</span><span class="sxs-lookup"><span data-stu-id="bf62f-117">0</span></span> | @ | <span data-ttu-id="bf62f-118">*Mandant*.mail.protection.office365.us (weitere Details finden Sie unten)</span><span class="sxs-lookup"><span data-stu-id="bf62f-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="bf62f-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-119">1 Hour</span></span> |
| <span data-ttu-id="bf62f-120">TXT</span><span class="sxs-lookup"><span data-stu-id="bf62f-120">TXT</span></span> | - | @ | <span data-ttu-id="bf62f-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="bf62f-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="bf62f-122">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-122">1 Hour</span></span> |
| <span data-ttu-id="bf62f-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf62f-123">CNAME</span></span> | - | <span data-ttu-id="bf62f-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bf62f-124">autodiscover</span></span> | <span data-ttu-id="bf62f-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="bf62f-125">autodiscover.office365.us</span></span> | <span data-ttu-id="bf62f-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="bf62f-127">Exchange AutoErmittlungsdatensatz</span><span class="sxs-lookup"><span data-stu-id="bf62f-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="bf62f-128">Wenn Sie über Exchange Server verfügen, wird empfohlen, den vorhandenen Datensatz während der Migration zu Exchange Online zu erhalten, und diesen Datensatz zu aktualisieren, sobald Sie die Migration abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="bf62f-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="bf62f-129">Exchange Online MX-Eintrag</span><span class="sxs-lookup"><span data-stu-id="bf62f-129">Exchange Online MX Record</span></span>

<span data-ttu-id="bf62f-130">Der WERT des MX-Eintrags für Ihre akzeptierten Domänen folgt einem  Standardformat wie oben *erwähnt:* Mandant .mail.protection.office365.us, das den Mandanten durch den ersten Teil Des Standard mandantennamens ersetzt.</span><span class="sxs-lookup"><span data-stu-id="bf62f-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="bf62f-131">Wenn Ihr Mandantenname z. B. contoso.onmicrosoft.us ist, verwenden Sie **contoso.mail.protection.office365.us** als Wert für Ihren MX-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="bf62f-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="bf62f-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bf62f-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="bf62f-133">#A0</span><span class="sxs-lookup"><span data-stu-id="bf62f-133">CNAME records</span></span>

| <span data-ttu-id="bf62f-134">Typ</span><span class="sxs-lookup"><span data-stu-id="bf62f-134">Type</span></span> | <span data-ttu-id="bf62f-135">Hostname</span><span class="sxs-lookup"><span data-stu-id="bf62f-135">Host name</span></span> | <span data-ttu-id="bf62f-136">Verweist auf Adresse oder Wert</span><span class="sxs-lookup"><span data-stu-id="bf62f-136">Points to address or value</span></span> | <span data-ttu-id="bf62f-137">TTL</span><span class="sxs-lookup"><span data-stu-id="bf62f-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="bf62f-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf62f-138">CNAME</span></span> | <span data-ttu-id="bf62f-139">sip</span><span class="sxs-lookup"><span data-stu-id="bf62f-139">sip</span></span> | <span data-ttu-id="bf62f-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bf62f-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="bf62f-141">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-141">1 Hour</span></span> |
| <span data-ttu-id="bf62f-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf62f-142">CNAME</span></span> | <span data-ttu-id="bf62f-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bf62f-143">lyncdiscover</span></span> | <span data-ttu-id="bf62f-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bf62f-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="bf62f-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="bf62f-146">SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="bf62f-146">SRV records</span></span>

| <span data-ttu-id="bf62f-147">Typ</span><span class="sxs-lookup"><span data-stu-id="bf62f-147">Type</span></span> | <span data-ttu-id="bf62f-148">Dienst</span><span class="sxs-lookup"><span data-stu-id="bf62f-148">Service</span></span> | <span data-ttu-id="bf62f-149">Protokoll</span><span class="sxs-lookup"><span data-stu-id="bf62f-149">Protocol</span></span> | <span data-ttu-id="bf62f-150">Port</span><span class="sxs-lookup"><span data-stu-id="bf62f-150">Port</span></span> | <span data-ttu-id="bf62f-151">Schriftbreite</span><span class="sxs-lookup"><span data-stu-id="bf62f-151">Weight</span></span> | <span data-ttu-id="bf62f-152">Priorität</span><span class="sxs-lookup"><span data-stu-id="bf62f-152">Priority</span></span> | <span data-ttu-id="bf62f-153">Name</span><span class="sxs-lookup"><span data-stu-id="bf62f-153">Name</span></span> | <span data-ttu-id="bf62f-154">Ziel</span><span class="sxs-lookup"><span data-stu-id="bf62f-154">Target</span></span> | <span data-ttu-id="bf62f-155">TTL</span><span class="sxs-lookup"><span data-stu-id="bf62f-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="bf62f-156">SRV</span><span class="sxs-lookup"><span data-stu-id="bf62f-156">SRV</span></span> | <span data-ttu-id="bf62f-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="bf62f-157">\_sip</span></span> | <span data-ttu-id="bf62f-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="bf62f-158">\_tls</span></span> | <span data-ttu-id="bf62f-159">443</span><span class="sxs-lookup"><span data-stu-id="bf62f-159">443</span></span> | <span data-ttu-id="bf62f-160">1</span><span class="sxs-lookup"><span data-stu-id="bf62f-160">1</span></span> | <span data-ttu-id="bf62f-161">100</span><span class="sxs-lookup"><span data-stu-id="bf62f-161">100</span></span> | @ | <span data-ttu-id="bf62f-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bf62f-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="bf62f-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-163">1 Hour</span></span> |
| <span data-ttu-id="bf62f-164">SRV</span><span class="sxs-lookup"><span data-stu-id="bf62f-164">SRV</span></span> | <span data-ttu-id="bf62f-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bf62f-165">\_sipfederationtls</span></span> | <span data-ttu-id="bf62f-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="bf62f-166">\_tcp</span></span> | <span data-ttu-id="bf62f-167">5061</span><span class="sxs-lookup"><span data-stu-id="bf62f-167">5061</span></span> | <span data-ttu-id="bf62f-168">1</span><span class="sxs-lookup"><span data-stu-id="bf62f-168">1</span></span> | <span data-ttu-id="bf62f-169">100</span><span class="sxs-lookup"><span data-stu-id="bf62f-169">100</span></span> | @ | <span data-ttu-id="bf62f-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="bf62f-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="bf62f-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="bf62f-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="bf62f-172">Zusätzliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="bf62f-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf62f-173">Wenn Sie über einen *vorhandenen msoid-CNAME-Eintrag* in Ihrer #A0 verfügen, müssen Sie den Eintrag zu diesem Zeitpunkt aus DNS entfernen. </span><span class="sxs-lookup"><span data-stu-id="bf62f-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="bf62f-174">Der msoid-Datensatz ist mit Microsoft 365 Enterprise Apps *(früher Office 365 ProPlus)* nicht kompatibel und verhindert, dass die Aktivierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="bf62f-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
