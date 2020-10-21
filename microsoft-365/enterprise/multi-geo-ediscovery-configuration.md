---
title: Konfigurieren von Microsoft 365 Multi-Geo eDiscovery
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: In diesem Artikel erfahren Sie, wie Sie mithilfe des Parameters Region eDiscovery für die Verwendung an Satellitenstandorten in Microsoft 365 Multi-Geo konfigurieren.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636805"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="16f12-103">Konfiguration von Microsoft 365 Multi-Geo eDiscovery</span><span class="sxs-lookup"><span data-stu-id="16f12-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="16f12-104">Mit den [erweiterten eDiscovery-Funktionen](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) kann ein Multi-Geo-eDiscovery-Administrator alle GEOSS durchsuchen, ohne einen Sicherheitsfilter für die Region verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="16f12-104">[Advanced eDiscovery capabilities](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="16f12-105">Daten werden in die Azure-Instanz des zentralen Speicherorts des Multi-Geo-Mandanten exportiert.</span><span class="sxs-lookup"><span data-stu-id="16f12-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="16f12-106">Ohne erweiterte eDiscovery-Funktionen kann ein eDiscovery-Manager oder Administrator eines Multi-Geo-Mandanten eDiscovery nur am zentralen Standort dieses Mandanten durchführen.</span><span class="sxs-lookup"><span data-stu-id="16f12-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="16f12-107">Um die Möglichkeit zur Durchführung von eDiscovery für Satellitenstandorte zu unterstützen, steht ein neuer Kompatibilitäts Sicherheitsfilter Parameter mit dem Namen "Region" über PowerShell zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="16f12-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="16f12-108">Dieser Parameter kann von Mandanten verwendet werden, deren zentraler Standort in Nordamerika, Europa oder im asiatisch-pazifischen Raum liegt.</span><span class="sxs-lookup"><span data-stu-id="16f12-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="16f12-109">Erweiterte eDiscovery wird für Mandanten empfohlen, deren zentraler Standort nicht in Nordamerika, Europa oder im asiatisch-pazifischen Raum liegt und die eDiscovery über Satelliten geografische Standorte hinweg ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="16f12-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="16f12-110">Der globale Microsoft 365-Administrator muss eDiscovery-Managerberechtigungen zuweisen, damit andere Personen eDiscovery durchführen können, und einen "Region"-Parameter im entsprechenden Compliancesicherheitsfilter zuweisen, um die Region zum Durchführen von eDiscovery als Satellitenstandort festzulegen. Andernfalls wird eDiscovery nicht für den Satellitenstandort durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="16f12-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="16f12-p103">Wenn die eDiscovery-Manager- oder Administratorrolle für einen bestimmten Satellitenstandort festgelegt ist, kann der eDiscovery-Manager oder Administrator nur eDiscovery-Suchaktionen für die SharePoint-Websites und OneDrive-Websites an diesem Satellitenstandort durchführen. Wenn ein eDiscovery-Manager oder Administrator versucht, SharePoint- oder OneDrive-Websites außerhalb des angegebenen Satellitenstandorts zu durchsuchen, werden keine Ergebnisse zurückgegeben. Wenn der eDiscovery-Manager oder Administrator für einen Satellitenstandort einen Export auslöst, werden Daten in der Azure-Instanz dieses Bereichs exportiert. So können Organisationen Compliance gewährleisten, indem nicht zugelassen wird, dass Inhalte über den kontrollierten Rahmen hinaus exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="16f12-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="16f12-115">Wenn ein eDiscovery-Manager mehrere SharePoint-Satellitenstandorte durchsuchen möchte, muss ein anderes Benutzerkonto für den eDiscovery-Manager erstellt werden, das den alternativen Satellitenstandort angibt, in dem sich OneDrive- oder SharePoint-Websites befinden.</span><span class="sxs-lookup"><span data-stu-id="16f12-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="16f12-116">So legen Sie den Compliancesicherheitsfilter für eine Region fest</span><span class="sxs-lookup"><span data-stu-id="16f12-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="16f12-117">Herstellen einer Verbindung mit Microsoft 365 Security Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="16f12-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="16f12-118">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="16f12-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="16f12-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="16f12-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="16f12-120">Informationen zu weiteren Parametern und zur Syntax finden Sie im Artikel [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter).</span><span class="sxs-lookup"><span data-stu-id="16f12-120">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
