---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659714"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="73fc5-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73fc5-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="73fc5-104">Microsoft Managed Desktop erfordert, dass wir Geräte mithilfe eines bestimmten Ansatzes verwalten, um die Leistung, Zuverlässigkeit und Dienstbarkeit von Geräten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="73fc5-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="73fc5-105">Verwaltungsbereich</span><span class="sxs-lookup"><span data-stu-id="73fc5-105">Management area</span></span>  |<span data-ttu-id="73fc5-106">Microsoft Managed Desktop-Ansatz</span><span class="sxs-lookup"><span data-stu-id="73fc5-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="73fc5-107">Gerätekonfiguration oder Richtlinienverwaltung</span><span class="sxs-lookup"><span data-stu-id="73fc5-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="73fc5-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="73fc5-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="73fc5-109">Anwendungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="73fc5-109">Application management</span></span>     | <span data-ttu-id="73fc5-110">Microsoft Intune und Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="73fc5-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="73fc5-111">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="73fc5-111">Driver deployment</span></span>     |  <span data-ttu-id="73fc5-112">Treiber, die im Gerät, Windows Update oder Intune enthalten sind</span><span class="sxs-lookup"><span data-stu-id="73fc5-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="73fc5-113">Gerätesicherheit</span><span class="sxs-lookup"><span data-stu-id="73fc5-113">Device security</span></span>     | <span data-ttu-id="73fc5-114">Siehe [Gerätesicherheit](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="73fc5-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="73fc5-115">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="73fc5-115">Identity and access management</span></span>     | <span data-ttu-id="73fc5-116">Siehe [Identitäts- und Zugriffsverwaltung](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="73fc5-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="73fc5-117">Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="73fc5-117">Network security</span></span>     | <span data-ttu-id="73fc5-118">Siehe [Netzwerksicherheit](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="73fc5-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="73fc5-119">Informationssicherheit</span><span class="sxs-lookup"><span data-stu-id="73fc5-119">Information security</span></span>     |  <span data-ttu-id="73fc5-120">Siehe [Informationssicherheit](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="73fc5-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="73fc5-121">Datenwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="73fc5-121">Data recovery</span></span>     | <span data-ttu-id="73fc5-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="73fc5-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="73fc5-123">Kernproduktivität</span><span class="sxs-lookup"><span data-stu-id="73fc5-123">Core productivity</span></span>     | <span data-ttu-id="73fc5-124">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="73fc5-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="73fc5-125">Browser</span><span class="sxs-lookup"><span data-stu-id="73fc5-125">Browser</span></span>     | <span data-ttu-id="73fc5-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="73fc5-126">Microsoft Edge</span></span>        |




<span data-ttu-id="73fc5-127">Microsoft Managed Desktop überwacht möglicherweise andere Software, die auf verwalteten Geräten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73fc5-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="73fc5-128">Wenn sich dies negativ auf die Geräteverwaltung, Gerätesicherheit, Leistung oder Zuverlässigkeit auswirken sollte, müssen Sie möglicherweise eine Ausnahme vom [Dienstplan anfordern.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="73fc5-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
