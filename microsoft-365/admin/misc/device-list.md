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

[Microsoft 365 Business-Dokumentation und -Ressourcen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Erste Schritte mit Microsoft 365 Business](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[Verwalten von Microsoft 365 Business](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
