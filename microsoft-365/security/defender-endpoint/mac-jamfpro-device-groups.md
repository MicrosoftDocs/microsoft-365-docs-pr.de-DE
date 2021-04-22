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
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Einrichten von Microsoft Defender for Endpoint auf macOS-Gerätegruppen in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Richten Sie die Gerätegruppen ein, die gruppenrichtlinienorganisationseinheit (OUs), die Gerätesammlung von Microsoft Endpoint Configuration Manager und die Gerätegruppen von Intune ähneln.

1. Navigieren Sie zu **Statische Computergruppen**.

2. Wählen Sie **Neu** aus. 

    ![Bild von Jamf Pro1](images/jamf-pro-static-group.png)

3. Geben Sie einen Anzeigenamen an, und wählen Sie **Speichern aus.**

    ![Bild von Jamf Pro2](images/jamfpro-machine-group.png)

4. Nun wird die **Computergruppe von Contoso unter** Statische **Computergruppen angezeigt.**

    ![Bild von Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Nächster Schritt
- [Einrichten von Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro](mac-jamfpro-policies.md)
