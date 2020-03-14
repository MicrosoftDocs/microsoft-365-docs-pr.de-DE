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
ms.openlocfilehash: 2b653575e9e79ffe3448f622ca5be2cef37999dd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633953"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="a8cb5-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8cb5-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="a8cb5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a8cb5-105">**Applies to:**</span></span>
- <span data-ttu-id="a8cb5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8cb5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a8cb5-107">Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a8cb5-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="a8cb5-108">Licensing requirements</span></span>
<span data-ttu-id="a8cb5-109">Für die Verwendung von Microsoft Threat Protection benötigen Sie eine der folgenden Lizenzen oder *eine* Kombination von Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="a8cb5-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="a8cb5-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a8cb5-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="a8cb5-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="a8cb5-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="a8cb5-112">Office 365 E5 und "Enterprise Mobility + Security E5 (EMS E5)" und Windows E5</span><span class="sxs-lookup"><span data-stu-id="a8cb5-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="a8cb5-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="a8cb5-113">Microsoft 365 A5</span></span>

<span data-ttu-id="a8cb5-114">Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="a8cb5-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="a8cb5-115">Sie haben noch keine Lizenz?</span><span class="sxs-lookup"><span data-stu-id="a8cb5-115">Don't have license yet?</span></span> [<span data-ttu-id="a8cb5-116">Testen oder kaufen eines Microsoft 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="a8cb5-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="a8cb5-117">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="a8cb5-117">Check your existing  licenses</span></span>
<span data-ttu-id="a8cb5-118">Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="a8cb5-119">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="a8cb5-120">Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="a8cb5-121">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="a8cb5-122">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="a8cb5-122">Browser requirements</span></span>
<span data-ttu-id="a8cb5-123">Greifen Sie auf Microsoft Threat Protection im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="a8cb5-124">Microsoft Threat Protection für US Government Community Cloud und US Government Community Cloud High (gcc High)-Kunden</span><span class="sxs-lookup"><span data-stu-id="a8cb5-124">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="a8cb5-125">Derzeit steht Microsoft-Bedrohungsschutz nicht für US gcc-und gcc-High-Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a8cb5-125">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="a8cb5-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a8cb5-126">Related topics</span></span>
- [<span data-ttu-id="a8cb5-127">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8cb5-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="a8cb5-128">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8cb5-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
