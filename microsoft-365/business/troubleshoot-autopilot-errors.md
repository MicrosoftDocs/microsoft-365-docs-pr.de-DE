---
title: Beheben von Problemen mit AutoPilot-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Hier erfahren Sie, wie Sie Fehler bei Autopiloten-Gerätedateien beheben.
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279836"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Beheben von Problemen mit AutoPilot-Geräten

## <a name="device-file-error-messages"></a>Fehlermeldungen zu Gerätedateien

Hier finden Sie Informationen zu einigen der Fehler, die beim Arbeiten mit autoPilot-Gerätedateien in Microsoft 365 Business auftreten können. 
  
|**Fehlercode**|**Korrektur Versuch**|
|:-----|:-----|
|UnGültiger Anforderungstext  <br/> |Dieser Fehler sollte nur selten auftreten, wenn dieser Fehler angezeigt wird, versuchen Sie es erneut.  <br/> |
|Hardware-Hashwert für ein Gerät ist nicht korrekt.  <br/> |Wenn dieser Fehler angezeigt wird, ist der Wert, den Sie in der CSV-Datei für den Hardwarehash eines Geräts angegeben haben, nicht richtig. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie glauben, dass der Wert richtig ist, aber dieser Fehler weiterhin auftritt, Fragen Sie Ihren Hardwareanbieter nach Hilfe.  <br/> |
|Einem anderen Mandanten zugewiesenes Gerät  <br/> |Wenn dieser Fehler angezeigt wird, ist der Wert, den Sie in der CSV-Datei für die Seriennummer oder den Product Key eines oder mehrerer Geräte angegeben haben, nicht richtig. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie glauben, dass der Wert richtig ist, aber dieser Fehler weiterhin auftritt, Fragen Sie Ihren Hardwareanbieter nach Hilfe.  <br/> |
|Die CSV-Datei enthält eine ungültige Seriennummer oder einen Produktschlüssel  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren tyring, bereits von einer anderen Organisation registriert ist. Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter nach Hilfe.  <br/> |
|Dieses Gerät wird für das Setup nicht mithilfe von autoPilot unterstützt.  <br/> | Dieser Fehler bedeutet, dass das Gerät die Bereitstellungsanforderungen für die autoPilot nicht erfüllt. Geräte müssen diese Anforderungen erfüllen:  <br/>  Windows 10, Version 1703 oder höher.  <br/>  Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.  <br/> |
|Gerät nicht gefunden  <br/> |Dieser Fehler bedeutet, dass ein oder mehrere Geräte in Ihrer CSV-Datei nicht für Ihre Organisation registriert sind. Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter nach Hilfe.  <br/> |
   
