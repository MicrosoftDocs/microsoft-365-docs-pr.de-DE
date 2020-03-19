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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857179"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="7d547-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7d547-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="7d547-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7d547-105">**Applies to:**</span></span>
- <span data-ttu-id="7d547-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7d547-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7d547-107">Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="7d547-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7d547-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="7d547-108">Licensing requirements</span></span>
<span data-ttu-id="7d547-109">Um Microsoft Threat Protection verwenden zu können, benötigen Sie entweder eine einzelne Lizenz oder eine Kombination aus Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="7d547-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="7d547-110">Einzelne Lizenz</span><span class="sxs-lookup"><span data-stu-id="7d547-110">Single license</span></span>
<span data-ttu-id="7d547-111">Sie können *eine* der folgenden Lizenzen verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d547-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="7d547-112">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7d547-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="7d547-113">Microsoft 365 E5 Sicherheit oder a5-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7d547-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="7d547-114">Kombination von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7d547-114">Combination of licenses</span></span>
<span data-ttu-id="7d547-115">Sie können auch eine Kombination aus Lizenzen für E5-oder A5-Abonnements für Office 365, *Enterprise Mobility + Security (EMS)* und Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d547-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="7d547-116">Die Lizenzkombination muss *alle* diese Lizenzen enthalten:</span><span class="sxs-lookup"><span data-stu-id="7d547-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="7d547-117">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7d547-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="7d547-118">*Enterprise Mobility + Security (EMS)* E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7d547-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="7d547-119">Windows E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7d547-119">Windows E5 or A5</span></span>

<span data-ttu-id="7d547-120">Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="7d547-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="7d547-121">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="7d547-121">Don't have license yet?</span></span> [<span data-ttu-id="7d547-122">Testen oder kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="7d547-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="7d547-123">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7d547-123">Check your existing  licenses</span></span>
<span data-ttu-id="7d547-124">Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d547-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="7d547-125">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="7d547-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="7d547-126">Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="7d547-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="7d547-127">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="7d547-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="7d547-128">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="7d547-128">Browser requirements</span></span>
<span data-ttu-id="7d547-129">Greifen Sie auf Microsoft Threat Protection im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="7d547-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="7d547-130">Microsoft Threat Protection für US Government Community Cloud und US Government Community Cloud High (gcc High)-Kunden</span><span class="sxs-lookup"><span data-stu-id="7d547-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="7d547-131">Derzeit steht Microsoft-Bedrohungsschutz nicht für US gcc-und gcc-High-Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7d547-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7d547-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7d547-132">Related topics</span></span>
- [<span data-ttu-id="7d547-133">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7d547-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7d547-134">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7d547-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
