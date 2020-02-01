---
title: Voraussetzungen für Microsoft Threat Protection
description: Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft Threat Protection kennen.
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz
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
ms.openlocfilehash: d45be77abd404f87484d0f8390f09f1b9bc3b8ce
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600006"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="2068a-104">Voraussetzungen für Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2068a-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="2068a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2068a-105">**Applies to:**</span></span>
- <span data-ttu-id="2068a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2068a-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2068a-107">Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen zum Ausführen und Verwenden von Microsoft 365 Security kennen.</span><span class="sxs-lookup"><span data-stu-id="2068a-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2068a-108">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2068a-108">Licensing requirements</span></span>
<span data-ttu-id="2068a-109">Für Microsoft 365 Security ist eine der folgenden Lizenzen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2068a-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="2068a-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2068a-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="2068a-111">Office 365 E5, Enterprise Mobility + Security E5 und Windows E5</span><span class="sxs-lookup"><span data-stu-id="2068a-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="2068a-112">Sie können diese Lizenzen auf der Seite [Microsoft 365 für Unternehmen](https://www.microsoft.com/en-us/microsoft-365/enterprise) erwerben.</span><span class="sxs-lookup"><span data-stu-id="2068a-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2068a-113">Überprüfen vorhandener Lizenzen</span><span class="sxs-lookup"><span data-stu-id="2068a-113">Check your existing  licenses</span></span>
<span data-ttu-id="2068a-114">Im Microsoft 365 Admin Center unter [admin.microsoft.com](https://admin.microsoft.com/) können Sie Ihre vorhandenen Lizenzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2068a-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="2068a-115">Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="2068a-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="2068a-116">Sie müssen entweder **Abrechnungsadministrator**- oder der **Globaler Leser**-[Rolle in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) angehören, um Lizenzierungsinformationen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="2068a-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="2068a-117">Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="2068a-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="2068a-118">Browseranforderungen</span><span class="sxs-lookup"><span data-stu-id="2068a-118">Browser requirements</span></span>
<span data-ttu-id="2068a-119">Der Zugriff auf das Microsoft 365 Security Center erfolgt über einen Browser.</span><span class="sxs-lookup"><span data-stu-id="2068a-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="2068a-120">Internet Explorer und Microsoft Edge werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2068a-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="2068a-121">Alle HTML5-kompatiblen Browser werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2068a-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2068a-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2068a-122">Related topics</span></span>
- [<span data-ttu-id="2068a-123">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2068a-123">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2068a-124">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2068a-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)