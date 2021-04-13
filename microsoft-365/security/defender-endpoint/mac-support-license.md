---
title: Behandeln von Lizenzproblemen für Microsoft Defender ATP für Mac
description: Behandeln von Lizenzproblemen in Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689113"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender for Endpoint unter macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Während Sie Microsoft Defender for Endpoint auf [macOS](microsoft-defender-endpoint-mac.md) und [manuellen](mac-install-manually.md) Bereitstellungstests oder einem Proof Of Concept (PoC) durch führen, wird möglicherweise der folgende Fehler angezeigt:

![Abbildung des Lizenzfehlers](images/no-license-found.png)

**Nachricht:** 

Keine Lizenz gefunden

Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise-Abonnements.

Weitere Informationen erhalten Sie von Ihrem Administrator.

**Ursache:** 

Sie haben das Microsoft Defender for Endpoint auf macOS-Paket bereitgestellt und/oder installiert ("Installationspaket herunterladen"), aber möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt.

**Lösung:**

Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)

