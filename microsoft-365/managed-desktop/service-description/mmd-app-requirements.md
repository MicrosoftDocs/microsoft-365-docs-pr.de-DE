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
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="2a2c9-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a2c9-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="2a2c9-104">Microsoft Managed Desktop erfordert, dass wir Geräte mit einem bestimmten Ansatz verwalten, um die Leistung, Zuverlässigkeit und Servicefähigkeit von Geräten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="2a2c9-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="2a2c9-105">Verwaltungsbereich</span><span class="sxs-lookup"><span data-stu-id="2a2c9-105">Management area</span></span>  |<span data-ttu-id="2a2c9-106">Microsoft Managed Desktop-Ansatz</span><span class="sxs-lookup"><span data-stu-id="2a2c9-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="2a2c9-107">Gerätekonfiguration oder Richtlinienverwaltung</span><span class="sxs-lookup"><span data-stu-id="2a2c9-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="2a2c9-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2a2c9-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="2a2c9-109">Anwendungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="2a2c9-109">Application management</span></span>     | <span data-ttu-id="2a2c9-110">Microsoft InTune und Unternehmens Portal</span><span class="sxs-lookup"><span data-stu-id="2a2c9-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="2a2c9-111">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="2a2c9-111">Driver deployment</span></span>     |  <span data-ttu-id="2a2c9-112">Im Gerät enthaltene Treiber, Windows Update oder InTune</span><span class="sxs-lookup"><span data-stu-id="2a2c9-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="2a2c9-113">Gerätesicherheit</span><span class="sxs-lookup"><span data-stu-id="2a2c9-113">Device security</span></span>     | <span data-ttu-id="2a2c9-114">Siehe [Gerätesicherheit](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="2a2c9-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="2a2c9-115">Identitäts- und Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="2a2c9-115">Identity and access management</span></span>     | <span data-ttu-id="2a2c9-116">Siehe [Identitäts-und Zugriffsverwaltung](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="2a2c9-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="2a2c9-117">Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="2a2c9-117">Network security</span></span>     | <span data-ttu-id="2a2c9-118">Siehe [Netzwerksicherheit](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="2a2c9-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="2a2c9-119">Informationssicherheit</span><span class="sxs-lookup"><span data-stu-id="2a2c9-119">Information security</span></span>     |  <span data-ttu-id="2a2c9-120">Siehe [Informationssicherheit](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="2a2c9-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="2a2c9-121">Datenwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="2a2c9-121">Data recovery</span></span>     | <span data-ttu-id="2a2c9-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2a2c9-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="2a2c9-123">Kern Produktivität</span><span class="sxs-lookup"><span data-stu-id="2a2c9-123">Core productivity</span></span>     | <span data-ttu-id="2a2c9-124">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="2a2c9-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="2a2c9-125">Browser</span><span class="sxs-lookup"><span data-stu-id="2a2c9-125">Browser</span></span>     | <span data-ttu-id="2a2c9-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2c9-126">Microsoft Edge</span></span>        |




<span data-ttu-id="2a2c9-127">Microsoft Managed Desktop überwacht möglicherweise andere auf verwalteten Geräten ausgeführten Software.</span><span class="sxs-lookup"><span data-stu-id="2a2c9-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="2a2c9-128">Wenn sich dies negativ auf Geräteverwaltung, Gerätesicherheit, Leistung oder Zuverlässigkeit auswirkt, müssen Sie möglicherweise eine [Ausnahme vom Dienstplan](customizing.md)anfordern.</span><span class="sxs-lookup"><span data-stu-id="2a2c9-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
