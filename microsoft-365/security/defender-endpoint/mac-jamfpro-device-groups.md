---
title: Einrichten von Gerätegruppen in Jamf Pro
description: Informationen zum Einrichten von Gerätegruppen in Jamf Pro für Microsoft Defender ATP für macOS
keywords: device, group, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 3e330f135e391214ffe25289d58c2d0de3257be0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062280"
---
# <a name="set-up-microsoft-defender-for-endpoint-for-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="dafd3-104">Einrichten von Microsoft Defender for Endpoint für macOS-Gerätegruppen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="dafd3-104">Set up Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dafd3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="dafd3-105">**Applies to:**</span></span>
- [<span data-ttu-id="dafd3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="dafd3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="dafd3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dafd3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dafd3-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="dafd3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dafd3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="dafd3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="dafd3-110">Richten Sie die Gerätegruppen ein, die gruppenrichtlinienorganisationseinheit (OUs), die Gerätesammlung von Microsoft Endpoint Configuration Manager und die Gerätegruppen von Intune ähneln.</span><span class="sxs-lookup"><span data-stu-id="dafd3-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="dafd3-111">Navigieren Sie zu **Statische Computergruppen**.</span><span class="sxs-lookup"><span data-stu-id="dafd3-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="dafd3-112">Wählen Sie **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="dafd3-112">Select **New**.</span></span> 

    ![Bild von Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="dafd3-114">Geben Sie einen Anzeigenamen an, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="dafd3-114">Provide a display name and select **Save**.</span></span>

    ![Bild von Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="dafd3-116">Nun wird die **Computergruppe von Contoso unter** Statische **Computergruppen angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="dafd3-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Bild von Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="dafd3-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="dafd3-118">Next step</span></span>
- [<span data-ttu-id="dafd3-119">Einrichten von Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="dafd3-119">Set up Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
