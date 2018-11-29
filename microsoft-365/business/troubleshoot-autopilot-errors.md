---
title: Problembehandlung bei AutoPilot-Gerätfehlern
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Hier erfahren Sie, wie AutoPilot Gerät Dateifehler behoben.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867739"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Problembehandlung bei AutoPilot-Gerätfehlern

## <a name="device-file-error-messages"></a>Gerät Datei Fehlermeldungen

Hier Informationen über einige der Fehler möglicherweise beim Arbeiten mit AutoPilot Gerätedateien in Microsoft 365 Business angezeigt. 
  
|**Fehlercode**|**Beheben versuchen**|
|:-----|:-----|
|Ungültige anforderungstextkörper  <br/> |Dieser Fehler sollten nur selten, auftreten, wenn dieser Fehler angezeigt wird, wiederholen Sie den Vorgang.  <br/> |
|Hardware-Hashwert für ein Gerät ist nicht korrekt.  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der angegebene Wert in der CSV-Datei für die Hardware-Hashwert von einem Gerät nicht korrekt ist. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie annehmen, dass der Wert korrekt ist, aber dieser Fehler weiterhin daran, erhalten Sie den Hardwarehersteller.  <br/> |
|Gerät an einen anderen Mandanten zugewiesen  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für die fortlaufende Zahl oder den Product Key ein oder mehrere Geräte bereitgestellt nicht korrekt ist. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie annehmen, dass der Wert korrekt ist, aber dieser Fehler weiterhin daran, erhalten Sie den Hardwarehersteller.  <br/> |
|Die CSV-Datei enthält eine ungültige Seriennummer oder Product key  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren versuchten sind bereits von einem anderen Unternehmen registriert ist. Um dieses Problem zu beheben, erhalten Sie beim Hardwarehersteller.  <br/> |
|Dieses Gerät ist nicht für das Setup unterstützt, mithilfe von AutoPilot  <br/> | Dieser Fehler bedeutet, dass das Gerät nicht AutoPilot bereitstellungsanforderungen erfüllt. Geräte müssen Sie diese Anforderungen erfüllen:  <br/>  Windows 10, Version 1703 oder höher.  <br/>  Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.  <br/> |
|Gerät nicht gefunden  <br/> |Dieser Fehler weist darauf hin, dass ein oder mehrere Geräte in Ihrer CSV-Datei ist nicht für Ihre Organisation registriert. Um dieses Problem zu beheben, erhalten Sie beim Hardwarehersteller.  <br/> |
   
