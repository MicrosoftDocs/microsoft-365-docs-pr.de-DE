---
title: Gerätezustände
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Erfahren Sie mehr über die verschiedenen Gerätezustände in der Liste Geräteaktionen in admin Home in Microsoft 365 Business.
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560818"
---
# <a name="device-states"></a><span data-ttu-id="5c63b-103">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="5c63b-103">Device states</span></span>

<span data-ttu-id="5c63b-104">Geräte in der Liste **Geräteaktionen** (Startseite für Administratoren \> **Geräteaktionen**) können die folgenden Zustände haben.</span><span class="sxs-lookup"><span data-stu-id="5c63b-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="5c63b-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="5c63b-106">**Status**</span></span>|<span data-ttu-id="5c63b-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5c63b-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c63b-108">Von Intune verwaltet</span><span class="sxs-lookup"><span data-stu-id="5c63b-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="5c63b-109">Verwaltet von Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5c63b-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="5c63b-110">Abkoppeln ausstehend</span><span class="sxs-lookup"><span data-stu-id="5c63b-110">Retire pending</span></span>  <br/> |<span data-ttu-id="5c63b-111">Microsoft 365 Business bereitet sich darauf vor, Unternehmensdaten vom Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5c63b-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="5c63b-112">Abkoppeln wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5c63b-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="5c63b-113">Microsoft 365 Business entfernt momentan Unternehmensdaten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="5c63b-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="5c63b-114">Fehler beim Abkoppeln</span><span class="sxs-lookup"><span data-stu-id="5c63b-114">Retire failed</span></span>  <br/> | <span data-ttu-id="5c63b-115">Beim Entfernen von Unternehmensdaten ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5c63b-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="5c63b-116">Zurückziehen abgebrochen</span><span class="sxs-lookup"><span data-stu-id="5c63b-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="5c63b-117">Die zurückzieh-Aktion wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5c63b-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="5c63b-118">Zurücksetzen steht aus</span><span class="sxs-lookup"><span data-stu-id="5c63b-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="5c63b-119">Es wird auf den Start des Zurücksetzens auf die Werkseinstellung gewartet.</span><span class="sxs-lookup"><span data-stu-id="5c63b-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="5c63b-120">Zurücksetzen wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5c63b-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="5c63b-121">Das Zurücksetzen auf die Werkseinstellung ist erfolgt.</span><span class="sxs-lookup"><span data-stu-id="5c63b-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="5c63b-122">Fehler beim Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="5c63b-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="5c63b-123">Factory-Reset konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5c63b-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="5c63b-124">Löschvorgang abgebrochen</span><span class="sxs-lookup"><span data-stu-id="5c63b-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="5c63b-125">Factory Wipe wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="5c63b-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="5c63b-126">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="5c63b-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="5c63b-127">Eine Aktion ist ausstehend (oder wird ausgeführt), aber das Gerät wurde für 30 Tage nicht eingecheckt.</span><span class="sxs-lookup"><span data-stu-id="5c63b-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="5c63b-128">Löschen steht aus</span><span class="sxs-lookup"><span data-stu-id="5c63b-128">Delete pending</span></span>  <br/> |<span data-ttu-id="5c63b-129">Die Löschaktion steht aus.</span><span class="sxs-lookup"><span data-stu-id="5c63b-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="5c63b-130">Ermittelt</span><span class="sxs-lookup"><span data-stu-id="5c63b-130">Discovered</span></span>  <br/> |<span data-ttu-id="5c63b-131">Microsoft 365 Business hat das Gerät erkannt.</span><span class="sxs-lookup"><span data-stu-id="5c63b-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
