---
title: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender ATP für Linux
keywords: microsoft, defender, atp, linux, cloud, connectivity, communication
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77ab7bbbb156165f26538cf3d14eae1e5e76d92c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587539"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint für Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Ausführen des Konnektivitätstests

Um zu testen, ob Defender for Endpoint für Linux mit den aktuellen Netzwerkeinstellungen mit der Cloud kommunizieren kann, führen Sie einen Verbindungstest über die Befehlszeile aus:

```bash
mdatp connectivity test
```

Erwartete Ausgabe:

```output
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

Wenn der [Konnektivitätstest](microsoft-defender-endpoint-linux.md#network-connections) fehlschlägt, überprüfen Sie, ob das Gerät über Internetzugriff verfügt und ob einer der vom Produkt benötigten Endpunkte von einem Proxy oder einer Firewall blockiert wird.

Fehler mit dem Lockenfehler 35 oder 60 geben die Ablehnung des Anheftens des Zertifikats an. Überprüfen Sie, ob die Verbindung unter SSL- oder HTTPS-Prüfung steht. Wenn ja, fügen Sie Microsoft Defender for Endpoint der Liste der zulässigen Daten hinzu.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Problembehandlung bei Umgebungen ohne Proxy oder mit transparentem Proxy

Führen Sie den folgenden Befehl im Terminal aus, um zu testen, ob eine Verbindung in einer Umgebung ohne Proxy oder mit einem transparenten Proxy nicht blockiert ist:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Die Ausgabe dieses Befehls sollte wie die folgenden sein:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Problembehandlung bei Umgebungen mit statischem Proxy

> [!WARNING]
> PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt. Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.
>
> Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt. Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint für Linux direkt an die relevanten URLs ohne Abfangen zu übergeben. Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.

Wenn ein statischer Proxy erforderlich ist, fügen Sie dem obigen Befehl einen Proxyparameter hinzu, der der Proxyadresse und dem Port `proxy_address:port` entspricht:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Stellen Sie sicher, dass Sie dieselbe Proxyadresse und denselben Port wie in der Datei `/lib/system/system/mdatp.service` konfiguriert verwenden. Überprüfen Sie die Proxykonfiguration, wenn fehler aus den obigen Befehlen auftreten.

> [!WARNING]
> Der statische Proxy kann nicht über eine systemweite `HTTPS_PROXY` Umgebungsvariable konfiguriert werden. Stellen Sie stattdessen sicher, `HTTPS_PROXY` dass dies ordnungsgemäß in der Datei festgelegt `/lib/system/system/mdatp.service` ist.

Um einen statischen Proxy verwenden zu können, `mdatp.service` muss die Datei geändert werden. Stellen Sie sicher, dass `#` der Vorschub entfernt wird, um die Auskommentierung der folgenden Zeile aus zu `/lib/systemd/system/mdatp.service` entfernen:

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Stellen Sie außerdem sicher, dass die richtige statische Proxyadresse ausgefüllt wird, um zu `address:port` ersetzen.

Wenn diese Datei richtig ist, führen Sie den folgenden Befehl im Terminal aus, um Defender for Endpoint für Linux neu zu laden und die Einstellung weiterzuververmehren:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

Versuchen Sie nach erfolgreichem Erfolg einen weiteren Konnektivitätstest über die Befehlszeile:

```bash
mdatp connectivity test
```

Wenn das Problem weiterhin besteht, wenden Sie sich an den Kundensupport.

## <a name="resources"></a>Ressourcen

- Weitere Informationen zum Konfigurieren des Produkts für die Verwendung eines statischen Proxys finden Sie unter [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).
