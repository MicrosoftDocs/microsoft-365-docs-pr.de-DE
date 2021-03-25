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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066431"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Behandeln von Lizenzproblemen für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpoint für Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Während Sie Microsoft Defender for Endpoint [](mac-install-manually.md) für [Mac](microsoft-defender-endpoint-mac.md) und manuelle Bereitstellungstests oder einen Proof Of Concept (PoC) durchführen, wird möglicherweise der folgende Fehler angezeigt:

![Abbildung des Lizenzfehlers](images/no-license-found.png)

**Nachricht:** 

Keine Lizenz gefunden

Es sieht so aus, als verfügt Ihre Organisation nicht über eine Lizenz für Microsoft 365 Enterprise-Abonnements.

Weitere Informationen erhalten Sie von Ihrem Administrator.

**Ursache:** 

Sie haben das Microsoft Defender for Endpoint für macOS-Paket ("Installationspaket herunterladen") bereitgestellt und/oder installiert, aber möglicherweise haben Sie das Konfigurationsskript ("Onboardingpaket herunterladen") ausgeführt.

**Lösung:**

Befolgen Sie die MicrosoftDefenderATPOnboardingMacOs.py, die hier dokumentiert sind: [Clientkonfiguration](mac-install-manually.md#client-configuration)

