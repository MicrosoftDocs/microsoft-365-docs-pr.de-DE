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
ms.openlocfilehash: df43b797576525d7d2d9d60d4b101f1517cccf2e
ms.sourcegitcommit: 25fec94d85afcd4dca585fd6ebce5d364ebe41c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "25608130"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="a63a8-103">Beheben von Problemen mit AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="a63a8-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="a63a8-104">Gerät Datei Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="a63a8-104">Device file error messages</span></span>

<span data-ttu-id="a63a8-105">Hier Informationen über einige der Fehler möglicherweise beim Arbeiten mit AutoPilot Gerätedateien in Microsoft 365 Business angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a63a8-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="a63a8-106">**Fehlercode**</span><span class="sxs-lookup"><span data-stu-id="a63a8-106">**Error code**</span></span>|<span data-ttu-id="a63a8-107">**Beheben versuchen**</span><span class="sxs-lookup"><span data-stu-id="a63a8-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a63a8-108">Ungültige anforderungstextkörper</span><span class="sxs-lookup"><span data-stu-id="a63a8-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="a63a8-109">Dieser Fehler sollten nur selten, auftreten, wenn dieser Fehler angezeigt wird, wiederholen Sie den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="a63a8-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="a63a8-110">Hardware-Hashwert für ein Gerät ist nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="a63a8-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="a63a8-p101">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der angegebene Wert in der CSV-Datei für die Hardware-Hashwert von einem Gerät nicht korrekt ist. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie annehmen, dass der Wert korrekt ist, aber dieser Fehler weiterhin daran, erhalten Sie den Hardwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="a63a8-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a63a8-114">Gerät an einen anderen Mandanten zugewiesen</span><span class="sxs-lookup"><span data-stu-id="a63a8-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="a63a8-p102">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für die fortlaufende Zahl oder den Product Key ein oder mehrere Geräte bereitgestellt nicht korrekt ist. Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde. Wenn Sie annehmen, dass der Wert korrekt ist, aber dieser Fehler weiterhin daran, erhalten Sie den Hardwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="a63a8-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a63a8-118">Die CSV-Datei enthält eine ungültige Seriennummer oder Product key</span><span class="sxs-lookup"><span data-stu-id="a63a8-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="a63a8-p103">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren versuchten sind bereits von einem anderen Unternehmen registriert ist. Um dieses Problem zu beheben, erhalten Sie beim Hardwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="a63a8-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a63a8-121">Dieses Gerät ist nicht für das Setup unterstützt, mithilfe von AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a63a8-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="a63a8-p104">Dieser Fehler bedeutet, dass das Gerät nicht AutoPilot bereitstellungsanforderungen erfüllt. Geräte müssen Sie diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a63a8-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="a63a8-124">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="a63a8-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="a63a8-125">Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a63a8-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="a63a8-126">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="a63a8-126">Device not found</span></span>  <br/> |<span data-ttu-id="a63a8-p105">Dieser Fehler weist darauf hin, dass ein oder mehrere Geräte in Ihrer CSV-Datei ist nicht für Ihre Organisation registriert. Um dieses Problem zu beheben, erhalten Sie beim Hardwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="a63a8-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
