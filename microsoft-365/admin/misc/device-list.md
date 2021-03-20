---
title: CSV-Datei einer Geräteliste
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Erfahren Sie, wie Sie eine CSV-Datei für AutoPilot in Microsoft 365 Business erstellen.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914738"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="daceb-103">CSV-Datei einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="daceb-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="daceb-104">CSV-Dateiformat einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="daceb-104">Device list .csv file format</span></span>

<span data-ttu-id="daceb-105">Zum Verwalten und Bereitstellen von Geräten über Windows AutoPilot benötigen Sie eine CSV-Datei, die spezifische Informationen zu den Geräten enthält.</span><span class="sxs-lookup"><span data-stu-id="daceb-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="daceb-106">Die Spalten in der Gerätelistendatei müssen folgende Überschriften in der angegebenen Reihenfolge aufweisen:</span><span class="sxs-lookup"><span data-stu-id="daceb-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="daceb-107">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="daceb-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="daceb-108">Spalte B: Leer lassen</span><span class="sxs-lookup"><span data-stu-id="daceb-108">Column B: leave blank</span></span>

- <span data-ttu-id="daceb-109">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="daceb-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="daceb-110">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="daceb-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="daceb-p101">Wenn Sie Geräte hinzufügen, müssen Sie sie auch einem Profil hinzufügen. Ein Profil dient zum Anwenden von AutoPilot-Bereitstellungsprofilen zu einem Gerät oder einer Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="daceb-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="daceb-113">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="daceb-113">Related articles</span></span>

[<span data-ttu-id="daceb-114">Microsoft 365 Business-Dokumentation und -Ressourcen</span><span class="sxs-lookup"><span data-stu-id="daceb-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="daceb-115">Erste Schritte mit Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="daceb-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="daceb-116">Verwalten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="daceb-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
