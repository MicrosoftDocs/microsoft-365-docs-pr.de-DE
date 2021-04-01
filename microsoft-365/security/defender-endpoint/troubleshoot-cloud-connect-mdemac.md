---
title: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint für Mac
description: In diesem Thema wird beschrieben, wie Sie Probleme mit der Cloudkonnektivität für Microsoft Defender for Endpoint für Mac beheben.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476685"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint für Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattform** macOS

In diesem Thema wird beschrieben, wie Sie Probleme mit der Cloudkonnektivität für Microsoft Defender for Endpoint für Mac beheben.

## <a name="run-the-connectivity-test"></a>Ausführen des Konnektivitätstests
Um zu testen, ob Defender for Endpoint für Mac mit den aktuellen Netzwerkeinstellungen mit der Cloud kommunizieren kann, führen Sie einen Verbindungstest über die Befehlszeile aus:

```Bash
mdatp connectivity test
```

Erwartete Ausgabe:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Wenn der [Konnektivitätstest](microsoft-defender-endpoint-mac.md#network-connections) fehlschlägt, überprüfen Sie, ob das Gerät über Internetzugriff verfügt und ob einer der vom Produkt benötigten Endpunkte von einem Proxy oder einer Firewall blockiert wird.

Fehler mit dem Lockenfehler 35 oder 60 deuten auf die Ablehnung des Anheftens von Zertifikaten hin, was auf ein potenzielles Problem bei der SSL- oder HTTPS-Überprüfung hinweist. Weitere Informationen finden Sie unter Anweisungen zur KONFIGURATION der SSL-Überprüfung.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Problembehandlung bei Umgebungen ohne Proxy oder mit Proxy autoconfig (PAC) oder mit Web Proxy AutoDiscovery Protocol (WPAD)
Verwenden Sie das folgende Verfahren, um zu testen, ob eine Verbindung in einer Umgebung ohne Proxy oder mit Proxy autoconfig (PAC) oder mit Web Proxy AutoDiscovery Protocol (WPAD) nicht blockiert wird.

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.

> [!WARNING]
> Authentifizierte Proxys werden nicht unterstützt. Stellen Sie sicher, dass nur PAC, WPAD oder ein statischer Proxy verwendet wird. Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt. Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Microsoft Defender for Endpoint für Mac direkt an die relevanten URLs ohne Abfangen zu übergeben. Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.
So testen Sie, ob eine Verbindung nicht blockiert ist: In einem Browser wie Microsoft Edge für Mac oder Safari öffnen https://x.cp.wd.microsoft.com/api/report und https://cdn.x.cp.wd.microsoft.com/ping .

Führen Sie optional im Terminal den folgenden Befehl aus:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

Die Ausgabe dieses Befehls sollte wie die folgenden sein:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
