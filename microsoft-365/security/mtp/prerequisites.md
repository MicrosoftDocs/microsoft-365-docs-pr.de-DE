---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen und andere Konfigurationseinstellungen für Microsoft 365 Defender
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, Kauf
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918870"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="7b661-104">Voraussetzungen für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b661-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b661-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7b661-105">**Applies to:**</span></span>
- <span data-ttu-id="7b661-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b661-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7b661-107">Erfahren Sie mehr über die Lizenzierung und andere Anforderungen für die Bereitstellung und Verwendung von [Microsoft 365 Defender](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7b661-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7b661-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="7b661-108">Licensing requirements</span></span>
<span data-ttu-id="7b661-109">Jede dieser Lizenzen ermöglicht Ihnen den Zugriff auf Microsoft 365 Defender-Features im Microsoft 365 Security Center ohne zusätzliche Kosten:</span><span class="sxs-lookup"><span data-stu-id="7b661-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="7b661-110">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7b661-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="7b661-111">Microsoft 365 E5 Security oder A5 Security</span><span class="sxs-lookup"><span data-stu-id="7b661-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="7b661-112">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7b661-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="7b661-113">Enterprise Mobility + Security (EMS) E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7b661-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="7b661-114">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="7b661-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="7b661-115">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7b661-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="7b661-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7b661-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="7b661-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7b661-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="7b661-118">Microsoft Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="7b661-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="7b661-119">Weitere Informationen finden Sie [in den Microsoft 365 Enterprise-Dienstplänen.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="7b661-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="7b661-120">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="7b661-120">Don't have license yet?</span></span> [<span data-ttu-id="7b661-121">Testen oder Kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="7b661-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="7b661-122">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7b661-122">Check your existing  licenses</span></span>
<span data-ttu-id="7b661-123">Wechseln Sie zu Microsoft 365 Admin Center ([admin.microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7b661-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="7b661-124">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="7b661-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="7b661-125">Sie müssen entweder der  Rolle "Abrechnungsadministrator" oder **"Globaler** [Leser" in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen werden, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="7b661-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="7b661-126">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="7b661-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7b661-127">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7b661-127">Required permissions</span></span>
<span data-ttu-id="7b661-128">Sie müssen ein globaler Administrator **oder** **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender aktivieren zu können.</span><span class="sxs-lookup"><span data-stu-id="7b661-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="7b661-129">Eine Liste der für die Verwendung von Microsoft 365 Defender erforderlichen Rollen und Informationen zur Regulierung des Zugriffs auf Daten finden Sie unter Verwalten des Zugriffs auf [Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7b661-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="7b661-130">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="7b661-130">Browser requirements</span></span>
<span data-ttu-id="7b661-131">Zugreifen auf Microsoft 365 Defender im Microsoft 365 Security Center mithilfe von Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-kompatiblen Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="7b661-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="7b661-132">Verfügbarkeit für us GCC, GCC High und andere US Government Institutions</span><span class="sxs-lookup"><span data-stu-id="7b661-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="7b661-133">Derzeit steht Microsoft 365 Defender *nicht* zur Verfügung für:</span><span class="sxs-lookup"><span data-stu-id="7b661-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="7b661-134">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="7b661-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="7b661-135">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="7b661-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="7b661-136">US Department of Defense</span><span class="sxs-lookup"><span data-stu-id="7b661-136">US Department of Defense</span></span>
- <span data-ttu-id="7b661-137">Alle US-Behörden mit kommerziellen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7b661-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b661-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7b661-138">Related topics</span></span>
- [<span data-ttu-id="7b661-139">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b661-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7b661-140">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b661-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="7b661-141">Verwalten von Zugriff und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7b661-141">Manage access and permissions</span></span>](mtp-permissions.md)