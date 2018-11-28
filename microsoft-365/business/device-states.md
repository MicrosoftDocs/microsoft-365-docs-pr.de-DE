---
title: Gerätezustände
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Informationen Sie zu Gerätestatus in Microsoft 365 Business.
ms.openlocfilehash: 50a79daf418749e4b73ba4b5ccb26991d120abbc
ms.sourcegitcommit: 25fec94d85afcd4dca585fd6ebce5d364ebe41c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "25607920"
---
# <a name="device-states"></a><span data-ttu-id="73b6c-103">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="73b6c-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="73b6c-104">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="73b6c-104">Device states</span></span>

<span data-ttu-id="73b6c-105">Geräte in der Liste **Geräteaktionen** (Startseite für Administratoren \> **Geräteaktionen**) können die folgenden Zustände haben.</span><span class="sxs-lookup"><span data-stu-id="73b6c-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="73b6c-107">**Zustand**</span><span class="sxs-lookup"><span data-stu-id="73b6c-107">**Status**</span></span>|<span data-ttu-id="73b6c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="73b6c-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73b6c-109">Von Intune verwaltet</span><span class="sxs-lookup"><span data-stu-id="73b6c-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="73b6c-110">Verwaltet von Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="73b6c-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="73b6c-111">Abkoppeln ausstehend</span><span class="sxs-lookup"><span data-stu-id="73b6c-111">Retire pending</span></span>  <br/> |<span data-ttu-id="73b6c-112">Microsoft 365 Business bereitet sich darauf vor, Unternehmensdaten vom Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="73b6c-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="73b6c-113">Abkoppeln wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="73b6c-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="73b6c-114">Microsoft 365 Business entfernt momentan Unternehmensdaten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="73b6c-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="73b6c-115">Fehler beim Abkoppeln</span><span class="sxs-lookup"><span data-stu-id="73b6c-115">Retire failed</span></span>  <br/> | <span data-ttu-id="73b6c-116">Beim Entfernen von Unternehmensdaten ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="73b6c-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="73b6c-117">Abkoppeln abgebrochen</span><span class="sxs-lookup"><span data-stu-id="73b6c-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="73b6c-118">Der Abkopplungsvorgang wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="73b6c-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="73b6c-119">Zurücksetzen steht aus</span><span class="sxs-lookup"><span data-stu-id="73b6c-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="73b6c-120">Es wird auf den Start des Zurücksetzens auf die Werkseinstellung gewartet.</span><span class="sxs-lookup"><span data-stu-id="73b6c-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="73b6c-121">Zurücksetzen wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="73b6c-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="73b6c-122">Das Zurücksetzen auf die Werkseinstellung ist erfolgt.</span><span class="sxs-lookup"><span data-stu-id="73b6c-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="73b6c-123">Fehler beim Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="73b6c-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="73b6c-124">Das Zurücksetzen auf die Werkseinstellung konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="73b6c-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="73b6c-125">Zurücksetzen abgebrochen</span><span class="sxs-lookup"><span data-stu-id="73b6c-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="73b6c-126">Das Zurücksetzen auf die Werkseinstellung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="73b6c-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="73b6c-127">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="73b6c-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="73b6c-128">Dies bedeutet, dass eine Aktion aussteht (oder im Gange ist), aber das Gerät seit mehr als 30 Tagen nicht eingecheckt wurde.</span><span class="sxs-lookup"><span data-stu-id="73b6c-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="73b6c-129">Löschen steht aus</span><span class="sxs-lookup"><span data-stu-id="73b6c-129">Delete pending</span></span>  <br/> |<span data-ttu-id="73b6c-130">Die Löschaktion steht aus.</span><span class="sxs-lookup"><span data-stu-id="73b6c-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="73b6c-131">Ermittelt</span><span class="sxs-lookup"><span data-stu-id="73b6c-131">Discovered</span></span>  <br/> |<span data-ttu-id="73b6c-132">Microsoft 365 Business hat das Gerät erkannt.</span><span class="sxs-lookup"><span data-stu-id="73b6c-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
