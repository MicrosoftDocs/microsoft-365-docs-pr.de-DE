---
title: Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint auf dem Mac
description: Behandeln von Lizenzproblemen in Microsoft Defender for Endpoint auf Dem Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244980"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt unter Mac OS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Während Sie Microsoft Defender for Endpoint auf [macOS](microsoft-defender-endpoint-mac.md) und [manuellen](mac-install-manually.md) Bereitstellungstests oder einem Proof Of Concept (PoC) durch führen, wird möglicherweise der folgende Fehler angezeigt:

![Abbildung des Lizenzfehlers](images/no-license-found.png)

**Nachricht:** 

Keine Lizenz gefunden

Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise Abonnement.

Weitere Informationen erhalten Sie von Ihrem Administrator.

**Ursache:** 

Sie haben das Microsoft Defender for Endpoint für macOS-Paket ("Installationspaket herunterladen") bereitgestellt und/oder installiert, aber Möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt, oder Sie haben dem Benutzer keine Lizenz zugewiesen.

**Lösung:**

Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)
