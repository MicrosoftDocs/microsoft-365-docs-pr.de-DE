---
title: Beheben von Problemen mit AutoPilot-Geräten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
description: Hier erfahren Sie, wie Sie Fehler bei Autopilot-Gerätedateien beheben.
ms.openlocfilehash: 88b59ec20ddda401c1dac45ff729ac38497a767e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074358"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Beheben von Problemen mit AutoPilot-Geräten

## <a name="device-file-error-messages"></a>Fehlermeldungen bei Gerätedateien

Hier finden Sie Informationen zu einigen der Fehler, die beim Arbeiten mit Autopilot-Gerätedateien in Microsoft 365 Business auftreten können. 
  
|**Fehlercode**|**Beheben Sie, um zu versuchen**|
|:-----|:-----|
|Ungültiger Anforderungstext  <br/> |Dieser Fehler sollte selten auftreten, wenn dieser Fehler auftritt, führen Sie den Vorgang erneut aus.  <br/> |
|Der Hardware Hash Wert für ein Gerät ist nicht richtig.  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für den Hardwarehash eines Geräts angegeben haben, nicht korrekt ist. Überprüfen Sie zunächst, ob der Wert ordnungsgemäß eingegeben wurde. Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie Ihren Hardwareanbieter um Hilfe.  <br/> |
|Einem anderen Mandanten zugewiesenes Gerät  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für die Seriennummer oder den Product Key eines oder mehrerer Geräte angegeben haben, nicht korrekt ist. Überprüfen Sie zunächst, ob der Wert ordnungsgemäß eingegeben wurde. Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie Ihren Hardwareanbieter um Hilfe.  <br/> |
|Die CSV-Datei enthält eine ungültige Seriennummer oder einen Produktschlüssel.  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das zu Registrier tyring Gerät bereits von einer anderen Organisation registriert ist. Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter um Hilfe.  <br/> |
|Dieses Gerät wird für das Setup nicht mithilfe von Autopilot unterstützt.  <br/> | Dieser Fehler bedeutet, dass das Gerät keine Autopilot-Bereitstellungsanforderungen erfüllt. Geräte müssen diese Anforderungen erfüllen:  <br/>  Windows 10, Version 1703 oder höher.  <br/>  Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.  <br/> |
|Gerät nicht gefunden  <br/> |Dieser Fehler bedeutet, dass ein oder mehrere Geräte in Ihrer CSV-Datei nicht in Ihrer Organisation registriert sind. Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter um Hilfe.  <br/> |
   
