---
title: Microsoft Defender für Endpunkt unter Linux – Ermittlung statischer Proxys
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux für statische Proxyermittlung konfiguriert wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, Proxy
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
ms.openlocfilehash: 6dca58070d21271ffc832bcd628679303736f99e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108139"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Konfigurieren von Microsoft Defender für Endpunkt unter Linux für die Ermittlung statischer Proxys

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender für Endpunkt kann einen Proxyserver mithilfe der ```HTTPS_PROXY``` Umgebungsvariablen ermitteln. Diese Einstellung muss **sowohl** zur Installationszeit als auch nach der Installation des Produkts konfiguriert werden.

## <a name="installation-time-configuration"></a>Konfiguration der Installationszeit

Während der Installation muss die ```HTTPS_PROXY``` Umgebungsvariable an den Paket-Manager übergeben werden. Der Paket-Manager kann diese Variable auf eine der folgenden Arten lesen:

- Die ```HTTPS_PROXY``` Variable wird in der folgenden Zeile ```/etc/environment``` definiert:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- Die `HTTPS_PROXY` Variable wird in der globalen Paket-Manager-Konfiguration definiert. In Ubuntu 18.04 können Sie beispielsweise die folgende Zeile hinzufügen `/etc/apt/apt.conf.d/proxy.conf` zu:
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Beachten Sie, dass oben zwei Methoden den Proxy definieren können, der für andere Anwendungen auf Ihrem System verwendet werden soll. Verwenden Sie diese Methode mit Vorsicht oder nur, wenn dies eine allgemeine globale Konfiguration sein soll.
  
- Die `HTTPS_PROXY` Variable wird den Installations- oder Deinstallationsbefehlen vorangestellt. Stellen Sie beispielsweise mit dem APT-Paket-Manager die Variable bei der Installation von Microsoft Defender für Endpunkt wie folgt voran: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Fügen Sie kein Sudo zwischen der Umgebungsvariablendefinition und apt hinzu, andernfalls wird die Variable nicht weitergegeben.

Die `HTTPS_PROXY` Umgebungsvariable kann während der Deinstallation auf ähnliche Weise definiert werden.

Beachten Sie, dass installation and uninstallation not necessarily fail if a proxy is required but not configured. Telemetriedaten werden jedoch nicht übermittelt, und der Vorgang kann aufgrund von Netzwerktimeouts viel länger dauern.

## <a name="post-installation-configuration"></a>Konfiguration nach der Installation
  
Nach der Installation muss die `HTTPS_PROXY` Umgebungsvariable in der Defender für Endpunkt-Dienstdatei definiert werden. Öffnen Sie dazu `/lib/systemd/system/mdatp.service` in einem Text-Editor, während Sie als Stammbenutzer ausgeführt werden. Anschließend können Sie die Variable auf eine von zwei Arten an den Dienst überweisen:

    > [!NOTE]
    > On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.

- Kommentieren Sie die Zeile `#Environment="HTTPS_PROXY=http://address:port"` aus, und geben Sie Ihre statische Proxyadresse an.

- Fügen Sie eine Zeile `EnvironmentFile=/path/to/env/file` hinzu. Dieser Pfad kann auf `/etc/environment` eine oder eine benutzerdefinierte Datei verweisen, von der eine die folgende Zeile hinzufügen muss:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Speichern und schließen Sie die Datei, nachdem Sie die Datei geändert `mdatp.service` haben. Starten Sie den Dienst neu, damit die Änderungen übernommen werden können. In Ubuntu umfasst dies zwei Befehle:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
