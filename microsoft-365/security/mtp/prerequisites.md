---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft 365 Defender
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, kaufen
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930090"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="69d54-104">Voraussetzungen für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69d54-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69d54-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="69d54-105">**Applies to:**</span></span>
- <span data-ttu-id="69d54-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69d54-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="69d54-107">Erfahren Sie mehr über Lizenzierung und andere Anforderungen für die Bereitstellung und Verwendung [von Microsoft 365 Defender.](microsoft-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="69d54-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="69d54-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="69d54-108">Licensing requirements</span></span>
<span data-ttu-id="69d54-109">Jede dieser Lizenzen ermöglicht Ihnen den Zugriff auf Microsoft 365 Defender-Features im Microsoft 365 Security Center ohne zusätzliche Kosten:</span><span class="sxs-lookup"><span data-stu-id="69d54-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="69d54-110">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="69d54-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="69d54-111">Microsoft 365 E5 Security oder A5 Security</span><span class="sxs-lookup"><span data-stu-id="69d54-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="69d54-112">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="69d54-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="69d54-113">Enterprise Mobility + Security (EMS) E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="69d54-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="69d54-114">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="69d54-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="69d54-115">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="69d54-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="69d54-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="69d54-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="69d54-117">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69d54-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="69d54-118">Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="69d54-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="69d54-119">Testlizenzen für Office 365 bieten derzeit keinen Zugriff auf Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="69d54-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="69d54-120">Weitere Informationen finden Sie [in den Microsoft 365 Enterprise-Serviceplänen.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="69d54-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="69d54-121">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="69d54-121">Don't have license yet?</span></span> [<span data-ttu-id="69d54-122">Testen oder Kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="69d54-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="69d54-123">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="69d54-123">Check your existing  licenses</span></span>
<span data-ttu-id="69d54-124">Wechseln Sie zum Microsoft 365 Admin Center ([admin.microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="69d54-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="69d54-125">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="69d54-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="69d54-126">Sie müssen entweder dem  Abrechnungsadministrator oder der Rolle des globalen **Lesers** [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="69d54-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="69d54-127">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="69d54-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="69d54-128">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="69d54-128">Required permissions</span></span>
<span data-ttu-id="69d54-129">Sie müssen ein globaler **Administrator oder** ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69d54-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="69d54-130">Eine Liste der Rollen, die für die Verwendung von Microsoft 365 Defender erforderlich sind, sowie Informationen dazu, wie der Zugriff auf Daten reguliert ist, finden Sie unter Verwaltung des Zugriffs auf [Microsoft 365 Defender.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="69d54-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="69d54-131">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="69d54-131">Browser requirements</span></span>
<span data-ttu-id="69d54-132">Greifen Sie auf Microsoft 365 Defender im Microsoft 365 Security Center mithilfe von Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-kompatiblen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="69d54-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="69d54-133">Verfügbarkeit für GCC, GCC High und andere US-Regierungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="69d54-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="69d54-134">Derzeit ist Microsoft 365 Defender *nicht* verfügbar für:</span><span class="sxs-lookup"><span data-stu-id="69d54-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="69d54-135">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="69d54-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="69d54-136">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="69d54-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="69d54-137">US-Verteidigungsministeriums</span><span class="sxs-lookup"><span data-stu-id="69d54-137">US Department of Defense</span></span>
- <span data-ttu-id="69d54-138">Alle US-Regierungseinrichtungen mit kommerziellen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="69d54-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="69d54-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="69d54-139">Related topics</span></span>
- [<span data-ttu-id="69d54-140">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69d54-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="69d54-141">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69d54-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="69d54-142">Verwalten von Zugriff und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="69d54-142">Manage access and permissions</span></span>](mtp-permissions.md)
