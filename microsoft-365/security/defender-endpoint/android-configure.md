---
title: Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Android konfiguriert wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, MDE, Android, Konfiguration
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
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841351"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="c19c8-104">Konfigurieren von Defender für Endpunkt unter Android-Features</span><span class="sxs-lookup"><span data-stu-id="c19c8-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c19c8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c19c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="c19c8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c19c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c19c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c19c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="c19c8-108">Bedingter Zugriff mit Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="c19c8-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="c19c8-109">Microsoft Defender für Endpunkt unter Android zusammen mit Microsoft Intune und Azure Active Directory ermöglicht das Erzwingen von Gerätekompatibilitäts- und Richtlinien für bedingten Zugriff basierend auf Geräterisikostufen.</span><span class="sxs-lookup"><span data-stu-id="c19c8-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="c19c8-110">Defender für Endpunkt ist eine MTD-Lösung (Mobile Threat Defense), die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c19c8-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="c19c8-111">Weitere Informationen zum Einrichten von Defender für Endpunkt unter Android und bedingtem Zugriff finden Sie unter [Defender für Endpunkt und Intune.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="c19c8-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="c19c8-112">Konfigurieren von benutzerdefinierten Indikatoren</span><span class="sxs-lookup"><span data-stu-id="c19c8-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="c19c8-113">Defender für Endpunkt unter Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.</span><span class="sxs-lookup"><span data-stu-id="c19c8-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="c19c8-114">Defender für Endpunkt unter Android ermöglicht Administratoren das Konfigurieren benutzerdefinierter Indikatoren zur Unterstützung von Android-Geräten.</span><span class="sxs-lookup"><span data-stu-id="c19c8-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="c19c8-115">Weitere Informationen zum Konfigurieren von benutzerdefinierten Indikatoren finden Sie unter [Verwalten von Indikatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="c19c8-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="c19c8-116">Konfigurieren des Webschutzes</span><span class="sxs-lookup"><span data-stu-id="c19c8-116">Configure web protection</span></span>
<span data-ttu-id="c19c8-117">Defender für Endpunkt unter Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures.</span><span class="sxs-lookup"><span data-stu-id="c19c8-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="c19c8-118">Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c19c8-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="c19c8-119">Defender für Endpunkt unter Android würde ein VPN verwenden, um das Webschutzfeature bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c19c8-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="c19c8-120">Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="c19c8-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="c19c8-121">Weitere Informationen finden Sie unter [Konfigurieren des Webschutzes auf Geräten mit Android.](/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="c19c8-121">For more information, see [Configure web protection on devices that run Android](/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c19c8-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c19c8-122">Related topics</span></span>
- [<span data-ttu-id="c19c8-123">Übersicht über Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="c19c8-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="c19c8-124">Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c19c8-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
