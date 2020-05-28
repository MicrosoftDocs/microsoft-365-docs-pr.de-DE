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
description: Hier erfahren Sie, wie Sie eine CSV-Datei für Autopilot in Microsoft 365 for Business erstellen.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399362"
---
# <a name="device-list-csv-file"></a>CSV-Datei einer Geräteliste

## <a name="device-list-csv-file-format"></a>CSV-Dateiformat einer Geräteliste

Zum Verwalten und Bereitstellen von Geräten über Windows AutoPilot benötigen Sie eine CSV-Datei, die spezifische Informationen zu den Geräten enthält.
  
Die Spalten in der Gerätelistendatei müssen folgende Überschriften in der angegebenen Reihenfolge aufweisen:
  
- Spalte A: Seriennummer des Geräts

- Spalte B: leer lassen

- Spalte C: Hardwarehash

Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert. 

Wenn Sie Geräte hinzufügen, müssen Sie sie auch einem Profil hinzufügen. Ein Profil dient zum Anwenden von AutoPilot-Bereitstellungsprofilen zu einem Gerät oder einer Gerätegruppe.
  
## <a name="related-articles"></a>Verwandte Artikel

[Dokumentation und Ressourcen zu Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Erste Schritte mit Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Verwalten von Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/business/manage)
  
