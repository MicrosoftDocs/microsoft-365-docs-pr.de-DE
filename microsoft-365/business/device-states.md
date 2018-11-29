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
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867787"
---
# <a name="device-states"></a><span data-ttu-id="bf0f1-103">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="bf0f1-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="bf0f1-104">Gerätezustände</span><span class="sxs-lookup"><span data-stu-id="bf0f1-104">Device states</span></span>

<span data-ttu-id="bf0f1-105">Geräte in der Liste **Geräteaktionen** (Startseite für Administratoren \> **Geräteaktionen**) können die folgenden Zustände haben.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="bf0f1-107">**Zustand**</span><span class="sxs-lookup"><span data-stu-id="bf0f1-107">**Status**</span></span>|<span data-ttu-id="bf0f1-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf0f1-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf0f1-109">Von Intune verwaltet</span><span class="sxs-lookup"><span data-stu-id="bf0f1-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="bf0f1-110">Verwaltet von Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-111">Abkoppeln ausstehend</span><span class="sxs-lookup"><span data-stu-id="bf0f1-111">Retire pending</span></span>  <br/> |<span data-ttu-id="bf0f1-112">Microsoft 365 Business bereitet sich darauf vor, Unternehmensdaten vom Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-113">Abkoppeln wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="bf0f1-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="bf0f1-114">Microsoft 365 Business entfernt momentan Unternehmensdaten vom Gerät.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-115">Fehler beim Abkoppeln</span><span class="sxs-lookup"><span data-stu-id="bf0f1-115">Retire failed</span></span>  <br/> | <span data-ttu-id="bf0f1-116">Beim Entfernen von Unternehmensdaten ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-117">Abkoppeln abgebrochen</span><span class="sxs-lookup"><span data-stu-id="bf0f1-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="bf0f1-118">Der Abkopplungsvorgang wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-119">Zurücksetzen steht aus</span><span class="sxs-lookup"><span data-stu-id="bf0f1-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="bf0f1-120">Es wird auf den Start des Zurücksetzens auf die Werkseinstellung gewartet.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-121">Zurücksetzen wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="bf0f1-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="bf0f1-122">Das Zurücksetzen auf die Werkseinstellung ist erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-123">Fehler beim Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="bf0f1-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="bf0f1-124">Das Zurücksetzen auf die Werkseinstellung konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-125">Zurücksetzen abgebrochen</span><span class="sxs-lookup"><span data-stu-id="bf0f1-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="bf0f1-126">Das Zurücksetzen auf die Werkseinstellung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-127">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="bf0f1-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="bf0f1-128">Dies bedeutet, dass eine Aktion aussteht (oder im Gange ist), aber das Gerät seit mehr als 30 Tagen nicht eingecheckt wurde.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-129">Löschen steht aus</span><span class="sxs-lookup"><span data-stu-id="bf0f1-129">Delete pending</span></span>  <br/> |<span data-ttu-id="bf0f1-130">Die Löschaktion steht aus.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="bf0f1-131">Ermittelt</span><span class="sxs-lookup"><span data-stu-id="bf0f1-131">Discovered</span></span>  <br/> |<span data-ttu-id="bf0f1-132">Microsoft 365 Business hat das Gerät erkannt.</span><span class="sxs-lookup"><span data-stu-id="bf0f1-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
