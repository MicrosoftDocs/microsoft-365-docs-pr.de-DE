---
title: CSV-Datei einer Geräteliste
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579218"
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
