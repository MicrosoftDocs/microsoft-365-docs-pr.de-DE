---
title: Gerätezustände
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Erfahren Sie mehr über die verschiedenen Gerätezustände in der Liste Geräteaktionen in Admin home in Microsoft 365 Business.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578465"
---
# <a name="device-states"></a><span data-ttu-id="2121b-103">Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="2121b-103">Device states</span></span>

<span data-ttu-id="2121b-104">Dieser Artikel gilt für Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2121b-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="2121b-105">Geräte in der Liste **Geräteaktionen** (Startseite für Administratoren \> **Geräteaktionen**) können die folgenden Zustände haben.</span><span class="sxs-lookup"><span data-stu-id="2121b-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="2121b-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="2121b-107">**Status**</span></span>|<span data-ttu-id="2121b-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2121b-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2121b-109">Von Intune verwaltet</span><span class="sxs-lookup"><span data-stu-id="2121b-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="2121b-110">Verwaltet von Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2121b-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="2121b-111">Abkoppeln ausstehend</span><span class="sxs-lookup"><span data-stu-id="2121b-111">Retire pending</span></span>  <br/> |<span data-ttu-id="2121b-112">Microsoft 365 Business Premium bereiten sich darauf vor, Unternehmensdaten vom Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2121b-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2121b-113">Abkoppeln wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="2121b-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="2121b-114">Microsoft 365 Business Premium entfernt derzeit Unternehmensdaten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="2121b-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2121b-115">Fehler beim Abkoppeln</span><span class="sxs-lookup"><span data-stu-id="2121b-115">Retire failed</span></span>  <br/> | <span data-ttu-id="2121b-116">Beim Entfernen von Unternehmensdaten ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2121b-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="2121b-117">Zurückziehen abgebrochen</span><span class="sxs-lookup"><span data-stu-id="2121b-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="2121b-118">Die Aktion "Zurückziehen" wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2121b-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="2121b-119">Zurücksetzen steht aus</span><span class="sxs-lookup"><span data-stu-id="2121b-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="2121b-120">Es wird auf den Start des Zurücksetzens auf die Werkseinstellung gewartet.</span><span class="sxs-lookup"><span data-stu-id="2121b-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="2121b-121">Zurücksetzen wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="2121b-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="2121b-122">Das Zurücksetzen auf die Werkseinstellung ist erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2121b-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="2121b-123">Fehler beim Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="2121b-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="2121b-124">Die Werkszurücksetzung konnte nicht mehr hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2121b-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="2121b-125">Wipe canceled</span><span class="sxs-lookup"><span data-stu-id="2121b-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="2121b-126">Die Werkslöschung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2121b-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="2121b-127">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="2121b-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="2121b-128">Eine Aktion ist ausstehend (oder in Bearbeitung), aber das Gerät ist seit mehr als 30 Tagen nicht eingecheckt.</span><span class="sxs-lookup"><span data-stu-id="2121b-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="2121b-129">Löschen steht aus</span><span class="sxs-lookup"><span data-stu-id="2121b-129">Delete pending</span></span>  <br/> |<span data-ttu-id="2121b-130">Die Löschaktion steht aus.</span><span class="sxs-lookup"><span data-stu-id="2121b-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="2121b-131">Ermittelt</span><span class="sxs-lookup"><span data-stu-id="2121b-131">Discovered</span></span>  <br/> |<span data-ttu-id="2121b-132">Microsoft 365 Business Premium Das Gerät wurde erkannt.</span><span class="sxs-lookup"><span data-stu-id="2121b-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
