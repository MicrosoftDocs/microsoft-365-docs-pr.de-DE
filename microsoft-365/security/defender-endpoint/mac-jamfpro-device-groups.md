---
title: Einrichten von Gerätegruppen in Jamf Pro
description: Informationen zum Einrichten von Gerätegruppen in Jamf Pro für Microsoft Defender for Endpoint unter macOS
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933805"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="64057-104">Einrichten von Microsoft Defender for Endpoint auf macOS-Gerätegruppen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="64057-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64057-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64057-105">**Applies to:**</span></span>
- [<span data-ttu-id="64057-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64057-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64057-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64057-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64057-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="64057-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64057-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64057-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="64057-110">Richten Sie die Gerätegruppen ein, die gruppenrichtlinienorganisationseinheit (OUs), die Gerätesammlung von Microsoft Endpoint Configuration Manager und die Gerätegruppen von Intune ähneln.</span><span class="sxs-lookup"><span data-stu-id="64057-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="64057-111">Navigieren Sie zu **Statische Computergruppen**.</span><span class="sxs-lookup"><span data-stu-id="64057-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="64057-112">Wählen Sie **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="64057-112">Select **New**.</span></span> 

    ![Bild von Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="64057-114">Geben Sie einen Anzeigenamen an, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="64057-114">Provide a display name and select **Save**.</span></span>

    ![Bild von Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="64057-116">Nun wird die **Computergruppe von Contoso unter** Statische **Computergruppen angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="64057-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Bild von Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="64057-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="64057-118">Next step</span></span>
- [<span data-ttu-id="64057-119">Einrichten von Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="64057-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
