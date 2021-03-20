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
# <a name="device-list-csv-file"></a>CSV-Datei einer Geräteliste

## <a name="device-list-csv-file-format"></a>CSV-Dateiformat einer Geräteliste

Zum Verwalten und Bereitstellen von Geräten über Windows AutoPilot benötigen Sie eine CSV-Datei, die spezifische Informationen zu den Geräten enthält.
  
Die Spalten in der Gerätelistendatei müssen folgende Überschriften in der angegebenen Reihenfolge aufweisen:
  
- Spalte A: Seriennummer des Geräts

- Spalte B: Leer lassen

- Spalte C: Hardwarehash

Diese Informationen erhalten Sie von Ihrem Hardwareanbieter oder durch Verwendung des [PowerShell-Skripts Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), das eine CSV-Datei generiert. 

Wenn Sie Geräte hinzufügen, müssen Sie sie auch einem Profil hinzufügen. Ein Profil dient zum Anwenden von AutoPilot-Bereitstellungsprofilen zu einem Gerät oder einer Gerätegruppe.
  
## <a name="related-articles"></a>Verwandte Artikel

[Microsoft 365 Business-Dokumentation und -Ressourcen](../../business/index.yml)
  
[Erste Schritte mit Microsoft 365 Business](../../business/microsoft-365-business-overview.md)
  
[Verwalten von Microsoft 365 Business](../../business/manage.md)
