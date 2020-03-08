---
title: Beheben von Problemen mit AutoPilot-Geräten
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Hier erfahren Sie, wie Sie Fehler beheben können, die beim Arbeiten mit Autopilot-Gerätedateien in Microsoft 365 Business angezeigt werden.
ms.openlocfilehash: dc1abd508156c8525859f6ca7e291ab38fc8859c
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560698"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="34ff3-103">Beheben von Problemen mit AutoPilot-Geräten</span><span class="sxs-lookup"><span data-stu-id="34ff3-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="34ff3-104">Fehlermeldungen bei Gerätedateien</span><span class="sxs-lookup"><span data-stu-id="34ff3-104">Device file error messages</span></span>

<span data-ttu-id="34ff3-105">Hier finden Sie Informationen zu einigen der Fehler, die beim Arbeiten mit Autopilot-Gerätedateien in Microsoft 365 Business auftreten können.</span><span class="sxs-lookup"><span data-stu-id="34ff3-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="34ff3-106">**Fehlercode**</span><span class="sxs-lookup"><span data-stu-id="34ff3-106">**Error code**</span></span>|<span data-ttu-id="34ff3-107">**Beheben Sie, um zu versuchen**</span><span class="sxs-lookup"><span data-stu-id="34ff3-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34ff3-108">Ungültiger Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="34ff3-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="34ff3-109">Dieser Fehler sollte selten auftreten, wenn dieser Fehler auftritt, führen Sie den Vorgang erneut aus.</span><span class="sxs-lookup"><span data-stu-id="34ff3-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="34ff3-110">Der Hardware Hash Wert für ein Gerät ist nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="34ff3-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="34ff3-111">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für den Hardwarehash eines Geräts angegeben haben, nicht korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="34ff3-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="34ff3-112">Überprüfen Sie zunächst, ob der Wert ordnungsgemäß eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="34ff3-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="34ff3-113">Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie Ihren Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="34ff3-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="34ff3-114">Einem anderen Mandanten zugewiesenes Gerät</span><span class="sxs-lookup"><span data-stu-id="34ff3-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="34ff3-115">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass der Wert, den Sie in der CSV-Datei für die Seriennummer oder den Product Key eines oder mehrerer Geräte angegeben haben, nicht korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="34ff3-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="34ff3-116">Überprüfen Sie zunächst, ob der Wert ordnungsgemäß eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="34ff3-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="34ff3-117">Wenn Sie der Meinung sind, dass der Wert richtig ist, dieser Fehler jedoch weiterhin auftritt, bitten Sie Ihren Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="34ff3-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="34ff3-118">Die CSV-Datei enthält eine ungültige Seriennummer oder einen Produktschlüssel.</span><span class="sxs-lookup"><span data-stu-id="34ff3-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="34ff3-119">Wenn dieser Fehler angezeigt wird, bedeutet dies, dass das Gerät, das Sie registrieren möchten, bereits von einer anderen Organisation registriert ist.</span><span class="sxs-lookup"><span data-stu-id="34ff3-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="34ff3-120">Um diesen Fehler zu beheben, Fragen Sie Ihren Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="34ff3-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="34ff3-121">Dieses Gerät wird für das Setup nicht mithilfe von Autopilot unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34ff3-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="34ff3-122">Dieser Fehler bedeutet, dass das Gerät keine Autopilot-Bereitstellungsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="34ff3-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="34ff3-123">Geräte müssen diese Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="34ff3-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="34ff3-124">Windows 10, Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="34ff3-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="34ff3-125">Neue Geräte, die eine Out-of-Box-Erfahrung mit Windows nicht durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="34ff3-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="34ff3-126">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="34ff3-126">Device not found</span></span>  <br/> |<span data-ttu-id="34ff3-127">Dieser Fehler bedeutet, dass ein oder mehrere Geräte in Ihrer CSV-Datei nicht in Ihrer Organisation registriert sind.</span><span class="sxs-lookup"><span data-stu-id="34ff3-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="34ff3-128">Um dies zu beheben, Fragen Sie Ihren Hardwareanbieter um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="34ff3-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
