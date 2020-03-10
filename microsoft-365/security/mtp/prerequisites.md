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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569043"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="66314-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66314-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="66314-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="66314-105">**Applies to:**</span></span>
- <span data-ttu-id="66314-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66314-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="66314-107">Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="66314-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="66314-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="66314-108">Licensing requirements</span></span>
<span data-ttu-id="66314-109">Für die Verwendung von Microsoft Threat Protection benötigen Sie eine der folgenden Lizenzen oder *eine* Kombination von Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="66314-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="66314-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="66314-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="66314-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="66314-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="66314-112">Office 365 E5 und "Enterprise Mobility + Security E5 (EMS E5)" und Windows E5</span><span class="sxs-lookup"><span data-stu-id="66314-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="66314-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="66314-113">Microsoft 365 A5</span></span>

<span data-ttu-id="66314-114">Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="66314-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="66314-115">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="66314-115">Don't have license yet?</span></span> [<span data-ttu-id="66314-116">Testen oder kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="66314-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="66314-117">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="66314-117">Check your existing  licenses</span></span>
<span data-ttu-id="66314-118">Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="66314-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="66314-119">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="66314-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="66314-120">Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="66314-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="66314-121">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="66314-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="66314-122">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="66314-122">Browser requirements</span></span>
<span data-ttu-id="66314-123">Greifen Sie auf Microsoft Threat Protection im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="66314-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66314-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="66314-124">Related topics</span></span>
- [<span data-ttu-id="66314-125">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66314-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="66314-126">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66314-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
