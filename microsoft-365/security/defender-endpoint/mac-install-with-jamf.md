---
title: Bereitstellen von Microsoft Defender ATP für macOS mit Jamf Pro
description: Bereitstellen von Microsoft Defender ATP für macOS mit Jamf Pro
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 0d4d0e46bf563c392d1c00f00491ec5511ef0f92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062287"
---
# <a name="deploying-microsoft-defender-for-endpoint-for-macos-with-jamf-pro"></a><span data-ttu-id="a97cc-104">Bereitstellen von Microsoft Defender for Endpoint für macOS mit Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a97cc-104">Deploying Microsoft Defender for Endpoint for macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a97cc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a97cc-105">**Applies to:**</span></span>
- [<span data-ttu-id="a97cc-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a97cc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a97cc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a97cc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a97cc-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a97cc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a97cc-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a97cc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a97cc-110">Erfahren Sie, wie Sie Microsoft Defender for Endpoint für macOS mit Jamf Pro bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a97cc-110">Learn how to deploy Microsoft Defender for Endpoint for macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="a97cc-111">Wenn Sie macOS Catalina (10.15.4) oder neuere Versionen von macOS verwenden, lesen Sie Neue Konfigurationsprofile für [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)und neuere Versionen von macOS .</span><span class="sxs-lookup"><span data-stu-id="a97cc-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="a97cc-112">Dies ist ein mehrstufiger Prozess.</span><span class="sxs-lookup"><span data-stu-id="a97cc-112">This is a multi step process.</span></span> <span data-ttu-id="a97cc-113">Sie müssen alle folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a97cc-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="a97cc-114">Anmelden beim Jamf-Portal</span><span class="sxs-lookup"><span data-stu-id="a97cc-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="a97cc-115">Einrichten der Microsoft Defender for Endpoint für macOS-Gerätegruppen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a97cc-115">Setup the Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="a97cc-116">Einrichten der Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a97cc-116">Setup the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="a97cc-117">Registrieren des Microsoft Defender for Endpoint für macOS-Geräte bei Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a97cc-117">Enroll the Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




