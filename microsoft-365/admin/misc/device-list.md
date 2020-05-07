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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Hier erfahren Sie, wie Sie eine CSV-Datei für Autopilot in Microsoft 365 for Business erstellen.
ms.openlocfilehash: c83862675db1372aa2cef27c727c04577b4cf5a3
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064651"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="6305d-103">CSV-Datei einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="6305d-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="6305d-104">CSV-Dateiformat einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="6305d-104">Device list .csv file format</span></span>

<span data-ttu-id="6305d-105">Zum Verwalten und Bereitstellen von Geräten über Windows AutoPilot benötigen Sie eine CSV-Datei, die spezifische Informationen zu den Geräten enthält.</span><span class="sxs-lookup"><span data-stu-id="6305d-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="6305d-106">Die Spalten in der Gerätelistendatei müssen folgende Überschriften in der angegebenen Reihenfolge aufweisen:</span><span class="sxs-lookup"><span data-stu-id="6305d-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="6305d-107">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="6305d-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="6305d-108">Spalte B: leer lassen</span><span class="sxs-lookup"><span data-stu-id="6305d-108">Column B: leave blank</span></span>

- <span data-ttu-id="6305d-109">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="6305d-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="6305d-110">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="6305d-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="6305d-p101">Wenn Sie Geräte hinzufügen, müssen Sie sie auch einem Profil hinzufügen. Ein Profil dient zum Anwenden von AutoPilot-Bereitstellungsprofilen zu einem Gerät oder einer Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="6305d-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6305d-113">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6305d-113">Related articles</span></span>

[<span data-ttu-id="6305d-114">Dokumentation und Ressourcen zu Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="6305d-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="6305d-115">Erste Schritte mit Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="6305d-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="6305d-116">Verwalten von Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="6305d-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
