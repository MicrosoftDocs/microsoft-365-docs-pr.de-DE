---
title: Behandeln von Leistungsproblemen für Microsoft Defender ATP für Mac
description: Behandeln von Leistungsproblemen in Microsoft Defender ATP für Mac.
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
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062223"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Behandeln von Leistungsproblemen für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpoint für Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dieses Thema enthält einige allgemeine Schritte, mit deren Unterstützung Leistungsprobleme im Zusammenhang mit Microsoft Defender for Endpoint für Mac eindr werden können.

Der Echtzeitschutz (Real-Time Protection, RTP) ist ein Feature von Microsoft Defender for Endpoint für Mac, das Ihr Gerät kontinuierlich überwacht und vor Bedrohungen schützt. Es besteht aus Datei- und Prozessüberwachung und anderen Heuristiken.

Abhängig von den ausgeführten Anwendungen und den Gerätemerkmalen kann es bei der Ausführung von Microsoft Defender for Endpoint für Mac zu einer suboptimalen Leistung kommen. Insbesondere Anwendungen oder Systemprozesse, die über einen kurzen Zeitraum auf viele Ressourcen zugreifen, können zu Leistungsproblemen in Microsoft Defender for Endpoint für Mac führen.

Die folgenden Schritte können verwendet werden, um diese Probleme zu beheben und zu beheben:

1. Deaktivieren Sie den Echtzeitschutz mithilfe einer der folgenden Methoden, und beobachten Sie, ob sich die Leistung verbessert. Dieser Ansatz hilft, die Leistungsprobleme von Microsoft Defender for Endpoint für Mac zu verengt.

    Wenn Ihr Gerät nicht von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz mithilfe einer der folgenden Optionen deaktiviert werden:

    - Über die Benutzeroberfläche. Öffnen Sie Microsoft Defender for Endpoint für Mac, und navigieren Sie zu **Einstellungen verwalten.**

      ![Verwalten des Screenshots für den Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Vom Terminal aus. Aus Sicherheitsgründen erfordert dieser Vorgang eine Erhöhung.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Wenn Ihr Gerät von Ihrer Organisation verwaltet wird, kann der Echtzeitschutz von Ihrem Administrator mithilfe der Anweisungen unter Festlegen von Einstellungen für [Microsoft Defender for Endpoint für Mac deaktiviert werden.](mac-preferences.md)

2. Öffnen Sie finder, und navigieren Sie zu   >  **Anwendungsprogramme**. Öffnen **Sie Aktivitätsüberwachung,** und analysieren Sie, welche Anwendungen die Ressourcen auf Ihrem System verwenden. Typische Beispiele sind Softwareupdater und Compiler.

3. Konfigurieren Sie Microsoft Defender für Endpoint für Mac mit Ausschlüssen für die Prozesse oder Datenträgerspeicherorte, die zu Leistungsproblemen beitragen, und aktivieren Sie den Echtzeitschutz erneut.

    Weitere Informationen finden Sie unter Configure [and validate exclusions for Microsoft Defender for Endpoint for Mac.](mac-exclusions.md)
