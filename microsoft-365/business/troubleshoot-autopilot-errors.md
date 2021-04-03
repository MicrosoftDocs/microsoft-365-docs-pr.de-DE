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
description: Erfahren Sie, wie Sie Fehler beheben, die beim Arbeiten mit AutoPilot-Gerätedateien in Microsoft 365 Business Premium möglicherweise angezeigt werden.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578085"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="9cab7-103">Beheben von Problemen mit AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="9cab7-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="9cab7-104">Fehlermeldungen zu Gerätedatei</span><span class="sxs-lookup"><span data-stu-id="9cab7-104">Device file error messages</span></span>

<span data-ttu-id="9cab7-105">Hier finden Sie Informationen zu einigen Fehlern, die beim Arbeiten mit AutoPilot-Gerätedateien in Microsoft 365 Business Premium auftreten können.</span><span class="sxs-lookup"><span data-stu-id="9cab7-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="9cab7-106">**Fehlercode**</span><span class="sxs-lookup"><span data-stu-id="9cab7-106">**Error code**</span></span>|<span data-ttu-id="9cab7-107">**Zu versuchende Korrektur**</span><span class="sxs-lookup"><span data-stu-id="9cab7-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9cab7-108">Ungültiger Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="9cab7-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="9cab7-109">Dieser Fehler sollte selten auftreten, wenn dieser Fehler angezeigt wird, versuchen Sie den Vorgang erneut.</span><span class="sxs-lookup"><span data-stu-id="9cab7-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="9cab7-110">Der Hardwarehashwert für ein Gerät ist nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="9cab7-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="9cab7-111">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der wert, den Sie in Ihrer #A0 für den Hardwarehash eines Geräts angegeben haben, nicht richtig ist.</span><span class="sxs-lookup"><span data-stu-id="9cab7-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="9cab7-112">Überprüfen Sie zunächst, ob der Wert richtig eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9cab7-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="9cab7-113">Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie den Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="9cab7-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="9cab7-114">Einem anderen Mandanten zugewiesenes Gerät</span><span class="sxs-lookup"><span data-stu-id="9cab7-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="9cab7-115">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in Ihrer CSV-Datei für die Seriennummer oder den Product Key eines oder mehrere Geräte angegeben haben, nicht richtig ist.</span><span class="sxs-lookup"><span data-stu-id="9cab7-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="9cab7-116">Überprüfen Sie zunächst, ob der Wert richtig eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9cab7-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="9cab7-117">Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie den Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="9cab7-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="9cab7-118">Die CSV-Datei enthält eine ungültige Seriennummer oder einen ungültigen Product Key.</span><span class="sxs-lookup"><span data-stu-id="9cab7-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="9cab7-119">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren möchten, bereits von einer anderen Organisation registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="9cab7-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="9cab7-120">Um diesen Fehler zu beheben, bitten Sie den Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="9cab7-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="9cab7-121">Dieses Gerät wird für das Setup mithilfe von AutoPilot nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9cab7-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="9cab7-122">Dieser Fehler bedeutet, dass das Gerät die Anforderungen für die AutoPilot-Bereitstellung nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="9cab7-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="9cab7-123">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9cab7-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="9cab7-124">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="9cab7-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="9cab7-125">Neue Geräte, die windows-out-of-box-Erfahrung noch nicht erlebt haben.</span><span class="sxs-lookup"><span data-stu-id="9cab7-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="9cab7-126">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="9cab7-126">Device not found</span></span>  <br/> |<span data-ttu-id="9cab7-127">Dieser Fehler bedeutet, dass mindestens ein Gerät in Ihrer CSV-Datei nicht in Ihrer Organisation registriert ist.</span><span class="sxs-lookup"><span data-stu-id="9cab7-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="9cab7-128">Um dies zu beheben, bitten Sie ihren Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="9cab7-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
