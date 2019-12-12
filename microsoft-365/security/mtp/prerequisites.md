---
title: Voraussetzungen für Microsoft Threat Protection
description: Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft Threat Protection kennen.
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: b136dfcb11265e9ab19328d6ad0b3c515f7fc86f
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911155"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="8c3fd-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c3fd-104">Microsoft Threat Protection</span></span>

<span data-ttu-id="8c3fd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8c3fd-105">**Applies to:**</span></span>
- <span data-ttu-id="8c3fd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c3fd-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="8c3fd-107">Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen zum Ausführen und Verwenden von Microsoft 365 Security kennen.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="8c3fd-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="8c3fd-108">Licensing requirements</span></span>
<span data-ttu-id="8c3fd-109">Für Microsoft 365 Security ist eine der folgenden Lizenzen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="8c3fd-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="8c3fd-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8c3fd-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="8c3fd-111">Office 365 E5, Enterprise Mobility + Security E5 und Windows E5</span><span class="sxs-lookup"><span data-stu-id="8c3fd-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="8c3fd-112">Sie können diese Lizenzen auf der Seite [Microsoft 365 für Unternehmen](https://www.microsoft.com/en-us/microsoft-365/enterprise) erwerben.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="8c3fd-113">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="8c3fd-113">Check your existing  licenses</span></span>
<span data-ttu-id="8c3fd-114">Im Microsoft 365 Admin Center unter [admin.microsoft.com](https://admin.microsoft.com/) können Sie Ihre vorhandenen Lizenzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="8c3fd-115">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="8c3fd-116">Sie müssen entweder **Abrechnungsadministrator**- oder der **Globaler Leser**-[Rolle in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) angehören, um Lizenzierungsinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="8c3fd-117">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="8c3fd-118">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="8c3fd-118">Browser requirements</span></span>
<span data-ttu-id="8c3fd-119">Der Zugriff auf das Microsoft 365 Security Center erfolgt über einen Browser.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="8c3fd-120">Internet Explorer und Microsoft Edge werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="8c3fd-121">Alle HTML5-kompatiblen Browser werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c3fd-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c3fd-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8c3fd-122">Related topics</span></span>
- [<span data-ttu-id="8c3fd-123">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c3fd-123">Microsoft Advanced Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8c3fd-124">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c3fd-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)