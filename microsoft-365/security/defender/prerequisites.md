---
title: Microsoft 365 Voraussetzungen für Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen und andere Konfigurationseinstellungen für Microsoft 365 Defender
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, Microsoft 365 Defender, M365, Lizenz, E5, A5, EMS, Kaufen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259403"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="083df-104">Microsoft 365 Voraussetzungen für Defender</span><span class="sxs-lookup"><span data-stu-id="083df-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="083df-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="083df-105">**Applies to:**</span></span>
- <span data-ttu-id="083df-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="083df-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="083df-107">Erfahren Sie mehr über die Lizenzierung und andere Anforderungen für die Bereitstellung und Verwendung [von Microsoft 365 Defender](microsoft-365-defender.md).</span><span class="sxs-lookup"><span data-stu-id="083df-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="083df-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="083df-108">Licensing requirements</span></span>
<span data-ttu-id="083df-109">Jede dieser Lizenzen ermöglicht Ihnen den Zugriff auf Microsoft 365 Defender-Features in Microsoft 365 Security Center ohne zusätzliche Kosten:</span><span class="sxs-lookup"><span data-stu-id="083df-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="083df-110">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="083df-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="083df-111">Microsoft 365 E3 mit dem Microsoft 365 E5 Security-Add-On</span><span class="sxs-lookup"><span data-stu-id="083df-111">Microsoft 365 E3 with the Microsoft 365 E5 Security add-on</span></span>
- <span data-ttu-id="083df-112">Microsoft 365 A3 mit dem Microsoft 365 A5 Security-Add-On</span><span class="sxs-lookup"><span data-stu-id="083df-112">Microsoft 365 A3 with the Microsoft 365 A5 Security add-on</span></span>
- <span data-ttu-id="083df-113">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="083df-113">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="083df-114">Enterprise Mobility + Security (EMS) E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="083df-114">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="083df-115">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="083df-115">Office 365 E5 or A5</span></span>
- <span data-ttu-id="083df-116">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="083df-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="083df-117">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="083df-117">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="083df-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="083df-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="083df-119">Microsoft Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="083df-119">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="083df-120">Weitere Informationen finden Sie [unter Microsoft 365 Enterprise Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="083df-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="083df-121">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="083df-121">Don't have license yet?</span></span> [<span data-ttu-id="083df-122">Testen oder Kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="083df-122">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="083df-123">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="083df-123">Check your existing  licenses</span></span>
<span data-ttu-id="083df-124">Wechseln Sie zu Microsoft 365 Admin Center ([admin.microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="083df-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="083df-125">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="083df-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="083df-126">Sie müssen entweder der  Rolle "Abrechnungsadministrator" oder **"Globaler** [Leser" in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen werden, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="083df-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="083df-127">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="083df-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="083df-128">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="083df-128">Required permissions</span></span>
<span data-ttu-id="083df-129">Sie müssen ein **globaler Administrator oder** **Sicherheitsadministrator** in Azure Active Directory sein, um defender Microsoft 365 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="083df-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="083df-130">Eine Liste der rollen, die für die Verwendung von Microsoft 365 Defender erforderlich sind, sowie Informationen zur Regulierung des Zugriffs auf Daten finden Sie unter Verwalten des Zugriffs [auf Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="083df-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="083df-131">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="083df-131">Browser requirements</span></span>
<span data-ttu-id="083df-132">Access Microsoft 365 Defender im Microsoft 365 Security Center mithilfe von Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-kompatiblen Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="083df-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="083df-133">Verfügbarkeit für US-GCC, GCC High und andere US-Regierungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="083df-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="083df-134">Derzeit ist Microsoft 365 Defender *nicht* verfügbar für:</span><span class="sxs-lookup"><span data-stu-id="083df-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="083df-135">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="083df-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="083df-136">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="083df-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="083df-137">US Department of Defense</span><span class="sxs-lookup"><span data-stu-id="083df-137">US Department of Defense</span></span>
- <span data-ttu-id="083df-138">Alle US-Behörden mit kommerziellen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="083df-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="083df-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="083df-139">Related topics</span></span>
- [<span data-ttu-id="083df-140">Microsoft 365 Übersicht über Defender</span><span class="sxs-lookup"><span data-stu-id="083df-140">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="083df-141">Microsoft 365 Defender aktivieren</span><span class="sxs-lookup"><span data-stu-id="083df-141">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="083df-142">Verwalten von Zugriff und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="083df-142">Manage access and permissions</span></span>](m365d-permissions.md)
