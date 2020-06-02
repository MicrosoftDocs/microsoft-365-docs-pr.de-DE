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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Erfahren Sie mehr über die verschiedenen Gerätezustände in der Liste Geräteaktionen in admin Home in Microsoft 365 for Business.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471177"
---
# <a name="device-states"></a><span data-ttu-id="00581-103">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="00581-103">Device states</span></span>

<span data-ttu-id="00581-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="00581-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="00581-105">Geräte in der Liste **Geräteaktionen** (Startseite für Administratoren \> **Geräteaktionen**) können die folgenden Zustände haben.</span><span class="sxs-lookup"><span data-stu-id="00581-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="00581-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="00581-107">**Status**</span></span>|<span data-ttu-id="00581-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="00581-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00581-109">Von Intune verwaltet</span><span class="sxs-lookup"><span data-stu-id="00581-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="00581-110">Verwaltet von Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="00581-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="00581-111">Abkoppeln ausstehend</span><span class="sxs-lookup"><span data-stu-id="00581-111">Retire pending</span></span>  <br/> |<span data-ttu-id="00581-112">Microsoft 365 Business Premium ist immer für die Entfernung von Unternehmensdaten aus dem Gerät gerüstet.</span><span class="sxs-lookup"><span data-stu-id="00581-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="00581-113">Abkoppeln wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="00581-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="00581-114">Microsoft 365 Business Premium entfernt derzeit Unternehmensdaten aus dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="00581-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="00581-115">Fehler beim Abkoppeln</span><span class="sxs-lookup"><span data-stu-id="00581-115">Retire failed</span></span>  <br/> | <span data-ttu-id="00581-116">Beim Entfernen von Unternehmensdaten ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="00581-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="00581-117">Zurückziehen abgebrochen</span><span class="sxs-lookup"><span data-stu-id="00581-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="00581-118">Die zurückzieh-Aktion wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="00581-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="00581-119">Zurücksetzen steht aus</span><span class="sxs-lookup"><span data-stu-id="00581-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="00581-120">Es wird auf den Start des Zurücksetzens auf die Werkseinstellung gewartet.</span><span class="sxs-lookup"><span data-stu-id="00581-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="00581-121">Zurücksetzen wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="00581-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="00581-122">Das Zurücksetzen auf die Werkseinstellung ist erfolgt.</span><span class="sxs-lookup"><span data-stu-id="00581-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="00581-123">Fehler beim Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="00581-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="00581-124">Factory-Reset konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00581-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="00581-125">Löschvorgang abgebrochen</span><span class="sxs-lookup"><span data-stu-id="00581-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="00581-126">Factory Wipe wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="00581-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="00581-127">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="00581-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="00581-128">Eine Aktion ist ausstehend (oder wird ausgeführt), aber das Gerät wurde für 30 Tage nicht eingecheckt.</span><span class="sxs-lookup"><span data-stu-id="00581-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="00581-129">Löschen steht aus</span><span class="sxs-lookup"><span data-stu-id="00581-129">Delete pending</span></span>  <br/> |<span data-ttu-id="00581-130">Die Löschaktion steht aus.</span><span class="sxs-lookup"><span data-stu-id="00581-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="00581-131">Ermittelt</span><span class="sxs-lookup"><span data-stu-id="00581-131">Discovered</span></span>  <br/> |<span data-ttu-id="00581-132">Microsoft 365 Business Premium hat das Gerät erkannt.</span><span class="sxs-lookup"><span data-stu-id="00581-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
