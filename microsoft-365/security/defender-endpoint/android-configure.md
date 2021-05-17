---
title: Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android
description: Beschreibt das Konfigurieren von Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935317"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="d42d7-104">Konfigurieren von Defender for Endpoint unter Android-Features</span><span class="sxs-lookup"><span data-stu-id="d42d7-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d42d7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d42d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="d42d7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d42d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d42d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d42d7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="d42d7-108">Bedingter Zugriff mit Defender for Endpoint unter Android</span><span class="sxs-lookup"><span data-stu-id="d42d7-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="d42d7-109">Microsoft Defender for Endpoint unter Android ermöglicht Microsoft Intune und Azure Active Directory die Erzwingung von Gerätekonformität und Richtlinien für bedingten Zugriff basierend auf Geräterisikostufen.</span><span class="sxs-lookup"><span data-stu-id="d42d7-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="d42d7-110">Defender for Endpoint ist eine Mobile Threat Defense (MTD)-Lösung, die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="d42d7-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="d42d7-111">Weitere Informationen zum Einrichten von Defender for Endpoint unter Android und bedingten Zugriff finden Sie unter [Defender for Endpoint und Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="d42d7-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="d42d7-112">Konfigurieren benutzerdefinierter Indikatoren</span><span class="sxs-lookup"><span data-stu-id="d42d7-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="d42d7-113">Defender for Endpoint unter Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.</span><span class="sxs-lookup"><span data-stu-id="d42d7-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="d42d7-114">Defender for Endpoint unter Android ermöglicht Administratoren die Konfiguration benutzerdefinierter Indikatoren zur Unterstützung von Android-Geräten.</span><span class="sxs-lookup"><span data-stu-id="d42d7-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="d42d7-115">Weitere Informationen zum Konfigurieren benutzerdefinierter Indikatoren finden Sie unter [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="d42d7-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="d42d7-116">Konfigurieren des Webschutzes</span><span class="sxs-lookup"><span data-stu-id="d42d7-116">Configure web protection</span></span>
<span data-ttu-id="d42d7-117">Defender für Endpoint unter Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures.</span><span class="sxs-lookup"><span data-stu-id="d42d7-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="d42d7-118">Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d42d7-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="d42d7-119">Defender für Endpoint unter Android würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="d42d7-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="d42d7-120">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="d42d7-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="d42d7-121">Weitere Informationen finden Sie unter [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span><span class="sxs-lookup"><span data-stu-id="d42d7-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d42d7-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d42d7-122">Related topics</span></span>
- [<span data-ttu-id="d42d7-123">Übersicht über Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="d42d7-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="d42d7-124">Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d42d7-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
