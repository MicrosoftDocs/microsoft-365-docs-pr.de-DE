---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für Microsoft 365 Defender.
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844776"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="54744-104">Voraussetzungen für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54744-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="54744-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="54744-105">**Applies to:**</span></span>
- <span data-ttu-id="54744-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54744-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="54744-107">Erfahren Sie mehr über Lizenzierung und andere Anforderungen für die Einrichtung und Verwendung von [Microsoft 365 Defender](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="54744-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="54744-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="54744-108">Licensing requirements</span></span>
<span data-ttu-id="54744-109">Durch diese Lizenzen erhalten Sie ohne zusätzliche Kosten Zugriff auf Microsoft 365 Defender-Funktionen im Microsoft 365 Security Center:</span><span class="sxs-lookup"><span data-stu-id="54744-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="54744-110">Microsoft 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="54744-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="54744-111">Microsoft 365 E5 Sicherheit oder a5-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="54744-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="54744-112">Windows 10 Enterprise E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="54744-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="54744-113">Enterprise Mobility + Security (EMS) E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="54744-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="54744-114">Office 365 E5 oder A5</span><span class="sxs-lookup"><span data-stu-id="54744-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="54744-115">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="54744-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="54744-116">Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="54744-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="54744-117">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="54744-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="54744-118">Verteidiger für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="54744-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="54744-119">Testlizenzen für Office 365 bieten derzeit keinen Zugriff auf Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="54744-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="54744-120">Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="54744-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="54744-121">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="54744-121">Don't have license yet?</span></span> [<span data-ttu-id="54744-122">Testen oder Kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="54744-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="54744-123">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54744-123">Check your existing  licenses</span></span>
<span data-ttu-id="54744-124">Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="54744-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="54744-125">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="54744-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="54744-126">Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="54744-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="54744-127">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="54744-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="54744-128">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="54744-128">Required permissions</span></span>
<span data-ttu-id="54744-129">Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="54744-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="54744-130">Eine Liste der Rollen, die für die Verwendung von Microsoft 365 Defender erforderlich sind, sowie Informationen darüber, wie der Zugriff auf Daten reguliert wird, finden Sie unter [Managing Access to Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="54744-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="54744-131">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="54744-131">Browser requirements</span></span>
<span data-ttu-id="54744-132">Greifen Sie auf Microsoft 365 Defender im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="54744-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="54744-133">Verfügbarkeit für US gcc, gcc High und andere US-Regierungsinstitutionen</span><span class="sxs-lookup"><span data-stu-id="54744-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="54744-134">Derzeit steht Microsoft 365 Defender *nicht* für Folgendes zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="54744-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="54744-135">US Government Community Cloud (gcc)</span><span class="sxs-lookup"><span data-stu-id="54744-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="54744-136">US Government Community Cloud High (gcc hoch)</span><span class="sxs-lookup"><span data-stu-id="54744-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="54744-137">US-Verteidigungsministerium</span><span class="sxs-lookup"><span data-stu-id="54744-137">US Department of Defense</span></span>
- <span data-ttu-id="54744-138">Alle US-Regierungsinstitutionen mit kommerziellen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54744-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="54744-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="54744-139">Related topics</span></span>
- [<span data-ttu-id="54744-140">Microsoft 365 Defender (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="54744-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="54744-141">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54744-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="54744-142">Verwalten von Zugriff und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="54744-142">Manage access and permissions</span></span>](mtp-permissions.md)
