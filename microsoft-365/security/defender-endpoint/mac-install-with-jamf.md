---
title: Bereitstellen von Microsoft Defender für Endpunkt unter macOS mit Jamf Pro
description: Bereitstellen von Microsoft Defender für Endpunkt unter macOS mit Jamf Pro
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Installation, bereitstellen, Deinstallation, Intune, jamfpro, macos, aus, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b41c5ec827e110e0101c50ce7babeb6442096edb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842890"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="6187f-104">Bereitstellen von Microsoft Defender für Endpunkt unter macOS mit Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6187f-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6187f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6187f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6187f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6187f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6187f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6187f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6187f-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="6187f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6187f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6187f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6187f-110">Erfahren Sie, wie Sie Microsoft Defender für Endpunkt unter macOS mit Jamf Pro bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6187f-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="6187f-111">Wenn Sie macOS- (10.15.4) oder neuere Versionen von macOS verwenden, finden Sie weitere Informationen unter ["Neue Konfigurationsprofile für macOS- und neuere Versionen von macOS".](/microsoft-365/security/defender-endpoint/mac-sysext-policies)</span><span class="sxs-lookup"><span data-stu-id="6187f-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="6187f-112">Dies ist ein mehrstufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="6187f-112">This is a multi step process.</span></span> <span data-ttu-id="6187f-113">Sie müssen alle folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6187f-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="6187f-114">Melden Sie sich beim Jamf-Portal an.</span><span class="sxs-lookup"><span data-stu-id="6187f-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="6187f-115">Einrichten der Microsoft Defender für Endpunkt auf macOS-Gerätegruppen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6187f-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="6187f-116">Einrichten der Microsoft Defender für Endpunkt unter macOS-Richtlinien in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6187f-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="6187f-117">Registrieren von Microsoft Defender für Endpunkt auf macOS-Geräten bei Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6187f-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




