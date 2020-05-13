---
title: Voraussetzungen für Microsoft Threat Protection
description: Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft Threat Protection kennen.
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, kaufen
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209235"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="48432-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="48432-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="48432-105">**Applies to:**</span></span>
- <span data-ttu-id="48432-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="48432-107">Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="48432-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="48432-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="48432-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="48432-109">Ab dem 12. Mai 2020 wird Microsoft schrittweise neue, optimierte Erfahrungen rund um die Lizenzanforderungen einführen und [Microsoft Threat Protection aktivieren](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="48432-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="48432-110">Einige Wochen während dieses Zeitraums werden einige Kunden beginnen, Änderungen an Ihren Portal-Erlebnissen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="48432-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="48432-111">Informationen zu den neuen Erfahrungen sind in diesem Artikel als **neue Erfahrung** markiert.</span><span class="sxs-lookup"><span data-stu-id="48432-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="48432-112">Um Microsoft Threat Protection verwenden zu können, benötigen Sie entweder eine einzelne Lizenz oder eine Kombination aus Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="48432-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="48432-113">Diese Lizenzen oder Lizenz Kombinationen ermöglichen den Zugriff auf Microsoft Threat Protection-Features ohne zusätzliche Kosten.</span><span class="sxs-lookup"><span data-stu-id="48432-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="48432-114">Einzelne Lizenz</span><span class="sxs-lookup"><span data-stu-id="48432-114">Single license</span></span>
<span data-ttu-id="48432-115">Sie können *eine* der folgenden Lizenzen verwenden:</span><span class="sxs-lookup"><span data-stu-id="48432-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="48432-116">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="48432-117">Microsoft 365 E5 Sicherheit oder a5-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="48432-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="48432-118">Kombination von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="48432-118">Combination of licenses</span></span>
<span data-ttu-id="48432-119">Sie können auch eine Kombination aus Lizenzen für E5-oder A5-Abonnements für Office 365, *Enterprise Mobility + Security (EMS)* und Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="48432-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="48432-120">Die Lizenzkombination muss *alle* diese Lizenzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="48432-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="48432-121">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="48432-122">*Enterprise Mobility + Security (EMS)* E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="48432-123">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="48432-124">Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="48432-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="48432-125">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="48432-125">Don't have license yet?</span></span> [<span data-ttu-id="48432-126">Testen oder Kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="48432-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="48432-127">**Neue Erfahrung:** Ab dem 12. Mai 2020 werden Kunden allmählich Änderungen an dieser Erfahrung erhalten.</span><span class="sxs-lookup"><span data-stu-id="48432-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="48432-128">Für Personen mit der neuen Benutzeroberfläche steht Ihnen die Option zum Aktivieren von Microsoft Threat Protection für *alle* Kunden mit einer der folgenden Lizenzen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="48432-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="48432-129">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="48432-130">Microsoft 365 E5 Sicherheit oder a5-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="48432-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="48432-131">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="48432-132">Enterprise Mobility + Security (EMS) E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="48432-133">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="48432-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="48432-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="48432-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="48432-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48432-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="48432-137">Office 365 Advanced Threat Protection (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="48432-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="48432-138">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="48432-138">Check your existing  licenses</span></span>
<span data-ttu-id="48432-139">Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="48432-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="48432-140">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="48432-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="48432-141">Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="48432-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="48432-142">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="48432-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="48432-143">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="48432-143">Browser requirements</span></span>
<span data-ttu-id="48432-144">Greifen Sie auf Microsoft Threat Protection im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="48432-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="us-gcc-and-gcc-high-availability"></a><span data-ttu-id="48432-145">Hohe Verfügbarkeit von US gcc und gcc</span><span class="sxs-lookup"><span data-stu-id="48432-145">US GCC and GCC High availability</span></span>
<span data-ttu-id="48432-146">Derzeit steht Microsoft Threat Protection nicht für US Government Community Cloud (gcc) und Government Community Cloud High (gcc High) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="48432-146">Currently, Microsoft Threat Protection is not available to US Government Community Cloud (GCC) and Government Community Cloud High (GCC High) customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="48432-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="48432-147">Related topics</span></span>
- [<span data-ttu-id="48432-148">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="48432-149">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48432-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
