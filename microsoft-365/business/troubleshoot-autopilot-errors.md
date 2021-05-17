---
title: Beheben von Problemen mit AutoPilot-Geräten
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Erfahren Sie, wie Sie Fehler beheben, die beim Arbeiten mit AutoPilot-Gerätedateien in der Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578085"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Beheben von Problemen mit AutoPilot-Geräten

## <a name="device-file-error-messages"></a>Fehlermeldungen zu Gerätedatei

Hier finden Sie Informationen zu einigen Fehlern, die beim Arbeiten mit AutoPilot-Gerätedateien in der Microsoft 365 Business Premium. 
  
|**Fehlercode**|**Zu versuchende Korrektur**|
|:-----|:-----|
|Ungültiger Anforderungstext  <br/> |Dieser Fehler sollte selten auftreten, wenn dieser Fehler angezeigt wird, versuchen Sie den Vorgang erneut.  <br/> |
|Der Hardwarehashwert für ein Gerät ist nicht korrekt.  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der wert, den Sie in Ihrer #A0 für den Hardwarehash eines Geräts angegeben haben, nicht richtig ist. Überprüfen Sie zunächst, ob der Wert richtig eingegeben wurde. Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie den Hardwareanbieter um Hilfe.  <br/> |
|Einem anderen Mandanten zugewiesenes Gerät  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in Ihrer CSV-Datei für die Seriennummer oder den Product Key eines oder mehrere Geräte angegeben haben, nicht richtig ist. Überprüfen Sie zunächst, ob der Wert richtig eingegeben wurde. Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie den Hardwareanbieter um Hilfe.  <br/> |
|Die CSV-Datei enthält eine ungültige Seriennummer oder einen ungültigen Product Key.  <br/> |Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren möchten, bereits von einer anderen Organisation registriert wurde. Um diesen Fehler zu beheben, bitten Sie den Hardwareanbieter um Hilfe.  <br/> |
|Dieses Gerät wird für das Setup mithilfe von AutoPilot nicht unterstützt.  <br/> | Dieser Fehler bedeutet, dass das Gerät die Anforderungen für die AutoPilot-Bereitstellung nicht erfüllt. Geräte müssen diese Anforderungen erfüllen:  <br/>  Windows 10, Version 1703 oder höher.  <br/>  Neue Geräte, die noch nicht über eine Windows erfahren haben.  <br/> |
|Gerät nicht gefunden  <br/> |Dieser Fehler bedeutet, dass mindestens ein Gerät in Ihrer CSV-Datei nicht in Ihrer Organisation registriert ist. Um dies zu beheben, bitten Sie ihren Hardwareanbieter um Hilfe.  <br/> |
