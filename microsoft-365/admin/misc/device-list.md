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
description: Hier erfahren Sie, wie Sie eine CSV-Datei für AutoPilo Tin Microsoft 365 Business erstellen.
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361356"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="abdb8-103">CSV-Datei einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="abdb8-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="abdb8-104">CSV-Dateiformat einer Geräteliste</span><span class="sxs-lookup"><span data-stu-id="abdb8-104">Device list .csv file format</span></span>

<span data-ttu-id="abdb8-105">Zum Verwalten und Bereitstellen von Geräten über Windows AutoPilot benötigen Sie eine CSV-Datei, die spezifische Informationen zu den Geräten enthält.</span><span class="sxs-lookup"><span data-stu-id="abdb8-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="abdb8-106">Die Spalten in der Gerätelistendatei müssen folgende Überschriften in der angegebenen Reihenfolge aufweisen:</span><span class="sxs-lookup"><span data-stu-id="abdb8-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="abdb8-107">Spalte A: Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="abdb8-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="abdb8-108">Spalte B: leer lassen</span><span class="sxs-lookup"><span data-stu-id="abdb8-108">Column B: leave blank</span></span>

- <span data-ttu-id="abdb8-109">Spalte C: Hardwarehash</span><span class="sxs-lookup"><span data-stu-id="abdb8-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="abdb8-110">Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="abdb8-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="abdb8-p101">Wenn Sie Geräte hinzufügen, müssen Sie sie auch einem Profil hinzufügen. Ein Profil dient zum Anwenden von AutoPilot-Bereitstellungsprofilen zu einem Gerät oder einer Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="abdb8-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="abdb8-113">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="abdb8-113">Related articles</span></span>

[<span data-ttu-id="abdb8-114">Microsoft 365 Business-Dokumentation und -Ressourcen</span><span class="sxs-lookup"><span data-stu-id="abdb8-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="abdb8-115">Erste Schritte mit Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="abdb8-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="abdb8-116">Verwalten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="abdb8-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
