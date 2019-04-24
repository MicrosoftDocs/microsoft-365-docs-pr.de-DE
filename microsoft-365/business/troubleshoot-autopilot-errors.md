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
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="a82ca-103">Beheben von Problemen mit AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="a82ca-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="a82ca-104">Fehlermeldungen zu Gerätedateien</span><span class="sxs-lookup"><span data-stu-id="a82ca-104">Device file error messages</span></span>

<span data-ttu-id="a82ca-105">Hier finden Sie Informationen zu einigen der Fehler, die beim Arbeiten mit autoPilot-Gerätedateien in Microsoft 365 Business auftreten können.</span><span class="sxs-lookup"><span data-stu-id="a82ca-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="a82ca-106">**Fehlercode**</span><span class="sxs-lookup"><span data-stu-id="a82ca-106">**Error code**</span></span>|<span data-ttu-id="a82ca-107">**Korrektur Versuch**</span><span class="sxs-lookup"><span data-stu-id="a82ca-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a82ca-108">UnGültiger Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="a82ca-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="a82ca-109">Dieser Fehler sollte nur selten auftreten, wenn dieser Fehler angezeigt wird, versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="a82ca-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="a82ca-110">Hardware-Hashwert für ein Gerät ist nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="a82ca-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="a82ca-111">Wenn dieser Fehler angezeigt wird, ist der Wert, den Sie in der CSV-Datei für den Hardwarehash eines Geräts angegeben haben, nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="a82ca-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="a82ca-112">Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a82ca-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a82ca-113">Wenn Sie glauben, dass der Wert richtig ist, aber dieser Fehler weiterhin auftritt, Fragen Sie Ihren Hardwareanbieter nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="a82ca-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a82ca-114">Einem anderen Mandanten zugewiesenes Gerät</span><span class="sxs-lookup"><span data-stu-id="a82ca-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="a82ca-115">Wenn dieser Fehler angezeigt wird, ist der Wert, den Sie in der CSV-Datei für die Seriennummer oder den Product Key eines oder mehrerer Geräte angegeben haben, nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="a82ca-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="a82ca-116">Stellen Sie zunächst sicher, dass der Wert richtig eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a82ca-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a82ca-117">Wenn Sie glauben, dass der Wert richtig ist, aber dieser Fehler weiterhin auftritt, Fragen Sie Ihren Hardwareanbieter nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="a82ca-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a82ca-118">Die CSV-Datei enthält eine ungültige Seriennummer oder einen Produktschlüssel</span><span class="sxs-lookup"><span data-stu-id="a82ca-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="a82ca-119">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren tyring, bereits von einer anderen Organisation registriert ist.</span><span class="sxs-lookup"><span data-stu-id="a82ca-119">If you see this error it means that the device you are tyring to register is already registered by an other organization.</span></span> <span data-ttu-id="a82ca-120">Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="a82ca-120">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a82ca-121">Dieses Gerät wird für das Setup nicht mithilfe von autoPilot unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a82ca-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="a82ca-122">Dieser Fehler bedeutet, dass das Gerät die Bereitstellungsanforderungen für die autoPilot nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a82ca-122">This error means the device does not meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="a82ca-123">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a82ca-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="a82ca-124">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="a82ca-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="a82ca-125">Neue Geräte, die nicht auf der Windows-Willkommensseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a82ca-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="a82ca-126">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="a82ca-126">Device not found</span></span>  <br/> |<span data-ttu-id="a82ca-127">Dieser Fehler bedeutet, dass ein oder mehrere Geräte in Ihrer CSV-Datei nicht für Ihre Organisation registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a82ca-127">This error means that one or more devices in your CSV file is not registered to your organization.</span></span> <span data-ttu-id="a82ca-128">Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="a82ca-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
