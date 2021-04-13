---
title: Konfigurieren von Microsoft Defender for Endpoint unter Android-Features
description: Beschreibt das Konfigurieren von Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, atp, mde, android, configuration
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
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688033"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="529fb-104">Konfigurieren von Defender for Endpoint für Android-Features</span><span class="sxs-lookup"><span data-stu-id="529fb-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="529fb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="529fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="529fb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="529fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="529fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="529fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="529fb-108">Bedingter Zugriff mit Defender for Endpoint für Android</span><span class="sxs-lookup"><span data-stu-id="529fb-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="529fb-109">Microsoft Defender für Endpoint unter Android ermöglicht zusammen mit Microsoft Intune und Azure Active Directory die Erzwingung der Gerätekonformität und Richtlinien für bedingten Zugriff auf der Grundlage von Geräterisikostufen.</span><span class="sxs-lookup"><span data-stu-id="529fb-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="529fb-110">Defender for Endpoint ist eine Mobile Threat Defense (MTD)-Lösung, die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="529fb-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="529fb-111">Weitere Informationen zum Einrichten von Defender for Endpoint für Android und bedingten Zugriff finden Sie unter [Defender for Endpoint und Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="529fb-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="529fb-112">Konfigurieren benutzerdefinierter Indikatoren</span><span class="sxs-lookup"><span data-stu-id="529fb-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="529fb-113">Defender for Endpoint für Android unterstützt nur das Erstellen benutzerdefinierter Indikatoren für IP-Adressen und URLs/Domänen.</span><span class="sxs-lookup"><span data-stu-id="529fb-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="529fb-114">Mit Defender for Endpoint für Android können Administratoren benutzerdefinierte Indikatoren konfigurieren, um auch Android-Geräte zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="529fb-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="529fb-115">Weitere Informationen zum Konfigurieren benutzerdefinierter Indikatoren finden Sie unter [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="529fb-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="529fb-116">Konfigurieren des Webschutzes</span><span class="sxs-lookup"><span data-stu-id="529fb-116">Configure web protection</span></span>
<span data-ttu-id="529fb-117">Defender for Endpoint für Android ermöglicht IT-Administratoren die Konfiguration des Webschutzfeatures.</span><span class="sxs-lookup"><span data-stu-id="529fb-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="529fb-118">Diese Funktion ist im Microsoft Endpoint Manager Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="529fb-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="529fb-119">Defender für Endpoint für Android würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="529fb-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="529fb-120">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="529fb-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="529fb-121">Weitere Informationen finden Sie unter [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span><span class="sxs-lookup"><span data-stu-id="529fb-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="529fb-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="529fb-122">Related topics</span></span>
- [<span data-ttu-id="529fb-123">Übersicht über Microsoft Defender for Endpoint unter Android</span><span class="sxs-lookup"><span data-stu-id="529fb-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="529fb-124">Bereitstellen von Microsoft Defender for Endpoint unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="529fb-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
