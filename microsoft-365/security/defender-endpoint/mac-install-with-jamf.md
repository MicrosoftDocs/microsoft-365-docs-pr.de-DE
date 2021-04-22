---
title: Bereitstellen von Microsoft Defender for Endpoint auf macOS mit Jamf Pro
description: Bereitstellen von Microsoft Defender for Endpoint auf macOS mit Jamf Pro
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d102635a284ec5c802e352f097d1632e2f20e166
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929061"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="2a9bd-104">Bereitstellen von Microsoft Defender for Endpoint auf macOS mit Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2a9bd-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2a9bd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2a9bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a9bd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2a9bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a9bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a9bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2a9bd-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2a9bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a9bd-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2a9bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2a9bd-110">Erfahren Sie, wie Sie Microsoft Defender for Endpoint auf macOS mit Jamf Pro bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2a9bd-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="2a9bd-111">Wenn Sie macOS Catalina (10.15.4) oder neuere Versionen von macOS verwenden, lesen Sie Neue Konfigurationsprofile für [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)und neuere Versionen von macOS .</span><span class="sxs-lookup"><span data-stu-id="2a9bd-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="2a9bd-112">Dies ist ein mehrstufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="2a9bd-112">This is a multi step process.</span></span> <span data-ttu-id="2a9bd-113">Sie müssen alle folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2a9bd-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="2a9bd-114">Anmelden beim Jamf-Portal</span><span class="sxs-lookup"><span data-stu-id="2a9bd-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="2a9bd-115">Einrichten der Microsoft Defender for Endpoint auf macOS-Gerätegruppen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2a9bd-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="2a9bd-116">Einrichten der Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2a9bd-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="2a9bd-117">Registrieren von Microsoft Defender for Endpoint auf macOS-Geräten bei Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2a9bd-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




